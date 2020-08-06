---
title: Resumir ou agregar valores usando expressões personalizadas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- custom expressions to aggregate values [SQL Server]
ms.assetid: 34130ac1-0106-4766-b324-acb0b7bb6f6e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9f03f82842178a68c8a3d04ebc1bd738c0ab0b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683277"
---
# <a name="summarize-or-aggregate-values-using-custom-expressions-visual-database-tools"></a><span data-ttu-id="a19b7-102">Resumir ou agregar valores usando expressões personalizadas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a19b7-102">Summarize or Aggregate Values Using Custom Expressions (Visual Database Tools)</span></span>
  <span data-ttu-id="a19b7-103">Além de utilizar funções de agregação para agregar dados, você pode criar expressões personalizadas para produzir valores de agregação.</span><span class="sxs-lookup"><span data-stu-id="a19b7-103">In addition to using aggregate functions to aggregate data, you can create custom expressions to produce aggregate values.</span></span> <span data-ttu-id="a19b7-104">É possível utilizar expressões personalizadas ao invés de funções de agregação em qualquer lugar de uma consulta de agregação.</span><span class="sxs-lookup"><span data-stu-id="a19b7-104">You can use custom expressions in place of aggregate functions anywhere in an aggregate query.</span></span>  
  
 <span data-ttu-id="a19b7-105">Por exemplo, na tabela `titles` você poderia querer criar uma consulta que exibisse não só o preço médio, mas qual seria o preço médio se houvesse um desconto.</span><span class="sxs-lookup"><span data-stu-id="a19b7-105">For example, in the `titles` table you might want to create a query that shows not just the average price, but what the average price would be if it were discounted.</span></span>  
  
 <span data-ttu-id="a19b7-106">Você não pode incluir uma expressão baseada em cálculos que envolvem apenas linhas individuais na tabela; a expressão deve se basear em um valor de agregação, pois somente os valores de agregação estão disponíveis no momento em que a expressão é calculada.</span><span class="sxs-lookup"><span data-stu-id="a19b7-106">You cannot include an expression that is based on calculations involving only individual rows in the table; the expression must be based on an aggregate value, because only the aggregate values are available at the time the expression is calculated.</span></span>  
  
### <a name="to-specify-a-custom-expression-for-a-summary-value"></a><span data-ttu-id="a19b7-107">Para especificar uma expressão personalizada para um valor resumido</span><span class="sxs-lookup"><span data-stu-id="a19b7-107">To specify a custom expression for a summary value</span></span>  
  
1.  <span data-ttu-id="a19b7-108">Especifique os grupos para a sua consulta.</span><span class="sxs-lookup"><span data-stu-id="a19b7-108">Specify the groups for your query.</span></span> <span data-ttu-id="a19b7-109">Para obter detalhes, veja [Agrupar linhas em resultados da consulta &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a19b7-109">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="a19b7-110">Vá para uma linha em branco do painel Critérios e digite a expressão na coluna **Colunas**.</span><span class="sxs-lookup"><span data-stu-id="a19b7-110">Move to a blank row of the Criteria pane, and then type the expression in the **Columns** column.</span></span>  
  
     <span data-ttu-id="a19b7-111">O [Designer de Consulta e Exibição](query-and-view-designer-tools-visual-database-tools.md) atribui automaticamente um alias de coluna à expressão para criar um título da coluna útil na saída da consulta.</span><span class="sxs-lookup"><span data-stu-id="a19b7-111">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically assigns a column alias to the expression to create a useful column heading in query output.</span></span> <span data-ttu-id="a19b7-112">Para obter mais detalhes, veja [Criar aliases de coluna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a19b7-112">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
3.  <span data-ttu-id="a19b7-113">Na coluna **Agrupar por** da expressão, selecione **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="a19b7-113">In the **Group By** column for the expression, select **Expression**.</span></span>  
  
4.  <span data-ttu-id="a19b7-114">Executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="a19b7-114">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a19b7-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a19b7-115">See Also</span></span>  
 <span data-ttu-id="a19b7-116">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a19b7-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a19b7-117">Resumir resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a19b7-117">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
