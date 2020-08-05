---
title: Manipulando dados (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], data manipulation
- data manipulation [MDX]
- Multidimensional Expressions [Analysis Services], data manipulation
ms.assetid: 4865192e-f46b-4ce5-b51c-9e08dbad5b85
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a1de8b9a3431d79573cd916fa7273b6d8fa7f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574364"
---
# <a name="manipulating-data-mdx"></a><span data-ttu-id="984cb-102">Manipulando dados (MDX)</span><span class="sxs-lookup"><span data-stu-id="984cb-102">Manipulating Data (MDX)</span></span>

<span data-ttu-id="984cb-103">As expressões multidimensionais (MDX) podem ser usadas para manipular os dados de várias formas.</span><span class="sxs-lookup"><span data-stu-id="984cb-103">Multidimensional Expressions (MDX) can be used to manipulate the data in a variety of ways.</span></span> <span data-ttu-id="984cb-104">O artigo listado neste artigo aborda alguns dos conceitos mais avançados de manipulação de dados na linguagem MDX.</span><span class="sxs-lookup"><span data-stu-id="984cb-104">The article listed in this article cover some of the more advanced concepts of data manipulation in the MDX language.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="984cb-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="984cb-105">In This Section</span></span>

|<span data-ttu-id="984cb-106">Tópico</span><span class="sxs-lookup"><span data-stu-id="984cb-106">Topic</span></span>|<span data-ttu-id="984cb-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="984cb-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="984cb-108">Como usar DRILLTHROUGH para recuperar os dados de origem&#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="984cb-108">Using DRILLTHROUGH to Retrieve Source Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-retrieve-source-data-using-drillthrough.md)|<span data-ttu-id="984cb-109">Discute o uso da instrução MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) para recuperar os conjuntos de linhas dos dados de origem aplicáveis a uma célula de uma fonte de dados multidimensional.</span><span class="sxs-lookup"><span data-stu-id="984cb-109">Discusses the use of the MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) statement to retrieve the rowsets of source data applicable to a cell in a multidimensional data source</span></span>|  
|[<span data-ttu-id="984cb-110">Como trabalhar com a função RollupChildren &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="984cb-110">Working with the RollupChildren Function &#40;MDX&#41;</span></span>](mdx-data-manipulation-rollupchildren-function.md)|<span data-ttu-id="984cb-111">Discute o impacto do MDX [RollupChildren](/sql/mdx/rollupchildren-mdx)</span><span class="sxs-lookup"><span data-stu-id="984cb-111">Discusses the impact of the MDX [RollupChildren](/sql/mdx/rollupchildren-mdx)</span></span>
|[<span data-ttu-id="984cb-112">Noções básicas sobre a ordem de passagem e a ordem de resolução &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="984cb-112">Understanding Pass Order and Solve Order &#40;MDX&#41;</span></span>](mdx-data-manipulation-understanding-pass-order-and-solve-order.md)|<span data-ttu-id="984cb-113">Detalha os conceitos da ordem de resolução e como esse recurso afeta expressões, instruções e scripts MDX.</span><span class="sxs-lookup"><span data-stu-id="984cb-113">Details the concepts of solve order, and how this feature affects MDX expressions, statements, and scripts.</span></span>|  

<!-- ??

|[Script for Search and Replace] function on the analysis of multidimensional data.|

GeneMi is removing this commented row because it is unclear what article its link meant to link to.
Also, I had to add its leading '|' character, for consistency to aid bulk automated updated to our markdown source code.

GeneMi , 2019/01/19
-->

## <a name="see-also"></a><span data-ttu-id="984cb-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="984cb-114">See Also</span></span>

[<span data-ttu-id="984cb-115">Conceitos básicos de consulta MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="984cb-115">MDX Query Fundamentals (Analysis Services)</span></span>](mdx-query-fundamentals-analysis-services.md)
