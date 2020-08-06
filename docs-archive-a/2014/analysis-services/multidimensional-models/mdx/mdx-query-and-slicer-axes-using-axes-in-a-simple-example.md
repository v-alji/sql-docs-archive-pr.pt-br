---
title: Usando eixos de consulta e de segmentação em um exemplo simples (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- query axis [MDX]
ms.assetid: 85bcb26f-5971-4153-b334-61f8d8b475b5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 324f082fd6659592e56af65680bd4aa623c625d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576031"
---
# <a name="using-query-and-slicer-axes-in-a-simple-example-mdx"></a><span data-ttu-id="2258c-102">Usando eixos de consulta e slicer em um exemplo simples (MDX)</span><span class="sxs-lookup"><span data-stu-id="2258c-102">Using Query and Slicer Axes in a Simple Example (MDX)</span></span>
  <span data-ttu-id="2258c-103">O exemplo simples apresentado neste tópico ilustra os fundamentos de como especificar e usar eixos de consulta e slicer.</span><span class="sxs-lookup"><span data-stu-id="2258c-103">The simple example presented in this topic illustrates the basics of specifying and using query and slicer axes.</span></span>  
  
## <a name="the-cube"></a><span data-ttu-id="2258c-104">O cubo</span><span class="sxs-lookup"><span data-stu-id="2258c-104">The Cube</span></span>  
 <span data-ttu-id="2258c-105">Um cubo, chamado CuboTeste, possui duas dimensões simples nomeadas Rota e Tempo.</span><span class="sxs-lookup"><span data-stu-id="2258c-105">A cube, named TestCube, has two simple dimensions named Route and Time.</span></span> <span data-ttu-id="2258c-106">Cada dimensão tem apenas uma hierarquia de usuário, chamadas respectivamente Rota e Tempo.</span><span class="sxs-lookup"><span data-stu-id="2258c-106">Each dimension has only one user hierarchy, named Route and Time respectively.</span></span> <span data-ttu-id="2258c-107">Como as medidas do cubo fazem parte da dimensão Medidas, esse cubo possui três dimensões no total.</span><span class="sxs-lookup"><span data-stu-id="2258c-107">Because the measures of the cube are part of the Measures dimension, this cube has three dimensions in all.</span></span>  
  
## <a name="the-query"></a><span data-ttu-id="2258c-108">A consulta</span><span class="sxs-lookup"><span data-stu-id="2258c-108">The Query</span></span>  
 <span data-ttu-id="2258c-109">A consulta serve para fornecer uma matriz com a qual a medida Pacotes pode ser comparada por rotas e horas.</span><span class="sxs-lookup"><span data-stu-id="2258c-109">The query is to provide a matrix in which the Packages measure can be compared across routes and times.</span></span>  
  
 <span data-ttu-id="2258c-110">No exemplo de consulta MDX a seguir, as hierarquias Rota e Tempo são os eixos de consulta e a dimensão Medidas é o eixo de slicer.</span><span class="sxs-lookup"><span data-stu-id="2258c-110">In the following MDX query example, the Route and Time hierarchies are the query axes, and the Measures dimension is the slicer axis.</span></span> <span data-ttu-id="2258c-111">A função [Members](/sql/mdx/members-set-mdx) indica que a linguagem MDX usará os membros da hierarquia ou do nível para construir um conjunto.</span><span class="sxs-lookup"><span data-stu-id="2258c-111">The [Members](/sql/mdx/members-set-mdx) function indicates that MDX will use the members of the hierarchy or level to construct a set.</span></span> <span data-ttu-id="2258c-112">O uso da função `Members` significa que você não terá que declarar explicitamente cada membro de uma hierarquia específica ou um nível em uma consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="2258c-112">The use of the `Members` function means that you do not have to explicitly state each member of a specific hierarchy or level in an MDX query.</span></span>  
  
```  
SELECT  
   { Route.nonground.Members } ON COLUMNS,  
   { Time.[1st half].Members } ON ROWS  
FROM TestCube  
WHERE ( [Measures].[Packages] )  
```  
  
## <a name="the-results"></a><span data-ttu-id="2258c-113">O resultado</span><span class="sxs-lookup"><span data-stu-id="2258c-113">The Results</span></span>  
 <span data-ttu-id="2258c-114">O resultado é uma grade que identifica o valor da medida Pacotes em cada intersecção das dimensões de eixo COLUMNS e ROWS.</span><span class="sxs-lookup"><span data-stu-id="2258c-114">The result is a grid that identifies the value of the Packages measure at each intersection of the COLUMNS and ROWS axis dimensions.</span></span> <span data-ttu-id="2258c-115">A tabela a seguir mostra como seria essa grade.</span><span class="sxs-lookup"><span data-stu-id="2258c-115">The following table shows how this grid would look.</span></span>  
  
||<span data-ttu-id="2258c-116">aérea</span><span class="sxs-lookup"><span data-stu-id="2258c-116">air</span></span>|<span data-ttu-id="2258c-117">marítima</span><span class="sxs-lookup"><span data-stu-id="2258c-117">sea</span></span>|  
|-|---------|---------|  
|<span data-ttu-id="2258c-118">1º trimestre</span><span class="sxs-lookup"><span data-stu-id="2258c-118">1st quarter</span></span>|<span data-ttu-id="2258c-119">60</span><span class="sxs-lookup"><span data-stu-id="2258c-119">60</span></span>|<span data-ttu-id="2258c-120">50</span><span class="sxs-lookup"><span data-stu-id="2258c-120">50</span></span>|  
|<span data-ttu-id="2258c-121">2º trimestre</span><span class="sxs-lookup"><span data-stu-id="2258c-121">2nd quarter</span></span>|<span data-ttu-id="2258c-122">45</span><span class="sxs-lookup"><span data-stu-id="2258c-122">45</span></span>|<span data-ttu-id="2258c-123">45</span><span class="sxs-lookup"><span data-stu-id="2258c-123">45</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2258c-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2258c-124">See Also</span></span>  
 <span data-ttu-id="2258c-125">[Especificando o conteúdo de um eixo de consulta &#40;&#41;MDX](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span><span class="sxs-lookup"><span data-stu-id="2258c-125">[Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span></span>  
 [<span data-ttu-id="2258c-126">Especificando o conteúdo de um eixo da segmentação &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="2258c-126">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
