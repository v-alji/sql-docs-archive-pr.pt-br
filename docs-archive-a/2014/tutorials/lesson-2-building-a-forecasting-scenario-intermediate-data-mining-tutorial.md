---
title: 'Lição 2: Criando um cenário de previsão (tutorial de mineração de dados intermediário) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time series [Analysis Services]
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: 9a988156-c900-4c22-97fa-f6b0c1aea9e2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c81d5846df0a37c2b4182cb92fea86ce6f3417a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568977"
---
# <a name="lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="931ab-102">Lição 2: Criando um cenário de previsão (Tutorial de data mining intermediário)</span><span class="sxs-lookup"><span data-stu-id="931ab-102">Lesson 2: Building a Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="931ab-103">Como analista de vendas da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], foi solicitado que você fizesse a previsão das vendas de produtos para o próximo ano.</span><span class="sxs-lookup"><span data-stu-id="931ab-103">As the sales analyst for [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you have been asked to forecast the sales of products for the next year.</span></span> <span data-ttu-id="931ab-104">Em particular, você deverá comparar previsões para regiões e linhas de produto diferentes.</span><span class="sxs-lookup"><span data-stu-id="931ab-104">In particular, you have been asked to compare forecasts for the different regions and product lines.</span></span> <span data-ttu-id="931ab-105">Adicionalmente, foi pedido que você determinasse se há variação nas vendas de produtos diferentes, dependendo da época do ano.</span><span class="sxs-lookup"><span data-stu-id="931ab-105">Additionally, you have been asked to determine whether sales of different products vary depending on the time of the year.</span></span>  
  
 <span data-ttu-id="931ab-106">Para localizar as informações solicitadas, nesta lição você resumirá os dados de vendas da empresa, mês a mês, e também resumirá os valores de vendas por três regiões: Europa, América do Norte e Pacífico.</span><span class="sxs-lookup"><span data-stu-id="931ab-106">To find the requested information, in this lesson you will summarize the company's sales data at the monthly level, and you will also summarize sales figures by three regions: Europe, North America, and the Pacific.</span></span>  
  
 <span data-ttu-id="931ab-107">Depois que completar as tarefas desta lição, você estará apto a responder às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="931ab-107">After you complete the tasks in this lesson, you will be able to answer the following questions:</span></span>  
  
-   <span data-ttu-id="931ab-108">Como as vendas de diferentes modelos de bicicleta mudam ao longo do tempo?</span><span class="sxs-lookup"><span data-stu-id="931ab-108">How do the sales of different bike models change over time?</span></span>  
  
-   <span data-ttu-id="931ab-109">Há diferenças entre os padrões para vendas nas três regiões?</span><span class="sxs-lookup"><span data-stu-id="931ab-109">Are there differences between the patterns for sales in the three regions?</span></span>  
  
-   <span data-ttu-id="931ab-110">Podemos prever picos de vendas?</span><span class="sxs-lookup"><span data-stu-id="931ab-110">Can we forecast sales peaks?</span></span>  
  
 <span data-ttu-id="931ab-111">A lição pode ser concluída em duas partes:</span><span class="sxs-lookup"><span data-stu-id="931ab-111">The lesson can be completed in two parts:</span></span>  
  
-   <span data-ttu-id="931ab-112">A parte Um apresenta os fundamentos de como criar e usar um modelo de série temporal.</span><span class="sxs-lookup"><span data-stu-id="931ab-112">Part One introduces the basics of how to create and use a time series model.</span></span>  
  
-   <span data-ttu-id="931ab-113">A Parte Dois orienta você na criação de um modelo de série temporal geral, baseado em todas as regiões.</span><span class="sxs-lookup"><span data-stu-id="931ab-113">Part Two walks you through creation of a general time series model, based on all regions.</span></span> <span data-ttu-id="931ab-114">Você pode usar esse modelo geral para *previsão cruzada*.</span><span class="sxs-lookup"><span data-stu-id="931ab-114">You can use this general model for *cross-prediction*.</span></span>  
  
 <span data-ttu-id="931ab-115">Para concluir as tarefas desta lição, que estão listadas abaixo, você usará a [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] fonte de dados criada na [lição 1: criando a solução intermediária de mineração de dados &#40;tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="931ab-115">To complete the tasks in this lesson, which are listed below, you will use the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source that you created in [Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="931ab-116">As datas usadas no banco de dados de exemplo [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] foram atualizadas para esta versão.</span><span class="sxs-lookup"><span data-stu-id="931ab-116">The dates in the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] sample database have been updated for this release.</span></span> <span data-ttu-id="931ab-117">Se você usar uma versão anterior do [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], poderá criar o modelo seguindo estas etapas, mas poderá ver resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="931ab-117">If you use an earlier version of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you can build the model following these steps, but you might see different results.</span></span>  
  
 <span data-ttu-id="931ab-118">**Criando um modelo de previsão simples**</span><span class="sxs-lookup"><span data-stu-id="931ab-118">**Creating a Simple Forecasting Model**</span></span>  
  
-   [<span data-ttu-id="931ab-119">Adicionando uma exibição da fonte de dados para prever &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-119">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="931ab-120">Criando uma estrutura de previsão e modelo &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-120">Creating a Forecasting Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="931ab-121">Modificando a estrutura de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-121">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="931ab-122">Personalizando e processando o modelo de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-122">Customizing and Processing the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/customize-process-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="931ab-123">Explorando o modelo de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-123">Exploring the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="931ab-124">Criando previsões de série temporal &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-124">Creating Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="931ab-125">**Criando um modelo de previsão geral para previsão cruzada**</span><span class="sxs-lookup"><span data-stu-id="931ab-125">**Creating a General Forecasting Model for Cross-Prediction**</span></span>  
  
-   [<span data-ttu-id="931ab-126">Previsões de série temporal avançada &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-126">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="931ab-127">Previsões de série temporal usando dados atualizados &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-127">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="931ab-128">Previsões de série temporal usando dados de substituição &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-128">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="931ab-129">Comparando previsões para modelos de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-129">Comparing Predictions for Forecasting Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="931ab-130">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="931ab-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="931ab-131">Adicionando uma exibição da fonte de dados para prever &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-131">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="931ab-132">Noções básicas sobre os requisitos de um modelo de série temporal &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-132">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="931ab-133">Todas as lições</span><span class="sxs-lookup"><span data-stu-id="931ab-133">All Lessons</span></span>  
 [<span data-ttu-id="931ab-134">Lição 1: criando a solução intermediária de mineração de dados &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-134">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="931ab-135">Lição 2: Cenário de previsão (tutorial de data mining intermediário)</span><span class="sxs-lookup"><span data-stu-id="931ab-135">Lesson 2: Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="931ab-136">Lição 3: Criando um cenário de cesta de compras &#40;Tutorial intermediário de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-136">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="931ab-137">Lição 4: Criando um cenário de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-137">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="931ab-138">Lição 5: Criando modelos de rede neural e de regressão logística &#40;Tutorial intermediário de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="931ab-138">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="931ab-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="931ab-139">See Also</span></span>  
 <span data-ttu-id="931ab-140">[Tutorial de mineração de dados básico](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="931ab-140">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="931ab-141">[Tutorial de mineração de dados intermediário &#40;Analysis Services de mineração de dados&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="931ab-141">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="931ab-142">Algoritmo MTS</span><span class="sxs-lookup"><span data-stu-id="931ab-142">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
