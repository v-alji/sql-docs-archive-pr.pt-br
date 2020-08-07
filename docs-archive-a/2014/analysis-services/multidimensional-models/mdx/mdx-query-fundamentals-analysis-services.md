---
title: Conceitos básicos de consulta MDX (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- statements [MDX]
- Multidimensional Expressions [Analysis Services], statements
- Multidimensional Expressions [Analysis Services], queries
- MDX [Analysis Services], statements
- MDX queries [Analysis Services]
- MDX [Analysis Services], queries
- queries [MDX]
ms.assetid: a560383b-bb58-472e-95f5-65d03d8ea08b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a2a9a4f564bc33cc7a1b41a1a4c766c7a76a2cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581561"
---
# <a name="mdx-query-fundamentals-analysis-services"></a><span data-ttu-id="68b7c-102">Conceitos básicos de consulta MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="68b7c-102">MDX Query Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="68b7c-103">O MDX (Multidimensional Expressions) permite que você consulte objetos multidimensionais, como cubos, e retorna conjuntos de células multidimensionais que contêm dados do cubo.</span><span class="sxs-lookup"><span data-stu-id="68b7c-103">Multidimensional Expressions (MDX) lets you query multidimensional objects, such as cubes, and return multidimensional cellsets that contain the cube's data.</span></span> <span data-ttu-id="68b7c-104">Este tópico e respectivos subtópicos fornecem uma visão geral das consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="68b7c-104">This topic and its subtopics provide an overview of MDX queries.</span></span>  
  
 <span data-ttu-id="68b7c-105">Os tópicos a seguir descrevem consultas MDX e os conjuntos de células que elas produzem, e fornecem informações mais detalhadas sobre a sintaxe básica de MDX.</span><span class="sxs-lookup"><span data-stu-id="68b7c-105">The following topics describe MDX queries and the cellsets they produce, and provide more detailed information about basic MDX syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68b7c-106">Para obter mais informações sobre problemas de desempenho relacionados a cálculos e consultas MDX, consulte a seção "escrevendo MDX eficiente" no [Guia de desempenho do SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="68b7c-106">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68b7c-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="68b7c-107">In This Section</span></span>  
  
|<span data-ttu-id="68b7c-108">Tópico</span><span class="sxs-lookup"><span data-stu-id="68b7c-108">Topic</span></span>|<span data-ttu-id="68b7c-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="68b7c-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="68b7c-110">A consulta básica de MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-110">The Basic MDX Query &#40;MDX&#41;</span></span>](mdx-query-the-basic-query.md)|<span data-ttu-id="68b7c-111">Fornece informações de sintaxe básica para a instrução MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="68b7c-111">Provides basic syntax information for the MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="68b7c-112">Restringindo a consulta com os eixos de consulta e segmentação &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-112">Restricting the Query with Query and Slicer Axes &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-restricting-the-query.md)|<span data-ttu-id="68b7c-113">Descreve o que são eixos de consulta e slicer e como os especificá-los.</span><span class="sxs-lookup"><span data-stu-id="68b7c-113">Describes what query and slicer axes are and how to specify them.</span></span>|  
|[<span data-ttu-id="68b7c-114">Estabelecendo o contexto de cubo em uma consulta &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-114">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)|<span data-ttu-id="68b7c-115">Fornece uma descrição sobre a finalidade da cláusula FROM em uma instrução MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="68b7c-115">Provides a description of the purpose of the FROM clause in an MDX SELECT statement.</span></span>|  
|[<span data-ttu-id="68b7c-116">Criando conjuntos nomeados em MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-116">Building Named Sets in MDX &#40;MDX&#41;</span></span>](mdx-named-sets-building-named-sets.md)|<span data-ttu-id="68b7c-117">Descreve a finalidade de conjuntos nomeados em MDX e as técnicas necessárias para criá-los e usá-los em consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="68b7c-117">Describes the purpose of named sets in MDX, and the techniques needed to create and use them in MDX queries.</span></span>|  
|[<span data-ttu-id="68b7c-118">Criando membros calculados em MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-118">Building Calculated Members in MDX &#40;MDX&#41;</span></span>](mdx-calculated-members-building-calculated-members.md)|<span data-ttu-id="68b7c-119">Fornece informações sobre membros calculados em MDX, incluindo as técnicas necessárias para criá-los e usá-los em expressões MDX.</span><span class="sxs-lookup"><span data-stu-id="68b7c-119">Provides information about calculated members in MDX, including the techniques needed to create and use them in MDX expressions.</span></span>|  
|[<span data-ttu-id="68b7c-120">Criando cálculos de célula em MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-120">Building Cell Calculations in MDX &#40;MDX&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/calculations.md)|<span data-ttu-id="68b7c-121">Detalha o processo de criação e utilização de células calculadas.</span><span class="sxs-lookup"><span data-stu-id="68b7c-121">Details the process of creating and using calculated cells.</span></span>|  
|[<span data-ttu-id="68b7c-122">Criando e usando valores de propriedade &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-122">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)|<span data-ttu-id="68b7c-123">Detalha o processo de criação e utilização de dimensão, nível, membro e propriedades de célula.</span><span class="sxs-lookup"><span data-stu-id="68b7c-123">Details the process of creating and using dimension, level, member, and cell properties.</span></span>|  
|[<span data-ttu-id="68b7c-124">Manipulando dados &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-124">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)|<span data-ttu-id="68b7c-125">Descreve os fundamentos inerentes da manipulação de dados usando o detalhamento e a representação acumulada, e também descreve a ordem de passagem e a ordem de resolução no MDX.</span><span class="sxs-lookup"><span data-stu-id="68b7c-125">Describes the basics behind manipulating data using drillthrough and rollup, and also describes pass order and solve order in MDX.</span></span>|  
|[<span data-ttu-id="68b7c-126">Modificando dados &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-126">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)|<span data-ttu-id="68b7c-127">Descreve como usar write-backs para alterar temporária ou permanentemente os dados multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="68b7c-127">Describes how to use writebacks to temporarily or permanently change multidimensional data.</span></span>|  
|[<span data-ttu-id="68b7c-128">Usando variáveis e parâmetros &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-128">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="68b7c-129">Descreve como utilizar variáveis e parâmetros em consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="68b7c-129">Describes how to use variables and parameters within MDX queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68b7c-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68b7c-130">See Also</span></span>  
 [<span data-ttu-id="68b7c-131">Referência de expressões multidimensionais &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="68b7c-131">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
