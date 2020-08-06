---
title: O script MDX básico (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default MDX scripts
- statements [MDX]
- expressions [MDX], scripts
- scripts [MDX], about scripts
ms.assetid: 83d9afda-7d34-42b5-8f28-20172a905f23
author: minewiskan
ms.author: owend
ms.openlocfilehash: de0d2fea002beda0eca480bd27140bdd202fcb83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683755"
---
# <a name="the-basic-mdx-script-mdx"></a><span data-ttu-id="6aab1-102">O script básico de MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="6aab1-102">The Basic MDX Script (MDX)</span></span>
  <span data-ttu-id="6aab1-103">Um script MDX define o processo de cálculo para um cubo no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6aab1-103">A Multidimensional Expressions (MDX) script defines the calculation process for a cube in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="6aab1-104">Existem dois tipos de scripts MDX:</span><span class="sxs-lookup"><span data-stu-id="6aab1-104">There are two types of MDX scripts:</span></span>  
  
 <span data-ttu-id="6aab1-105">**O script MDX padrão**</span><span class="sxs-lookup"><span data-stu-id="6aab1-105">**The default MDX script**</span></span>  
 <span data-ttu-id="6aab1-106">Quando você cria um cubo, o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] cria um script MDX padrão para esse cubo.</span><span class="sxs-lookup"><span data-stu-id="6aab1-106">At the time that you create a cube, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates a default MDX script for that cube.</span></span> <span data-ttu-id="6aab1-107">Esse script define uma passagem de cálculo para o cubo inteiro.</span><span class="sxs-lookup"><span data-stu-id="6aab1-107">This script defines a calculation pass for the whole cube.</span></span>  
  
 <span data-ttu-id="6aab1-108">**Script MDX definido pelo usuário**</span><span class="sxs-lookup"><span data-stu-id="6aab1-108">**User-defined MDX script**</span></span>  
 <span data-ttu-id="6aab1-109">Depois que você criar um cubo, poderá adicionar scripts MDX definidos pelo usuário que ampliam os recursos de cálculo do cubo.</span><span class="sxs-lookup"><span data-stu-id="6aab1-109">After you have created a cube, you can add user-defined MDX scripts that extend the calculation capabilities of the cube.</span></span>  
  
## <a name="the-default-mdx-script"></a><span data-ttu-id="6aab1-110">O script MDX padrão</span><span class="sxs-lookup"><span data-stu-id="6aab1-110">The Default MDX Script</span></span>  
 <span data-ttu-id="6aab1-111">O script MDX padrão criado pelo [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] quando você define um cubo contém uma única instrução CALCULATE.</span><span class="sxs-lookup"><span data-stu-id="6aab1-111">The default MDX script that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates when you define a cube contains a single CALCULATE statement.</span></span> <span data-ttu-id="6aab1-112">Essa única instrução CALCULATE fica no início do script MDX padrão e indica que o cubo inteiro deve ser calculado durante a primeira passagem de cálculo.</span><span class="sxs-lookup"><span data-stu-id="6aab1-112">This single CALCULATE statement is at the beginning of the default MDX script, and indicates that the entire cube should be calculated during the first calculation pass.</span></span>  
  
 <span data-ttu-id="6aab1-113">O script MDX padrão também contém comandos de script que criam conjuntos nomeados, atribuições e membros calculados criados no Designer de Cubo:</span><span class="sxs-lookup"><span data-stu-id="6aab1-113">The default MDX script also contains the script commands that create named sets, assignments, and calculated members created in Cube Designer:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="6aab1-114">adiciona diretamente comandos de script ao script MDX padrão.</span><span class="sxs-lookup"><span data-stu-id="6aab1-114">directly adds script commands to the default MDX script.</span></span>  
  
-   <span data-ttu-id="6aab1-115">Para cada conjunto nomeado do cubo, existe uma instrução CREATE SET correspondente no script MDX padrão.</span><span class="sxs-lookup"><span data-stu-id="6aab1-115">For each named set in the cube, a corresponding CREATE SET statement exists in the default MDX script.</span></span>  
  
-   <span data-ttu-id="6aab1-116">Para cada membro calculado definido no cubo, existe uma instrução CREATE MEMBER correspondente no script MDX padrão.</span><span class="sxs-lookup"><span data-stu-id="6aab1-116">For each calculated member defined in the cube, a corresponding CREATE MEMBER statement exists in the default MDX script.</span></span>  
  
 <span data-ttu-id="6aab1-117">Você controla a ordem de comandos de script, conjuntos nomeados e membros calculados no script MDX padrão usando a guia **Cálculos** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="6aab1-117">You can control the order of script commands, named sets, and calculated members in the default MDX script by using the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="6aab1-118">Para obter mais informações sobre como definir cálculos armazenados no script MDX padrão, consulte [Cálculos em modelos multidimensionais](../calculations-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="6aab1-118">For more information on defining calculations stored in the default MDX script, see [Calculations in Multidimensional Models](../calculations-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="6aab1-119">Se não houver um script MDX associado a um cubo, este assumirá o script MDX padrão.</span><span class="sxs-lookup"><span data-stu-id="6aab1-119">If there is no MDX script associated with a cube, the cube assumes the default MDX script.</span></span> <span data-ttu-id="6aab1-120">Um cubo precisa estar associado a pelo menos um script MDX porque o cubo depende do script MDX para determinar o comportamento do cálculo.</span><span class="sxs-lookup"><span data-stu-id="6aab1-120">A cube needs to be associated with at least one MDX script because a cube relies on the MDX script to determine calculation behavior.</span></span> <span data-ttu-id="6aab1-121">Em outras palavras, um cubo que não foi associado a um script MDX ou foi associado a um script MDX vazio não poderia e não deveria ser capaz de calcular células.</span><span class="sxs-lookup"><span data-stu-id="6aab1-121">In other words, a cube that was not associated with an MDX script or was associated with an empty MDX script could not and would not be able to calculate any cells.</span></span> <span data-ttu-id="6aab1-122">Se você criar cubos programaticamente, seja usando comandos do Analysis Services Scripting Language (ASSL) ou usando o Analysis Management Objects (AMO), é recomendável que você crie um script MDX padrão que contenha uma única instrução CALCULATE para o cubo.</span><span class="sxs-lookup"><span data-stu-id="6aab1-122">If you programmatically create cubes, either by using Analysis Services Scripting Language (ASSL) commands or by using Analysis Management Objects (AMO), it is recommended that you create a default MDX script containing a single CALCULATE statement for the cube.</span></span>  
  
## <a name="mdx-script-content"></a><span data-ttu-id="6aab1-123">Conteúdo do script MDX</span><span class="sxs-lookup"><span data-stu-id="6aab1-123">MDX Script Content</span></span>  
 <span data-ttu-id="6aab1-124">Um script MDX pode conter as seguintes instruções e expressões:</span><span class="sxs-lookup"><span data-stu-id="6aab1-124">An MDX script can contain the following statements and expressions:</span></span>  
  
 <span data-ttu-id="6aab1-125">Todas as instruções de script MDX</span><span class="sxs-lookup"><span data-stu-id="6aab1-125">All MDX scripting statements</span></span>  
 <span data-ttu-id="6aab1-126">Em scripts MDX, as instruções de script MDX controlam o contexto e o escopo dos cálculos e gerenciam o comportamento de outras instruções do script MDX.</span><span class="sxs-lookup"><span data-stu-id="6aab1-126">In MDX scripts, MDX scripting statements control the context and scope of calculations, and manage the behavior of other statements in the MDX script.</span></span> <span data-ttu-id="6aab1-127">Essa categoria inclui as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="6aab1-127">This category includes the following statements:</span></span>  
  
-   [<span data-ttu-id="6aab1-128">CALCULADO</span><span class="sxs-lookup"><span data-stu-id="6aab1-128">CALCULATE</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
-   [<span data-ttu-id="6aab1-129">Trave</span><span class="sxs-lookup"><span data-stu-id="6aab1-129">FREEZE</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
-   [<span data-ttu-id="6aab1-130">COM</span><span class="sxs-lookup"><span data-stu-id="6aab1-130">SCOPE</span></span>](/sql/mdx/mdx-scripting-scope)  
  
 <span data-ttu-id="6aab1-131">Para obter mais informações sobre instruções de scripts MDX, consulte [Instruções de script MDX &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span><span class="sxs-lookup"><span data-stu-id="6aab1-131">For more information on MDX scripting statements, see [MDX Scripting Statements &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span></span>  
  
 [<span data-ttu-id="6aab1-132">CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="6aab1-132">CREATE MEMBER</span></span>](/sql/mdx/mdx-data-definition-create-member)  
 <span data-ttu-id="6aab1-133">Uma instrução CREATE MEMBER cria membros calculados.</span><span class="sxs-lookup"><span data-stu-id="6aab1-133">The CREATE MEMBER statement creates calculated members.</span></span> <span data-ttu-id="6aab1-134">Para obter mais informações sobre como criar membros calculados, consulte [Criando membros calculados em MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="6aab1-134">For more information about how to create calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
 [<span data-ttu-id="6aab1-135">CREATE SET</span><span class="sxs-lookup"><span data-stu-id="6aab1-135">CREATE SET</span></span>](/sql/mdx/mdx-data-definition-create-set)  
 <span data-ttu-id="6aab1-136">A instrução CREATE SET cria conjuntos nomeados.</span><span class="sxs-lookup"><span data-stu-id="6aab1-136">The CREATE SET statement creates named sets.</span></span> <span data-ttu-id="6aab1-137">Para obter mais informações sobre como criar conjuntos de nomes, consulte [Criando conjuntos nomeados em MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="6aab1-137">For more information about how to create names sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="6aab1-138">Instruções de condição</span><span class="sxs-lookup"><span data-stu-id="6aab1-138">Conditional statements</span></span>  
 <span data-ttu-id="6aab1-139">As instruções condicionais adicionam lógica condicional a scripts MDX.</span><span class="sxs-lookup"><span data-stu-id="6aab1-139">Conditional statements add conditional logic to MDX scripts.</span></span> <span data-ttu-id="6aab1-140">Essa categoria inclui as instruções [CASE](/sql/mdx/case-statement-mdx) e [IF](/sql/mdx/mdx-scripting-if) .</span><span class="sxs-lookup"><span data-stu-id="6aab1-140">This category includes the [CASE](/sql/mdx/case-statement-mdx) and [IF](/sql/mdx/mdx-scripting-if) statements.</span></span>  
  
 <span data-ttu-id="6aab1-141">Expressões de atribuição</span><span class="sxs-lookup"><span data-stu-id="6aab1-141">Assignment expressions</span></span>  
 <span data-ttu-id="6aab1-142">Uma expressão de atribuição atribui uma expressão, como um valor, a um subcubo restrito.</span><span class="sxs-lookup"><span data-stu-id="6aab1-142">An assignment expression assigns an expression, such as a value, to a constrained subcube.</span></span> <span data-ttu-id="6aab1-143">Uma expressão de subcubo restrito é uma coleção de expressões de conjunto restritas que definem as "bordas" de um subcubo em um script MDX.</span><span class="sxs-lookup"><span data-stu-id="6aab1-143">A constrained subcube expression is a collection of constrained set expressions that define the "edges" of a subcube within an MDX script.</span></span> <span data-ttu-id="6aab1-144">Os códigos a seguir mostram a sintaxe de uma expressão de subcubo restrito:</span><span class="sxs-lookup"><span data-stu-id="6aab1-144">The following codes shows the syntax for a constrained subcube expression:</span></span>  
  
```  
<Constrained subcube> ::= (   
    ( <Constrained set> [<Crossjoin operator> <Constrained set>...] |  
    <ROOT function> |  
    <TREE function> |  
    LEAVES() |  
    * ) [, <Constrained subcube>...]  
<Constrained set> ::=   
    <Natural hierarchy>.MEMBERS |   
    <Natural hierarchy>.LEVEL(<numeric expression>).MEMBERS |   
    { <Natural hierarchy member> } |   
    DESCENDANTS( <Natural hierarchy member>, <Level expression>, ( SELF | AFTER | SELF_AND_AFTER ) ) |   
    DESCENDANTS( <Natural hierarchy member>, , LEAVES )  
<Natural hierarchy> ::= <Hierarchy identifier>  
<Natural hierarchy member> ::= <Natural hierarchy>.<identifier>[.<identifier>...]  
```  
  
## <a name="see-also"></a><span data-ttu-id="6aab1-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6aab1-145">See Also</span></span>  
 <span data-ttu-id="6aab1-146">[Referência de linguagem MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="6aab1-146">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="6aab1-147">Conceitos básicos do script MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6aab1-147">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
