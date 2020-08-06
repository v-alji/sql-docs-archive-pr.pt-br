---
title: 'Lição 2: adicionando modelos de mineração à estrutura de mineração de série temporal | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75c2a74b-21ce-44fb-a26b-68be4c685c12
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ae0bb91fafb53c0c077a4e0d82558b550d0e6070
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568980"
---
# <a name="lesson-2-adding-mining-models-to-the-time-series-mining-structure"></a><span data-ttu-id="63864-102">Lição 2: Adicionando modelos de mineração à estrutura de mineração de série temporal</span><span class="sxs-lookup"><span data-stu-id="63864-102">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>
  <span data-ttu-id="63864-103">Nesta lição, você adicionará um novo modelo de mineração à estrutura de mineração que acabou de criar na [lição 1: Criando um modelo de mineração de série temporal e estrutura de mineração](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="63864-103">In this lesson, you will add a new mining model to the mining structure that you just created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="63864-104">Instrução ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="63864-104">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="63864-105">Para adicionar um novo modelo de mineração a uma estrutura de mineração existente, use a instrução [ALTER MINING structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="63864-105">In order to add a new mining model to an existing mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="63864-106">O código na instrução pode ser dividido nas seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="63864-106">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="63864-107">Identificando a estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="63864-107">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="63864-108">Nomeando o modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="63864-108">Naming the mining model</span></span>  
  
-   <span data-ttu-id="63864-109">Definindo a coluna de chave</span><span class="sxs-lookup"><span data-stu-id="63864-109">Defining the key column</span></span>  
  
-   <span data-ttu-id="63864-110">Definindo as colunas previsíveis</span><span class="sxs-lookup"><span data-stu-id="63864-110">Defining the predictable columns</span></span>  
  
-   <span data-ttu-id="63864-111">Especificando as alterações de algoritmo e de qualquer parâmetro</span><span class="sxs-lookup"><span data-stu-id="63864-111">Specifying the algorithm and any parameter changes</span></span>  
  
 <span data-ttu-id="63864-112">A seguir, veja um exemplo genérico da instrução ALTER MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="63864-112">The following is a generic example of the ALTER MINING STRUCTURE statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
   ([<key columns>],  
    <mining model columns>  
   )  
USING <algorithm name>([<algorithm parameters>])  
[WITH DRILLTHROUGH]  
```  
  
 <span data-ttu-id="63864-113">A primeira linha do código identifica a estrutura de mineração existente à qual os modelos de mineração serão adicionados:</span><span class="sxs-lookup"><span data-stu-id="63864-113">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="63864-114">A linha seguinte do código nomeia o modelo de mineração que será adicionado à estrutura de mineração:</span><span class="sxs-lookup"><span data-stu-id="63864-114">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="63864-115">Para obter informações sobre como nomear um objeto no DMX, consulte [identificadores &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="63864-115">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="63864-116">As linhas seguintes do código definem as colunas a partir da estrutura de mineração que será usada pelo modelo de mineração:</span><span class="sxs-lookup"><span data-stu-id="63864-116">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key columns>],  
<mining model columns>  
```  
  
 <span data-ttu-id="63864-117">Você só pode usar colunas que já existem na estrutura de mineração, e a primeira coluna na lista deve ser a coluna de chave da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="63864-117">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="63864-118">A próximas linhas do código definem o algoritmo de mineração que gera o modelo de mineração e os parâmetros que podem ser definidos no algoritmo, além de especificarem se você pode detalhar a partir do modelo de mineração até a exibição de dados nos casos de treinamento:</span><span class="sxs-lookup"><span data-stu-id="63864-118">The next lines of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm, and specify whether you can drill down from the mining model into view detailed data in the training cases:</span></span>  
  
```  
USING <algorithm name>([<algorithm parameters>])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="63864-119">Para obter mais informações sobre os parâmetros de algoritmo que você pode ajustar, consulte [referência técnica do algoritmo do Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="63864-119">For more information about the algorithm parameters that you can adjust, see [Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="63864-120">Você pode especificar que uma coluna no modelo de mineração seja utilizada para previsão usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="63864-120">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="63864-121">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="63864-121">Lesson Tasks</span></span>  
 <span data-ttu-id="63864-122">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="63864-122">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="63864-123">Adicionar um novo modelo de mineração de série temporal à estrutura.</span><span class="sxs-lookup"><span data-stu-id="63864-123">Add a new time series mining model to the structure.</span></span>  
  
-   <span data-ttu-id="63864-124">Alterar os parâmetros do algoritmo para usar um método de análise e uma previsão diferentes</span><span class="sxs-lookup"><span data-stu-id="63864-124">Change the algorithm parameters to use a different method of analysis and prediction</span></span>  
  
## <a name="adding-an-arima-time-series-model-to-the-structure"></a><span data-ttu-id="63864-125">Adicionar um modelo de série temporal ARIMA à estrutura</span><span class="sxs-lookup"><span data-stu-id="63864-125">Adding an ARIMA Time Series Model to the Structure</span></span>  
 <span data-ttu-id="63864-126">A primeira etapa é adicionar um novo modelo de mineração de previsão à estrutura existente.</span><span class="sxs-lookup"><span data-stu-id="63864-126">The first step is to add a new forecasting mining model to the existing structure.</span></span> <span data-ttu-id="63864-127">Por padrão, o algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Times Series cria modelos de mineração de série temporal usando dois algoritmos, ARIMA e ARTXP, combinando os resultados.</span><span class="sxs-lookup"><span data-stu-id="63864-127">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm creates time series mining models by using two algorithms, ARIMA and ARTXP, and blending the results.</span></span> <span data-ttu-id="63864-128">No entanto, você pode especificar um único algoritmo para usar ou pode especificar a combinação exata de algoritmos.</span><span class="sxs-lookup"><span data-stu-id="63864-128">However, you can specify a single algorithm to use, or you can specify the exact blend of algorithms.</span></span> <span data-ttu-id="63864-129">Nesta etapa, você adicionará um novo modelo que só utiliza o algoritmo ARIMA.</span><span class="sxs-lookup"><span data-stu-id="63864-129">In this step, you will add a new model that uses only the ARIMA algorithm.</span></span> <span data-ttu-id="63864-130">Este algoritmo foi otimizado para previsão de longo prazo.</span><span class="sxs-lookup"><span data-stu-id="63864-130">This algorithm is optimized for long-term prediction.</span></span>  
  
#### <a name="to-add-an-arima-time-series-mining-model"></a><span data-ttu-id="63864-131">Para adicionar um modelo de mineração de série temporal ARIMA</span><span class="sxs-lookup"><span data-stu-id="63864-131">To add an ARIMA time series mining model</span></span>  
  
1.  <span data-ttu-id="63864-132">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX** para abrir o editor de consultas e uma nova consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="63864-132">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="63864-133">Copie o exemplo genérico da instrução ALTER MINING STRUCTURE na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="63864-133">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="63864-134">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="63864-134">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="63864-135">por:</span><span class="sxs-lookup"><span data-stu-id="63864-135">with:</span></span>  
  
    ```  
    [Forecasting_MIXED_Structure]  
    ```  
  
4.  <span data-ttu-id="63864-136">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="63864-136">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="63864-137">por:</span><span class="sxs-lookup"><span data-stu-id="63864-137">with:</span></span>  
  
    ```  
    Forecasting_ARIMA  
    ```  
  
5.  <span data-ttu-id="63864-138">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="63864-138">Replace the following:</span></span>  
  
    ```  
    <key columns>,  
    ```  
  
     <span data-ttu-id="63864-139">por:</span><span class="sxs-lookup"><span data-stu-id="63864-139">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]  
    ```  
  
     <span data-ttu-id="63864-140">Observe que não é preciso repetir as informações de tipo de data ou de tipo de conteúdo fornecidas na instrução CREATE MINING MODEL, uma vez que elas já estão armazenadas na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="63864-140">Note that you do not need to repeat any of the date type or content type information that you provided in the CREATE MINING MODEL statement, because this information is already stored in the mining structure.</span></span>  
  
6.  <span data-ttu-id="63864-141">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="63864-141">Replace the following:</span></span>  
  
    ```  
    <mining model columns>  
    ```  
  
     <span data-ttu-id="63864-142">por:</span><span class="sxs-lookup"><span data-stu-id="63864-142">with:</span></span>  
  
    ```  
    ([Quantity] PREDICT,  
    [Amount] PREDICT  
    )  
    ```  
  
7.  <span data-ttu-id="63864-143">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="63864-143">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([<algorithm parameters>])   
    [WITH DRILLTHROUGH]  
    ```  
  
     <span data-ttu-id="63864-144">por:</span><span class="sxs-lookup"><span data-stu-id="63864-144">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="63864-145">A instrução resultante deverá ser agora:</span><span class="sxs-lookup"><span data-stu-id="63864-145">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARIMA]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
8.  <span data-ttu-id="63864-146">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="63864-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
9. <span data-ttu-id="63864-147">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Forecasting_ARIMA.dmx` .</span><span class="sxs-lookup"><span data-stu-id="63864-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARIMA.dmx`.</span></span>  
  
10. <span data-ttu-id="63864-148">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="63864-148">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-artxp-time-series-model-to-the-structure"></a><span data-ttu-id="63864-149">Adicionar um modelo de série temporal ARTXP à estrutura</span><span class="sxs-lookup"><span data-stu-id="63864-149">Adding an ARTXP Time Series Model to the Structure</span></span>  
 <span data-ttu-id="63864-150">O algoritmo ARTXP era o algoritmo padrão de série temporal do SQL Server 2005 e é otimizado para previsões a curto prazo.</span><span class="sxs-lookup"><span data-stu-id="63864-150">The ARTXP algorithm was the default time series algorithm in SQL Server 2005 and is optimized for short-term prediction.</span></span> <span data-ttu-id="63864-151">Para comparar previsões usando todos os três algoritmos de série temporal, você adicionará mais um modelo, baseado no algoritmo ARTXP.</span><span class="sxs-lookup"><span data-stu-id="63864-151">To compare predictions by using all three time series algorithms, you will add one more model that is based on the ARTXP algorithm.</span></span>  
  
#### <a name="to-add-an-artxp-time-series-mining-model"></a><span data-ttu-id="63864-152">Para adicionar um modelo de mineração de série temporal ARTXP</span><span class="sxs-lookup"><span data-stu-id="63864-152">To add an ARTXP time series mining model</span></span>  
  
1.  <span data-ttu-id="63864-153">Copie o código a seguir em uma janela de consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="63864-153">Copy the following code into a blank query window.</span></span>  
  
     <span data-ttu-id="63864-154">Observe que não é necessário alterar nada, exceto o nome do novo modelo de mineração e o valor do parâmetro FORECAST_METHOD.</span><span class="sxs-lookup"><span data-stu-id="63864-154">Note that you do not need to change anything except the name of the new mining model, and the value of the FORECAST_METHOD parameter.</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARTXP]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARTXP')  
    WITH DRILLTHROUGH  
    ```  
  
2.  <span data-ttu-id="63864-155">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="63864-155">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
3.  <span data-ttu-id="63864-156">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Forecasting_ARTXP.dmx` .</span><span class="sxs-lookup"><span data-stu-id="63864-156">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARTXP.dmx`.</span></span>  
  
4.  <span data-ttu-id="63864-157">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="63864-157">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="63864-158">Na próxima lição, você processará todos os modelos e a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="63864-158">In the next lesson, you will process all of the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="63864-159">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="63864-159">Next Lesson</span></span>  
 [<span data-ttu-id="63864-160">Lição 3: Processando a estrutura e os modelos de série temporal</span><span class="sxs-lookup"><span data-stu-id="63864-160">Lesson 3: Processing the Time Series Structure and Models</span></span>](../../2014/tutorials/lesson-3-processing-the-time-series-structure-and-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="63864-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63864-161">See Also</span></span>  
 <span data-ttu-id="63864-162">[Algoritmo do Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="63864-162">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 [<span data-ttu-id="63864-163">Referência técnica do algoritmo MTS</span><span class="sxs-lookup"><span data-stu-id="63864-163">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
