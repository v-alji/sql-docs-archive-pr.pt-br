---
title: Criar índices clusterizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], clustered indexes
- clustered indexes, creating
- clustered indexes, PRIMARY KEY constraint
- clustered indexes, UNIQUE constraint
- indexes [SQL Server], clustered
ms.assetid: 47148383-c2c7-4f08-a9e4-7016bf2d1d13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 567ff9a01bd93323149168b9e3aa0f34d78aee39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573001"
---
# <a name="create-clustered-indexes"></a><span data-ttu-id="bef02-102">Criar índices clusterizados</span><span class="sxs-lookup"><span data-stu-id="bef02-102">Create Clustered Indexes</span></span>
  <span data-ttu-id="bef02-103">Você pode criar índices clusterizados em tabelas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bef02-103">You can create clustered indexes on tables in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bef02-104">Com poucas exceções, toda tabela deveria ter um índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="bef02-104">With few exceptions, every table should have a clustered index.</span></span> <span data-ttu-id="bef02-105">Além de melhorar o desempenho da consulta, o índice clusterizado pode ser recompilado ou reorganizado sob demanda para controlar a fragmentação de tabela.</span><span class="sxs-lookup"><span data-stu-id="bef02-105">Besides improving query performance, a clustered index can be rebuilt or reorganized on demand to control table fragmentation.</span></span> <span data-ttu-id="bef02-106">Um índice clusterizado também pode ser criado em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="bef02-106">A clustered index can also be created on a view.</span></span> <span data-ttu-id="bef02-107">(Os índices clusterizados são definidos no tópico [Índices clusterizados e não clusterizados descritos](clustered-and-nonclustered-indexes-described.md).)</span><span class="sxs-lookup"><span data-stu-id="bef02-107">(Clustered indexes are defined in the topic [Clustered and Nonclustered Indexes Described](clustered-and-nonclustered-indexes-described.md).)</span></span>  
  
 <span data-ttu-id="bef02-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="bef02-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bef02-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="bef02-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bef02-110">Implementações comuns</span><span class="sxs-lookup"><span data-stu-id="bef02-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="bef02-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="bef02-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bef02-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="bef02-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bef02-113">**Para criar um índice clusterizado em uma tabela, usando:**</span><span class="sxs-lookup"><span data-stu-id="bef02-113">**To create a clustered index on a table, using:**</span></span>  
  
     [<span data-ttu-id="bef02-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bef02-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bef02-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bef02-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bef02-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bef02-116">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="bef02-117">Implementações comuns</span><span class="sxs-lookup"><span data-stu-id="bef02-117">Typical Implementations</span></span>  
 <span data-ttu-id="bef02-118">Os índices clusterizados são implementados das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="bef02-118">Clustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="bef02-119">**Restrições PRIMARY KEY e UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="bef02-119">**PRIMARY KEY and UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="bef02-120">Quando se cria uma restrição PRIMARY KEY, é criado automaticamente um índice clusterizado exclusivo na coluna ou a coluna é automaticamente criada se não existir um índice clusterizado na tabela e você não especificar um índice não clusterizado exclusivo.</span><span class="sxs-lookup"><span data-stu-id="bef02-120">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="bef02-121">A coluna de chave primária não pode permitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="bef02-121">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="bef02-122">Quando se cria uma restrição UNIQUE, é criado, por padrão, um índice não clusterizado exclusivo para impor uma restrição UNIQUE por padrão.</span><span class="sxs-lookup"><span data-stu-id="bef02-122">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="bef02-123">Você pode especificar um índice clusterizado exclusivo caso ainda não exista um índice clusterizado na tabela.</span><span class="sxs-lookup"><span data-stu-id="bef02-123">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="bef02-124">O índice criado como parte da restrição recebe automaticamente o mesmo nome da restrição.</span><span class="sxs-lookup"><span data-stu-id="bef02-124">An index created as part of the constraint is automatically given the same name as the constraint name.</span></span> <span data-ttu-id="bef02-125">Para obter mais informações, consulte [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) e [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="bef02-125">For more information, see [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) and [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="bef02-126">**Índice independente de uma restrição**</span><span class="sxs-lookup"><span data-stu-id="bef02-126">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="bef02-127">Você pode criar um índice clusterizado em uma coluna diferente da coluna de chave primária se uma restrição de chave primária não clusterizada tiver sido especificada.</span><span class="sxs-lookup"><span data-stu-id="bef02-127">You can create a clustered index on a column other than primary key column if a nonclustered primary key constraint was specified.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bef02-128">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="bef02-128">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bef02-129">Quando uma estrutura de índice clusterizado é criada, o espaço em disco de ambas as estruturas, a antiga (origem) e a nova (destino), é necessário em seus respectivos arquivos e grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bef02-129">When a clustered index structure is created, disk space for both the old (source) and new (target) structures is required in their respective files and filegroups.</span></span> <span data-ttu-id="bef02-130">A antiga estrutura não é desalocada até que a transação completa seja confirmada.</span><span class="sxs-lookup"><span data-stu-id="bef02-130">The old structure is not deallocated until the complete transaction commits.</span></span> <span data-ttu-id="bef02-131">Pode igualmente ser necessário espaço temporário em disco adicional, para classificação.</span><span class="sxs-lookup"><span data-stu-id="bef02-131">Additional temporary disk space for sorting may also be required.</span></span> <span data-ttu-id="bef02-132">Para obter mais informações, consulte [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span><span class="sxs-lookup"><span data-stu-id="bef02-132">For more information, see [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span></span>  
  
-   <span data-ttu-id="bef02-133">Se um índice clusterizado for criado em uma pilha com vários índices não clusterizados existentes, todos os índices não clusterizados deverão ser recriados de modo que contenham o valor de chave de clusterização em vez do RID (Identificador de Linha).</span><span class="sxs-lookup"><span data-stu-id="bef02-133">If a clustered index is created on a heap with several existing nonclustered indexes, all the nonclustered indexes must be rebuilt so that they contain the clustering key value instead of the row identifier (RID).</span></span> <span data-ttu-id="bef02-134">Da mesma forma, se um índice clusterizado for cancelado em uma tabela com vários índices não clusterizados, os índices não clusterizados serão todos recriados como parte da operação DROP.</span><span class="sxs-lookup"><span data-stu-id="bef02-134">Similarly, if a clustered index is dropped on a table that has several nonclustered indexes, the nonclustered indexes are all rebuilt as part of the DROP operation.</span></span> <span data-ttu-id="bef02-135">Isso pode despender um tempo significativo em tabelas grandes.</span><span class="sxs-lookup"><span data-stu-id="bef02-135">This may take significant time on large tables.</span></span>  
  
     <span data-ttu-id="bef02-136">A forma preferencial de criação de índices em tabelas grandes é iniciar com o índice clusterizado e depois criar os índices não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="bef02-136">The preferred way to build indexes on large tables is to start with the clustered index and then build any nonclustered indexes.</span></span> <span data-ttu-id="bef02-137">Considere a definição da opção ONLINE como ON ao criar índices em tabelas existentes.</span><span class="sxs-lookup"><span data-stu-id="bef02-137">Consider setting the ONLINE option to ON when you create indexes on existing tables.</span></span> <span data-ttu-id="bef02-138">Quando definidos como ON, os bloqueios de tabela não são mantidos a longo prazo.</span><span class="sxs-lookup"><span data-stu-id="bef02-138">When set to ON, long-term table locks are not held.</span></span> <span data-ttu-id="bef02-139">Isso permite consultas ou atualizações à tabela subjacente para continuar.</span><span class="sxs-lookup"><span data-stu-id="bef02-139">This enables queries or updates to the underlying table to continue.</span></span> <span data-ttu-id="bef02-140">Para obter mais informações, consulte [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="bef02-140">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="bef02-141">A chave de um índice clusterizado não pode conter colunas `varchar` que tenham dados existentes na unidade de alocação ROW_OVERFLOW_DATA.</span><span class="sxs-lookup"><span data-stu-id="bef02-141">The index key of a clustered index cannot contain `varchar` columns that have existing data in the ROW_OVERFLOW_DATA allocation unit.</span></span> <span data-ttu-id="bef02-142">Se um índice clusterizado for criado em uma coluna `varchar` e os dados existentes estiverem na unidade de alocação IN_ROW_DATA, as ações subsequentes de inserção ou atualização na coluna que faria o push dos dados da linha apresentarão falha.</span><span class="sxs-lookup"><span data-stu-id="bef02-142">If a clustered index is created on a `varchar` column and the existing data is in the IN_ROW_DATA allocation unit, subsequent insert or update actions on the column that would push the data off-row will fail.</span></span> <span data-ttu-id="bef02-143">Para obter informações sobre tabelas que podem conter dados de estouro de linha, use a função de gerenciamento dinâmico [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bef02-143">To obtain information about tables that might contain row-overflow data, use the [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) dynamic management function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bef02-144">Segurança</span><span class="sxs-lookup"><span data-stu-id="bef02-144">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bef02-145">Permissões</span><span class="sxs-lookup"><span data-stu-id="bef02-145">Permissions</span></span>  
 <span data-ttu-id="bef02-146">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="bef02-146">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="bef02-147">O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="bef02-147">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bef02-148">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bef02-148">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-object-explorer"></a><span data-ttu-id="bef02-149">Para criar um índice clusterizado usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="bef02-149">To create a clustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="bef02-150">No Pesquisador de Objetos, expanda a tabela na qual você deseja criar um índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="bef02-150">In Object Explorer, expand the table on which you want to create a clustered index.</span></span>  
  
2.  <span data-ttu-id="bef02-151">Clique com o botão direito do mouse na pasta **Índices**, aponte para **Novo Índice** e selecione **Índice Clusterizado...** .</span><span class="sxs-lookup"><span data-stu-id="bef02-151">Right-click the **Indexes** folder, point to **New Index**, and select **Clustered Index...**.</span></span>  
  
3.  <span data-ttu-id="bef02-152">Na caixa de diálogo **Novo Índice** , na página **Geral** , insira o nome do novo índice na caixa **Nome do índice** .</span><span class="sxs-lookup"><span data-stu-id="bef02-152">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
4.  <span data-ttu-id="bef02-153">Em **Colunas de chave de índice**, clique em **Adicionar...** .</span><span class="sxs-lookup"><span data-stu-id="bef02-153">Under **Index key columns**, click **Add...**.</span></span>  
  
5.  <span data-ttu-id="bef02-154">Na caixa de diálogo **selecionar colunas de**_table_name_ , marque a caixa de seleção da coluna da tabela a ser adicionada ao índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="bef02-154">In the **Select Columns from**_table_name_ dialog box, select the check box of the table column to be added to the clustered index.</span></span>  
  
6.  <span data-ttu-id="bef02-155">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bef02-155">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="bef02-156">Na caixa de diálogo **Novo Índice** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bef02-156">In the **New Index** dialog box, click **OK**.</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-the-table-designer"></a><span data-ttu-id="bef02-157">Para criar um índice clusterizado usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="bef02-157">To create a clustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="bef02-158">No Pesquisador de Objetos, expanda o banco de dados na qual você deseja criar uma tabela com um índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="bef02-158">In Object Explorer, expand the database on which you want to create a table with a clustered index.</span></span>  
  
2.  <span data-ttu-id="bef02-159">Clique com o botão direito do mouse na pasta **Tabelas** e clique em **Nova Tabela...** .</span><span class="sxs-lookup"><span data-stu-id="bef02-159">Right-click the **Tables** folder and click **New Table...**.</span></span>  
  
3.  <span data-ttu-id="bef02-160">Crie uma tabela como você faria normalmente.</span><span class="sxs-lookup"><span data-stu-id="bef02-160">Create a new table as you normally would.</span></span> <span data-ttu-id="bef02-161">Para obter mais informações, veja [Criar tabelas &#40;Mecanismo de Banco de Dados&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="bef02-161">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span>  
  
4.  <span data-ttu-id="bef02-162">Clique com o botão direito do mouse na tabela criada acima e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="bef02-162">Right-click the new table created above and click **Design**.</span></span>  
  
5.  <span data-ttu-id="bef02-163">No menu **Designer de Tabela** , clique em **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="bef02-163">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
6.  <span data-ttu-id="bef02-164">Na caixa de diálogo **Índices/Chaves** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bef02-164">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
7.  <span data-ttu-id="bef02-165">Selecione o novo índice na caixa de texto **Índice ou Chave Exclusiva/Primária Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="bef02-165">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
8.  <span data-ttu-id="bef02-166">Na grade, selecione **Criar como Clusterizado**e selecione **Sim** na lista suspensa, à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="bef02-166">In the grid, select **Create as Clustered**, and choose **Yes** from the drop-down list to the right of the property.</span></span>  
  
9. <span data-ttu-id="bef02-167">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="bef02-167">Click **Close**.</span></span>  
  
10. <span data-ttu-id="bef02-168">No menu **Arquivo** , clique em **Salvar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="bef02-168">On the **File** menu, click **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bef02-169">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bef02-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-clustered-index"></a><span data-ttu-id="bef02-170">Para criar um índice clusterizado</span><span class="sxs-lookup"><span data-stu-id="bef02-170">To create a clustered index</span></span>  
  
1.  <span data-ttu-id="bef02-171">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bef02-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bef02-172">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="bef02-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bef02-173">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="bef02-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Create a new table with three columns.  
    CREATE TABLE dbo.TestTable  
        (TestCol1 int NOT NULL,  
         TestCol2 nchar(10) NULL,  
         TestCol3 nvarchar(50) NULL);  
    GO  
    -- Create a clustered index called IX_TestTable_TestCol1  
    -- on the dbo.TestTable table using the TestCol1 column.  
    CREATE CLUSTERED INDEX IX_TestTable_TestCol1   
        ON dbo.TestTable (TestCol1);   
    GO  
    ```  
  
 <span data-ttu-id="bef02-174">Para obter mais informações, consulte [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bef02-174">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef02-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bef02-175">See Also</span></span>  
 <span data-ttu-id="bef02-176">[Criar chaves primárias](../tables/create-primary-keys.md) </span><span class="sxs-lookup"><span data-stu-id="bef02-176">[Create Primary Keys](../tables/create-primary-keys.md) </span></span>  
 [<span data-ttu-id="bef02-177">Criar restrições exclusivas</span><span class="sxs-lookup"><span data-stu-id="bef02-177">Create Unique Constraints</span></span>](../tables/create-unique-constraints.md)  
  
  
