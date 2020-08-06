---
title: Usar o PowerShell para fazer backup de vários bancos de dados para o serviço de armazenamento de BLOBs do Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: f7008339-e69d-4e20-9265-d649da670460
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95da5d0009f88943029e62960e7429b292242bbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574742"
---
# <a name="use-powershell-to-backup-multiple-databases-to-azure-blob-storage-service"></a><span data-ttu-id="a169b-102">Usar o PowerShell para fazer backup de vários bancos de dados no serviço de Armazenamento de Blobs</span><span class="sxs-lookup"><span data-stu-id="a169b-102">Use PowerShell to Backup Multiple Databases to Azure Blob Storage Service</span></span>
  <span data-ttu-id="a169b-103">Este tópico fornece scripts de exemplo que podem ser usados para automatizar backups no serviço do Armazenamento do Blobs do Azure usando os cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a169b-103">This topic provides sample scripts that can be used to automate backups to Azure Blob storage service using PowerShell cmdlets.</span></span>  
  
## <a name="overview-of-powershell-cmdlets-for-backup-and-restore"></a><span data-ttu-id="a169b-104">Visão geral de cmdlets do PowerShell para backup e restauração</span><span class="sxs-lookup"><span data-stu-id="a169b-104">Overview of PowerShell cmdlets for Backup and Restore</span></span>  
 <span data-ttu-id="a169b-105">`Backup-SqlDatabase` e `Restore-SqlDatabase` são os dois cmdlets principais disponíveis para fazer operações de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="a169b-105">The `Backup-SqlDatabase` and `Restore-SqlDatabase` are the two main cmdlets available to do backup and restore operations.</span></span> <span data-ttu-id="a169b-106">Além disso, há outros cmdlets que podem ser necessários para automatizar backups no armazenamento de Blobs do Windows Azure, como o conjunto de cmdlets **SqlCredential**. A seguir, é apresentada uma lista de cmdlets do PowerShell disponíveis no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que são usados em operações de backup e restauração:</span><span class="sxs-lookup"><span data-stu-id="a169b-106">In addition, there are other cmdlets that may be required to automate backups to Azure Blob storage like the set of **SqlCredential** cmdlets  Following is a list of PowerShell cmdlets available in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that are used in backup and restore operations:</span></span>  
  
 <span data-ttu-id="a169b-107">Backup-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="a169b-107">Backup-SqlDatabase</span></span>  
 <span data-ttu-id="a169b-108">Este cmdlet é usado para criar um backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a169b-108">This cmdlet is used to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Backup.</span></span>  
  
 <span data-ttu-id="a169b-109">Restore-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="a169b-109">Restore-SqlDatabase</span></span>  
 <span data-ttu-id="a169b-110">Usado para restaurar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a169b-110">Used to restore a database.</span></span>  
  
 <span data-ttu-id="a169b-111">New-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="a169b-111">New-SqlCredential</span></span>  
 <span data-ttu-id="a169b-112">Este cmdlet é usado para criar uma Credencial SQL a ser usada para o backup do SQL Server no Armazenamento do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="a169b-112">This cmdlet is used to create a SQL Credential to use for SQL Server Backup to Azure Storage.</span></span> <span data-ttu-id="a169b-113">Para obter mais informações sobre credenciais e seu uso em SQL Server Backup e restauração, consulte [SQL Server Backup e restauração com o serviço de armazenamento de BLOBs do Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="a169b-113">For more information on credentials and their use in SQL Server Backup and Restore, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="a169b-114">Get-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="a169b-114">Get-SqlCredential</span></span>  
 <span data-ttu-id="a169b-115">Este cmdlet é usado para recuperar o objeto Credential e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="a169b-115">This cmdlet is used to retrieve the Credential object and its properties.</span></span>  
  
 <span data-ttu-id="a169b-116">Remove-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="a169b-116">Remove-SqlCredential</span></span>  
 <span data-ttu-id="a169b-117">Exclui o objeto Credencial SQL</span><span class="sxs-lookup"><span data-stu-id="a169b-117">Delete a SQL Credential object</span></span>  
  
 <span data-ttu-id="a169b-118">Set-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="a169b-118">Set-SqlCredential</span></span>  
 <span data-ttu-id="a169b-119">Este cmdlet é usado para alterar ou definir as propriedades do objeto SQL Credential.</span><span class="sxs-lookup"><span data-stu-id="a169b-119">This cmdlet is used to change or set the properties of the SQL Credential Object.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a169b-120">Os cmdlets de Credencial são usados no backup e na restauração para cenários de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="a169b-120">The Credential cmdlets are used in Backup and Restore to Azure Blob storage scenarios.</span></span>  
  
### <a name="powershell-for-multi-database-multi-instance-backup-operations"></a><span data-ttu-id="a169b-121">PowerShell para operações de backup com várias instâncias e bancos de dados</span><span class="sxs-lookup"><span data-stu-id="a169b-121">PowerShell for Multi-Database, Multi-Instance Backup Operations</span></span>  
 <span data-ttu-id="a169b-122">As seções a seguir incluem scripts para várias operações, como a criação de uma Credencial SQL em várias instâncias do SQL Server, fazendo backup de todos os bancos de dados de usuário em uma instância do SQL Server etc.</span><span class="sxs-lookup"><span data-stu-id="a169b-122">The following sections include scripts for various operations like creating a SQL Credential on multiple instance of SQL Server, backing up all user databases in an instance of SQL Server, and such.</span></span> <span data-ttu-id="a169b-123">Você pode usar esses scripts para automatizar ou agendar operações de backup de acordo com os requisitos do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="a169b-123">You can use these scripts to automate or schedule backup operations according to the requirements of your environment.</span></span> <span data-ttu-id="a169b-124">Os scripts fornecidos aqui são exemplos, e podem ser modificados ou estendidos para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="a169b-124">The scripts provided here are examples, and may be modified or extended for your environment.</span></span>  
  
 <span data-ttu-id="a169b-125">Estas são as considerações sobre os exemplos de script:</span><span class="sxs-lookup"><span data-stu-id="a169b-125">The following are considerations for the sample scripts:</span></span>  
  
1.  <span data-ttu-id="a169b-126">**Navegando nos caminhos do SQL Server PowerShell:** o Windows PowerShell implementa cmdlets para navegar no caminho que representa a hierarquia de objetos com suporte em um provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a169b-126">**Navigating SQL Server PowerShell paths:** Windows PowerShell implements cmdlets to navigate the path structure that represents the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="a169b-127">Ao navegar até um nó do caminho, você pode usar outros cmdlets para executar operações básicas no objeto atual.</span><span class="sxs-lookup"><span data-stu-id="a169b-127">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span>  
  
2.  <span data-ttu-id="a169b-128">Cmdlet `Get-ChildItem`: as informações retornadas pelo `Get-ChildItem` dependem do local em um caminho do SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a169b-128">`Get-ChildItem` cmdlet: The information returned by the `Get-ChildItem` depends on the location in a SQL Server PowerShell path.</span></span> <span data-ttu-id="a169b-129">Por exemplo, se o local estiver no nível do computador, esse cmdlet retornará todas as instâncias do mecanismo de banco de dados do SQL Server instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="a169b-129">For example, if the location is at the computer level, this cmdlet returns all the SQL Server database engine instances installed on the computer.</span></span> <span data-ttu-id="a169b-130">Como outro exemplo, se o local estiver no nível do objeto, como os bancos de dados, este cmdlet retornará uma lista de objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a169b-130">As another example, if the location is at the object level such as databases, then this cmdlet returns a list of database objects.</span></span>  <span data-ttu-id="a169b-131">Por padrão, o cmdlet `Get-ChildItem` não retorna nenhum objeto do sistema.</span><span class="sxs-lookup"><span data-stu-id="a169b-131">By default the `Get-ChildItem` cmdlet does not return system objects.</span></span>  <span data-ttu-id="a169b-132">Usando o parâmetro -Force, você poderá ver os objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="a169b-132">Using the -Force parameter you can see the system objects.</span></span>  
  
     <span data-ttu-id="a169b-133">Para obter mais informações, consulte [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span><span class="sxs-lookup"><span data-stu-id="a169b-133">For more information, see [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span></span>  
  
3.  <span data-ttu-id="a169b-134">Embora cada exemplo de código possa ser testado independentemente com a alteração dos valores de variáveis, criar uma conta de armazenamento do Microsoft Azure e de uma Credencial SQL é um pré-requisito e, portanto, necessário em todas as operações de backup e restauração no serviço de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="a169b-134">Although each code sample can be tried independently by changing the variable values, creating an Azure Storage Account and a SQL Credential are prerequisites and required for all backup and restore operations to Azure Blob storage service.</span></span>  
  
### <a name="create-a-sql-credential-on-all-the-instances-of-sql-server"></a><span data-ttu-id="a169b-135">Criar uma Credencial SQL em todas as instâncias do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a169b-135">Create a SQL Credential on All the Instances of SQL Server</span></span>  
 <span data-ttu-id="a169b-136">Há dois scripts de exemplo e ambos criam uma Credencial SQL “mybackupToURL” em todas as instâncias do SQL Server em um computador.</span><span class="sxs-lookup"><span data-stu-id="a169b-136">There are two sample scripts, and both create a SQL Credential "mybackupToURL" on all the instances of SQL Server on a computer.</span></span> <span data-ttu-id="a169b-137">O primeiro exemplo é simples, e cria as credenciais e não intercepta exceções.</span><span class="sxs-lookup"><span data-stu-id="a169b-137">The first example creates is simple and creates the credential and does not trap exceptions.</span></span>  <span data-ttu-id="a169b-138">Por exemplo, se já houvesse uma credencial existente com o mesmo nome em uma das instâncias do computador, o script apresentaria falha.</span><span class="sxs-lookup"><span data-stu-id="a169b-138">For example, if there was already an existing credential with the same name on one of the instances of the computer, the script would fail.</span></span> <span data-ttu-id="a169b-139">O segundo exemplo intercepta erros e permite que o script continue.</span><span class="sxs-lookup"><span data-stu-id="a169b-139">The second example traps errors and allows the script to continue.</span></span>  
  
```powershell
import-module sqlps  
  
# create variables  
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#pipe the instances to new-sqlcredentail cmdlet to create SQL credential  
$instances | New-SqlCredential -Name $credentialName -Identity $storageAccount -Secret $secureString  
```  
  
```powershell
import-module sqlps  
  
# set the parameter values
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#loop through instances and create a SQL credential, output any errors  
ForEach ($instance In $instances)  
{  
    Try  
{  
     New-SqlCredential -Name $credentialName -path "SQLServer:\SQL\$($instance.name)" -Identity $storageAccount -Secret $secureString -ea Stop
}  
Catch [Exception]  
    {
            Write-Host "instance - $($instance.name): "$_.Exception.Message
    }
 }
```  
  
### <a name="remove-a-sql-credential-from-all-the-instances-of-sql-server"></a><span data-ttu-id="a169b-140">Remover uma Credencial SQL de todas as instâncias do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a169b-140">Remove A SQL Credential from All the Instances of SQL Server</span></span>  
 <span data-ttu-id="a169b-141">Este script pode ser usado para remover uma credencial específica de todas as instâncias do SQL Server instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="a169b-141">This script can be used to remove a specific credential from all the instances of SQL Server installed on the computer.</span></span> <span data-ttu-id="a169b-142">Se o objeto Credential não existir em uma instância específica, será exibida uma mensagem de erro, e o script continuará até que todas as instâncias sejam verificadas.</span><span class="sxs-lookup"><span data-stu-id="a169b-142">If the Credential object does not exist on a specific instance, an error message is displayed, and the script continues until all instances are checked.</span></span>  
  
```powershell
import-module sqlps  
  
cd SQLServer:\SQL\COMPUTERNAME  
$credentialName = "mybackuptoURL"  
  
$instances = Get-ChildItem  
  
ForEach ($instance In $instances)  
   {
    Try  
        {  
            $path = "SQLServer:\SQL\$($instance.name)\credentials\$credentialName"   
            Remove-SqlCredential -Path $path -ea stop   
         }  
         Catch [Exception]  
         {  
            Write-Host $_.Exception.Message
        }
    }  
```  
  
### <a name="full-database-backup-for-all-databases-including-system-databases"></a><span data-ttu-id="a169b-143">Backup completo de todos os bancos de dados (INCLUINDO BANCOS DE DADOS DO SISTEMA)</span><span class="sxs-lookup"><span data-stu-id="a169b-143">Full Database Backup for all Databases (INCLUDING SYSTEM DATABASES)</span></span>  
 <span data-ttu-id="a169b-144">O script a seguir cria backup de todos os bancos de dados no computador.</span><span class="sxs-lookup"><span data-stu-id="a169b-144">The following script creates backups of all databases on the computer.</span></span> <span data-ttu-id="a169b-145">Isso inclui os bancos de dados de usuário e o banco de dados de sistema **msdb** .</span><span class="sxs-lookup"><span data-stu-id="a169b-145">This includes both user databases and **msdb** system database.</span></span> <span data-ttu-id="a169b-146">O script filtra os bancos de dados de sistema **tempdb** e **model** .</span><span class="sxs-lookup"><span data-stu-id="a169b-146">The script filters out **tempdb** and **model** system databases.</span></span>  
  
```powershell
import-module sqlps  
# set the parameter values  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the  databases -filter out tempdb and model databases  
  
 ForEach ($instance In $instances)  
 {  
   $path = "sqlserver:\sql\$($instance.name)\databases"  
   $alldatabases = Get-ChildItem -Force -path $path | Where-Object {$_.name -ne "tempdb" -and $_.name -ne "model"}   
   $alldatabases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On -script   
 }
```  
  
### <a name="full-database-backup-for-all-user-databases"></a><span data-ttu-id="a169b-147">Backup completo de TODOS os bancos de dados de usuário</span><span class="sxs-lookup"><span data-stu-id="a169b-147">Full Database Backup for ALL User Databases</span></span>  
 <span data-ttu-id="a169b-148">O script a seguir pode ser usado para fazer backup de todos as bancos de dados de usuário em todas as instâncias do SQL Server no computador.</span><span class="sxs-lookup"><span data-stu-id="a169b-148">The following script can be used to back up all the user databases on all the instances of SQL Server on the computer.</span></span>  
  
```powershell
import-module sqlps
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the user databases  
 ForEach ($instance In $instances)  
 {  
    $databases = dir "sqlserver:\sql\$($instance.name)\databases"  
    $databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On
 }  
```  
  
### <a name="full-database-backup-for-master-and-msdb-system-databases-on-all-the-instances-of-sql-server"></a><span data-ttu-id="a169b-149">Backup completo de banco de dados para MASTER e MSDB (BANCOS DE DADOS DO SISTEMA) em todas as instâncias do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a169b-149">Full Database Backup for MASTER and MSDB (SYSTEM DATABASES) On All the Instances of SQL Server</span></span>  
 <span data-ttu-id="a169b-150">O script a seguir pode ser usado para fazer backup dos bancos de dados **master** e **msdb** em todas as instâncias do SQL Server instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="a169b-150">The following script can be used to back up **master** and **msdb** databases on all the instances of SQL Server installed on the computer.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackupToUrl"  
$sysDbs = "master", "msdb"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
$instances = Get-ChildItem
ForEach ($instance In $instances)  
 {  
      ForEach ($s In $sysdbs)  
     {  
        Backup-SqlDatabase -Database $s -path "sqlserver:\sql\$($instance.name)" -BackupContainer  $backupUrlContainer -SqlCredential $credentialName -Compression On   
}
 } 
```  
  
### <a name="full-database-backup-for-all-user-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="a169b-151">Backup completo de todos os bancos de dados de usuário em uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a169b-151">Full Database Backup for All User Databases on an Instance of SQL Server</span></span>  
 <span data-ttu-id="a169b-152">O script a seguir é usado para fazer backup somente dos bancos de dados de usuário disponíveis em uma instância nomeada do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a169b-152">The following script is used to back up only the user databases available on a named instance of SQL Server.</span></span> <span data-ttu-id="a169b-153">O mesmo script pode ser usado como instância padrão no computador alterando o valor do parâmetro $srvPath.</span><span class="sxs-lookup"><span data-stu-id="a169b-153">The same script can be used for the default instance on the computer by changing the $srvPath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME"  # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
  
#retrieves the database objects for a specific instance  
$databases = dir $srvPath\databases  
  
#backup all the user databases  
$databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
```  
  
### <a name="full-database-backup-for-only-system-databases-master-and-msdb-on-an-instance-of-sql-server"></a><span data-ttu-id="a169b-154">Backup completo somente para os bancos de dados de sistema (MASTER e MSDB) em uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a169b-154">Full Database Backup for Only System Databases (MASTER AND MSDB) On an Instance of SQL Server</span></span>  
 <span data-ttu-id="a169b-155">O script completo a seguir pode ser usado para fazer backup dos bancos de dados **master** e **msdb** em uma instância nomeada do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a169b-155">The full script can be used to back up the **master** and the **msdb** databases on a named instance of SQL Server.</span></span> <span data-ttu-id="a169b-156">O mesmo script pode ser usado como instância padrão no computador alterando o valor do parâmetro $srvPath.</span><span class="sxs-lookup"><span data-stu-id="a169b-156">The same script can be used for the default instance on the computer by changing the $srvpath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME" # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#navigate to instance level  
cd $srvPath  
  
$sysDbs = "master", "msdb"  
ForEach ($s In $sysDbs)
{  
Backup-SqlDatabase -Database $s -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="a169b-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a169b-157">See Also</span></span>
 <span data-ttu-id="a169b-158">[SQL Server Backup e restauração com o serviço de armazenamento de BLOBs do Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server Backup em URL práticas recomendadas e solução de problemas](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="a169b-158">[SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span></span>  
