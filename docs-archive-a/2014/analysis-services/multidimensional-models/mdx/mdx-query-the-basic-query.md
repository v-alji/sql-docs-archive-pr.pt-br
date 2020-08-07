---
title: A consulta MDX básica (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], SELECT statement
- queries [MDX], about queries
- cellsets [MDX]
- SELECT statement [MDX]
- cubes [Analysis Services], SELECT statement
ms.assetid: 4fa5a95a-fec9-4584-875c-dbf030c53e82
author: minewiskan
ms.author: owend
ms.openlocfilehash: b6b1a70753abe8e477bd1e522a37f4513cc12a52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581560"
---
# <a name="the-basic-mdx-query-mdx"></a><span data-ttu-id="b0ffe-102">A consulta básica de MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="b0ffe-102">The Basic MDX Query (MDX)</span></span>
  <span data-ttu-id="b0ffe-103">A consulta MDX (expressões multidimensionais) básicas é a instrução SELECT – a consulta usada com mais frequência em MDX.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-103">The basic Multidimensional Expressions (MDX) query is the SELECT statement-the most frequently used query in MDX.</span></span> <span data-ttu-id="b0ffe-104">Entendendo como a instrução MDX SELECT deve especificar um conjunto de resultados, como é sua sintaxe e como criar uma consulta simples usando a instrução SELECT, você terá uma compreensão sólida de como usar a linguagem MDX para consultar dados multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-104">By understanding how an MDX SELECT statement must specify a result set, what the syntax of the SELECT statement is, and how to create a simple query using the SELECT statement, you will have a solid understanding of how to use MDX to query multidimensional data.</span></span>  
  
## <a name="specifying-a-result-set"></a><span data-ttu-id="b0ffe-105">Especificando um conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="b0ffe-105">Specifying a Result Set</span></span>  
 <span data-ttu-id="b0ffe-106">Na linguagem MDX, a instrução SELECT especifica um conjunto de resultados que contém um subconjunto de dados multidimensionais retornados a partir de um cubo.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-106">In MDX, the SELECT statement specifies a result set that contains a subset of multidimensional data that has been returned from a cube.</span></span> <span data-ttu-id="b0ffe-107">Para especificar um conjunto de resultados, a consulta MDX deve conter as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="b0ffe-107">To specify a result set, an MDX query must contain the following information:</span></span>  
  
-   <span data-ttu-id="b0ffe-108">O número de eixos que você deseja que o conjunto de resultados contenha.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-108">The number of axes that you want the result set to contain.</span></span> <span data-ttu-id="b0ffe-109">É possível especificar até 128 eixos em uma consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-109">You can specify up to 128 axes in an MDX query.</span></span>  
  
-   <span data-ttu-id="b0ffe-110">O conjunto de membros ou tuplas a ser incluído em cada eixo da consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-110">The set of members or tuples to include on each axis of the MDX query.</span></span>  
  
-   <span data-ttu-id="b0ffe-111">O nome do cubo que define o contexto da consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-111">The name of the cube that sets the context of the MDX query.</span></span>  
  
-   <span data-ttu-id="b0ffe-112">O conjunto de membros ou tuplas a ser incluído no eixo da segmentação de dados.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-112">The set of members or tuples to include on the slicer axis.</span></span> <span data-ttu-id="b0ffe-113">Para obter mais informações sobre eixos de consulta e de segmentação de dados, consulte [Restrição à consulta com eixos de consulta e de segmentação de dados &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-113">For more information about slicer and query axes, see[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span></span>  
  
 <span data-ttu-id="b0ffe-114">Para identificar os eixos de consulta, o cubo que será consultado e o eixo da segmentação de dados, a instrução MDX SELECT usa as seguintes cláusulas:</span><span class="sxs-lookup"><span data-stu-id="b0ffe-114">To identify the query axes, the cube that will be queried, and the slicer axis, the MDX SELECT statement uses the following clauses:</span></span>  
  
-   <span data-ttu-id="b0ffe-115">Uma cláusula SELECT que determina os eixos de consulta de uma instrução MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-115">A SELECT clause that determines the query axes of an MDX SELECT statement.</span></span> <span data-ttu-id="b0ffe-116">Para obter mais informações sobre a construção de eixos de consulta em uma cláusula SELECT, consulte [Especificação do conteúdo de um eixo de consulta &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-116">For more information about the construction of query axes in a SELECT clause, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="b0ffe-117">Uma cláusula FROM que determina qual cubo será consultado.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-117">A FROM clause that determines which cube will be queried.</span></span> <span data-ttu-id="b0ffe-118">Para obter mais informações sobre a cláusula FROM, consulte [Instrução SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-118">For more information about the FROM clause, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
-   <span data-ttu-id="b0ffe-119">Uma cláusula WHERE opcional que determina quais membros ou tuplas usar no eixo da segmentação de dados para restringir os dados retornados.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-119">An optional WHERE clause that determines which members or tuples to use on the slicer axis to restrict the data returned.</span></span> <span data-ttu-id="b0ffe-120">Para obter mais informações sobre a construção de eixos de segmentação de dados em uma cláusula WHERE, consulte [Especificação do conteúdo de um eixo de segmentação de dados &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-120">For more information about the construction of a slicer axis in a WHERE clause, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0ffe-121">Para obter informações mais detalhadas sobre as várias cláusulas da instrução SELECT, consulte [Instrução SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-121">For more detailed information about the various clauses of the SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="select-statement-syntax"></a><span data-ttu-id="b0ffe-122">Sintaxe da instrução SELECT</span><span class="sxs-lookup"><span data-stu-id="b0ffe-122">SELECT Statement Syntax</span></span>  
 <span data-ttu-id="b0ffe-123">A sintaxe a seguir mostra uma instrução SELECT básica, incluindo o uso das cláusulas SELECT, FROM e WHERE:</span><span class="sxs-lookup"><span data-stu-id="b0ffe-123">The following syntax shows a basic SELECT statement that includes the use of the SELECT, FROM, and WHERE clauses:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause>   
    [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
```  
  
 <span data-ttu-id="b0ffe-124">A instrução MDX SELECT oferece suporte à sintaxe opcional, como a palavra-chave WITH, ao uso de funções MDX para criar membros calculados para inclusão no eixo ou no eixo da segmentação de dados e à capacidade de retornar os valores das propriedades da célula específica como parte da consulta.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-124">The MDX SELECT statement supports optional syntax, such as the WITH keyword, the use of MDX functions to create calculated members for inclusion in an axis or slicer axis, and the ability to return the values of specific cell properties as part of the query.</span></span> <span data-ttu-id="b0ffe-125">Para obter mais informações sobre a instrução MDX SELECT, consulte [Instrução SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-125">For more information about the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
### <a name="comparing-the-syntax-of-the-mdx-select-statement-to-sql"></a><span data-ttu-id="b0ffe-126">Comparando a sintaxe da instrução MDX SELECT com o SQL</span><span class="sxs-lookup"><span data-stu-id="b0ffe-126">Comparing the Syntax of the MDX SELECT Statement to SQL</span></span>  
 <span data-ttu-id="b0ffe-127">O formato da sintaxe da instrução MDX SELECT é similar à sintaxe do SQL.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-127">The syntax format for the MDX SELECT statement is similar to that of SQL syntax.</span></span> <span data-ttu-id="b0ffe-128">No entanto, há várias diferenças fundamentais:</span><span class="sxs-lookup"><span data-stu-id="b0ffe-128">However, there are several fundamental differences:</span></span>  
  
-   <span data-ttu-id="b0ffe-129">A sintaxe MDX distingue conjuntos ao redor de tuplas ou membros com chaves (os caracteres {e}.) Para obter mais informações sobre membros, tupla e sintaxe SET, consulte [trabalhando com membros, tuplas e conjuntos &#40;&#41;MDX ](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-129">MDX syntax distinguishes sets by surrounding tuples or members with braces (the { and } characters.) For more information about member, tuple, and set syntax, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
-   <span data-ttu-id="b0ffe-130">As consultas MDX têm 0, 1, 2 ou até 128 eixos de consulta na instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-130">MDX queries can have 0, 1, 2 or up to 128 query axes in the SELECT statement.</span></span> <span data-ttu-id="b0ffe-131">Cada eixo se comporta exatamente da mesma maneira, diferentemente do SQL, onde há diferenças significativas entre o comportamento das linhas e das colunas de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-131">Each axis behaves in exactly the same way, unlike SQL where there are significant differences between how the rows and the columns of a query behave.</span></span>  
  
-   <span data-ttu-id="b0ffe-132">Como com uma consulta SQL, a cláusula FROM nomeia a fonte dos dados para a consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-132">As with an SQL query, the FROM clause names the source of the data for the MDX query.</span></span> <span data-ttu-id="b0ffe-133">No entanto, a cláusula MDX FROM é restrita a um único cubo.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-133">However, the MDX FROM clause is restricted to a single cube.</span></span> <span data-ttu-id="b0ffe-134">Informações de outros cubos podem ser recuperadas valor a valor usando a função LookupCube.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-134">Information from other cubes can be retrieved on a value-by-value basis by using the LookupCube function.</span></span>  
  
-   <span data-ttu-id="b0ffe-135">A cláusula WHERE descreve o eixo da segmentação de dados em uma consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-135">The WHERE clause describes the slicer axis in an MDX query.</span></span> <span data-ttu-id="b0ffe-136">Ela atua como um eixo extra, invisível na consulta, segmentando os valores que aparecem nas células do conjunto de resultados; diferentemente da cláusula WHERE do SQL, ela não afeta diretamente o que aparece nos eixos das linhas da consulta.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-136">It acts as something like an invisible, extra axis in the query, slicing the values that appear in the cells in the result set; unlike the SQL WHERE clause it does not directly affect what appears on the rows axis of the query.</span></span> <span data-ttu-id="b0ffe-137">A funcionalidade da cláusula WHERE do SQL está disponível por meio de outras funções MDX, como a função FILTER.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-137">The functionality of the SQL WHERE clause is available through other MDX functions such as the FILTER function.</span></span>  
  
## <a name="select-statement-example"></a><span data-ttu-id="b0ffe-138">Exemplo de instrução SELECT</span><span class="sxs-lookup"><span data-stu-id="b0ffe-138">SELECT Statement Example</span></span>  
 <span data-ttu-id="b0ffe-139">O exemplo a seguir mostra uma consulta MDX básica que usa a instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-139">The following example shows a basic MDX query that uses the SELECT statement.</span></span> <span data-ttu-id="b0ffe-140">Ela retorna um conjunto de resultados que contém os valores de vendas e tributos de 2002 e 2003 da região sudoeste.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-140">This query returns a result set that contains the 2002 and 2003 sales and tax amounts for the Southwest sales territories.</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON COLUMNS,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON ROWS  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="b0ffe-141">Neste exemplo, a consulta define as seguintes informações do conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="b0ffe-141">In this example, the query defines the following result set information:</span></span>  
  
-   <span data-ttu-id="b0ffe-142">A cláusula SELECT define os eixos da consulta como os membros Valor de Vendas e Valor de Tributos da dimensão Medidas e os membros 2002 e 2003 da dimensão Data.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-142">The SELECT clause sets the query axes as the Sales Amount and Tax Amount members of the Measures dimension, and the 2002 and 2003 members of the Date dimension.</span></span>  
  
-   <span data-ttu-id="b0ffe-143">A cláusula FROM indica que a fonte de dados é o cubo Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-143">The FROM clause indicates that the data source is the Adventure Works cube.</span></span>  
  
-   <span data-ttu-id="b0ffe-144">A cláusula WHERE define o eixo do slicer como o membro Sudoeste da dimensão Região de vendas.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-144">The WHERE clause defines the slicer axis as the Southwest member of the Sales Territory dimension.</span></span>  
  
 <span data-ttu-id="b0ffe-145">Observe que o exemplo de consulta também usa os aliases de eixo COLUMNS e ROWS.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-145">Notice that the query example also uses the COLUMNS and ROWS axis aliases.</span></span> <span data-ttu-id="b0ffe-146">As posições ordinais desses eixos também poderiam ser usadas.</span><span class="sxs-lookup"><span data-stu-id="b0ffe-146">The ordinal positions for these axes could also have been used.</span></span> <span data-ttu-id="b0ffe-147">O exemplo a seguir mostra como a consulta MDX poderia ter sido escrita para usar a posição ordinal de cada eixo:</span><span class="sxs-lookup"><span data-stu-id="b0ffe-147">The following example shows how the MDX query could have been written to use the ordinal position of each axis:</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON 0,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON 1  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="b0ffe-148">Para obter exemplos mais detalhados, consulte [Especificação do conteúdo de um eixo de consulta &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)e [Especificação do conteúdo de um eixo de segmentação de dados &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="b0ffe-148">For more detailed examples, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)and [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ffe-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0ffe-149">See Also</span></span>  
 <span data-ttu-id="b0ffe-150">[Conceitos principais em MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="b0ffe-150">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 [<span data-ttu-id="b0ffe-151">Instrução SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b0ffe-151">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
