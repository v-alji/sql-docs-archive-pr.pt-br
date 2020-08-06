---
title: Especificando o conteúdo de um eixo de segmentação (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- filtering data [MDX]
ms.assetid: c56b0a70-cdec-427f-990e-425290344e7d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8620c54970ea14a2ac01c85262a372d2b3db0d68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679055"
---
# <a name="specifying-the-contents-of-a-slicer-axis-mdx"></a><span data-ttu-id="e7fb7-102">Especificando o conteúdo de um eixo do slicer (MDX)</span><span class="sxs-lookup"><span data-stu-id="e7fb7-102">Specifying the Contents of a Slicer Axis (MDX)</span></span>
  <span data-ttu-id="e7fb7-103">O eixo de slicer filtra os dados retornados pela instrução MDX SELECT, restringindo os dados retornados para que somente os dados da intersecção com os membros especificados sejam retornados.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-103">The slicer axis filters the data returned by the Multidimensional Expressions (MDX) SELECT statement, restricting the returned data so that only data intersecting with the specified members will be returned.</span></span> <span data-ttu-id="e7fb7-104">Pode ser considerado como um eixo adicional invisível em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-104">It can be thought of as an invisible extra axis in a query.</span></span> <span data-ttu-id="e7fb7-105">O eixo de slicer é definido na cláusula WHERE da instrução MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-105">The slicer axis is defined in the WHERE clause of the SELECT statement in MDX.</span></span>  
  
## <a name="slicer-axis-syntax"></a><span data-ttu-id="e7fb7-106">Sintaxe de eixo de slicer</span><span class="sxs-lookup"><span data-stu-id="e7fb7-106">Slicer Axis Syntax</span></span>  
 <span data-ttu-id="e7fb7-107">Para especificar um eixo de slicer explicitamente, use a `<SELECT slicer axis clause>` no formato MDX, como descrita na sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="e7fb7-107">To explicitly specify a slicer axis, you  using the `<SELECT slicer axis clause>` in MDX, as described in the following syntax:</span></span>  
  
```  
<SELECT slicer axis clause> ::=  WHERE Set_Expression  
```  
  
 <span data-ttu-id="e7fb7-108">Na sintaxe do eixo de slicer mostrada, `Set_Expression` pode assumir a expressão de tupla, que é tratada como um conjunto para a avaliação ou como uma expressão de conjunto.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-108">In the slicer axis syntax shown, `Set_Expression` can take either a tuple expression, which is treated as a set for the purposes of evaluating the clause, or a set expression.</span></span> <span data-ttu-id="e7fb7-109">Se for especificada uma expressão de conjunto, a linguagem MDX tentará avaliar o conjunto, agregando as células de resultado a cada tupla do conjunto.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-109">If a set expression is specified, MDX will try to evaluate the set, aggregating the result cells in every tuple along the set.</span></span> <span data-ttu-id="e7fb7-110">Em outras palavras, a linguagem MDX tentará usar a função [Aggregate](/sql/mdx/aggregate-mdx) no conjunto, agregando cada medida pela sua função de agregação associada.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-110">In other words, MDX will try to use the [Aggregate](/sql/mdx/aggregate-mdx) function on the set, aggregating each measure by its associated aggregation function.</span></span> <span data-ttu-id="e7fb7-111">Além disso, se a expressão de conjunto não puder ser expressa como uma interjunção dos membros da hierarquia do atributo, a linguagem MDX tratará as células que ficarem fora da expressão de conjunto do slicer como nulas para a avaliação.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-111">Also, if the set expression cannot be expressed as a crossjoin of attribute hierarchy members, MDX treats cells that fall outside of the set expression for the slicer as null for evaluation purposes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e7fb7-112">Diferente da cláusula WHERE no SQL, a cláusula WHERE em uma instrução MDX SELECT nunca filtra diretamente o que é retornado no eixo Linhas de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-112">Unlike the WHERE clause in SQL, the WHERE clause of an MDX SELECT statement never directly filters what is returned on the Rows axis of a query.</span></span> <span data-ttu-id="e7fb7-113">Para filtrar o que aparece no eixo Linhas ou Colunas de uma consulta, você pode usar diversas funções MDX, como, por exemplo, FILTER, NONEMPTY e TOPCOUNT.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-113">To filter what appears on the Rows or Columns axis of a query, you can use a variety of MDX functions, for example FILTER, NONEMPTY and TOPCOUNT.</span></span>  
  
### <a name="implicit-slicer-axis"></a><span data-ttu-id="e7fb7-114">Eixo de slicer implícito</span><span class="sxs-lookup"><span data-stu-id="e7fb7-114">Implicit Slicer Axis</span></span>  
 <span data-ttu-id="e7fb7-115">Se um membro de uma hierarquia do cubo não for explicitamente incluído em um eixo de consulta, o membro padrão dessa hierarquia será incluído implicitamente no eixo de slicer.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-115">If a member from a hierarchy within the cube is not explicitly included in a query axis, the default member from that hierarchy is implicitly included in the slicer axis.</span></span> <span data-ttu-id="e7fb7-116">Para obter mais informações sobre membros padrão, consulte [Definir um membro padrão](../attribute-properties-define-a-default-member.md).</span><span class="sxs-lookup"><span data-stu-id="e7fb7-116">For more information about default members, see [Define a Default Member](../attribute-properties-define-a-default-member.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e7fb7-117">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e7fb7-117">Examples</span></span>  
 <span data-ttu-id="e7fb7-118">A seguinte consulta não inclui uma cláusula WHERE e retorna o valor da medida Quantidade de Vendas pela Internet todos os Anos Civis:</span><span class="sxs-lookup"><span data-stu-id="e7fb7-118">The following query does not include a WHERE clause, and returns the value of the Internet Sales Amount measure for all Calendar Years:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="e7fb7-119">Veja como adicionar uma cláusula WHERE:</span><span class="sxs-lookup"><span data-stu-id="e7fb7-119">Adding a WHERE clause, as follows:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States])  
  
```  
  
 <span data-ttu-id="e7fb7-120">não altera o que é retornado em Linhas ou Colunas na consulta; altera os valores retornados para cada célula.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-120">does not change what is returned on Rows or Columns in the query; it changes the values returned for each cell.</span></span> <span data-ttu-id="e7fb7-121">Neste exemplo, a consulta é fatiada de forma que isso retorne o valor de Quantidade de Vendas pela Internet durante todos os Anos Civis, mas só para Clientes que moram nos Estados Unidos. Vários membros de hierarquias diferentes podem ser acrescentados à cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-121">In this example, the query is sliced so that it returns the value of Internet Sales Amount for all Calendar Years but only for Customers who live in the United States.Multiple members from different hierarchies can be added to the WHERE clause.</span></span> <span data-ttu-id="e7fb7-122">A seguinte consulta mostra o valor de Quantidade de Vendas pela Internet durante todos os Anos Civis para Clientes que moram nos Estados Unidos e que compraram Produtos na Categoria Bicicletas:</span><span class="sxs-lookup"><span data-stu-id="e7fb7-122">The following query shows the value of Internet Sales Amount for all Calendar Years for Customers who live in the United States and who bought Products in the Category Bikes:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE([Customer].[Customer Geography].[Country].&[United States], [Product].[Category].&[1])  
```  
  
 <span data-ttu-id="e7fb7-123">Se você desejar usar vários membros da mesma hierarquia, precisará incluir um conjunto na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-123">If you want to use multiple members from the same hierarchy, you need to include a set in the WHERE clause.</span></span> <span data-ttu-id="e7fb7-124">Por exemplo, a seguinte consulta mostra o valor da Quantidade de Vendas pela Internet durante todos os Anos Civis para Clientes que compraram Produtos na Categoria Bicicletas e moram nos Estados Unidos ou no Reino Unido:</span><span class="sxs-lookup"><span data-stu-id="e7fb7-124">For example, the following query shows the value of Internet Sales Amount for all Calendar Years for Customers who bought Products in the Category Bikes and live in either the United States or the United Kingdom:</span></span>  
  
```  
SELECT {[Measures].[Internet Sales Amount]} ON COLUMNS,  
[Date].[Calendar Year].MEMBERS ON ROWS  
FROM [Adventure Works]  
WHERE(  
{[Customer].[Customer Geography].[Country].&[United States]  
, [Customer].[Customer Geography].[Country].&[United Kingdom]}  
, [Product].[Category].&[1])  
  
```  
  
 <span data-ttu-id="e7fb7-125">Como mencionado antes, o uso de um conjunto na cláusula WHERE implicitamente agregará valores a todos os membros do conjunto.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-125">As mentioned above, using a set in the WHERE clause will implicitly aggregate values for all members in the set.</span></span> <span data-ttu-id="e7fb7-126">Nesse caso, a consulta mostra valores agregados para os Estados Unidos e o Reino Unido em cada célula.</span><span class="sxs-lookup"><span data-stu-id="e7fb7-126">In this case, the query shows aggregated values for the United States and the United Kingdom in each cell.</span></span>  
  
  
