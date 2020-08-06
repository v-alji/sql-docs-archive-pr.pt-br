---
title: Práticas recomendadas e solução de problemas de backup do SQL Server para URL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: de676bea-cec7-479d-891a-39ac8b85664f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06127b5e4b422750554c30fae23b6190107cb643
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575176"
---
# <a name="sql-server-backup-to-url-best-practices-and-troubleshooting"></a><span data-ttu-id="ba049-102">Práticas recomendadas e solução de problemas de backup do SQL Server para URL</span><span class="sxs-lookup"><span data-stu-id="ba049-102">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>
  <span data-ttu-id="ba049-103">Este tópico inclui melhores práticas e dicas de solução de problemas para backup e restaurações do SQL Server no serviço de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="ba049-103">This topic includes best practices and troubleshooting tips for SQL Server backup and restores to the Azure Blob service.</span></span>  
  
 <span data-ttu-id="ba049-104">Para obter mais informações sobre como usar o serviço de Armazenamento de Blobs do Azure para operações de backup ou restauração do SQL Server, confira:</span><span class="sxs-lookup"><span data-stu-id="ba049-104">For more information about using Azure Blob storage service for SQL Server backup or restore operations, see:</span></span>  
  
-   [<span data-ttu-id="ba049-105">Backup e restauração do SQL Server no serviço de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="ba049-105">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
-   [<span data-ttu-id="ba049-106">Tutorial: Backup e restauração do SQL Server no serviço de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="ba049-106">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="managing-backups"></a><span data-ttu-id="ba049-107">Gerenciando backups</span><span class="sxs-lookup"><span data-stu-id="ba049-107">Managing Backups</span></span>  
 <span data-ttu-id="ba049-108">A lista a seguir inclui recomendações gerais para gerenciar backups:</span><span class="sxs-lookup"><span data-stu-id="ba049-108">The following list includes general recommendations to manage backups:</span></span>  
  
-   <span data-ttu-id="ba049-109">O nome de arquivo exclusivo para cada backup é recomendável para evitar a substituição acidental dos blobs.</span><span class="sxs-lookup"><span data-stu-id="ba049-109">Unique file name for every backup is recommended to prevent accidentally overwriting the blobs.</span></span>  
  
-   <span data-ttu-id="ba049-110">Ao criar um contêiner, é recomendável definir o nível de acesso para **privado**, de forma que apenas os usuários ou as contas que podem fornecer as informações sobre autenticação necessárias possam ler ou gravar os blobs no contêiner.</span><span class="sxs-lookup"><span data-stu-id="ba049-110">When creating a container, it is recommended that you set the access level to **private**, so only users or accounts that can provide the required authentication information can read or write the blobs in the container.</span></span>  
  
-   <span data-ttu-id="ba049-111">Para SQL Server bancos de dados em uma instância do SQL Server em execução em uma máquina virtual do Azure, use uma conta de armazenamento na mesma região que a máquina virtual para evitar custos de transferência de dados entre regiões.</span><span class="sxs-lookup"><span data-stu-id="ba049-111">For SQL Server databases on an instance of SQL Server running in an Azure Virtual Machine, use a storage account in the same region as the virtual machine to avoid data transfer costs between regions.</span></span> <span data-ttu-id="ba049-112">O uso da mesma região também assegura o desempenho ideal para operações de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="ba049-112">Using the same region also ensures optimal performance for backup and restore operations.</span></span>  
  
-   <span data-ttu-id="ba049-113">A atividade de backup com falha pode resultar em um arquivo de backup inválido.</span><span class="sxs-lookup"><span data-stu-id="ba049-113">Failed backup activity can result in an invalid backup file.</span></span> <span data-ttu-id="ba049-114">Recomendamos a identificação periódica de backup com falha e exclusão dos arquivos de blob.</span><span class="sxs-lookup"><span data-stu-id="ba049-114">We recommend periodic identification of failed backups and deleting the blob files.</span></span> <span data-ttu-id="ba049-115">Para obter mais informações, consulte [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md).</span><span class="sxs-lookup"><span data-stu-id="ba049-115">For more information, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
-   <span data-ttu-id="ba049-116">O uso da opção `WITH COMPRESSION` durante o backup pode minimizar os custos com armazenamento e transações de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="ba049-116">Using the `WITH COMPRESSION` option during backup can minimize your storage costs and storage transaction costs.</span></span> <span data-ttu-id="ba049-117">Ele também pode diminuir o tempo necessário para concluir o processo de backup.</span><span class="sxs-lookup"><span data-stu-id="ba049-117">It can also decrease the time taken to complete the backup process.</span></span>  
  
## <a name="handling-large-files"></a><span data-ttu-id="ba049-118">Tratando arquivos grandes</span><span class="sxs-lookup"><span data-stu-id="ba049-118">Handling Large Files</span></span>  
  
-   <span data-ttu-id="ba049-119">A operação de backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa vários threads a fim de otimizar a transferência de dados para os serviços de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="ba049-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup operation uses multiple threads to optimize data transfer to Azure Blob storage services.</span></span>  <span data-ttu-id="ba049-120">No entanto, o desempenho depende de vários fatores, como largura de banda do ISV e tamanho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ba049-120">However the performance depends on various factors, such as ISV bandwidth and size of the database.</span></span> <span data-ttu-id="ba049-121">Se você pretende fazer backup de bancos de dados ou grupos de arquivos grandes em um banco de dados do SQL Server no local, é recomendável que você teste a taxa de transferência primeiro.</span><span class="sxs-lookup"><span data-stu-id="ba049-121">If you plan to back up large databases or filegroups from an on-premise SQL Server database, it is recommended that you do some throughput testing first.</span></span> <span data-ttu-id="ba049-122">Os [SLA do armazenamento do Azure](https://go.microsoft.com/fwlink/?LinkId=271619) têm tempos de processamento máximos para BLOBs que você pode levar em consideração.</span><span class="sxs-lookup"><span data-stu-id="ba049-122">[Azure storage SLA's](https://go.microsoft.com/fwlink/?LinkId=271619) have maximum processing times for blobs that you can take into consideration.</span></span>  
  
-   <span data-ttu-id="ba049-123">O uso da opção `WITH COMPRESSION`, como recomendado na seção **Gerenciando o backup**, é muito importante ao fazer backup de arquivos grandes.</span><span class="sxs-lookup"><span data-stu-id="ba049-123">Using the `WITH COMPRESSION` option as recommended in the **Managing Backup** section, it is very important when backing up large files.</span></span>  
  
## <a name="troubleshooting-backup-to-or-restore-from-url"></a><span data-ttu-id="ba049-124">Solução de problemas de backup para ou restauração de URL</span><span class="sxs-lookup"><span data-stu-id="ba049-124">Troubleshooting Backup To or Restore from URL</span></span>  
 <span data-ttu-id="ba049-125">Veja a seguir algumas maneiras rápidas de solucionar problemas de erros ao fazer backup ou restauração do serviço de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="ba049-125">Following are some quick ways to troubleshoot errors when backing up to or restoring from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="ba049-126">Para evitar erros devido a opções ou limitações sem suporte, examine a lista de limitações e suporte para comandos de BACKUP e restauração no artigo [SQL Server Backup e restauração com o serviço de armazenamento de BLOBs do Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="ba049-126">To avoid errors due to unsupported options or limitations, review the list of limitations, and support for BACKUP and RESTORE commands information in the [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) article.</span></span>  
  
 <span data-ttu-id="ba049-127">**Erros de autenticação:**</span><span class="sxs-lookup"><span data-stu-id="ba049-127">**Authentication Errors:**</span></span>  
  
-   <span data-ttu-id="ba049-128">COM CREDENTIAL é uma nova opção e é necessária para fazer backup ou restauração a partir do serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="ba049-128">WITH CREDENTIAL is a new option and required to back up to or restore from the Azure Blob storage service.</span></span> <span data-ttu-id="ba049-129">As falhas relacionadas à credencial podem ser as seguintes:</span><span class="sxs-lookup"><span data-stu-id="ba049-129">Failures related to credential could be the following:</span></span>  
  
     <span data-ttu-id="ba049-130">A credencial especificada no comando `BACKUP` ou `RESTORE` não existe.</span><span class="sxs-lookup"><span data-stu-id="ba049-130">The credential specified in the `BACKUP` or `RESTORE` command does not exist.</span></span> <span data-ttu-id="ba049-131">Para evitar esse problema, inclua instruções T-SQL para criar a credencial caso não exista nenhuma na instrução de backup.</span><span class="sxs-lookup"><span data-stu-id="ba049-131">To avoid this issue, you can include T-SQL statements to create the credential if one does not exist in the backup statement.</span></span> <span data-ttu-id="ba049-132">Este é um exemplo que você pode usar:</span><span class="sxs-lookup"><span data-stu-id="ba049-132">The following is an example you can use:</span></span>  
  
    ```  
    IF NOT EXISTS  
    (SELECT * FROM sys.credentials   
    WHERE credential_identity = 'mycredential')  
    CREATE CREDENTIAL <credential name> WITH IDENTITY = 'mystorageaccount'  
    ,SECRET = '<storage access key> ;  
  
    ```  
  
-   <span data-ttu-id="ba049-133">A credencial existem, mas a conta de logon usada para executar o comando de backup não tem permissões para acessar as credenciais.</span><span class="sxs-lookup"><span data-stu-id="ba049-133">The credential exists but the login account that is used to run the backup command does not have permissions to access the credentials.</span></span> <span data-ttu-id="ba049-134">Use uma conta de logon na função **db_backupoperator** com permissões **Alterar qualquer credencial** .</span><span class="sxs-lookup"><span data-stu-id="ba049-134">Use a login account in the **db_backupoperator** role with **Alter any credential** permissions.</span></span>  
  
-   <span data-ttu-id="ba049-135">Verifique o nome da conta de armazenamento e os valores de chave.</span><span class="sxs-lookup"><span data-stu-id="ba049-135">Verify the storage account name and key values.</span></span> <span data-ttu-id="ba049-136">As informações armazenadas na credencial devem corresponder aos valores de propriedade da conta de armazenamento do Azure que você está usando nas operações de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="ba049-136">The information stored in the credential must match the property values of the Azure storage account you are using in the backup and restore operations.</span></span>  
  
 <span data-ttu-id="ba049-137">**Erros/falhas de backup:**</span><span class="sxs-lookup"><span data-stu-id="ba049-137">**Backup Errors/Failures:**</span></span>  
  
-   <span data-ttu-id="ba049-138">Os backups paralelos no mesmo Blob ocasionam a falha de um dos backups com o erro **Falha na inicialização** .</span><span class="sxs-lookup"><span data-stu-id="ba049-138">Parallel backups to the same blob cause one of the backups to fail with an **Initialization failed** error.</span></span>  
  
-   <span data-ttu-id="ba049-139">Use os seguintes logs de erro para facilitar a solução de problemas de backup:</span><span class="sxs-lookup"><span data-stu-id="ba049-139">Use the following error logs to help with troubleshooting backup errors:</span></span>  
  
    -   <span data-ttu-id="ba049-140">Defina o sinalizador de rastreamento 3051 para ativar o registro em um log de erros específico com o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="ba049-140">Set trace flag 3051 to turn on logging to a specific error log with the following format in:</span></span>  
  
         <span data-ttu-id="ba049-141">BackupToUrl- \<instname> - \<dbname> -Action- \<PID> . log, onde \<action> é um de:</span><span class="sxs-lookup"><span data-stu-id="ba049-141">BackupToUrl-\<instname>-\<dbname>-action-\<PID>.log Where \<action> is one of:</span></span>  
  
        -   `DB`  
  
        -   `FILELISTONLY`  
  
        -   `LABELONLY`  
  
        -   `HEADERONLY`  
  
        -   `VERIFYONLY`  
  
    -   <span data-ttu-id="ba049-142">Você também pode encontrar informações examinando o log de eventos do Windows-em logs de aplicativo com o nome ' SQLBackupToUrl '.</span><span class="sxs-lookup"><span data-stu-id="ba049-142">You can also find information by reviewing the Windows Event Log - Under Application logs with the name 'SQLBackupToUrl'.</span></span>  
  
-   <span data-ttu-id="ba049-143">Ao fazer a restauração em um backup compactado, você verá o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="ba049-143">When restoring from a compressed backup, you might see the following error:</span></span>  
  
    -   <span data-ttu-id="ba049-144">**A SqlException 3284 ocorreu. Severidade: 16 Estados: 5**</span><span class="sxs-lookup"><span data-stu-id="ba049-144">**SqlException 3284 occurred. Severity: 16 State: 5**</span></span>  
        <span data-ttu-id="ba049-145">**A marca de mensagem do dispositivo ' https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak ' não está alinhada. Emita novamente a instrução RESTORE com o mesmo tamanho de bloco usado para criar o conjunto de backup: ' 65536 ' é semelhante a um valor possível.**</span><span class="sxs-lookup"><span data-stu-id="ba049-145">**Message Filemark on device 'https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak' is not aligned. Reissue the Restore statement with the same block size used to create the backupset: '65536' looks like a possible value.**</span></span>  
  
         <span data-ttu-id="ba049-146">Para corrigir esse erro, emita novamente a instrução `BACKUP` com `BLOCKSIZE = 65536` especificada.</span><span class="sxs-lookup"><span data-stu-id="ba049-146">To solve this error, reissue the `BACKUP` statement with `BLOCKSIZE = 65536` specified.</span></span>  
  
-   <span data-ttu-id="ba049-147">Erro durante o backup devido a blobs que têm concessão ativa: A atividade de backup com falha pode resultar em blobs com concessões ativas.</span><span class="sxs-lookup"><span data-stu-id="ba049-147">Error during backup due to blobs that have active lease on them: Failed backup activity can result in blobs with active leases.</span></span>  
  
     <span data-ttu-id="ba049-148">Se houver uma nova tentativa de uso de uma instrução de backup, a operação de backup pode falhar com um erro semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="ba049-148">If a backup statement is reattempted, backup operation might fail with an error similar to the following:</span></span>  
  
     <span data-ttu-id="ba049-149">**A opção backup a URL recebeu uma exceção do ponto de extremidade remoto. Mensagem de exceção: o servidor remoto retornou um erro: (412) há uma concessão no blob e nenhuma ID de concessão foi especificada na solicitação**.</span><span class="sxs-lookup"><span data-stu-id="ba049-149">**Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (412) There is currently a lease on the blob and no lease ID was specified in the request**.</span></span>  
  
     <span data-ttu-id="ba049-150">Se for feita uma nova tentativa de uso de uma instrução de restauração em um arquivo de blob de backup que tenha uma concessão ativa, a operação de restauração falhará com um erro semelhante a:</span><span class="sxs-lookup"><span data-stu-id="ba049-150">If a restore statement is attempted on a backup blob file that has an active lease, the restore operation fails with an error similar to the following:</span></span>  
  
     <span data-ttu-id="ba049-151">**Mensagem de exceção: O servidor remoto retornou um erro: (409) Conflito.**</span><span class="sxs-lookup"><span data-stu-id="ba049-151">**Exception Message: The remote server returned an error: (409) Conflict..**</span></span>  
  
     <span data-ttu-id="ba049-152">Quando esse erro ocorre, os arquivos de blob precisam ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="ba049-152">When such error occurs, the blob files need to be deleted.</span></span> <span data-ttu-id="ba049-153">Para obter mais informações sobre esse cenário e como corrigir o problema, consulte [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span><span class="sxs-lookup"><span data-stu-id="ba049-153">For more information on this scenario and how to correct this problem, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
## <a name="proxy-errors"></a><span data-ttu-id="ba049-154">Erros de proxy</span><span class="sxs-lookup"><span data-stu-id="ba049-154">Proxy Errors</span></span>  
 <span data-ttu-id="ba049-155">Se você estiver usando servidores proxy para acessar a Internet, poderá ver os seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="ba049-155">If you are using Proxy Servers to access the internet, you may see the following issues:</span></span>  
  
 <span data-ttu-id="ba049-156">**Conexão limitada por servidores proxy:**</span><span class="sxs-lookup"><span data-stu-id="ba049-156">**Connection throttling by Proxy Servers:**</span></span>  
  
 <span data-ttu-id="ba049-157">Os servidores proxy podem ter configurações que limitam o número de conexões por minuto.</span><span class="sxs-lookup"><span data-stu-id="ba049-157">Proxy Servers can have settings that limit the number of connections per minute.</span></span> <span data-ttu-id="ba049-158">O processo de Backup para URL é multi-threaded e, portanto, pode ir além desse limite.</span><span class="sxs-lookup"><span data-stu-id="ba049-158">The Backup to URL process is a multi-threaded process and hence can go over this limit.</span></span> <span data-ttu-id="ba049-159">Se isso acontecer, o servidor proxy elimina a conexão.</span><span class="sxs-lookup"><span data-stu-id="ba049-159">If this happens, the proxy server kills the connection.</span></span> <span data-ttu-id="ba049-160">Para resolver esse problema, altere as configurações de proxy para que o SQL Server não use o proxy.</span><span class="sxs-lookup"><span data-stu-id="ba049-160">To resolve this issue, change the proxy settings so SQL Server is not using the proxy.</span></span>   <span data-ttu-id="ba049-161">A seguir estão alguns exemplos dos tipos ou mensagens de erro que você pode ver no log de erros:</span><span class="sxs-lookup"><span data-stu-id="ba049-161">Following are some examples of the types or error messages you may see in the error log:</span></span>  
  
-   <span data-ttu-id="ba049-162">Falha ao gravar em " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak ": o backup para a URL recebeu uma exceção do ponto de extremidade remoto.</span><span class="sxs-lookup"><span data-stu-id="ba049-162">Write on "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak" failed: Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="ba049-163">Mensagem de exceção: não é possível ler dados da conexão de transporte: a conexão foi fechada.</span><span class="sxs-lookup"><span data-stu-id="ba049-163">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
-   <span data-ttu-id="ba049-164">Ocorreu um erro de E/S não recuperável no arquivo “http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:” Não foi possível coletar o erro do ponto de extremidade remoto.</span><span class="sxs-lookup"><span data-stu-id="ba049-164">A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Error could not be gathered from Remote Endpoint.</span></span>  
  
     <span data-ttu-id="ba049-165">Msg 3013, Nível 16, Estado 1, Linha 2</span><span class="sxs-lookup"><span data-stu-id="ba049-165">Msg 3013, Level 16, State 1, Line 2</span></span>  
  
     <span data-ttu-id="ba049-166">BACKUP DATABASE está sendo encerrado de forma anormal.</span><span class="sxs-lookup"><span data-stu-id="ba049-166">BACKUP DATABASE is terminating abnormally.</span></span>  
  
-   <span data-ttu-id="ba049-167">BackupIoRequest:: ReportIoError: falha de gravação no dispositivo de backup ' http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak '.</span><span class="sxs-lookup"><span data-stu-id="ba049-167">BackupIoRequest::ReportIoError: write failure on backup device 'http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak'.</span></span> <span data-ttu-id="ba049-168">Erro de sistema operacional: a opção Backup para URL recebeu uma exceção do ponto de extremidade remoto.</span><span class="sxs-lookup"><span data-stu-id="ba049-168">Operating system error Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="ba049-169">Mensagem de exceção: não é possível ler dados da conexão de transporte: a conexão foi fechada.</span><span class="sxs-lookup"><span data-stu-id="ba049-169">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
 <span data-ttu-id="ba049-170">Se você ativar o log detalhado usando o sinalizador de rastreamento 3051, também poderá ver a seguinte mensagem nos logs:</span><span class="sxs-lookup"><span data-stu-id="ba049-170">If you turn on the verbose logging using the trace flag 3051 you may also see the following message in the logs:</span></span>  
  
 <span data-ttu-id="ba049-171">Código de status HTTP 502, Erro de proxy da mensagem de status HTTP (o número de solicitações HTTP por minuto excedeu o limite configurado.</span><span class="sxs-lookup"><span data-stu-id="ba049-171">HTTP status code 502, HTTP Status Message Proxy Error ( The number of HTTP requests per minute exceeded the configured limit.</span></span> <span data-ttu-id="ba049-172">Contate o administrador do ISA Server.</span><span class="sxs-lookup"><span data-stu-id="ba049-172">Contact your ISA Server administrator.</span></span>  <span data-ttu-id="ba049-173">)</span><span class="sxs-lookup"><span data-stu-id="ba049-173">)</span></span>  
  
 <span data-ttu-id="ba049-174">**Configurações de proxy padrão não escolhidas:**</span><span class="sxs-lookup"><span data-stu-id="ba049-174">**Default Proxy Settings not picked up:**</span></span>  
  
 <span data-ttu-id="ba049-175">Às vezes, as configurações padrão não são selecionadas, causando erros de autenticação de proxy como a mostrada abaixo:*ocorreu um erro de e/s não recuperável no arquivo " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: " o backup para a URL recebeu uma exceção do ponto de extremidade remoto. Mensagem de exceção: o servidor remoto retornou um erro: (407) autenticação de* **proxy necessária**.</span><span class="sxs-lookup"><span data-stu-id="ba049-175">Sometimes the default settings are not picked up causing proxy authentication errors such as the one shown below:*A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (407)* **Proxy Authentication Required**.</span></span>  
  
 <span data-ttu-id="ba049-176">Para resolver esse problema, crie um arquivo de configuração que permite que o processo de Backup para URL use as configurações de proxy padrão usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ba049-176">To resolve this issue, create a configuration file that allows the Backup to URL process to use the default proxy settings using the following steps:</span></span>  
  
1.  <span data-ttu-id="ba049-177">Crie um arquivo de configuração chamado BackuptoURL.exe.config com o seguinte xml:</span><span class="sxs-lookup"><span data-stu-id="ba049-177">Create a configuration file named BackuptoURL.exe.config  with the following xml:</span></span>  
  
    ```  
    <?xml version ="1.0"?>  
    <configuration>   
                    <system.net>   
                                    <defaultProxy enabled="true" useDefaultCredentials="true">   
                                                    <proxy usesystemdefault="true" />   
                                    </defaultProxy>   
                    </system.net>  
    </configuration>  
  
    ```  
  
2.  <span data-ttu-id="ba049-178">Coloque o arquivo de configuração na pasta Binn da instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba049-178">Place the configuration file in the Binn folder of the SQL Server Instance.</span></span> <span data-ttu-id="ba049-179">Por exemplo, se o meu SQL Server estiver instalado na unidade C do computador, coloque o arquivo de configuração aqui: *c:\Arquivos de PROGRAMAS\MICROSOFT SQL Server\MSSQL12. \<InstanceName> \MSSQL\Binn*.</span><span class="sxs-lookup"><span data-stu-id="ba049-179">For example, if my SQL Server is installed on the C drive of the machine, place the configuration file here: *C:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Binn*.</span></span>  
  
## <a name="troubleshooting-sql-server-managed-backup-to-azure"></a><span data-ttu-id="ba049-180">Solucionar problemas de backup gerenciado do SQL Server para Azure</span><span class="sxs-lookup"><span data-stu-id="ba049-180">Troubleshooting SQL Server Managed Backup to Azure</span></span>  
 <span data-ttu-id="ba049-181">Como o backup gerenciado do SQL Server é criado com base no Backup para URL, as dicas de solução de problemas descritas nas seções anteriores aplicam-se a bancos de dados ou instâncias que usam o Backup Gerenciado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba049-181">Since SQL Server Managed Backup is built on top of Backup to URL, the troubleshooting tips described in the earlier sections apply to databases or instances using SQL Server Managed Backup.</span></span>  <span data-ttu-id="ba049-182">Informações sobre solução de problemas SQL Server Backup gerenciado para o Azure são descritas em detalhes em [solução de problemas SQL Server Backup gerenciado para o Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="ba049-182">Information about troubleshooting SQL Server Managed Backup to Azure is described in detail in [Troubleshooting SQL Server Managed  Backup to Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba049-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba049-183">See Also</span></span>  
 [<span data-ttu-id="ba049-184">Restaurar de backups armazenados no Azure</span><span class="sxs-lookup"><span data-stu-id="ba049-184">Restoring From Backups Stored in Azure</span></span>](restoring-from-backups-stored-in-microsoft-azure.md)  
  
  
