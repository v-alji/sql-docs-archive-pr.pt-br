---
title: Criar consultas Criar Tabela (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- table creation [SQL Server], Make Table query
- inserting tables
- Make Table query
- adding tables
ms.assetid: 4493cffa-7b2d-4c24-8ef0-d49329198972
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91c4a3bf45935053789d6e884b1af5b338b4c7c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680258"
---
# <a name="create-make-table-queries-visual-database-tools"></a><span data-ttu-id="b5c59-102">Criar consultas Criar Tabela (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b5c59-102">Create Make Table Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="b5c59-103">Você pode copiar linhas em uma tabela nova utilizando uma consulta Criar Tabela, que é útil para criar subconjuntos de dados para trabalhar ou copiar o conteúdo de uma tabela de um banco de dados para outro.</span><span class="sxs-lookup"><span data-stu-id="b5c59-103">You can copy rows into a new table using a Make Table query, which is useful for creating subsets of data to work with or copying the contents of a table from one database to another.</span></span> <span data-ttu-id="b5c59-104">Uma consulta Criar Tabela é semelhante a uma consulta Inserir Resultados, porém cria uma nova tabela para copiar as linhas.</span><span class="sxs-lookup"><span data-stu-id="b5c59-104">A Make Table query is similar to an Insert Results query but creates a new table to copy rows into.</span></span>  
  
 <span data-ttu-id="b5c59-105">Ao criar uma consulta Criar Tabela, você especifica:</span><span class="sxs-lookup"><span data-stu-id="b5c59-105">When you create a Make Table query, you specify:</span></span>  
  
-   <span data-ttu-id="b5c59-106">O nome da nova tabela de banco de dados (a tabela de destino).</span><span class="sxs-lookup"><span data-stu-id="b5c59-106">The name of the new database table (the destination table).</span></span>  
  
-   <span data-ttu-id="b5c59-107">A tabela ou as tabelas de banco de dados de onde copiar as linhas (a tabela de origem).</span><span class="sxs-lookup"><span data-stu-id="b5c59-107">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="b5c59-108">Você pode copiar de uma única tabela ou de tabelas unidas.</span><span class="sxs-lookup"><span data-stu-id="b5c59-108">You can copy from a single table or from joined tables.</span></span>  
  
-   <span data-ttu-id="b5c59-109">As colunas da tabela de origem cujo conteúdo você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="b5c59-109">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="b5c59-110">A ordem de classificação, se você desejar copiar as linhas em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="b5c59-110">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="b5c59-111">Os critérios de pesquisa para definir as linhas que você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="b5c59-111">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="b5c59-112">As opções Agrupar por, se você quiser copiar somente resumos informativos.</span><span class="sxs-lookup"><span data-stu-id="b5c59-112">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="b5c59-113">Por exemplo, a consulta a seguir cria uma nova tabela chamada `uk`_`customers` e copia informações da tabela `customers` :</span><span class="sxs-lookup"><span data-stu-id="b5c59-113">For example, the following query creates a new table called `uk`_`customers` and copies information from the `customers` table to it:</span></span>  
  
```  
SELECT *   
INTO uk_customers  
FROM customers  
WHERE country = 'UK'  
```  
  
 <span data-ttu-id="b5c59-114">Para usar uma consulta Criar Tabela com êxito:</span><span class="sxs-lookup"><span data-stu-id="b5c59-114">In order to use a Make Table query successfully:</span></span>  
  
-   <span data-ttu-id="b5c59-115">Seu banco de dados deve oferecer suporte à sintaxe SELECT...INTO.</span><span class="sxs-lookup"><span data-stu-id="b5c59-115">Your database must support the SELECT...INTO syntax.</span></span>  
  
-   <span data-ttu-id="b5c59-116">Você deve ter permissão para criar uma tabela no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="b5c59-116">You must have permission to create a table in the target database.</span></span>  
  
### <a name="to-create-a-make-table-query"></a><span data-ttu-id="b5c59-117">Para criar uma consulta Criar Tabela</span><span class="sxs-lookup"><span data-stu-id="b5c59-117">To create a Make Table query</span></span>  
  
1.  <span data-ttu-id="b5c59-118">Adicione a tabela ou as tabelas de origem ao painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="b5c59-118">Add the source table or tables to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="b5c59-119">No menu **Designer de Consultas** , aponte para **Alterar Tipo**e clique em **Criar Tabela**.</span><span class="sxs-lookup"><span data-stu-id="b5c59-119">From the **Query Designer** menu, point to **Change Type**, and then click **Make Table**.</span></span>  
  
3.  <span data-ttu-id="b5c59-120">Na caixa de diálogo **Criar Tabela** , digite o nome da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="b5c59-120">In the **Make Table** dialog box, type the name of the destination table.</span></span> <span data-ttu-id="b5c59-121">O Designer de Consulta e Exibição não verifica se o nome já está em uso ou se você tem permissão para criar a tabela.</span><span class="sxs-lookup"><span data-stu-id="b5c59-121">The Query and View Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
     <span data-ttu-id="b5c59-122">Para criar uma tabela de destino em outro banco de dados, especifique um nome de tabela totalmente qualificado incluindo o nome do banco de dados de destino, o proprietário (se necessário) e o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="b5c59-122">To create a destination table in another database, specify a fully qualified table name including the name of the target database, the owner (if required), and the name of the table.</span></span>  
  
4.  <span data-ttu-id="b5c59-123">Especifique as colunas a serem copiadas adicionando-as à consulta.</span><span class="sxs-lookup"><span data-stu-id="b5c59-123">Specify the columns to copy by adding them to the query.</span></span> <span data-ttu-id="b5c59-124">Para obter detalhes, veja [Adicionar colunas a consultas &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5c59-124">For details, see [Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="b5c59-125">As colunas só serão copiadas se você as adicionar à consulta.</span><span class="sxs-lookup"><span data-stu-id="b5c59-125">Columns will be copied only if you add them to the query.</span></span> <span data-ttu-id="b5c59-126">Para copiar linhas inteiras, escolha \*\* \* (todas as colunas)\*\*.</span><span class="sxs-lookup"><span data-stu-id="b5c59-126">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="b5c59-127">O Designer de Consulta e Exibição adiciona as colunas escolhidas à coluna **Coluna** do painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="b5c59-127">The Query and View Designer adds the columns you choose to the **Column** column of the Criteria pane.</span></span>  
  
5.  <span data-ttu-id="b5c59-128">Se você quiser copiar as linhas em uma ordem específica, selecione a ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="b5c59-128">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="b5c59-129">Para obter detalhes, consulte **Classificação e agrupamento de resultados de consultas**.</span><span class="sxs-lookup"><span data-stu-id="b5c59-129">For details, see **Sorting and Grouping Query Results**.</span></span>  
  
6.  <span data-ttu-id="b5c59-130">Especifique as linhas a serem copiadas inserindo critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b5c59-130">Specify the rows to copy by entering search conditions.</span></span> <span data-ttu-id="b5c59-131">Para obter detalhes, consulte [Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5c59-131">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="b5c59-132">Se você não especificar um critério de pesquisa, todas as linhas da tabela de origem serão copiadas na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="b5c59-132">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5c59-133">Quando você insere uma coluna para ser pesquisada no painel Critérios, o Designer de Consulta e Exibição também a adiciona à lista de colunas a serem copiadas.</span><span class="sxs-lookup"><span data-stu-id="b5c59-133">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="b5c59-134">Se você quiser utilizar uma coluna para fazer uma pesquisa, mas não quiser copiá-la, desmarque a caixa de seleção próxima ao nome da coluna no retângulo que representa a tabela ou o objeto estruturado por tabela.</span><span class="sxs-lookup"><span data-stu-id="b5c59-134">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-structured object.</span></span>  
  
7.  <span data-ttu-id="b5c59-135">Para copiar resumos informativos, especifique as opções Agrupar por.</span><span class="sxs-lookup"><span data-stu-id="b5c59-135">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="b5c59-136">Para obter detalhes, consulte [Resumir resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5c59-136">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="b5c59-137">Quando você executa a consulta Criar Tabela, nenhum resultado é relatado no painel de [Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5c59-137">When you execute a Make Table query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="b5c59-138">Em vez disso, será exibida uma mensagem indicando o total de linhas copiadas.</span><span class="sxs-lookup"><span data-stu-id="b5c59-138">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c59-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5c59-139">See Also</span></span>  
 <span data-ttu-id="b5c59-140">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b5c59-140">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b5c59-141">Tipos de consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b5c59-141">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
