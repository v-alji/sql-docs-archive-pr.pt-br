---
title: Criando cálculos de célula em MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculated cells [MDX]
- queries [MDX], cell calculations
- cells [MDX]
- MDX [Analysis Services], calculations
- calculation subcubes [MDX]
- calculated values [MDX]
- Multidimensional Expressions [Analysis Services], cell calculations
ms.assetid: 068aea63-d419-4791-a960-3d74e76f808e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ab3219850c49c2ec16a12aab3ba7db67e9a8721
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681865"
---
# <a name="building-cell-calculations-in-mdx-mdx"></a><span data-ttu-id="a8dc9-102">Criando cálculos de célula em MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="a8dc9-102">Building Cell Calculations in MDX (MDX)</span></span>
  <span data-ttu-id="a8dc9-103">As expressões multidimensionais (MDX) fornecem inúmeras ferramentas para a geração de valores calculados, como membros calculados, acúmulos personalizados e membros personalizados.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-103">Multidimensional Expressions (MDX) provides you with a number of tools for generating calculated values, such as calculated members, custom rollups, and custom members.</span></span> <span data-ttu-id="a8dc9-104">No entanto, usar esses recursos para afetar um conjunto específico de células, ou uma única célula para esse fim, seria difícil.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-104">However, using these features to affect a specific set of cells, or a single cell for that matter, would be difficult.</span></span>  
  
 <span data-ttu-id="a8dc9-105">Para valores calculados gerados especificamente para células, use o recurso de células calculadas em MDX.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-105">To generated calculated values for specifically for cells, you need to use the calculated cells feature in MDX.</span></span> <span data-ttu-id="a8dc9-106">As células calculadas permitem a definição de uma porção de células específica, chamada *subcubo de cálculo*, e aplicam uma fórmula a todas as células do subcubo de cálculo, sujeita a um critério opcional que pode ser aplicado a cada célula.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-106">Calculated cells let you define a specific slice of cells, called a *calculation subcube*, and apply a formula to each and every cell within the calculation subcube, subject to an optional condition that can be applied to each cell.</span></span>  
  
 <span data-ttu-id="a8dc9-107">Células calculadas também oferecem funcionalidades complexas, como fórmulas que visam metas, como as usadas em KPIs (indicadores chave de desempenho), ou fórmulas de análise especulativa.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-107">Calculated cells also offer complex functionality, such as goal-seeking formulas, as used in KPIs, or speculative analysis formulas.</span></span> <span data-ttu-id="a8dc9-108">Esse nível de funcionalidade é proveniente do recurso de pedido de passagem no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] que permite que passes recursivos sejam feitos com células calculadas, com fórmulas de cálculo aplicadas a passagens específicas na ordem de passagem.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-108">This level of functionality comes from the pass order feature in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that allows recursive passes to be made with calculated cells, with calculation formulas applied at specific passes in the pass order.</span></span> <span data-ttu-id="a8dc9-109">Para obter mais informações sobre ordem de passagem, consulte [Entendendo a ordem de passagem e a ordem de resolução &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="a8dc9-109">For more information on pass order, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="a8dc9-110">Em termos de escopo de criação, as células calculadas são similares a conjuntos nomeados e membros calculados no modo como as células calculas podem ser temporariamente criadas para o ciclo de vida de uma sessão ou de uma única consulta ou disponibilizadas globalmente como parte de um cubo:</span><span class="sxs-lookup"><span data-stu-id="a8dc9-110">In terms of creation scope, calculated cells are similar to both named sets and calculated members in that calculated cells can be temporarily created for the lifetime of either a session or a single query, or made globally available as part of a cube:</span></span>  
  
-   <span data-ttu-id="a8dc9-111">**Com escopo da consulta** Para criar uma célula calculada que seja definida como parte de uma consulta MDX e, portanto, cujo escopo esteja limitado à consulta, use a palavra-chave WITH.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-111">**Query-scoped** To create a calculated cell that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="a8dc9-112">Você pode usar a célula calculada em uma instrução MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-112">You can then use the calculated cell within an MDX SELECT statement.</span></span> <span data-ttu-id="a8dc9-113">Usando essa abordagem, a célula calculada criada pelo uso da palavra-chave `WITH` pode ser alterada sem afetar a instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-113">Using this approach, the calculated cell created by using the `WITH` keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="a8dc9-114">Para obter mais informações sobre como usar a palavra-chave WITH para criar membros calculados, consulte [Criando cálculos de célula no escopo da consulta &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span><span class="sxs-lookup"><span data-stu-id="a8dc9-114">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span></span>  
  
-   <span data-ttu-id="a8dc9-115">**Com escopo da sessão** Para criar um membro calculado cujo escopo seja mais amplo que o contexto da consulta, ou seja, cujo escopo seja o tempo de vida da sessão MDX, use a instrução CREATE CELL CALCULATION ou ALTER CUBE.</span><span class="sxs-lookup"><span data-stu-id="a8dc9-115">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use either the CREATE CELL CALCULATION or ALTER CUBE statement.</span></span>  
  
     <span data-ttu-id="a8dc9-116">Para obter mais informações sobre como usar a instrução CREATE CELL CALCULATION ou ALTER CUBE para criar células calculadas em uma sessão, consulte [Criando células calculadas no escopo da sessão](mdx-cell-calculations-session-scoped-calculated-cells.md)</span><span class="sxs-lookup"><span data-stu-id="a8dc9-116">For more information about how to use either the CREATE CELL CALCULATION or ALTER CUBE statement to create calculated cells in a session, see [Creating Session-Scoped Calculated Cells](mdx-cell-calculations-session-scoped-calculated-cells.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8dc9-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8dc9-117">See Also</span></span>  
 <span data-ttu-id="a8dc9-118">[Instrução ALTER CUBE &#40;MDX&#41;](/sql/mdx/mdx-data-definition-alter-cube) </span><span class="sxs-lookup"><span data-stu-id="a8dc9-118">[ALTER CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-alter-cube) </span></span>  
 <span data-ttu-id="a8dc9-119">[CRIAR instrução de cálculo de célula &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span><span class="sxs-lookup"><span data-stu-id="a8dc9-119">[CREATE CELL CALCULATION Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span></span>  
 <span data-ttu-id="a8dc9-120">[Criando cálculos de célula com escopo de consulta &#40;&#41;MDX](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="a8dc9-120">[Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 [<span data-ttu-id="a8dc9-121">Conceitos básicos de consulta MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a8dc9-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
