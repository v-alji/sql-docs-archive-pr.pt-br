---
title: 'Lição 5: estendendo o modelo de série temporal | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7aad4946-c903-4e25-88b9-b087c20cb67d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2716e985897f8115d189d9410b7cdb13fb1af291
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571722"
---
# <a name="lesson-5-extending-the-time-series-model"></a><span data-ttu-id="22e7b-102">Lição 5: Estendendo o modelo de série temporal</span><span class="sxs-lookup"><span data-stu-id="22e7b-102">Lesson 5: Extending the Time Series Model</span></span>
  <span data-ttu-id="22e7b-103">No [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, é possível adicionar novos dados a um modelo de série temporal e incorporar automaticamente os novos dados no módulo.</span><span class="sxs-lookup"><span data-stu-id="22e7b-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, you can add new data to a time series model and automatically incorporate the new data into the model.</span></span> <span data-ttu-id="22e7b-104">Você adiciona novos dados a um modelo de mineração de série temporal de um de dois modos:</span><span class="sxs-lookup"><span data-stu-id="22e7b-104">You add new data to a time series mining model in one of two ways:</span></span>  
  
-   <span data-ttu-id="22e7b-105">Use PREDICTION JOIN para unir dados em uma fonte externa para os dados de treinamento.</span><span class="sxs-lookup"><span data-stu-id="22e7b-105">Use a PREDICTION JOIN to join data in an external source to the training data.</span></span>  
  
-   <span data-ttu-id="22e7b-106">Use uma consulta de previsão singleton para fornecer dados para uma fatia de cada vez.</span><span class="sxs-lookup"><span data-stu-id="22e7b-106">Use a singleton prediction query to provide data one slice at a time.</span></span>  
  
 <span data-ttu-id="22e7b-107">Por exemplo, suponha que você treinou o modelo de mineração em dados de vendas existentes há alguns meses.</span><span class="sxs-lookup"><span data-stu-id="22e7b-107">For example, assume that you trained the mining model on existing sales data some months ago.</span></span> <span data-ttu-id="22e7b-108">Ao fazer novas vendas, talvez você queira atualizar as previsões de vendas para incorporá-las aos novos dados.</span><span class="sxs-lookup"><span data-stu-id="22e7b-108">When you get new sales, you might want to update the sales predictions to incorporate the new data.</span></span> <span data-ttu-id="22e7b-109">É possível fazer isso em uma etapa, fornecendo os novos números de vendas como dados de entrada e gerando novas previsões baseadas no conjunto de dados composto.</span><span class="sxs-lookup"><span data-stu-id="22e7b-109">You can do this in one step, by supplying the new sales figures as input data and generating new predictions based on the composite data set.</span></span>  
  
## <a name="making-predictions-with-extend_model_cases"></a><span data-ttu-id="22e7b-110">Fazendo previsões com EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="22e7b-110">Making Predictions with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="22e7b-111">A seguir, exemplos genéricos de uma previsão de série temporal usando EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="22e7b-111">The following are generic examples of a time series prediction using EXTEND_MODEL_CASES.</span></span> <span data-ttu-id="22e7b-112">O primeiro exemplo permite que você especifique o número de previsões, começando pelo último período do modelo original:</span><span class="sxs-lookup"><span data-stu-id="22e7b-112">The first example enables you to specify the number of predictions starting from the last time step of the original model:</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>]  
```  
  
 <span data-ttu-id="22e7b-113">O segundo exemplo permite que você especifique o período onde as previsões devem começar e onde devem terminar.</span><span class="sxs-lookup"><span data-stu-id="22e7b-113">The second example enables you to specify the time step where predictions should start, and where they should end.</span></span> <span data-ttu-id="22e7b-114">Essa opção é importante quando você estende os casos do modelo já que, por padrão, os períodos usados para consultas de previsão sempre iniciam no término da série original.</span><span class="sxs-lookup"><span data-stu-id="22e7b-114">This option is important when you extend the model cases because, by default, the time steps used for prediction queries always start at the end of the original series.</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n-start, n-end, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>}  
```  
  
 <span data-ttu-id="22e7b-115">Neste tutorial, você criará ambos os tipos de consultas.</span><span class="sxs-lookup"><span data-stu-id="22e7b-115">In this tutorial, you will create both kinds of queries.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query-on-a-time-series-model"></a><span data-ttu-id="22e7b-116">Como criar uma consulta de previsão singleton em um modelo de série temporal</span><span class="sxs-lookup"><span data-stu-id="22e7b-116">To create a singleton prediction query on a time series model</span></span>  
  
1.  <span data-ttu-id="22e7b-117">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="22e7b-117">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="22e7b-118">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="22e7b-118">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="22e7b-119">Copie o exemplo genérico da instrução singleton, no campo em branco da consulta.</span><span class="sxs-lookup"><span data-stu-id="22e7b-119">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="22e7b-120">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22e7b-120">Replace the following:</span></span>  
  
    ```  
    SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
    ```  
  
     <span data-ttu-id="22e7b-121">por:</span><span class="sxs-lookup"><span data-stu-id="22e7b-121">with:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    ```  
  
     <span data-ttu-id="22e7b-122">A primeira linha recupera um valor do modelo que identifica a série.</span><span class="sxs-lookup"><span data-stu-id="22e7b-122">The first line retrieves a value from the model that identifies the series.</span></span>  
  
     <span data-ttu-id="22e7b-123">A segunda linha contém a função de previsão, que obtém 6 previsões para Quantidade.</span><span class="sxs-lookup"><span data-stu-id="22e7b-123">The second line contains the prediction function, which gets 6 predictions for Quantity.</span></span> <span data-ttu-id="22e7b-124">Um alias, `PredictQty`, é atribuído à coluna de resultados da previsão para facilitar a compreensão dos resultados.</span><span class="sxs-lookup"><span data-stu-id="22e7b-124">An alias, `PredictQty`, is assigned to the prediction result column to make it easier to understand the results.</span></span>  
  
4.  <span data-ttu-id="22e7b-125">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22e7b-125">Replace the following:</span></span>  
  
    ```  
    FROM <mining model>  
    ```  
  
     <span data-ttu-id="22e7b-126">por:</span><span class="sxs-lookup"><span data-stu-id="22e7b-126">with:</span></span>  
  
    ```  
    FROM [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="22e7b-127">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22e7b-127">Replace the following:</span></span>  
  
    ```  
    PREDICTION JOIN <source query>  
    ```  
  
     <span data-ttu-id="22e7b-128">por:</span><span class="sxs-lookup"><span data-stu-id="22e7b-128">with:</span></span>  
  
    ```  
    NATURAL PREDICTION JOIN   
    (  
       SELECT 1 AS [Reporting Date],  
       '10' AS [Quantity],  
       'M200 Europe' AS [Model Region]  
       UNION SELECT  
       2 AS [Reporting Date],  
       15 AS [Quantity]),  
       'M200 Europe' AS [Model Region]  
    ) AS t  
    ```  
  
6.  <span data-ttu-id="22e7b-129">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22e7b-129">Replace the following:</span></span>  
  
    ```  
    [WHERE <criteria>]  
    ```  
  
     <span data-ttu-id="22e7b-130">por:</span><span class="sxs-lookup"><span data-stu-id="22e7b-130">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="22e7b-131">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="22e7b-131">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    FROM  
       [Forecasting_MIXED]  
    NATURAL PREDICTION JOIN   
       SELECT 1 AS [ReportingDate],  
      '10' AS [Quantity],  
      'M200 Europe' AS [ModelRegion]  
    UNION SELECT  
      2 AS [ReportingDate],  
      15 AS [Quantity]),  
      'M200 Europe' AS [ModelRegion]  
    ) AS t  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
7.  <span data-ttu-id="22e7b-132">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="22e7b-132">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="22e7b-133">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Singleton_TimeSeries_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="22e7b-133">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_TimeSeries_Query.dmx`.</span></span>  
  
9. <span data-ttu-id="22e7b-134">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="22e7b-134">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="22e7b-135">A consulta retorna previsões de quantidade de vendas para as bicicletas M200 na Europa e nas regiões do Pacífico.</span><span class="sxs-lookup"><span data-stu-id="22e7b-135">The query returns predictions of sales quantity for the M200 bicycle in the Europe and Pacific regions.</span></span>  
  
## <a name="understanding-prediction-start-with-extend_model_cases"></a><span data-ttu-id="22e7b-136">Compreendendo o início das previsões com EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="22e7b-136">Understanding Prediction Start with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="22e7b-137">Agora que você criou previsões com base no modelo original, e com novos dados, poderá comparar os resultados para ver como a atualização dos dados de vendas afeta as previsões.</span><span class="sxs-lookup"><span data-stu-id="22e7b-137">Now that you have created predictions based on the original model, and with new data, you can compare the results to see how updating the sales data affects the predictions.</span></span> <span data-ttu-id="22e7b-138">Antes disso, examine o código recém-criado e observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22e7b-138">Before you do so, review the code that you just created, and notice the following:</span></span>  
  
-   <span data-ttu-id="22e7b-139">Você só forneceu novos dados para a região da Europa.</span><span class="sxs-lookup"><span data-stu-id="22e7b-139">You supplied new data for only the Europe region.</span></span>  
  
-   <span data-ttu-id="22e7b-140">Você só forneceu novos dados relativos a dois meses.</span><span class="sxs-lookup"><span data-stu-id="22e7b-140">You supplied only two months' worth of new data.</span></span>  
  
 <span data-ttu-id="22e7b-141">A tabela a seguir mostra como os novos valores fornecidos para a M200 na Europa afetam as previsões.</span><span class="sxs-lookup"><span data-stu-id="22e7b-141">The following table shows how the new values supplied for M200 Europe affect predictions.</span></span> <span data-ttu-id="22e7b-142">Você não forneceu dados novos para o produto M200 na região do Pacífico, mas essa série será apresentada para fins de comparação:</span><span class="sxs-lookup"><span data-stu-id="22e7b-142">You did not provide any new data for the M200 product in the Pacific region, but this series is presented for comparison:</span></span>  
  
 <span data-ttu-id="22e7b-143">**Produto e região: Europa M200l**</span><span class="sxs-lookup"><span data-stu-id="22e7b-143">**Product and Region: M200 Europe**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="22e7b-144">Modelo existente (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="22e7b-144">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="22e7b-145">Modelo com dados de vendas atualizados (`PredictTimeSeries` com `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="22e7b-145">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="22e7b-146">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-146">M200 Europe</span></span>|<span data-ttu-id="22e7b-147">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-147">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-148">77</span><span class="sxs-lookup"><span data-stu-id="22e7b-148">77</span></span>|<span data-ttu-id="22e7b-149">10</span><span class="sxs-lookup"><span data-stu-id="22e7b-149">10</span></span>|  
|<span data-ttu-id="22e7b-150">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-150">M200 Europe</span></span>|<span data-ttu-id="22e7b-151">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-151">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-152">64</span><span class="sxs-lookup"><span data-stu-id="22e7b-152">64</span></span>|<span data-ttu-id="22e7b-153">15</span><span class="sxs-lookup"><span data-stu-id="22e7b-153">15</span></span>|  
|<span data-ttu-id="22e7b-154">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-154">M200 Europe</span></span>|<span data-ttu-id="22e7b-155">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-155">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-156">59</span><span class="sxs-lookup"><span data-stu-id="22e7b-156">59</span></span>|<span data-ttu-id="22e7b-157">72</span><span class="sxs-lookup"><span data-stu-id="22e7b-157">72</span></span>|  
|<span data-ttu-id="22e7b-158">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-158">M200 Europe</span></span>|<span data-ttu-id="22e7b-159">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-159">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-160">56</span><span class="sxs-lookup"><span data-stu-id="22e7b-160">56</span></span>|<span data-ttu-id="22e7b-161">69</span><span class="sxs-lookup"><span data-stu-id="22e7b-161">69</span></span>|  
|<span data-ttu-id="22e7b-162">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-162">M200 Europe</span></span>|<span data-ttu-id="22e7b-163">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-163">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-164">56</span><span class="sxs-lookup"><span data-stu-id="22e7b-164">56</span></span>|<span data-ttu-id="22e7b-165">68</span><span class="sxs-lookup"><span data-stu-id="22e7b-165">68</span></span>|  
|<span data-ttu-id="22e7b-166">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-166">M200 Europe</span></span>|<span data-ttu-id="22e7b-167">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-167">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-168">74</span><span class="sxs-lookup"><span data-stu-id="22e7b-168">74</span></span>|<span data-ttu-id="22e7b-169">89</span><span class="sxs-lookup"><span data-stu-id="22e7b-169">89</span></span>|  
  
 <span data-ttu-id="22e7b-170">**Produto e região: M200 Pacífico**</span><span class="sxs-lookup"><span data-stu-id="22e7b-170">**Product and Region: M200 Pacific**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="22e7b-171">Modelo existente (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="22e7b-171">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="22e7b-172">Modelo com dados de vendas atualizados (`PredictTimeSeries` com `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="22e7b-172">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="22e7b-173">M200 Pacífico</span><span class="sxs-lookup"><span data-stu-id="22e7b-173">M200 Pacific</span></span>|<span data-ttu-id="22e7b-174">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-174">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-175">41</span><span class="sxs-lookup"><span data-stu-id="22e7b-175">41</span></span>|<span data-ttu-id="22e7b-176">41</span><span class="sxs-lookup"><span data-stu-id="22e7b-176">41</span></span>|  
|<span data-ttu-id="22e7b-177">M200 Pacífico</span><span class="sxs-lookup"><span data-stu-id="22e7b-177">M200 Pacific</span></span>|<span data-ttu-id="22e7b-178">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-178">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-179">44</span><span class="sxs-lookup"><span data-stu-id="22e7b-179">44</span></span>|<span data-ttu-id="22e7b-180">44</span><span class="sxs-lookup"><span data-stu-id="22e7b-180">44</span></span>|  
|<span data-ttu-id="22e7b-181">M200 Pacífico</span><span class="sxs-lookup"><span data-stu-id="22e7b-181">M200 Pacific</span></span>|<span data-ttu-id="22e7b-182">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-182">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-183">38</span><span class="sxs-lookup"><span data-stu-id="22e7b-183">38</span></span>|<span data-ttu-id="22e7b-184">38</span><span class="sxs-lookup"><span data-stu-id="22e7b-184">38</span></span>|  
|<span data-ttu-id="22e7b-185">M200 Pacífico</span><span class="sxs-lookup"><span data-stu-id="22e7b-185">M200 Pacific</span></span>|<span data-ttu-id="22e7b-186">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-186">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-187">41</span><span class="sxs-lookup"><span data-stu-id="22e7b-187">41</span></span>|<span data-ttu-id="22e7b-188">41</span><span class="sxs-lookup"><span data-stu-id="22e7b-188">41</span></span>|  
|<span data-ttu-id="22e7b-189">M200 Pacífico</span><span class="sxs-lookup"><span data-stu-id="22e7b-189">M200 Pacific</span></span>|<span data-ttu-id="22e7b-190">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-190">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-191">36</span><span class="sxs-lookup"><span data-stu-id="22e7b-191">36</span></span>|<span data-ttu-id="22e7b-192">36</span><span class="sxs-lookup"><span data-stu-id="22e7b-192">36</span></span>|  
|<span data-ttu-id="22e7b-193">M200 Pacífico</span><span class="sxs-lookup"><span data-stu-id="22e7b-193">M200 Pacific</span></span>|<span data-ttu-id="22e7b-194">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-194">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-195">39</span><span class="sxs-lookup"><span data-stu-id="22e7b-195">39</span></span>|<span data-ttu-id="22e7b-196">39</span><span class="sxs-lookup"><span data-stu-id="22e7b-196">39</span></span>|  
  
 <span data-ttu-id="22e7b-197">A partir desses resultados, você pode observar dois aspectos:</span><span class="sxs-lookup"><span data-stu-id="22e7b-197">From these results, you can see two things:</span></span>  
  
-   <span data-ttu-id="22e7b-198">As duas primeiras previsões para a série M200 Europe são exatamente iguais aos novos dados fornecidos.</span><span class="sxs-lookup"><span data-stu-id="22e7b-198">The first two predictions for the M200 Europe series are exactly the same as the new data you supplied.</span></span> <span data-ttu-id="22e7b-199">Por design, o Analysis Services retorna os pontos de dados novos reais em vez de fazer uma previsão.</span><span class="sxs-lookup"><span data-stu-id="22e7b-199">By design, Analysis Services returns the actual new data points instead of making a prediction.</span></span> <span data-ttu-id="22e7b-200">Isso acontece porque quando você estende os casos do modelo, os períodos usados para consultas de previsão sempre iniciam no término da série original.</span><span class="sxs-lookup"><span data-stu-id="22e7b-200">That is because when you extend the model cases, the time steps used for prediction queries always start at the end of the original series.</span></span> <span data-ttu-id="22e7b-201">Portanto, se você adicionar dois novos pontos de dados, as duas primeiras previsões retornadas sobrepõem os novos dados.</span><span class="sxs-lookup"><span data-stu-id="22e7b-201">Therefore, if you add two new data points, the first two predictions returned overlap with the new data.</span></span>  
  
-   <span data-ttu-id="22e7b-202">Depois que todos os novos pontos de dados forem usados, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fará previsões com base no modelo atualizado.</span><span class="sxs-lookup"><span data-stu-id="22e7b-202">After all the new data points are used up, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] makes predictions based on the updated model.</span></span> <span data-ttu-id="22e7b-203">Dessa forma, começando em setembro de 2005, você pode ver a diferença entre as previsões para M200 Europe a partir do modelo original, na coluna à esquerda, e a partir do modelo que usa EXTEND_MODEL_CASES, na coluna à direita.</span><span class="sxs-lookup"><span data-stu-id="22e7b-203">Therefore, starting in September 2005, you can see the difference between predictions for M200 Europe from the original model, in the left-hand column, and the model that uses EXTEND_MODEL_CASES, in the right-hand column.</span></span> <span data-ttu-id="22e7b-204">As previsões são diferentes porque o modelo foi atualizado com os novos dados.</span><span class="sxs-lookup"><span data-stu-id="22e7b-204">The predictions are different because the model has been updated with the new data.</span></span>  
  
## <a name="using-start-and-end-time-steps-to-control-predictions"></a><span data-ttu-id="22e7b-205">Usando períodos inicial e final para controlar previsões</span><span class="sxs-lookup"><span data-stu-id="22e7b-205">Using Start and End Time Steps to Control Predictions</span></span>  
 <span data-ttu-id="22e7b-206">Quando você estende um modelo, os novos dados são sempre anexados ao fim da série.</span><span class="sxs-lookup"><span data-stu-id="22e7b-206">When you extend a model, the new data is always attached to the end of the series.</span></span> <span data-ttu-id="22e7b-207">No entanto, para fins de previsão, as frações de tempo usadas para consultas de previsão sempre iniciam no término da série original.</span><span class="sxs-lookup"><span data-stu-id="22e7b-207">However, for the purpose of prediction, the time slices used for prediction queries start at the end of the original series.</span></span> <span data-ttu-id="22e7b-208">Se você quiser obter somente as previsões novas ao adicionar os novos dados, deverá especificar o ponto inicial como um número de frações de tempo.</span><span class="sxs-lookup"><span data-stu-id="22e7b-208">If you want to obtain only the new predictions when you add the new data, you must specify the starting point as a number of time slices.</span></span> <span data-ttu-id="22e7b-209">Por exemplo, se você estiver adicionando dois novos pontos de dados e quiser fazer quatro três previsões novas, proceda da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="22e7b-209">For example, if you are adding two new data points and want to make four new predictions, you would do the following:</span></span>  
  
-   <span data-ttu-id="22e7b-210">Crie uma PREDICTION JOIN em um modelo de série temporal e especifique dois meses de dados novos.</span><span class="sxs-lookup"><span data-stu-id="22e7b-210">Create a PREDICTION JOIN on a time series model, and specify two months of new data.</span></span>  
  
-   <span data-ttu-id="22e7b-211">Solicite previsões para quatro frações de tempo, onde o ponto inicial será 3 e o ponto final será a fração de tempo 6.</span><span class="sxs-lookup"><span data-stu-id="22e7b-211">Request predictions for four time slices, where the starting point is 3, and the ending point is time slice 6.</span></span>  
  
 <span data-ttu-id="22e7b-212">Em outras palavras, se os novos dados contiverem n frações de tempo e você solicitar previsões de etapas de 1 a n, as previsões coincidirão com o mesmo período que os novos dados.</span><span class="sxs-lookup"><span data-stu-id="22e7b-212">In other words, if your new data contains n time slices, and you request predictions for time steps 1 through n, the predictions will coincide with the same period as the new data.</span></span> <span data-ttu-id="22e7b-213">Para conseguir previsões para períodos de tempo não cobertos pelos seus dados, você deve iniciar as previsões na fração de tempo n+1 após a nova série de dados ou assegurar-se de solicitar frações de tempo adicionais.</span><span class="sxs-lookup"><span data-stu-id="22e7b-213">To get new predictions for a time periods not covered by your data, you must either start predictions at the time slice n+1 after the new data series, or make sure that you request additional time slices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22e7b-214">Não é possível fazer previsões históricas quando você adiciona novos dados.</span><span class="sxs-lookup"><span data-stu-id="22e7b-214">You cannot make historical predictions when you add new data.</span></span>  
  
 <span data-ttu-id="22e7b-215">O exemplo a seguir mostra a instrução DMX, que permite a você obter somente as novas previsões para as duas séries do exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="22e7b-215">The following example shows the DMX statement that lets you get only the new predictions for the two series in the previous example.</span></span>  
  
```  
SELECT [Model Region],  
PredictTimeSeries([Quantity],3,6, EXTEND_MODEL_CASES) AS PredictQty  
FROM  
   [Forecasting_MIXED]  
NATURAL PREDICTION JOIN   
   SELECT 1 AS [ReportingDate],  
  '10' AS [Quantity],  
  'M200 Europe' AS [ModelRegion]  
UNION SELECT  
  2 AS [ReportingDate],  
  15 AS [Quantity]),  
  'M200 Europe' AS [ModelRegion]  
) AS t  
WHERE [ModelRegion] = 'M200 Europe'  
```  
  
 <span data-ttu-id="22e7b-216">Os resultados da previsão começam na fração de tempo 3, que ocorre após os 2 meses de dados novos fornecidos por você.</span><span class="sxs-lookup"><span data-stu-id="22e7b-216">The prediction results start at time slice 3, which is after the 2 months of new data that you supplied.</span></span>  
  
 <span data-ttu-id="22e7b-217">**Produto e região: Europa M200l**</span><span class="sxs-lookup"><span data-stu-id="22e7b-217">**Product and Region: M200 Europe**</span></span>  
  
 <span data-ttu-id="22e7b-218">Modelo com dados atualizados (PredictTimeSeries com EXTEND_MODEL_CASES)</span><span class="sxs-lookup"><span data-stu-id="22e7b-218">Model with updated data (PredictTimeSeries with EXTEND_MODEL_CASES)</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="22e7b-219">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-219">M200 Europe</span></span>|<span data-ttu-id="22e7b-220">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-220">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-221">72</span><span class="sxs-lookup"><span data-stu-id="22e7b-221">72</span></span>|  
|<span data-ttu-id="22e7b-222">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-222">M200 Europe</span></span>|<span data-ttu-id="22e7b-223">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-223">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-224">69</span><span class="sxs-lookup"><span data-stu-id="22e7b-224">69</span></span>|  
|<span data-ttu-id="22e7b-225">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-225">M200 Europe</span></span>|<span data-ttu-id="22e7b-226">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-226">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-227">68</span><span class="sxs-lookup"><span data-stu-id="22e7b-227">68</span></span>|  
|<span data-ttu-id="22e7b-228">M200 Europa</span><span class="sxs-lookup"><span data-stu-id="22e7b-228">M200 Europe</span></span>|<span data-ttu-id="22e7b-229">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="22e7b-229">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="22e7b-230">89</span><span class="sxs-lookup"><span data-stu-id="22e7b-230">89</span></span>|  
  
## <a name="making-predictions-with-replace_model_cases"></a><span data-ttu-id="22e7b-231">Fazendo previsões com REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="22e7b-231">Making Predictions with REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="22e7b-232">Substituir os casos de modelo é útil quando você desejar treinar um modelo em um conjunto de casos e, então, aplicar o modelo a uma série de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="22e7b-232">Replacing the model cases is useful when you want to train a model on one set of cases and then apply that model to a different data series.</span></span> <span data-ttu-id="22e7b-233">Uma explicação detalhada desse cenário é apresentada na [lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="22e7b-233">A detailed walkthrough of this scenario is presented in [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e7b-234">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22e7b-234">See Also</span></span>  
 <span data-ttu-id="22e7b-235">[Exemplos de consulta de modelo de série temporal](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="22e7b-235">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="22e7b-236">PredictTimeSeries &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="22e7b-236">PredictTimeSeries &#40;DMX&#41;</span></span>](/sql/dmx/predicttimeseries-dmx)  
  
  
