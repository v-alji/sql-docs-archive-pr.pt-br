---
title: 'Lição 4: Criando previsões de série temporal usando DMX | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6b883e43-209d-489a-8dc3-9349f88acae8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 772e5f5f71ca82dd18fec48730522c80e907414f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678364"
---
# <a name="lesson-4-creating-time-series-predictions-using-dmx"></a><span data-ttu-id="12677-102">Lição 4: Criando previsões de série temporal usando DMX</span><span class="sxs-lookup"><span data-stu-id="12677-102">Lesson 4: Creating Time Series Predictions Using DMX</span></span>
  <span data-ttu-id="12677-103">Nesta lição e na lição a seguir, você usará DMX (extensões de mineração de dados) para criar diferentes tipos de previsões com base nos modelos de série temporal criados na [lição 1: Criando um modelo de mineração de série temporal e uma estrutura de mineração](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) e [lição 2: adicionando modelos de mineração à estrutura de mineração de série temporal](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="12677-103">In this lesson and the following lesson, you will use Data Mining Extensions (DMX) to create different types of predictions based on the time series models that you created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) and [Lesson 2: Adding Mining Models to the Time Series Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span></span>  
  
 <span data-ttu-id="12677-104">Com um modelo de série temporal, você tem várias opções para fazer previsões:</span><span class="sxs-lookup"><span data-stu-id="12677-104">With a time series model, you have many options for making predictions:</span></span>  
  
-   <span data-ttu-id="12677-105">Usar os padrões e os dados existentes no modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="12677-105">Use the existing patterns and data in the mining model</span></span>  
  
-   <span data-ttu-id="12677-106">Usar os padrões existentes no modelo de mineração mas fornecer dados novos</span><span class="sxs-lookup"><span data-stu-id="12677-106">Use the existing patterns in the mining model but supply new data</span></span>  
  
-   <span data-ttu-id="12677-107">Adicionar novos dados ao modelo ou atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="12677-107">Add new data to the model or update the model.</span></span>  
  
 <span data-ttu-id="12677-108">A sintaxe para criar esses tipos de previsão foi resumida a seguir:</span><span class="sxs-lookup"><span data-stu-id="12677-108">The syntax for making these prediction types is summarized below:</span></span>  
  
 <span data-ttu-id="12677-109">Previsão de série temporal padrão</span><span class="sxs-lookup"><span data-stu-id="12677-109">Default time series prediction</span></span>  
 <span data-ttu-id="12677-110">Use o [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) para retornar o número especificado de previsões do modelo de mineração treinado.</span><span class="sxs-lookup"><span data-stu-id="12677-110">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) to return the specified number of predictions from the trained mining model.</span></span>  
  
 <span data-ttu-id="12677-111">Por exemplo, consulte exemplos de consulta de modelo de [&#41;do PredictTimeSeries &#40;DMX](/sql/dmx/predicttimeseries-dmx) ou de [série temporal](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="12677-111">For example, see [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) or [Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span></span>  
  
 <span data-ttu-id="12677-112">EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="12677-112">EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="12677-113">Use o [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) com o argumento EXTEND_MODEL_CASES para adicionar novos dados, estender a série e criar previsões com base no modelo de mineração atualizado.</span><span class="sxs-lookup"><span data-stu-id="12677-113">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the EXTEND_MODEL_CASES argument to add new data, extend the series, and create predictions based on the updated mining model.</span></span>  
  
 <span data-ttu-id="12677-114">Este tutorial contém um exemplo de como usar EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="12677-114">This tutorial contains an example of how to use EXTEND_MODEL_CASES.</span></span>  
  
 <span data-ttu-id="12677-115">REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="12677-115">REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="12677-116">Use o [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) com o argumento REPLACE_MODEL_CASES para substituir os dados originais por uma nova série de dados e, em seguida, crie previsões com base na aplicação dos padrões no modelo de mineração à nova série de dados.</span><span class="sxs-lookup"><span data-stu-id="12677-116">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the REPLACE_MODEL_CASES argument to replace the original data with a new data series, and then create predictions based on applying the patterns in the mining model to the new data series.</span></span>  
  
 <span data-ttu-id="12677-117">Para obter um exemplo de como usar REPLACE_MODEL_CASES, consulte [lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="12677-117">For an example of how to use REPLACE_MODEL_CASES, see [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="12677-118">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="12677-118">Lesson Tasks</span></span>  
 <span data-ttu-id="12677-119">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="12677-119">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="12677-120">Criar uma consulta para obter as previsões padrão com base em dados existentes.</span><span class="sxs-lookup"><span data-stu-id="12677-120">Create a query to get the default predictions based on existing data.</span></span>  
  
 <span data-ttu-id="12677-121">Na lição a seguir, você executará as seguintes tarefas relacionadas:</span><span class="sxs-lookup"><span data-stu-id="12677-121">In the following lesson you will perform the following related tasks:</span></span>  
  
-   <span data-ttu-id="12677-122">Criar uma consulta para fornecer novos dados e obter previsões atualizadas.</span><span class="sxs-lookup"><span data-stu-id="12677-122">Create a query to supply new data and get updated predictions.</span></span>  
  
 <span data-ttu-id="12677-123">Além de criar consultas manualmente usando DMX, você também pode criar previsões usando o construtor de consultas de previsão no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12677-123">In addition to creating queries manually by using DMX, you can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="simple-time-series-prediction-query"></a><span data-ttu-id="12677-124">Consulta de previsão de série temporal simples</span><span class="sxs-lookup"><span data-stu-id="12677-124">Simple Time Series Prediction Query</span></span>  
 <span data-ttu-id="12677-125">A primeira etapa é usar a instrução `SELECT FROM` junto com a função `PredictTimeSeries` para criar previsões de série temporal.</span><span class="sxs-lookup"><span data-stu-id="12677-125">The first step is to use the `SELECT FROM` statement together with the `PredictTimeSeries` function to create time series predictions.</span></span> <span data-ttu-id="12677-126">Modelos de série temporal dão suporte a uma sintaxe simplificada para a criação de previsões: você não precisa fornecer qualquer entrada, mas especificar o número de previsões a serem criadas.</span><span class="sxs-lookup"><span data-stu-id="12677-126">Time series models support a simplified syntax for creating predictions: you do not need to supply any inputs, but only have to specify the number of predictions to create.</span></span> <span data-ttu-id="12677-127">A seguir, um exemplo genérico da instrução que será usada:</span><span class="sxs-lookup"><span data-stu-id="12677-127">The following is a generic example of the statement you will use:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model name>]   
WHERE [<criteria>]  
```  
  
 <span data-ttu-id="12677-128">A lista de seleção pode conter colunas do modelo, como o nome da linha de produto para a qual você está criando as previsões ou funções de previsão, como [retardo &#40;dmx&#41;](/sql/dmx/lag-dmx) ou [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), que são especificamente para modelos de mineração de série temporal.</span><span class="sxs-lookup"><span data-stu-id="12677-128">The select list can contain columns from the model, such as the name of the product line that you are creating the predictions for, or prediction functions, such as [Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) or [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), which are specifically for time series mining models.</span></span>  
  
#### <a name="to-create-a-simple-time-series-prediction-query"></a><span data-ttu-id="12677-129">Para criar uma consulta de previsão de série temporal simples</span><span class="sxs-lookup"><span data-stu-id="12677-129">To create a simple time series prediction query</span></span>  
  
1.  <span data-ttu-id="12677-130">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="12677-130">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="12677-131">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="12677-131">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="12677-132">Copie o exemplo genérico da instrução na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="12677-132">Copy the generic example of the statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="12677-133">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12677-133">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="12677-134">por:</span><span class="sxs-lookup"><span data-stu-id="12677-134">with:</span></span>  
  
    ```  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    ```  
  
     <span data-ttu-id="12677-135">A primeira linha recupera um valor do modelo de mineração que identifica a série.</span><span class="sxs-lookup"><span data-stu-id="12677-135">The first line retrieves a value from the mining model that identifies the series.</span></span>  
  
     <span data-ttu-id="12677-136">A segunda e a terceira linhas usam a função `PredictTimeSeries`.</span><span class="sxs-lookup"><span data-stu-id="12677-136">The second and third lines use the `PredictTimeSeries` function.</span></span> <span data-ttu-id="12677-137">Cada linha prevê um atributo diferente, `[Quantity]` ou `[Amount]`.</span><span class="sxs-lookup"><span data-stu-id="12677-137">Each line predicts a different attribute, `[Quantity]` or `[Amount]`.</span></span> <span data-ttu-id="12677-138">Os números depois dos nomes dos atributos previsíveis especificam o número de períodos a serem previstos.</span><span class="sxs-lookup"><span data-stu-id="12677-138">The numbers after the names of the predictable attributes specify the number of time steps to predict.</span></span>  
  
     <span data-ttu-id="12677-139">A cláusula `AS` é usada para fornecer um nome para a coluna retornada por cada função de previsão.</span><span class="sxs-lookup"><span data-stu-id="12677-139">The `AS` clause is used to provide a name for the column that is returned by each prediction function.</span></span> <span data-ttu-id="12677-140">Se você não fornecer um alias, por padrão ambas as colunas serão retornadas com o rótulo `Expression`.</span><span class="sxs-lookup"><span data-stu-id="12677-140">If you do not supply an alias, by default both columns are returned with the label, `Expression`.</span></span>  
  
4.  <span data-ttu-id="12677-141">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12677-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="12677-142">por:</span><span class="sxs-lookup"><span data-stu-id="12677-142">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="12677-143">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12677-143">Replace the following:</span></span>  
  
    ```  
    WHERE [criteria>]   
    ```  
  
     <span data-ttu-id="12677-144">por:</span><span class="sxs-lookup"><span data-stu-id="12677-144">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="12677-145">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="12677-145">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    FROM   
    [Forecasting_MIXED]  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
6.  <span data-ttu-id="12677-146">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="12677-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="12677-147">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `SimpleTimeSeriesPrediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="12677-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SimpleTimeSeriesPrediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="12677-148">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="12677-148">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="12677-149">A consulta retorna 6 previsões para cada uma das duas combinações de produto e região especificadas na cláusula `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="12677-149">The query returns 6 predictions for each of the two combinations of product and region that are specified in the `WHERE` clause.</span></span>  
  
 <span data-ttu-id="12677-150">Na próxima lição, você criará uma consulta para fornecer novos dados ao modelo e comparar os resultados da previsão aos da previsão recém-criada.</span><span class="sxs-lookup"><span data-stu-id="12677-150">In the next lesson, you will create a query that supplies new data to the model, and compare the results of that prediction with the one you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="12677-151">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="12677-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="12677-152">Lição 5: Estendendo o modelo de série temporal</span><span class="sxs-lookup"><span data-stu-id="12677-152">Lesson 5: Extending the Time Series Model</span></span>](../../2014/tutorials/lesson-5-extending-the-time-series-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="12677-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12677-153">See Also</span></span>  
 <span data-ttu-id="12677-154">[&#41;&#40;DMX PredictTimeSeries](/sql/dmx/predicttimeseries-dmx) </span><span class="sxs-lookup"><span data-stu-id="12677-154">[PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) </span></span>  
 <span data-ttu-id="12677-155">[Retardo &#40;&#41;DMX](/sql/dmx/lag-dmx) </span><span class="sxs-lookup"><span data-stu-id="12677-155">[Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) </span></span>  
 <span data-ttu-id="12677-156">[Exemplos de consulta de modelo de série temporal](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="12677-156">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="12677-157">Lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="12677-157">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
  
