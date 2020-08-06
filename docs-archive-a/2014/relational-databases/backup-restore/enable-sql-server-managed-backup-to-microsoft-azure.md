---
title: Configurando SQL Server Backup gerenciado para o Azure | Microsoft Docs
ms.custom: ''
ms.date: 08/04/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 68ebb53e-d5ad-4622-af68-1e150b94516e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9e3b86fde91028106263310aad8a1952fc041a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582469"
---
# <a name="setting-up-sql-server-managed-backup-to-azure"></a><span data-ttu-id="9bbae-102">Configurar o backup gerenciado do SQL Server para Azure</span><span class="sxs-lookup"><span data-stu-id="9bbae-102">Setting up SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="9bbae-103">Este tópico inclui dois tutoriais:</span><span class="sxs-lookup"><span data-stu-id="9bbae-103">This topic includes two tutorials:</span></span>  
  
 <span data-ttu-id="9bbae-104">Configure o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] no nível do banco de dados, habilite a notificação por email e monitore a atividade de backup.</span><span class="sxs-lookup"><span data-stu-id="9bbae-104">Set up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="9bbae-105">Ao configurar o  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] no nível da instância, habilite a notificação por email e monitore a atividade de backup.</span><span class="sxs-lookup"><span data-stu-id="9bbae-105">Setting up  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the instance level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="9bbae-106">Para obter um tutorial sobre como configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] grupos de disponibilidade, confira [configurando SQL Server Backup gerenciado para Microsoft Azure para grupos de disponibilidade](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-106">For a tutorial on setting up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for Availability Groups, see [Setting up SQL Server Managed Backup to Microsoft Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
## <a name="setting-up-ss_smartbackup"></a><span data-ttu-id="9bbae-107">Configurando o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bbae-107">Setting Up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span></span>  
  
### <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><span data-ttu-id="9bbae-108">Habilitar e configurar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="9bbae-108">Enable and Configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="9bbae-109">Este tutorial descreve as etapas necessárias para habilitar e configurar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para um banco de dados (TestDB), seguidas pelas etapas para habilitar o monitoramento do status de integridade do [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9bbae-109">This tutorial describes the steps necessary to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a database (TestDB), followed by steps to enable monitoring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="9bbae-110">**Permissões:**</span><span class="sxs-lookup"><span data-stu-id="9bbae-110">**Permissions:**</span></span>  
  
-   <span data-ttu-id="9bbae-111">Requer associação na função de banco de dados **db_backupoperator** , com permissões **ALTER ANY Credential** e `EXECUTE` permissões em **sp_delete_backuphistory**procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="9bbae-111">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="9bbae-112">Requer permissões **SELECT** na função **smart_admin.fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="9bbae-112">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="9bbae-113">Requer `EXECUTE` permissões no procedimento armazenado **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="9bbae-113">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="9bbae-114">Além disso, requer permissões `VIEW SERVER STATE`, pois chama internamente outros objetos do sistema que exigem essa permissão.</span><span class="sxs-lookup"><span data-stu-id="9bbae-114">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  
  
-   <span data-ttu-id="9bbae-115">Requer `EXECUTE` permissões nos `smart_admin.sp_set_instance_backup` `smart_admin.sp_backup_master_switch` procedimentos armazenados e.</span><span class="sxs-lookup"><span data-stu-id="9bbae-115">Requires `EXECUTE` permissions on the `smart_admin.sp_set_instance_backup` and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  


1.  <span data-ttu-id="9bbae-116">**Criar uma conta de armazenamento Microsoft Azure:** Os backups são armazenados no serviço de armazenamento Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="9bbae-116">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="9bbae-117">Você deve primeiro criar uma conta de armazenamento Microsoft Azure, se ainda não tiver uma conta.</span><span class="sxs-lookup"><span data-stu-id="9bbae-117">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="9bbae-118">SQL Server 2014 usa blobs de página, que são diferentes dos BLOBs de bloco e de acréscimo.</span><span class="sxs-lookup"><span data-stu-id="9bbae-118">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="9bbae-119">Portanto, você deve criar uma conta de uso geral e não uma conta de BLOB.</span><span class="sxs-lookup"><span data-stu-id="9bbae-119">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="9bbae-120">Para saber mais, confira [Sobre as contas de armazenamento do Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="9bbae-120">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="9bbae-121">Anote o nome da conta de armazenamento e as chaves de acesso.</span><span class="sxs-lookup"><span data-stu-id="9bbae-121">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="9bbae-122">O nome da conta de armazenamento e as informações de chave de acesso são usados para criar uma Credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="9bbae-122">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="9bbae-123">A Credencial SQL é usada para realizar a autenticação na conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9bbae-123">The SQL Credential is used to authenticate to the storage account.</span></span>  
 
2.  <span data-ttu-id="9bbae-124">**Criar uma credencial SQL:** Crie uma Credencial do SQL usando o nome da conta de armazenamento como a Identidade e a chave de acesso de armazenamento como a senha.</span><span class="sxs-lookup"><span data-stu-id="9bbae-124">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="9bbae-125">**Verifique se SQL Server Agent serviço foi iniciado e está em execução:**  Inicie SQL Server Agent se ele não estiver em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="9bbae-125">**Ensure SQL Server Agent service is Started and Running:**  Start SQL Server Agent if it is not currently running.</span></span>  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="9bbae-126">requer que o SQL Server Agent esteja em execução na instância para executar operações de backup.</span><span class="sxs-lookup"><span data-stu-id="9bbae-126">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="9bbae-127">Talvez seja necessário definir o SQL Server Agent para ser executado automaticamente, a fim de assegurar que as operações de backup ocorrerão regularmente.</span><span class="sxs-lookup"><span data-stu-id="9bbae-127">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="9bbae-128">**Determinar o período de retenção:** determine o período de retenção dos arquivos de backup.</span><span class="sxs-lookup"><span data-stu-id="9bbae-128">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="9bbae-129">O período de retenção é especificado em dias e pode variar de 1 a 30.</span><span class="sxs-lookup"><span data-stu-id="9bbae-129">The retention period is specified in days and can range from 1 to 30.</span></span>  
  
5.  <span data-ttu-id="9bbae-130">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Inicie o SQL Server Management Studio e conecte-se à instância na qual o banco de dados está instalado.</span><span class="sxs-lookup"><span data-stu-id="9bbae-130">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance where the database is installed.</span></span> <span data-ttu-id="9bbae-131">Na janela de consulta, execute a seguinte instrução após modificar os valores do nome do banco de dados, a Credencial SQL, o período de retenção e as opções de criptografia de acordo com seus requisitos:</span><span class="sxs-lookup"><span data-stu-id="9bbae-131">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="9bbae-132">Para obter mais informações sobre como criar um certificado para criptografia, consulte a etapa **criar um certificado de backup** em [criar um backup criptografado](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-132">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@retention_days=30   
                    ,@credential_name='MyCredential'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
                    ,@enable_backup=1;  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="9bbae-133">está habilitado no banco de dados que você especificou.</span><span class="sxs-lookup"><span data-stu-id="9bbae-133">is now enabled on the database you specified.</span></span> <span data-ttu-id="9bbae-134">Podem ser necessários até 15 minutos para que as operações de backup no banco de dados comecem a ser executadas.</span><span class="sxs-lookup"><span data-stu-id="9bbae-134">It may take up to 15 minutes for the backup operations on the database to start to run.</span></span>  
  
6.  <span data-ttu-id="9bbae-135">**Examinar a Configuração Padrão do Evento Estendido:** examine as configurações do Evento Estendido executando a instrução transact-SQL a seguir.</span><span class="sxs-lookup"><span data-stu-id="9bbae-135">**Review Extended Event Default Configuration:** Review the Extended Event settings by running the following transact-SQL statement.</span></span>  
  
    ```  
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="9bbae-136">Você verá que os eventos de canal Admin, Operacional e Analítico estão habilitados por padrão e não podem ser desabilitados.</span><span class="sxs-lookup"><span data-stu-id="9bbae-136">You should see that Admin, Operational, and Analytical channel events are enabled by default and cannot be disabled.</span></span> <span data-ttu-id="9bbae-137">Isso deve ser suficiente para monitorar os eventos que requerem intervenção manual.</span><span class="sxs-lookup"><span data-stu-id="9bbae-137">This should be sufficient to monitor the events that require manual intervention.</span></span>  <span data-ttu-id="9bbae-138">Você pode habilitar os eventos de depuração, mas os canais de depuração incluem eventos informativos e de depuração que o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] usa para detectar problemas e resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="9bbae-138">You can enable debug events, but the debug channels include informational and debug events that [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] uses to detect issues and solve them.</span></span> <span data-ttu-id="9bbae-139">Para obter mais informações, consulte [monitorar SQL Server Backup gerenciado para Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-139">For more information, see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
7.  <span data-ttu-id="9bbae-140">**Habilitar e configurar a notificação do status de integridade:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] tem um procedimento armazenado que cria um trabalho de agente para enviar notificações por email sobre erros ou avisos que possam exigir atenção.</span><span class="sxs-lookup"><span data-stu-id="9bbae-140">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span> <span data-ttu-id="9bbae-141">As etapas a seguir descrevem o processo para habilitar e configurar notificações por email:</span><span class="sxs-lookup"><span data-stu-id="9bbae-141">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="9bbae-142">Configure o Database Mail se ele ainda não estiver habilitado na instância.</span><span class="sxs-lookup"><span data-stu-id="9bbae-142">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="9bbae-143">Para obter mais informações, consulte [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-143">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="9bbae-144">Configure o SQL Server Agent Notification para usar o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="9bbae-144">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="9bbae-145">Para obter mais informações, consulte [Configurar o SQL Server Agent Mail para usar o Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-145">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="9bbae-146">**Habilitar notificações por email para receber avisos e erros de backup:** Na janela de consulta, execute as seguintes instruções Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="9bbae-146">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email1;email2>'  
  
        ```  
  
         <span data-ttu-id="9bbae-147">Para obter mais informações e um script de exemplo completo, consulte [monitorar SQL Server Backup gerenciado para Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-147">For more information, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
8.  <span data-ttu-id="9bbae-148">**Exibir arquivos de backup na Conta de Armazenamento do Microsoft Azure:** conecte-se à conta de armazenamento no SQL Server Management Studio ou no Portal de Gerenciamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="9bbae-148">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="9bbae-149">Você verá um contêiner para a instância do SQL Server que hospeda o banco de dados que configurou para usar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bbae-149">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="9bbae-150">Você também poderá consultar um banco de dados e um backup de log 15 minutos depois de habilitar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9bbae-150">You may also see a database and a log backup within 15 minutes of enabling [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the database.</span></span>  
  
9. <span data-ttu-id="9bbae-151">**Monitorar o Status de Integridade:**  Realize o monitoramento por meio das notificações por email configuradas anteriormente ou monitore de forma ativa os eventos registrados em log.</span><span class="sxs-lookup"><span data-stu-id="9bbae-151">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="9bbae-152">Estes são alguns exemplos de instruções Transact-SQL usados para exibir os eventos:</span><span class="sxs-lookup"><span data-stu-id="9bbae-152">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    -- to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="9bbae-153">As etapas descritas nesta seção destinam-se especificamente à configuração do [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] pela primeira vez no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9bbae-153">The steps described in this section are specifically for configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the first time on the database.</span></span> <span data-ttu-id="9bbae-154">Você pode modificar as configurações existentes usando o mesmo procedimento armazenado do sistema **smart_admin.sp_set_db_backup** e fornecer os novos valores.</span><span class="sxs-lookup"><span data-stu-id="9bbae-154">You can modify the existing configurations using the same system stored procedure **smart_admin.sp_set_db_backup** and provide the new values.</span></span> <span data-ttu-id="9bbae-155">Para obter mais informações, consulte [SQL Server Backup gerenciado para Microsoft Azure-configurações de armazenamento e retenção](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-155">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span></span>  
  
### <a name="enable-ss_smartbackup-for-the-instance-with-default-settings"></a><span data-ttu-id="9bbae-156">Habilitar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para a instância com configurações padrão</span><span class="sxs-lookup"><span data-stu-id="9bbae-156">Enable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the Instance with Default Settings</span></span>  
 <span data-ttu-id="9bbae-157">Este tutorial descreve as etapas para habilitar e configurar [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] o para a instância do, ' MyInstance ', \\ .</span><span class="sxs-lookup"><span data-stu-id="9bbae-157">This tutorial describes the steps to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the instance, 'MyInstance',\\.</span></span> <span data-ttu-id="9bbae-158">Inclui etapas para habilitar o monitoramento do status de integridade do [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9bbae-158">It includes steps to enable monitoring the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="9bbae-159">**Permissões:**</span><span class="sxs-lookup"><span data-stu-id="9bbae-159">**Permissions:**</span></span>  
  
-   <span data-ttu-id="9bbae-160">Requer associação na função de banco de dados **db_backupoperator** , com permissões **ALTER ANY Credential** e `EXECUTE` permissões em **sp_delete_backuphistory**procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="9bbae-160">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="9bbae-161">Requer permissões **SELECT** na função **smart_admin.fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="9bbae-161">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="9bbae-162">Requer `EXECUTE` permissões no procedimento armazenado **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="9bbae-162">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="9bbae-163">Além disso, requer permissões `VIEW SERVER STATE`, pois chama internamente outros objetos do sistema que exigem essa permissão.</span><span class="sxs-lookup"><span data-stu-id="9bbae-163">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  


1.  <span data-ttu-id="9bbae-164">**Criar uma conta de armazenamento Microsoft Azure:** Os backups são armazenados no serviço de armazenamento Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="9bbae-164">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="9bbae-165">Você deve primeiro criar uma conta de armazenamento Microsoft Azure, se ainda não tiver uma conta.</span><span class="sxs-lookup"><span data-stu-id="9bbae-165">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="9bbae-166">SQL Server 2014 usa blobs de página, que são diferentes dos BLOBs de bloco e de acréscimo.</span><span class="sxs-lookup"><span data-stu-id="9bbae-166">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="9bbae-167">Portanto, você deve criar uma conta de uso geral e não uma conta de BLOB.</span><span class="sxs-lookup"><span data-stu-id="9bbae-167">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="9bbae-168">Para saber mais, confira [Sobre as contas de armazenamento do Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="9bbae-168">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="9bbae-169">Anote o nome da conta de armazenamento e as chaves de acesso.</span><span class="sxs-lookup"><span data-stu-id="9bbae-169">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="9bbae-170">O nome da conta de armazenamento e as informações de chave de acesso são usados para criar uma Credencial SQL.</span><span class="sxs-lookup"><span data-stu-id="9bbae-170">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="9bbae-171">A Credencial SQL é usada para realizar a autenticação na conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9bbae-171">The SQL Credential is used to authenticate to the storage account.</span></span>  
  
2.  <span data-ttu-id="9bbae-172">**Criar uma credencial SQL:** Crie uma Credencial do SQL usando o nome da conta de armazenamento como a Identidade e a chave de acesso de armazenamento como a senha.</span><span class="sxs-lookup"><span data-stu-id="9bbae-172">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="9bbae-173">**Garantir que o serviço SQL Server Agent foi iniciado e está em execução:** Inicie o SQL Server Agent se ele não estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="9bbae-173">**Ensure SQL Server Agent service is Started and Running:** Start SQL Server Agent if it is not currently running.</span></span> [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="9bbae-174">requer que o SQL Server Agent esteja em execução na instância para executar operações de backup.</span><span class="sxs-lookup"><span data-stu-id="9bbae-174">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="9bbae-175">Talvez seja necessário definir o SQL Server Agent para ser executado automaticamente, a fim de assegurar que as operações de backup ocorrerão regularmente.</span><span class="sxs-lookup"><span data-stu-id="9bbae-175">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="9bbae-176">**Determinar o período de retenção:** determine o período de retenção dos arquivos de backup.</span><span class="sxs-lookup"><span data-stu-id="9bbae-176">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="9bbae-177">O período de retenção é especificado em dias e pode variar de 1 a 30.</span><span class="sxs-lookup"><span data-stu-id="9bbae-177">The retention period is specified in days and can range from 1 to 30.</span></span> <span data-ttu-id="9bbae-178">Depois que o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for habilitado no nível da instância com os valores padrão, os novos bancos de dados criados depois herdarão as configurações.</span><span class="sxs-lookup"><span data-stu-id="9bbae-178">Once [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is enabled at the instance level with the defaults all new databases created thereafter will inherit the settings.</span></span> <span data-ttu-id="9bbae-179">Somente os bancos de dados definidos para modelos de recuperação completa ou bulk-logged têm suporte e serão configuradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9bbae-179">Only databases that are set to full or bulk-logged recovery models are supported and will be configured automatically.</span></span> <span data-ttu-id="9bbae-180">Você poderá desabilitar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para um banco de dados específico a qualquer momento se não quiser o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configurado.</span><span class="sxs-lookup"><span data-stu-id="9bbae-180">You may disable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a specific database at any time if you  do not want [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configured.</span></span> <span data-ttu-id="9bbae-181">Você também pode alterar a configuração de um banco de dados configurando o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] no nível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9bbae-181">You can also change the configuration for a specific database by configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
5.  <span data-ttu-id="9bbae-182">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Inicie o SQL Server Management Studio e conecte-se à instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9bbae-182">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance of SQL Server.</span></span> <span data-ttu-id="9bbae-183">Na janela de consulta, execute a seguinte instrução após modificar os valores do nome do banco de dados, a Credencial SQL, o período de retenção e as opções de criptografia de acordo com seus requisitos:</span><span class="sxs-lookup"><span data-stu-id="9bbae-183">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and the encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="9bbae-184">Para obter mais informações sobre como criar um certificado para criptografia, consulte a etapa **criar um certificado de backup** em [criar um backup criptografado](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-184">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    Go  
       EXEC smart_admin.sp_set_instance_backup  
                     @enable_backup=1  
                    ,@retention_days=30   
                    ,@credential_name='sqlbackuptoURL'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert';  
    GO  
  
    ```  
  
     <span data-ttu-id="9bbae-185">O [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] agora está habilitado na instância.</span><span class="sxs-lookup"><span data-stu-id="9bbae-185">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is now enabled on the instance.</span></span>  
  
6.  <span data-ttu-id="9bbae-186">Verifique os parâmetros de configuração executando a seguinte instrução Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="9bbae-186">Verify the configuration settings by running the following Transact-SQL statement:</span></span>  
  
    ```  
    Use msdb;  
    GO  
    SELECT * FROM smart_admin.fn_backup_instance_config ();  
  
    ```  
  
7.  <span data-ttu-id="9bbae-187">Criar um novo banco de dados na instância</span><span class="sxs-lookup"><span data-stu-id="9bbae-187">Create a new database on the instance.</span></span> <span data-ttu-id="9bbae-188">Execute a seguinte instrução Transact-SQL para exibir os parâmetros de configuração do [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] para o banco de dados:</span><span class="sxs-lookup"><span data-stu-id="9bbae-188">Run the following Transact-SQL statement to view the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configuration settings for the database:</span></span>  
  
    ```  
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('NewDB')  
    ```  
  
     <span data-ttu-id="9bbae-189">Podem ser necessários até 15 minutos para que configurações apareçam e as operações de backup no banco de dados comecem a ser executadas.</span><span class="sxs-lookup"><span data-stu-id="9bbae-189">It may take up to 15 minutes for the settings to show and backup operations on the database to start to run.</span></span>  
  
8.  <span data-ttu-id="9bbae-190">**Habilitar e configurar a notificação do status de integridade:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] tem um procedimento armazenado que cria um trabalho de agente para enviar notificações por email sobre erros ou avisos que possam exigir atenção.</span><span class="sxs-lookup"><span data-stu-id="9bbae-190">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span>  <span data-ttu-id="9bbae-191">Para receber essas notificações, você deve habilitar a execução do procedimento armazenado que cria um Trabalho do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="9bbae-191">To receive such notifications, you must enable run the stored procedure which creates a SQL Server Agent Job.</span></span> <span data-ttu-id="9bbae-192">As etapas a seguir descrevem o processo para habilitar e configurar notificações por email:</span><span class="sxs-lookup"><span data-stu-id="9bbae-192">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="9bbae-193">Configure o Database Mail se ele ainda não estiver habilitado na instância.</span><span class="sxs-lookup"><span data-stu-id="9bbae-193">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="9bbae-194">Para obter mais informações, consulte [Configure Database Mail](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-194">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="9bbae-195">Configure o SQL Server Agent Notification para usar o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="9bbae-195">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="9bbae-196">Para obter mais informações, consulte [Configurar o SQL Server Agent Mail para usar o Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-196">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="9bbae-197">**Habilitar notificações por email para receber avisos e erros de backup:** Na janela de consulta, execute as seguintes instruções Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="9bbae-197">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email address>'  
  
        ```  
  
         <span data-ttu-id="9bbae-198">Para obter mais informações sobre como monitorar o e um script de exemplo completo, consulte [monitorar SQL Server Backup gerenciado para Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="9bbae-198">For more information about how to monitor, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
9. <span data-ttu-id="9bbae-199">**Exibir arquivos de backup na Conta de Armazenamento do Microsoft Azure:** conecte-se à conta de armazenamento no SQL Server Management Studio ou no Portal de Gerenciamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="9bbae-199">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="9bbae-200">Você verá um contêiner para a instância do SQL Server que hospeda o banco de dados que configurou para usar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bbae-200">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="9bbae-201">Você também poderá consultar um banco de dados e um backup de log 15 minutos depois de criar um novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9bbae-201">You may also see a database and a log backup within 15 minutes of creating a new database.</span></span>  
  
10. <span data-ttu-id="9bbae-202">**Monitorar o Status de Integridade:**  Realize o monitoramento por meio das notificações por email configuradas anteriormente ou monitore de forma ativa os eventos registrados em log.</span><span class="sxs-lookup"><span data-stu-id="9bbae-202">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="9bbae-203">Estes são alguns exemplos de instruções Transact-SQL usados para exibir os eventos:</span><span class="sxs-lookup"><span data-stu-id="9bbae-203">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    --  to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="9bbae-204">As configurações padrão do [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] podem ser substituídas por um banco de dados específico através da definição das configurações no nível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9bbae-204">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] default settings can be overridden for a specific database by configuring the settings specifically at the database level.</span></span> <span data-ttu-id="9bbae-205">Você também pode pausar e retomar o serviço do [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] temporariamente.</span><span class="sxs-lookup"><span data-stu-id="9bbae-205">You can also pause and resume [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] service temporarily.</span></span> <span data-ttu-id="9bbae-206">Para obter mais informações, consulte [SQL Server Backup gerenciado para Microsoft Azure-configurações de armazenamento e retenção](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9bbae-206">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)</span></span>  
  
  
