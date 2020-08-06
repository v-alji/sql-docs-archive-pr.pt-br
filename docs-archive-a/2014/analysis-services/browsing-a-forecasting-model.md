---
title: Navegando em um modelo de previsão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- forecasting [data mining]
- mining models, viewing
- mining model, time series
- time series [data mining]
ms.assetid: ad35a528-1949-4048-8678-3b9760c1c88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d0b188c4ed6fba9bc5b1082725b17c99081c1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571117"
---
# <a name="browsing-a-forecasting-model"></a><span data-ttu-id="9be5a-102">Procurando um modelo de previsão</span><span class="sxs-lookup"><span data-stu-id="9be5a-102">Browsing a Forecasting Model</span></span>
  <span data-ttu-id="9be5a-103">Quando você abre um modelo de previsão usando **procurar**, o modelo é exibido em um visualizador interativo, semelhante ao Visualizador de modelos de série temporal no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9be5a-103">When you open a forecasting model using **Browse**, the model is displayed in an interactive viewer, similar to the time series model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="9be5a-104">O visualizador ajuda a explorar tendências, comparar séries, criar previsões e obter informações sobre o modelo e os dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="9be5a-104">The viewer helps you explore trends, compare series, create predictions, and get information about the model and the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="9be5a-105">Explorar o modelo</span><span class="sxs-lookup"><span data-stu-id="9be5a-105">Explore the Model</span></span>  
 <span data-ttu-id="9be5a-106">O Visualizador de **navegação** para modelos de previsão fornece uma exibição de gráfico, que mostra as tendências ao longo do tempo e permite que você crie previsões e uma exibição de modelo, que representa a série temporal como uma árvore de decisão ou uma árvore de regressão.</span><span class="sxs-lookup"><span data-stu-id="9be5a-106">The **Browse** viewer for forecasting models provides a chart view, which shows the trends over time and lets you create predictions, and a model view, which represents the time series as a decision tree or a regression tree.</span></span>  
  
-   [<span data-ttu-id="9be5a-107">Modo de exibição de Gráfico</span><span class="sxs-lookup"><span data-stu-id="9be5a-107">Chart view</span></span>](#bkmk_charts)  
  
-   [<span data-ttu-id="9be5a-108">Exibição de modelo</span><span class="sxs-lookup"><span data-stu-id="9be5a-108">Model view</span></span>](#bkmk_Model)  
  
 <span data-ttu-id="9be5a-109">Para fazer experiências com um modelo de previsão, você pode usar os dados de exemplo na guia Previsão da pasta de trabalho de dados de exemplo e criar um modelo de série temporal usando o [Assistente de previsão &#40;suplementos de mineração de dados para excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) na faixa de bits de **mineração de dados** ou [prever &#40;ferramentas de análise de tabela para o&#41;do Excel](forecast-table-analysis-tools-for-excel.md) na faixa de guia **analisar** .</span><span class="sxs-lookup"><span data-stu-id="9be5a-109">To experiment with a forecasting model, you can use the sample data on the Forecast tab of the sample data workbook, and build a time series model using the [Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) in the **Data Mining** ribbon, or [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) in the **Analyze** ribbon.</span></span>  
  
###  <a name="chart"></a><a name="bkmk_charts"></a><span data-ttu-id="9be5a-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="9be5a-110">Chart</span></span>  
 <span data-ttu-id="9be5a-111">A guia **gráfico** exibe a tendência em sua série de dados ao longo do tempo, junto com os valores previstos.</span><span class="sxs-lookup"><span data-stu-id="9be5a-111">The **Chart** tab displays the trend in your data series over time, together with the predicted values.</span></span> <span data-ttu-id="9be5a-112">O eixo vertical do gráfico representa os valores da série e o eixo horizontal representa o tempo.</span><span class="sxs-lookup"><span data-stu-id="9be5a-112">The vertical axis of the chart represents the values of the series, and the horizontal axis represents time.</span></span>  
  
##### <a name="explore-the-forecasting-chart"></a><span data-ttu-id="9be5a-113">Explorar o gráfico de previsão</span><span class="sxs-lookup"><span data-stu-id="9be5a-113">Explore the forecasting chart</span></span>  
  
1.  <span data-ttu-id="9be5a-114">Este modelo contém várias séries temporais, mas para simplificar o gráfico, você poderá exibir uma única série ou algumas séries relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9be5a-114">This model contains multiple time series, but to simplify the chart, you can display a single series, or just a few related series.</span></span>  
  
     <span data-ttu-id="9be5a-115">![previsões históricas no modelo de previsão](media/dm13-forecast-chart-historicpredictions.gif "previsões históricas no modelo de previsão")</span><span class="sxs-lookup"><span data-stu-id="9be5a-115">![historical predictions in the forecasting model](media/dm13-forecast-chart-historicpredictions.gif "historical predictions in the forecasting model")</span></span>  
  
     <span data-ttu-id="9be5a-116">Use as caixas de seleção para selecionar a previsão apenas para América do Norte e apenas para Valor de vendas.</span><span class="sxs-lookup"><span data-stu-id="9be5a-116">Use the check boxes to select the forecast for just North America, and just for sales Amount.</span></span>  
  
2.  <span data-ttu-id="9be5a-117">Clique em **etapas de previsão** e digite um novo valor para controlar quantos valores de tempo futuros você deseja ver no gráfico.</span><span class="sxs-lookup"><span data-stu-id="9be5a-117">Click **Prediction Steps** and type a new value to control how many future time values you want to see in the chart.</span></span>  
  
     <span data-ttu-id="9be5a-118">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="9be5a-118">The default is 5.</span></span>  
  
3.  <span data-ttu-id="9be5a-119">Clique em qualquer ponto na linha, seja o histórico ou futuro, para ver os valores exatos para esse ponto no tempo, exibidos na **legenda de mineração**.</span><span class="sxs-lookup"><span data-stu-id="9be5a-119">Click any point in the line, either historical or future, to see the exact values for that point in time, displayed in the **Mining Legend**.</span></span>  
  
4.  <span data-ttu-id="9be5a-120">O gráfico exibe dados históricos e futuros.</span><span class="sxs-lookup"><span data-stu-id="9be5a-120">The chart displays both historical and future data.</span></span> <span data-ttu-id="9be5a-121">Observe a linha pontilhada, com um plano de fundo sombreado.</span><span class="sxs-lookup"><span data-stu-id="9be5a-121">Note the dotted line, with a shaded background.</span></span> <span data-ttu-id="9be5a-122">Esses valores são as previsões futuras, com base no modelo.</span><span class="sxs-lookup"><span data-stu-id="9be5a-122">These values are the future predictions, based on the model.</span></span>  
  
     <span data-ttu-id="9be5a-123">Os dados históricos (usados para criar o modelo) são mostrados no lado esquerdo do gráfico.</span><span class="sxs-lookup"><span data-stu-id="9be5a-123">The historical data (which you used to build the model) is shown in the left side of the chart.</span></span>  
  
5.  <span data-ttu-id="9be5a-124">Selecione a opção **Mostrar previsões históricas** para ter um sentido para a estabilidade da série temporal.</span><span class="sxs-lookup"><span data-stu-id="9be5a-124">Select the **Show historic predictions** option to get a sense for the stability of the time series.</span></span>  
  
     <span data-ttu-id="9be5a-125">![previsões para uma única série do modelo](media/dm13-forecast-chart-singleseries.gif "previsões para uma única série do modelo")</span><span class="sxs-lookup"><span data-stu-id="9be5a-125">![forecasts for a single series in the model](media/dm13-forecast-chart-singleseries.gif "forecasts for a single series in the model")</span></span>  
  
     <span data-ttu-id="9be5a-126">As previsões históricas são valores previstos com base nas séries para esse ponto, que são comparadas com os valores reais históricos.</span><span class="sxs-lookup"><span data-stu-id="9be5a-126">Historical predictions are values predicted based on the series to that point, which are compared to actual historical values.</span></span> <span data-ttu-id="9be5a-127">Se a linha pontilhada (com os valores previstos) estiver muito distante da linha sólida (os valores reais), isso significará que a primeira parte da série talvez não exatamente preveja os valores posteriores.</span><span class="sxs-lookup"><span data-stu-id="9be5a-127">If the dotted line (with the predicted values) is far apart from the solid line (the actual values), it means the first part of the series perhaps does not accurately predict the later values.</span></span> <span data-ttu-id="9be5a-128">Você poderá precisar de mais dados ou isso pode apenas ser um indicador de volatilidade no ciclo.</span><span class="sxs-lookup"><span data-stu-id="9be5a-128">You might need more data, or it might simply be an indicator of volatility in the cycle.</span></span>  
  
6.  <span data-ttu-id="9be5a-129">Selecione a opção **Mostrar desvios** para exibir barras de erro no gráfico.</span><span class="sxs-lookup"><span data-stu-id="9be5a-129">Select the **Show Deviations** option to display error bars in the chart.</span></span>  
  
     <span data-ttu-id="9be5a-130">As barras de erro permitem avaliar visualmente a variação das previsões.</span><span class="sxs-lookup"><span data-stu-id="9be5a-130">The error bars let you visually assess the variability of the predictions.</span></span> <span data-ttu-id="9be5a-131">A qualidade das previsões varia dependendo dos seus dados de origem, mas, à medida que você aumenta o número de etapas de previsão, deverá ver os desvios aumentarem continuamente.</span><span class="sxs-lookup"><span data-stu-id="9be5a-131">The quality of predictions varies depending on your source data, but as you increase the number of prediction steps, you should see the deviations steadily increase.</span></span>  
  
 <span data-ttu-id="9be5a-132">**Dicas**</span><span class="sxs-lookup"><span data-stu-id="9be5a-132">**Tips**</span></span>  
  
-   <span data-ttu-id="9be5a-133">Para alternar a exibição da **legenda de mineração**, clique com o botão direito do mouse em qualquer ponto no gráfico.</span><span class="sxs-lookup"><span data-stu-id="9be5a-133">To toggle display of the **Mining Legend**, right-click any point in the chart.</span></span>  
  
     <span data-ttu-id="9be5a-134">É possível exibir um intervalo de tempo específico clicando no gráfico, arrastando uma seleção de tempo pelo gráfico e clicando novamente para ampliar o intervalo selecionado.</span><span class="sxs-lookup"><span data-stu-id="9be5a-134">You can view a specific time range by clicking the chart, dragging a time selection across the chart, and then clicking again to zoom in on the selected range.</span></span>  
  
-   <span data-ttu-id="9be5a-135">Para obter uma cópia do gráfico atual, clique em **copiar para o Excel**e, em seguida, clique em uma planilha no Excel.</span><span class="sxs-lookup"><span data-stu-id="9be5a-135">To get a copy of the current chart, click **Copy to Excel**, then click a worksheet in Excel.</span></span> <span data-ttu-id="9be5a-136">Um gráfico é inserido na planilha usando todas as opções que você tiver definido, incluindo uma legenda.</span><span class="sxs-lookup"><span data-stu-id="9be5a-136">A graphic is inserted in the sheet using all the options you had set, including a legend.</span></span>  
  
     <span data-ttu-id="9be5a-137">No entanto, esse gráfico é estático para que você não possa editar a legenda ou exibir os dados subjacentes; Se você precisar de uma exibição de gráfico mais interativa, use os [visualizadores do Visio](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="9be5a-137">However, this graphic is static so you cannot edit the legend or view the underlying data; if you need a more interactive chart view, use the [Visio viewers](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span></span>  
  
-   <span data-ttu-id="9be5a-138">Clique em **ABS** na barra de menus do visualizador para alternar entre curvas absolutas e relativas.</span><span class="sxs-lookup"><span data-stu-id="9be5a-138">Click **Abs** in the viewer menu bar to toggle between absolute and relative curves.</span></span>  
  
     <span data-ttu-id="9be5a-139">Essa opção será útil se seu gráfico tiver vários modelos, mas a escala dos dados para cada modelo será muito diferente.</span><span class="sxs-lookup"><span data-stu-id="9be5a-139">This option is useful if your chart contains multiple models, but the scale of the data for each model is very different.</span></span>  
  
     <span data-ttu-id="9be5a-140">Por exemplo, se as lojas da região do Pacífico forem novas e as vendas estiverem baixas, e se os valores absolutos estiverem sendo usados, a linha que mostra as vendas do Pacífico poderá aparecer inalterada, dificultando a visualização das alterações reais, enquanto os outros modelos serão exibidos em uma escala mais comum.</span><span class="sxs-lookup"><span data-stu-id="9be5a-140">For example, if the Pacific region stores were new and sales were low, and if absolute values are used, the line showing Pacific sales might appear flat, making it difficult to see actual changes, whereas the other models would be displayed at a more normal scale.</span></span>  
  
     <span data-ttu-id="9be5a-141">Ao alternar a exibição para usar valores relativos, você poderá normalizar a escala de modelos diferentes e exibir diferenças como uma porcentagem de alteração.</span><span class="sxs-lookup"><span data-stu-id="9be5a-141">By switching the view to use relative values, you can normalize the scale of different models, and display differences as a percent of change.</span></span> <span data-ttu-id="9be5a-142">Quando a alteração é referente a cada modelo, ela pode ser exibida no mesmo gráfico sem distorção significativa.</span><span class="sxs-lookup"><span data-stu-id="9be5a-142">When change is relative to each model, they can be displayed in the same graph without significant distortion.</span></span>  
  
 [<span data-ttu-id="9be5a-143">Explorar o modelo</span><span class="sxs-lookup"><span data-stu-id="9be5a-143">Explore the Model</span></span>](#bkmk_Top)  
  
###  <a name="model"></a><a name="bkmk_Model"></a><span data-ttu-id="9be5a-144">Deprecia</span><span class="sxs-lookup"><span data-stu-id="9be5a-144">Model</span></span>  
 <span data-ttu-id="9be5a-145">Um modelo de previsão também pode ser representado como uma árvore de decisão ou, se a série for predominantemente linear, um modelo de regressão.</span><span class="sxs-lookup"><span data-stu-id="9be5a-145">A forecasting model can also be represented as a decision tree, or, if the series is mostly linear, a regression model.</span></span>  
  
 <span data-ttu-id="9be5a-146">Por exemplo, neste modelo, há uma diferença na fórmula de regressão com base em uma determinada condição, para que a árvore seja dividida em duas ramificações, cada uma com uma fórmula de regressão diferente.</span><span class="sxs-lookup"><span data-stu-id="9be5a-146">For example, in this model, there is a difference in the regression formula based on a certain condition, so the tree splits into two branches, each with a different regression formula.</span></span>  
  
 <span data-ttu-id="9be5a-147">![Filtrar série única no modelo de previsão](media/dm13-forecast-model-northamerica.gif "Filtrar série única no modelo de previsão")</span><span class="sxs-lookup"><span data-stu-id="9be5a-147">![Filter single series in the forecasting model](media/dm13-forecast-model-northamerica.gif "Filter single series in the forecasting model")</span></span>  
  
##### <a name="explore-the-forecasting-model-as-a-tree"></a><span data-ttu-id="9be5a-148">Explorar o modelo de previsão como uma árvore</span><span class="sxs-lookup"><span data-stu-id="9be5a-148">Explore the forecasting model as a tree</span></span>  
  
1.  <span data-ttu-id="9be5a-149">Clique na lista suspensa **árvore** e escolha um modelo a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="9be5a-149">Click the **Tree** dropdown list and choose a model to display.</span></span>  
  
     <span data-ttu-id="9be5a-150">Uma árvore separada ou nó de regressão é exibido para cada atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="9be5a-150">A separate tree or regression node is displayed for each predictable attribute.</span></span> <span data-ttu-id="9be5a-151">Por exemplo, se seus dados contiverem vendas para Europa, América do Norte e Pacífico, haverá três modelos diferentes, um para cada série de dados.</span><span class="sxs-lookup"><span data-stu-id="9be5a-151">For example, if your data contains sales for Europe, North America, and the Pacific, there would three different models, one for each data series.</span></span>  
  
2.  <span data-ttu-id="9be5a-152">Arraste o controle deslizante **Mostrar nível** para filtrar os níveis inferiores da árvore e concentre-se nas divisões mais importantes.</span><span class="sxs-lookup"><span data-stu-id="9be5a-152">Drag the **Show Level** slider to filter out lower levels of the tree, and focus on the most important splits.</span></span>  
  
3.  <span data-ttu-id="9be5a-153">Clique em cada nó para exibir algumas estatísticas descritivas na **legenda de mineração**.</span><span class="sxs-lookup"><span data-stu-id="9be5a-153">Click each node to view some descriptive statistics in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="9be5a-154">Quando você coloca o cursor do mouse sobre um nó, uma Dica de Ferramenta também exibe as mesmas estatísticas, bem como a fórmula completa que descreve esse nó.</span><span class="sxs-lookup"><span data-stu-id="9be5a-154">As you pause over a node with the mouse, a ToolTip also displays the same statistics, as well as the full formula describing that node.</span></span>  
  
4.  <span data-ttu-id="9be5a-155">Se você quiser copiar as informações na legenda de **mineração**, clique com o botão direito do mouse na **legenda de mineração**, selecione **copiar**e clique dentro de sua planilha do Excel.</span><span class="sxs-lookup"><span data-stu-id="9be5a-155">If you want to copy the information in the **Mining Legend**, right-click the **Mining Legend**, select **Copy**, and click inside your Excel worksheet.</span></span> <span data-ttu-id="9be5a-156">A opção **copiar para o Excel** copia o grafo, não as estatísticas.</span><span class="sxs-lookup"><span data-stu-id="9be5a-156">The **Copy to Excel** option copies the graph, not the statistics.</span></span>  
  
 [<span data-ttu-id="9be5a-157">Explorar o modelo</span><span class="sxs-lookup"><span data-stu-id="9be5a-157">Explore the Model</span></span>](#bkmk_Top)  
  
## <a name="see-also"></a><span data-ttu-id="9be5a-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9be5a-158">See Also</span></span>  
 [<span data-ttu-id="9be5a-159">Pesquisando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="9be5a-159">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
