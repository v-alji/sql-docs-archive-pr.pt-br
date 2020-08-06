---
title: Trabalhando com membros, tuplas e conjuntos (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], tuples
- member keys [MDX]
- MDX [Analysis Services], sets
- calculated members [MDX]
- members [MDX]
- Multidimensional Expressions [Analysis Services], members
- named sets [MDX]
- Multidimensional Expressions [Analysis Services], tuples
- member functions [MDX]
- sets [MDX]
- MDX [Analysis Services], members
- member names [MDX]
- Multidimensional Expressions [Analysis Services], sets
- tuple functions
- tuples
- set functions [MDX]
ms.assetid: b6ec2439-caef-46d3-9fd7-5f4526cee334
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ce3bf2d5ad7df2b1cd74897b3b49c7cef97e8ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569686"
---
# <a name="working-with-members-tuples-and-sets-mdx"></a><span data-ttu-id="1994f-102">Trabalhando com membros, tuplas e conjuntos (MDX)</span><span class="sxs-lookup"><span data-stu-id="1994f-102">Working with Members, Tuples, and Sets (MDX)</span></span>
  <span data-ttu-id="1994f-103">A linguagem MDX fornece inúmeras funções que retornam um ou mais membros, tuplas ou conjuntos ou que agem como tais.</span><span class="sxs-lookup"><span data-stu-id="1994f-103">MDX provides numerous functions that return one or more members, tuples, or sets; or that act upon a member, tuple, or set.</span></span>  
  
## <a name="member-functions"></a><span data-ttu-id="1994f-104">Funções de membro</span><span class="sxs-lookup"><span data-stu-id="1994f-104">Member Functions</span></span>  
 <span data-ttu-id="1994f-105">A linguagem MDX fornece várias funções para recuperar membros de outras entidades MDX, como de dimensões, níveis, conjuntos ou tuplas.</span><span class="sxs-lookup"><span data-stu-id="1994f-105">MDX provides several functions for retrieving members from other MDX entities, such as from dimensions, levels, sets, or tuples.</span></span> <span data-ttu-id="1994f-106">Por exemplo, a função [FirstChild](/sql/mdx/firstchild-mdx) é uma função que age em um membro e retorna um membro.</span><span class="sxs-lookup"><span data-stu-id="1994f-106">For example, the [FirstChild](/sql/mdx/firstchild-mdx) function is a function that acts upon a member and returns a member.</span></span>  
  
 <span data-ttu-id="1994f-107">Para obter o primeiro membro filho da dimensão Tempo, você pode declarar explicitamente o membro, como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="1994f-107">To obtain the first child member of the Time dimension, you can explicitly state the member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].[CY 2001] on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="1994f-108">Também é possível usar a função `FirstChild` para retornar o mesmo membro, como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="1994f-108">You can also use the `FirstChild` function to return the same member, as in the following example.</span></span>  
  
```  
SELECT [Date].[Calendar Year].FirstChild on 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="1994f-109">Para obter mais informações sobre as funções de membro MDX, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-109">For more information about MDX member functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="tuple-functions"></a><span data-ttu-id="1994f-110">funções de tupla</span><span class="sxs-lookup"><span data-stu-id="1994f-110">Tuple Functions</span></span>  
 <span data-ttu-id="1994f-111">A linguagem MDX fornece várias funções que retornam tuplas e que podem ser usadas em qualquer lugar onde uma tupla é aceitada.</span><span class="sxs-lookup"><span data-stu-id="1994f-111">MDX provides several functions that return tuples, and they can be used anywhere that a tuple is accepted.</span></span> <span data-ttu-id="1994f-112">Por exemplo, a função [Item &#40;Tupla&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) pode ser usada para extrair a primeira tupla do conjunto, o que é muito útil quando você sabe que um conjunto é composto por uma única tupla e quer fornecer essa tupla a uma função que requer uma tupla.</span><span class="sxs-lookup"><span data-stu-id="1994f-112">For example, the [Item &#40;Tuple&#41; &#40;MDX&#41;](/sql/mdx/item-tuple-mdx) function can be used to extract the first tuple from set, which is very useful when you know that a set is composed of a single tuple and you want to supply that tuple to a function that requires a tuple.</span></span>  
  
 <span data-ttu-id="1994f-113">O exemplo a seguir retorna a primeira tupla do conjunto de tuplas do eixo de coluna.</span><span class="sxs-lookup"><span data-stu-id="1994f-113">The following example returns the first tuple from within the set of tuples on the column axis.</span></span>  
  
```  
SELECT {  
   ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2003]  
   )  
, ([Measures].[Reseller Sales Amount]  
      ,[Date].[Calendar Year].[CY 2004]  
   )  
}.Item(0)  
ON COLUMNS   
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="1994f-114">Para obter mais informações sobre as funções de tupla, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-114">For more information about tuple functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="set-functions"></a><span data-ttu-id="1994f-115">Funções do conjunto</span><span class="sxs-lookup"><span data-stu-id="1994f-115">Set Functions</span></span>  
 <span data-ttu-id="1994f-116">A linguagem MDX fornece várias funções que retornam conjuntos.</span><span class="sxs-lookup"><span data-stu-id="1994f-116">MDX provides several functions that return sets.</span></span> <span data-ttu-id="1994f-117">Digitar explicitamente tuplas e colocá-las entre chaves não é a única maneira de recuperar um conjunto.</span><span class="sxs-lookup"><span data-stu-id="1994f-117">Explicitly typing tuples and enclosing them in braces is not the only way to retrieve a set.</span></span> <span data-ttu-id="1994f-118">Para obter mais informações sobre a função de membros para retornar um conjunto, consulte [Principais conceitos em MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="1994f-118">For more information about the members function to return a set, see [Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md).</span></span> <span data-ttu-id="1994f-119">Há várias funções de conjunto adicionais.</span><span class="sxs-lookup"><span data-stu-id="1994f-119">There are many additional set functions.</span></span>  
  
 <span data-ttu-id="1994f-120">O operador dois pontos permite o uso da ordem natural dos membros para criar um conjunto.</span><span class="sxs-lookup"><span data-stu-id="1994f-120">The colon operator lets you use the natural order of members to create a set.</span></span> <span data-ttu-id="1994f-121">Por exemplo, o conjunto mostrado no exemplo a seguir contém tuplas do primeiro ao quarto trimestre do ano calendário 2002.</span><span class="sxs-lookup"><span data-stu-id="1994f-121">For example, the set shown in the following example contains tuples for the 1st through the 4th quarter of calendar year 2002.</span></span>  
  
```  
SELECT   
   {[Calendar Quarter].[Q1 CY 2002]:[Calendar Quarter].[Q4 CY 2002]}   
ON 0  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="1994f-122">Se você não usar o operador dois pontos para criar o conjunto, pode criar o mesmo conjunto de membros especificando as tuplas do exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="1994f-122">If you do not use the colon operator to create the set, you can create the same set of members by specifying the tuples in the following example.</span></span>  
  
```  
SELECT {  
   [Calendar Quarter].[Q1 CY 2002],   
   [Calendar Quarter].[Q2 CY 2002],   
   [Calendar Quarter].[Q3 CY 2002],   
   [Calendar Quarter].[Q4 CY 2002]  
   } ON 0  
FROM [Adventure Works]  
  
```  
  
 <span data-ttu-id="1994f-123">O operador dois pontos é uma função inclusiva.</span><span class="sxs-lookup"><span data-stu-id="1994f-123">The colon operator is an inclusive function.</span></span> <span data-ttu-id="1994f-124">Os membros em ambos os lados do operador dois pontos são incluídos no conjunto resultante.</span><span class="sxs-lookup"><span data-stu-id="1994f-124">The members on both sides of the colon operator are included in the resulting set.</span></span>  
  
 <span data-ttu-id="1994f-125">Para obter mais informações sobre as funções de conjunto, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-125">For more information about set functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="array-functions"></a><span data-ttu-id="1994f-126">Funções de Matriz</span><span class="sxs-lookup"><span data-stu-id="1994f-126">Array Functions</span></span>  
 <span data-ttu-id="1994f-127">Uma função de matriz age em um conjunto e retorna uma matriz.</span><span class="sxs-lookup"><span data-stu-id="1994f-127">An array function acts upon a set and returns an array.</span></span> <span data-ttu-id="1994f-128">Para obter mais informações sobre as funções de matriz, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-128">For more information about array functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="hierarchy-functions"></a><span data-ttu-id="1994f-129">Funções de hierarquia</span><span class="sxs-lookup"><span data-stu-id="1994f-129">Hierarchy Functions</span></span>  
 <span data-ttu-id="1994f-130">Uma função de hierarquia retorna uma hierarquia ao agir em um membro, um nível, uma hierarquia ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1994f-130">A hierarchy function returns a hierarchy by acting upon a member, level, hierarchy, or string.</span></span> <span data-ttu-id="1994f-131">Para obter mais informações sobre as funções de hierarquia, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-131">For more information about hierarchy functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="level-functions"></a><span data-ttu-id="1994f-132">Funções de nível</span><span class="sxs-lookup"><span data-stu-id="1994f-132">Level Functions</span></span>  
 <span data-ttu-id="1994f-133">Uma função nivelada retorna um nível ao agir em um membro, um nível ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1994f-133">A level function returns a level by acting upon a member, level, or string.</span></span> <span data-ttu-id="1994f-134">Para obter mais informações sobre as funções de nível, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-134">For more information about level functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="logical-functions"></a><span data-ttu-id="1994f-135">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="1994f-135">Logical Functions</span></span>  
 <span data-ttu-id="1994f-136">Uma função lógica age em uma expressão MDX para retornar informações sobre tuplas, membros ou conjuntos da expressão.</span><span class="sxs-lookup"><span data-stu-id="1994f-136">A logical function acts upon a MDX expression to return information about the tuples, members, or sets in the expression.</span></span> <span data-ttu-id="1994f-137">Por exemplo, a função [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) avalia se uma expressão retornou um valor de célula vazio.</span><span class="sxs-lookup"><span data-stu-id="1994f-137">For example, the [IsEmpty &#40;MDX&#41;](/sql/mdx/isempty-mdx) function evaluates whether an expression has returned an empty cell value.</span></span> <span data-ttu-id="1994f-138">Para obter mais informações sobre as funções lógicas, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-138">For more information about logical functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="numeric-functions"></a><span data-ttu-id="1994f-139">Funções numéricas</span><span class="sxs-lookup"><span data-stu-id="1994f-139">Numeric Functions</span></span>  
 <span data-ttu-id="1994f-140">Uma função numérica age em uma expressão MDX para retornar um valor escalar.</span><span class="sxs-lookup"><span data-stu-id="1994f-140">A numeric function acts upon a MDX expression to return a scalar value.</span></span> <span data-ttu-id="1994f-141">Por exemplo, a função [Agregado &#40;MDX&#41;](/sql/mdx/aggregate-mdx) retorna um valor escalar calculado agregando medidas sobre as tuplas de um conjunto especificado.</span><span class="sxs-lookup"><span data-stu-id="1994f-141">For example, the [Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) function returns a scalar value calculated by aggregating measures over the tuples in a specified set.</span></span> <span data-ttu-id="1994f-142">Para obter mais informações sobre as funções numéricas, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-142">For more information about numeric functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="string-functions"></a><span data-ttu-id="1994f-143">Funções de Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="1994f-143">String Functions</span></span>  
 <span data-ttu-id="1994f-144">A função de cadeia de caracteres age em uma expressão MDX para retornar uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1994f-144">A string function acts upon a MDX expression to return a string.</span></span> <span data-ttu-id="1994f-145">Por exemplo, a função [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) retorna um valor de cadeia de caracteres que contém o nome exclusivo de uma dimensão, uma hierarquia, um nível ou um membro.</span><span class="sxs-lookup"><span data-stu-id="1994f-145">For example, the [UniqueName &#40;MDX&#41;](/sql/mdx/uniquename-mdx) function returns a string value containing the unique name of a dimension, hierarchy, level, or member.</span></span> <span data-ttu-id="1994f-146">Para obter mais informações sobre as funções de cadeia de caracteres, consulte [Referência da Função MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span><span class="sxs-lookup"><span data-stu-id="1994f-146">For more information about string functions, see [MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1994f-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1994f-147">See Also</span></span>  
 <span data-ttu-id="1994f-148">[Conceitos principais em MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="1994f-148">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="1994f-149">[Conceitos básicos de consulta MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="1994f-149">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="1994f-150">Referência da Função MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="1994f-150">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
