---
title: Restaurar arquivos para um novo local (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring databases [SQL Server], moving
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
ms.assetid: b4f4791d-646e-4632-9980-baae9cb1aade
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a8336e5d186fb72df4e0a17fdd9affccab4ee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680485"
---
# <a name="restore-files-to-a-new-location-sql-server"></a><span data-ttu-id="15e8a-102">Restaurar arquivos para um novo local (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="15e8a-102">Restore Files to a New Location (SQL Server)</span></span>
  <span data-ttu-id="15e8a-103">Este tópico descreve como restaurar arquivos para um novo local no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15e8a-103">This topic describes how to restore files to a new location in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="15e8a-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="15e8a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="15e8a-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="15e8a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="15e8a-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="15e8a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="15e8a-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="15e8a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="15e8a-108">**Para restaurar arquivos para um novo local, usando:**</span><span class="sxs-lookup"><span data-stu-id="15e8a-108">**To restore files to a new location, using:**</span></span>  
  
     [<span data-ttu-id="15e8a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15e8a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="15e8a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15e8a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="15e8a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="15e8a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="15e8a-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="15e8a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="15e8a-113">O administrador do sistema que restaura os arquivos deve ser a única pessoa que no momento esteja usando o banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-113">The system administrator restoring the files must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="15e8a-114">RESTORE não é permitido em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="15e8a-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="15e8a-115">No modelo de recuperação completa ou bulk-logged, antes de poder restaurar arquivos, você deve fazer backup do log de transações ativas (conhecido como a parte final do log).</span><span class="sxs-lookup"><span data-stu-id="15e8a-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="15e8a-116">Para obter mais informações, veja [Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="15e8a-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="15e8a-117">Para restaurar um banco de dados criptografado, é necessário ter acesso ao certificado ou à chave assimétrica usada para criptografar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="15e8a-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="15e8a-118">Sem o certificado ou a chave assimétrica, o banco de dados não pode ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="15e8a-119">Como resultado, o certificado usado para criptografar a chave de criptografia do banco de dados deverá ser retido enquanto o backup for necessário.</span><span class="sxs-lookup"><span data-stu-id="15e8a-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="15e8a-120">Para obter mais informações, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="15e8a-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="15e8a-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="15e8a-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="15e8a-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="15e8a-122">Permissions</span></span>  
 <span data-ttu-id="15e8a-123">Se o banco de dados que está sendo restaurado não existir, o usuário deverá ter permissões CREATE DATABASE para poder executar o comando RESTORE.</span><span class="sxs-lookup"><span data-stu-id="15e8a-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="15e8a-124">Se o banco de dados existir, as permissões RESTORE usarão como padrão os membros das funções de servidor fixas **sysadmin** e **dbcreator** e o proprietário (**dbo**) do banco de dados (para a opção FROM DATABASE_SNAPSHOT, o banco de dados sempre existe).</span><span class="sxs-lookup"><span data-stu-id="15e8a-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="15e8a-125">As permissões RESTORE são concedidas a funções nas quais as informações de associação estão sempre disponíveis para o servidor.</span><span class="sxs-lookup"><span data-stu-id="15e8a-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="15e8a-126">Como a associação da função de banco de dados fixa pode ser verificada apenas quando o banco de dados está acessível e não danificado, o que nem sempre é o caso quando RESTORE é executado, os membros da função de banco de dados fixa **db_owner** não têm permissões RESTORE.</span><span class="sxs-lookup"><span data-stu-id="15e8a-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="15e8a-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15e8a-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="15e8a-128">Para restaurar arquivos para um novo local</span><span class="sxs-lookup"><span data-stu-id="15e8a-128">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="15e8a-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expanda essa instância e expanda **Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="15e8a-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="15e8a-130">Clique com o botão direito do mouse no banco de dados desejado, aponte para **Tarefas**e para **Restaurar**, e clique em **Arquivos e Grupos de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="15e8a-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="15e8a-131">Na página **Geral** , na caixa de listagem **Banco de dados de destino** , digite o banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="15e8a-132">Você pode digitar um novo banco de dados ou escolher um banco de dados existente na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="15e8a-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="15e8a-133">A lista inclui todos os bancos de dados do servidor, excluindo os bancos de dados do sistema **mestre** e **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="15e8a-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="15e8a-134">Para especificar a origem e o local dos conjuntos de backup a serem restaurados, clique em uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="15e8a-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="15e8a-135">**Do Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="15e8a-135">**From database**</span></span>  
  
         <span data-ttu-id="15e8a-136">Digite um nome de banco de dados na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="15e8a-136">Enter a database name in the list box.</span></span> <span data-ttu-id="15e8a-137">Essa lista contém apenas os bancos de dados em que foi feito backup segundo o histórico de backups do **msdb** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="15e8a-138">**Do Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="15e8a-138">**From device**</span></span>  
  
         <span data-ttu-id="15e8a-139">Clique no botão Procurar.</span><span class="sxs-lookup"><span data-stu-id="15e8a-139">Click the browse button.</span></span> <span data-ttu-id="15e8a-140">Na caixa de diálogo **Especificar dispositivos de backup** , selecione um dos tipos de dispositivos listados na caixa de listagem **Tipo de mídia de backup** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="15e8a-141">Para selecionar um ou mais dispositivos para a caixa de listagem **Mídia de backup** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="15e8a-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="15e8a-142">Após adicionar os dispositivos desejados à caixa de listagem **Mídia de backup** , clique em **OK** para voltar à página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="15e8a-143">Na grade **Selecione os conjuntos de backup a serem restaurados** , selecione os backups a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="15e8a-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="15e8a-144">Essa grade exibe os backups disponíveis para o local especificado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="15e8a-145">Por padrão, um plano de recuperação é sugerido.</span><span class="sxs-lookup"><span data-stu-id="15e8a-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="15e8a-146">Para substituir o plano de recuperação sugerido, você pode alterar as seleções na grade.</span><span class="sxs-lookup"><span data-stu-id="15e8a-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="15e8a-147">Todos os backups que dependem de um backup não selecionado serão desmarcados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="15e8a-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="15e8a-148">Título da coluna</span><span class="sxs-lookup"><span data-stu-id="15e8a-148">Column head</span></span>|<span data-ttu-id="15e8a-149">Valores</span><span class="sxs-lookup"><span data-stu-id="15e8a-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="15e8a-150">**Restaurar**</span><span class="sxs-lookup"><span data-stu-id="15e8a-150">**Restore**</span></span>|<span data-ttu-id="15e8a-151">As caixas de seleção selecionadas indicam os conjuntos de backup a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="15e8a-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="15e8a-152">**Nome**</span><span class="sxs-lookup"><span data-stu-id="15e8a-152">**Name**</span></span>|<span data-ttu-id="15e8a-153">O nome do conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="15e8a-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="15e8a-154">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="15e8a-154">**File Type**</span></span>|<span data-ttu-id="15e8a-155">Especifica o tipo dos dados na no backup: **Dados**, **Log** ou **Dados de Fluxo de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="15e8a-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="15e8a-156">Dados que são contidos em tabelas estão nos arquivos **Dados** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="15e8a-157">Dados de log de transações estão nos arquivos **Log** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="15e8a-158">Dados de BLOB (objeto binário grande) armazenados no sistema de arquivos estão localizados em arquivos de **Dados do Fluxo de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="15e8a-159">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="15e8a-159">**Type**</span></span>|<span data-ttu-id="15e8a-160">O tipo de backup realizado: **Total**, **Diferencial** ou **Log de Transações**.</span><span class="sxs-lookup"><span data-stu-id="15e8a-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="15e8a-161">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="15e8a-161">**Server**</span></span>|<span data-ttu-id="15e8a-162">Nome da instância do Mecanismo de Banco de Dados que executou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="15e8a-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="15e8a-163">**Nome Lógico do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="15e8a-163">**File Logical Name**</span></span>|<span data-ttu-id="15e8a-164">O nome lógico do arquivo.</span><span class="sxs-lookup"><span data-stu-id="15e8a-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="15e8a-165">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="15e8a-165">**Database**</span></span>|<span data-ttu-id="15e8a-166">Nome do banco de dados envolvido na operação de backup.</span><span class="sxs-lookup"><span data-stu-id="15e8a-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="15e8a-167">**Data de Início**</span><span class="sxs-lookup"><span data-stu-id="15e8a-167">**Start Date**</span></span>|<span data-ttu-id="15e8a-168">A data e hora de início da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="15e8a-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="15e8a-169">**Data de Conclusão**</span><span class="sxs-lookup"><span data-stu-id="15e8a-169">**Finish Date**</span></span>|<span data-ttu-id="15e8a-170">A data e hora da conclusão da operação de backup, apresentadas na configuração regional do cliente.</span><span class="sxs-lookup"><span data-stu-id="15e8a-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="15e8a-171">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="15e8a-171">**Size**</span></span>|<span data-ttu-id="15e8a-172">O tamanho do conjunto de backup em bytes.</span><span class="sxs-lookup"><span data-stu-id="15e8a-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="15e8a-173">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="15e8a-173">**User Name**</span></span>|<span data-ttu-id="15e8a-174">O nome do usuário que realizou a operação de backup.</span><span class="sxs-lookup"><span data-stu-id="15e8a-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="15e8a-175">No painel **Selecionar uma página** , clique na página **Opções** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="15e8a-176">Na grade **Restaurar os arquivos de banco de dados como** , especifique um novo local para o arquivo ou arquivos que você quer mover.</span><span class="sxs-lookup"><span data-stu-id="15e8a-176">In the **Restore database files as** grid, specify a new location for the file or files that you want to move.</span></span>  
  
    |<span data-ttu-id="15e8a-177">Título da coluna</span><span class="sxs-lookup"><span data-stu-id="15e8a-177">Column head</span></span>|<span data-ttu-id="15e8a-178">Valores</span><span class="sxs-lookup"><span data-stu-id="15e8a-178">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="15e8a-179">**Nome do arquivo original**</span><span class="sxs-lookup"><span data-stu-id="15e8a-179">**Original File Name**</span></span>|<span data-ttu-id="15e8a-180">O caminho completo do arquivo de backup de origem.</span><span class="sxs-lookup"><span data-stu-id="15e8a-180">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="15e8a-181">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="15e8a-181">**File Type**</span></span>|<span data-ttu-id="15e8a-182">Especifica o tipo dos dados na no backup: **Dados**, **Log** ou **Dados de Fluxo de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="15e8a-182">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="15e8a-183">Dados que são contidos em tabelas estão nos arquivos **Dados** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-183">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="15e8a-184">Dados de log de transações estão nos arquivos **Log** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-184">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="15e8a-185">Dados de BLOB (objeto binário grande) armazenados no sistema de arquivos estão localizados em arquivos de **Dados do Fluxo de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="15e8a-185">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="15e8a-186">**Restaurar Como**</span><span class="sxs-lookup"><span data-stu-id="15e8a-186">**Restore As**</span></span>|<span data-ttu-id="15e8a-187">O caminho completo do arquivo de banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-187">The full path of the database file to be restored.</span></span> <span data-ttu-id="15e8a-188">Para especificar um novo arquivo de restauração, clique na caixa de texto e edite o caminho sugerido e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="15e8a-188">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="15e8a-189">Alterar o caminho ou o nome do arquivo na coluna **Restaurar Como** é equivalente ao uso da opção MOVE em uma declaração RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15e8a-189">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="15e8a-190">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15e8a-190">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="15e8a-191">Para restaurar arquivos para um novo local</span><span class="sxs-lookup"><span data-stu-id="15e8a-191">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="15e8a-192">Opcionalmente, execute a instrução RESTORE FILELISTONLY para determinar o número e os nomes dos arquivos no backup de banco de dados completo.</span><span class="sxs-lookup"><span data-stu-id="15e8a-192">Optionally, execute the RESTORE FILELISTONLY statement to determine the number and names of the files in the full database backup.</span></span>  
  
2.  <span data-ttu-id="15e8a-193">Execute a instrução RESTORE DATABASE para restaurar o backup de banco de dados completo, especificando:</span><span class="sxs-lookup"><span data-stu-id="15e8a-193">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="15e8a-194">O nome do banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-194">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="15e8a-195">O dispositivo de backup do qual o backup de banco de dados completo será restaurado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-195">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="15e8a-196">A cláusula MOVE para cada arquivo a ser restaurado em um no local</span><span class="sxs-lookup"><span data-stu-id="15e8a-196">The MOVE clause for each file to restore to a new location.</span></span>  
  
    -   <span data-ttu-id="15e8a-197">A cláusula NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="15e8a-197">The NORECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="15e8a-198">Se os arquivos foram modificados depois que o backup de arquivo foi criado, execute a instrução RESTORE LOG para aplicar o backup de log de transações, especificando:</span><span class="sxs-lookup"><span data-stu-id="15e8a-198">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="15e8a-199">O nome do banco de dados ao qual o log de transações será aplicado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-199">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="15e8a-200">O dispositivo de backup do qual o backup de log de transações será restaurado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-200">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="15e8a-201">A cláusula NORECOVERY se você tiver outro backup de log de transações para aplicar depois do atual; caso contrário, especifique a cláusula RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="15e8a-201">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="15e8a-202">Os backups de log de transações, se aplicados, devem cobrir a hora em que os backups dos arquivos e grupos de arquivos foram feitos.</span><span class="sxs-lookup"><span data-stu-id="15e8a-202">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="15e8a-203">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="15e8a-203">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="15e8a-204">Esse exemplo restaura dois dos arquivos para o banco de dados `MyNwind` que ficavam originalmente localizados no Drive C em novos locais no Drive D. Dois logs de transações também serão aplicados para restaurar o banco de dados para a hora atual.</span><span class="sxs-lookup"><span data-stu-id="15e8a-204">This example restores two of the files for the `MyNwind` database that were originally located on Drive C to new locations on Drive D. Two transaction logs will also be applied to restore the database to the current time.</span></span> <span data-ttu-id="15e8a-205">A instrução `RESTORE FILELISTONLY` é usada para determinar o número e os nomes lógicos e físicos dos arquivos no banco de dados que está sendo restaurado.</span><span class="sxs-lookup"><span data-stu-id="15e8a-205">The `RESTORE FILELISTONLY` statement is used to determine the number and logical and physical names of the files in the database being restored.</span></span>  
  
```sql  
USE master;  
GO  
-- First determine the number and names of the files in the backup.  
RESTORE FILELISTONLY  
   FROM MyNwind_1;  
-- Restore the files for MyNwind.  
RESTORE DATABASE MyNwind  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   MOVE 'MyNwind_data_1' TO 'D:\MyData\MyNwind_data_1.mdf',   
   MOVE 'MyNwind_data_2' TO 'D:\MyData\MyNwind_data_2.ndf';  
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
  
## <a name="see-also"></a><span data-ttu-id="15e8a-206">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15e8a-206">See Also</span></span>  
 <span data-ttu-id="15e8a-207">[Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="15e8a-207">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="15e8a-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15e8a-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="15e8a-209">[Copiar bancos de dados com backup e restauração](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="15e8a-209">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="15e8a-210">Restaurar arquivos e grupos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="15e8a-210">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
  
