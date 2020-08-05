---
title: Excluindo arquivos de blob de backup com concessões ativas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 13a8f879-274f-4934-a722-b4677fc9a782
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02aea910589633a5c3ec79e283c757727b4d92cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573140"
---
# <a name="deleting-backup-blob-files-with-active-leases"></a><span data-ttu-id="6f845-102">Excluindo arquivos de blob de backup com arrendamentos ativos</span><span class="sxs-lookup"><span data-stu-id="6f845-102">Deleting Backup Blob Files with Active Leases</span></span>
  <span data-ttu-id="6f845-103">Ao fazer backup ou restaurar do armazenamento do Azure, o SQL Server adquire uma concessão infinita para bloquear o acesso exclusivo ao blob.</span><span class="sxs-lookup"><span data-stu-id="6f845-103">When backing up to or restoring from Azure storage, SQL Server acquires an infinite lease in order to lock exclusive access to the blob.</span></span> <span data-ttu-id="6f845-104">Quando o processo de backup ou restauração for concluído com êxito, a concessão será liberada.</span><span class="sxs-lookup"><span data-stu-id="6f845-104">When the backup or restore process is successfully completed, the lease is released.</span></span> <span data-ttu-id="6f845-105">Se um backup ou uma restauração falhar, o processo de backup tentará limpar qualquer blob inválido.</span><span class="sxs-lookup"><span data-stu-id="6f845-105">If a backup or restore fails, the backup process attempts to clean up any invalid blob.</span></span> <span data-ttu-id="6f845-106">Entretanto, se o backup falhar devido a uma falha de conectividade de rede prolongada ou contínua, o processo de backup pode não ser capaz de obter acesso ao blob e o blob pode permanecer órfão.</span><span class="sxs-lookup"><span data-stu-id="6f845-106">However, if the backup fails due to prolonged or sustained network connectivity failure, the backup  process may not be able gain access to the blob and the blob may remain orphaned.</span></span> <span data-ttu-id="6f845-107">Isso significa que o blob só poderá ser gravado ou excluído quando a concessão for liberada.</span><span class="sxs-lookup"><span data-stu-id="6f845-107">This means that the blob cannot be written to or deleted until the lease is released.</span></span> <span data-ttu-id="6f845-108">Este tópico descreve como liberar a concessão e excluir o blob.</span><span class="sxs-lookup"><span data-stu-id="6f845-108">This topic describes how to release the lease and deleting the blob..</span></span>  
  
 <span data-ttu-id="6f845-109">Para obter mais informações sobre os tipos de arrendamentos, leia este [artigo](https://go.microsoft.com/fwlink/?LinkId=275664).</span><span class="sxs-lookup"><span data-stu-id="6f845-109">For more information on the types of leases, read this [article](https://go.microsoft.com/fwlink/?LinkId=275664).</span></span>  
  
 <span data-ttu-id="6f845-110">Se a operação de backup falhar, isso poderá resultar em um arquivo de backup que não é válido.</span><span class="sxs-lookup"><span data-stu-id="6f845-110">If the backup operation fails, it can result in a backup file that is not valid.</span></span>  <span data-ttu-id="6f845-111">O arquivo de blob de backup pode ter também uma concessão ativa, impedindo que ele seja excluído ou substituído.</span><span class="sxs-lookup"><span data-stu-id="6f845-111">The backup blob file might also have an active lease, preventing it from being deleted or overwritten.</span></span>  <span data-ttu-id="6f845-112">Para excluir ou substituir esses blobs, primeiro a concessão deve ser interrompida. Se houver falhas de backup, recomendamos que você limpe as concessões e exclua os blobs.</span><span class="sxs-lookup"><span data-stu-id="6f845-112">In order to delete or overwrite such blobs, the lease should first be broken.If there are backup failures, we recommend that you clean up leases and delete blobs.</span></span> <span data-ttu-id="6f845-113">Você também pode optar por fazer a limpeza periódica como parte das tarefas de gerenciamento de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="6f845-113">You can also choose cleanup periodically as part of storage management tasks.</span></span>  
  
 <span data-ttu-id="6f845-114">Se houver uma falha na restauração, as restaurações subsequentes não serão bloqueadas e, portanto, a concessão ativa possivelmente não será um problema.</span><span class="sxs-lookup"><span data-stu-id="6f845-114">If there is a restore failure, subsequent restores are not blocked, and therefore the active lease may not be an issue.</span></span> <span data-ttu-id="6f845-115">A interrupção da concessão só é necessária quando você precisa substituir ou excluir o blob.</span><span class="sxs-lookup"><span data-stu-id="6f845-115">Breaking the lease is only necessary when you have to overwrite or delete the blob.</span></span>  
  
## <a name="managing-orphaned-blobs"></a><span data-ttu-id="6f845-116">Gerenciando blobs órfãos</span><span class="sxs-lookup"><span data-stu-id="6f845-116">Managing Orphaned Blobs</span></span>  
 <span data-ttu-id="6f845-117">As etapas a seguir descrevem como efetuar a limpeza após uma atividade de restauração ou backup com falha.</span><span class="sxs-lookup"><span data-stu-id="6f845-117">The follow steps describe how to clean up after failed backup or restore activity.</span></span> <span data-ttu-id="6f845-118">Todas as etapas podem ser executadas por meio dos scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f845-118">All the steps can be done using PowerShell scripts.</span></span> <span data-ttu-id="6f845-119">Um exemplo de código é fornecido na seção a seguir:</span><span class="sxs-lookup"><span data-stu-id="6f845-119">A code example is provided in the following section:</span></span>  
  
1.  <span data-ttu-id="6f845-120">**Identificando os blobs que têm arrendamentos:** Se você tiver um script ou processo que executa os processos de backup, talvez possa capturar a falha no script ou processo e usá-la para limpar os blobs.</span><span class="sxs-lookup"><span data-stu-id="6f845-120">**Identifying blobs that have leases:** If you have a script or a process that runs the backup processes, you might be able to capture the failure within the script or process and use that to clean up the blobs.</span></span>   <span data-ttu-id="6f845-121">Você também pode usar as propriedades LeaseStats e LeastState para identificar os blobs que têm arrendamentos neles.</span><span class="sxs-lookup"><span data-stu-id="6f845-121">You can also use the LeaseStats and LeastState properties to identify the blobs that have leases on them.</span></span> <span data-ttu-id="6f845-122">Após identificar os blobs, recomendamos que você examine a lista e verifique a validade do arquivo de backup antes de excluir o blob.</span><span class="sxs-lookup"><span data-stu-id="6f845-122">Once you have identified the blobs, we recommend that you review the list, verify the validity of the backup file before deleting the blob.</span></span>  
  
2.  <span data-ttu-id="6f845-123">**Interrompendo a concessão:** uma solicitação autorizada pode interromper a concessão sem fornecer uma ID de concessão.</span><span class="sxs-lookup"><span data-stu-id="6f845-123">**Breaking the lease:** An authorized request can break the lease without supplying a lease ID.</span></span> <span data-ttu-id="6f845-124">Consulte [aqui](https://go.microsoft.com/fwlink/?LinkID=275664) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6f845-124">See [here](https://go.microsoft.com/fwlink/?LinkID=275664) for more information.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="6f845-125">O SQL Server emite uma ID de concessão para estabelecer o acesso exclusivo durante a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="6f845-125">SQL Server issues a lease ID to establish exclusive access during the restore operation.</span></span> <span data-ttu-id="6f845-126">A ID de concessão da restauração é BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span><span class="sxs-lookup"><span data-stu-id="6f845-126">The restore lease ID is BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span></span>  
  
3.  <span data-ttu-id="6f845-127">**Excluindo o blob:** para excluir um blob que tem uma concessão ativa, primeiro você deve interromper a concessão.</span><span class="sxs-lookup"><span data-stu-id="6f845-127">**Deleting the Blob:** To delete a blob that has an active lease, you must first break the lease.</span></span>  
  
###  <a name="powershell-script-example"></a><a name="Code_Example"></a><span data-ttu-id="6f845-128">Exemplo de script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f845-128">PowerShell Script Example</span></span>  
 <span data-ttu-id="6f845-129">Importante se você estiver executando o PowerShell 2,0, poderá ter problemas ao carregar o assembly do Microsoft WindowsAzure.Storage.dll. \*\* \* \* \* \* \*\*</span><span class="sxs-lookup"><span data-stu-id="6f845-129">**\*\* Important \*\*** If you are running PowerShell 2.0, you may have problems loading the Microsoft WindowsAzure.Storage.dll assembly.</span></span> <span data-ttu-id="6f845-130">Recomendamos que você atualize o Powershell 3.0 para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="6f845-130">We recommend that you upgrade to Powershell 3.0 to solve the issue.</span></span> <span data-ttu-id="6f845-131">Você também pode usar a seguinte solução para o PowerShell 2.0:</span><span class="sxs-lookup"><span data-stu-id="6f845-131">You may also use the following workaround for PowerShell 2.0:</span></span>  
  
-   <span data-ttu-id="6f845-132">Crie ou modifique o arquivo powershell.exe.config para carregar os assemblies do .NET 2.0 e do .NET 4.0 em runtime com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f845-132">Create or modify the powershell.exe.config file to load .NET 2.0 and .NET 4.0 assemblies at runtime with the following:</span></span>  
  
    ```xml
    <?xml version="1.0"?>
    <configuration>
        <startup useLegacyV2RuntimeActivationPolicy="true">
            <supportedRuntime version="v4.0.30319"/>
            <supportedRuntime version="v2.0.50727"/>
        </startup>
    </configuration>
    ```  
  
 <span data-ttu-id="6f845-133">O exemplo a seguir ilustra a identificação de blobs que têm arrendamentos ativos e sua interrupção.</span><span class="sxs-lookup"><span data-stu-id="6f845-133">The following example illustrates identifying blobs that have active leases and then breaking them.</span></span> <span data-ttu-id="6f845-134">O exemplo também demonstra como filtrar IDs de concessão da versão.</span><span class="sxs-lookup"><span data-stu-id="6f845-134">The example also demonstrates how filter for release lease IDs.</span></span>  
  
 <span data-ttu-id="6f845-135">Dicas para executar este script</span><span class="sxs-lookup"><span data-stu-id="6f845-135">Tips on running this script</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="6f845-136">Se um backup para o serviço de armazenamento de BLOBs do Azure estiver em execução ao mesmo tempo que esse script, o backup poderá falhar, pois esse script interromperá a concessão que o backup está tentando adquirir ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="6f845-136">If a backup to Azure Blob storage service is running at the same time as this script, the backup can fail since this script will break the lease that the backup is trying to acquire at the same time.</span></span> <span data-ttu-id="6f845-137">Recomendamos a execução deste script durante uma janela de manutenção ou quando não houver nenhum backup programado para execução.</span><span class="sxs-lookup"><span data-stu-id="6f845-137">We recommend running this script during a maintenance windows or when no backups are expected to run.</span></span>  
  
1.  <span data-ttu-id="6f845-138">Ao executar esse script, você será solicitado a fornecer valores para a conta de armazenamento, a chave de armazenamento, o contêiner e os parâmetros de caminho e nome do assembly de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="6f845-138">When you run this script, you will be prompted to provide values for the storage account, storage key, container, and the Azure storage assembly path and name parameters.</span></span> <span data-ttu-id="6f845-139">O caminho do armazenamento do assembly é o diretório de instalação da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f845-139">The path of the storage is assembly is the installation directory of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6f845-140">O nome de arquivo do assembly de armazenamento é Microsoft.WindowsAzure.Storage.dll.</span><span class="sxs-lookup"><span data-stu-id="6f845-140">The file name for the storage assembly is Microsoft.WindowsAzure.Storage.dll.</span></span> <span data-ttu-id="6f845-141">O seguinte é um exemplo dos prompts e valores inseridos:</span><span class="sxs-lookup"><span data-stu-id="6f845-141">Following is an example of the prompts and values entered:</span></span>  
  
    ```  
    cmdlet  at command pipeline position 1  
    Supply values for the following parameters:  
    storageAccount: mycloudstorageaccount  
    storageKey: 0BopKY7eEha3gBnistYk+904nf  
    blobContainer: mycontainer   
    storageAssemblyPath: C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Microsoft.WindowsAzure.Storage.dll  
    ```  
  
2.  <span data-ttu-id="6f845-142">Se não houver nenhum blob que tenha bloqueado arrendamentos, você verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="6f845-142">If there are no blobs that have locked leases you should see the following message:</span></span>  
  
     <span data-ttu-id="6f845-143">**Não há nenhum blob com status de concessão bloqueado**</span><span class="sxs-lookup"><span data-stu-id="6f845-143">**There are no blobs with locked lease status**</span></span>  
  
     <span data-ttu-id="6f845-144">Se houver blobs com arrendamentos bloqueados, você verá as seguintes mensagens:</span><span class="sxs-lookup"><span data-stu-id="6f845-144">If there are blobs with locked leases, you should see the following messages:</span></span>  
  
     <span data-ttu-id="6f845-145">**Interrompendo arrendamentos**</span><span class="sxs-lookup"><span data-stu-id="6f845-145">**Breaking Leases**</span></span>  
  
     <span data-ttu-id="6f845-146">**A concessão em \<URL of the Blob> é uma concessão de restauração: você verá esta mensagem somente se tiver um blob com uma concessão de restauração que ainda está ativa.**</span><span class="sxs-lookup"><span data-stu-id="6f845-146">**The lease on \<URL of the Blob> is a restore lease: You will see this message only if you have a blob with a restore lease that is still active.**</span></span>  
  
     <span data-ttu-id="6f845-147">**A concessão em \<URL of the Blob> não é uma concessão de restauração que quebra a concessão em \<URL of the Bob> .**</span><span class="sxs-lookup"><span data-stu-id="6f845-147">**The lease on \<URL of the Blob> is not a restore lease Breaking lease on \<URL of the Bob>.**</span></span>  
  
```powershell
param(  
       [Parameter(Mandatory=$true)]  
       [string]$storageAccount,  
       [Parameter(Mandatory=$true)]  
       [string]$storageKey,  
       [Parameter(Mandatory=$true)]  
       [string]$blobContainer,  
       [Parameter(Mandatory=$true)]  
       [string]$storageAssemblyPath  
)  
  
# Well known Restore Lease ID  
$restoreLeaseId = "BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2"  
  
# Load the storage assembly without locking the file for the duration of the PowerShell session  
$bytes = [System.IO.File]::ReadAllBytes($storageAssemblyPath)  
[System.Reflection.Assembly]::Load($bytes)  
  
$cred = New-Object 'Microsoft.WindowsAzure.Storage.Auth.StorageCredentials' $storageAccount, $storageKey  
$client = New-Object 'Microsoft.WindowsAzure.Storage.Blob.CloudBlobClient' "https://$storageAccount.blob.core.windows.net", $cred  
$container = $client.GetContainerReference($blobContainer)  
  
#list all the blobs  
$allBlobs = $container.ListBlobs()
  
$lockedBlobs = @()  
# filter blobs that are have Lease Status as "locked"  
foreach($blob in $allBlobs)  
{  
    $blobProperties = $blob.Properties
    if($blobProperties.LeaseStatus -eq "Locked")  
    {  
        $lockedBlobs += $blob  
    }  
}  
  
if ($lockedBlobs.Count -eq 0)  
{
    Write-Host " There are no blobs with locked lease status"  
}

if($lockedBlobs.Count -gt 0)  
{  
    Write-Host "Breaking leases"  
    foreach($blob in $lockedBlobs )
    {  
        try  
        {  
            $blob.AcquireLease($null, $restoreLeaseId, $null, $null, $null)  
            Write-Host "The lease on $($blob.Uri) is a restore lease"  
        }  
        catch [Microsoft.WindowsAzure.Storage.StorageException]  
        {  
            if($_.Exception.RequestInformation.HttpStatusCode -eq 409)  
            {  
                Write-Host "The lease on $($blob.Uri) is not a restore lease"  
            }  
        }  
  
        Write-Host "Breaking lease on $($blob.Uri)"  
        $blob.BreakLease($(New-TimeSpan), $null, $null, $null) | Out-Null  
    }  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="6f845-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f845-148">See Also</span></span>  
 [<span data-ttu-id="6f845-149">Solução de problemas e melhores práticas de backup do SQL Server para URL</span><span class="sxs-lookup"><span data-stu-id="6f845-149">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
