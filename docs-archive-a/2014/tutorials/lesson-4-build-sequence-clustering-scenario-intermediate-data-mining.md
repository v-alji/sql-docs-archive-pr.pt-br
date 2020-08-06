---
title: 'Lição 4: Criando um cenário de clustering de sequências (tutorial de mineração de dados intermediário) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- sequence clustering algorithms [Analysis Services]
- tutorials [Data Mining]
ms.assetid: 63436bbd-0f73-4012-b6f1-358c81e4d92a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 0f417c685d8af898de7c66ffe82045fa76b582e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678365"
---
# <a name="lesson-4-building-a-sequence-clustering-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="6341d-102">Lição 4: Criando um cenário de clustering de sequências (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="6341d-102">Lesson 4: Building a Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="6341d-103">O departamento de marketing da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] deseja compreender como os clientes navegam pelo site da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6341d-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to understand how customers move through the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Web site.</span></span> <span data-ttu-id="6341d-104">A empresa suspeita que há um padrão para a ordem na qual os clientes colocam os produtos em suas cestas de compra.</span><span class="sxs-lookup"><span data-stu-id="6341d-104">The company suspects that there is a pattern to the order in which customers put products into their shopping baskets.</span></span> <span data-ttu-id="6341d-105">Eles desejam analisar a ordem das sequências de compra para aprender como os clientes adicionam itens relacionados às suas cestas.</span><span class="sxs-lookup"><span data-stu-id="6341d-105">They want to analyze the order of purchase sequences to learn how customers add related items to their baskets.</span></span> <span data-ttu-id="6341d-106">Em seguida, eles podem usar essas informações para simplificar o fluxo do site para que ele leve os clientes a adquirir produtos adicionais.</span><span class="sxs-lookup"><span data-stu-id="6341d-106">They can then use this information to streamline the flow of the Web site so that it leads customers to purchase additional products.</span></span>  
  
 <span data-ttu-id="6341d-107">Depois de concluir as tarefas desta lição, você terá criado um modelo de mineração que usa o algoritmo Clustering de Sequências do [!INCLUDE[msCoName](../includes/msconame-md.md)] para prever o próximo item que os clientes colocarão em suas cestas de compra.</span><span class="sxs-lookup"><span data-stu-id="6341d-107">After you complete the tasks in this lesson, you will have created a mining model that uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm to predict the next item that customers will put into their shopping baskets.</span></span> <span data-ttu-id="6341d-108">Você fará testes com duas versões do modelo: uma que analisa somente a ordem de produtos na cesta e outra que contém alguns dados demográficos de cliente adicionais para clustering.</span><span class="sxs-lookup"><span data-stu-id="6341d-108">You will experiment with two versions of the model: one that analyzes only the order of products in the basket, and one that contains some additional customer demographics for clustering.</span></span> <span data-ttu-id="6341d-109">Por fim, você usará os modelos para criar previsões que poderão ser usadas na recomendação de produtos aos clientes.</span><span class="sxs-lookup"><span data-stu-id="6341d-109">Finally, you will use the models to create predictions that you can use to recommend products to customers.</span></span>  
  
 <span data-ttu-id="6341d-110">Para concluir as tarefas na lição, você usará a estrutura de mineração da cesta de compras criada na [lição 3: Criando um cenário de cesta de mercado &#40;tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="6341d-110">To complete the tasks in the lesson, you will use the market basket mining structure that you created in [Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="6341d-111">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="6341d-111">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="6341d-112">Criando uma estrutura de modelo de mineração de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-112">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="6341d-113">Processando o modelo de clustering de sequências</span><span class="sxs-lookup"><span data-stu-id="6341d-113">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
-   [<span data-ttu-id="6341d-114">Explorando o modelo de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-114">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="6341d-115">Criando um modelo de clustering de sequências relacionados &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-115">Creating a Related Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="6341d-116">Criando previsões em um modelo de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-116">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6341d-117">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="6341d-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6341d-118">Criando uma estrutura de modelo de mineração de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-118">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="6341d-119">Todas as lições</span><span class="sxs-lookup"><span data-stu-id="6341d-119">All Lessons</span></span>  
 [<span data-ttu-id="6341d-120">Lição 1: criando a solução intermediária de mineração de dados &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-120">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="6341d-121">Lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-121">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="6341d-122">Lição 3: Criando um cenário de cesta de compras &#40;Tutorial intermediário de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-122">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="6341d-123">Lição 4: Cenário de clustering de sequências (tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="6341d-123">Lesson 4: Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="6341d-124">Lição 5: Criando modelos de rede neural e de regressão logística &#40;Tutorial intermediário de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-124">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="6341d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6341d-125">See Also</span></span>  
 <span data-ttu-id="6341d-126">[Tutorial de mineração de dados básico](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="6341d-126">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="6341d-127">Tutorial de mineração de dados intermediário &#40;Analysis Services de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="6341d-127">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
