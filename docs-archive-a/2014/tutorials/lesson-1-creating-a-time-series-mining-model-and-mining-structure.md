---
title: 'Lição 1: Criando um modelo de mineração de série temporal e uma estrutura de mineração | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b201f2b8-9ab5-425b-9ff3-fe321a60a7b7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2513bc3837dd224f6561eb0015ced538ea3add8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570399"
---
# <a name="lesson-1-creating-a-time-series-mining-model-and-mining-structure"></a><span data-ttu-id="ce3af-102">Lição 1: Criando um modelo de mineração de série temporal e uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="ce3af-102">Lesson 1: Creating a Time Series Mining Model and Mining Structure</span></span>
  <span data-ttu-id="ce3af-103">Nesta lição, você criará um modelo de mineração que permite prever valores com o passar do tempo, com base em dados históricos.</span><span class="sxs-lookup"><span data-stu-id="ce3af-103">In this lesson, you will create a mining model that allows you to predict values over time, based on historical data.</span></span> <span data-ttu-id="ce3af-104">Quando você criar o modelo, a estrutura subjacente será gerada automaticamente e poderá ser usada como a base para outros modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="ce3af-104">When you create the model, the underlying structure will be generated automatically and can be used as the basis for additional mining models.</span></span>  
  
 <span data-ttu-id="ce3af-105">Esta lição supõe que você já conhece modelos de previsão e os requisitos do algoritmo MTS.</span><span class="sxs-lookup"><span data-stu-id="ce3af-105">This lesson assumes that you are familiar with forecasting models and with the requirements of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="ce3af-106">Para obter mais informações, consulte [Algoritmo MTS](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="ce3af-106">For more information, see [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span></span>  
  
## <a name="create-mining-model-statement"></a><span data-ttu-id="ce3af-107">Instrução CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="ce3af-107">CREATE MINING MODEL Statement</span></span>  
 <span data-ttu-id="ce3af-108">Para criar um modelo de mineração diretamente e gerar automaticamente a estrutura de mineração subjacente, use a instrução [criar modelo de mineração &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) .</span><span class="sxs-lookup"><span data-stu-id="ce3af-108">In order to create a mining model directly and automatically generate the underlying mining structure, you use the [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) statement.</span></span> <span data-ttu-id="ce3af-109">O código na instrução pode ser dividido nas seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="ce3af-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="ce3af-110">Nomeando o modelo</span><span class="sxs-lookup"><span data-stu-id="ce3af-110">Naming the model</span></span>  
  
-   <span data-ttu-id="ce3af-111">Definindo o carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="ce3af-111">Defining the time stamp</span></span>  
  
-   <span data-ttu-id="ce3af-112">Definindo coluna de chave da série opcional</span><span class="sxs-lookup"><span data-stu-id="ce3af-112">Defining the optional series key column</span></span>  
  
-   <span data-ttu-id="ce3af-113">Definindo o atributo ou os atributos previsíveis</span><span class="sxs-lookup"><span data-stu-id="ce3af-113">Defining the predictable attribute or attributes</span></span>  
  
 <span data-ttu-id="ce3af-114">A seguir, um exemplo genérico da instrução CREATE MINING MODEL:</span><span class="sxs-lookup"><span data-stu-id="ce3af-114">The following is a generic example of the CREATE MINING MODEL statement:</span></span>  
  
```  
CREATE MINING MODEL [<Mining Structure Name>]  
(  
   <key columns>,  
   <predictable attribute columns>  
)  
USING <algorithm name>([parameter list])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="ce3af-115">A primeira linha do código define o nome do modelo de mineração:</span><span class="sxs-lookup"><span data-stu-id="ce3af-115">The first line of the code defines the name of the mining model:</span></span>  
  
```  
CREATE MINING MODEL [Mining Model Name]  
```  
  
 <span data-ttu-id="ce3af-116">O Analysis Services gera automaticamente um nome para a estrutura subjacente, ao anexar "_structure" ao nome do modelo, o que garante que o nome da estrutura seja diferente do nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="ce3af-116">Analysis Services automatically generates a name for the underlying structure, by appending "_structure" to the model name, which ensures that the structure name is unique from the model name.</span></span> <span data-ttu-id="ce3af-117">Para obter informações sobre como nomear um objeto no DMX, consulte [identificadores &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="ce3af-117">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="ce3af-118">A próxima linha do código define a coluna de chave do modelo de mineração que, no caso de um modelo de série temporal identifica exclusivamente um período na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ce3af-118">The next line of the code defines the key column for the mining model, which in the case of a time series model uniquely identifies a time step in the source data.</span></span> <span data-ttu-id="ce3af-119">A etapa temporal é identificada com as palavras-chave `KEY TIME` após o nome da coluna e os tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="ce3af-119">The time step is identified with the `KEY TIME` keywords after the column name and data types.</span></span> <span data-ttu-id="ce3af-120">Se o modelo de série temporal tiver uma chave de série separada, será identificado pela palavra-chave `KEY`.</span><span class="sxs-lookup"><span data-stu-id="ce3af-120">If the time series model has a separate series key, it is identified by using the `KEY` keyword.</span></span>  
  
```  
<key columns>  
```  
  
 <span data-ttu-id="ce3af-121">A próxima linha do código é usada para definir as colunas do modelo que serão previstas.</span><span class="sxs-lookup"><span data-stu-id="ce3af-121">The next line of the code is used to define the columns in the model that will be predicted.</span></span> <span data-ttu-id="ce3af-122">Você pode ter vários atributos previsíveis em um único modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="ce3af-122">You can have multiple predictable attributes in a single mining model.</span></span> <span data-ttu-id="ce3af-123">Quando há vários atributos previsíveis, o algoritmo MTS gera uma análise separada para cada série:</span><span class="sxs-lookup"><span data-stu-id="ce3af-123">When there are multiple predictable attributes, the Microsoft Time Series algorithm generates a separate analysis for each series:</span></span>  
  
```  
<predictable attribute columns>  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="ce3af-124">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="ce3af-124">Lesson Tasks</span></span>  
 <span data-ttu-id="ce3af-125">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="ce3af-125">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="ce3af-126">Criar uma nova consulta em branco</span><span class="sxs-lookup"><span data-stu-id="ce3af-126">Create a new blank query</span></span>  
  
-   <span data-ttu-id="ce3af-127">Alterar a consulta para criar o modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="ce3af-127">Alter the query to create the mining model</span></span>  
  
-   <span data-ttu-id="ce3af-128">Executar a consulta</span><span class="sxs-lookup"><span data-stu-id="ce3af-128">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="ce3af-129">Criando a consulta</span><span class="sxs-lookup"><span data-stu-id="ce3af-129">Creating the Query</span></span>  
 <span data-ttu-id="ce3af-130">A primeira etapa é se conectar a uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e criar uma nova consulta DMX no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce3af-130">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="ce3af-131">Para criar uma nova consulta DMX no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce3af-131">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="ce3af-132">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce3af-132">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="ce3af-133">Na caixa de diálogo **conectar ao servidor** , para **tipo de servidor**, selecione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="ce3af-133">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="ce3af-134">Em **nome do servidor**, digite `LocalHost` ou o nome da instância do à [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qual você deseja se conectar para esta lição.</span><span class="sxs-lookup"><span data-stu-id="ce3af-134">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="ce3af-135">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ce3af-135">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="ce3af-136">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="ce3af-136">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="ce3af-137">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="ce3af-137">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="ce3af-138">Alterando a consulta</span><span class="sxs-lookup"><span data-stu-id="ce3af-138">Altering the Query</span></span>  
 <span data-ttu-id="ce3af-139">A próxima etapa é modificar a instrução CREATE MINING MODEL para criar o modelo de mineração usado para previsão, junto com sua estrutura de mineração subjacente.</span><span class="sxs-lookup"><span data-stu-id="ce3af-139">The next step is to modify the CREATE MINING MODEL statement to create the mining model used for forecasting, together with its underlying mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-model-statement"></a><span data-ttu-id="ce3af-140">Para personalizar a instrução CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="ce3af-140">To customize the CREATE MINING MODEL statement</span></span>  
  
1.  <span data-ttu-id="ce3af-141">No Editor de Consultas, copie o exemplo genérico da instrução CREATE MINING MODEL na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="ce3af-141">In Query Editor, copy the generic example of the CREATE MINING MODEL statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="ce3af-142">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce3af-142">Replace the following:</span></span>  
  
    ```  
    [mining model name]   
    ```  
  
     <span data-ttu-id="ce3af-143">por:</span><span class="sxs-lookup"><span data-stu-id="ce3af-143">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
3.  <span data-ttu-id="ce3af-144">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce3af-144">Replace the following:</span></span>  
  
    ```  
    <key columns>  
    ```  
  
     <span data-ttu-id="ce3af-145">por:</span><span class="sxs-lookup"><span data-stu-id="ce3af-145">with:</span></span>  
  
    ```  
    [Reporting Date] DATE KEY TIME,  
    [Model Region] TEXT KEY  
    ```  
  
     <span data-ttu-id="ce3af-146">A palavra-chave `TIME KEY` indica que a coluna ReportingDate contém os valores de período usados na classificação dos valores.</span><span class="sxs-lookup"><span data-stu-id="ce3af-146">The `TIME KEY` keyword indicates that the ReportingDate column contains the time step values used to order the values.</span></span> <span data-ttu-id="ce3af-147">Períodos podem ser datas e horas, inteiros ou qualquer tipo de dados classificado, desde que os valores sejam exclusivos e que os dados estejam classificados.</span><span class="sxs-lookup"><span data-stu-id="ce3af-147">Time steps can be dates and times, integers, or any ordered data type, so long as the values are unique and the data is sorted.</span></span>  
  
     <span data-ttu-id="ce3af-148">As palavras-chave `TEXT` e `KEY` indicam que a coluna ModelRegion contém uma chave de série adicional.</span><span class="sxs-lookup"><span data-stu-id="ce3af-148">The `TEXT` and `KEY` keywords indicate that the ModelRegion column contains an additional series key.</span></span> <span data-ttu-id="ce3af-149">Você só pode ter uma chave de série e os valores da coluna devem ser distintos.</span><span class="sxs-lookup"><span data-stu-id="ce3af-149">You can have only one series key, and the values in the column must be distinct.</span></span>  
  
4.  <span data-ttu-id="ce3af-150">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce3af-150">Replace the following:</span></span>  
  
    ```  
    < predictable attribute columns> )  
    ```  
  
     <span data-ttu-id="ce3af-151">por:</span><span class="sxs-lookup"><span data-stu-id="ce3af-151">with:</span></span>  
  
    ```  
    [Quantity] LONG CONTINUOUS PREDICT,  
    [Amount] DOUBLE CONTINUOUS PREDICT  
    )  
    ```  
  
5.  <span data-ttu-id="ce3af-152">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce3af-152">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([parameter list])  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="ce3af-153">por:</span><span class="sxs-lookup"><span data-stu-id="ce3af-153">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series(AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="ce3af-154">O parâmetro do algoritmo `AUTO_DETECT_PERIODICITY` = 0.8 indica que você deseja que o algoritmo detecte ciclos nos dados.</span><span class="sxs-lookup"><span data-stu-id="ce3af-154">The algorithm parameter, `AUTO_DETECT_PERIODICITY` = 0.8, indicates that you want the algorithm to detect cycles in the data.</span></span> <span data-ttu-id="ce3af-155">Definir esse valor mais próximo a 1 favorece a descoberta de vários padrões mas pode diminuir a velocidade de processamento.</span><span class="sxs-lookup"><span data-stu-id="ce3af-155">Setting this value closer to 1 favors the discovery of many patterns but can slow processing.</span></span>  
  
     <span data-ttu-id="ce3af-156">O parâmetro de algoritmo `FORECAST_METHOD` indica se você deseja que os dados sejam analisados usando ARTXP, ARIMA ou uma mistura de ambos.</span><span class="sxs-lookup"><span data-stu-id="ce3af-156">The algorithm parameter, `FORECAST_METHOD`, indicates whether you want the data to be analyzed using ARTXP, ARIMA, or a mixture of both.</span></span>  
  
     <span data-ttu-id="ce3af-157">A palavra-chave `WITH DRILLTHROUGH` especifica que você deseja ser capaz de exibir estatísticas detalhadas nos dados de origem após a conclusão do modelo.</span><span class="sxs-lookup"><span data-stu-id="ce3af-157">The keyword, `WITH DRILLTHROUGH`, specify that you want to be able to view detailed statistics in the source data after the model is complete.</span></span> <span data-ttu-id="ce3af-158">Adicione esta cláusula se quiser navegar pelos detalhes do modelo usando o Visualizador MTS.</span><span class="sxs-lookup"><span data-stu-id="ce3af-158">You must add this clause if you want to browse the model by using the Microsoft Time Series Viewer.</span></span> <span data-ttu-id="ce3af-159">Ela não é obrigatória para a previsão.</span><span class="sxs-lookup"><span data-stu-id="ce3af-159">It is not required for prediction.</span></span>  
  
     <span data-ttu-id="ce3af-160">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="ce3af-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING MODEL [Forecasting_MIXED]  
         (  
        [Reporting Date] DATE KEY TIME,  
        [Model Region] TEXT KEY,  
        [Quantity] LONG CONTINUOUS PREDICT,  
        [Amount] DOUBLE CONTINUOUS PREDICT  
        )  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
  
    ```  
  
6.  <span data-ttu-id="ce3af-161">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="ce3af-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="ce3af-162">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Forecasting_MIXED.dmx` .</span><span class="sxs-lookup"><span data-stu-id="ce3af-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_MIXED.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="ce3af-163">Executando a consulta</span><span class="sxs-lookup"><span data-stu-id="ce3af-163">Executing the Query</span></span>  
 <span data-ttu-id="ce3af-164">A última etapa é executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="ce3af-164">The final step is to execute the query.</span></span> <span data-ttu-id="ce3af-165">Depois que você cria e salva a consulta, ela deve ser executada para criar o modelo de mineração e sua estrutura de mineração no servidor.</span><span class="sxs-lookup"><span data-stu-id="ce3af-165">After a query is created and saved, it needs to be executed to create the mining model and its mining structure on the server.</span></span> <span data-ttu-id="ce3af-166">Para obter mais informações sobre a execução de consultas no editor de consultas, consulte [mecanismo de banco de dados editor de consultas &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ce3af-166">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="ce3af-167">Para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="ce3af-167">To execute the query</span></span>  
  
-   <span data-ttu-id="ce3af-168">No editor de consultas, na barra de ferramentas, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="ce3af-168">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="ce3af-169">O status da consulta é exibido na guia **mensagens** na parte inferior do editor de consultas após a conclusão da execução da instrução.</span><span class="sxs-lookup"><span data-stu-id="ce3af-169">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="ce3af-170">As mensagens devem exibir:</span><span class="sxs-lookup"><span data-stu-id="ce3af-170">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="ce3af-171">Uma nova estrutura chamada **Forecasting_MIXED_Structure** agora existe no servidor, junto com o modelo de mineração relacionado **Forecasting_MIXED**.</span><span class="sxs-lookup"><span data-stu-id="ce3af-171">A new structure named **Forecasting_MIXED_Structure** now exists on the server, together with the related mining model **Forecasting_MIXED**.</span></span>  
  
 <span data-ttu-id="ce3af-172">Na próxima lição, você adicionará um modelo de mineração à estrutura de mineração de **Forecasting_MIXED** que acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="ce3af-172">In the next lesson, you will add a mining model to the **Forecasting_MIXED** mining structure that you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="ce3af-173">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="ce3af-173">Next Lesson</span></span>  
 [<span data-ttu-id="ce3af-174">Lição 2: Adicionando modelos de mineração à estrutura de mineração de série temporal</span><span class="sxs-lookup"><span data-stu-id="ce3af-174">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce3af-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ce3af-175">See Also</span></span>  
 <span data-ttu-id="ce3af-176">[Conteúdo do modelo de mineração para modelos de série temporal &#40;mineração de dados Analysis Services&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ce3af-176">[Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="ce3af-177">Referência técnica do algoritmo MTS</span><span class="sxs-lookup"><span data-stu-id="ce3af-177">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
