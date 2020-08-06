---
title: Criar índices filtrados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- filtered indexes [SQL Server], about filtered indexes
- designing indexes [SQL Server], filtered
- filtered indexes [SQL Server]
- nonclustered indexes [SQL Server], filtered
- indexes [SQL Server], filtered
ms.assetid: 25e1fcc5-45d7-4c53-8c79-5493dfaa1c74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77cf641ca84181496f26a995244029d0525ade63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685127"
---
# <a name="create-filtered-indexes"></a><span data-ttu-id="e517b-102">Criar índices filtrados</span><span class="sxs-lookup"><span data-stu-id="e517b-102">Create Filtered Indexes</span></span>
  <span data-ttu-id="e517b-103">Este tópico descreve como criar um índice filtrado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e517b-103">This topic describes how to create a filtered index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e517b-104">Um índice filtrado é um índice não clusterizado otimizado, criado especialmente para consultas que fazem seleções a partir de um subconjunto bem definido de dados.</span><span class="sxs-lookup"><span data-stu-id="e517b-104">A filtered index is an optimized nonclustered index especially suited to cover queries that select from a well-defined subset of data.</span></span> <span data-ttu-id="e517b-105">Ele usa um predicado de filtro para indexar uma parte das linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="e517b-105">It uses a filter predicate to index a portion of rows in the table.</span></span> <span data-ttu-id="e517b-106">Um índice filtrado bem projetado pode melhorar o desempenho da consulta, bem como reduzir os custos de manutenção e de armazenamento do índice em comparação com os índices de tabela completa.</span><span class="sxs-lookup"><span data-stu-id="e517b-106">A well-designed filtered index can improve query performance as well as reduce index maintenance and storage costs compared with full-table indexes.</span></span>  
  
 <span data-ttu-id="e517b-107">Os índices filtrados podem oferecer as seguintes vantagens com relação aos índices de tabela completa:</span><span class="sxs-lookup"><span data-stu-id="e517b-107">Filtered indexes can provide the following advantages over full-table indexes:</span></span>  
  
-   <span data-ttu-id="e517b-108">**Melhor desempenho de consultas e qualidade de plano**</span><span class="sxs-lookup"><span data-stu-id="e517b-108">**Improved query performance and plan quality**</span></span>  
  
     <span data-ttu-id="e517b-109">Um índice filtrado bem projetado melhora o desempenho das consultas e a qualidade do plano de execução porque é menor do que um índice não clusterizado de tabela completa e possui estatísticas filtradas.</span><span class="sxs-lookup"><span data-stu-id="e517b-109">A well-designed filtered index improves query performance and execution plan quality because it is smaller than a full-table nonclustered index and has filtered statistics.</span></span> <span data-ttu-id="e517b-110">As estatísticas filtradas são mais precisas do que as estatísticas de tabela completa, pois abrangem apenas as linhas do índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="e517b-110">The filtered statistics are more accurate than full-table statistics because they cover only the rows in the filtered index.</span></span>  
  
-   <span data-ttu-id="e517b-111">**Redução dos custos de manutenção do índice**</span><span class="sxs-lookup"><span data-stu-id="e517b-111">**Reduced index maintenance costs**</span></span>  
  
     <span data-ttu-id="e517b-112">A manutenção do índice é feita apenas quando as instruções DML (linguagem de manipulação de dados) afetam os dados do índice.</span><span class="sxs-lookup"><span data-stu-id="e517b-112">An index is maintained only when data manipulation language (DML) statements affect the data in the index.</span></span> <span data-ttu-id="e517b-113">Um índice filtrado reduz os custos de manutenção em comparação com o índice não clusterizado de tabela completa porque é menor e a manutenção é feita somente quando seus dados são alterados.</span><span class="sxs-lookup"><span data-stu-id="e517b-113">A filtered index reduces index maintenance costs compared with a full-table nonclustered index because it is smaller and is only maintained when the data in the index is changed.</span></span> <span data-ttu-id="e517b-114">É possível ter um grande número de índices filtrados, especialmente quando eles contêm dados que são raramente alterados.</span><span class="sxs-lookup"><span data-stu-id="e517b-114">It is possible to have a large number of filtered indexes, especially when they contain data that is changed infrequently.</span></span> <span data-ttu-id="e517b-115">Do mesmo modo, se um índice filtrado tiver apenas dados modificados com frequência, seu tamanho reduzido diminuirá o custo de atualização das estatísticas.</span><span class="sxs-lookup"><span data-stu-id="e517b-115">Similarly, if a filtered index contains only the frequently modified data, the smaller size of the index reduces the cost of updating the statistics.</span></span>  
  
-   <span data-ttu-id="e517b-116">**Redução dos custos de armazenamento do índice**</span><span class="sxs-lookup"><span data-stu-id="e517b-116">**Reduced index storage costs**</span></span>  
  
     <span data-ttu-id="e517b-117">A criação de um índice filtrado pode reduzir o armazenamento em disco de índices não clusterizados quando um índice de tabela completa não é necessário.</span><span class="sxs-lookup"><span data-stu-id="e517b-117">Creating a filtered index can reduce disk storage for nonclustered indexes when a full-table index is not necessary.</span></span> <span data-ttu-id="e517b-118">É possível substituir um índice não clusterizado de tabela completa por vários índices filtrados sem aumentar de forma significativa os requisitos de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="e517b-118">You can replace a full-table nonclustered index with multiple filtered indexes without significantly increasing the storage requirements.</span></span>  
  
 <span data-ttu-id="e517b-119">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="e517b-119">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e517b-120">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="e517b-120">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e517b-121">Considerações de criação</span><span class="sxs-lookup"><span data-stu-id="e517b-121">Design Considerations</span></span>](#Design)  
  
     [<span data-ttu-id="e517b-122">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="e517b-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e517b-123">Segurança</span><span class="sxs-lookup"><span data-stu-id="e517b-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e517b-124">**Para criar um índice filtrado usando:**</span><span class="sxs-lookup"><span data-stu-id="e517b-124">**To create a filtered index, using:**</span></span>  
  
     [<span data-ttu-id="e517b-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e517b-125">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e517b-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e517b-126">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e517b-127">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e517b-127">Before You Begin</span></span>  
  
###  <a name="design-considerations"></a><a name="Design"></a> <span data-ttu-id="e517b-128">Considerações de criação</span><span class="sxs-lookup"><span data-stu-id="e517b-128">Design Considerations</span></span>  
  
-   <span data-ttu-id="e517b-129">Quando a coluna tem apenas uma pequena quantidade de valores relevantes para consultas, você pode criar um índice filtrado no subconjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="e517b-129">When a column only has a small number of relevant values for queries, you can create a filtered index on the subset of values.</span></span> <span data-ttu-id="e517b-130">Por exemplo, se os valores de uma coluna forem predominantemente NULL e a consulta selecionar apenas valores não NULL, será possível criar um índice filtrado para linhas de dados não NULL.</span><span class="sxs-lookup"><span data-stu-id="e517b-130">For example, when the values in a column are mostly NULL and the query selects only from the non-NULL values, you can create a filtered index for the non-NULL data rows.</span></span> <span data-ttu-id="e517b-131">O índice resultante será menor e sua manutenção será menos dispendiosa em comparação com um índice não clusterizado de tabela completa definido nas mesmas colunas de chave.</span><span class="sxs-lookup"><span data-stu-id="e517b-131">The resulting index will be smaller and cost less to maintain than a full-table nonclustered index defined on the same key columns.</span></span>  
  
-   <span data-ttu-id="e517b-132">Quando a tabela contém linhas de dados heterogêneos, é possível criar um índice filtrado para uma ou mais categorias de dados.</span><span class="sxs-lookup"><span data-stu-id="e517b-132">When a table has heterogeneous data rows, you can create a filtered index for one or more categories of data.</span></span> <span data-ttu-id="e517b-133">Isso pode melhorar o desempenho das consultas nessas linhas de dados limitando o foco de uma consulta a uma área específica da tabela.</span><span class="sxs-lookup"><span data-stu-id="e517b-133">This can improve the performance of queries on these data rows by narrowing the focus of a query to a specific area of the table.</span></span> <span data-ttu-id="e517b-134">Novamente, o índice resultante será menor e sua manutenção será menos dispendiosa em comparação com um índice não clusterizado de tabela completa.</span><span class="sxs-lookup"><span data-stu-id="e517b-134">Again, the resulting index will be smaller and cost less to maintain than a full-table nonclustered index.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e517b-135">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="e517b-135">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e517b-136">Não é possível criar um índice filtrado em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="e517b-136">You cannot create a filtered index on a view.</span></span> <span data-ttu-id="e517b-137">No entanto, o otimizador de consulta pode se beneficiar do índice filtrado definido em uma tabela referenciada em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="e517b-137">However, the query optimizer can benefit from a filtered index defined on a table that is referenced in a view.</span></span> <span data-ttu-id="e517b-138">O otimizador de consulta considera um índice filtrado para uma consulta que seleciona uma exibição se os resultados da consulta estiverem corretos.</span><span class="sxs-lookup"><span data-stu-id="e517b-138">The query optimizer considers a filtered index for a query that selects from a view if the query results will be correct.</span></span>  
  
-   <span data-ttu-id="e517b-139">Os índices filtrados têm as seguintes vantagens em relação às exibições indexadas:</span><span class="sxs-lookup"><span data-stu-id="e517b-139">Filtered indexes have the following advantages over indexed views:</span></span>  
  
    -   <span data-ttu-id="e517b-140">Redução dos custos de manutenção do índice.</span><span class="sxs-lookup"><span data-stu-id="e517b-140">Reduced index maintenance costs.</span></span> <span data-ttu-id="e517b-141">Por exemplo, o processador de consulta usa menos recursos da CPU para atualizar um índice filtrado do que uma exibição indexada.</span><span class="sxs-lookup"><span data-stu-id="e517b-141">For example, the query processor uses fewer CPU resources to update a filtered index than an indexed view.</span></span>  
  
    -   <span data-ttu-id="e517b-142">Melhor qualidade de plano.</span><span class="sxs-lookup"><span data-stu-id="e517b-142">Improved plan quality.</span></span> <span data-ttu-id="e517b-143">Por exemplo, durante a compilação de uma consulta, o otimizador de consulta considera usar um índice filtrado em mais situações do que a exibição indexada equivalente.</span><span class="sxs-lookup"><span data-stu-id="e517b-143">For example, during query compilation, the query optimizer considers using a filtered index in more situations than the equivalent indexed view.</span></span>  
  
    -   <span data-ttu-id="e517b-144">Recriações de índice online.</span><span class="sxs-lookup"><span data-stu-id="e517b-144">Online index rebuilds.</span></span> <span data-ttu-id="e517b-145">É possível recriar índices filtrados enquanto estão disponíveis para consultas.</span><span class="sxs-lookup"><span data-stu-id="e517b-145">You can rebuild filtered indexes while they are available for queries.</span></span> <span data-ttu-id="e517b-146">As recriações de índices online não têm suporte para exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="e517b-146">Online index rebuilds are not supported for indexed views.</span></span> <span data-ttu-id="e517b-147">Para obter mais informações, veja a opção REBUILD de [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e517b-147">For more information, see the REBUILD option for [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
    -   <span data-ttu-id="e517b-148">Índices não exclusivos.</span><span class="sxs-lookup"><span data-stu-id="e517b-148">Non-unique indexes.</span></span> <span data-ttu-id="e517b-149">Os índices filtrados podem ser não exclusivos, enquanto as exibições indexadas devem ser exclusivas.</span><span class="sxs-lookup"><span data-stu-id="e517b-149">Filtered indexes can be non-unique, whereas indexed views must be unique.</span></span>  
  
-   <span data-ttu-id="e517b-150">Os índices filtrados são definidos em uma tabela e oferecem suporte apenas a operadores de comparação simples.</span><span class="sxs-lookup"><span data-stu-id="e517b-150">Filtered indexes are defined on one table and only support simple comparison operators.</span></span> <span data-ttu-id="e517b-151">Se você precisar de uma expressão de filtro que referencie várias tabelas ou que tenha uma lógica complexa, deverá criar uma exibição.</span><span class="sxs-lookup"><span data-stu-id="e517b-151">If you need a filter expression that references multiple tables or has complex logic, you should create a view.</span></span>  
  
-   <span data-ttu-id="e517b-152">A coluna na expressão do índice filtrado não precisará ser uma coluna de chave ou incluída na definição do índice filtrado, se a expressão do índice filtrado for equivalente ao predicado da consulta e a consulta não retorná-la com os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="e517b-152">A column in the filtered index expression does not need to be a key or included column in the filtered index definition if the filtered index expression is equivalent to the query predicate and the query does not return the column in the filtered index expression with the query results.</span></span>  
  
-   <span data-ttu-id="e517b-153">A coluna na expressão de índice filtrado deverá ser uma coluna de chave ou incluída na definição do índice filtrado se o predicado de consulta usá-la em uma comparação que não for equivalente à expressão do índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="e517b-153">A column in the filtered index expression should be a key or included column in the filtered index definition if the query predicate uses the column in a comparison that is not equivalent to the filtered index expression.</span></span>  
  
-   <span data-ttu-id="e517b-154">A coluna na expressão do índice filtrado deverá ser uma coluna de chave ou incluída na definição do índice filtrado se fizer parte do conjunto de resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="e517b-154">A column in the filtered index expression should be a key or included column in the filtered index definition if the column is in the query result set.</span></span>  
  
-   <span data-ttu-id="e517b-155">A chave de índice clusterizado da tabela não precisa ser uma coluna de chave ou incluída na definição do índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="e517b-155">The clustered index key of the table does not need to be a key or included column in the filtered index definition.</span></span> <span data-ttu-id="e517b-156">A chave de índice clusterizado é incluída automaticamente em todos os índices não clusterizados, inclusive índices filtrados.</span><span class="sxs-lookup"><span data-stu-id="e517b-156">The clustered index key is automatically included in all nonclustered indexes, including filtered indexes.</span></span>  
  
-   <span data-ttu-id="e517b-157">Se o operador de comparação especificado na expressão do índice filtrado resultar em uma conversão de dados implícita ou explícita, ocorrerá um erro se a conversão ocorrer à esquerda do operador de comparação.</span><span class="sxs-lookup"><span data-stu-id="e517b-157">If the comparison operator specified in the filtered index expression of the filtered index results in an implicit or explicit data conversion, an error will occur if the conversion occurs on the left side of a comparison operator.</span></span> <span data-ttu-id="e517b-158">Uma solução seria gravar a expressão do índice filtrado com o operador de conversão de dados (CAST ou CONVERT) à direita do operador de comparação.</span><span class="sxs-lookup"><span data-stu-id="e517b-158">A solution is to write the filtered index expression with the data conversion operator (CAST or CONVERT) on the right side of the comparison operator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e517b-159">Segurança</span><span class="sxs-lookup"><span data-stu-id="e517b-159">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e517b-160">Permissões</span><span class="sxs-lookup"><span data-stu-id="e517b-160">Permissions</span></span>  
 <span data-ttu-id="e517b-161">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="e517b-161">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="e517b-162">O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="e517b-162">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span> <span data-ttu-id="e517b-163">Para modificar a expressão de índice filtrado, use CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="e517b-163">To modify the filtered index expression, use CREATE INDEX WITH DROP_EXISTING.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e517b-164">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e517b-164">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="e517b-165">Para criar um índice filtrado</span><span class="sxs-lookup"><span data-stu-id="e517b-165">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="e517b-166">No Pesquisador de Objetos, clique no sinal de adição para expandir o banco de dados que contém a tabela na qual você deseja criar um índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="e517b-166">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create a filtered index.</span></span>  
  
2.  <span data-ttu-id="e517b-167">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="e517b-167">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="e517b-168">Clique no sinal de adição ao lado da tabela na qual você deseja criar um índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="e517b-168">Click the plus sign to expand the table on which you want to create a filtered index.</span></span>  
  
4.  <span data-ttu-id="e517b-169">Clique com o botão direito do mouse na pasta **Índices**, aponte para **Novo Índice** e selecione **Índice Não Clusterizado...** .</span><span class="sxs-lookup"><span data-stu-id="e517b-169">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="e517b-170">Na caixa de diálogo **Novo Índice** , na página **Geral** , insira o nome do novo índice na caixa **Nome do índice** .</span><span class="sxs-lookup"><span data-stu-id="e517b-170">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="e517b-171">Em **Colunas de chave de índice**, clique em **Adicionar...** .</span><span class="sxs-lookup"><span data-stu-id="e517b-171">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="e517b-172">Na caixa de diálogo **selecionar colunas de**_table_name_ , marque as caixas de seleção das colunas da tabela a serem adicionadas ao índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e517b-172">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
8.  <span data-ttu-id="e517b-173">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e517b-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="e517b-174">Na página **Filtro**, em **Expressão de Filtro**, digite a expressão SQL que você usará para criar o índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="e517b-174">On the **Filter** page, under **Filter Expression**, enter SQL expression that you'll use to create the filtered index.</span></span>  
  
10. <span data-ttu-id="e517b-175">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e517b-175">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e517b-176">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e517b-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="e517b-177">Para criar um índice filtrado</span><span class="sxs-lookup"><span data-stu-id="e517b-177">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="e517b-178">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e517b-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e517b-179">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e517b-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e517b-180">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e517b-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Looks for an existing filtered index named "FIBillOfMaterialsWithEndDate"  
    -- and deletes it from the table Production.BillOfMaterials if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
        WHERE name = N'FIBillOfMaterialsWithEndDate'  
        AND object_id = OBJECT_ID (N'Production.BillOfMaterials'))  
    DROP INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials  
    GO  
    -- Creates a filtered index "FIBillOfMaterialsWithEndDate"  
    -- on the table Production.BillOfMaterials   
    -- using the columms ComponentID and StartDate.  
  
    CREATE NONCLUSTERED INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials (ComponentID, StartDate)  
        WHERE EndDate IS NOT NULL ;  
    GO  
    ```  
  
     <span data-ttu-id="e517b-181">O índice filtrado acima é válido para a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="e517b-181">The filtered index above is valid for the following query.</span></span> <span data-ttu-id="e517b-182">Você pode exibir o plano de execução da consulta para determinar se o otimizador de consulta usou o índice filtrado.</span><span class="sxs-lookup"><span data-stu-id="e517b-182">You can display the query execution plan to determine if the query optimizer used the filtered index.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ProductAssemblyID, ComponentID, StartDate   
    FROM Production.BillOfMaterials  
    WHERE EndDate IS NOT NULL   
        AND ComponentID = 5   
        AND StartDate > '01/01/2008' ;  
    GO  
    ```  
  
#### <a name="to-ensure-that-a-filtered-index-is-used-in-a-sql-query"></a><span data-ttu-id="e517b-183">Para garantir que um índice filtrado seja usado em uma consulta SQL</span><span class="sxs-lookup"><span data-stu-id="e517b-183">To ensure that a filtered index is used in a SQL query</span></span>  
  
1.  <span data-ttu-id="e517b-184">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e517b-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e517b-185">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e517b-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e517b-186">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e517b-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ComponentID, StartDate FROM Production.BillOfMaterials  
        WITH ( INDEX ( FIBillOfMaterialsWithEndDate ) )   
    WHERE EndDate IN ('20000825', '20000908', '20000918');   
    GO  
    ```  
  
 <span data-ttu-id="e517b-187">Para obter mais informações, veja [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e517b-187">For more information, see  [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
