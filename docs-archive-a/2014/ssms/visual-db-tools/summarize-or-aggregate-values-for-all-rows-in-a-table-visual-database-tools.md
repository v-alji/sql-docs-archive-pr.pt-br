---
title: Resumir ou agregar valores para todas as linhas em uma tabela (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- aggregate functions [SQL Server], summarizing query results
ms.assetid: f5af876e-f937-4110-ba09-07999c35a699
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5c4d80c8ab2b811b8e796f0a37b2180a2866c332
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683279"
---
# <a name="summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="54ad7-102">Resumir ou agregar valores para todas as linhas em uma tabela (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="54ad7-102">Summarize or Aggregate Values for All Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="54ad7-103">Usando uma função de agregação, você pode criar um resumo para obter todos os valores em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="54ad7-103">Using an aggregate function, you can create a summary for all the values in a table.</span></span> <span data-ttu-id="54ad7-104">Por exemplo, é possível criar uma consulta, como a seguinte, para exibir o preço total de todos os livros da tabela `titles` :</span><span class="sxs-lookup"><span data-stu-id="54ad7-104">For example, you can create a query such as the following to display the total price for all books in the `titles` table:</span></span>  
  
```  
SELECT SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="54ad7-105">Você pode criar várias agregações na mesma consulta usando funções de agregação com mais de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="54ad7-105">You can create multiple aggregations in the same query by using aggregate functions with more than one column.</span></span> <span data-ttu-id="54ad7-106">Por exemplo, é possível criar uma consulta que calcule o total da coluna `price` e a média da coluna `discount` .</span><span class="sxs-lookup"><span data-stu-id="54ad7-106">For example, you can create a query that calculates the total of the `price` column and the average of the `discount` column.</span></span>  
  
 <span data-ttu-id="54ad7-107">Você também pode agregar a mesma coluna de modos diferentes (como totalizar, contar e calcular a média) na mesma consulta.</span><span class="sxs-lookup"><span data-stu-id="54ad7-107">You can also aggregate the same column in different ways (such as totaling, counting, and averaging) in the same query.</span></span> <span data-ttu-id="54ad7-108">Por exemplo, a consulta seguinte calcula a média e resume a coluna `price` da tabela `titles` :</span><span class="sxs-lookup"><span data-stu-id="54ad7-108">For example, the following query averages and summarizes the `price` column from the `titles` table:</span></span>  
  
```  
SELECT AVG(price), SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="54ad7-109">Se você adicionar um critério de pesquisa, será possível agregar o subconjunto de linhas que atendam àquela condição.</span><span class="sxs-lookup"><span data-stu-id="54ad7-109">If you add a search condition, you can aggregate the subset of rows that meet that condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54ad7-110">Você também pode contar todas as linhas na tabela ou aquelas que atendam uma condição específica.</span><span class="sxs-lookup"><span data-stu-id="54ad7-110">You can also count all the rows in the table or the ones that meet a specific condition.</span></span> <span data-ttu-id="54ad7-111">Para obter detalhes, veja [Como contar linhas em uma tabela &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54ad7-111">For details, see [Count Rows in a Table &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="54ad7-112">Quando você cria um valor de agregação único para todas as linhas em uma tabela, somente os valores de agregação são exibidos.</span><span class="sxs-lookup"><span data-stu-id="54ad7-112">When you create a single aggregation value for all rows in a table, you display only the aggregate values themselves.</span></span> <span data-ttu-id="54ad7-113">Por exemplo, se você estivesse totalizando o valor da coluna `price` da tabela `titles` , você também não exibiria títulos individuais, nomes de publicador, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="54ad7-113">For example, if you are totaling the value of the `price` column of the `titles` table, you would not also display individual titles, publisher names, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54ad7-114">Se estiver subtotalizando (ou seja, criando grupos), você poderá exibir valores de coluna para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="54ad7-114">If you are subtotaling - that is, creating groups - you can display column values for each group.</span></span> <span data-ttu-id="54ad7-115">Para obter detalhes, veja [Agrupar linhas em resultados da consulta &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54ad7-115">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
### <a name="to-aggregate-values-for-all-rows"></a><span data-ttu-id="54ad7-116">Para agregar valores para todas as linhas</span><span class="sxs-lookup"><span data-stu-id="54ad7-116">To aggregate values for all rows</span></span>  
  
1.  <span data-ttu-id="54ad7-117">Verifique se a tabela que você quer agregar já está presente no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="54ad7-117">Be sure the table you want to aggregate is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="54ad7-118">Clique com o botão direito do mouse na tela de fundo do painel Diagrama e escolha **Agrupar por** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="54ad7-118">Right-click the background of the Diagram pane, then choose **Group By** from the shortcut menu.</span></span> <span data-ttu-id="54ad7-119">O [Designer de consulta e exibição](query-and-view-designer-tools-visual-database-tools.md) adiciona uma coluna **Agrupar por** à grade no painel critérios.</span><span class="sxs-lookup"><span data-stu-id="54ad7-119">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="54ad7-120">Some a coluna que você quer agregar ao painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="54ad7-120">Add the column you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="54ad7-121">Verifique se a coluna esteja marcada para saída.</span><span class="sxs-lookup"><span data-stu-id="54ad7-121">Be sure that the column is marked for output.</span></span>  
  
     <span data-ttu-id="54ad7-122">O Designer de Consulta e Exibição atribui automaticamente um alias de coluna à coluna que você está resumindo.</span><span class="sxs-lookup"><span data-stu-id="54ad7-122">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="54ad7-123">Você pode substituir este alias por um mais significativo.</span><span class="sxs-lookup"><span data-stu-id="54ad7-123">You can replace this alias with a more meaningful one.</span></span> <span data-ttu-id="54ad7-124">Para obter detalhes, veja [Criar aliases de coluna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54ad7-124">For details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="54ad7-125">Na coluna de grade **Agrupar por**, selecione a função de agregação apropriada, como: **Soma**, **Média**, **Mín**, **Máx** e **Contar**.</span><span class="sxs-lookup"><span data-stu-id="54ad7-125">In the **Group By** grid column, select the appropriate aggregate function, such as: **Sum**, **Avg**, **Min**, **Max**, **Count**.</span></span> <span data-ttu-id="54ad7-126">Se você quiser agregar somente linhas exclusivas no conjunto de resultados, escolha uma função de agregação com as opções DISTINCT, como **Min Distinct**.</span><span class="sxs-lookup"><span data-stu-id="54ad7-126">If you want to aggregate only unique rows in the result set, choose an aggregate function with the DISTINCT options, such as **Min Distinct**.</span></span> <span data-ttu-id="54ad7-127">Não escolha **Agrupar por**, **Expressão**nem **Onde**, porque essas opções não se aplicam quando você agrega todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="54ad7-127">Do not choose **Group By**, **Expression**, or **Where**, because those options do not apply when you are aggregating all rows.</span></span>  
  
     <span data-ttu-id="54ad7-128">O Designer de Consulta e Exibição substitui o nome de coluna da instrução no [Painel SQL](sql-pane-visual-database-tools.md) com a função de agregação que você especificar.</span><span class="sxs-lookup"><span data-stu-id="54ad7-128">The Query and View Designer replaces the column name in the statement in the [SQL pane](sql-pane-visual-database-tools.md) with the aggregate function that you specify.</span></span> <span data-ttu-id="54ad7-129">Por exemplo, a instrução SQL poderia se parecer com:</span><span class="sxs-lookup"><span data-stu-id="54ad7-129">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT SUM(price)  
    FROM titles  
    ```  
  
5.  <span data-ttu-id="54ad7-130">Se você quiser criar mais de uma agregação na consulta, repita os passos 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="54ad7-130">If you want to create more than one aggregation in the query, repeat steps 3 and 4.</span></span>  
  
     <span data-ttu-id="54ad7-131">Quando você adiciona outra coluna à lista de saída da consulta ou faz a classificação por lista, o Designer de Consulta e Exibição preenche automaticamente o termo **Agrupar por** na coluna **Agrupar por** da grade.</span><span class="sxs-lookup"><span data-stu-id="54ad7-131">When you add another column to the query output list or order by list, the Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span> <span data-ttu-id="54ad7-132">Selecione a função de agregação apropriada.</span><span class="sxs-lookup"><span data-stu-id="54ad7-132">Select the appropriate aggregate function.</span></span>  
  
6.  <span data-ttu-id="54ad7-133">Adicione critérios de pesquisa, se existir, para especificar o subconjunto de linhas que deseja resumir.</span><span class="sxs-lookup"><span data-stu-id="54ad7-133">Add search conditions, if any, to specify the subset of rows you want to summarize.</span></span>  
  
 <span data-ttu-id="54ad7-134">Quando você executar a consulta, o painel Resultados exibirá as agregações por você especificadas.</span><span class="sxs-lookup"><span data-stu-id="54ad7-134">When you execute the query, the Results pane displays the aggregations that you specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54ad7-135">O Designer de Consulta e Exibição mantém funções de agregação como parte da instrução SQL no painel SQL até que você desative o modo Agrupar por.</span><span class="sxs-lookup"><span data-stu-id="54ad7-135">The Query and View Designer maintains aggregate functions as part of the SQL statement in the SQL pane until you explicitly turn off Group By mode.</span></span> <span data-ttu-id="54ad7-136">Portanto, se você modificar sua consulta alterando o tipo, as tabelas ou os objetos com valor de tabela presentes no painel Diagrama, a consulta resultante poderá incluir funções de agregação inválidas.</span><span class="sxs-lookup"><span data-stu-id="54ad7-136">Therefore, if you modify your query by changing its type or by changing which tables or table-valued objects are present in the Diagram pane, the resulting query might include invalid aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ad7-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54ad7-137">See Also</span></span>  
 <span data-ttu-id="54ad7-138">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="54ad7-138">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="54ad7-139">Resumir resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="54ad7-139">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
