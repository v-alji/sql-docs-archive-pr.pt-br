---
title: Criar consultas Inserir Resultados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- result sets [SQL Server], queries
- results [SQL Server], query
- Insert Results query
- queries [SQL Server], results
ms.assetid: 8770d630-09cc-47ec-a0e9-e9de2d7bbc89
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02643c2cf3295debe740a696941f8730d4417254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680259"
---
# <a name="create-insert-results-queries-visual-database-tools"></a><span data-ttu-id="3c49f-102">Criar consultas Inserir Resultados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3c49f-102">Create Insert Results Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="3c49f-103">Você pode copiar linhas de uma tabela para outra ou em uma tabela utilizando uma consulta Inserir Resultados.</span><span class="sxs-lookup"><span data-stu-id="3c49f-103">You can copy rows from one table to another or within a table using an Insert Results query.</span></span> <span data-ttu-id="3c49f-104">Por exemplo, em uma tabela `titles` , é possível utilizar uma consulta Inserir Resultados para copiar informações sobre todos os títulos de um publicador para uma segunda tabela que você pode disponibilizar para esse publicador.</span><span class="sxs-lookup"><span data-stu-id="3c49f-104">For example, in a `titles` table, you can use an Insert Results query to copy information about all the titles for one publisher to a second table that you can make available to that publisher.</span></span> <span data-ttu-id="3c49f-105">Uma consulta Inserir Resultados é semelhante às Consultas de Criar Tabela, mas copia linhas para uma tabela existente.</span><span class="sxs-lookup"><span data-stu-id="3c49f-105">An Insert Results query is similar to Make Table Queries, but copies rows into an existing table.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="3c49f-106">Você também pode copiar linhas de uma tabela para outra utilizando recortar e colar.</span><span class="sxs-lookup"><span data-stu-id="3c49f-106">You can also copy rows from one table to another using cut and paste.</span></span> <span data-ttu-id="3c49f-107">Crie uma consulta para cada tabela e execute as consultas.</span><span class="sxs-lookup"><span data-stu-id="3c49f-107">Create a query for each table and run the queries.</span></span> <span data-ttu-id="3c49f-108">Copie as linhas que você deseja de uma grade de resultados para outra.</span><span class="sxs-lookup"><span data-stu-id="3c49f-108">Copy the rows you want from one results grid to the other.</span></span>  
  
 <span data-ttu-id="3c49f-109">Ao criar uma consulta Inserir Resultados, você especifica:</span><span class="sxs-lookup"><span data-stu-id="3c49f-109">When you create an Insert Results query, you specify:</span></span>  
  
-   <span data-ttu-id="3c49f-110">A tabela de banco de dados para a qual copiar linhas (a tabela de destino).</span><span class="sxs-lookup"><span data-stu-id="3c49f-110">The database table to copy rows to (the destination table).</span></span>  
  
-   <span data-ttu-id="3c49f-111">A tabela ou as tabelas de banco de dados de onde copiar as linhas (a tabela de origem).</span><span class="sxs-lookup"><span data-stu-id="3c49f-111">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="3c49f-112">A tabela ou as tabelas de origem se tornam parte de uma subconsulta.</span><span class="sxs-lookup"><span data-stu-id="3c49f-112">The source table or tables become part of a subquery.</span></span> <span data-ttu-id="3c49f-113">Se você estiver copiando em uma tabela, a tabela de origem será a mesma que a tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="3c49f-113">If you are copying within a table, the source table is the same as the destination table.</span></span>  
  
-   <span data-ttu-id="3c49f-114">As colunas da tabela de origem cujo conteúdo você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="3c49f-114">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="3c49f-115">As colunas de destino na tabela de destino para onde copiar os dados.</span><span class="sxs-lookup"><span data-stu-id="3c49f-115">The target columns in the destination table to copy the data to.</span></span>  
  
-   <span data-ttu-id="3c49f-116">Os critérios de pesquisa para definir as linhas que você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="3c49f-116">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="3c49f-117">A ordem de classificação, se você desejar copiar as linhas em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="3c49f-117">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="3c49f-118">As opções Agrupar por, se você quiser copiar somente resumos informativos.</span><span class="sxs-lookup"><span data-stu-id="3c49f-118">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="3c49f-119">Por exemplo, a consulta a seguir copia informações de título da tabela `titles` para uma tabela de arquivo morto chamada `archivetitles`.</span><span class="sxs-lookup"><span data-stu-id="3c49f-119">For example, the following query copies title information from the `titles` table to an archive table called `archivetitles`.</span></span> <span data-ttu-id="3c49f-120">A consulta copia o conteúdo de quatro colunas para todos os títulos que pertencem a um publicador específico:</span><span class="sxs-lookup"><span data-stu-id="3c49f-120">The query copies the contents of four columns for all titles belonging to a particular publisher:</span></span>  
  
```  
INSERT INTO archivetitles   
   (title_id, title, type, pub_id)  
SELECT title_id, title, type, pub_id  
FROM titles  
WHERE (pub_id = '0766')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3c49f-121">Para inserir valores em uma linha nova, utilize uma consulta Insert Values.</span><span class="sxs-lookup"><span data-stu-id="3c49f-121">To insert values into a new row, use an Insert Values query.</span></span>  
  
 <span data-ttu-id="3c49f-122">Você pode copiar o conteúdo das colunas selecionadas ou de todas as colunas em uma linha.</span><span class="sxs-lookup"><span data-stu-id="3c49f-122">You can copy the contents of selected columns or of all columns in a row.</span></span> <span data-ttu-id="3c49f-123">Em ambos os casos, os dados que estão sendo copiados devem ser compatíveis com as colunas nas linhas para as quais você está copiando.</span><span class="sxs-lookup"><span data-stu-id="3c49f-123">In either case, the data you are copying must be compatible with the columns in the rows you are copying to.</span></span> <span data-ttu-id="3c49f-124">Por exemplo, se você copiar o conteúdo de uma coluna como `price`, a coluna da linha que você estiver copiando deverá aceitar dados numéricos com casas decimais.</span><span class="sxs-lookup"><span data-stu-id="3c49f-124">For example, if you copy the contents of a column such as `price`, the column in the row you are copying to must accept numeric data with decimal places.</span></span> <span data-ttu-id="3c49f-125">Se você estiver copiando uma linha inteira, a tabela de destino deverá ter colunas compatíveis na mesma posição física da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="3c49f-125">If you are copying an entire row, the destination table must have compatible columns in the same physical position as the source table.</span></span>  
  
 <span data-ttu-id="3c49f-126">Quando você cria uma consulta Inserir Resultados, o painel Critérios é alterado para refletir as opções disponíveis para cópia de dados.</span><span class="sxs-lookup"><span data-stu-id="3c49f-126">When you create an Insert Results query, the Criteria pane changes to reflect options available for copying data.</span></span> <span data-ttu-id="3c49f-127">Uma coluna Anexar é adicionada para permitir que você especifique as colunas nas quais os dados devem ser copiados.</span><span class="sxs-lookup"><span data-stu-id="3c49f-127">An Append column is added to allow you to specify the columns into which data should be copied.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="3c49f-128">Você não pode desfazer a ação de executar uma consulta Inserir Resultados.</span><span class="sxs-lookup"><span data-stu-id="3c49f-128">You cannot undo the action of executing an Insert Results query.</span></span> <span data-ttu-id="3c49f-129">Como precaução, faça backup de seus dados antes de executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="3c49f-129">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-results-query"></a><span data-ttu-id="3c49f-130">Para criar uma consulta Inserir Resultados</span><span class="sxs-lookup"><span data-stu-id="3c49f-130">To create an Insert Results query</span></span>  
  
1.  <span data-ttu-id="3c49f-131">Crie uma nova consulta e adicione a tabela da qual você quer copiar linhas (a tabela de origem).</span><span class="sxs-lookup"><span data-stu-id="3c49f-131">Create a new query and add the table from which you want to copy rows (the source table).</span></span> <span data-ttu-id="3c49f-132">Se você estiver copiando linhas em uma tabela, poderá adicionar a tabela de origem como tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="3c49f-132">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
2.  <span data-ttu-id="3c49f-133">No menu **Designer de Consulta** , aponte para **Alterar Tipo**e clique em **Inserir Resultados**.</span><span class="sxs-lookup"><span data-stu-id="3c49f-133">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
3.  <span data-ttu-id="3c49f-134">Na caixa de diálogo [Escolher Tabela de Destino para Inserir Resultados](visual-database-tools.md), selecione a tabela para copiar linhas (tabela de destino).</span><span class="sxs-lookup"><span data-stu-id="3c49f-134">In the [Choose Target Table for Insert Results Dialog Box](visual-database-tools.md), select the table to copy rows to (the destination table).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3c49f-135">O Designer de Consulta e Exibição não pode determinar antecipadamente quais tabelas e exibições podem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="3c49f-135">The Query and View Designer cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="3c49f-136">Portanto, a lista **Nome de Tabela** na caixa de diálogo **Escolher Tabela para Inserir a Partir da Consulta** mostra todas as tabelas e exibições disponíveis na conexão de dados que você estiver consultando, mesmo aquelas para as quais não é possível copiar linhas.</span><span class="sxs-lookup"><span data-stu-id="3c49f-136">Therefore, the **Table Name** list in the **Choose Table for Insert From Query** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
4.  <span data-ttu-id="3c49f-137">No retângulo que representa a tabela ou o objeto com valor de tabela, escolha os nomes das colunas cujo conteúdo você quer copiar.</span><span class="sxs-lookup"><span data-stu-id="3c49f-137">In the rectangle representing the table or table-valued object, choose the names of the columns whose contents you want to copy.</span></span> <span data-ttu-id="3c49f-138">Para copiar linhas inteiras, escolha \*\* \* (todas as colunas)\*\*.</span><span class="sxs-lookup"><span data-stu-id="3c49f-138">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="3c49f-139">O Designer de Consulta e Exibição adiciona as colunas escolhidas à coluna **Coluna** do painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="3c49f-139">The Query and View Designer adds the columns you choose to the **Column** column of the Criteriapane.</span></span>  
  
5.  <span data-ttu-id="3c49f-140">Na coluna **Acrescentar** do painel Critérios, selecione uma coluna de destino na tabela de destino para cada coluna que você está copiando.</span><span class="sxs-lookup"><span data-stu-id="3c49f-140">In the **Append** column of the Criteria pane, select a target column in the destination table for each column you are copying.</span></span> <span data-ttu-id="3c49f-141">Escolha \*TableName. \* \* se você estiver copiando linhas inteiras.</span><span class="sxs-lookup"><span data-stu-id="3c49f-141">Choose *tablename.\** if you are copying entire rows.</span></span> <span data-ttu-id="3c49f-142">As colunas na tabela de destino devem ter os mesmos tipos de dados (ou compatíveis) que as colunas na tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="3c49f-142">The columns in the destination table must have the same (or compatible) data types as the columns in the source table.</span></span>  
  
6.  <span data-ttu-id="3c49f-143">Se você quiser copiar as linhas em uma ordem específica, selecione a ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="3c49f-143">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="3c49f-144">Para obter detalhes, consulte [Classificar e agrupar resultados da consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c49f-144">For details, see [Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span></span>  
  
7.  <span data-ttu-id="3c49f-145">Especifique as linhas a serem copiadas inserindo critérios de pesquisa na coluna **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="3c49f-145">Specify the rows to copy by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="3c49f-146">Para obter detalhes, consulte [Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c49f-146">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="3c49f-147">Se você não especificar um critério de pesquisa, todas as linhas da tabela de origem serão copiadas na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="3c49f-147">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3c49f-148">Quando você insere uma coluna para ser pesquisada no painel Critérios, o Designer de Consulta e Exibição também a adiciona à lista de colunas a serem copiadas.</span><span class="sxs-lookup"><span data-stu-id="3c49f-148">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="3c49f-149">Se você quiser utilizar uma coluna para pesquisar mas não quiser copiá-la, desmarque a caixa de seleção próxima ao nome da coluna no retângulo que representa a tabela ou objeto com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="3c49f-149">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
8.  <span data-ttu-id="3c49f-150">Para copiar resumos informativos, especifique as opções Agrupar por.</span><span class="sxs-lookup"><span data-stu-id="3c49f-150">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="3c49f-151">Para obter detalhes, consulte [Resumir resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c49f-151">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="3c49f-152">Quando você executa uma consulta Inserir Resultados, nenhum resultado é relatado no [Painel de Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c49f-152">When you execute an Insert Results query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="3c49f-153">Em vez disso, será exibida uma mensagem indicando o total de linhas copiadas.</span><span class="sxs-lookup"><span data-stu-id="3c49f-153">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c49f-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3c49f-154">See Also</span></span>  
 <span data-ttu-id="3c49f-155">[Tipos de consultas &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3c49f-155">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3c49f-156">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3c49f-156">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
