---
title: 'Lição 1: criando a solução de mineração de dados intermediárias (tutorial de mineração de dados intermediário) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: d8e3f89f-091c-434e-8f67-639f073edcdf
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: e1a69c78fee37abef8bb899ecf9a635fa7c7dba1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569775"
---
# <a name="lesson-1-creating-the-intermediate-data-mining-solution-intermediate-data-mining-tutorial"></a><span data-ttu-id="11152-102">Lição 1: Criando a solução intermediária de data mining (Tutorial de data mining intermediário)</span><span class="sxs-lookup"><span data-stu-id="11152-102">Lesson 1: Creating the Intermediate Data Mining Solution (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="11152-103">No tutorial Mineração de dados básica, você criou um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que contém uma solução simples de mineração de dados baseada no novo banco de dados [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11152-103">In the Basic Data Mining tutorial, you created an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project that contains a simple data mining solution based on the new [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="11152-104">Para esse tutorial, você criará um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à parte usando o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11152-104">For this tutorial, you will create a separate [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project by using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="11152-105">Você irá criar uma fonte de dados [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que usa o [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], e adicionar várias exibições da fonte de dados novas a essa fonte de dados, para dar suporte a cenários e tipos de modelos.</span><span class="sxs-lookup"><span data-stu-id="11152-105">You will create a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source that uses [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], and add several new data source views to that data source, to support the scenarios and model types.</span></span>  
  
 <span data-ttu-id="11152-106">Esta lição consiste na seguinte tarefa:</span><span class="sxs-lookup"><span data-stu-id="11152-106">This lesson consists of the following task:</span></span>  
  
-   [<span data-ttu-id="11152-107">Criando uma solução e uma fonte de dados &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="11152-107">Creating a Solution and Data Source &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-solution-and-data-source-intermediate-data-mining-tutorial.md)  
  
## <a name="next-step"></a><span data-ttu-id="11152-108">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="11152-108">Next Step</span></span>  
 [<span data-ttu-id="11152-109">Lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="11152-109">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="11152-110">Todas as lições</span><span class="sxs-lookup"><span data-stu-id="11152-110">All Lessons</span></span>  
 <span data-ttu-id="11152-111">Lição 1: Criando a solução intermediária de data mining</span><span class="sxs-lookup"><span data-stu-id="11152-111">Lesson 1: Creating the Intermediate Data Mining Solution</span></span>  
  
 [<span data-ttu-id="11152-112">Lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="11152-112">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="11152-113">Lição 3: Criando um cenário de cesta de compras &#40;Tutorial intermediário de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="11152-113">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="11152-114">Lição 4: Criando um cenário de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="11152-114">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="11152-115">Lição 5: Criando modelos de rede neural e de regressão logística &#40;Tutorial intermediário de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="11152-115">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="11152-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="11152-116">See Also</span></span>  
 <span data-ttu-id="11152-117">[Tutorial de mineração de dados básico](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="11152-117">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="11152-118">Criando e consultando modelos de mineração de dados com DMX: Tutoriais &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="11152-118">Creating and Querying Data Mining Models with DMX: Tutorials &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/create-query-data-mining-models-dmx-tutorials.md)  
  
  
