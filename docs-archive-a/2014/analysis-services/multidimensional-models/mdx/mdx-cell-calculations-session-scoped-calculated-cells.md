---
title: Criando células calculadas no escopo da sessão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- session-scoped calculated members [MDX]
ms.assetid: f2d14a89-6286-4e74-9afb-091076f93f21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 199de07778a153cd1bc40b5033d364e5e0055bd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572743"
---
# <a name="creating-session-scoped-calculated-cells"></a><span data-ttu-id="a1087-102">Criando células calculadas no escopo da sessão</span><span class="sxs-lookup"><span data-stu-id="a1087-102">Creating Session-Scoped Calculated Cells</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="a1087-103">Esta sintaxe não está mais em uso.</span><span class="sxs-lookup"><span data-stu-id="a1087-103">This syntax has been deprecated.</span></span> <span data-ttu-id="a1087-104">Em vez dela, use atribuições MDX.</span><span class="sxs-lookup"><span data-stu-id="a1087-104">You should use MDX assignments should instead.</span></span> <span data-ttu-id="a1087-105">Para obter mais informações sobre atribuições, consulte [O script básico de MDX &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="a1087-105">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="a1087-106">Para criar células calculadas disponíveis para todas as consultas da mesma sessão, você pode usar a instrução [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) ou a instrução [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) .</span><span class="sxs-lookup"><span data-stu-id="a1087-106">To create calculated cells that are available to all queries in the same session, you can use either the [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) statement or the [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) statement.</span></span> <span data-ttu-id="a1087-107">Ambas produzem o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="a1087-107">Both statements have the same result.</span></span>  
  
## <a name="create-cell-calculation-syntax"></a><span data-ttu-id="a1087-108">Sintaxe de CREATE CELL CALCULATION</span><span class="sxs-lookup"><span data-stu-id="a1087-108">CREATE CELL CALCULATION Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1087-109">Esta sintaxe não está mais em uso.</span><span class="sxs-lookup"><span data-stu-id="a1087-109">This syntax has been deprecated.</span></span> <span data-ttu-id="a1087-110">Em vez dela, use atribuições MDX.</span><span class="sxs-lookup"><span data-stu-id="a1087-110">You should use MDX assignments should instead.</span></span> <span data-ttu-id="a1087-111">Para obter mais informações sobre atribuições, consulte [O script básico de MDX &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="a1087-111">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="a1087-112">Use a sintaxe a seguir para usar a instrução CREATE CELL CALCULATION para definir uma célula calculada no escopo da sessão:</span><span class="sxs-lookup"><span data-stu-id="a1087-112">Use the following syntax to use the CREATE CELL CALCULATION statement to define a session-scoped calculated cell:</span></span>  
  
```  
CREATE CELL CALCULATION Cube_Expression.<CREATE CELL CALCULATION body clause>  
  
<CREATE CELL CALCULATION body clause> ::=CellCalc_Identifier FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
## <a name="alter-cube-syntax"></a><span data-ttu-id="a1087-113">Sintaxe de ALTER CUBE</span><span class="sxs-lookup"><span data-stu-id="a1087-113">ALTER CUBE Syntax</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1087-114">Esta sintaxe não está mais em uso.</span><span class="sxs-lookup"><span data-stu-id="a1087-114">This syntax has been deprecated.</span></span> <span data-ttu-id="a1087-115">Em vez dela, use atribuições MDX.</span><span class="sxs-lookup"><span data-stu-id="a1087-115">You should use MDX assignments should instead.</span></span> <span data-ttu-id="a1087-116">Para obter mais informações sobre atribuições, consulte [O script básico de MDX &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="a1087-116">For more information on assignments, see [The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md).</span></span>  
  
 <span data-ttu-id="a1087-117">Use a sintaxe a seguir para usar a instrução ALTER CUBE para definir uma célula calculada no escopo da sessão:</span><span class="sxs-lookup"><span data-stu-id="a1087-117">Use the following syntax to use the ALTER CUBE statement to define a session-scoped calculated cell:</span></span>  
  
```  
ALTER CUBE Cube_Identifier CREATE CELL CALCULATION  
FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
 <span data-ttu-id="a1087-118">O valor `String_Expression` contém uma lista de expressões de conjunto MDX ortogonais e unidimensionais, sendo que cada uma deve resolver uma das categorias de conjuntos listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a1087-118">The `String_Expression` value contains a list of orthogonal, single-dimensional MDX set expressions, each of which must resolve to one of the categories of sets that are listed in the following table.</span></span>  
  
|<span data-ttu-id="a1087-119">Categoria</span><span class="sxs-lookup"><span data-stu-id="a1087-119">Category</span></span>|<span data-ttu-id="a1087-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="a1087-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a1087-121">Conjunto vazio</span><span class="sxs-lookup"><span data-stu-id="a1087-121">Empty set</span></span>|<span data-ttu-id="a1087-122">Uma expressão de conjunto MDX resolvida em um conjunto vazio.</span><span class="sxs-lookup"><span data-stu-id="a1087-122">An MDX set expression that resolves into an empty set.</span></span> <span data-ttu-id="a1087-123">Nesse caso, o escopo da célula calculada é o cubo inteiro.</span><span class="sxs-lookup"><span data-stu-id="a1087-123">In this case, the scope of the calculated cell is the whole cube.</span></span>|  
|<span data-ttu-id="a1087-124">Conjunto de membro único</span><span class="sxs-lookup"><span data-stu-id="a1087-124">Single member set</span></span>|<span data-ttu-id="a1087-125">Uma expressão de conjunto MDX resolvida em um único membro.</span><span class="sxs-lookup"><span data-stu-id="a1087-125">An MDX set expression that resolves into a single member.</span></span>|  
|<span data-ttu-id="a1087-126">Conjunto de membros do nível</span><span class="sxs-lookup"><span data-stu-id="a1087-126">Set of level members</span></span>|<span data-ttu-id="a1087-127">Uma expressão de conjunto MDX resolvida nos membros de um mesmo nível.</span><span class="sxs-lookup"><span data-stu-id="a1087-127">An MDX set expression that resolves into the members of a single level.</span></span> <span data-ttu-id="a1087-128">Um exemplo disso é a *Level_Expression*.`Members`</span><span class="sxs-lookup"><span data-stu-id="a1087-128">An example of this is the *Level_Expression*.`Members`</span></span> <span data-ttu-id="a1087-129">Função MDX.</span><span class="sxs-lookup"><span data-stu-id="a1087-129">MDX function.</span></span> <span data-ttu-id="a1087-130">Para incluir membros calculados, use o *Level_Expression*.`AllMembers`</span><span class="sxs-lookup"><span data-stu-id="a1087-130">To include calculated members, use the *Level_Expression*.`AllMembers`</span></span> <span data-ttu-id="a1087-131">Função MDX.</span><span class="sxs-lookup"><span data-stu-id="a1087-131">MDX function.</span></span><br /><br /> <span data-ttu-id="a1087-132">Para obter mais informações, consulte [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span><span class="sxs-lookup"><span data-stu-id="a1087-132">For more information, see [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).</span></span>|  
|<span data-ttu-id="a1087-133">Conjunto de descendentes</span><span class="sxs-lookup"><span data-stu-id="a1087-133">Set of descendants</span></span>|<span data-ttu-id="a1087-134">Uma expressão de conjunto MDX resolvida nos descendentes de um membro especificado.</span><span class="sxs-lookup"><span data-stu-id="a1087-134">An MDX set expression that resolves into the descendants of a specified member.</span></span> <span data-ttu-id="a1087-135">Um exemplo disso é a `Descendants` função MDX (*Member_Expression*, *Level_Expression*, *Desc_Flag*).</span><span class="sxs-lookup"><span data-stu-id="a1087-135">An example of this is the `Descendants`(*Member_Expression*, *Level_Expression*, *Desc_Flag*) MDX function.</span></span><br /><br /> <span data-ttu-id="a1087-136">Para obter mais informações, consulte [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span><span class="sxs-lookup"><span data-stu-id="a1087-136">For more information, see [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1087-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a1087-137">See Also</span></span>  
 [<span data-ttu-id="a1087-138">Criando cálculos de célula em MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="a1087-138">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)  
  
  
