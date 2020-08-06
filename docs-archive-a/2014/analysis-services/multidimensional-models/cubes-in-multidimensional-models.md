---
title: Cubos em modelos multidimensionais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OLAP objects [Analysis Services], cubes
- cubes [Analysis Services], about cubes
- cubes [Analysis Services]
- OLAP [Analysis Services], cubes
ms.assetid: e0f7acf3-4b07-41fc-a5fc-ac30b4a56c54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 372bb8075b232ff8fbf8a54facf9bc065e6763a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685355"
---
# <a name="cubes-in-multidimensional-models"></a><span data-ttu-id="74e26-102">Cubos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-102">Cubes in Multidimensional Models</span></span>
  <span data-ttu-id="74e26-103">Um cubo é uma estrutura multidimensional que contém informações para fins analíticos; os principais elementos constituintes de um cubo são dimensões e medidas.</span><span class="sxs-lookup"><span data-stu-id="74e26-103">A cube is a multidimensional structure that contains information for analytical purposes; the main constituents of a cube are dimensions and measures.</span></span> <span data-ttu-id="74e26-104">As dimensões definem a estrutura do cubo que você usa para fazer divisões, e as medidas fornecem valores numéricos agregados de interesse do usuário final.</span><span class="sxs-lookup"><span data-stu-id="74e26-104">Dimensions define the structure of the cube that you use to slice and dice over, and measures provide aggregated numerical values of interest to the end user.</span></span> <span data-ttu-id="74e26-105">Como é uma estrutura lógica, um cubo permite a um aplicativo cliente recuperar valores, de medidas, como se estivessem contidos em células no cubo; as células são definidas para cada valor resumido possível.</span><span class="sxs-lookup"><span data-stu-id="74e26-105">As a logical structure, a cube allows a client application to retrieve values, of measures, as if they were contained in cells in the cube; cells are defined for every possible summarized value.</span></span> <span data-ttu-id="74e26-106">Uma célula, no cubo, é definida pela interseção de membros de dimensão e contém os valores agregados das medidas nessa interseção específica.</span><span class="sxs-lookup"><span data-stu-id="74e26-106">A cell, in the cube, is defined by the intersection of dimension members and contains the aggregated values of the measures at that specific intersection.</span></span>  
  
## <a name="benefits-of-using-cubes"></a><span data-ttu-id="74e26-107">Benefícios do uso de cubos</span><span class="sxs-lookup"><span data-stu-id="74e26-107">Benefits of Using Cubes</span></span>  
 <span data-ttu-id="74e26-108">Um cubo oferece um único local onde todos os dados relacionados são armazenados para análise.</span><span class="sxs-lookup"><span data-stu-id="74e26-108">A cube provides a single place where all related data, for analysis, is stored.</span></span>  
  
## <a name="components-of-cubes"></a><span data-ttu-id="74e26-109">Componentes de cubos</span><span class="sxs-lookup"><span data-stu-id="74e26-109">Components of Cubes</span></span>  
 <span data-ttu-id="74e26-110">Um cubo é constituído de:</span><span class="sxs-lookup"><span data-stu-id="74e26-110">A cube is composed of:</span></span>  
  
|<span data-ttu-id="74e26-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="74e26-111">Element</span></span>|<span data-ttu-id="74e26-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="74e26-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74e26-113">Dimensões</span><span class="sxs-lookup"><span data-stu-id="74e26-113">Dimensions</span></span>|[<span data-ttu-id="74e26-114">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-114">Dimensions in Multidimensional Models</span></span>](dimensions-in-multidimensional-models.md)|  
|<span data-ttu-id="74e26-115">Medidas e Grupos de Medidas</span><span class="sxs-lookup"><span data-stu-id="74e26-115">Measures and Measure Groups</span></span>|[<span data-ttu-id="74e26-116">Criar medidas e grupos de medidas em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-116">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|  
|<span data-ttu-id="74e26-117">Partições</span><span class="sxs-lookup"><span data-stu-id="74e26-117">Partitions</span></span>|[<span data-ttu-id="74e26-118">Partições em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-118">Partitions in Multidimensional Models</span></span>](partitions-in-multidimensional-models.md)|  
|<span data-ttu-id="74e26-119">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="74e26-119">Perspectives</span></span>|[<span data-ttu-id="74e26-120">Perspectivas em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-120">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|  
|<span data-ttu-id="74e26-121">Hierarquias</span><span class="sxs-lookup"><span data-stu-id="74e26-121">Hierarchies</span></span>|[<span data-ttu-id="74e26-122">Criar hierarquias definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="74e26-122">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)|  
|<span data-ttu-id="74e26-123">Ações</span><span class="sxs-lookup"><span data-stu-id="74e26-123">Actions</span></span>|[<span data-ttu-id="74e26-124">Ações em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-124">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|  
|<span data-ttu-id="74e26-125">KPI (indicadores de desempenho chave)</span><span class="sxs-lookup"><span data-stu-id="74e26-125">Key Performance Indicators (KPI)</span></span>|[<span data-ttu-id="74e26-126">Indicadores Chave de Desempenho &#40;KPIs&#41; em Modelos Multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-126">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](key-performance-indicators-kpis-in-multidimensional-models.md)|  
|<span data-ttu-id="74e26-127">Cálculos</span><span class="sxs-lookup"><span data-stu-id="74e26-127">Calculations</span></span>|[<span data-ttu-id="74e26-128">Cálculos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-128">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|  
|<span data-ttu-id="74e26-129">Translations</span><span class="sxs-lookup"><span data-stu-id="74e26-129">Translations</span></span>|[<span data-ttu-id="74e26-130">Traduções em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-130">Translations in Multidimensional Models</span></span>](translations-in-multidimensional-models-analysis-services.md)|  
  
## <a name="related-tasks"></a><span data-ttu-id="74e26-131">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="74e26-131">Related Tasks</span></span>  
  
|<span data-ttu-id="74e26-132">Tópico</span><span class="sxs-lookup"><span data-stu-id="74e26-132">Topic</span></span>|<span data-ttu-id="74e26-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="74e26-133">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="74e26-134">Criar um cubo usando o Assistente para Cubos</span><span class="sxs-lookup"><span data-stu-id="74e26-134">Create a Cube Using the Cube Wizard</span></span>](create-a-cube-using-the-cube-wizard.md)|<span data-ttu-id="74e26-135">Descreve como usar o Assistente para Cubos para definir um cubo, as dimensões, os atributos de dimensão e as hierarquias definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="74e26-135">Describes how to use the Cube Wizard to define a cube, dimensions, dimension attributes, and user-defined hierarchies.</span></span>|  
|[<span data-ttu-id="74e26-136">Criar medidas e grupos de medidas em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-136">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|<span data-ttu-id="74e26-137">Descreve como definir os grupos de medidas.</span><span class="sxs-lookup"><span data-stu-id="74e26-137">Describes how to define measure groups.</span></span>|  
|[<span data-ttu-id="74e26-138">Cálculos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-138">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|<span data-ttu-id="74e26-139">Descreve como definir e configurar um cálculo em um script MDX.</span><span class="sxs-lookup"><span data-stu-id="74e26-139">Describes how to define and configure a calculation in an MDX script.</span></span>|  
|[<span data-ttu-id="74e26-140">Ações em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-140">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|<span data-ttu-id="74e26-141">Descreve como definir e configurar uma ação.</span><span class="sxs-lookup"><span data-stu-id="74e26-141">Describes how to define and configure an action.</span></span>|  
|[<span data-ttu-id="74e26-142">Perspectivas em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="74e26-142">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|<span data-ttu-id="74e26-143">Descreve como definir e configurar uma perspectiva.</span><span class="sxs-lookup"><span data-stu-id="74e26-143">Describes how to define and configure a perspective.</span></span>|  
|[<span data-ttu-id="74e26-144">Definindo procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="74e26-144">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)|<span data-ttu-id="74e26-145">Descreve como trabalhar com procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="74e26-145">Describes how to work with stored procedures.</span></span>|  
  
  
