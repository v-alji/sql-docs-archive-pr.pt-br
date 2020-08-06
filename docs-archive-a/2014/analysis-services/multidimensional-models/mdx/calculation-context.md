---
title: Contexto de cálculo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aec8aa98-b77d-4f8f-9684-2618b1d8e970
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6d14df51c6ec37fb96520af7acf207227ae4ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681222"
---
# <a name="calculation-context"></a><span data-ttu-id="82621-102">Contexto de cálculo</span><span class="sxs-lookup"><span data-stu-id="82621-102">Calculation Context</span></span>
  <span data-ttu-id="82621-103">O contexto de cálculo é o subespaço conhecido do cubo onde uma expressão é avaliada e todas as coordenadas são explicitamente conhecidas ou podem ser derivadas da expressão.</span><span class="sxs-lookup"><span data-stu-id="82621-103">The calculation context is the known subspace of the cube where an expression is evaluated and all coordinates are either explicitly known or can be derived from the expression.</span></span>  
  
## <a name="determining-the-calculation-context"></a><span data-ttu-id="82621-104">Determinando o contexto de cálculo</span><span class="sxs-lookup"><span data-stu-id="82621-104">Determining the calculation context</span></span>  
 <span data-ttu-id="82621-105">Cada conjunto, membro, tupla, ou função numérica é executado no contexto de toda a expressão ou instrução MDX.</span><span class="sxs-lookup"><span data-stu-id="82621-105">Every set, member, tuple, or numeric function executes in the context of the entire MDX expression or statement.</span></span> <span data-ttu-id="82621-106">Quando um argumento, como uma tupla, é transmitido para uma função, somente algumas das coordenadas no espaço do cubo são explicitamente fornecidas.</span><span class="sxs-lookup"><span data-stu-id="82621-106">When an argument, such as a tuple, is passed to a function, only some of the coordinates in the cube space are explicitly provided.</span></span> <span data-ttu-id="82621-107">As outras coordenadas são obtidas com base no contexto de cálculo atual.</span><span class="sxs-lookup"><span data-stu-id="82621-107">The other coordinates are obtained based on the current calculation context.</span></span>  
  
 <span data-ttu-id="82621-108">O contexto de cálculo para coordenadas de célula não especificada e membros de atributo é determinado na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="82621-108">The calculation context for unspecified cell coordinates and attribute members is determined in the following order:</span></span>  
  
1.  <span data-ttu-id="82621-109">A cláusula FROM (se aplicável) – essa cláusula pode especificar um cubo inteiro ou pode especificar um subcubo na forma de uma instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="82621-109">The FROM clause (if applicable) - this clause can either specify an entire cube or can specify a subcube in the form of a SELECT statement.</span></span>  
  
2.  <span data-ttu-id="82621-110">A cláusula WHERE (se aplicável) – essa cláusula, também conhecida como *eixo de segmentação*, em que você especifica um conjunto, tupla ou membro que restringe os membros retornados no eixo da coluna e eixo de linhas em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="82621-110">The WHERE clause (if applicable) - this clause, which is also known as the *slicer axis*, on which you specify a set, tuple, or member that restricts the members returned on the column and row axis by a query.</span></span> <span data-ttu-id="82621-111">Conceitualmente, o membro padrão de cada hierarquia de atributo que não é especificado explicitamente no eixo da coluna ou no eixo de linhas faz parte do eixo do slicer.</span><span class="sxs-lookup"><span data-stu-id="82621-111">Conceptually, the default member of every attribute hierarchy that is not explicitly specified on column or row axis is part of the slicer axis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82621-112">Quando as coordenadas da célula de um atributo específico são especificadas no eixo do slicer e em outro eixo, as coordenadas especificadas na função podem ter prioridade ao determinar os membros do conjunto no eixo.</span><span class="sxs-lookup"><span data-stu-id="82621-112">When cell coordinates for a particular attribute are specified on both the slicer axis and on another axis, the coordinates specified in the function may take precedence in determining the members of the set on the axis.</span></span> <span data-ttu-id="82621-113">As funções [Filter (MDX)](/sql/mdx/filter-mdx) e [Order (MDX)](/sql/mdx/order-mdx) são exemplos dessas funções – você pode filtrar ou pode ordenar um resultado por membros de atributo que são excluídos do contexto de cálculo pela cláusula WHERE, ou por uma instrução SELECT na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="82621-113">The [Filter (MDX)](/sql/mdx/filter-mdx) and [Order (MDX)](/sql/mdx/order-mdx) functions are examples of such functions - you can filter or order a result by attribute members that are excluded from the calculation context by the WHERE clause, or by a SELECT statement in the FROM clause.</span></span>  
  
3.  <span data-ttu-id="82621-114">Os conjuntos nomeados e membros calculados definidos na consulta ou na expressão.</span><span class="sxs-lookup"><span data-stu-id="82621-114">The named sets and calculated members defined in the query or expression.</span></span>  
  
4.  <span data-ttu-id="82621-115">As tuplas e conjuntos especificados nos eixos de linhas e da coluna, utilizando o membro padrão para atributos que não aparecem no eixo de linha, coluna ou do slicer.</span><span class="sxs-lookup"><span data-stu-id="82621-115">The tuples and sets specified on the row and column axes, utilizing the default member for attributes that do not appear on the row, column, or slicer axis.</span></span>  
  
5.  <span data-ttu-id="82621-116">As células de cubo ou subcubo em cada eixo, eliminando tuplas vazias no eixo e aplicando a cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="82621-116">The cube or subcube cells on each axis, eliminating empty tuples on the axis and applying the HAVING clause.</span></span>  
  
6.  <span data-ttu-id="82621-117">Para obter mais informações, consulte [Estabelecendo o contexto de cubo em uma consulta &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="82621-117">For more information, see [Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span></span>  
  
 <span data-ttu-id="82621-118">Na consulta a seguir, o contexto de cálculo para o eixo de linha é restrito pelo membro de atributo País e pelo membro de atributo Ano Civil que são especificados na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="82621-118">In the following query, the calculation context for the row axis is restricted by the Country attribute member and the Calendar Year attribute member that are specified in the WHERE clause.</span></span>  
  
```  
SELECT Customer.City.City.Members ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France, [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="82621-119">Porém, se você modificar essa consulta especificando a função `FILTER` no eixo de linhas, e utilizar um membro de hierarquia de atributo Ano Civil na função `FILTER`, o membro de atributo da hierarquia de atributo Ano Civil que é usada para fornecer o contexto de cálculo aos membros do conjunto no eixo da coluna poderá ser modificado.</span><span class="sxs-lookup"><span data-stu-id="82621-119">However, if you modify this query by specifying the `FILTER` function on the row axis, and utilize a Calendar Year attribute hierarchy member in the `FILTER` function, then the attribute member from the Calendar Year attribute hierarchy that is used to provide the calculation context for the members of the set on the column axis can be modified.</span></span>  
  
```  
SELECT FILTER  
   (  
      Customer.City.City.Members,   
         ([Date].[Calendar].[Calendar Year].[CY 2003],  
            Measures.[Internet Order Quantity]) > 75   
   ) ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France,  
   [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="82621-120">Na consulta anterior, o contexto de cálculo para as células nas tuplas que aparecem no eixo da coluna é filtrado pelo membro CY 2003 da hierarquia de atributo Ano Civil, mesmo se o contexto de cálculo nominal da hierarquia de atributo Ano Civil for CY 2004.</span><span class="sxs-lookup"><span data-stu-id="82621-120">In the previous query, the calculation context for the cells in the tuples that appear on the column axis is filtered by the CY 2003 member of the Calendar Year attribute hierarchy, even though the nominal calculation context for the Calendar Year attribute hierarchy is CY 2004.</span></span> <span data-ttu-id="82621-121">Além disso, o contexto é filtrado pela medida Quantidade de Pedidos pela Internet.</span><span class="sxs-lookup"><span data-stu-id="82621-121">Furthermore, it is filtered by the Internet Order Quantity measure.</span></span> <span data-ttu-id="82621-122">No entanto, assim que os membros do conjunto no eixo da coluna são definidos, o contexto de cálculo dos valores dos membros que aparecem no eixo é novamente determinado pela cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="82621-122">However, once the members of the set on the column axis is set, the calculation context for the values for the members that appear on the axis is again determined by the WHERE clause.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82621-123">Para aprimorar o desempenho da consulta, você deve eliminar membros e tuplas no processo de resolução o quanto antes.</span><span class="sxs-lookup"><span data-stu-id="82621-123">To increase query performance, you should eliminate members and tuples as early in the resolution process as possible.</span></span> <span data-ttu-id="82621-124">Dessa forma, cálculos complexos de tempo de consulta no conjunto final de membros operam com o menor número possível de células.</span><span class="sxs-lookup"><span data-stu-id="82621-124">In this manner, complex query time calculations on the final set of members operate on the fewest cells possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82621-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82621-125">See Also</span></span>  
 <span data-ttu-id="82621-126">[Estabelecendo o contexto de cubo em uma consulta &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="82621-126">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 <span data-ttu-id="82621-127">[Conceitos básicos de consulta MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="82621-127">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="82621-128">Principais conceitos em MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="82621-128">Key Concepts in MDX &#40;Analysis Services&#41;</span></span>](../key-concepts-in-mdx-analysis-services.md)  
  
  
