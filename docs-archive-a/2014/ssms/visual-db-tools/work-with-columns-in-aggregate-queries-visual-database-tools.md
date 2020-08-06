---
title: Trabalhar com colunas em consultas de agregação (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query summary results
- GROUP BY clause, query summary results
- aggregate queries [SQL Server]
- WHERE clause, query summary results
ms.assetid: 1b82681f-3d4f-4b9a-bb1d-2060e44f2577
author: stevestein
ms.author: sstein
ms.openlocfilehash: 880f7529cebd7f51951e62952e3b5f13190f99b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678473"
---
# <a name="work-with-columns-in-aggregate-queries-visual-database-tools"></a><span data-ttu-id="32b33-102">Trabalhar com colunas em consultas de agregação (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="32b33-102">Work with Columns in Aggregate Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="32b33-103">Quando você cria consultas de agregação, o [Designer de Consulta e Exibição](visual-database-tools.md) faz determinadas suposições para poder criar uma consulta válida.</span><span class="sxs-lookup"><span data-stu-id="32b33-103">When you create aggregate queries the [Query and View Designer](visual-database-tools.md) makes certain assumptions so that it can construct a valid query.</span></span> <span data-ttu-id="32b33-104">Por exemplo, se você estiver criando uma consulta de agregação e marcar uma coluna de dados para saída, o Designer de Consulta e Exibição fará com que a coluna automaticamente faça parte da cláusula GROUP BY para que você não tente exibir inadvertidamente o conteúdo de uma linha individual em um resumo.</span><span class="sxs-lookup"><span data-stu-id="32b33-104">For example, if you are creating an aggregate query and mark a data column for output, the Query and View Designer automatically makes the column part of the GROUP BY clause so that you do not inadvertently attempt to display the contents of an individual row in a summary.</span></span>  
  
## <a name="using-group-by"></a><span data-ttu-id="32b33-105">Usando Agrupar por</span><span class="sxs-lookup"><span data-stu-id="32b33-105">Using Group By</span></span>  
 <span data-ttu-id="32b33-106">O Designer de Consulta e Exibição usa as seguintes diretrizes para trabalhar com colunas:</span><span class="sxs-lookup"><span data-stu-id="32b33-106">The Query and View Designer uses the following guidelines for working with columns:</span></span>  
  
-   <span data-ttu-id="32b33-107">Quando você escolhe a opção Agrupar por ou adiciona uma função de agregação a uma consulta, todas as colunas marcadas para saída ou usadas para classificação são adicionadas automaticamente à cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="32b33-107">When you choose the Group By option or add an aggregate function to a query, all columns marked for output or used for sorting are automatically added to the GROUP BY clause.</span></span> <span data-ttu-id="32b33-108">As colunas não serão adicionadas automaticamente à cláusula GROUP BY se já fizerem parte de uma função de agregação.</span><span class="sxs-lookup"><span data-stu-id="32b33-108">Columns are not automatically added to the GROUP BY clause if they are already part of an aggregate function.</span></span>  
  
     <span data-ttu-id="32b33-109">Se você não quiser que uma determinada coluna faça parte da cláusula GROUP BY, deverá alterar isso manualmente selecionando uma opção diferente na coluna Agrupar por do painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="32b33-109">If you do not want a particular column to be part of the GROUP BY clause, you must manually change it by selecting a different option in the Group By column of the Criteria pane.</span></span> <span data-ttu-id="32b33-110">Porém, o Designer de Consulta e Exibição não impedirá a escolha de uma opção que possa resultar em uma consulta que não será executada.</span><span class="sxs-lookup"><span data-stu-id="32b33-110">However, the Query and View Designer will not prevent you from choosing an option that can result in a query that will not run.</span></span>  
  
-   <span data-ttu-id="32b33-111">Se você adicionar uma coluna de saída de consulta manualmente a uma função de agregação no painel Critérios ou SQL, o Designer de Consulta e Exibição não removerá automaticamente outras colunas de saída da consulta.</span><span class="sxs-lookup"><span data-stu-id="32b33-111">If you manually add a query output column to an aggregate function in either the Criteria or SQL pane, the Query and View Designer does not automatically remove other output columns from the query.</span></span> <span data-ttu-id="32b33-112">Portanto, você deve remover as colunas restantes da saída da consulta ou torná-las parte da cláusula GROUP BY ou de uma função de agregação.</span><span class="sxs-lookup"><span data-stu-id="32b33-112">Therefore, you must remove the remaining columns from the query output or make them part of the GROUP BY clause or of an aggregate function.</span></span>  
  
 <span data-ttu-id="32b33-113">Quando você insere um critério de pesquisa na coluna Filtrar do painel Critérios, o Designer de Consulta e Exibição segue estas regras:</span><span class="sxs-lookup"><span data-stu-id="32b33-113">When you enter a search condition into the Filter column of the Criteria pane, the Query and View Designer follows these rules:</span></span>  
  
-   <span data-ttu-id="32b33-114">Se a coluna **Agrupar por** da grade não for exibida (porque você ainda não especificou uma consulta de agregação), os critérios de pesquisa serão colocados na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="32b33-114">If the **Group By** column of the grid is not displayed (because you have not yet specified an aggregate query), the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="32b33-115">Se você já estiver em uma consulta de agregação e tiver selecionado a opção **Where** na coluna **Agrupar por** , os critérios de pesquisa serão colocados na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="32b33-115">If you are already in an aggregate query and have selected the option **Where** in the **Group By** column, the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="32b33-116">Se a coluna **Agrupar por** contiver qualquer valor diferente de **Where**, os critérios de pesquisa serão colocados na cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="32b33-116">If the **Group By** column contains any value other than **Where**, the search condition is placed in the HAVING clause.</span></span>  
  
## <a name="using-the-having-and-where-clauses"></a><span data-ttu-id="32b33-117">Usando as cláusulas HAVING e WHERE</span><span class="sxs-lookup"><span data-stu-id="32b33-117">Using the HAVING and WHERE Clauses</span></span>  
 <span data-ttu-id="32b33-118">Os seguintes princípios descrevem como você pode fazer referência a colunas em uma consulta de agregação nos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="32b33-118">The following principles describe how you can reference columns in an aggregate query in search conditions.</span></span> <span data-ttu-id="32b33-119">Em geral, você pode usar uma coluna em um critério de pesquisa para filtrar as linhas que devem ser resumidas (uma cláusula WHERE) ou determinar quais resultados agrupados serão exibidos na saída final (uma cláusula HAVING).</span><span class="sxs-lookup"><span data-stu-id="32b33-119">In general, you can use a column in a search condition to filter the rows that should be summarized (a WHERE clause) or to determine which grouped results appear in the final output (a HAVING clause).</span></span>  
  
-   <span data-ttu-id="32b33-120">As colunas de dados individuais podem ser exibidas na cláusula WHERE ou HAVING, dependendo de como elas estão sendo usadas em outra consulta.</span><span class="sxs-lookup"><span data-stu-id="32b33-120">Individual data columns can appear in either the WHERE or HAVING clause, depending on how they are used elsewhere in the query.</span></span>  
  
-   <span data-ttu-id="32b33-121">As cláusulas WHERE são usadas para selecionar um subconjunto de linhas para resumo e agrupamento e, depois, são aplicadas antes que qualquer agrupamento seja feito.</span><span class="sxs-lookup"><span data-stu-id="32b33-121">WHERE clauses are used to select a subset of rows for summarizing and grouping and are thus applied before any grouping is done.</span></span> <span data-ttu-id="32b33-122">Portanto, você poderá usar uma coluna de dados em uma cláusula WHERE mesmo se ela não fizer parte da cláusula GROUP BY ou estiver contida em uma função de agregação.</span><span class="sxs-lookup"><span data-stu-id="32b33-122">Therefore, you can use a data column in a WHERE clause even if it is not part of the GROUP BY clause or contained in an aggregate function.</span></span> <span data-ttu-id="32b33-123">Por exemplo, a instrução seguinte seleciona todos os títulos que custam mais de R$ 10,00 e calcula a média do preço:</span><span class="sxs-lookup"><span data-stu-id="32b33-123">For example, the following statement selects all titles that cost more than $10.00 and averages the price:</span></span>  
  
    ```  
    SELECT AVG(price)  
    FROM titles  
    WHERE price > 10  
    ```  
  
-   <span data-ttu-id="32b33-124">Se você criar uma condição de pesquisa que envolva uma coluna também usada em uma cláusula GROUP BY ou em uma função de agregação, a condição de pesquisa poderá ser exibida como uma cláusula WHERE ou como uma cláusula HAVING; você decide quando você criar a condição.</span><span class="sxs-lookup"><span data-stu-id="32b33-124">If you create a search condition that involves a column also used in a GROUP BY clause or aggregate function, the search condition can appear as either a WHERE clause or a HAVING clause - you can decide which when you create the condition.</span></span> <span data-ttu-id="32b33-125">Por exemplo, a seguinte instrução cria um preço médio para os títulos de cada editor, depois exibe a média para as publicações nas quais o preço médio é maior que R$ 10,00:</span><span class="sxs-lookup"><span data-stu-id="32b33-125">For example, the following statement creates an average price for the titles for each publisher, then displays the average for the publishers in which the average price is greater than $10.00:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
    ```  
  
-   <span data-ttu-id="32b33-126">Se você usar uma função de agregação em um critério de pesquisa, o critério envolverá um resumo e deverá, portanto, fazer parte da cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="32b33-126">If you use an aggregate function in a search condition, the condition involves a summary and must therefore be part of the HAVING clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b33-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32b33-127">See Also</span></span>  
 <span data-ttu-id="32b33-128">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="32b33-128">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="32b33-129">Classificar e agrupar resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="32b33-129">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
