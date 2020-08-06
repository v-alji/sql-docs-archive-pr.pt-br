---
title: Previsões de série temporal usando dados atualizados (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af73681d-ce1c-4b6e-b195-6df3d2fb5275
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2017defaba74071b1a12bee14a5d8907e4c71cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568928"
---
# <a name="time-series-predictions-using-updated-data-intermediate-data-mining-tutorial"></a><span data-ttu-id="4e284-102">Previsões de série temporal usando dados atualizados (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="4e284-102">Time Series Predictions using Updated Data (Intermediate Data Mining Tutorial)</span></span>
    
## <a name="creating-predictions-using-the-extended-sales-data"></a><span data-ttu-id="4e284-103">Criando previsões usando os dados de vendas estendidos</span><span class="sxs-lookup"><span data-stu-id="4e284-103">Creating Predictions using the Extended Sales Data</span></span>  
 <span data-ttu-id="4e284-104">Nesta lição, você criará uma consulta de previsão que adiciona os novos dados de vendas ao modelo.</span><span class="sxs-lookup"><span data-stu-id="4e284-104">In this lesson, you will create a prediction query that adds the new sales data to the model.</span></span> <span data-ttu-id="4e284-105">Ao estender o modelo com novos dados, você poderá obter previsões atualizadas que incluem os pontos de dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="4e284-105">By extending the model with new data, you can get up-to-date predictions that include the newest data points.</span></span>  
  
 <span data-ttu-id="4e284-106">Criar previsões de série temporal que usam novos dados é fácil: basta adicionar o parâmetro EXTEND_MODEL_CASES à função de [&#41;PredictTimeSeries &#40;DMX](/sql/dmx/predicttimeseries-dmx) , especificar a origem dos novos dados e especificar quantas previsões você deseja obter.</span><span class="sxs-lookup"><span data-stu-id="4e284-106">Creating time series predictions that use new data is easy: you simply add the parameter EXTEND_MODEL_CASES to the [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) function, specify the source of the new data, and specify how many predictions you want to get.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="4e284-107">O parâmetro EXTEND_MODEL_CASES é opcional; por padrão, o modelo é estendido a qualquer momento que você cria uma consulta de previsão de série temporal unindo novos dados como entradas.</span><span class="sxs-lookup"><span data-stu-id="4e284-107">The parameter EXTEND_MODEL_CASES is optional; by default the model is extended any time that you create a time series prediction query by joining new data as inputs.</span></span>  
  
#### <a name="to-build-the-prediction-query-and-add-new-data"></a><span data-ttu-id="4e284-108">Para criar a consulta de previsão e adicionar novos dados</span><span class="sxs-lookup"><span data-stu-id="4e284-108">To build the prediction query and add new data</span></span>  
  
1.  <span data-ttu-id="4e284-109">Se o modelo ainda não estiver aberto, clique duas vezes na estrutura de previsão e, no designer de mineração de dados, clique na guia **previsão do modelo de mineração** .</span><span class="sxs-lookup"><span data-stu-id="4e284-109">If the model is not already open, double-click the Forecasting structure, and in Data Mining Designer, click the **Mining Model Prediction** tab.</span></span>  
  
2.  <span data-ttu-id="4e284-110">No painel **modelo de mineração** , a previsão do modelo já deve estar selecionada.</span><span class="sxs-lookup"><span data-stu-id="4e284-110">In the **Mining Model** pane, the model Forecasting should already be selected.</span></span> <span data-ttu-id="4e284-111">Se não estiver selecionado, clique em **selecionar modelo**e, em seguida, selecione o modelo, previsão.</span><span class="sxs-lookup"><span data-stu-id="4e284-111">If it is not selected, click **Select Model**, and then select the model, Forecasting.</span></span>  
  
3.  <span data-ttu-id="4e284-112">No painel **selecionar tabela (s) de entrada** , clique em **selecionar tabela de casos**.</span><span class="sxs-lookup"><span data-stu-id="4e284-112">In the **Select Input Table(s)** pane, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="4e284-113">Na caixa de diálogo **selecionar tabela** , selecione a fonte de dados, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e284-113">In the **Select Table** dialog box, select the data source, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
     <span data-ttu-id="4e284-114">Na lista de exibições da fonte de dados, selecione NewSalesData e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e284-114">From the list of data source views, select NewSalesData and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4e284-115">Clique com o botão direito do mouse na superfície da área de design e selecione **Modificar Conexões**.</span><span class="sxs-lookup"><span data-stu-id="4e284-115">Right-click the surface of the design area and select **Modify Connections**.</span></span>  
  
6.  <span data-ttu-id="4e284-116">Usando a caixa de diálogo **modificar mapeamento** , mapeie as colunas no modelo para as colunas nos dados externos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4e284-116">Using the **Modify Mapping** dialog box, map the columns in the model to the columns in the external data as follows:</span></span>  
  
    -   <span data-ttu-id="4e284-117">Mapeie a coluna ReportingDate no modelo de mineração para a coluna NewDate nos dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="4e284-117">Map the ReportingDate column in the mining model to the NewDate column in the input data.</span></span>  
  
    -   <span data-ttu-id="4e284-118">Mapeie a coluna de valor no modelo de mineração para a coluna NewAmount nos dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="4e284-118">Map the Amount column in the mining model to the NewAmount column in the input data.</span></span>  
  
    -   <span data-ttu-id="4e284-119">Mapeie a coluna quantidade no modelo de mineração para a coluna NewQty nos dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="4e284-119">Map the Quantity column in the mining model to the NewQty column in the input data.</span></span>  
  
    -   <span data-ttu-id="4e284-120">Mapeie a coluna ModelRegion no modelo de mineração para a coluna série nos dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="4e284-120">Map the ModelRegion column in the mining model to the Series column in the input data.</span></span>  
  
7.  <span data-ttu-id="4e284-121">Agora você criará a consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="4e284-121">Now you will build the prediction query.</span></span>  
  
     <span data-ttu-id="4e284-122">Primeiramente, adicione uma coluna à consulta de previsão para produzir a série à qual a previsão se aplica.</span><span class="sxs-lookup"><span data-stu-id="4e284-122">First, add a column to the prediction query to output the series the prediction applies to.</span></span>  
  
    1.  <span data-ttu-id="4e284-123">Na grade, clique na primeira linha vazia, em **origem**, e selecione previsão.</span><span class="sxs-lookup"><span data-stu-id="4e284-123">In the grid, click the first empty row, under **Source**, and then select Forecasting.</span></span>  
  
    2.  <span data-ttu-id="4e284-124">Na coluna **campo** , selecione região do modelo e para **alias**, digite `Model Region` .</span><span class="sxs-lookup"><span data-stu-id="4e284-124">In the **Field** column, select Model Region and for **Alias**, type `Model Region`.</span></span>  
  
8.  <span data-ttu-id="4e284-125">Em seguida, adicione e edite a função de previsão.</span><span class="sxs-lookup"><span data-stu-id="4e284-125">Next, add and edit the prediction function.</span></span>  
  
    1.  <span data-ttu-id="4e284-126">Clique em uma linha vazia e, em **origem**, selecione **função de previsão**.</span><span class="sxs-lookup"><span data-stu-id="4e284-126">Click an empty row, and under **Source**, select **Prediction Function**.</span></span>  
  
    2.  <span data-ttu-id="4e284-127">Para **campo**, selecione **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="4e284-127">For **Field**, select **PredictTimeSeries**.</span></span>  
  
    3.  <span data-ttu-id="4e284-128">Para **alias**, digite **valores previstos**.</span><span class="sxs-lookup"><span data-stu-id="4e284-128">For **Alias**, type **Predicted Values**.</span></span>  
  
    4.  <span data-ttu-id="4e284-129">Arraste a quantidade de campo do painel **modelo de mineração** até a coluna **critérios/argumento** .</span><span class="sxs-lookup"><span data-stu-id="4e284-129">Drag the field Quantity from the **Mining Model** pane into the **Criteria/Argument** column.</span></span>  
  
    5.  <span data-ttu-id="4e284-130">Na coluna **critérios/argumento** , após o nome do campo, digite o seguinte texto: **5, EXTEND_MODEL_CASES**</span><span class="sxs-lookup"><span data-stu-id="4e284-130">In the **Criteria/Argument** column, after the field name, type the following text:  **5,EXTEND_MODEL_CASES**</span></span>  
  
         <span data-ttu-id="4e284-131">O texto completo da caixa de texto **critérios/argumento** deve ser o seguinte:`[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span><span class="sxs-lookup"><span data-stu-id="4e284-131">The complete text of the **Criteria/Argument** text box should be as follows: `[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span></span>  
  
9. <span data-ttu-id="4e284-132">Clique em **resultados** e examine os resultados.</span><span class="sxs-lookup"><span data-stu-id="4e284-132">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="4e284-133">As previsões começam em julho (o primeiro intervalo de tempo após o término dos dados originais) e terminam em novembro (o quinto intervalo de tempo após o término dos dados originais).</span><span class="sxs-lookup"><span data-stu-id="4e284-133">The predictions begin in July (the first time slice after the end of the original data) and end at November (the fifth time slice after the end of the original data).</span></span>  
  
 <span data-ttu-id="4e284-134">Você pode ver que para usar este tipo de consulta de previsão efetivamente, é preciso saber quando os dados antigos terminam, bem como quantos intervalos de tempo há nos novos dados.</span><span class="sxs-lookup"><span data-stu-id="4e284-134">You can see that to use this type of prediction query effectively, you need to know when the old data ends, as well as how many time slices there are in the new data.</span></span>  
  
 <span data-ttu-id="4e284-135">Por exemplo, neste modelo, a série de dados original terminava em junho, e os dados para os meses de julho, agosto e setembro.</span><span class="sxs-lookup"><span data-stu-id="4e284-135">For example, in this model, the original data series ended in June, and the data is for the months of July, August, and September.</span></span>  
  
 <span data-ttu-id="4e284-136">As previsões que usam EXTEND_MODEL_CASES sempre começam ao término da série de dados original.</span><span class="sxs-lookup"><span data-stu-id="4e284-136">Predictions that use EXTEND_MODEL_CASES always begin at the end of the original data series.</span></span> <span data-ttu-id="4e284-137">Portanto, se você desejar obter somente as previsões para os meses desconhecidos, deverá especificar os pontos de início e término para a previsão.</span><span class="sxs-lookup"><span data-stu-id="4e284-137">Therefore, if you want to get only the predictions for the unknown months, you need to specify the starting point and the end point for prediction.</span></span> <span data-ttu-id="4e284-138">Ambos os valores são especificados como vários intervalos de tempo que iniciam ao término dos dados antigos.</span><span class="sxs-lookup"><span data-stu-id="4e284-138">Both values are specified as a number of time slices starting at the end of the old data.</span></span>  
  
 <span data-ttu-id="4e284-139">O procedimento a seguir demonstra como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="4e284-139">The following procedure demonstrates how to do this.</span></span>  
  
### <a name="change-the-start-and-end-points-of-the-predictions"></a><span data-ttu-id="4e284-140">Alterar os pontos de início e término das previsões</span><span class="sxs-lookup"><span data-stu-id="4e284-140">Change the start and end points of the predictions</span></span>  
  
1.  <span data-ttu-id="4e284-141">Em previsão Construtor de Consultas, clique em **consulta** para alternar para a exibição DMX.</span><span class="sxs-lookup"><span data-stu-id="4e284-141">In Prediction Query Builder, click **Query** to switch to DMX view.</span></span>  
  
2.  <span data-ttu-id="4e284-142">Localize a instrução DMX que contém a função PredictTimeSeries e altere-a como segue:</span><span class="sxs-lookup"><span data-stu-id="4e284-142">Locate the DMX statement that contains the PredictTimeSeries function and change it as follows:</span></span>  
  
     `PredictTimeSeries([Forecasting 12].[Quantity],4,6,EXTEND_MODEL_CASES)`  
  
3.  <span data-ttu-id="4e284-143">Clique em **resultados** e examine os resultados.</span><span class="sxs-lookup"><span data-stu-id="4e284-143">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="4e284-144">Agora as previsões começam em outubro (o quarto intervalo de tempo, contando do término dos dados originais) e terminam em dezembro (o sexto intervalo de tempo, contando do término dos dados originais).</span><span class="sxs-lookup"><span data-stu-id="4e284-144">Now the predictions begin at October (the fourth time slice, counting from the end of the original data) and end at December (the sixth time slice, counting from the end of the original data).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4e284-145">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="4e284-145">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4e284-146">Previsões de série temporal usando dados de substituição &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="4e284-146">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="4e284-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e284-147">See Also</span></span>  
 <span data-ttu-id="4e284-148">[Referência técnica do algoritmo do Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4e284-148">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="4e284-149">Conteúdo do modelo de mineração para modelos de série temporal &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4e284-149">Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md)  
  
  
