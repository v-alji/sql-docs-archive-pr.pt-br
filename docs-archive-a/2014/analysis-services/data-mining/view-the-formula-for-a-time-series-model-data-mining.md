---
title: Exibir a fórmula para um modelo de série temporal (mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- ARTXP
- time series algorithms [Analysis Services]
- ARIMA
- time series [Analysis Services]
- Time Series Viewer [Analysis Services]
ms.assetid: 825ef719-2f44-4979-be01-5a81f54e1a53
author: minewiskan
ms.author: owend
ms.openlocfilehash: eff61c469d34f084e6a0eb11c49a1c37c7cc97c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568878"
---
# <a name="view-the-formula-for-a-time-series-model-data-mining"></a><span data-ttu-id="4227f-102">Exibir a fórmula para um modelo de série temporal (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="4227f-102">View the Formula for a Time Series Model (Data Mining)</span></span>
  <span data-ttu-id="4227f-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] Designer de mineração de dados do Visualizador de séries temporais fornece a maneira mais fácil de exibir os detalhes da equação de regressão usada em um modelo de série temporal.</span><span class="sxs-lookup"><span data-stu-id="4227f-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series viewer inData Mining Designer provides the easiest way to view the details of the regression equation used in a time series model.</span></span>  
  
 <span data-ttu-id="4227f-104">Você pode extrair a fórmula de regressão para um modelo de série temporal consultando o conteúdo do modelo.</span><span class="sxs-lookup"><span data-stu-id="4227f-104">You can extract the regression formula for a time series model by querying the model content.</span></span> <span data-ttu-id="4227f-105">No entanto, para exibir a fórmula ARTXP ou ARIMA completa, recomendamos que você use a **legenda de mineração** do [Visualizador do Microsoft Time Series](browse-a-model-using-the-microsoft-time-series-viewer.md), que apresenta todas as constantes em um formato legível.</span><span class="sxs-lookup"><span data-stu-id="4227f-105">However, to view the complete ARTXP or ARIMA formula, we recommend that you use the **Mining Legend** of the [Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md), which presents all the constants in a readable format.</span></span>  
  
 <span data-ttu-id="4227f-106">Se você criar um modelo misto, as análises ARIMA e ARTXP serão criadas em árvores separadas, unidas no nó raiz que representa o modelo.</span><span class="sxs-lookup"><span data-stu-id="4227f-106">If you create a mixed model, the ARIMA and ARTXP analyses are created in separate trees, joined at the root node representing the model.</span></span> <span data-ttu-id="4227f-107">As estruturas das árvores ARIMA e ARTXP são bem diferentes.</span><span class="sxs-lookup"><span data-stu-id="4227f-107">The structures of the ARIMA and ARTXP trees are very different.</span></span> <span data-ttu-id="4227f-108">Por exemplo, a árvore ARTXP na verdade é uma estrutura de árvore, como uma árvore de decisão, enquanto a árvore ARIMA representa uma série de médias móveis.</span><span class="sxs-lookup"><span data-stu-id="4227f-108">For example, the ARTXP tree is in fact a tree structure, like a decision tree, whereas the ARIMA tree represents a series of moving averages.</span></span> <span data-ttu-id="4227f-109">Assim, embora as duas representações estejam presentes em um modelo por conveniência, elas devem ser tratadas como modelos independentes.</span><span class="sxs-lookup"><span data-stu-id="4227f-109">Therefore, although the two representations are presented in one model for convenience, they should be treated as two independent models.</span></span> <span data-ttu-id="4227f-110">As equações também são completamente diferentes e não podem ser combinadas ou comparadas.</span><span class="sxs-lookup"><span data-stu-id="4227f-110">The equations are also completely different and cannot be combined or compared.</span></span>  
  
 <span data-ttu-id="4227f-111">Você também pode exibir modelos de série temporal usando o [Visualizador de árvore de conteúdo genérica da Microsoft](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4227f-111">You can also view time series models by using the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="4227f-112">Para obter mais informações sobre o conteúdo de um modelo de série temporal, consulte [conteúdo do modelo de mineração para modelos de série temporal &#40;&#41;de mineração de dados Analysis Services ](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4227f-112">For more information about the content of a time series model, see [Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-time-series-models-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-view-the-artxp-regression-formula-for-a-time-series-model"></a><span data-ttu-id="4227f-113">Para exibir a fórmula de regressão ARTXP para um modelo de série temporal</span><span class="sxs-lookup"><span data-stu-id="4227f-113">To view the ARTXP regression formula for a time series model</span></span>  
  
1.  <span data-ttu-id="4227f-114">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selecione o modelo de série temporal que você quer exibir e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="4227f-114">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="4227f-115">-- ou --</span><span class="sxs-lookup"><span data-stu-id="4227f-115">-- or --</span></span>  
  
     <span data-ttu-id="4227f-116">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], selecione o modelo de série temporal e clique na guia **Visualizador do Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="4227f-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="4227f-117">Clique na guia **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="4227f-117">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="4227f-118">Se o modelo contiver várias árvores, selecione uma única árvore na lista suspensa **Árvore** .</span><span class="sxs-lookup"><span data-stu-id="4227f-118">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4227f-119">Um modelo sempre terá várias árvores se você tiver mais de uma série de dados.</span><span class="sxs-lookup"><span data-stu-id="4227f-119">A model will always have multiple trees if you have more than one data series.</span></span> <span data-ttu-id="4227f-120">No entanto, você não visualizará tantas árvores no **visualizador MTS** quanto no [Visualizador de Árvore de Conteúdo Genérica da Microsoft](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4227f-120">However, you will not see as many trees in the **Time Series viewer** as you will see in the [Microsoft Generic Content Tree Viewer](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span> <span data-ttu-id="4227f-121">Isso ocorre porque o visualizador de Série Temporal combina as informações de ARIMA e ARTXP para cada série de dados em uma única representação.</span><span class="sxs-lookup"><span data-stu-id="4227f-121">That is because the Time Series viewer combines the ARIMA and ARTXP information for each data series into a single representation.</span></span>  
  
4.  <span data-ttu-id="4227f-122">Clique em qualquer nó folha na árvore.</span><span class="sxs-lookup"><span data-stu-id="4227f-122">Click any leaf node in the tree.</span></span>  
  
     <span data-ttu-id="4227f-123">Nós rotulados como **Série de Dados** sempre são nós folha e podem conter uma equação.</span><span class="sxs-lookup"><span data-stu-id="4227f-123">Nodes that are labeled as **Data Series** are always leaf nodes and can contain an equation.</span></span> <span data-ttu-id="4227f-124">Se um nó **(All)** não tiver nenhum nó filho, ele também poderá conter uma equação.</span><span class="sxs-lookup"><span data-stu-id="4227f-124">If an **(All)** node has no child nodes, it can also contain an equation.</span></span>  
  
5.  <span data-ttu-id="4227f-125">Se a **Legenda de Mineração** não estiver disponível, clique com o botão direito do mouse no nó e selecione **Mostrar Legenda**.</span><span class="sxs-lookup"><span data-stu-id="4227f-125">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
     <span data-ttu-id="4227f-126">A fórmula ARTXP é exibida na primeira metade da **Legenda de Mineração**, como a **Equação de nó de árvore**.</span><span class="sxs-lookup"><span data-stu-id="4227f-126">The ARTXP formula is displayed in the first half of the **Mining Legend**, as the **Tree node equation**.</span></span>  
  
### <a name="to-view-the-arima-formula-for-a-time-series-model"></a><span data-ttu-id="4227f-127">Para exibir a fórmula de ARIMA para um modelo de série temporal</span><span class="sxs-lookup"><span data-stu-id="4227f-127">To view the ARIMA formula for a time series model</span></span>  
  
1.  <span data-ttu-id="4227f-128">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selecione o modelo de série temporal que você quer exibir e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="4227f-128">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the time series model that you want to view, and click **Browse**.</span></span>  
  
     <span data-ttu-id="4227f-129">-- ou --</span><span class="sxs-lookup"><span data-stu-id="4227f-129">-- or --</span></span>  
  
     <span data-ttu-id="4227f-130">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], selecione o modelo de série temporal e clique na guia **Visualizador do Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="4227f-130">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the time series model, and then click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="4227f-131">Clique na guia **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="4227f-131">Click the **Model** tab.</span></span>  
  
3.  <span data-ttu-id="4227f-132">Se o modelo contiver várias árvores, selecione uma única árvore na lista suspensa **Árvore** .</span><span class="sxs-lookup"><span data-stu-id="4227f-132">If the model contains multiple trees, select a single tree from the **Tree** drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4227f-133">O modelo sempre terá várias árvores se você incluir mais de uma série de dados.</span><span class="sxs-lookup"><span data-stu-id="4227f-133">The model will always have multiple trees if you include more than one data series.</span></span>  
  
4.  <span data-ttu-id="4227f-134">Clique em qualquer nó na árvore.</span><span class="sxs-lookup"><span data-stu-id="4227f-134">Click any node in the tree.</span></span>  
  
     <span data-ttu-id="4227f-135">A fórmula de ARIMA é exibida na segunda metade da **Legenda de Mineração**, como a **Equação ARIMA**.</span><span class="sxs-lookup"><span data-stu-id="4227f-135">The ARIMA formula is displayed in the second half of the **Mining Legend**, as the **ARIMA equation**.</span></span>  
  
5.  <span data-ttu-id="4227f-136">Se a **Legenda de Mineração** não estiver disponível, clique com o botão direito do mouse no nó e selecione **Mostrar Legenda**.</span><span class="sxs-lookup"><span data-stu-id="4227f-136">If the **Mining Legend** is not available, right-click the node, and select **Show Legend**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4227f-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4227f-137">See Also</span></span>  
 <span data-ttu-id="4227f-138">[Tarefas e instruções do Visualizador do modelo de mineração](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="4227f-138">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="4227f-139">[Procurar um modelo usando o Visualizador do Microsoft Time Series](browse-a-model-using-the-microsoft-time-series-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="4227f-139">[Browse a Model Using the Microsoft Time Series Viewer](browse-a-model-using-the-microsoft-time-series-viewer.md) </span></span>  
 [<span data-ttu-id="4227f-140">Exemplos de consulta de um modelo de série temporal</span><span class="sxs-lookup"><span data-stu-id="4227f-140">Time Series Model Query Examples</span></span>](time-series-model-query-examples.md)  
  
  
