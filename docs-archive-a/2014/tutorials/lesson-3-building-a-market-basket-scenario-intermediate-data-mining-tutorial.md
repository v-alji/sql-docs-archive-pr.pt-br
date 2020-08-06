---
title: 'Lição 3: Criando um cenário de cesta de compras (tutorial intermediário de mineração de dados) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- association algorithms [Analysis Services]
- nested tables
- tutorials [Data Mining]
ms.assetid: 651eef38-772e-4d97-af51-075b1b27fc5a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a281aa62fbf08393c95f12ded9886ac212b3165f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683197"
---
# <a name="lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="92ca8-102">Lição 3: Criando um cenário de cesta de compras (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="92ca8-102">Lesson 3: Building a Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="92ca8-103">O departamento de marketing da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] quer melhorar o site da empresa para promover uma venda cruzada.</span><span class="sxs-lookup"><span data-stu-id="92ca8-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to improve the company Web site to promote cross-selling.</span></span> <span data-ttu-id="92ca8-104">Como parte da atualização do site, eles gostariam de ter a capacidade de prever produtos que um cliente talvez queira comprar, com base em outros produtos que já estão em sua cesta de compras online.</span><span class="sxs-lookup"><span data-stu-id="92ca8-104">As part of the site update, they would like the ability to predict products that a customer might want to purchase, based on the other products that are already in the customer's online shopping basket.</span></span> <span data-ttu-id="92ca8-105">O departamento de marketing também deseja entender melhor o comportamento de compra do cliente, para que possa criar o site de modo que os itens que tendem a ser adquiridos juntos apareçam juntos.</span><span class="sxs-lookup"><span data-stu-id="92ca8-105">The marketing department also wants to understand customer purchasing behavior better, so that they can design the Web site so that the items that tend to be purchased together appear together.</span></span> <span data-ttu-id="92ca8-106">Eles descobriram que a mineração de dados é especialmente útil para esse tipo de *análise de cesta de mercado* e lhe pediram para desenvolver um modelo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="92ca8-106">They have learned that data mining is especially useful for this kind of *market basket analysis* and have asked you to develop a data mining model.</span></span>  
  
 <span data-ttu-id="92ca8-107">Depois de concluir as tarefas desta lição, você terá um modelo de mineração completo que mostra grupos de itens a partir do histórico de transações do cliente.</span><span class="sxs-lookup"><span data-stu-id="92ca8-107">After you complete the tasks in this lesson, you will have a mining model that shows groups of items from historical customer transactions.</span></span> <span data-ttu-id="92ca8-108">Adicionalmente, você poderá usar o modelo de mineração para prever itens adicionais que talvez o cliente queira comprar.</span><span class="sxs-lookup"><span data-stu-id="92ca8-108">Additionally, you can use the mining model to predict additional items that a customer may want to purchase.</span></span>  
  
 <span data-ttu-id="92ca8-109">Para concluir as tarefas nesta lição, você usará a solução e a fonte de dados que criou na primeira lição do tutorial de [mineração de dados intermediário &#40;Analysis Services&#41;de mineração de dados ](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="92ca8-109">To complete the tasks in this lesson, you will use the solution and data source that you created in the first lesson of the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="92ca8-110">Você modificará essa solução adicionando uma exibição da fonte de dados com tabelas sobre o cliente, incluindo uma tabela aninhada de compras de clientes.</span><span class="sxs-lookup"><span data-stu-id="92ca8-110">You will modify this solution by adding a data source view that contains tables about the customer, including a nested table of customer purchases.</span></span>  <span data-ttu-id="92ca8-111">Em seguida, você criará um modelo de mineração que use o algoritmo Microsoft Association Rules, apropriado a cenários de cesta de compras.</span><span class="sxs-lookup"><span data-stu-id="92ca8-111">You will then build a mining model that uses the Microsoft Association Rules algorithm, which is suited to market basket scenarios.</span></span>  
  
 <span data-ttu-id="92ca8-112">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="92ca8-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="92ca8-113">Adicionando uma exibição da fonte de dados com tabelas aninhadas &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-113">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="92ca8-114">Criando uma estrutura de cesta de mercado e um modelo &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-114">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="92ca8-115">Modificando e processando o modelo de cesta de mercado &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-115">Modifying and Processing the Market Basket Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modify-process-market-basket-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="92ca8-116">Explorando os modelos de cesta de mercado &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-116">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="92ca8-117">Filtrando uma tabela aninhada em um modelo de mineração &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-117">Filtering a Nested Table in a Mining Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="92ca8-118">Prevendo associações &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-118">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="92ca8-119">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="92ca8-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="92ca8-120">Adicionando uma exibição da fonte de dados com tabelas aninhadas &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-120">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="92ca8-121">Todas as lições</span><span class="sxs-lookup"><span data-stu-id="92ca8-121">All Lessons</span></span>  
 [<span data-ttu-id="92ca8-122">Lição 1: criando a solução intermediária de mineração de dados &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-122">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="92ca8-123">Lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-123">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="92ca8-124">Lição 3: Cenário de cesta de compras (tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="92ca8-124">Lesson 3: Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="92ca8-125">Lição 4: Criando um cenário de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-125">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="92ca8-126">Lição 5: Criando modelos de rede neural e de regressão logística &#40;Tutorial intermediário de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-126">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="92ca8-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92ca8-127">See Also</span></span>  
 <span data-ttu-id="92ca8-128">[Tutorial de mineração de dados básico](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="92ca8-128">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="92ca8-129">[Lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="92ca8-129">[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="92ca8-130">Lição 4: Criando um cenário de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="92ca8-130">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
  
