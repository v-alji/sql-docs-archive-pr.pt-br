---
title: Restaurar arquivos e grupos de arquivos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restorefilesandfilegrps.general.f1
- sql12.swb.restorefilesandfilegrps.options.f1
- sql12.swb.bselectfilegrpsfiles.f1
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], restoring files and filegroups
- restoring [SQL Server], files
ms.assetid: 72603b21-3065-4b56-8b01-11b707911b05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2576f1326cb50fa197b1623aaa1326d70137823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680487"
---
# <a name="restore-files-and-filegroups-sql-server"></a><span data-ttu-id="dc959-102">Restaurar arquivos e grupos de arquivos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dc959-102">Restore Files and Filegroups (SQL Server)</span></span>
  <span data-ttu-id="dc959-103">Este tópico descreve como restaurar arquivos e grupos de arquivos no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc959-103">This topic describes how to restore files and filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="dc959-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="dc959-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dc959-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="dc959-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dc959-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="dc959-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="dc959-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="dc959-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dc959-108">**Para restaurar arquivos e grupos de arquivos usando:**</span><span class="sxs-lookup"><span data-stu-id="dc959-108">**To restore files and filegroups, using:**</span></span>  
  
     [<span data-ttu-id="dc959-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dc959-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dc959-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc959-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dc959-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="dc959-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dc959-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="dc959-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="dc959-113">O administrador do sistema que restaura os arquivos e grupos de arquivos deve ser a única pessoa que atualmente esteja usando o banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="dc959-113">The system administrator restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="dc959-114">RESTORE não é permitido em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="dc959-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="dc959-115">No modelo de recuperação simples, o arquivo deve pertencer a um grupo de arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="dc959-115">Under the simple recovery model, the file must belong to a read-only filegroup.</span></span>  
  
-   <span data-ttu-id="dc959-116">No modelo de recuperação completa ou bulk-logged, antes de poder restaurar arquivos, você deve fazer backup do log de transações ativas (conhecido como a parte final do log).</span><span class="sxs-lookup"><span data-stu-id="dc959-116">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="dc959-117">Para obter mais informações, veja [Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="dc959-117">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="dc959-118">Para restaurar um banco de dados criptografado, é necessário ter acesso ao certificado ou à chave assimétrica usada para criptografar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dc959-118">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="dc959-119">Sem o certificado ou a chave assimétrica, o banco de dados não pode ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="dc959-119">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="dc959-120">Como resultado, o certificado usado para criptografar a chave de criptografia do banco de dados deverá ser retido enquanto o backup for necessário.</span><span class="sxs-lookup"><span data-stu-id="dc959-120">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="dc959-121">Para obter mais informações, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="dc959-121">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dc959-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="dc959-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dc959-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="dc959-123">Permissions</span></span>  
 <span data-ttu-id="dc959-124">Se o banco de dados que está sendo restaurado não existir, o usuário deverá ter permissões CREATE DATABASE para poder executar o comando RESTORE.</span><span class="sxs-lookup"><span data-stu-id="dc959-124">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="dc959-125">Se o banco de dados existir, as permissões RESTORE usarão como padrão os membros das funções de servidor fixas **sysadmin** e **dbcreator** e o proprietário (**dbo**) do banco de dados (para a opção FROM DATABASE_SNAPSHOT, o banco de dados sempre existe).</span><span class="sxs-lookup"><span data-stu-id="dc959-125">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="dc959-126">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="dc959-126">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="dc959-127">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="dc959-127">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dc959-128">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dc959-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="dc959-129">Para restaurar arquivos e grupos de arquivos</span><span class="sxs-lookup"><span data-stu-id="dc959-129">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="dc959-130">Depois de se conectar à instância adequada do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], no Pesquisador de Objetos, clique no nome do servidor para expandir a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="dc959-130">After you connect to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="dc959-131">Expanda os **Bancos de dados**.</span><span class="sxs-lookup"><span data-stu-id="dc959-131">Expand **Databases**.</span></span> <span data-ttu-id="dc959-132">Dependendo do banco de dados, selecione um banco de dados de usuário ou expanda os **Bancos de dados do sistema**e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="dc959-132">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="dc959-133">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="dc959-133">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="dc959-134">Clique em **Arquivos e Grupos de Arquivos**, que abre a caixa de diálogo **Restaurar Arquivos e Grupos de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="dc959-134">Click **Files and Filegroups**, which opens the **Restore Files and Filegroups** dialog box.</span></span>  
  
5.  <span data-ttu-id="dc959-135">Na página **Geral** , na caixa de listagem **Banco de dados de destino** , digite o banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="dc959-135">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="dc959-136">Você pode digitar um novo banco de dados ou escolher um banco de dados existente na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="dc959-136">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="dc959-137">A lista inclui todos os bancos de dados do servidor, excluindo os bancos de dados do sistema **mestre** e **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="dc959-137">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
6.  <span data-ttu-id="dc959-138">Para especificar a origem e o local dos conjuntos de backup a serem restaurados, clique em uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="dc959-138">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="dc959-139">**Do Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="dc959-139">**From database**</span></span>  
  
         <span data-ttu-id="dc959-140">Digite um nome de banco de dados na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="dc959-140">Enter a database name in the list box.</span></span> <span data-ttu-id="dc959-141">Essa lista contém apenas os bancos de dados em que foi feito backup segundo o histórico de backups do **msdb** .</span><span class="sxs-lookup"><span data-stu-id="dc959-141">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="dc959-142">**Do Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="dc959-142">**From device**</span></span>  
  
         <span data-ttu-id="dc959-143">Clique no botão Procurar.</span><span class="sxs-lookup"><span data-stu-id="dc959-143">Click the browse button.</span></span> <span data-ttu-id="dc959-144">Na caixa de diálogo **Especificar dispositivos de backup** , selecione um dos tipos de dispositivos listados na caixa de listagem **Tipo de mídia de backup** .</span><span class="sxs-lookup"><span data-stu-id="dc959-144">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="dc959-145">Para selecionar um ou mais dispositivos para a caixa de listagem **Mídia de backup** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dc959-145">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="dc959-146">Após adicionar os dispositivos desejados à caixa de listagem **Mídia de backup** , clique em **OK** para voltar à página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="dc959-146">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
7.  <span data-ttu-id="dc959-147">Na grade **Selecione os conjuntos de backup a serem restaurados** , selecione os backups a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="dc959-147">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="dc959-148">Essa grade exibe os backups disponíveis para o local especificado.</span><span class="sxs-lookup"><span data-stu-id="dc959-148">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="dc959-149">Por padrão, um plano de recuperação é sugerido.</span><span class="sxs-lookup"><span data-stu-id="dc959-149">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="dc959-150">Para substituir o plano de recuperação sugerido, você pode alterar as seleções na grade.</span><span class="sxs-lookup"><span data-stu-id="dc959-150">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="dc959-151">Todos os backups que dependem de um backup não selecionado serão desmarcados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dc959-151">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="dc959-152">Título da coluna</span><span class="sxs-lookup"><span data-stu-id="dc959-152">Column head</span></span>|<span data-ttu-id="dc959-153">Valores</span><span class="sxs-lookup"><span data-stu-id="dc959-153">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="dc959-154">**Restaurar**</span><span class="sxs-lookup"><span data-stu-id="dc959-154">**Restore**</span></span>|<span data-ttu-id="dc959-155">As caixas de seleção selecionadas indicam os conjuntos de backup a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="dc959-155">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="dc959-156">**Nome**</span><span class="sxs-lookup"><span data-stu-id="dc959-156">**Name**</span></span>|<span data-ttu-id="dc959-157">O nome do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="dc959-157">The name of the backup set.</span></span>|  
    |<span data-ttu-id="dc959-158">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="dc959-158">**File Type**</span></span>|<span data-ttu-id="dc959-159">Especifica o tipo dos dados na no backup: **Dados**, **Log** ou **Dados de Fluxo de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="dc959-159">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="dc959-160">Dados que são contidos em tabelas estão nos arquivos **Dados** .</span><span class="sxs-lookup"><span data-stu-id="dc959-160">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="dc959-161">Dados de log de transações estão nos arquivos **Log** .</span><span class="sxs-lookup"><span data-stu-id="dc959-161">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="dc959-162">Dados de BLOB (objeto binário grande) armazenados no sistema de arquivos estão localizados em arquivos de **Dados do Fluxo de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="dc959-162">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="dc959-163">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dc959-163">**Type**</span></span>|<span data-ttu-id="dc959-164">O tipo de backup realizado: **Total**, **Diferencial** ou **Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="dc959-164">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="dc959-165">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="dc959-165">**Server**</span></span>|<span data-ttu-id="dc959-166">Nome da instância do Mecanismo de Banco de Dados que executou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="dc959-166">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="dc959-167">**Nome Lógico do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="dc959-167">**File Logical Name**</span></span>|<span data-ttu-id="dc959-168">O nome lógico do arquivo.</span><span class="sxs-lookup"><span data-stu-id="dc959-168">The logical name of the file.</span></span>|  
    |<span data-ttu-id="dc959-169">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="dc959-169">**Database**</span></span>|<span data-ttu-id="dc959-170">Nome do banco de dados envolvido na operação de backup.</span><span class="sxs-lookup"><span data-stu-id="dc959-170">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="dc959-171">**Data de Início**</span><span class="sxs-lookup"><span data-stu-id="dc959-171">**Start Date**</span></span>|<span data-ttu-id="dc959-172">A data e hora de início da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="dc959-172">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="dc959-173">**Data de Conclusão**</span><span class="sxs-lookup"><span data-stu-id="dc959-173">**Finish Date**</span></span>|<span data-ttu-id="dc959-174">A data e hora da conclusão da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="dc959-174">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="dc959-175">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="dc959-175">**Size**</span></span>|<span data-ttu-id="dc959-176">O tamanho do conjunto de backup em bytes.</span><span class="sxs-lookup"><span data-stu-id="dc959-176">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="dc959-177">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="dc959-177">**User Name**</span></span>|<span data-ttu-id="dc959-178">O nome do usuário que realizou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="dc959-178">The name of the user who performed the backup operation.</span></span>|  
  
8.  <span data-ttu-id="dc959-179">Para exibir ou selecionar as opções avançadas, clique em **Opções** em **Painel Selecionar uma página**.</span><span class="sxs-lookup"><span data-stu-id="dc959-179">To view or select the advanced options, click **Options** in the **Select a page pane**.</span></span>  
  
9. <span data-ttu-id="dc959-180">No painel **Opções de restauração** , você pode escolher uma das seguintes opções, de acordo com sua situação.</span><span class="sxs-lookup"><span data-stu-id="dc959-180">In the **Restore options** panel, you can choose any of the following options, if appropriate for your situation.</span></span>  
  
     <span data-ttu-id="dc959-181">**Restaurar um grupo de arquivos**</span><span class="sxs-lookup"><span data-stu-id="dc959-181">**Restore as filegroup**</span></span>  
     <span data-ttu-id="dc959-182">Indica que um grupo de arquivos inteiro está sendo restaurado.</span><span class="sxs-lookup"><span data-stu-id="dc959-182">Indicates that an entire filegroup is being restored.</span></span>  
  
     <span data-ttu-id="dc959-183">**Substituir o banco de dados existente**</span><span class="sxs-lookup"><span data-stu-id="dc959-183">**Overwrite the existing database**</span></span>  
     <span data-ttu-id="dc959-184">Especifica que a operação de restauração deve substituir quaisquer bancos de dados existentes e seus arquivos relacionados, mesmo se já existirem outros bancos de dados ou arquivos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="dc959-184">Specifies that the restore operation should overwrite any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
     <span data-ttu-id="dc959-185">Selecionar esta opção equivale ao uso da opção REPLACE em uma declaração RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc959-185">Selecting this option is equivalent to using the REPLACE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="dc959-186">**Perguntar antes de restaurar cada backup**</span><span class="sxs-lookup"><span data-stu-id="dc959-186">**Prompt before restoring each backup**</span></span>  
     <span data-ttu-id="dc959-187">Solicita sua confirmação antes de restaurar cada conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="dc959-187">Asks you for confirmation before restoring each backup set.</span></span>  
  
     <span data-ttu-id="dc959-188">Esta opção é particularmente útil quando você precisar trocar as fitas de conjuntos de mídia diferentes, tal como quando o servidor tiver um dispositivo de fita.</span><span class="sxs-lookup"><span data-stu-id="dc959-188">This option is particularly useful where you must swap tapes for different media sets, such as when the server has one tape device.</span></span>  
  
     <span data-ttu-id="dc959-189">**Acesso restrito ao banco de dados restaurado**</span><span class="sxs-lookup"><span data-stu-id="dc959-189">**Restrict access to the restored database**</span></span>  
     <span data-ttu-id="dc959-190">Disponibiliza o banco de dados restaurado apenas para os membros do **db_owner**, **dbcreator**ou **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="dc959-190">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
     <span data-ttu-id="dc959-191">Selecionar esta opção é como usar a opção RESTRICTED_USER na declaração RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc959-191">Selecting this option is synonymous to using the RESTRICTED_USER option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
10. <span data-ttu-id="dc959-192">Opcionalmente, você pode restaurar o banco de dados para um novo local, especificando um novo destino de restauração para cada arquivo na grade **Restaurar os arquivos de banco de dados como** .</span><span class="sxs-lookup"><span data-stu-id="dc959-192">Optionally, you can restore the database to a new location by specifying a new restore destination for each file in the **Restore database files as** grid.</span></span>  
  
    |<span data-ttu-id="dc959-193">Título da coluna</span><span class="sxs-lookup"><span data-stu-id="dc959-193">Column head</span></span>|<span data-ttu-id="dc959-194">Valores</span><span class="sxs-lookup"><span data-stu-id="dc959-194">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="dc959-195">**Nome do arquivo original**</span><span class="sxs-lookup"><span data-stu-id="dc959-195">**Original File Name**</span></span>|<span data-ttu-id="dc959-196">O caminho completo do arquivo de backup de origem.</span><span class="sxs-lookup"><span data-stu-id="dc959-196">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="dc959-197">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="dc959-197">**File Type**</span></span>|<span data-ttu-id="dc959-198">Especifica o tipo dos dados na no backup: **Dados**, **Log** ou **Dados de Fluxo de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="dc959-198">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="dc959-199">Dados que são contidos em tabelas estão nos arquivos **Dados** .</span><span class="sxs-lookup"><span data-stu-id="dc959-199">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="dc959-200">Dados de log de transações estão nos arquivos **Log** .</span><span class="sxs-lookup"><span data-stu-id="dc959-200">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="dc959-201">Dados de BLOB (objeto binário grande) armazenados no sistema de arquivos estão localizados em arquivos de **Dados do Fluxo de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="dc959-201">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="dc959-202">**Restaurar Como**</span><span class="sxs-lookup"><span data-stu-id="dc959-202">**Restore As**</span></span>|<span data-ttu-id="dc959-203">O caminho completo do arquivo de banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="dc959-203">The full path of the database file to be restored.</span></span> <span data-ttu-id="dc959-204">Para especificar um novo arquivo de restauração, clique na caixa de texto e edite o caminho sugerido e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="dc959-204">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="dc959-205">Alterar o caminho ou o nome do arquivo na coluna **Restaurar Como** é equivalente ao uso da opção MOVE em uma declaração RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc959-205">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
11. <span data-ttu-id="dc959-206">O painel **Estado de recuperação** determina o estado do banco de dados após a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="dc959-206">The **Recovery state** panel determines the state of the database after the restore operation.</span></span>  
  
     <span data-ttu-id="dc959-207">**Deixar o banco de dados pronto para uso revertendo as transações não confirmadas. Os logs de transações adicionais não podem ser restaurados. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="dc959-207">**Leave the database ready for use by rolling back the uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
     <span data-ttu-id="dc959-208">Recupera o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dc959-208">Recovers the database.</span></span> <span data-ttu-id="dc959-209">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="dc959-209">This is the default behavior.</span></span> <span data-ttu-id="dc959-210">Escolha essa opção somente se estiver restaurando todos os backups necessários agora.</span><span class="sxs-lookup"><span data-stu-id="dc959-210">Choose this option only if you are restoring all of the necessary backups now.</span></span> <span data-ttu-id="dc959-211">Esta opção equivale à especificação WITH RECOVERY em uma declaração RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc959-211">This option is equivalent to specifying WITH RECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="dc959-212">**Deixe o banco de dados não operacional e não reverta as transações não confirmadas. Os logs de transações adicionais podem ser restaurados. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="dc959-212">**Leave the database non-operational, and don't roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
     <span data-ttu-id="dc959-213">Deixa o banco de dados no estado de restauração.</span><span class="sxs-lookup"><span data-stu-id="dc959-213">Leaves the database in the restoring state.</span></span> <span data-ttu-id="dc959-214">Para recuperar o banco de dados, será necessário realizar outra restauração usando a opção RESTORE WITH RECOVERY (veja acima).</span><span class="sxs-lookup"><span data-stu-id="dc959-214">To recover the database, you will need to perform another restore using the preceding RESTORE WITH RECOVERY option (see above).</span></span> <span data-ttu-id="dc959-215">Esta opção equivale à especificação WITH NORECOVERY em uma declaração RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc959-215">This option is equivalent to specifying WITH NORECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="dc959-216">Se selecionar esta opção, a opção **Preservar parâmetros de replicação** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="dc959-216">If you select this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
     <span data-ttu-id="dc959-217">**Deixar o banco de dados no modo somente leitura. Reverter as transações não confirmadas, mas salvar a operação de reversão em um arquivo para que os efeitos da recuperação possam ser desfeitos. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="dc959-217">**Leave the database in read-only mode. Roll back the uncommitted transactions, but save the rollback operation in a file so the recovery effects can be undone. (RESTORE WITH STANDBY)**</span></span>  
     <span data-ttu-id="dc959-218">Deixa o banco de dados no estado de espera.</span><span class="sxs-lookup"><span data-stu-id="dc959-218">Leaves the database in a standby state.</span></span> <span data-ttu-id="dc959-219">Esta opção equivale à especificação WITH STANDBY em uma declaração RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc959-219">This option is equivalent to specifying WITH STANDBY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="dc959-220">A escolha desta opção requer que você especifique um arquivo de espera.</span><span class="sxs-lookup"><span data-stu-id="dc959-220">Choosing this option requires that you specify a standby file.</span></span>  
  
     <span data-ttu-id="dc959-221">**Reverter de arquivo de desfazer**</span><span class="sxs-lookup"><span data-stu-id="dc959-221">**Rollback undo file**</span></span>  
     <span data-ttu-id="dc959-222">Especifique o nome do arquivo de espera na caixa de texto **Reverter arquivo de desfazer** .</span><span class="sxs-lookup"><span data-stu-id="dc959-222">Specify a standby file name in the **Rollback undo file** text box.</span></span> <span data-ttu-id="dc959-223">Esta opção será necessária se o banco de dados estiver no modo somente leitura (RESTORE WITH STANDBY).</span><span class="sxs-lookup"><span data-stu-id="dc959-223">This option is required if you leave the database in read-only mode (RESTORE WITH STANDBY).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dc959-224">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc959-224">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="dc959-225">Para restaurar arquivos e grupos de arquivos</span><span class="sxs-lookup"><span data-stu-id="dc959-225">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="dc959-226">Execute a instrução RESTORE DATABASE para restaurar o backup de arquivos e grupo de arquivos, especificando:</span><span class="sxs-lookup"><span data-stu-id="dc959-226">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="dc959-227">O nome do banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="dc959-227">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="dc959-228">O dispositivo de backup do qual o backup de banco de dados completo será restaurado.</span><span class="sxs-lookup"><span data-stu-id="dc959-228">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="dc959-229">A cláusula FILE para cada arquivo a restaurar.</span><span class="sxs-lookup"><span data-stu-id="dc959-229">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="dc959-230">A cláusula FILEGROUP para cada grupo de arquivos a restaurar.</span><span class="sxs-lookup"><span data-stu-id="dc959-230">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="dc959-231">A cláusula NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="dc959-231">The NORECOVERY clause.</span></span> <span data-ttu-id="dc959-232">Se os arquivos não foram modificados depois que o backup foi criado, especifique a cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="dc959-232">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="dc959-233">Se os arquivos foram modificados depois que o backup de arquivo foi criado, execute a instrução RESTORE LOG para aplicar o backup de log de transações, especificando:</span><span class="sxs-lookup"><span data-stu-id="dc959-233">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="dc959-234">O nome do banco de dados ao qual o log de transações será aplicado.</span><span class="sxs-lookup"><span data-stu-id="dc959-234">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="dc959-235">O dispositivo de backup do qual o backup de log de transações será restaurado.</span><span class="sxs-lookup"><span data-stu-id="dc959-235">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="dc959-236">A cláusula NORECOVERY se você tiver outro backup de log de transações para aplicar depois do atual; caso contrário, especifique a cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="dc959-236">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="dc959-237">Os backups de log de transações, se aplicados, devem cobrir o tempo quando foi feito o backup dos arquivos e grupos de arquivos até o final do log (a menos que sejam restaurados TODOS os arquivos de banco de dados).</span><span class="sxs-lookup"><span data-stu-id="dc959-237">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up until the end of log (unless ALL database files are restored).</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="dc959-238">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dc959-238">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="dc959-239">Este exemplo restaura os arquivos e grupos de arquivos para o banco de dados `MyDatabase` .</span><span class="sxs-lookup"><span data-stu-id="dc959-239">This example restores the files and filegroups for the `MyDatabase` database.</span></span> <span data-ttu-id="dc959-240">Para restaurar o banco de dados para a hora atual, dois logs de transações são aplicados.</span><span class="sxs-lookup"><span data-stu-id="dc959-240">To restore the database to the current time, two transaction logs are applied.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyDatabase.  
RESTORE DATABASE MyDatabase  
   FILE = 'MyDatabase_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyDatabase_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyDatabase_1  
   WITH NORECOVERY;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc959-241">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc959-241">See Also</span></span>  
 <span data-ttu-id="dc959-242">[Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="dc959-242">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="dc959-243">[Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dc959-243">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="dc959-244">[Criar um backup completo de banco de dados &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dc959-244">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="dc959-245">[Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dc959-245">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="dc959-246">[Restaurar um backup de log de transações &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dc959-246">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="dc959-247">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dc959-247">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
