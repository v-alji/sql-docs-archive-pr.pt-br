---
title: Estabelecendo o contexto de cubo em uma consulta (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], MDX
- MDX [Analysis Services], cube context
- SELECT statement [MDX]
- Multidimensional Expressions [Analysis Services], cube context
- queries [MDX], cube context
ms.assetid: 79d6a1e8-2825-4eb9-97df-5071aecae8f0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72ae6e19f879651feb47841d70b444e9f845c74e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678313"
---
# <a name="establishing-cube-context-in-a-query-mdx"></a><span data-ttu-id="2f2d2-102">Estabelecendo o contexto de cubo em uma consulta (MDX)</span><span class="sxs-lookup"><span data-stu-id="2f2d2-102">Establishing Cube Context in a Query (MDX)</span></span>
  <span data-ttu-id="2f2d2-103">Toda consulta MDX é executada em um contexto de cubo especificado.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-103">Every MDX query runs within a specified cube context.</span></span> <span data-ttu-id="2f2d2-104">Esse contexto define os membros que são avaliados pelas expressões da consulta.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-104">This context defines the members that are evaluated by the expressions within the query.</span></span>  
  
 <span data-ttu-id="2f2d2-105">Na instrução SELECT, a cláusula FROM determina o contexto de cubo.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-105">In the SELECT statement, the FROM clause determines the cube context.</span></span> <span data-ttu-id="2f2d2-106">Esse contexto pode ser o cubo inteiro ou apenas um subcubo dele.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-106">This context can be the whole cube or just a subcube from that cube.</span></span> <span data-ttu-id="2f2d2-107">Ao especificar o contexto de cubo usando a cláusula FROM, você pode usar funções adicionais para expandir ou restringir esse contexto.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-107">Having specified cube context through the FROM clause, you can use additional functions to expand or restrict that context.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f2d2-108">As instruções SCOPE e CALCULATE também permitem administrar o contexto de cubo a partir de um script MDX.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-108">The SCOPE and CALCULATE statements also let you manage cube context from within an MDX script.</span></span> <span data-ttu-id="2f2d2-109">Para obter mais informações, consulte [Conceitos básicos do script MDX &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="2f2d2-109">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
## <a name="from-clause-syntax"></a><span data-ttu-id="2f2d2-110">Sintaxe da cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="2f2d2-110">FROM Clause Syntax</span></span>  
 <span data-ttu-id="2f2d2-111">A sintaxe a seguir descreve a cláusula FROM:</span><span class="sxs-lookup"><span data-stu-id="2f2d2-111">The following syntax describes the FROM clause:</span></span>  
  
```  
<SELECT subcube clause> ::=  
   Cube_Identifier |   
   (SELECT [  
      * |   
      ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]   
   FROM <SELECT subcube clause> <SELECT slicer axis clause> )  
```  
  
 <span data-ttu-id="2f2d2-112">Nessa sintaxe, observe que é a cláusula `<SELECT subcube clause>` que descreve o cubo ou o subcubo no qual a instrução SELECT é executada.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-112">In this syntax, notice that it is the `<SELECT subcube clause>` clause that describes the cube or subcube on which the SELECT statement is executed.</span></span>  
  
 <span data-ttu-id="2f2d2-113">Um exemplo simples de uma cláusula FROM seria aquele executado no cubo inteiro de exemplo Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-113">A simple example of a FROM clause would be one that runs against the entire Adventure Works sample cube.</span></span> <span data-ttu-id="2f2d2-114">Essa cláusula FROM teria o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="2f2d2-114">Such a FROM clause would have the following format:</span></span>  
  
```  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="2f2d2-115">Para obter mais informações sobre a cláusula FROM na instrução MDX SELECT, consulte [Instrução SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="2f2d2-115">For more information about the FROM clause in the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="refining-the-context"></a><span data-ttu-id="2f2d2-116">Refinando o contexto</span><span class="sxs-lookup"><span data-stu-id="2f2d2-116">Refining the Context</span></span>  
 <span data-ttu-id="2f2d2-117">Embora a cláusula FROM especifique o contexto de cubo como um único cubo, ela não impede que você trabalhe com os dados de mais de um cubo ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-117">Although the FROM clause specifies the cube context as within a single cube, this does not have to limit you from working with data from more than one cube at a time.</span></span>  
  
 <span data-ttu-id="2f2d2-118">Você pode usar a função MDX [LookupCube](/sql/mdx/lookupcube-mdx) para recuperar dados de cubos fora do contexto de cubo.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-118">You can use the MDX [LookupCube](/sql/mdx/lookupcube-mdx) function to retrieve data from cubes outside the cube context.</span></span> <span data-ttu-id="2f2d2-119">Além disso, funções, como a função [Filter](/sql/mdx/filter-mdx) , estão disponíveis para permitir a restrição temporária do contexto durante a avaliação da consulta.</span><span class="sxs-lookup"><span data-stu-id="2f2d2-119">Additionally, functions such as the [Filter](/sql/mdx/filter-mdx) function, are available that allow temporary restriction of the context while evaluating the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2d2-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f2d2-120">See Also</span></span>  
 [<span data-ttu-id="2f2d2-121">Conceitos básicos de consulta MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2f2d2-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
