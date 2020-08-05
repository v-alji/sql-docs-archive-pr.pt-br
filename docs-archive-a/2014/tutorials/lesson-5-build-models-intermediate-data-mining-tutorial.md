---
title: 'Lição 5: criando modelos de rede neural e de regressão logística (tutorial de mineração de dados intermediário) | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- logistic regression [Analysis Services]
- data mining [Analysis Services], tutorials
- neural networks
- tutorials [Data Mining]
- neural network model [Analysis Services]
ms.assetid: 42c3701a-1fd2-44ff-b7de-377345bbbd6b
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a8c9fcf0380582f15fa2bf30d6fdeb97bb2ab1fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572869"
---
# <a name="lesson-5-building-neural-network-and-logistic-regression-models-intermediate-data-mining-tutorial"></a><span data-ttu-id="27baa-102">Lição 5: Criando modelos de rede neural e de regressão logística (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="27baa-102">Lesson 5: Building Neural Network and Logistic Regression Models (Intermediate Data Mining Tutorial)</span></span>
  
  
 <span data-ttu-id="27baa-103">O departamento de Operações da [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] está envolvido em um projeto para melhorar satisfação do cliente com seu call center.</span><span class="sxs-lookup"><span data-stu-id="27baa-103">The Operations department of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] is engaged in a project to improve customer satisfaction with their call center.</span></span> <span data-ttu-id="27baa-104">Eles contrataram um fornecedor para gerenciar o call center e relatar a métrica da efetividade do call center e pediram a você para analisar alguns dados preliminares apresentados pelo fornecedor.</span><span class="sxs-lookup"><span data-stu-id="27baa-104">They hired a vendor to manage the call center and to report metrics on call center effectiveness, and have asked you to analyze some preliminary data provided by the vendor.</span></span> <span data-ttu-id="27baa-105">Eles querem saber se é há alguma descoberta interessante.</span><span class="sxs-lookup"><span data-stu-id="27baa-105">They want to know if there are any interesting findings.</span></span> <span data-ttu-id="27baa-106">Em particular, eles gostariam de saber se os dados sugerem algum problema com a equipe ou maneiras de melhorar a satisfação do cliente.</span><span class="sxs-lookup"><span data-stu-id="27baa-106">In particular, they would like to know if the data suggests any staffing problems with staffing or ways to improve customer satisfaction.</span></span>  
  
 <span data-ttu-id="27baa-107">O conjunto de dados é pequeno e abrange apenas um período de 30 dias na operação do call center.</span><span class="sxs-lookup"><span data-stu-id="27baa-107">The data set is small and covers only a 30-day period in the operation of the call center.</span></span> <span data-ttu-id="27baa-108">Os dados mostram o número de operadores novos e experientes em cada turno, o número de chamadas recebidas, o número de pedidos e os problemas que devem ser resolvidos e o tempo médio que o cliente aguarda para alguém responder à chamada.</span><span class="sxs-lookup"><span data-stu-id="27baa-108">The data tracks the number of new and experienced operators in each shift, the number of incoming calls, the number of orders as well as issues that must be resolved, and the average time a customer waits for someone to respond to a call.</span></span> <span data-ttu-id="27baa-109">Os dados também incluem uma métrica de qualidade de serviço baseada na *taxa de abandono*, que é um indicador de frustração do cliente.</span><span class="sxs-lookup"><span data-stu-id="27baa-109">The data also includes a service quality metric based on *abandon rate*, which is an indicator of customer frustration.</span></span>  
  
 <span data-ttu-id="27baa-110">Como você não tem nenhuma expectativa anterior sobre o que os dados mostrarão, você decide usar um modelo de rede neural para explorar as possíveis correlações.</span><span class="sxs-lookup"><span data-stu-id="27baa-110">Because you do not have any prior expectations about what the data will show, you decide to use a neural network model to explore possible correlations.</span></span> <span data-ttu-id="27baa-111">Os modelos de rede neural são usados com frequência para exploração, porque podem analisar relações complexas entre muitas entradas e saídas.</span><span class="sxs-lookup"><span data-stu-id="27baa-111">Neural network models are often used for exploration because they can analyze complex relationships between many inputs and outputs.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="27baa-112">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="27baa-112">What You Will Learn</span></span>  
 <span data-ttu-id="27baa-113">Nesta lição, você usará o algoritmo de rede neural para criar um modelo que você e a equipe de Operações possam usar para entender as tendências nos dados.</span><span class="sxs-lookup"><span data-stu-id="27baa-113">In this lesson, you will use the neural network algorithm to build a model that you and the Operations team can use to understand the trends in the data.</span></span> <span data-ttu-id="27baa-114">Como parte desta lição, você tentará responder as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="27baa-114">As part of this lesson, you will try to answer the following questions:</span></span>  
  
-   <span data-ttu-id="27baa-115">Quais fatores afetam a satisfação do cliente?</span><span class="sxs-lookup"><span data-stu-id="27baa-115">What factors affect customer satisfaction?</span></span>  
  
-   <span data-ttu-id="27baa-116">O que o call center pode fazer para melhorar a qualidade do serviço?</span><span class="sxs-lookup"><span data-stu-id="27baa-116">What can the call center do to improve service quality?</span></span>  
  
 <span data-ttu-id="27baa-117">Com base nos resultados, você criará um modelo de regressão logística que poderá usar para previsões.</span><span class="sxs-lookup"><span data-stu-id="27baa-117">Based on the results, you will then build a logistic regression model that you can use for predictions.</span></span> <span data-ttu-id="27baa-118">As previsões serão usadas pela equipe de Operações como um auxílio no planejamento da operação do call center.</span><span class="sxs-lookup"><span data-stu-id="27baa-118">The predictions will be used by the Operations team as an aid in planning call center operation.</span></span>  
  
 <span data-ttu-id="27baa-119">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="27baa-119">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="27baa-120">Adicionando uma exibição da fonte de dados para dados do Call Center &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-120">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="27baa-121">Criando uma estrutura de rede neural e um modelo &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-121">Creating a Neural Network Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-neural-network-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="27baa-122">Explorando o modelo do Call Center &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-122">Exploring the Call Center Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-call-center-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="27baa-123">Adicionando um modelo de regressão logística à estrutura do Call Center &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-123">Adding a Logistic Regression Model to the Call Center Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-logistic-regression-model-to-call-center-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="27baa-124">Criando previsões para os modelos do Call Center &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-124">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="27baa-125">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="27baa-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="27baa-126">Adicionando uma exibição da fonte de dados para dados do Call Center &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-126">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="27baa-127">Todas as lições</span><span class="sxs-lookup"><span data-stu-id="27baa-127">All Lessons</span></span>  
 [<span data-ttu-id="27baa-128">Lição 1: criando a solução intermediária de mineração de dados &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-128">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="27baa-129">Lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-129">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="27baa-130">Lição 3: Criando um cenário de cesta de compras &#40;Tutorial intermediário de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-130">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="27baa-131">Lição 4: Criando um cenário de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-131">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 <span data-ttu-id="27baa-132">Lição 5: Cenário de rede neural e de regressão logística (tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="27baa-132">Lesson 5: Neural Network and Logistic Regression Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27baa-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27baa-133">See Also</span></span>  
 <span data-ttu-id="27baa-134">[Tutorial de mineração de dados básico](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="27baa-134">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="27baa-135">Tutorial de mineração de dados intermediário &#40;Analysis Services de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="27baa-135">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
