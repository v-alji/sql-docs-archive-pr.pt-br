---
title: Guia gráfico (visualizadores do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.timeseries.chart.f1
ms.assetid: 8803cdbb-f1b3-436c-994d-ee662ecf64dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c4d3aefb785bf3b5495a7c4c9a0cdea334b9d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571708"
---
# <a name="chart-tab-mining-model-viewers"></a><span data-ttu-id="be8cd-102">Guia Gráficos (Visualizadores do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="be8cd-102">Chart Tab (Mining Model Viewers)</span></span>
  <span data-ttu-id="be8cd-103">Use o painel **Gráfico** para exibir os dados históricos usados ao treinar um modelo de série temporal, junto com os valores previstos.</span><span class="sxs-lookup"><span data-stu-id="be8cd-103">Use the **Chart** pane to display the historical data used in training a time series model, together with the predicted values.</span></span> <span data-ttu-id="be8cd-104">O eixo vertical do gráfico representa o valor da série e o eixo horizontal representa o tempo.</span><span class="sxs-lookup"><span data-stu-id="be8cd-104">The vertical axis of the chart represents the value of the series, and the horizontal axis represents time.</span></span> <span data-ttu-id="be8cd-105">Previsões futuras serão representadas por uma linha pontilhada.</span><span class="sxs-lookup"><span data-stu-id="be8cd-105">Future predictions are represented by a dotted line.</span></span>  
  
 <span data-ttu-id="be8cd-106">**Para obter mais informações:** [Algoritmo MTS](data-mining/microsoft-time-series-algorithm.md)e [Procurar um modelo usando o visualizador MTS](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="be8cd-106">**For More Information:** [Microsoft Time Series Algorithm](data-mining/microsoft-time-series-algorithm.md), [Browse a Model Using the Microsoft Time Series Viewer](data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="be8cd-107">Opções</span><span class="sxs-lookup"><span data-stu-id="be8cd-107">Options</span></span>  
 <span data-ttu-id="be8cd-108">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="be8cd-108">**Refresh viewer content**</span></span>  
 <span data-ttu-id="be8cd-109">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="be8cd-109">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="be8cd-110">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="be8cd-110">**Mining Model**</span></span>  
 <span data-ttu-id="be8cd-111">Escolha um modelo de mineração dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="be8cd-111">Choose a mining model, from those in the current mining structure.</span></span> <span data-ttu-id="be8cd-112">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="be8cd-112">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="be8cd-113">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="be8cd-113">**Viewer**</span></span>  
 <span data-ttu-id="be8cd-114">Escolha um visualizador para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="be8cd-114">Choose a viewer to explore the selected mining model.</span></span> <span data-ttu-id="be8cd-115">Você pode usar o visualizador personalizado para modelo de série temporal, ou Visualizador de Conteúdo de Mineração da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be8cd-115">You can use the custom viewer for time series models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="be8cd-116">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="be8cd-116">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="be8cd-117">**Ampliar**</span><span class="sxs-lookup"><span data-stu-id="be8cd-117">**Zoom In**</span></span>  
 <span data-ttu-id="be8cd-118">Amplie a imagem do gráfico.</span><span class="sxs-lookup"><span data-stu-id="be8cd-118">Zoom in to the chart.</span></span>  
  
 <span data-ttu-id="be8cd-119">**Reduzir**</span><span class="sxs-lookup"><span data-stu-id="be8cd-119">**Zoom Out**</span></span>  
 <span data-ttu-id="be8cd-120">Reduza a imagem do gráfico.</span><span class="sxs-lookup"><span data-stu-id="be8cd-120">Zoom out from the chart.</span></span>  
  
 <span data-ttu-id="be8cd-121">**Dimensionar diagrama para ajustar à janela**</span><span class="sxs-lookup"><span data-stu-id="be8cd-121">**Scale diagram to fit window**</span></span>  
 <span data-ttu-id="be8cd-122">Reduza o gráfico até que ele se ajuste totalmente na tela.</span><span class="sxs-lookup"><span data-stu-id="be8cd-122">Zoom out from the chart until the whole chart fits within the screen.</span></span>  
  
 <span data-ttu-id="be8cd-123">**ABS**</span><span class="sxs-lookup"><span data-stu-id="be8cd-123">**Abs**</span></span>  
 <span data-ttu-id="be8cd-124">Alterne entre duas exibições de gráfico: na exibição padrão, os números são mostrados em relação à distribuição global (como percentual).</span><span class="sxs-lookup"><span data-stu-id="be8cd-124">Switch between two chart views: in the default view numbers are graphed relative to the overall distribution (as percentage).</span></span> <span data-ttu-id="be8cd-125">Se você clicar em **Abs**, os números serão mostrados como valores absolutos.</span><span class="sxs-lookup"><span data-stu-id="be8cd-125">If you click **Abs**, the numbers are graphed as absolute values.</span></span>  
  
 <span data-ttu-id="be8cd-126">**Copiar os gráficos para a área de transferência**</span><span class="sxs-lookup"><span data-stu-id="be8cd-126">**Copy the charts to the clipboard**</span></span>  
 <span data-ttu-id="be8cd-127">Copie todo o gráfico para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="be8cd-127">Copy the complete chart to the clipboard.</span></span>  
  
 <span data-ttu-id="be8cd-128">**Mostrar Desvios**</span><span class="sxs-lookup"><span data-stu-id="be8cd-128">**Show Deviations**</span></span>  
 <span data-ttu-id="be8cd-129">Selecione esta opção para adicionar barras de erro ao gráfico.</span><span class="sxs-lookup"><span data-stu-id="be8cd-129">Select this option to add error bars to the graph.</span></span> <span data-ttu-id="be8cd-130">Barras de erros representam a variância das previsões e, portanto, só aparecem nos valores previstos.</span><span class="sxs-lookup"><span data-stu-id="be8cd-130">Error bars represent the variance of the predictions and therefore appear only on the predicted values.</span></span>  
  
 <span data-ttu-id="be8cd-131">**Etapas de previsão**</span><span class="sxs-lookup"><span data-stu-id="be8cd-131">**Prediction steps**</span></span>  
 <span data-ttu-id="be8cd-132">Escolha quantas etapas futuras você deseja consultar no visualizador.</span><span class="sxs-lookup"><span data-stu-id="be8cd-132">Choose how many future time steps you want to see in the viewer.</span></span>  
  
 <span data-ttu-id="be8cd-133">**Seleção de série**</span><span class="sxs-lookup"><span data-stu-id="be8cd-133">**Series selection**</span></span>  
 <span data-ttu-id="be8cd-134">Abra uma caixa de diálogo da qual você poderá selecionar séries para incluir no visualizador.</span><span class="sxs-lookup"><span data-stu-id="be8cd-134">Open a dialog box from which you can select series to include in the viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be8cd-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="be8cd-135">See Also</span></span>  
 <span data-ttu-id="be8cd-136">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="be8cd-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="be8cd-137">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="be8cd-137">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="be8cd-138">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="be8cd-138">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
