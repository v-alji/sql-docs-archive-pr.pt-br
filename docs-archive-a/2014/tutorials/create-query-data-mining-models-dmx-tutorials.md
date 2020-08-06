---
title: 'Criando e consultando modelos de mineração de dados com DMX: Tutoriais (Analysis Services-Mineração de dados) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 145b81a7-c0c3-4ca3-bb32-0b482423b9a0
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 22ed01105a32f460bcbeb2c067299fdf62af2eed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568265"
---
# <a name="creating-and-querying-data-mining-models-with-dmx-tutorials-analysis-services---data-mining"></a><span data-ttu-id="bf4ba-102">Criando e consultando modelos de mineração de dados com DMX: Tutoriais (Analysis Services – Mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="bf4ba-102">Creating and Querying Data Mining Models with DMX: Tutorials (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="bf4ba-103">Depois de criar uma solução de Data Mining usando [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o, você pode criar consultas em relação aos modelos de Data Mining para prever tendências, recuperar padrões nos dados e medir a precisão dos modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-103">After you have created a data mining solution by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you can create queries against the data mining models to predict trends, retrieve patterns in the data, and measure the accuracy of the mining models.</span></span>  
  
 <span data-ttu-id="bf4ba-104">Os tutoriais passo a passo na lista a seguir ajudarão você a aprender a criar e executar Data Mining consultas usando o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para que você possa obter o máximo de seus dados.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-104">The step-by-step tutorials in the following list will help you learn how to build and run data mining queries by using [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] so that you can get the most from your data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf4ba-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bf4ba-105">In This Section</span></span>  
  
-   [<span data-ttu-id="bf4ba-106">Tutorial DMX Comprador de bicicleta</span><span class="sxs-lookup"><span data-stu-id="bf4ba-106">Bike Buyer DMX Tutorial</span></span>](../../2014/tutorials/bike-buyer-dmx-tutorial.md)  
  
     <span data-ttu-id="bf4ba-107">Este tutorial o orienta durante a criação de uma nova estrutura e de modelos de mineração usando a linguagem DMX e explica como criar consultas de previsão DMX.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-107">This tutorial walks you through the creation of a new mining structure and mining models by using the Data Mining Extensions (DMX) language, and explains how to create DMX prediction queries.</span></span>  
  
-   [<span data-ttu-id="bf4ba-108">Tutorial de DMX do Market Basket</span><span class="sxs-lookup"><span data-stu-id="bf4ba-108">Market Basket DMX Tutorial</span></span>](../../2014/tutorials/market-basket-dmx-tutorial.md)  
  
     <span data-ttu-id="bf4ba-109">Este tutorial usa um cenário de cesta de compras típico, no qual você localiza associações entre os produtos que clientes compram em conjunto.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-109">This tutorial uses a typical market basket scenario, where you find associations between the products that customers purchase together.</span></span> <span data-ttu-id="bf4ba-110">Este tutorial também demonstra como usar tabelas aninhadas quando você cria uma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-110">This tutorial also demonstrates how to use nested tables when you create a mining structure.</span></span> <span data-ttu-id="bf4ba-111">Crie e treine um modelo com base nesta estrutura e crie previsões usando DMX.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-111">You build and train a model based on this structure, and then create predictions using DMX.</span></span>  
  
-   [<span data-ttu-id="bf4ba-112">Tutorial DMX de previsão de série temporal</span><span class="sxs-lookup"><span data-stu-id="bf4ba-112">Time Series Prediction DMX Tutorial</span></span>](../../2014/tutorials/time-series-prediction-dmx-tutorial.md)  
  
     <span data-ttu-id="bf4ba-113">Este tutorial cria um modelo de previsão para ilustrar o uso da instrução CREATE MODEL (DMX).</span><span class="sxs-lookup"><span data-stu-id="bf4ba-113">This tutorial creates a forecasting model to illustrate the use of the CREATE MODEL (DMX) statement.</span></span> <span data-ttu-id="bf4ba-114">Você adiciona modelos relacionados e personaliza o comportamento de cada um ao alterar os parâmetros do algoritmo MTS.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-114">You then add related models and customize the behavior of each by changing the parameters of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="bf4ba-115">Por fim, cria previsões e as atualiza com novos dados.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-115">Finally you create predictions and update the predictions with new data.</span></span> <span data-ttu-id="bf4ba-116">A capacidade de atualizar uma série temporal ao fazer previsões foi adicionada no [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf4ba-116">The ability to update a time series while making predictions was added in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bf4ba-117">Referência</span><span class="sxs-lookup"><span data-stu-id="bf4ba-117">Reference</span></span>  
 [<span data-ttu-id="bf4ba-118">Algoritmos de mineração de dados &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bf4ba-118">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="bf4ba-119">Referência de DMX &#40;extensões DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="bf4ba-119">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
## <a name="related-sections"></a><span data-ttu-id="bf4ba-120">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="bf4ba-120">Related Sections</span></span>  
  
-   [<span data-ttu-id="bf4ba-121">Tutorial de mineração de dados básico</span><span class="sxs-lookup"><span data-stu-id="bf4ba-121">Basic Data Mining Tutorial</span></span>](../../2014/tutorials/basic-data-mining-tutorial.md)  
  
     <span data-ttu-id="bf4ba-122">Este tutorial introduz conceitos básicos, por exemplo, como criar um projeto e como criar estruturas e modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-122">This tutorial introduces basic concepts, such as how to create a project and how to build mining structures and mining models.</span></span>  
  
-   [<span data-ttu-id="bf4ba-123">Tutorial de mineração de dados intermediário &#40;Analysis Services de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="bf4ba-123">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
     <span data-ttu-id="bf4ba-124">Este tutorial contém algumas lições independentes, cada uma introduzindo um tipo de modelo diferente.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-124">This tutorial contains a number of independent lessons, each introducing you to a different model type.</span></span> <span data-ttu-id="bf4ba-125">Cada lição orienta você pelo processo de criação de um modelo, de exploração do modelo e de personalização do modelo e de criação de consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="bf4ba-125">Each lesson walks you through the process of creating a model, exploring the model, and then customizing the model and creating prediction queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4ba-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf4ba-126">See Also</span></span>  
 <span data-ttu-id="bf4ba-127">[Soluções de mineração de dados](../../2014/analysis-services/data-mining/data-mining-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="bf4ba-127">[Data Mining Solutions](../../2014/analysis-services/data-mining/data-mining-solutions.md) </span></span>  
 <span data-ttu-id="bf4ba-128">[Ferramentas de mineração de dados](../../2014/analysis-services/data-mining/data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bf4ba-128">[Data Mining Tools](../../2014/analysis-services/data-mining/data-mining-tools.md) </span></span>  
 [<span data-ttu-id="bf4ba-129">Projetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="bf4ba-129">Data Mining Projects</span></span>](../../2014/analysis-services/data-mining/data-mining-projects.md)  
  
  
