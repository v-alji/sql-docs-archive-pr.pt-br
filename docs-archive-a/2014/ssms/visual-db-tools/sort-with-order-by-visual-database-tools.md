---
title: Classificar com ORDER BY (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ORDER BY clause [Visual Database Tools]
ms.assetid: 459f5640-8058-4c24-97e7-7bbd6168bc39
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93bdb9ed01c7935c5b9dae543804fca758a9262d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683874"
---
# <a name="sort-with-order-by-visual-database-tools"></a><span data-ttu-id="9fa4b-102">Classificar com ORDER BY (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9fa4b-102">Sort with ORDER BY (Visual Database Tools)</span></span>
  <span data-ttu-id="9fa4b-103">Você pode classificar resultados de consulta por uma ou mais das colunas nas linhas retornadas usando uma cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-103">You can sort query results by one or more of the columns in the returned rows by using an ORDER BY clause.</span></span> <span data-ttu-id="9fa4b-104">Você pode definir uma cláusula ORDER BY escolhendo opções no painel Detalhes de Critérios.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-104">You can define an ORDER BY clause by choosing options in the Criteria Details pane.</span></span>  
  
### <a name="to-sort-a-query-using-an-order-by-clause"></a><span data-ttu-id="9fa4b-105">Para classificar uma consulta usando uma cláusula ORDER BY</span><span class="sxs-lookup"><span data-stu-id="9fa4b-105">To sort a query using an ORDER BY clause</span></span>  
  
1.  <span data-ttu-id="9fa4b-106">Abra uma consulta ou crie uma nova.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-106">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="9fa4b-107">No [Painel Critérios](visual-database-tools.md), clique na coluna **Tipo de Classificação** da linha que corresponde à coluna a ser usada para classificar seus resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-107">In the [Criteria Pane](visual-database-tools.md), click the **Sort Type** column for the row corresponding to the column that you want to use to sort your query results.</span></span>  
  
3.  <span data-ttu-id="9fa4b-108">Escolha *Crescente* ou *Decrescente* na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-108">Choose *Ascending* or *Descending* from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fa4b-109">Desmarcar a entrada **Tipo de Classificação** de uma coluna remove essa coluna da cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-109">Clearing the **Sort Type** entry for a column removes that column from the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="9fa4b-110">Note que conforme você trabalha no painel de critérios, a cláusula UNION de sua consulta é alterada para corresponder a suas ações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fa4b-111">Ao classificar resultados em mais de uma coluna, especifique a ordem de pesquisa das colunas em relação umas às outras usando a coluna **Ordem de Classificação** .</span><span class="sxs-lookup"><span data-stu-id="9fa4b-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the **Sort Order** column.</span></span> <span data-ttu-id="9fa4b-112">Para obter mais informações, consulte **Como classificar várias colunas em consultas**.</span><span class="sxs-lookup"><span data-stu-id="9fa4b-112">For more information, see **How to: Sort Multiple Columns in Queries**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa4b-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9fa4b-113">See Also</span></span>  
 <span data-ttu-id="9fa4b-114">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9fa4b-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="9fa4b-115">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9fa4b-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9fa4b-116">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9fa4b-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
