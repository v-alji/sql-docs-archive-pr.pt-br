---
title: Reduzir um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkdatabase.f1
helpviewer_keywords:
- shrinking databases
- databases [SQL Server], shrinking
- decreasing database size
- database shrinking [SQL Server]
- reducing database size
ms.assetid: 83afbf74-fd50-4c39-831c-b1f473a50620
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246036bfea6dc8431f878165330f7f0571949897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678781"
---
# <a name="shrink-a-database"></a><span data-ttu-id="b61d4-102">Reduzir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b61d4-102">Shrink a Database</span></span>
  <span data-ttu-id="b61d4-103">Este tópico descreve como reduzir um banco de dados usando o Pesquisador de Objetos no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b61d4-103">This topic describes how to shrink a database by using Object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b61d4-104">A redução de arquivos de dados recupera espaço com a movimentação de páginas de dados do final do arquivo para o espaço desocupado mais próximo à frente do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b61d4-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="b61d4-105">Quando espaço livre suficiente é criado no final do arquivo, as páginas de dados no final do arquivo podem ser desalocadas e retornadas para o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b61d4-105">When enough free space is created at the end of the file, data pages at end of the file can be deallocated and returned to the file system.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b61d4-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b61d4-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b61d4-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b61d4-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b61d4-108">O banco de dados não pode se tornar menor que o tamanho mínimo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b61d4-108">The database cannot be made smaller than the minimum size of the database.</span></span> <span data-ttu-id="b61d4-109">O tamanho mínimo é aquele especificado na criação inicial do banco de dados ou o último tamanho explicitamente configurado por meio de uma operação de alteração de tamanho de arquivo, como DBCC SHRINKFILE.</span><span class="sxs-lookup"><span data-stu-id="b61d4-109">The minimum size is the size specified when the database was originally created, or the last explicit size set by using a file-size-changing operation, such as DBCC SHRINKFILE.</span></span> <span data-ttu-id="b61d4-110">Por exemplo, se um banco de dados foi criado originalmente com um tamanho de 10 MB e atingir 100 MB, a menor redução desse banco de dados será de 10 MB, mesmo se todos os dados do banco de dados forem excluídos.</span><span class="sxs-lookup"><span data-stu-id="b61d4-110">For example, if a database was originally created with a size of 10 MB and grew to 100 MB, the smallest size the database could be reduced to is 10 MB, even if all the data in the database has been deleted.</span></span>  
  
-   <span data-ttu-id="b61d4-111">Não é possível reduzir um banco de dados enquanto ele estiver sendo armazenado em backup.</span><span class="sxs-lookup"><span data-stu-id="b61d4-111">You cannot shrink a database while the database is being backed up.</span></span> <span data-ttu-id="b61d4-112">Da mesma forma, não é possível fazer backup de um banco de dados enquanto houver uma operação de redução em processamento.</span><span class="sxs-lookup"><span data-stu-id="b61d4-112">Conversely, you cannot backup a database while a shrink operation on the database is in process.</span></span>  
  
-   <span data-ttu-id="b61d4-113">DBCC SHRINKDATABASE falhará quando encontrar um índices columnstore xVelocity de memória otimizada.</span><span class="sxs-lookup"><span data-stu-id="b61d4-113">DBCC SHRINKDATABASE will fail when it encounters an xVelocity memory optimized columnstore index.</span></span> <span data-ttu-id="b61d4-114">O trabalho concluído antes de encontrar o índice de columnstore será bem-sucedido, de modo que o banco de dados talvez seja menor.</span><span class="sxs-lookup"><span data-stu-id="b61d4-114">Work completed before encountering the columnstore index will succeed so the database might be smaller.</span></span> <span data-ttu-id="b61d4-115">Para concluir DBCC SHRINKDATABASE, desabilite todos os índices de columnstore antes de executar DBCC SHRINKDATABASE e recrie os índices de columnstore.</span><span class="sxs-lookup"><span data-stu-id="b61d4-115">To complete DBCC SHRINKDATABASE, disable all columnstore indexes before executing DBCC SHRINKDATABASE, and then rebuild the columnstore indexes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b61d4-116">Recomendações</span><span class="sxs-lookup"><span data-stu-id="b61d4-116">Recommendations</span></span>  
  
-   <span data-ttu-id="b61d4-117">Para visualizar a quantidade atual de espaço livre (não alocado) no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b61d4-117">To view the current amount of free (unallocated) space in the database.</span></span> <span data-ttu-id="b61d4-118">Para obter mais informações, consulte [Exibir dados e informações de espaço de log para um banco de dados](display-data-and-log-space-information-for-a-database.md)</span><span class="sxs-lookup"><span data-stu-id="b61d4-118">For more information, see [Display Data and Log Space Information for a Database](display-data-and-log-space-information-for-a-database.md)</span></span>  
  
-   <span data-ttu-id="b61d4-119">Considere as seguintes informações ao planejar reduzir um banco de dados:</span><span class="sxs-lookup"><span data-stu-id="b61d4-119">Consider the following information when you plan to shrink a database:</span></span>  
  
    -   <span data-ttu-id="b61d4-120">Uma operação de redução é mais eficiente depois de uma operação que cria muito espaço não utilizado, como operações que truncam ou excluem uma tabela.</span><span class="sxs-lookup"><span data-stu-id="b61d4-120">A shrink operation is most effective after an operation that creates lots of unused space, such as a truncate table or a drop table operation.</span></span>  
  
    -   <span data-ttu-id="b61d4-121">A maioria dos bancos de dados exige algum espaço livre disponível para operações comuns rotineiras.</span><span class="sxs-lookup"><span data-stu-id="b61d4-121">Most databases require some free space to be available for regular day-to-day operations.</span></span> <span data-ttu-id="b61d4-122">Se você reduzir um banco de dados repetidamente e perceber que ele aumentou novamente, isso indica que o espaço reduzido é necessário para as operações rotineiras.</span><span class="sxs-lookup"><span data-stu-id="b61d4-122">If you shrink a database repeatedly and notice that the database size grows again, this indicates that the space that was shrunk is required for regular operations.</span></span> <span data-ttu-id="b61d4-123">Nesse caso, reduzir repetidamente um banco de dados é uma operação inútil.</span><span class="sxs-lookup"><span data-stu-id="b61d4-123">In these cases, repeatedly shrinking the database is a wasted operation.</span></span>  
  
    -   <span data-ttu-id="b61d4-124">Uma operação de redução não preserva o estado de fragmentação de índices do banco de dados e, geralmente, aumenta o nível de fragmentação.</span><span class="sxs-lookup"><span data-stu-id="b61d4-124">A shrink operation does not preserve the fragmentation state of indexes in the database, and generally increases fragmentation to a degree.</span></span> <span data-ttu-id="b61d4-125">Essa é outra razão para não reduzir o banco de dados repetidamente.</span><span class="sxs-lookup"><span data-stu-id="b61d4-125">This is another reason not to repeatedly shrink the database.</span></span>  
  
    -   <span data-ttu-id="b61d4-126">A menos que você tenha um requisito específico, não defina a opção de banco de dados AUTO_SHRINK como ON.</span><span class="sxs-lookup"><span data-stu-id="b61d4-126">Unless you have a specific requirement, do not set the AUTO_SHRINK database option to ON.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b61d4-127">Segurança</span><span class="sxs-lookup"><span data-stu-id="b61d4-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b61d4-128">Permissões</span><span class="sxs-lookup"><span data-stu-id="b61d4-128">Permissions</span></span>  
 <span data-ttu-id="b61d4-129">Exige associação à função de servidor fixa **sysadmin** ou à função de banco de dados fixa **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="b61d4-129">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b61d4-130">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b61d4-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="b61d4-131">Para reduzir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b61d4-131">To shrink a database</span></span>  
  
1.  <span data-ttu-id="b61d4-132">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="b61d4-132">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="b61d4-133">Expanda **Bancos de Dados**e clique com o botão direito do mouse no banco de dados que deseja reduzir.</span><span class="sxs-lookup"><span data-stu-id="b61d4-133">Expand **Databases**, and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="b61d4-134">Aponte para **Tarefas**, depois **Reduzir**e clique em **Banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="b61d4-134">Point to **Tasks**, point to **Shrink**, and then click **Database**.</span></span>  
  
     <span data-ttu-id="b61d4-135">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="b61d4-135">**Database**</span></span>  
     <span data-ttu-id="b61d4-136">Exibe o nome do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="b61d4-136">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="b61d4-137">**Espaço alocado atual**</span><span class="sxs-lookup"><span data-stu-id="b61d4-137">**Current allocated space**</span></span>  
     <span data-ttu-id="b61d4-138">Exibe o espaço total utilizado e não utilizado para o banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="b61d4-138">Displays the total used and unused space for the selected database.</span></span>  
  
     <span data-ttu-id="b61d4-139">**Espaço livre disponível**</span><span class="sxs-lookup"><span data-stu-id="b61d4-139">**Available free space**</span></span>  
     <span data-ttu-id="b61d4-140">Exibe a soma de espaço livre no log e nos arquivos de dados do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="b61d4-140">Displays the sum of free space in the log and data files of the selected database.</span></span>  
  
     <span data-ttu-id="b61d4-141">**Reorganizar arquivos antes de liberar espaço não utilizado**</span><span class="sxs-lookup"><span data-stu-id="b61d4-141">**Reorganize files before releasing unused space**</span></span>  
     <span data-ttu-id="b61d4-142">Selecionar essa opção é equivalente a executar DBCC SHRINKDATABASE especificando uma opção de porcentagem de destino.</span><span class="sxs-lookup"><span data-stu-id="b61d4-142">Selecting this option is equivalent to executing DBCC SHRINKDATABASE specifying a target percent option.</span></span> <span data-ttu-id="b61d4-143">Desmarcar esta opção é o mesmo que executar DBCC SHRINKDATABASE com a opção TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="b61d4-143">Clearing this option is equivalent to executing DBCC SHRINKDATABASE with TRUNCATEONLY option.</span></span> <span data-ttu-id="b61d4-144">Por padrão, essa opção não é selecionada quando a caixa de diálogo está aberta.</span><span class="sxs-lookup"><span data-stu-id="b61d4-144">By default, this option is not selected when the dialog is opened.</span></span> <span data-ttu-id="b61d4-145">Se esta opção for selecionada, o usuário deverá especificar uma opção de porcentagem de destino.</span><span class="sxs-lookup"><span data-stu-id="b61d4-145">If this option is selected, the user must specify a target percent option.</span></span>  
  
     <span data-ttu-id="b61d4-146">**Máximo espaço livre em arquivos após a redução**</span><span class="sxs-lookup"><span data-stu-id="b61d4-146">**Maximum free space in files after shrinking**</span></span>  
     <span data-ttu-id="b61d4-147">Digite a porcentagem máxima de espaço livre a ser deixado nos arquivos de banco de dados após a redução do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b61d4-147">Enter the maximum percentage of free space to be left in the database files after the database has been shrunk.</span></span> <span data-ttu-id="b61d4-148">Os valores permitidos estão entre 0 e 99.</span><span class="sxs-lookup"><span data-stu-id="b61d4-148">Permissible values are between 0 and 99.</span></span>  
  
4.  <span data-ttu-id="b61d4-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b61d4-149">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b61d4-150">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b61d4-150">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="b61d4-151">Para reduzir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b61d4-151">To shrink a database</span></span>  
  
1.  <span data-ttu-id="b61d4-152">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b61d4-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b61d4-153">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b61d4-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b61d4-154">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b61d4-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b61d4-155">Este exemplo usa [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) para reduzir o tamanho dos arquivos de dados e de log no banco de dados `UserDB` e liberar `10` por cento de espaço livre no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b61d4-155">This example uses [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) to decreases the size of the data and log files in the `UserDB` database and to allow for `10` percent free space in the database.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKDB1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkdb1)]  
  
##  <a name="follow-up-after-you-shrink-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="b61d4-156">Acompanhamento: depois de reduzir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="b61d4-156">Follow Up: After you shrink a database</span></span>  
 <span data-ttu-id="b61d4-157">Os dados movidos para reduzir um arquivo podem ser espalhados para qualquer local disponível no arquivo.</span><span class="sxs-lookup"><span data-stu-id="b61d4-157">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="b61d4-158">Isso provoca uma fragmentação do índice e pode reduzir a velocidade do desempenho de consultas que pesquisam um intervalo do índice.</span><span class="sxs-lookup"><span data-stu-id="b61d4-158">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="b61d4-159">Para eliminar a fragmentação, considere a recompilação dos índices no arquivo após a redução.</span><span class="sxs-lookup"><span data-stu-id="b61d4-159">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61d4-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b61d4-160">See Also</span></span>  
 <span data-ttu-id="b61d4-161">[Reduzir um arquivo](shrink-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="b61d4-161">[Shrink a File](shrink-a-file.md) </span></span>  
 <span data-ttu-id="b61d4-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b61d4-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="b61d4-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b61d4-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="b61d4-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b61d4-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="b61d4-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b61d4-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span></span>  
 [<span data-ttu-id="b61d4-166">Arquivos e grupos de arquivos do banco de dados</span><span class="sxs-lookup"><span data-stu-id="b61d4-166">Database Files and Filegroups</span></span>](database-files-and-filegroups.md)  
  
  
