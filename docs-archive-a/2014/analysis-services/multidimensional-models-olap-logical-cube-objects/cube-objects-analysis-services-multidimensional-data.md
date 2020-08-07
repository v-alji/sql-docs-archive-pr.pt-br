---
title: Objetos de cubo (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], objects
ms.assetid: 5cee362e-3f95-4467-bc6c-29b1518ecbf3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0e6dfb75be696ab26893e668b99dc36c7340f86c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574945"
---
# <a name="cube-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="dfa44-102">Objetos cubo (Analysis Services – Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="dfa44-102">Cube Objects (Analysis Services - Multidimensional Data)</span></span>
    
## <a name="introducing-cube-objects"></a><span data-ttu-id="dfa44-103">Apresentando objetos cubo</span><span class="sxs-lookup"><span data-stu-id="dfa44-103">Introducing Cube Objects</span></span>  
 <span data-ttu-id="dfa44-104">Um simples objeto <xref:Microsoft.AnalysisServices.Cube> é composto de: informações básicas, dimensões e grupos de medidas.</span><span class="sxs-lookup"><span data-stu-id="dfa44-104">A simple <xref:Microsoft.AnalysisServices.Cube> object is composed of: basic information, dimensions, and measure groups.</span></span> <span data-ttu-id="dfa44-105">As informações básicas incluem o nome do cubo, a medida padrão do cubo, a fonte de dados, o modo de armazenamento e outros.</span><span class="sxs-lookup"><span data-stu-id="dfa44-105">Basic information includes the name of the cube, the default measure of the cube, the data source, the storage mode, and others.</span></span>  
  
 <span data-ttu-id="dfa44-106">A coleção Dimensões contém o conjunto real de dimensões usado no cubo da coleção de dimensões de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dfa44-106">The Dimensions collection contains the actual set of dimensions used in the cube from the database dimensions colection.</span></span> <span data-ttu-id="dfa44-107">Todas as dimensões precisam ser definidas na coleção de dimensões do banco de dados antes de serem referenciadas no cubo.</span><span class="sxs-lookup"><span data-stu-id="dfa44-107">All dimensions have to be defined in the dimensions collection of the database before being referenced in the cube.</span></span> <span data-ttu-id="dfa44-108">As dimensões privadas não estão disponíveis no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dfa44-108">Private dimensions are not available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dfa44-109">Os grupos de medidas são conjuntos de medidas no cubo.</span><span class="sxs-lookup"><span data-stu-id="dfa44-109">Measure groups are sets of measures in the cube.</span></span> <span data-ttu-id="dfa44-110">Um grupo de medidas é uma coleção de medidas que têm uma fonte de dados e um conjunto de dimensões em comum.</span><span class="sxs-lookup"><span data-stu-id="dfa44-110">A measure group is a collection of measures that have a common data source view and a common set of dimensions.</span></span> <span data-ttu-id="dfa44-111">Um grupo de medidas é a unidade de processo para medidas; grupos de medidas podem ser processados individualmente e, em seguida, pesquisados.</span><span class="sxs-lookup"><span data-stu-id="dfa44-111">A measure group is the unit of process for measures; measure groups can be processed individually and then browsed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dfa44-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="dfa44-112">In this section</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dfa44-113">Tópico</span><span class="sxs-lookup"><span data-stu-id="dfa44-113">Topic</span></span>||  
|[<span data-ttu-id="dfa44-114">Ações &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="dfa44-114">Actions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models/actions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="dfa44-115">Agregações e designs de agregação</span><span class="sxs-lookup"><span data-stu-id="dfa44-115">Aggregations and Aggregation Designs</span></span>](aggregations-and-aggregation-designs.md)||  
|[<span data-ttu-id="dfa44-116">Cálculos</span><span class="sxs-lookup"><span data-stu-id="dfa44-116">Calculations</span></span>](calculations.md)||  
|[<span data-ttu-id="dfa44-117">As células de cubo &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="dfa44-117">Cube Cells &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-cells-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="dfa44-118">Propriedades do cubo</span><span class="sxs-lookup"><span data-stu-id="dfa44-118">Cube Properties</span></span>](cube-properties-multidimensional-model-programming.md)||  
|[<span data-ttu-id="dfa44-119">&#40;de armazenamento de cubos Analysis Services dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="dfa44-119">Cube Storage &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-storage-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="dfa44-120">Traduções de cubo</span><span class="sxs-lookup"><span data-stu-id="dfa44-120">Cube Translations</span></span>](cube-translations.md)||  
|[<span data-ttu-id="dfa44-121">Relações de dimensão</span><span class="sxs-lookup"><span data-stu-id="dfa44-121">Dimension Relationships</span></span>](dimension-relationships.md)||  
|[<span data-ttu-id="dfa44-122">Indicadores Chave de Desempenho &#40;KPIs&#41; em Modelos Multidimensionais</span><span class="sxs-lookup"><span data-stu-id="dfa44-122">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](../multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)||  
|[<span data-ttu-id="dfa44-123">Medidas e Grupos de Medidas</span><span class="sxs-lookup"><span data-stu-id="dfa44-123">Measures and Measure Groups</span></span>](../multidimensional-models/measures-and-measure-groups.md)||  
|[<span data-ttu-id="dfa44-124">Partições &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="dfa44-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partitions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="dfa44-125">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="dfa44-125">Perspectives</span></span>](perspectives.md)||  
  
  
