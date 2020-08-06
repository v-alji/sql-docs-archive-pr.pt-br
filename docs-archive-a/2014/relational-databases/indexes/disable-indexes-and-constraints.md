---
title: Desabilitar índices e restrições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.disableindexes.f1
helpviewer_keywords:
- disabled indexes [SQL Server], index operations
- nonclustered indexes [SQL Server], disabling
- disabled indexes [SQL Server], guidelines
- clustered indexes, disabling
- constraints [SQL Server], disabling
- disabled indexes [SQL Server], viewing
- FOREIGN KEY constraints, disabling
- statistical information [SQL Server], indexes
- index disabling [SQL Server]
- indexed views [SQL Server], disabled indexes
ms.assetid: 2198f1af-fa44-47e9-92df-f4fde322ba18
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 40f9de4108be4defeb2353a9e7835c289641a819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685108"
---
# <a name="disable-indexes-and-constraints"></a><span data-ttu-id="b1a4c-102">Desabilitar índices e restrições</span><span class="sxs-lookup"><span data-stu-id="b1a4c-102">Disable Indexes and Constraints</span></span>
  <span data-ttu-id="b1a4c-103">Este tópico descreve como desabilitar um índice ou restrições no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1a4c-103">This topic describes how to disable an index or constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b1a4c-104">A desabilitação de um índice impede que o usuário o acesse, e que índices clusterizados acessem os dados da tabela subjacente.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-104">Disabling an index prevents user access to the index, and for clustered indexes to the underlying table data.</span></span> <span data-ttu-id="b1a4c-105">A definição do índice permanece nos metadados e as estatísticas do índice são mantidas em índices não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-105">The index definition remains in metadata, and index statistics are kept on nonclustered indexes.</span></span> <span data-ttu-id="b1a4c-106">A desabilitação de um índice não clusterizado ou clusterizado em uma exibição exclui fisicamente os dados do índice.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-106">Disabling a nonclustered or clustered index on a view physically deletes the index data.</span></span> <span data-ttu-id="b1a4c-107">A desabilitação de um índice clusterizado em uma tabela impede o acesso aos dados; os dados ainda permanecem na tabela, mas ficam indisponíveis para operações DML (linguagem de manipulação de dados) até que o índice seja descartado ou recriado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-107">Disabling a clustered index on a table prevents access to the data; the data still remains in the table, but is unavailable for data manipulation language (DML) operations until the index is dropped or rebuilt.</span></span>  
  
 <span data-ttu-id="b1a4c-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b1a4c-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b1a4c-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b1a4c-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b1a4c-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="b1a4c-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b1a4c-112">**Para desabilitar um índice usando:**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-112">**To disable an index, using:**</span></span>  
  
     [<span data-ttu-id="b1a4c-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1a4c-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b1a4c-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1a4c-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b1a4c-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b1a4c-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b1a4c-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b1a4c-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b1a4c-117">O índice não é mantido enquanto estiver desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-117">The index is not maintained while it is disabled.</span></span>  
  
-   <span data-ttu-id="b1a4c-118">O otimizador de consulta não considera o índice desabilitado ao criar planos de execução de consulta.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-118">The query optimizer does not consider the disabled index when creating query execution plans.</span></span> <span data-ttu-id="b1a4c-119">As consultas que referenciam o índice desabilitado com uma dica de tabela também falham.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-119">Also, queries that reference the disabled index with a table hint fail.</span></span>  
  
-   <span data-ttu-id="b1a4c-120">Você não pode criar um índice que usa o mesmo nome que um índice desabilitado existente.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-120">You cannot create an index that uses the same name as an existing disabled index.</span></span>  
  
-   <span data-ttu-id="b1a4c-121">Um índice desabilitado pode ser cancelado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-121">A disabled index can be dropped.</span></span>  
  
-   <span data-ttu-id="b1a4c-122">Ao desabilitar um índice exclusivo, a restrição PRIMARY KEY ou UNIQUE e todas as restrições FOREIGN KEY que referenciam as colunas indexadas de outras tabelas também são desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-122">When disabling a unique index, the PRIMARY KEY or UNIQUE constraint and all FOREIGN KEY constraints that reference the indexed columns from other tables are also disabled.</span></span> <span data-ttu-id="b1a4c-123">Ao desabilitar um índice clusterizado, todas as restrições FOREIGN KEY de entrada e saída na tabela subjacente também são desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-123">When disabling a clustered index, all incoming and outgoing FOREIGN KEY constraints on the underlying table are also disabled.</span></span> <span data-ttu-id="b1a4c-124">Os nomes das restrições são listados em uma mensagem de aviso quando o índice é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-124">The constraint names are listed in a warning message when the index is disabled.</span></span> <span data-ttu-id="b1a4c-125">Depois de recompilar o índice, todas as restrições devem ser habilitadas manualmente usando a instrução ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-125">After rebuilding the index, all constraints must be manually enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="b1a4c-126">Os índices não clusterizados são desabilitados automaticamente quando o índice clusterizado associado é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-126">Nonclustered indexes are automatically disabled when the associated clustered index is disabled.</span></span> <span data-ttu-id="b1a4c-127">Eles não podem ser habilitados até o índice clusterizado na tabela ou exibição ser habilitado ou o índice clusterizado na tabela for cancelado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-127">They cannot be enabled until either the clustered index on the table or view is enabled or the clustered index on the table is dropped.</span></span> <span data-ttu-id="b1a4c-128">Os índices não clusterizados devem ser explicitamente habilitados, a menos que o índice clusterizado tenha sido habilitado usando a instrução ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-128">Nonclustered indexes must be explicitly enabled, unless the clustered index was enabled by using the ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="b1a4c-129">A instrução ALTER INDEX ALL REBUILD recompila e habilita todos os índices desabilitados na tabela, com exceção dos índices desabilitados nas exibições.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-129">The ALTER INDEX ALL REBUILD statement rebuilds and enables all disabled indexes on the table, except for disabled indexes on views.</span></span> <span data-ttu-id="b1a4c-130">Os índices em exibições devem ser habilitados em uma instrução ALTER INDEX ALL REBUILD separada.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-130">Indexes on views must be enabled in a separate ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="b1a4c-131">Desabilitar um índice clusterizado em uma tabela também desabilita todos os índices clusterizados e não clusterizados em exibições que referenciam essa tabela.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-131">Disabling a clustered index on a table also disables all clustered and nonclustered indexes on views that reference that table.</span></span> <span data-ttu-id="b1a4c-132">Esses índices devem ser recompilados da mesma maneira que aqueles da tabela referenciada.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-132">These indexes must be rebuilt just as those on the referenced table.</span></span>  
  
-   <span data-ttu-id="b1a4c-133">As linhas de dados do índice clusterizado desabilitado não podem ser acessadas, exceto para cancelar ou recompilar o índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-133">The data rows of the disabled clustered index cannot be accessed except to drop or rebuild the clustered index.</span></span>  
  
-   <span data-ttu-id="b1a4c-134">Você pode recompilar um índice não clusterizado desabilitado online quando a tabela não tiver um índice clusterizado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-134">You can rebuild a disabled nonclustered index online when the table does not have a disabled clustered index.</span></span> <span data-ttu-id="b1a4c-135">Porém, sempre precisará recompilar um índice clusterizado desabilitado offline se você usar a instrução ALTER INDEX REBUILD ou CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-135">However, you must always rebuild a disabled clustered index offline if you use either the ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING statement.</span></span> <span data-ttu-id="b1a4c-136">Para obter mais informações sobre operações de índice online, consulte [Executar operações de índice online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="b1a4c-136">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="b1a4c-137">A instrução CREATE STATISTICS não pode ser executada com êxito em uma tabela que tem um índice clusterizado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-137">The CREATE STATISTICS statement cannot be successfully executed on a table that has a disabled clustered index.</span></span>  
  
-   <span data-ttu-id="b1a4c-138">A opção de banco de dados AUTO_CREATE_STATISTICS cria novas estatísticas em uma coluna quando o índice é desabilitado e existem as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="b1a4c-138">The AUTO_CREATE_STATISTICS database option creates new statistics on a column when the index is disabled and the following conditions exist:</span></span>  
  
    -   <span data-ttu-id="b1a4c-139">AUTO_CREATE_STATISTICS é definido como ON</span><span class="sxs-lookup"><span data-stu-id="b1a4c-139">AUTO_CREATE_STATISTICS is set to ON</span></span>  
  
    -   <span data-ttu-id="b1a4c-140">Não há nenhuma estatística existente para a coluna.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-140">There are no existing statistics for the column.</span></span>  
  
    -   <span data-ttu-id="b1a4c-141">As estatísticas são exigidas durante a otimização da consulta.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-141">Statistics are required during query optimization.</span></span>  
  
-   <span data-ttu-id="b1a4c-142">Se um índice clusterizado for desabilitado, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) não poderá retornar informações sobre a tabela subjacente. Em vez disso, a instrução reportará que o índice clusterizado está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-142">If a clustered index is disabled, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) cannot return information about the underlying table; instead, the statement reports that the clustered index is disabled.</span></span> <span data-ttu-id="b1a4c-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) não pode ser usado para desfragmentar um índice desabilitado; a instrução falha com uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) cannot be used to defragment a disabled index; the statement fails with an error message.</span></span> <span data-ttu-id="b1a4c-144">Você pode usar [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) para recriar um índice desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-144">You can use [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) to rebuild a disabled index.</span></span>  
  
-   <span data-ttu-id="b1a4c-145">Criar um novo índice clusterizado habilita índices não clusterizados previamente desabilitados.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-145">Creating a new clustered index enables previously disabled nonclustered indexes.</span></span> <span data-ttu-id="b1a4c-146">Para obter mais informações, consulte [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="b1a4c-146">For more information, see [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b1a4c-147">Segurança</span><span class="sxs-lookup"><span data-stu-id="b1a4c-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b1a4c-148">Permissões</span><span class="sxs-lookup"><span data-stu-id="b1a4c-148">Permissions</span></span>  
 <span data-ttu-id="b1a4c-149">Para executar ALTER INDEX, no mínimo, a permissão ALTER na tabela ou exibição é necessária.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-149">To execute ALTER INDEX, at a minimum, ALTER permission on the table or view is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b1a4c-150">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1a4c-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="b1a4c-151">Para desabilitar um índice</span><span class="sxs-lookup"><span data-stu-id="b1a4c-151">To disable an index</span></span>  
  
1.  <span data-ttu-id="b1a4c-152">No Pesquisador de Objetos, clique no sinal de adição ao lado do banco de dados que contém a tabela na qual você deseja desabilitar um índice.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable an index.</span></span>  
  
2.  <span data-ttu-id="b1a4c-153">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="b1a4c-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b1a4c-154">Clique no sinal de adição ao lado da tabela na qual você deseja desabilitar um índice.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-154">Click the plus sign to expand the table on which you want to disable an index.</span></span>  
  
4.  <span data-ttu-id="b1a4c-155">Clique no sinal de adição para expandir a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="b1a4c-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="b1a4c-156">Clique com o botão direito do mouse no índice a ser desabilitado e selecione **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-156">Right-click the index you want to disable and select **Disable**.</span></span>  
  
6.  <span data-ttu-id="b1a4c-157">Na caixa de diálogo **Desabilitar Índices** , verifique se o índice correto está na grade **Índices a serem desabilitados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-157">In the **Disable Indexes** dialog box, verify that the correct index is in the **Indexes to disable** grid and click **OK**.</span></span>  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="b1a4c-158">Para desabilitar todos os índices de uma tabela</span><span class="sxs-lookup"><span data-stu-id="b1a4c-158">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="b1a4c-159">No Pesquisador de Objetos, clique no sinal de adição para expandir o banco de dados que contém a tabela na qual você deseja desabilitar os índices.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-159">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable the indexes.</span></span>  
  
2.  <span data-ttu-id="b1a4c-160">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="b1a4c-160">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b1a4c-161">Clique no sinal de adição para expandir a tabela na qual você deseja desabilitar os índices.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-161">Click the plus sign to expand the table on which you want to disable the indexes.</span></span>  
  
4.  <span data-ttu-id="b1a4c-162">Clique com o botão direito do mouse na pasta **Índices** e selecione **Desabilitar Todos**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-162">Right-click the **Indexes** folder and select **Disable All**.</span></span>  
  
5.  <span data-ttu-id="b1a4c-163">Na caixa de diálogo **Desabilitar Índices** , verifique se os índices corretos estão na grade **Índices a serem desabilitados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-163">In the **Disable Indexes** dialog box, verify that the correct indexes are in the **Indexes to disable** grid and click **OK**.</span></span> <span data-ttu-id="b1a4c-164">Para remover um índice da grade **Índices a serem desabilitados** , selecione o índice e pressione a tecla Delete.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-164">To remove an index from the **Indexes to disable** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="b1a4c-165">As informações a seguir estão disponíveis na caixa de diálogo **Desabilitar Índices** :</span><span class="sxs-lookup"><span data-stu-id="b1a4c-165">The following information is available in the **Disable Indexes** dialog box:</span></span>  
  
 <span data-ttu-id="b1a4c-166">**Nome do Índice**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-166">**Index Name**</span></span>  
 <span data-ttu-id="b1a4c-167">Exibe o nome do índice.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-167">Displays the name of the index.</span></span> <span data-ttu-id="b1a4c-168">Durante a execução, esta coluna exibe também um ícone que representa o status.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-168">During execution, this column also displays an icon representing the status.</span></span>  
  
 <span data-ttu-id="b1a4c-169">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-169">**Table Name**</span></span>  
 <span data-ttu-id="b1a4c-170">Exibe o nome da tabela ou exibição na qual o índice foi criado.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-170">Displays the name of the table or view that the index was created on.</span></span>  
  
 <span data-ttu-id="b1a4c-171">**Tipo de Índice**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-171">**Index Type**</span></span>  
 <span data-ttu-id="b1a4c-172">Exibe o tipo de índice: **Clusterizado**, **Não clusterizado**, **Espacial**ou **XML**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-172">Displays the type of the index: **Clustered**, **Nonclustered**, **Spatial**, or **XML**.</span></span>  
  
 <span data-ttu-id="b1a4c-173">**Status**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-173">**Status**</span></span>  
 <span data-ttu-id="b1a4c-174">Exibe o status atual da operação de desabilitação.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-174">Displays the status of the disable operation.</span></span> <span data-ttu-id="b1a4c-175">Os possíveis valores após a execução são:</span><span class="sxs-lookup"><span data-stu-id="b1a4c-175">Possible values after execution are:</span></span>  
  
-   <span data-ttu-id="b1a4c-176">Em branco</span><span class="sxs-lookup"><span data-stu-id="b1a4c-176">Blank</span></span>  
  
     <span data-ttu-id="b1a4c-177">Antes de execução o **Status** fica em branco.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-177">Prior to execution **Status** is blank.</span></span>  
  
-   <span data-ttu-id="b1a4c-178">**Em andamento**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-178">**In progress**</span></span>  
  
     <span data-ttu-id="b1a4c-179">A desabilitação dos índices foi iniciada mas não está concluída.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-179">Disabling of the indexes has been started but is not complete.</span></span>  
  
-   <span data-ttu-id="b1a4c-180">**Êxito**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-180">**Success**</span></span>  
  
     <span data-ttu-id="b1a4c-181">A operação de desabilitação foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-181">The disable operation completed successfully.</span></span>  
  
-   <span data-ttu-id="b1a4c-182">**Erro**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-182">**Error**</span></span>  
  
     <span data-ttu-id="b1a4c-183">Foi encontrado um erro durante a operação de desabilitação do índice e a operação e a operação não foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-183">An error was encountered during the index disable operation, and the operation did not complete successfully.</span></span>  
  
-   <span data-ttu-id="b1a4c-184">**Stopped (parado)**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-184">**Stopped**</span></span>  
  
     <span data-ttu-id="b1a4c-185">A desabilitação do índice não foi concluída com êxito porque o usuário interrompeu a operação.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-185">The disable of the index was not completed successfully because the user stopped the operation.</span></span>  
  
 <span data-ttu-id="b1a4c-186">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="b1a4c-186">**Message**</span></span>  
 <span data-ttu-id="b1a4c-187">Fornece o texto de mensagens de erro durante a operação de desabilitação.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-187">Provides the text of error messages during the disable operation.</span></span> <span data-ttu-id="b1a4c-188">Durante a execução, os erros aparecem como hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-188">During execution, errors appear as hyperlinks.</span></span> <span data-ttu-id="b1a4c-189">O texto dos hiperlinks descreve o corpo do erro.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-189">The text of the hyperlinks describes the body of the error.</span></span> <span data-ttu-id="b1a4c-190">A coluna **Mensagem** raramente é grande o suficiente para acomodar o texto de mensagem completo.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-190">The **Message** column is rarely wide enough to read the full message text.</span></span> <span data-ttu-id="b1a4c-191">Há dois modos para obter o texto completo:</span><span class="sxs-lookup"><span data-stu-id="b1a4c-191">There are two ways to get the full text:</span></span>  
  
-   <span data-ttu-id="b1a4c-192">Mova o ponteiro de mouse sobre a célula de mensagem para exibir uma dica de ferramenta com o texto do erro.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-192">Move the mouse pointer over the message cell to display a ToolTip with the error text.</span></span>  
  
-   <span data-ttu-id="b1a4c-193">Clique no hiperlink para exibir uma caixa de diálogo que exibe o erro completo.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-193">Click the hyperlink to display a dialog box displaying the full error.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b1a4c-194">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1a4c-194">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="b1a4c-195">Para desabilitar um índice</span><span class="sxs-lookup"><span data-stu-id="b1a4c-195">To disable an index</span></span>  
  
1.  <span data-ttu-id="b1a4c-196">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1a4c-196">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b1a4c-197">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-197">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b1a4c-198">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-198">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- disables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    DISABLE;  
    ```  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="b1a4c-199">Para desabilitar todos os índices de uma tabela</span><span class="sxs-lookup"><span data-stu-id="b1a4c-199">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="b1a4c-200">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1a4c-200">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b1a4c-201">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-201">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b1a4c-202">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b1a4c-202">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Disables all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    DISABLE;  
    ```  
  
 <span data-ttu-id="b1a4c-203">Para obter mais informações, consulte [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1a4c-203">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
