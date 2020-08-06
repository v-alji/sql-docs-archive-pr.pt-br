---
title: Guia modelo (visualizadores do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.timeseries.decisiontree.f1
ms.assetid: 50570bb4-fcac-411e-b530-0398437efda7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 656468b2b850502ff4be32fbdbe501c775f7a3b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683165"
---
# <a name="model-tab-mining-model-viewers"></a><span data-ttu-id="3133b-102">Guia Modelos (Visualizadores do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="3133b-102">Model Tab (Mining Model Viewers)</span></span>
  <span data-ttu-id="3133b-103">A guia **Modelo** no Visualizador MTS exibe uma representação de uma série temporal como um nó em um gráfico, semelhante aos usados em modelos de árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="3133b-103">The **Model** tab in the Microsoft Time Series Viewer displays a representation of a time series as a node in a graph, similar to those used in decision tree models.</span></span>  
  
 <span data-ttu-id="3133b-104">Use esta exibição de um modelo de série temporal para extrair informações úteis sobre a análise de série temporal, inclusive a equação para o gráfico, as condições de ARIMA e os coeficientes.</span><span class="sxs-lookup"><span data-stu-id="3133b-104">Use this view of a time series model to extract useful information about the time series analysis, including the equation for the graph, the ARIMA terms, and the coefficients.</span></span>  
  
 <span data-ttu-id="3133b-105">**Para obter mais informações:** [algoritmo MTS](data-mining/microsoft-time-series-algorithm.md), [Procurar um modelo usando o visualizador MTS](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md), [algoritmo MTS](data-mining/microsoft-time-series-algorithm.md)</span><span class="sxs-lookup"><span data-stu-id="3133b-105">**For More Information:** [Microsoft Time Series Algorithm](data-mining/microsoft-time-series-algorithm.md), [Browse a Model Using the Microsoft Time Series Viewer](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md), [Microsoft Time Series Algorithm](data-mining/microsoft-time-series-algorithm.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="3133b-106">Opções</span><span class="sxs-lookup"><span data-stu-id="3133b-106">Options</span></span>  
 <span data-ttu-id="3133b-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="3133b-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="3133b-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="3133b-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="3133b-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="3133b-109">**Mining Model**</span></span>  
 <span data-ttu-id="3133b-110">Escolha um modelo de mineração para exibição.</span><span class="sxs-lookup"><span data-stu-id="3133b-110">Choose a mining model to view.</span></span> <span data-ttu-id="3133b-111">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="3133b-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="3133b-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="3133b-112">**Viewer**</span></span>  
 <span data-ttu-id="3133b-113">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="3133b-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="3133b-114">Você pode usar o visualizador personalizado para este tipo de modelo ou o visualizador de **Árvore de Conteúdo Genérica da Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="3133b-114">You can use the custom viewer for this model type, or the **Microsoft Generic Content Tree** viewer.</span></span> <span data-ttu-id="3133b-115">Você também poderá usar visualizadores de plug-in, se houver algum.</span><span class="sxs-lookup"><span data-stu-id="3133b-115">You can also use plug-in viewers, if available.</span></span>  
  
 <span data-ttu-id="3133b-116">**Ampliar**</span><span class="sxs-lookup"><span data-stu-id="3133b-116">**Zoom In**</span></span>  
 <span data-ttu-id="3133b-117">Amplie a imagem do diagrama.</span><span class="sxs-lookup"><span data-stu-id="3133b-117">Zoom in to the diagram.</span></span>  
  
 <span data-ttu-id="3133b-118">**Reduzir**</span><span class="sxs-lookup"><span data-stu-id="3133b-118">**Zoom Out**</span></span>  
 <span data-ttu-id="3133b-119">Reduza a imagem do diagrama.</span><span class="sxs-lookup"><span data-stu-id="3133b-119">Zoom out from the diagram.</span></span>  
  
 <span data-ttu-id="3133b-120">**Copiar Exibição do Gráfico**</span><span class="sxs-lookup"><span data-stu-id="3133b-120">**Copy Graph View**</span></span>  
 <span data-ttu-id="3133b-121">Copie a seção visível do diagrama para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="3133b-121">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="3133b-122">**Copiar Todo o Gráfico**</span><span class="sxs-lookup"><span data-stu-id="3133b-122">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="3133b-123">Copie todo o diagrama na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="3133b-123">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="3133b-124">**Dimensionar diagrama para ajustar à janela**</span><span class="sxs-lookup"><span data-stu-id="3133b-124">**Scale diagram to fit window**</span></span>  
 <span data-ttu-id="3133b-125">Reduza o diagrama até que o diagrama inteiro se ajuste na tela.</span><span class="sxs-lookup"><span data-stu-id="3133b-125">Zoom out from the diagram until the whole diagram fits within the screen.</span></span>  
  
 <span data-ttu-id="3133b-126">**Três**</span><span class="sxs-lookup"><span data-stu-id="3133b-126">**Tree**</span></span>  
 <span data-ttu-id="3133b-127">Selecione uma árvore da lista suspensa para ser mostrada no visualizador</span><span class="sxs-lookup"><span data-stu-id="3133b-127">Select a tree from the dropdown list to show in the viewer</span></span>  
  
 <span data-ttu-id="3133b-128">Se o modelo de série temporal incluir várias séries, cada série será representada como uma árvore separada.</span><span class="sxs-lookup"><span data-stu-id="3133b-128">If the time series model includes multiple series, each series is represented as a separate tree.</span></span> <span data-ttu-id="3133b-129">Por exemplo, se você criou previsões com o passar do tempo para [Quantidade] e [Quantidade de Vendas], uma série separada foi criada para cada atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="3133b-129">For example, if you created predictions over time for both [Quantity] and [Sales Amount], a separate series is created for each predictable attribute.</span></span>  
  
 <span data-ttu-id="3133b-130">O comprimento da cor que é realçada na lista indica o número de níveis na árvore.</span><span class="sxs-lookup"><span data-stu-id="3133b-130">The length of the color highlighting in the list indicates the number of levels in the tree.</span></span> <span data-ttu-id="3133b-131">Ou seja, um modelo de série temporal que pode ser representado por um único nó teria uma única equação para descrever a tendência e a barra colorida seria muito curta.</span><span class="sxs-lookup"><span data-stu-id="3133b-131">That is, a time series model that can be represented by a single node would have a single equation to describe the trend and the colored bar would be very short.</span></span> <span data-ttu-id="3133b-132">(Logicamente, se o modelo for MIXED, o nó conterá uma equação ARIMA e ARTXP.)</span><span class="sxs-lookup"><span data-stu-id="3133b-132">(Of course, if the model is a MIXED model, the node will contain both an ARIMA and an ARTXP equation.)</span></span>  
  
 <span data-ttu-id="3133b-133">Se a árvore mostrada na lista suspensa tiver uma barra colorida mais longa, isso significará que o modelo tem muitas ramificações na árvore.</span><span class="sxs-lookup"><span data-stu-id="3133b-133">If the tree shown in the dropdown list has a longer colored bar, it means the model has many branches in the tree.</span></span> <span data-ttu-id="3133b-134">Ramificar significa que a regressão é mais complexa e o modelo tem que ser quebrado em vários segmentos, com uma equação diferente (ou par de equações) em cada nó.</span><span class="sxs-lookup"><span data-stu-id="3133b-134">Branching means the regression is more complex and the model has to be broken into multiple segments, with a different equation (or pair of equations) in each node.</span></span>  
  
 <span data-ttu-id="3133b-135">**Tela de fundo**</span><span class="sxs-lookup"><span data-stu-id="3133b-135">**Background**</span></span>  
 <span data-ttu-id="3133b-136">Use este controle para selecionar o estado que é representado pela cor do plano de fundo em cada nó.</span><span class="sxs-lookup"><span data-stu-id="3133b-136">Use this control to select the state that is represented by the background color in each node.</span></span>  
  
 <span data-ttu-id="3133b-137">**Expansão padrão**</span><span class="sxs-lookup"><span data-stu-id="3133b-137">**Default Expansion**</span></span>  
 <span data-ttu-id="3133b-138">Ajuste o número de níveis padrão exibidos para todas as árvores do modelo.</span><span class="sxs-lookup"><span data-stu-id="3133b-138">Adjust the default number of levels that are displayed for all trees in the model.</span></span>  
  
 <span data-ttu-id="3133b-139">**Mostrar Nível**</span><span class="sxs-lookup"><span data-stu-id="3133b-139">**Show Level**</span></span>  
 <span data-ttu-id="3133b-140">Altere o número de níveis mostrados na árvore.</span><span class="sxs-lookup"><span data-stu-id="3133b-140">Change the number of levels that are shown in the tree.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3133b-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3133b-141">See Also</span></span>  
 <span data-ttu-id="3133b-142">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="3133b-142">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="3133b-143">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="3133b-143">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="3133b-144">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="3133b-144">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
