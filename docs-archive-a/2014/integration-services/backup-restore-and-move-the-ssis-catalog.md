---
title: Fazer backup, restaurar e mover o catálogo do SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bf806aef-8556-48ab-aed5-e95de9a2204e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9de552ddd54168f516f42d9988302561616fd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572665"
---
# <a name="backup-restore-and-move-the-ssis-catalog"></a><span data-ttu-id="76d0a-102">Fazer backup, restaurar e mover o catálogo do SSIS</span><span class="sxs-lookup"><span data-stu-id="76d0a-102">Backup, Restore, and Move the SSIS Catalog</span></span>
  [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] <span data-ttu-id="76d0a-103">inclui o banco de dados SSISDB.</span><span class="sxs-lookup"><span data-stu-id="76d0a-103">includes the SSISDB database.</span></span> <span data-ttu-id="76d0a-104">Você consulta exibições no banco de dados SSISDB para inspecionar objetos, configurações e dados operacionais que são armazenados no catálogo do **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="76d0a-104">You query views in the SSISDB database to inspect objects, settings, and operational data that are stored in the **SSISDB** catalog.</span></span> <span data-ttu-id="76d0a-105">Este tópico fornece instruções para fazer backup do banco de dados e restaurá-lo.</span><span class="sxs-lookup"><span data-stu-id="76d0a-105">This topic provides instructions for backing up and restoring the database.</span></span>  
  
 <span data-ttu-id="76d0a-106">O catálogo do **SSISDB** armazena os pacotes que você implantou no servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d0a-106">The **SSISDB** catalog stores the packages that you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="76d0a-107">Para obter mais informações sobre o catálogo, consulte [Catálogo do SSIS](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="76d0a-107">For more information about the catalog, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
##  <a name="to-back-up-the-ssis-database"></a><a name="backup"></a> <span data-ttu-id="76d0a-108">Para fazer o backup do banco de dados SSIS</span><span class="sxs-lookup"><span data-stu-id="76d0a-108">To Back up the SSIS Database</span></span>  
  
1.  <span data-ttu-id="76d0a-109">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d0a-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="76d0a-110">Faça backup da chave mestra para o banco de dados do SSISDB, usando a instrução Transact-SQL BACKUP MASTER KEY.</span><span class="sxs-lookup"><span data-stu-id="76d0a-110">Back up the master key for the SSISDB database, by using the BACKUP MASTER KEY Transact-SQL statement.</span></span> <span data-ttu-id="76d0a-111">A chave é armazenada em um arquivo que você especifica.</span><span class="sxs-lookup"><span data-stu-id="76d0a-111">The key is stored in a file that you specify.</span></span> <span data-ttu-id="76d0a-112">Use a senha para criptografar a chave mestra no arquivo.</span><span class="sxs-lookup"><span data-stu-id="76d0a-112">Use a password to encrypt the master key in the file.</span></span>  
  
     <span data-ttu-id="76d0a-113">Para obter mais informações sobre a instrução, consulte [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="76d0a-113">For more information about the statement, see [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
     <span data-ttu-id="76d0a-114">No exemplo a seguir, a chave mestra é exportada para o arquivo `c:\temp directory\RCTestInstKey` .</span><span class="sxs-lookup"><span data-stu-id="76d0a-114">In the following example, the master key is exported to the `c:\temp directory\RCTestInstKey` file.</span></span> <span data-ttu-id="76d0a-115">A senha `LS2Setup!` é usada para criptografar a chave mestra.</span><span class="sxs-lookup"><span data-stu-id="76d0a-115">The `LS2Setup!` password is used to encrypt the master key.</span></span>  
  
    ```  
    backup master key to file = 'c:\temp\RCTestInstKey'  
           encryption by password = 'LS2Setup!'  
  
    ```  
  
3.  <span data-ttu-id="76d0a-116">Faça backup do banco de dados do SSISDB usando a caixa de diálogo **Backup de Banco de Dados** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d0a-116">Back up the SSISDB database by using the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="76d0a-117">Para obter mais informações, confira [Como executar backup de um banco de dados (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span><span class="sxs-lookup"><span data-stu-id="76d0a-117">For more information, see [How to: Back Up a Database (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=231812).</span></span>  
  
4.  <span data-ttu-id="76d0a-118">Gere o script de CREATE LOGIN para ##MS_SSISServerCleanupJobLogin ##, fazendo o seguinte.</span><span class="sxs-lookup"><span data-stu-id="76d0a-118">Generate the CREATE LOGIN script for ##MS_SSISServerCleanupJobLogin##, by doing the following.</span></span> <span data-ttu-id="76d0a-119">Para obter mais informações, veja [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="76d0a-119">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="76d0a-120">No Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expanda o nó **Segurança** e expanda o nó **Logons** .</span><span class="sxs-lookup"><span data-stu-id="76d0a-120">In Object Explorer in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Security** node and then expand the **Logins** node.</span></span>  
  
    2.  <span data-ttu-id="76d0a-121">Clique com o botão direito do mouse em **##MS_SSISServerCleanupJobLogin##** e clique em **Script de Logon como** > **CREATE To** > **Nova Janela do Editor de Consultas**.</span><span class="sxs-lookup"><span data-stu-id="76d0a-121">Right-click **##MS_SSISServerCleanupJobLogin##**, and then click **Script Login as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
5.  <span data-ttu-id="76d0a-122">Se você estiver restaurando o banco de dados SSISDB para uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] na qual o catálogo do SSISDB nunca foi criado, gere o script CREATE PROCEDURE para sp_ssis_startup, fazendo o seguinte.</span><span class="sxs-lookup"><span data-stu-id="76d0a-122">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate the CREATE PROCEDURE script for sp_ssis_startup, by doing the following.</span></span> <span data-ttu-id="76d0a-123">Para obter mais informações, consulte [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="76d0a-123">For more information, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
    1.  <span data-ttu-id="76d0a-124">No Pesquisador de objetos, expanda o nó **bancos de dados** e expanda os bancos de **dados do sistema**  >  nó de**master**  >  **Programmability**  >  **procedimentos armazenados** de programação mestre.</span><span class="sxs-lookup"><span data-stu-id="76d0a-124">In Object Explorer, expand the **Databases** node and then expand the **System Databases** > **master** > **Programmability** > **Stored Procedures** node.</span></span>  
  
    2.  <span data-ttu-id="76d0a-125">Clique com o botão direito do mouse em **dbo.sp_ssis_startup**e clique em **Script de Procedimento Armazenado como** > **CREATE To** > **Nova Janela do Editor de Consultas**.</span><span class="sxs-lookup"><span data-stu-id="76d0a-125">Right click **dbo.sp_ssis_startup**, and then click **Script Stored Procedure as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
6.  <span data-ttu-id="76d0a-126">Confirme que o SQL Server Agent foi iniciado</span><span class="sxs-lookup"><span data-stu-id="76d0a-126">Confirm that SQL Server Agent has been started</span></span>  
  
7.  <span data-ttu-id="76d0a-127">Se você estiver restaurando o banco de dados SSISDB para uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] na qual o catálogo do SSISDB nunca foi criado, gere um script para o Trabalho de Manutenção do Servidor SSIS, fazendo o seguinte.</span><span class="sxs-lookup"><span data-stu-id="76d0a-127">If you will be restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, generate a script for the SSIS Server Maintenance Job by doing the following.</span></span> <span data-ttu-id="76d0a-128">O script é criado automaticamente no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent quando o catálogo do SSISDB é criado.</span><span class="sxs-lookup"><span data-stu-id="76d0a-128">The script is created in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent automatically when the SSISDB catalog is created.</span></span> <span data-ttu-id="76d0a-129">O trabalho ajuda a limpar os logs da operação de limpeza fora da janela de retenção e remove versões anteriores de projetos.</span><span class="sxs-lookup"><span data-stu-id="76d0a-129">The job helps clean up cleanup operation logs outside the retention window and remove older versions of projects.</span></span>  
  
    1.  <span data-ttu-id="76d0a-130">No Pesquisador de Objetos, expanda o nó **SQL Server Agent** e, em seguida, expanda o nó **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="76d0a-130">In Object Explorer, expand the **SQL Server Agent** node and then expand the **Jobs** node.</span></span>  
  
    2.  <span data-ttu-id="76d0a-131">Clique com o botão direito do mouse em trabalho de manutenção do servidor SSIS e clique em **trabalho de script como**  >  **criar para a**  >  **nova janela do editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="76d0a-131">Right click SSIS Server Maintenance Job, and then click **Script Job as** > **CREATE To** > **New Query Editor Window**.</span></span>  
  
### <a name="to-restore-the-ssis-database"></a><span data-ttu-id="76d0a-132">Para restaurar o banco de dados SSIS</span><span class="sxs-lookup"><span data-stu-id="76d0a-132">To Restore the SSIS Database</span></span>  
  
1.  <span data-ttu-id="76d0a-133">Se você estiver restaurando o banco de dados SSISDB para uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] onde o catálogo do SSISDB nunca foi criado, habilite o clr (Common Language Runtime) executando o procedimento armazenado sp_configure.</span><span class="sxs-lookup"><span data-stu-id="76d0a-133">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, enable common language runtime (clr) by running the sp_configure stored procedure.</span></span> <span data-ttu-id="76d0a-134">Para obter mais informações, veja [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) e [Opção clr habilitado](https://go.microsoft.com/fwlink/?LinkId=231855).</span><span class="sxs-lookup"><span data-stu-id="76d0a-134">For more information, see [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) and [clr enabled Option](https://go.microsoft.com/fwlink/?LinkId=231855).</span></span>  
  
    ```  
    use master   
           sp_configure 'clr enabled', 1  
           reconfigure  
  
    ```  
  
2.  <span data-ttu-id="76d0a-135">Se você estiver restaurando o banco de dados SSISDB para uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] onde o catálogo do SSISDB nunca foi criado, crie a chave assimétrica e o logon da chave assimétrica e conceda permissão UNSAFE para o logon.</span><span class="sxs-lookup"><span data-stu-id="76d0a-135">If you are restoring the SSISDB database to an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog was never created, create the asymmetric key and the login from the asymmetric key, and grant UNSAFE permission to the login.</span></span>  
  
    ```  
    Create Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey  
           FROM Executable File = 'C:\Program Files\Microsoft SQL Server\110\DTS\Binn\Microsoft.SqlServer.IntegrationServices.Server.dll'  
  
    ```  
  
     [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="76d0a-136">Os procedimentos armazenados CLR exigem que permissões de UNSAFE sejam concedidas ao logon porque o logon exige acesso adicional a recursos restritos, como a API do Microsoft Win32.</span><span class="sxs-lookup"><span data-stu-id="76d0a-136">CLR stored procedures require UNSAFE permissions to be granted to the login because the login requires additional access to restricted resources, such as the Microsoft Win32 API.</span></span> <span data-ttu-id="76d0a-137">Para obter mais informações sobre a permissão de código UNSAFE, consulte [Criando um assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="76d0a-137">For more information about the UNSAFE code permission, see [Creating an Assembly](../relational-databases/clr-integration/assemblies/creating-an-assembly.md).</span></span>  
  
    ```  
    Create Login MS_SQLEnableSystemAssemblyLoadingUser  
           FROM Asymmetric key MS_SQLEnableSystemAssemblyLoadingKey   
  
           Grant unsafe Assembly to MS_SQLEnableSystemAssemblyLoadingUser  
  
    ```  
  
3.  <span data-ttu-id="76d0a-138">Restaure o banco de dados SSISDB do backup usando a caixa de diálogo **Restaurar Banco de Dados** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d0a-138">Restore the SSISDB database from the backup by using the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="76d0a-139">Para obter mais informações, consulte os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="76d0a-139">For more information, see the following topics.</span></span>  
  
    -   [<span data-ttu-id="76d0a-140">Restaurar banco de dados &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="76d0a-140">Restore Database &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="76d0a-141">Restaurar banco de dados &#40;página Arquivos&#41;</span><span class="sxs-lookup"><span data-stu-id="76d0a-141">Restore Database &#40;Files Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-files-page.md)  
  
    -   [<span data-ttu-id="76d0a-142">Restaurar banco de dados &#40;página Opções&#41;</span><span class="sxs-lookup"><span data-stu-id="76d0a-142">Restore Database &#40;Options Page&#41;</span></span>](../relational-databases/backup-restore/restore-database-options-page.md)  
  
4.  <span data-ttu-id="76d0a-143">Execute os scripts que você criou no procedimento [Para fazer backup do banco de dados SSIS](#backup) para ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup e Trabalho de Manutenção do Servidor SSIS.</span><span class="sxs-lookup"><span data-stu-id="76d0a-143">Execute the scripts that you created in the [To Back up the SSIS Database](#backup) for ##MS_SSISServerCleanupJobLogin##, sp_ssis_startup, and SSIS Server Maintenance Job.</span></span> <span data-ttu-id="76d0a-144">Confirme que o SQL Server Agent foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="76d0a-144">Confirm that SQL Server Agent has been started.</span></span>  
  
5.  <span data-ttu-id="76d0a-145">Execute a instrução a seguir para definir o procedimento sp_ssis_startup para execução automática.</span><span class="sxs-lookup"><span data-stu-id="76d0a-145">Run the following statement to set the sp_ssis_startup prodecure for autoexecution.</span></span> <span data-ttu-id="76d0a-146">Para obter mais informações, veja [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="76d0a-146">For more information, see [sp_procoption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql).</span></span>  
  
    ```  
    EXEC sp_procoption N'sp_ssis_startup','startup','on'  
    ```  
  
6.  <span data-ttu-id="76d0a-147">Mapeie o usuário do SSISDB ##MS_SSISServerCleanupJobUser## (banco de dados do SSISDB) para ##MS_SSISServerCleanupJobLogin## usando a caixa de diálogo **Propriedades de Logon** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76d0a-147">Map the SSISDB user ##MS_SSISServerCleanupJobUser## (SSISDB database) to ##MS_SSISServerCleanupJobLogin##, by using the **Login Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
7.  <span data-ttu-id="76d0a-148">Restaure a chave mestra usando um dos seguintes métodos.</span><span class="sxs-lookup"><span data-stu-id="76d0a-148">Restore the master key by using one of the following methods.</span></span> <span data-ttu-id="76d0a-149">Para obter mais informações sobre criptografia, consulte [Hierarquia de criptografia](../relational-databases/security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="76d0a-149">For more information about encryption, see [Encryption Hierarchy](../relational-databases/security/encryption/encryption-hierarchy.md).</span></span>  
  
    -   <span data-ttu-id="76d0a-150">**Método 1**</span><span class="sxs-lookup"><span data-stu-id="76d0a-150">**Method 1**</span></span>  
  
         <span data-ttu-id="76d0a-151">Use esse método se você já executou um backup da chave mestra do banco de dados e tem a senha usada para criptografar a chave mestra.</span><span class="sxs-lookup"><span data-stu-id="76d0a-151">Use this method if you've already performed a backup of the database master key, and you have the password used to encrypt the master key.</span></span>  
  
        ```  
               Restore master key from file = 'c:\temp\RCTestInstKey'  
               Decryption by password = 'LS2Setup!' -- 'Password used to encrypt the master key during SSISDB backup'  
               Encryption by password = 'LS3Setup!' -- 'New Password'  
               Force  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="76d0a-152">Confirme que a conta de serviço do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tem permissões para ler o arquivo da chave de backup.</span><span class="sxs-lookup"><span data-stu-id="76d0a-152">Confirm that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service account has permissions to read the backup key file.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="76d0a-153">Você verá a seguinte mensagem de aviso exibida no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] se a chave mestra de banco de dados ainda não tiver sido criptografada pela chave mestra de serviço.</span><span class="sxs-lookup"><span data-stu-id="76d0a-153">You will see the following warning message displayed in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] if the database master key has not yet been encrypted by the service master key.</span></span> <span data-ttu-id="76d0a-154">Ignore a mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="76d0a-154">Ignore the warning message.</span></span>  
        >   
        >  <span data-ttu-id="76d0a-155">**A chave mestra atual não pode ser descriptografada. O erro foi ignorado porque a opção FORCE foi especificada.**</span><span class="sxs-lookup"><span data-stu-id="76d0a-155">**The current master key cannot be decrypted. The error was ignored because the FORCE option was specified.**</span></span>  
        >   
        >  <span data-ttu-id="76d0a-156">O argumento FORCE especifica que o processo de restauração deve continuar mesmo se a chave mestra de banco de dados atual não estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="76d0a-156">The FORCE argument specifies that the restore process should continue even if the current database master key is not open.</span></span> <span data-ttu-id="76d0a-157">Para o catálogo do SSISDB, como a chave mestra de banco de dados não foi aberta na instância onde você está restaurando o banco de dados, você verá esta mensagem.</span><span class="sxs-lookup"><span data-stu-id="76d0a-157">For the SSISDB catalog, because the database master key has not been opened on the instance where you are restoring the database, you will see this message.</span></span>  
  
    -   <span data-ttu-id="76d0a-158">**Método 2**</span><span class="sxs-lookup"><span data-stu-id="76d0a-158">**Method 2**</span></span>  
  
         <span data-ttu-id="76d0a-159">Use este método se você tiver a senha original que foi usada para criar o SSISDB.</span><span class="sxs-lookup"><span data-stu-id="76d0a-159">Use this method if you have the original password that was used to create SSISDB.</span></span>  
  
        ```  
        open master key decryption by password = 'LS1Setup!' --'Password used when creating SSISDB'  
               Alter Master Key Add encryption by Service Master Key  
        ```  
  
8.  <span data-ttu-id="76d0a-160">Determine se o esquema de catálogo SSISDB e os binários [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] (ISServerExec e SQLCLR assembly) são compatíveis executando [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span><span class="sxs-lookup"><span data-stu-id="76d0a-160">Determine whether the SSISDB catalog schema and the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] binaries (ISServerExec and SQLCLR assembly) are compatible, by running [catalog.check_schema_version](/sql/integration-services/system-stored-procedures/catalog-check-schema-version).</span></span>  
  
9. <span data-ttu-id="76d0a-161">Para confirmar que o banco de dados do SSISDB foi restaurado com êxito, execute operações no catálogo d SSISDB, por exemplo, executar pacotes que foram implantados no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76d0a-161">To confirm that the SSISDB database has been restored successfully, perform operations against the SSISDB catalog such as running packages that have been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="76d0a-162">Para obter mais informações, consulte [Executar um pacote no servidor SSIS usando o SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="76d0a-162">For more information, see [Run a Package on the SSIS Server Using SQL Server Management Studio](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md).</span></span>  
  
### <a name="to-move-the-ssis-database"></a><span data-ttu-id="76d0a-163">Para mover o banco de dados SSIS</span><span class="sxs-lookup"><span data-stu-id="76d0a-163">To Move the SSIS Database</span></span>  
  
-   <span data-ttu-id="76d0a-164">Siga as instruções para mover bancos de dados de usuários.</span><span class="sxs-lookup"><span data-stu-id="76d0a-164">Follow the instructions for moving user databases.</span></span> <span data-ttu-id="76d0a-165">Para obter mais informações, veja [Mover bancos de dados de usuário](../relational-databases/databases/move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="76d0a-165">For more information, see [Move User Databases](../relational-databases/databases/move-user-databases.md).</span></span>  
  
     <span data-ttu-id="76d0a-166">Assegure-se de fazer backup da chave mestra do banco de dados SSISDB e proteger o arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="76d0a-166">Ensure that you back up the master key for the SSISDB database and protect the backup file.</span></span> <span data-ttu-id="76d0a-167">Para obter mais informações, consulte [Para fazer o backup do banco de dados SSIS](#backup).</span><span class="sxs-lookup"><span data-stu-id="76d0a-167">For more information, see [To Back up the SSIS Database](#backup).</span></span>  
  
     <span data-ttu-id="76d0a-168">Verifique se os objetos pertinentes do Integration Services (SSIS) estão criados na nova instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] na qual o catálogo do SSISDB ainda não foi criado.</span><span class="sxs-lookup"><span data-stu-id="76d0a-168">Ensure that the Integration Services (SSIS) relevant objects are created in the new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance where the SSISDB catalog has not yet been created.</span></span>  
  
  
