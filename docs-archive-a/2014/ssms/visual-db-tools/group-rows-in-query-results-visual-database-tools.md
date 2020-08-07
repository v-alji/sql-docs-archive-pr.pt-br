---
title: Agrupar linhas em resultados da consulta (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing table subsets
- grouping rows
- grouping query results
ms.assetid: b07082d5-4d55-4903-9af9-4c470554c6d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52de25c86425d95f5917d89c8a3f4fec8939fb16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574985"
---
# <a name="group-rows-in-query-results-visual-database-tools"></a><span data-ttu-id="817ed-102">Agrupar linhas em resultados da consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="817ed-102">Group Rows in Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="817ed-103">Para criar subtotais ou para mostrar outro resumo informativo de subconjuntos de uma tabela, crie grupos usando uma consulta de agregação.</span><span class="sxs-lookup"><span data-stu-id="817ed-103">If you want to create subtotals or show other summary information for subsets of a table, you create groups using an aggregate query.</span></span> <span data-ttu-id="817ed-104">Cada grupo resume os dados de todas as linhas da tabela que possuem o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="817ed-104">Each group summarizes the data for all the rows in the table that have the same value.</span></span>  
  
 <span data-ttu-id="817ed-105">Por exemplo, pode ser necessário exibir o preço médio de um livro na tabela `titles` , mas classifique os resultados por editora.</span><span class="sxs-lookup"><span data-stu-id="817ed-105">For example, you might want to see the average price of a book in the `titles` table, but break the results down by publisher.</span></span> <span data-ttu-id="817ed-106">Para isso, agrupe a consulta por publicador (por exemplo, `pub_id`).</span><span class="sxs-lookup"><span data-stu-id="817ed-106">To do so, you group the query by publisher (for example, `pub_id`).</span></span> <span data-ttu-id="817ed-107">A saída da consulta resultante poderá ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="817ed-107">The resulting query output might look like this:</span></span>  
  
 <span data-ttu-id="817ed-108">![Resultados de consulta: preço médio agrupado por publicador](../../database-engine/media//dv3w9e1.gif "Resultados de consulta: preço médio agrupado por publicador")</span><span class="sxs-lookup"><span data-stu-id="817ed-108">![Query results: average price grouped by publisher](../../database-engine/media//dv3w9e1.gif "Query results: average price grouped by publisher")</span></span>  
  
 <span data-ttu-id="817ed-109">Quando se agrupam dados, só é possível exibir dados resumidos ou agrupados, como:</span><span class="sxs-lookup"><span data-stu-id="817ed-109">When you group data, you can display only summary or grouped data, such as:</span></span>  
  
-   <span data-ttu-id="817ed-110">Os valores das colunas agrupadas (os que aparecem na cláusula GROUP BY).</span><span class="sxs-lookup"><span data-stu-id="817ed-110">The values of the grouped columns (those that appear in the GROUP BY clause).</span></span> <span data-ttu-id="817ed-111">No exemplo acima, `pub_id` é a coluna agrupada.</span><span class="sxs-lookup"><span data-stu-id="817ed-111">In the example above, `pub_id` is the grouped column.</span></span>  
  
-   <span data-ttu-id="817ed-112">Os valores produzidos por funções de agregação, como SUM( ) e AVG( ).</span><span class="sxs-lookup"><span data-stu-id="817ed-112">Values produced by aggregate functions such as SUM( ) and AVG( ).</span></span> <span data-ttu-id="817ed-113">No exemplo anterior, a segunda coluna é produzida usando a função AVG( ) com a coluna `price` .</span><span class="sxs-lookup"><span data-stu-id="817ed-113">In the example above, the second column is produced by using the AVG( ) function with the `price` column.</span></span>  
  
 <span data-ttu-id="817ed-114">Você não pode exibir valores de linhas individuais.</span><span class="sxs-lookup"><span data-stu-id="817ed-114">You cannot display values from individual rows.</span></span> <span data-ttu-id="817ed-115">Por exemplo, se o agrupamento for feito somente por publicador, não será possível exibir igualmente os títulos individuais da consulta.</span><span class="sxs-lookup"><span data-stu-id="817ed-115">For example, if you group only by publisher, you cannot also display individual titles in the query.</span></span> <span data-ttu-id="817ed-116">Portanto, se colunas forem adicionadas à saída da consulta, o [Designer de Consulta e Exibição](visual-database-tools.md) adicionará automaticamente essas colunas à cláusula GROUP BY da instrução no [Painel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="817ed-116">Therefore, if you add columns to the query output, the [Query and View Designer](visual-database-tools.md) automatically adds them to the GROUP BY clause of the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="817ed-117">Em vez disso, para agregar uma coluna, especifique uma função de agregação para aquela coluna.</span><span class="sxs-lookup"><span data-stu-id="817ed-117">If you want a column to be aggregated instead, you can specify an aggregate function for that column.</span></span>  
  
 <span data-ttu-id="817ed-118">Se o agrupamento for feito por mais de uma coluna, cada grupo da consulta mostrará os valores de agregação de todas as colunas de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="817ed-118">If you group by more than one column, each group in the query shows the aggregate values for all grouping columns.</span></span>  
  
 <span data-ttu-id="817ed-119">Por exemplo, a consulta a seguir, realizada nos grupos de tabela `titles` por publicador (`pub_id`) e também pelo tipo de livro (`type`).</span><span class="sxs-lookup"><span data-stu-id="817ed-119">For example, the following query against the `titles` table groups by publisher (`pub_id`) and also by book type (`type`).</span></span> <span data-ttu-id="817ed-120">Os resultados de consulta são ordenados por publicador e mostram informações resumidas sobre todos os diferentes tipos de livros que o publicador produz:</span><span class="sxs-lookup"><span data-stu-id="817ed-120">The query results are ordered by publisher and show summary information for each different type of book that the publisher produces:</span></span>  
  
```  
SELECT pub_id, type, SUM(price) Total_price  
FROM titles  
GROUP BY pub_id, type  
```  
  
 <span data-ttu-id="817ed-121">A saída resultante pode ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="817ed-121">The resulting output might look like this:</span></span>  
  
 <span data-ttu-id="817ed-122">![Resultados de consulta: preço agrupado por publicador e tipo](../../database-engine/media//dv3w9e2.gif "Resultados de consulta: preço agrupado por publicador e tipo")</span><span class="sxs-lookup"><span data-stu-id="817ed-122">![Query results: price grouped by publisher and type](../../database-engine/media//dv3w9e2.gif "Query results: price grouped by publisher and type")</span></span>  
  
### <a name="to-group-rows"></a><span data-ttu-id="817ed-123">Para agrupar linhas</span><span class="sxs-lookup"><span data-stu-id="817ed-123">To group rows</span></span>  
  
1.  <span data-ttu-id="817ed-124">Inicie a consulta adicionando as tabelas a serem resumidas ao Painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="817ed-124">Start the query by adding the tables you want to summarize to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="817ed-125">Clique com o botão direito do mouse na tela de fundo do painel Diagrama e escolha **Adicionar Grupo por** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="817ed-125">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="817ed-126">O Designer de Consulta e Exibição adicionará a coluna **Agrupar por** à grade do Painel de Critérios.</span><span class="sxs-lookup"><span data-stu-id="817ed-126">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="817ed-127">Adicione a coluna ou colunas que você deseja agrupar ao Painel de Critérios.</span><span class="sxs-lookup"><span data-stu-id="817ed-127">Add the column or columns you want to group to the Criteria pane.</span></span> <span data-ttu-id="817ed-128">Para que a coluna apareça na saída da consulta, certifique-se de que a coluna **Saída** seja selecionada para saída.</span><span class="sxs-lookup"><span data-stu-id="817ed-128">If you want the column to appear in the query output, be sure that the **Output** column is selected for output.</span></span>  
  
     <span data-ttu-id="817ed-129">O Designer de Consulta e Exibição adicionará uma cláusula GROUP BY à instrução no Painel SQL.</span><span class="sxs-lookup"><span data-stu-id="817ed-129">The Query and View Designer adds a GROUP BY clause to the statement in the SQL pane.</span></span> <span data-ttu-id="817ed-130">Por exemplo, a instrução SQL poderia se parecer com:</span><span class="sxs-lookup"><span data-stu-id="817ed-130">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT pub_id  
    FROM titles  
    GROUP BY pub_id  
    ```  
  
4.  <span data-ttu-id="817ed-131">Adicione a coluna ou colunas que você deseja agregar ao Painel de Critérios.</span><span class="sxs-lookup"><span data-stu-id="817ed-131">Add the column or columns you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="817ed-132">Verifique se a coluna esteja marcada para saída.</span><span class="sxs-lookup"><span data-stu-id="817ed-132">Be sure that the column is marked for output.</span></span>  
  
5.  <span data-ttu-id="817ed-133">Na célula de grade **Agrupar por** da coluna que será agregada, selecione a função de agregação correta.</span><span class="sxs-lookup"><span data-stu-id="817ed-133">In the **Group By** grid cell for the column that is going to be aggregated, select the appropriate aggregate function.</span></span>  
  
     <span data-ttu-id="817ed-134">O Designer de Consulta e Exibição atribui automaticamente um alias de coluna à coluna que você está resumindo.</span><span class="sxs-lookup"><span data-stu-id="817ed-134">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="817ed-135">Você pode substituir esse alias gerado automaticamente por outro que tenha mais significado.</span><span class="sxs-lookup"><span data-stu-id="817ed-135">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="817ed-136">Para obter mais detalhes, veja [Criar aliases de coluna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="817ed-136">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="817ed-137">![Adicionar um alias de coluna ao conjunto de resultados de consulta](../../database-engine/media//dv3w9e3.gif "Adicionar um alias de coluna ao conjunto de resultados de consulta")</span><span class="sxs-lookup"><span data-stu-id="817ed-137">![Adding a column alias to the query result set](../../database-engine/media//dv3w9e3.gif "Adding a column alias to the query result set")</span></span>  
  
     <span data-ttu-id="817ed-138">A instrução correspondente no painel **SQL** pode ter esse formato:</span><span class="sxs-lookup"><span data-stu-id="817ed-138">The corresponding statement in the **SQL** pane might look like this:</span></span>  
  
    ```  
    SELECT   pub_id, SUM(price) AS Totalprice  
    FROM     titles  
    GROUP BY pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="817ed-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="817ed-139">See Also</span></span>  
 [<span data-ttu-id="817ed-140">Classificar e agrupar resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="817ed-140">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
