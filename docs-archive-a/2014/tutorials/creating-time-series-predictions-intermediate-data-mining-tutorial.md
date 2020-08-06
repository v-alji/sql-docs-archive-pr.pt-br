---
title: Criando previsões de série temporal (tutorial intermediário de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: fb22cffa-ac99-4d34-ac4a-9c93068e33e8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1175cdffd1512e0cb876b9565dd0727a9f094c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571247"
---
# <a name="creating-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="d3f6f-102">Criando previsões de série temporal (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="d3f6f-102">Creating Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="d3f6f-103">Nas tarefas anteriores desta lição, você criou um modelo de série temporal e explorou os resultados.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-103">In the previous tasks in this lesson, you created a time series model and explored the results.</span></span> <span data-ttu-id="d3f6f-104">Por padrão, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sempre cria um conjunto de cinco (5) previsões para um modelo de série temporal e a exibe os valores previstos como parte do gráfico de previsão.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-104">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] always creates a set of five (5) predictions for a time series model and displays the predicted values as part of the forecasting chart.</span></span> <span data-ttu-id="d3f6f-105">No entanto, também é possível criar previsões criando-se consultas de previsão DMX.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-105">However, you can also create forecasts by building Data Mining Extensions (DMX) prediction queries.</span></span>  
  
 <span data-ttu-id="d3f6f-106">Nesta tarefa, você criará uma consulta de previsão que gera as mesmas previsões vistas no visualizador.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-106">In this task, you will create a prediction query that generates the same predictions that you saw in the viewer.</span></span> <span data-ttu-id="d3f6f-107">Esta tarefa supõe que você já tenha concluído as lições do Tutorial de data mining básico e esteja familiarizado com a forma de usar o Construtor de Consultas de Previsão.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-107">This task assumes that you have already completed the lessons in the Basic Data Mining Tutorial and are familiar with how to use Prediction Query Builder.</span></span> <span data-ttu-id="d3f6f-108">Agora você aprenderá a criar consultas específicas dos modelos de série temporal.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-108">You will now learn how to create queries specific to time series models.</span></span>  
  
## <a name="creating-time-series-predictions"></a><span data-ttu-id="d3f6f-109">Criando previsões de série temporal</span><span class="sxs-lookup"><span data-stu-id="d3f6f-109">Creating Time Series Predictions</span></span>  
 <span data-ttu-id="d3f6f-110">Tipicamente, a primeira etapa da criação de uma consulta de previsão é selecionar um modelo de mineração e tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-110">Typically, the first step in creating a prediction query is to select a mining model and input table.</span></span> <span data-ttu-id="d3f6f-111">No entanto, um modelo de série temporário não requer entrada adicional para uma previsão regular.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-111">However, a time series model does not require additional input for a regular prediction.</span></span> <span data-ttu-id="d3f6f-112">Dessa forma, não é preciso especificar uma nova fonte de dados ao fazer previsões, a menos que esteja adicionando dados ao modelo ou substituindo os dados.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-112">Therefore, you do not need to specify a new source of data when making predictions, unless you are adding data to the model or replacing the data.</span></span>  
  
 <span data-ttu-id="d3f6f-113">Para esta lição, você deve especificar o número de etapas de previsão.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-113">For this lesson, you must specify the number of prediction steps.</span></span> <span data-ttu-id="d3f6f-114">É possível especificar o nome da série para obter uma previsão para determinada combinação de um produto e de uma região.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-114">You can specify the series name, to get a prediction for a particular combination of a product and a region.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="d3f6f-115">Para selecionar um modelo e uma tabela de entrada</span><span class="sxs-lookup"><span data-stu-id="d3f6f-115">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="d3f6f-116">Na guia **previsão do modelo de mineração** do designer de mineração de dados, na caixa **modelo de mineração** , clique em **selecionar modelo**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-116">On the **Mining Model Prediction** tab of the Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="d3f6f-117">Na caixa de diálogo **selecionar modelo de mineração** , expanda a estrutura de previsão, selecione o modelo de **previsão** na lista e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-117">In the **Select Mining Model** dialog box, expand the Forecasting structure, select the **Forecasting** model from the list, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d3f6f-118">Ignore a caixa **selecionar tabela (s) de entrada** .</span><span class="sxs-lookup"><span data-stu-id="d3f6f-118">Ignore the **Select Input Table(s)** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d3f6f-119">Para um modelo de série temporal, você não precisa especificar uma entrada separada, a menos que esteja fazendo previsão cruzada.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-119">For a time series model, you do not need to specify a separate input unless you are doing cross-prediction.</span></span>  
  
4.  <span data-ttu-id="d3f6f-120">Na coluna **origem** , na grade da guia Previsão do **modelo de mineração** , clique na célula da primeira linha vazia e selecione **previsão modelo de mineração**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-120">In the **Source** column, in the grid on the **Mining Model Prediction** tab, click the cell in the first empty row, and then select **Forecasting mining model**.</span></span>  
  
5.  <span data-ttu-id="d3f6f-121">Na coluna **campo** , selecione **região do modelo**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-121">In the **Field** column, select **Model Region**.</span></span>  
  
     <span data-ttu-id="d3f6f-122">Essa ação adiciona o identificador da série à consulta de previsão para indicar a combinação de modelo e região a que a previsão se aplica.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-122">This action adds the series identifier to the prediction query to indicate the combination of model and region to which the prediction applies.</span></span>  
  
6.  <span data-ttu-id="d3f6f-123">Clique na próxima linha vazia na coluna **origem** e selecione **função de previsão**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-123">Click the next empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
7.  <span data-ttu-id="d3f6f-124">Na coluna **campo** , selecione **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-124">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d3f6f-125">Também é possível usar a função `Predict` com modelos de série temporal.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-125">You can also use the `Predict` function with time series models.</span></span> <span data-ttu-id="d3f6f-126">No entanto, por padrão, a função Prever cria somente uma previsão para cada série.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-126">However, by default, the Predict function creates only one prediction for each series.</span></span> <span data-ttu-id="d3f6f-127">Portanto, para especificar várias etapas de previsão, você deve usar a função **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="d3f6f-127">Therefore, to specify multiple prediction steps, you must use the **PredictTimeSeries** function.</span></span>  
  
8.  <span data-ttu-id="d3f6f-128">No painel **modelo de mineração** , selecione a coluna do modelo de mineração, **valor.**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-128">In the **Mining Model** pane, select the mining model column, **Amount.**</span></span> <span data-ttu-id="d3f6f-129">Arraste valor para a caixa **critérios/argumentos** para a função **PredictTimeSeries** que você adicionou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-129">Drag Amount to the **Criteria/Arguments** box for the **PredictTimeSeries** function that you added earlier.</span></span>  
  
9. <span data-ttu-id="d3f6f-130">Clique na caixa **critérios/argumentos** e digite uma vírgula, seguida por **5**, após o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-130">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="d3f6f-131">O texto na caixa **critérios/argumentos** agora deve exibir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d3f6f-131">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[Amount],5`  
  
10. <span data-ttu-id="d3f6f-132">Na coluna **alias** , digite `PredictAmount` .</span><span class="sxs-lookup"><span data-stu-id="d3f6f-132">In the **Alias** column, type `PredictAmount`.</span></span>  
  
11. <span data-ttu-id="d3f6f-133">Clique na próxima linha vazia na coluna **origem** e selecione a função de **previsão** novamente.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-133">Click the next empty row in the **Source** column, and then select **Prediction Function** again.</span></span>  
  
12. <span data-ttu-id="d3f6f-134">Na coluna **campo** , selecione **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-134">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
13. <span data-ttu-id="d3f6f-135">No painel **modelo de mineração** , selecione a quantidade da coluna e arraste-a para a caixa **critérios/argumentos** da segunda função **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="d3f6f-135">In the **Mining Model** pane, select the column Quantity, and then drag it into the **Criteria/Arguments** box for the second **PredictTimeSeries** function.</span></span>  
  
14. <span data-ttu-id="d3f6f-136">Clique na caixa **critérios/argumentos** e digite uma vírgula, seguida por **5**, após o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-136">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="d3f6f-137">O texto na caixa **critérios/argumentos** agora deve exibir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d3f6f-137">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[ Quantity],5`  
  
15. <span data-ttu-id="d3f6f-138">Na coluna **alias** , digite `PredictQuantity` .</span><span class="sxs-lookup"><span data-stu-id="d3f6f-138">In the **Alias** column, type `PredictQuantity`.</span></span>  
  
16. <span data-ttu-id="d3f6f-139">Clique em **alternar para a exibição de resultado da consulta**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-139">Click **Switch to query result view**.</span></span>  
  
     <span data-ttu-id="d3f6f-140">Os resultados da consulta serão exibidos em formato tabular.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-140">The results of the query are displayed in tabular format.</span></span>  
  
 <span data-ttu-id="d3f6f-141">Lembre-se de que você criou três tipos diferentes de resultados no construtor de consultas, um que usa valores de uma coluna e dois que obtêm valores de uma função de previsão.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-141">Remember that you created three different types of results in the query builder, one that uses values from a column, and two that get predicted values from a prediction function.</span></span> <span data-ttu-id="d3f6f-142">Dessa forma, os resultados da consulta contêm três colunas separadas.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-142">Therefore, the results of the query contain three separate columns.</span></span> <span data-ttu-id="d3f6f-143">A primeira coluna contém a lista de combinações de produtos e de regiões.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-143">The first column contains the list of product and region combinations.</span></span> <span data-ttu-id="d3f6f-144">A segunda e a terceira colunas contêm uma tabela aninhada de resultados de previsão.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-144">The second and third columns each contain a nested table of prediction results.</span></span> <span data-ttu-id="d3f6f-145">Cada tabela aninhada contém a etapa temporal e os valores previstos, como na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="d3f6f-145">Each nested table contains the time step and predicted values, such as the following table:</span></span>  
  
 <span data-ttu-id="d3f6f-146">Resultados de exemplo (os valores são truncados em duas casas decimais):</span><span class="sxs-lookup"><span data-stu-id="d3f6f-146">Example results (amounts are truncated to two decimal places):</span></span>  
  
 <span data-ttu-id="d3f6f-147">**Europa M200l PredictAmount**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-147">**M200 Europe PredictAmount**</span></span>  
  
|<span data-ttu-id="d3f6f-148">$TIME</span><span class="sxs-lookup"><span data-stu-id="d3f6f-148">$TIME</span></span>|<span data-ttu-id="d3f6f-149">Quantidade</span><span class="sxs-lookup"><span data-stu-id="d3f6f-149">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="d3f6f-150">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-150">7/25/2008</span></span>|<span data-ttu-id="d3f6f-151">99978, 0</span><span class="sxs-lookup"><span data-stu-id="d3f6f-151">99978.00</span></span>|  
|<span data-ttu-id="d3f6f-152">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-152">8/25/2008</span></span>|<span data-ttu-id="d3f6f-153">145575, 7</span><span class="sxs-lookup"><span data-stu-id="d3f6f-153">145575.07</span></span>|  
|<span data-ttu-id="d3f6f-154">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-154">9/25/2008</span></span>|<span data-ttu-id="d3f6f-155">116835,19</span><span class="sxs-lookup"><span data-stu-id="d3f6f-155">116835.19</span></span>|  
|<span data-ttu-id="d3f6f-156">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-156">10/25/2008</span></span>|<span data-ttu-id="d3f6f-157">116537,38</span><span class="sxs-lookup"><span data-stu-id="d3f6f-157">116537.38</span></span>|  
|<span data-ttu-id="d3f6f-158">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-158">11/25/2008</span></span>|<span data-ttu-id="d3f6f-159">107760,55</span><span class="sxs-lookup"><span data-stu-id="d3f6f-159">107760.55</span></span>|  
  
 <span data-ttu-id="d3f6f-160">**Europa M200l PredictQuantity**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-160">**M200 Europe PredictQuantity**</span></span>  
  
|<span data-ttu-id="d3f6f-161">$TIME</span><span class="sxs-lookup"><span data-stu-id="d3f6f-161">$TIME</span></span>|<span data-ttu-id="d3f6f-162">Quantidade</span><span class="sxs-lookup"><span data-stu-id="d3f6f-162">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="d3f6f-163">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-163">7/25/2008</span></span>|<span data-ttu-id="d3f6f-164">52</span><span class="sxs-lookup"><span data-stu-id="d3f6f-164">52</span></span>|  
|<span data-ttu-id="d3f6f-165">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-165">8/25/2008</span></span>|<span data-ttu-id="d3f6f-166">67</span><span class="sxs-lookup"><span data-stu-id="d3f6f-166">67</span></span>|  
|<span data-ttu-id="d3f6f-167">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-167">9/25/2008</span></span>|<span data-ttu-id="d3f6f-168">58</span><span class="sxs-lookup"><span data-stu-id="d3f6f-168">58</span></span>|  
|<span data-ttu-id="d3f6f-169">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-169">10/25/2008</span></span>|<span data-ttu-id="d3f6f-170">57</span><span class="sxs-lookup"><span data-stu-id="d3f6f-170">57</span></span>|  
|<span data-ttu-id="d3f6f-171">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-171">11/25/2008</span></span>|<span data-ttu-id="d3f6f-172">54</span><span class="sxs-lookup"><span data-stu-id="d3f6f-172">54</span></span>|  
  
 <span data-ttu-id="d3f6f-173">**M200 América do Norte-PredictAmount**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-173">**M200 North America - PredictAmount**</span></span>  
  
|<span data-ttu-id="d3f6f-174">$TIME</span><span class="sxs-lookup"><span data-stu-id="d3f6f-174">$TIME</span></span>|<span data-ttu-id="d3f6f-175">Quantidade</span><span class="sxs-lookup"><span data-stu-id="d3f6f-175">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="d3f6f-176">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-176">7/25/2008</span></span>|<span data-ttu-id="d3f6f-177">348533,93</span><span class="sxs-lookup"><span data-stu-id="d3f6f-177">348533.93</span></span>|  
|<span data-ttu-id="d3f6f-178">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-178">8/25/2008</span></span>|<span data-ttu-id="d3f6f-179">340097,98</span><span class="sxs-lookup"><span data-stu-id="d3f6f-179">340097.98</span></span>|  
|<span data-ttu-id="d3f6f-180">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-180">9/25/2008</span></span>|<span data-ttu-id="d3f6f-181">257986,19</span><span class="sxs-lookup"><span data-stu-id="d3f6f-181">257986.19</span></span>|  
|<span data-ttu-id="d3f6f-182">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-182">10/25/2008</span></span>|<span data-ttu-id="d3f6f-183">374658,24</span><span class="sxs-lookup"><span data-stu-id="d3f6f-183">374658.24</span></span>|  
|<span data-ttu-id="d3f6f-184">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-184">11/25/2008</span></span>|<span data-ttu-id="d3f6f-185">379241,44</span><span class="sxs-lookup"><span data-stu-id="d3f6f-185">379241.44</span></span>|  
  
 <span data-ttu-id="d3f6f-186">**M200 América do Norte-PredictQuantity**</span><span class="sxs-lookup"><span data-stu-id="d3f6f-186">**M200 North America - PredictQuantity**</span></span>  
  
|<span data-ttu-id="d3f6f-187">$TIME</span><span class="sxs-lookup"><span data-stu-id="d3f6f-187">$TIME</span></span>|<span data-ttu-id="d3f6f-188">Quantidade</span><span class="sxs-lookup"><span data-stu-id="d3f6f-188">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="d3f6f-189">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-189">7/25/2008</span></span>|<span data-ttu-id="d3f6f-190">272</span><span class="sxs-lookup"><span data-stu-id="d3f6f-190">272</span></span>|  
|<span data-ttu-id="d3f6f-191">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-191">8/25/2008</span></span>|<span data-ttu-id="d3f6f-192">152</span><span class="sxs-lookup"><span data-stu-id="d3f6f-192">152</span></span>|  
|<span data-ttu-id="d3f6f-193">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-193">9/25/2008</span></span>|<span data-ttu-id="d3f6f-194">250</span><span class="sxs-lookup"><span data-stu-id="d3f6f-194">250</span></span>|  
|<span data-ttu-id="d3f6f-195">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-195">10/25/2008</span></span>|<span data-ttu-id="d3f6f-196">181</span><span class="sxs-lookup"><span data-stu-id="d3f6f-196">181</span></span>|  
|<span data-ttu-id="d3f6f-197">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="d3f6f-197">11/25/2008</span></span>|<span data-ttu-id="d3f6f-198">290</span><span class="sxs-lookup"><span data-stu-id="d3f6f-198">290</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="d3f6f-199">As datas que são usadas no banco de dados de exemplo foram alteradas para esta versão.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-199">The dates that are used in the sample database have changed for this release.</span></span> <span data-ttu-id="d3f6f-200">Se você estiver usando uma versão anterior dos dados de exemplo, poderá ver resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-200">If you are using an earlier version of the sample data, you might see different results.</span></span>  
  
## <a name="saving-the-prediction-results"></a><span data-ttu-id="d3f6f-201">Salvando os resultados da previsão</span><span class="sxs-lookup"><span data-stu-id="d3f6f-201">Saving the Prediction Results</span></span>  
 <span data-ttu-id="d3f6f-202">Você tem várias opções diferentes para usar os resultados da previsão.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-202">You have several different options for using the prediction results.</span></span> <span data-ttu-id="d3f6f-203">É possível simplificar os resultados, copiar os dados da exibição Resultados e colá-los em uma planilha do Excel ou outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-203">You can flatten the results, copy the data from the Results view, and paste it into an Excel worksheet or other file.</span></span>  
  
 <span data-ttu-id="d3f6f-204">Para simplificar o processo de salvar os resultados, o Designer de Mineração de Dados fornece também o recurso para salvar os dados em uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-204">To simplify the process of saving results, Data Mining Designer also provides the ability to save the data to a data source view.</span></span> <span data-ttu-id="d3f6f-205">A funcionalidade para salvar resultados em uma exibição da fonte de dados só está disponível no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3f6f-205">The functionality for saving results to a data source view is available only in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d3f6f-206">Os resultados só podem ser armazenados em um formato simplificado.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-206">The results can only be stored in a flattened format.</span></span>  
  
#### <a name="to-flatten-the-results-in-the-results-pane"></a><span data-ttu-id="d3f6f-207">Para mesclar os resultados no painel Resultados</span><span class="sxs-lookup"><span data-stu-id="d3f6f-207">To flatten the results in the Results pane</span></span>  
  
1.  <span data-ttu-id="d3f6f-208">No Construtor de Consultas de previsão, clique em **alternar para a exibição de design de consulta**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-208">In the Prediction Query Builder, click **Switch to query design view**.</span></span>  
  
     <span data-ttu-id="d3f6f-209">A exibição é alterada para permitir a edição manual do texto da consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-209">The view changes to allow manual editing of the DMX query text.</span></span>  
  
2.  <span data-ttu-id="d3f6f-210">Digite a palavra-chave `FLATTENED` após a palavra-chave `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-210">Type the `FLATTENED` keyword after the `SELECT` keyword.</span></span> <span data-ttu-id="d3f6f-211">O texto completo da consulta deve ser assim:</span><span class="sxs-lookup"><span data-stu-id="d3f6f-211">The complete query text should be as follows:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    ```  
  
3.  <span data-ttu-id="d3f6f-212">Como opção, você pode digitar uma cláusula para restringir os resultados, como o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="d3f6f-212">Optionally, you can type a clause to restrict the results, such as the following example:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    WHERE [Forecasting].[Model Region] = 'M200 North America'   
    OR [Forecasting].[Model Region] = 'M200 Europe'  
  
    ```  
  
4.  <span data-ttu-id="d3f6f-213">Clique em **alternar para a exibição de resultado da consulta**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-213">Click **Switch to query result view**.</span></span>  
  
#### <a name="to-export-prediction-query-results"></a><span data-ttu-id="d3f6f-214">Para exportar resultados da consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="d3f6f-214">To export prediction query results</span></span>  
  
1.  <span data-ttu-id="d3f6f-215">Clique em **salvar resultados da consulta**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-215">Click **Save query results**.</span></span>  
  
2.  <span data-ttu-id="d3f6f-216">Na caixa de diálogo **salvar resultado da consulta de mineração de dados** , para **fonte de dados**, selecione [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3f6f-216">In the **Save Data Mining Query Result** dialog box, for **Data Source**, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="d3f6f-217">Também será possível criar uma fonte de dados se você quiser salvar os dados em um banco de dados relacional diferente.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-217">You can also create a data source if you want to save the data to a different relational database.</span></span>  
  
3.  <span data-ttu-id="d3f6f-218">Na coluna **nome da tabela** , digite um novo nome de tabela temporária, como **previsões de teste**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-218">In the **Table Name** column, type a new temporary table name, such as **Test Predictions**.</span></span>  
  
4.  <span data-ttu-id="d3f6f-219">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-219">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d3f6f-220">Para exibir a tabela criada, crie uma conexão ao mecanismo de banco de dados da instância onde os dados foram salvos e crie uma consulta.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-220">To view the table that you created, create a connection to the database engine of the instance where you saved the data, and create a query.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="d3f6f-221">Conclusão</span><span class="sxs-lookup"><span data-stu-id="d3f6f-221">Conclusion</span></span>  
 <span data-ttu-id="d3f6f-222">Você aprendeu a criar um modelo de série temporal básico, interpretar as previsões e criar previsões.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-222">You have learned how to build a basic time series model, interpret the forecasts, and create predictions.</span></span>  
  
 <span data-ttu-id="d3f6f-223">As tarefas restantes deste tutorial são opcionais e descrevem previsões de série temporal avançadas.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-223">The remaining tasks in this tutorial are optional, and describe advanced time series predictions.</span></span> <span data-ttu-id="d3f6f-224">Se você decidir ir adiante, aprenderá a adicionar novos dados ao seu modelo e criar previsões na série estendida.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-224">If you decide to go on, you will learn how to add new data to your model and create predictions on the extended series.</span></span> <span data-ttu-id="d3f6f-225">Você também aprenderá a executar a previsão cruzada, usando a tendência no modelo, mas substituindo os dados por uma nova série de dados.</span><span class="sxs-lookup"><span data-stu-id="d3f6f-225">You will also learn how to perform cross-prediction, by using the trend in the model but replacing the data with a new series of data.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d3f6f-226">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="d3f6f-226">Next Lesson</span></span>  
 [<span data-ttu-id="d3f6f-227">Previsões de série temporal avançada &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="d3f6f-227">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3f6f-228">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3f6f-228">See Also</span></span>  
 [<span data-ttu-id="d3f6f-229">Exemplos de consulta de um modelo de série temporal</span><span class="sxs-lookup"><span data-stu-id="d3f6f-229">Time Series Model Query Examples</span></span>](../../2014/analysis-services/data-mining/time-series-model-query-examples.md)  
  
  
