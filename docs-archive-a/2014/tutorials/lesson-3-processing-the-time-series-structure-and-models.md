---
title: 'Lição 3: processando a estrutura e os modelos de série temporal | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 16e27b57-eae1-47a7-a02c-47b6ed487d87
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 493d27c9836eb765c655eba5bbb004e4d48cde40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681300"
---
# <a name="lesson-3-processing-the-time-series-structure-and-models"></a><span data-ttu-id="fb403-102">Lição 3: Processando a estrutura e os modelos de série temporal</span><span class="sxs-lookup"><span data-stu-id="fb403-102">Lesson 3: Processing the Time Series Structure and Models</span></span>
  <span data-ttu-id="fb403-103">Nesta lição, você usará a instrução [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) para processar as estruturas de mineração de série temporal e os modelos de mineração que você criou.</span><span class="sxs-lookup"><span data-stu-id="fb403-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement to process the time series mining structures and mining models that you created.</span></span>  
  
 <span data-ttu-id="fb403-104">Ao processar uma estrutura de mineração, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lê os dados de origem e compila as estruturas que dão suporte a modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="fb403-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="fb403-105">Sempre será necessário processar um modelo e uma estrutura de mineração em sua criação.</span><span class="sxs-lookup"><span data-stu-id="fb403-105">You always have to process a mining model and structure when you first create it.</span></span> <span data-ttu-id="fb403-106">Se você especificar a estrutura de mineração ao usar INSERT INTO, a instrução processará a estrutura de mineração e todos os seus modelos de mineração associados.</span><span class="sxs-lookup"><span data-stu-id="fb403-106">If you specify the mining structure when using INSERT INTO, the statement processes the mining structure and all its associated mining models.</span></span>  
  
 <span data-ttu-id="fb403-107">Quando você adicionar um modelo de mineração a uma estrutura de mineração que já foi processada, será possível usar a instrução `INSERT INTO MINING MODEL` para processar somente o novo modelo de mineração usando os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="fb403-107">When you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to process just the new mining model by using the existing data.</span></span>  
  
 <span data-ttu-id="fb403-108">Para obter mais informações sobre o processamento de modelos de mineração, consulte [requisitos e considerações de processamento &#40;&#41;de mineração de dados ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="fb403-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="fb403-109">Instrução INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="fb403-109">INSERT INTO Statement</span></span>  
 <span data-ttu-id="fb403-110">Para treinar a estrutura de mineração de série temporal e todos os seus modelos de mineração associados, use a instrução [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="fb403-110">In order to train the time series mining structure and all its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="fb403-111">O código na instrução pode ser dividido nas seguintes partes.</span><span class="sxs-lookup"><span data-stu-id="fb403-111">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="fb403-112">Identificando a estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="fb403-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="fb403-113">Listando as colunas na estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="fb403-113">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="fb403-114">Definindo os dados de treinamento</span><span class="sxs-lookup"><span data-stu-id="fb403-114">Defining the training data</span></span>  
  
 <span data-ttu-id="fb403-115">A seguir, um exemplo genérico da instrução `INSERT INTO`:</span><span class="sxs-lookup"><span data-stu-id="fb403-115">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="fb403-116">A primeira linha do código identifica a estrutura de mineração a ser treinada:</span><span class="sxs-lookup"><span data-stu-id="fb403-116">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="fb403-117">As linhas seguintes do código especificam as colunas definidas pela estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="fb403-117">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="fb403-118">É preciso listar cada coluna na estrutura de mineração, e cada coluna deve mapear para uma coluna contida nos dados da consulta de origem.</span><span class="sxs-lookup"><span data-stu-id="fb403-118">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="fb403-119">As linhas finais do código definem os dados que serão usados para treinar a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="fb403-119">The final lines of the code define the data that will be used to train the mining structure.</span></span>  
  
```  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="fb403-120">Nesta lição, use `OPENQUERY` para definir os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="fb403-120">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="fb403-121">Para obter mais informações sobre outros métodos de definição de uma consulta nos dados de origem, consulte [&#60;&#62;de consulta de dados de origem ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="fb403-121">For more information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="fb403-122">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="fb403-122">Lesson Tasks</span></span>  
 <span data-ttu-id="fb403-123">Você executará a seguinte tarefa nesta lição:</span><span class="sxs-lookup"><span data-stu-id="fb403-123">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="fb403-124">Processar a estrutura de mineração Forecasting_MIXED_Structure</span><span class="sxs-lookup"><span data-stu-id="fb403-124">Process the mining structure Forecasting_MIXED_Structure</span></span>  
  
-   <span data-ttu-id="fb403-125">Processar os modelos de mineração relacionados Forecasting_MIXED, Forecasting_ARIMA e Forecasting_ARTXP</span><span class="sxs-lookup"><span data-stu-id="fb403-125">Process the related mining models Forecasting_MIXED, Forecasting_ARIMA, and Forecasting_ARTXP</span></span>  
  
## <a name="processing-the-time-series-mining-structure"></a><span data-ttu-id="fb403-126">Processando a estrutura de mineração de série temporal</span><span class="sxs-lookup"><span data-stu-id="fb403-126">Processing the Time Series Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-and-related-mining-models-by-using-insert-into"></a><span data-ttu-id="fb403-127">Para processar a estrutura de mineração e os modelos de mineração relacionados usando INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="fb403-127">To process the mining structure and related mining models by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="fb403-128">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="fb403-128">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="fb403-129">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="fb403-129">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="fb403-130">Copie o exemplo genérico da instrução INSERT INTO no campo em branco da consulta.</span><span class="sxs-lookup"><span data-stu-id="fb403-130">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="fb403-131">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb403-131">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="fb403-132">por:</span><span class="sxs-lookup"><span data-stu-id="fb403-132">with:</span></span>  
  
    ```  
    Forecasting_MIXED_Structure  
    ```  
  
4.  <span data-ttu-id="fb403-133">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb403-133">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="fb403-134">por:</span><span class="sxs-lookup"><span data-stu-id="fb403-134">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]   
    ```  
  
5.  <span data-ttu-id="fb403-135">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb403-135">Replace the following:</span></span>  
  
    ```  
    OPENQUERY(<source data definition>)  
    ```  
  
     <span data-ttu-id="fb403-136">por:</span><span class="sxs-lookup"><span data-stu-id="fb403-136">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2008R2],'SELECT [ReportingDate], [ModelRegion], [Quantity], [Amount]  
    FROM vTimeSeries ORDER BY [ReportingDate]')  
    ```  
  
     <span data-ttu-id="fb403-137">A consulta de origem faz referência à [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] fonte de dados definida no projeto de exemplo IntermediateTutorial.</span><span class="sxs-lookup"><span data-stu-id="fb403-137">The source query references the  [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the IntermediateTutorial sample project.</span></span> <span data-ttu-id="fb403-138">Ela usa esta fonte de dados para acessar a exibição vTimeSeries.</span><span class="sxs-lookup"><span data-stu-id="fb403-138">It uses this data source to access the view vTimeSeries.</span></span> <span data-ttu-id="fb403-139">Essa exibição contém os dados de origem que serão usados para treinar o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="fb403-139">This view contains the source data that will be used to train the mining model.</span></span> <span data-ttu-id="fb403-140">Se você não estiver familiarizado com este projeto ou com essas exibições, consulte[lição 2: Criando um cenário de previsão &#40;tutorial de mineração de dados intermediário&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="fb403-140">If you are not familiar with this project or this views, see[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="fb403-141">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="fb403-141">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Forecasting_MIXED_Structure]  
    (  
       [ReportingDate],[ModelRegion],[Quantity],[Amount])  
    )  
    OPENQUERY(  
    [Adventure Works DW 2008R2],  
    'SELECT [ReportingDate],[ModelRegion],[Quantity],[Amount] FROM vTimeSeries ORDER BY [ReportingDate]'  
    )   
    ```  
  
6.  <span data-ttu-id="fb403-142">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="fb403-142">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="fb403-143">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `ProcessForecastingAll.dmx` .</span><span class="sxs-lookup"><span data-stu-id="fb403-143">In the **Save As** dialog box, browse to the appropriate folder, and name the file `ProcessForecastingAll.dmx`.</span></span>  
  
8.  <span data-ttu-id="fb403-144">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="fb403-144">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="fb403-145">Depois que execução da consulta for concluída, você poderá criar previsões usando os modelos de mineração processados.</span><span class="sxs-lookup"><span data-stu-id="fb403-145">After the query has finished running, you can create predictions by using the processed mining models.</span></span> <span data-ttu-id="fb403-146">Na próxima lição, você criará várias previsões com base nos modelos de mineração que criou.</span><span class="sxs-lookup"><span data-stu-id="fb403-146">In the next lesson, you will create several predictions based on the mining models that you created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="fb403-147">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="fb403-147">Next Lesson</span></span>  
 [<span data-ttu-id="fb403-148">Lição 4: Criando previsões de série temporal usando DMX</span><span class="sxs-lookup"><span data-stu-id="fb403-148">Lesson 4: Creating Time Series Predictions Using DMX</span></span>](../../2014/tutorials/lesson-4-creating-time-series-predictions-using-dmx.md)  
  
## <a name="see-also"></a><span data-ttu-id="fb403-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb403-149">See Also</span></span>  
 <span data-ttu-id="fb403-150">[Requisitos e considerações de processamento &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="fb403-150">[Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span></span>  
 <span data-ttu-id="fb403-151">[&#62;de consulta de dados de origem&#60;](/sql/dmx/source-data-query) </span><span class="sxs-lookup"><span data-stu-id="fb403-151">[&#60;source data query&#62;](/sql/dmx/source-data-query) </span></span>  
 [<span data-ttu-id="fb403-152">&#40;DE&#41;DE OPENQUERY DO DMX</span><span class="sxs-lookup"><span data-stu-id="fb403-152">OPENQUERY &#40;DMX&#41;</span></span>](/sql/dmx/source-data-query-openquery)  
  
  
