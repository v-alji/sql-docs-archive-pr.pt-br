---
title: Restaurar arquivos e grupos de arquivos sobre arquivos existentes (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
- overwriting filegroups
- overwriting files
ms.assetid: 517e07eb-9685-4b06-90af-b1cc496700b7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc72ae3ae2472fe579755fa624e9af6953c7aed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573127"
---
# <a name="restore-files-and-filegroups-over-existing-files-sql-server"></a><span data-ttu-id="455b9-102">Restaurar arquivos e grupos de arquivos sobre arquivos existentes (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="455b9-102">Restore Files and Filegroups over Existing Files (SQL Server)</span></span>
  <span data-ttu-id="455b9-103">Este tópico descreve como restaurar arquivos e grupos de arquivos sobre arquivos existentes no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="455b9-103">This topic describes how to restore files and filegroups over existing files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="455b9-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="455b9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="455b9-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="455b9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="455b9-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="455b9-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="455b9-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="455b9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="455b9-108">**Para restaurar arquivos e grupos de arquivos sobre arquivos existentes usando:**</span><span class="sxs-lookup"><span data-stu-id="455b9-108">**To restore files and filegroups over existing files, using:**</span></span>  
  
     [<span data-ttu-id="455b9-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="455b9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="455b9-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="455b9-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="455b9-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="455b9-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="455b9-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="455b9-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="455b9-113">O administrador do sistema que restaura os arquivos e grupos de arquivos deve ser a única pessoa usando atualmente o banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="455b9-113">The system administrator who is restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="455b9-114">RESTORE não é permitido em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="455b9-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="455b9-115">No modelo de recuperação completa ou bulk-logged, antes de poder restaurar arquivos, você deve fazer backup do log de transações ativas (conhecido como a parte final do log).</span><span class="sxs-lookup"><span data-stu-id="455b9-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="455b9-116">Para obter mais informações, veja [Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="455b9-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="455b9-117">Para restaurar um banco de dados criptografado, é necessário ter acesso ao certificado ou à chave assimétrica usada para criptografar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="455b9-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="455b9-118">Sem o certificado ou a chave assimétrica, o banco de dados não pode ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="455b9-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="455b9-119">Como resultado, o certificado usado para criptografar a chave de criptografia do banco de dados deverá ser retido enquanto o backup for necessário.</span><span class="sxs-lookup"><span data-stu-id="455b9-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="455b9-120">Para obter mais informações, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="455b9-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="455b9-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="455b9-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="455b9-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="455b9-122">Permissions</span></span>  
 <span data-ttu-id="455b9-123">Se o banco de dados que está sendo restaurado não existir, o usuário deverá ter permissões CREATE DATABASE para poder executar o comando RESTORE.</span><span class="sxs-lookup"><span data-stu-id="455b9-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="455b9-124">Se o banco de dados existir, as permissões RESTORE usarão como padrão os membros das funções de servidor fixas **sysadmin** e **dbcreator** e o proprietário (**dbo**) do banco de dados (para a opção FROM DATABASE_SNAPSHOT, o banco de dados sempre existe).</span><span class="sxs-lookup"><span data-stu-id="455b9-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="455b9-125">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="455b9-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="455b9-126">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="455b9-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="455b9-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="455b9-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups-over-existing-files"></a><span data-ttu-id="455b9-128">Para restaurar arquivos e grupos de arquivos sobre arquivos existentes</span><span class="sxs-lookup"><span data-stu-id="455b9-128">To restore files and filegroups over existing files</span></span>  
  
1.  <span data-ttu-id="455b9-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expanda essa instância e expanda **Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="455b9-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="455b9-130">Clique com o botão direito do mouse no banco de dados desejado, aponte para **Tarefas**e para **Restaurar**, e clique em **Arquivos e Grupos de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="455b9-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="455b9-131">Na página **Geral** , na caixa de listagem **Banco de dados de destino** , digite o banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="455b9-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="455b9-132">Você pode digitar um novo banco de dados ou escolher um banco de dados existente na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="455b9-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="455b9-133">A lista inclui todos os bancos de dados do servidor, excluindo os bancos de dados do sistema **mestre** e **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="455b9-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="455b9-134">Para especificar a origem e o local dos conjuntos de backup a serem restaurados, clique em uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="455b9-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="455b9-135">**Do Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="455b9-135">**From database**</span></span>  
  
         <span data-ttu-id="455b9-136">Digite um nome de banco de dados na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="455b9-136">Enter a database name in the list box.</span></span> <span data-ttu-id="455b9-137">Essa lista contém apenas os bancos de dados em que foi feito backup segundo o histórico de backups do **msdb** .</span><span class="sxs-lookup"><span data-stu-id="455b9-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="455b9-138">**Do Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="455b9-138">**From device**</span></span>  
  
         <span data-ttu-id="455b9-139">Clique no botão Procurar.</span><span class="sxs-lookup"><span data-stu-id="455b9-139">Click the browse button.</span></span> <span data-ttu-id="455b9-140">Na caixa de diálogo **Especificar dispositivos de backup** , selecione um dos tipos de dispositivos listados na caixa de listagem **Tipo de mídia de backup** .</span><span class="sxs-lookup"><span data-stu-id="455b9-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="455b9-141">Para selecionar um ou mais dispositivos para a caixa de listagem **Mídia de backup** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="455b9-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="455b9-142">Após adicionar os dispositivos desejados à caixa de listagem **Mídia de backup** , clique em **OK** para voltar à página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="455b9-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="455b9-143">Na grade **Selecione os conjuntos de backup a serem restaurados** , selecione os backups a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="455b9-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="455b9-144">Essa grade exibe os backups disponíveis para o local especificado.</span><span class="sxs-lookup"><span data-stu-id="455b9-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="455b9-145">Por padrão, um plano de recuperação é sugerido.</span><span class="sxs-lookup"><span data-stu-id="455b9-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="455b9-146">Para substituir o plano de recuperação sugerido, você pode alterar as seleções na grade.</span><span class="sxs-lookup"><span data-stu-id="455b9-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="455b9-147">Todos os backups que dependem de um backup não selecionado serão desmarcados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="455b9-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="455b9-148">Título da coluna</span><span class="sxs-lookup"><span data-stu-id="455b9-148">Column head</span></span>|<span data-ttu-id="455b9-149">Valores</span><span class="sxs-lookup"><span data-stu-id="455b9-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="455b9-150">**Restaurar**</span><span class="sxs-lookup"><span data-stu-id="455b9-150">**Restore**</span></span>|<span data-ttu-id="455b9-151">As caixas de seleção selecionadas indicam os conjuntos de backup a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="455b9-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="455b9-152">**Nome**</span><span class="sxs-lookup"><span data-stu-id="455b9-152">**Name**</span></span>|<span data-ttu-id="455b9-153">O nome do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="455b9-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="455b9-154">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="455b9-154">**File Type**</span></span>|<span data-ttu-id="455b9-155">Especifica o tipo dos dados na no backup: **Dados**, **Log** ou **Dados de Fluxo de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="455b9-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="455b9-156">Dados que são contidos em tabelas estão nos arquivos **Dados** .</span><span class="sxs-lookup"><span data-stu-id="455b9-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="455b9-157">Dados de log de transações estão nos arquivos **Log** .</span><span class="sxs-lookup"><span data-stu-id="455b9-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="455b9-158">Dados de BLOB (objeto binário grande) armazenados no sistema de arquivos estão localizados em arquivos de **Dados do Fluxo de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="455b9-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="455b9-159">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="455b9-159">**Type**</span></span>|<span data-ttu-id="455b9-160">O tipo de backup realizado: **Total**, **Diferencial** ou **Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="455b9-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="455b9-161">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="455b9-161">**Server**</span></span>|<span data-ttu-id="455b9-162">Nome da instância do Mecanismo de Banco de Dados que executou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="455b9-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="455b9-163">**Nome Lógico do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="455b9-163">**File Logical Name**</span></span>|<span data-ttu-id="455b9-164">O nome lógico do arquivo.</span><span class="sxs-lookup"><span data-stu-id="455b9-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="455b9-165">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="455b9-165">**Database**</span></span>|<span data-ttu-id="455b9-166">Nome do banco de dados envolvido na operação de backup.</span><span class="sxs-lookup"><span data-stu-id="455b9-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="455b9-167">**Data de Início**</span><span class="sxs-lookup"><span data-stu-id="455b9-167">**Start Date**</span></span>|<span data-ttu-id="455b9-168">A data e hora de início da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="455b9-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="455b9-169">**Data de Conclusão**</span><span class="sxs-lookup"><span data-stu-id="455b9-169">**Finish Date**</span></span>|<span data-ttu-id="455b9-170">A data e hora da conclusão da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="455b9-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="455b9-171">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="455b9-171">**Size**</span></span>|<span data-ttu-id="455b9-172">O tamanho do conjunto de backup em bytes.</span><span class="sxs-lookup"><span data-stu-id="455b9-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="455b9-173">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="455b9-173">**User Name**</span></span>|<span data-ttu-id="455b9-174">O nome do usuário que realizou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="455b9-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="455b9-175">No painel **Selecionar uma página** , clique na página **Opções** .</span><span class="sxs-lookup"><span data-stu-id="455b9-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="455b9-176">No painel **Opções de restauração** , selecione **Substituir o banco de dados existente (WITH REPLACE)** .</span><span class="sxs-lookup"><span data-stu-id="455b9-176">In the **Restore options** panel, select **Overwrite the existing database (WITH REPLACE)**.</span></span> <span data-ttu-id="455b9-177">A operação de restauração substitui os bancos de dados existentes e seus arquivos relacionados, mesmo se já existirem outros bancos de dados ou arquivos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="455b9-177">The restore operation overwrites any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="455b9-178">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="455b9-178">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups-over-existing-files"></a><span data-ttu-id="455b9-179">Para restaurar arquivos e grupos de arquivos sobre arquivos existentes</span><span class="sxs-lookup"><span data-stu-id="455b9-179">To restore files and filegroups over existing files</span></span>  
  
1.  <span data-ttu-id="455b9-180">Execute a instrução RESTORE DATABASE para restaurar o backup de arquivos e grupo de arquivos, especificando:</span><span class="sxs-lookup"><span data-stu-id="455b9-180">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="455b9-181">O nome do banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="455b9-181">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="455b9-182">O dispositivo de backup do qual o backup de banco de dados completo será restaurado.</span><span class="sxs-lookup"><span data-stu-id="455b9-182">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="455b9-183">A cláusula FILE para cada arquivo a restaurar.</span><span class="sxs-lookup"><span data-stu-id="455b9-183">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="455b9-184">A cláusula FILEGROUP para cada grupo de arquivos a restaurar.</span><span class="sxs-lookup"><span data-stu-id="455b9-184">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="455b9-185">A opção de REPLACE para especificar que cada arquivo pode ser restaurado de arquivos existentes do mesmo nome e local.</span><span class="sxs-lookup"><span data-stu-id="455b9-185">The REPLACE option to specify that each file can be restored over existing files of the same name and location.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="455b9-186">Use a opção de REPLACE cautelosamente.</span><span class="sxs-lookup"><span data-stu-id="455b9-186">Use the REPLACE option cautiously.</span></span> <span data-ttu-id="455b9-187">Para obter mais informações, consulte .</span><span class="sxs-lookup"><span data-stu-id="455b9-187">For more information, see .</span></span>  
  
    -   <span data-ttu-id="455b9-188">A opção de NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="455b9-188">The NORECOVERY option.</span></span> <span data-ttu-id="455b9-189">Se os arquivos não foram modificados depois que o backup foi criado, especifique a cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="455b9-189">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="455b9-190">Se os arquivos foram modificados depois que o backup de arquivo foi criado, execute a instrução RESTORE LOG para aplicar o backup de log de transações, especificando:</span><span class="sxs-lookup"><span data-stu-id="455b9-190">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="455b9-191">O nome do banco de dados ao qual o log de transações será aplicado.</span><span class="sxs-lookup"><span data-stu-id="455b9-191">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="455b9-192">O dispositivo de backup do qual o backup de log de transações será restaurado.</span><span class="sxs-lookup"><span data-stu-id="455b9-192">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="455b9-193">A cláusula NORECOVERY se você tiver outro backup de log de transações para aplicar depois do atual; caso contrário, especifique a cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="455b9-193">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="455b9-194">Os backups de log de transações, se aplicados, devem cobrir a hora em que os backups dos arquivos e grupos de arquivos foram feitos.</span><span class="sxs-lookup"><span data-stu-id="455b9-194">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="455b9-195">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="455b9-195">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="455b9-196">O exemplo seguinte restaura os arquivos e grupos de arquivos para o banco de dados `MyNwind` e substitui qualquer arquivo existente do mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="455b9-196">The following example restores the files and filegroups for the `MyNwind` database, and replaces any existing files of the same name.</span></span> <span data-ttu-id="455b9-197">Também serão aplicados dois logs de transações para restaurar o banco de dados a hora atual.</span><span class="sxs-lookup"><span data-stu-id="455b9-197">Two transaction logs will also be applied to restore the database to the current time.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyNwind.  
RESTORE DATABASE MyNwind  
   FILE = 'MyNwind_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyNwind_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   REPLACE;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="455b9-198">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="455b9-198">See Also</span></span>  
 <span data-ttu-id="455b9-199">[Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="455b9-199">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="455b9-200">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="455b9-200">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="455b9-201">[Restaurar arquivos e grupos de arquivos &#40;SQL Server&#41;](restore-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="455b9-201">[Restore Files and Filegroups &#40;SQL Server&#41;](restore-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="455b9-202">Copiar bancos de dados com backup e restauração</span><span class="sxs-lookup"><span data-stu-id="455b9-202">Copy Databases with Backup and Restore</span></span>](../databases/copy-databases-with-backup-and-restore.md)  
  
  
