---
title: Classificar em ordem crescente ou decrescente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- descending sorts
- ascending sorts
ms.assetid: d61cc55b-9ee8-4ecf-a32f-6459ae43910b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b5e6b00f62cfc297cc5930bc8cf3a41314a2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582728"
---
# <a name="sort-in-ascending-or-descending-order-visual-database-tools"></a><span data-ttu-id="fd48e-102">Classificar em ordem crescente ou decrescente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fd48e-102">Sort in Ascending or Descending Order (Visual Database Tools)</span></span>
  <span data-ttu-id="fd48e-103">Você pode classificar os resultados da consulta em ordem crescente ou decrescente em uma ou mais das colunas do conjunto de resultados usando as palavras-chaves `ASC` ou `DESC` com a cláusula `ORDER BY` .</span><span class="sxs-lookup"><span data-stu-id="fd48e-103">You can sort query results in ascending or descending order on one or more of the columns in the result set by using the `ASC` or `DESC` keywords with the `ORDER BY` clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd48e-104">A ordem de classificação é determinada em parte pela sequência de ordenação da coluna.</span><span class="sxs-lookup"><span data-stu-id="fd48e-104">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="fd48e-105">Você pode alterar a sequência de ordenação na [Caixa de Diálogo de Ordenação](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fd48e-105">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="fd48e-106">O procedimento seguinte supõe que você tenha uma consulta aberta no Designer de Consulta e Visualização que usa a cláusula ORDER BY para ordenar uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="fd48e-106">The following procedure assumes that you have a query open in Query and View Designer that uses the ORDER BY clause to sort one or more columns.</span></span>  
  
### <a name="to-specify-or-change-the-order-in-which-results-are-sorted"></a><span data-ttu-id="fd48e-107">Para especificar ou alterar a ordem na qual os resultados são ordenados</span><span class="sxs-lookup"><span data-stu-id="fd48e-107">To specify or change the order in which results are sorted</span></span>  
  
1.  <span data-ttu-id="fd48e-108">No painel [Critérios](criteria-pane-visual-database-tools.md), clique no campo **Tipo de Classificação** para a coluna que você deseja reclassificar.</span><span class="sxs-lookup"><span data-stu-id="fd48e-108">In the [Criteria pane](criteria-pane-visual-database-tools.md), click the **Sort Type** field for the column that you want to reorder.</span></span>  
  
2.  <span data-ttu-id="fd48e-109">Escolha **Crescente** ou **Decrescente** para especificar a ordem de classificação da coluna.</span><span class="sxs-lookup"><span data-stu-id="fd48e-109">Choose **Ascending** or **Descending** to specify the sort order for the column.</span></span>  
  
 <span data-ttu-id="fd48e-110">Note que conforme você trabalha no painel de critérios, a cláusula UNION de sua consulta é alterada para corresponder a suas ações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="fd48e-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd48e-111">Ao classificar resultados em mais de uma coluna, especifique a ordem de pesquisa das colunas em relação umas às outras usando a coluna Ordem de Classificação.</span><span class="sxs-lookup"><span data-stu-id="fd48e-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the Sort Order column.</span></span> <span data-ttu-id="fd48e-112">Para obter mais informações, consulte [Classificar várias colunas em consultas &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fd48e-112">For more information, see [Sort Multiple Columns in Queries &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd48e-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd48e-113">See Also</span></span>  
 <span data-ttu-id="fd48e-114">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fd48e-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="fd48e-115">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fd48e-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fd48e-116">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fd48e-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
