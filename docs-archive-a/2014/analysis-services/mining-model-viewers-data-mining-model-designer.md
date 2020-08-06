---
title: Visualizadores do modelo de mineração (Designer de modelo de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.viewers.f1
ms.assetid: 4ba391d5-c97b-4848-ba7c-7d096fa4b7dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4cc1c9d72a08ef49ed2f4f466953d2ba61394178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684942"
---
# <a name="mining-model-viewers-data-mining-model-designer"></a><span data-ttu-id="0d867-102">Visualizadores do Modelo de Mineração (Designer do Modelo de Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="0d867-102">Mining Model Viewers (Data Mining Model Designer)</span></span>
  <span data-ttu-id="0d867-103">Use a guia **Visualizador do Modelo de Mineração** para explorar os modelos de mineração contidos em uma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="0d867-103">Use the **Mining Model Viewer** tab to explore the mining models that a mining structure contains.</span></span>

 <span data-ttu-id="0d867-104">Selecione primeiro o modelo de mineração e, em seguida, selecione um visualizador.</span><span class="sxs-lookup"><span data-stu-id="0d867-104">First you select the mining model and then you select a viewer.</span></span> <span data-ttu-id="0d867-105">Cada modelo tem sempre dois visualizadores disponíveis: um visualizar personalizado, que pode incluir várias guias, e o visualizador genérico.</span><span class="sxs-lookup"><span data-stu-id="0d867-105">Each model always has two viewers available: a custom viewer, which can include multiple tabs, and the generic viewer.</span></span>

 <span data-ttu-id="0d867-106">Para obter instruções passo a passo sobre como usar cada visualizador, consulte [Visualizadores do modelo de mineração de dados](data-mining/data-mining-model-viewers.md).</span><span class="sxs-lookup"><span data-stu-id="0d867-106">For a walkthrough of how to use each viewer, see [Data Mining Model Viewers](data-mining/data-mining-model-viewers.md).</span></span>

## <a name="common-options"></a><span data-ttu-id="0d867-107">Opções comuns</span><span class="sxs-lookup"><span data-stu-id="0d867-107">Common Options</span></span>
 <span data-ttu-id="0d867-108">**Atualizar conteúdo do visualizador** Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="0d867-108">**Refresh viewer content** Reload the mining model in the viewer.</span></span>

 <span data-ttu-id="0d867-109">**Modelo de mineração** Escolha um modelo de mineração para exibir o que está presente na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="0d867-109">**Mining Model** Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="0d867-110">O modelo de mineração será aberto primeiro no visualizador personalizado associado.</span><span class="sxs-lookup"><span data-stu-id="0d867-110">The mining model will first open in its associated custom viewer.</span></span>

 <span data-ttu-id="0d867-111">**Visualizador** Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="0d867-111">**Viewer** Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="0d867-112">Essa lista inclui os visualizadores que [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o fornece para cada modelo de mineração, o [!INCLUDE[msCoName](../includes/msconame-md.md)] Visualizador de conteúdo de mineração e quaisquer visualizadores de plug-in.</span><span class="sxs-lookup"><span data-stu-id="0d867-112">This list includes the viewers that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides for each mining model, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer, and any plug-in viewers.</span></span>

 <span data-ttu-id="0d867-113">O diagrama a seguir mostra um visualizador personalizado e um genérico para o mesmo modelo.</span><span class="sxs-lookup"><span data-stu-id="0d867-113">The following diagram shows a custom viewer and the generic viewer for the same model.</span></span>

-   <span data-ttu-id="0d867-114">O diagrama superior mostra o visualizador para um modelo de mineração baseado no algoritmo MTS.</span><span class="sxs-lookup"><span data-stu-id="0d867-114">The upper diagram shows the viewer for a mining model based on the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="0d867-115">Esse visualizador personalizado específico cria automaticamente um gráfico da série temporal e fornece cinco previsões.</span><span class="sxs-lookup"><span data-stu-id="0d867-115">This particular custom viewer automatically creates a graph of the time series and provides five predictions.</span></span>

-   <span data-ttu-id="0d867-116">O diagrama inferior mostra o mesmo modelo, exibido usando o **Visualizador de Árvore de Conteúdo Genérica da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0d867-116">The lower diagram shows the same model displayed using the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="0d867-117">Este visualizador apresenta o conteúdo do modelo de mineração de acordo com um esquema padronizado.</span><span class="sxs-lookup"><span data-stu-id="0d867-117">This viewer presents the contents of the mining model according to a standardized schema.</span></span> <span data-ttu-id="0d867-118">Para obter mais informações, consulte [Visualizador de Árvore de Conteúdo Genérica da Microsoft &#40;Mineração de dados&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="0d867-118">For more information, see [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](microsoft-generic-content-tree-viewer-data-mining.md).</span></span>

 <span data-ttu-id="0d867-119">![Visão geral do designer de modelo de mineração](media/generic-mining-model-tab1.gif "Visão geral do designer de modelo de mineração")</span><span class="sxs-lookup"><span data-stu-id="0d867-119">![Overview of mining model designer](media/generic-mining-model-tab1.gif "Overview of mining model designer")</span></span>

## <a name="viewers-and-their-components"></a><span data-ttu-id="0d867-120">Visualizadores e seus componentes</span><span class="sxs-lookup"><span data-stu-id="0d867-120">Viewers and Their Components</span></span>
 <span data-ttu-id="0d867-121">Dependendo do modelo que você selecionar, você verá um visualizador personalizado diferente, adaptado para o algoritmo usado para criar o modelo de mineração de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="0d867-121">Depending on the model that you select, you will see a different custom viewer, tailored to the algorithm that you used to create the selected data mining model.</span></span> <span data-ttu-id="0d867-122">Cada visualizador personalizado tem uma variedade de ferramentas e caixas de diálogo para ajudar a explorar as estatísticas e os padrões no modelo.</span><span class="sxs-lookup"><span data-stu-id="0d867-122">Each custom viewer has a variety of tools and dialog boxes for helping you explore the statistics and patterns in the model.</span></span>

 <span data-ttu-id="0d867-123">A lista a seguir descreve as opções em cada visualizador personalizado.</span><span class="sxs-lookup"><span data-stu-id="0d867-123">The following list describes the options in each of the custom viewers.</span></span>

### <a name="microsoft-association-rules-algorithm"></a><span data-ttu-id="0d867-124">Algoritmo Regras de Associação da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-124">Microsoft Association Rules Algorithm</span></span>

-   [<span data-ttu-id="0d867-125">Procurar um modelo usando o Visualizador de Regras de Associação da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-125">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)

    -   [<span data-ttu-id="0d867-126">Guia conjuntos de itens &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-126">Itemsets Tab &#40;Mining Model Viewer&#41;</span></span>](itemsets-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-127">Guia regras &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-127">Rules Tab &#40;Mining Model Viewer&#41;</span></span>](rules-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-128">Guia rede de dependências &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-128">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

### <a name="microsoft-clustering-algorithm"></a><span data-ttu-id="0d867-129">Algoritmo Microsoft Clustering</span><span class="sxs-lookup"><span data-stu-id="0d867-129">Microsoft Clustering Algorithm</span></span>

-   [<span data-ttu-id="0d867-130">Procurar um modelo usando o Visualizador de Cluster da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-130">Browse a Model Using the Microsoft Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)

    -   [<span data-ttu-id="0d867-131">Guia diagrama de cluster &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-131">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-132">Guia perfis de cluster &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-132">Cluster Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-133">Guia características do cluster &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-133">Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-134">Guia discriminação de cluster &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-134">Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-135">Caixa de diálogo legenda de mineração &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-135">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-decision-tree-algorithm"></a><span data-ttu-id="0d867-136">Algoritmo Árvore de Decisão da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-136">Microsoft Decision Tree Algorithm</span></span>

-   [<span data-ttu-id="0d867-137">Procurar um modelo usando a Exibição de Árvore da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-137">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)

    -   [<span data-ttu-id="0d867-138">Guia árvore de decisão &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-138">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-139">Guia rede de dependências &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-139">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-140">Caixa de diálogo legenda de mineração &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-140">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-linear-regression-algorithm"></a><span data-ttu-id="0d867-141">Algoritmo Regressão Linear da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-141">Microsoft Linear Regression Algorithm</span></span>

-   [<span data-ttu-id="0d867-142">Procurar um modelo usando o Visualizador de Rede Neural da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-142">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="0d867-143">Guia árvore de decisão &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-143">Decision Tree Tab &#40;Mining Model Viewer&#41;</span></span>](decision-tree-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-144">Guia rede de dependências &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-144">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-145">Caixa de diálogo legenda de mineração &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-145">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

### <a name="microsoft-logistic-regression-algorithm"></a><span data-ttu-id="0d867-146">Algoritmo Regressão Logística da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-146">Microsoft Logistic Regression Algorithm</span></span>

-   [<span data-ttu-id="0d867-147">Procurar um modelo usando o Visualizador de Rede Neural da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-147">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

### <a name="microsoft-nave-bayes-algorithm"></a><span data-ttu-id="0d867-148">Algoritmo Microsoft Naïve Bayes</span><span class="sxs-lookup"><span data-stu-id="0d867-148">Microsoft Naïve Bayes Algorithm</span></span>

-   [<span data-ttu-id="0d867-149">Procurar um modelo usando o Visualizador do Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="0d867-149">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)

    -   [<span data-ttu-id="0d867-150">Guia rede de dependências &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-150">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-151">Guia perfis de atributo &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-151">Attribute Profiles Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-152">Guia características do atributo &#40;o Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-152">Attribute Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-153">Guia discriminação de atributo &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-153">Attribute Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](attribute-discrimination-tab-mining-model-viewer.md)

### <a name="microsoft-neural-network-algorithm"></a><span data-ttu-id="0d867-154">Microsoft Neural Network Algorithm</span><span class="sxs-lookup"><span data-stu-id="0d867-154">Microsoft Neural Network Algorithm</span></span>

-   [<span data-ttu-id="0d867-155">Procurar um modelo usando o Visualizador de Rede Neural da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-155">Browse a Model Using the Microsoft Neural Network Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-neural-network-viewer.md)

    -   [<span data-ttu-id="0d867-156">Guia rede de dependências &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-156">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](dependency-network-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-157">Visualizador de modelo de mineração de &#40;de rede neural&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-157">Neural Network &#40;Mining Model Viewer&#41;</span></span>](neural-network-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-158">Caixa de diálogo Localizar nó &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-158">Find Node Dialog Box &#40;Mining Model Viewer&#41;</span></span>](find-node-dialog-box-mining-model-viewer.md)

### <a name="microsoft-sequence-clustering-algorithm"></a><span data-ttu-id="0d867-159">Microsoft Sequence Clustering Algorithm</span><span class="sxs-lookup"><span data-stu-id="0d867-159">Microsoft Sequence Clustering Algorithm</span></span>

-   [<span data-ttu-id="0d867-160">Procurar um modelo usando o Visualizador de Cluster de Sequência da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d867-160">Browse a Model Using the Microsoft Sequence Cluster Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)

    -   [<span data-ttu-id="0d867-161">Guia diagrama de clustering de sequências &#40;Visualizador do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="0d867-161">Sequence Clustering Cluster Diagram Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-diagram-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-162">Guia perfis de cluster do clustering de sequências &#40;Visualizador do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="0d867-162">Sequence Clustering Cluster Profiles Tab &#40;Mining Model Viewer</span></span>](sequence-clustering-cluster-profiles-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-163">Guia características do cluster clustering de sequências &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-163">Sequence Clustering Cluster Characteristics Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-characteristics-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-164">Guia discriminação de cluster de clustering de sequências &#40;Visualizador de modelos de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-164">Sequence Clustering Cluster Discrimination Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-discrimination-tab-mining-model-viewer.md)

    -   [<span data-ttu-id="0d867-165">Guia transição de cluster do clustering de sequências &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-165">Sequence Clustering Cluster Transition Tab &#40;Mining Model Viewer&#41;</span></span>](sequence-clustering-cluster-transition-tab-mining-model-viewer.md)

### <a name="microsoft-time-series-algorithm"></a><span data-ttu-id="0d867-166">Algoritmo MTS</span><span class="sxs-lookup"><span data-stu-id="0d867-166">Microsoft Time Series Algorithm</span></span>

-   [<span data-ttu-id="0d867-167">Procurar um modelo usando o Visualizador MTS</span><span class="sxs-lookup"><span data-stu-id="0d867-167">Browse a Model Using the Microsoft Time Series Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)

    -   [<span data-ttu-id="0d867-168">Guia modelo &#40;visualizadores de modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-168">Model Tab &#40;Mining Model Viewers&#41;</span></span>](model-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="0d867-169">Guia gráfico &#40;visualizadores de modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-169">Chart Tab &#40;Mining Model Viewers&#41;</span></span>](chart-tab-mining-model-viewers.md)

    -   [<span data-ttu-id="0d867-170">Caixa de diálogo legenda de mineração &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-170">Mining Legend Dialog Box &#40;Mining Model Viewer&#41;</span></span>](mining-legend-dialog-box-mining-model-viewer.md)

## <a name="see-also"></a><span data-ttu-id="0d867-171">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d867-171">See Also</span></span>
 <span data-ttu-id="0d867-172">[Modelos de mineração exiba &#40;designer de modelo de mineração de dados&#41;](mining-models-view-data-mining-model-designer.md) [exibição de estrutura de mineração &#40;](mining-structure-view-data-mining-model-designer.md) designer de modelo de mineração de dados&#41;designer de dados de [precisão de mineração &#40;Data Mining](mining-accuracy-chart-designer-data-mining.md)&#41;previsão Construtor de consultas &#40;de [mineração de dados](prediction-query-builder-data-mining.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="0d867-172">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) [Mining Structure View &#40;Data Mining Model Designer&#41;](mining-structure-view-data-mining-model-designer.md) [Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) [Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md)</span></span>


