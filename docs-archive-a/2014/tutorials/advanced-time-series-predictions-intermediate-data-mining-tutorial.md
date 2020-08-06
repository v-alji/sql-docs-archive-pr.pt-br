---
title: Previsões avançadas de série temporal (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b614ebdb-07ca-44af-a0ff-893364bd4b71
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 70ebf856ba0782cbf44969aba30602818015582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683216"
---
# <a name="advanced-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="3a451-102">Previsões de série temporal avançadas (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="3a451-102">Advanced Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="3a451-103">Você viu na exploração do modelo de previsão que embora as vendas na maioria das regiões siga um padrão similar, algumas regiões e alguns modelos, como o M200 na região do Pacífico, exibem tendências muito diferentes.</span><span class="sxs-lookup"><span data-stu-id="3a451-103">You saw from exploring the forecasting model that although sales in most of the regions follow a similar pattern, some regions and some models, such as the M200 model in the Pacific region, exhibit very different trends.</span></span> <span data-ttu-id="3a451-104">Isso não é surpresa para você, já que sabe que as diferenças entre as regiões são comuns e podem ser causadas por muitos fatores, incluindo promoções de marketing, geração de relatórios imprecisos ou eventos geopolíticos.</span><span class="sxs-lookup"><span data-stu-id="3a451-104">This does not surprise you, as you know that differences among regions are common and can be caused by many factors, including marketing promotions, inaccurate reporting, or geopolitical events.</span></span>  
  
 <span data-ttu-id="3a451-105">Porém, seus usuários estão pedindo um modelo que possa ser aplicado no mundo todo.</span><span class="sxs-lookup"><span data-stu-id="3a451-105">However, your users are asking for a model that can be applied worldwide.</span></span> <span data-ttu-id="3a451-106">Portanto, para minimizar o efeito dos fatores individuais sobre as projeções, você decide criar um modelo baseado em medidas agregadas de vendas mundiais.</span><span class="sxs-lookup"><span data-stu-id="3a451-106">Therefore, to minimize the effect of individual factors on projections, you decide to build a model that is based on aggregated measures of worldwide sales.</span></span> <span data-ttu-id="3a451-107">Assim, você poderá fazer previsões com esse modelo para cada região.</span><span class="sxs-lookup"><span data-stu-id="3a451-107">You can then use this model to make predictions for each individual region.</span></span>  
  
 <span data-ttu-id="3a451-108">Nesta tarefa, você criará todas as fontes de dados de que precisa para executar as tarefas de previsão avançadas.</span><span class="sxs-lookup"><span data-stu-id="3a451-108">In this task, you will build all the data sources that you need to perform the advanced prediction tasks.</span></span> <span data-ttu-id="3a451-109">Você criará duas exibições de fonte de dados para usar como entradas para a consulta de previsão, e uma exibição de fonte de dados para usar na criação de um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="3a451-109">You will create two data source views for use as inputs to the prediction query, and one data source view to use in building a new model.</span></span>  
  
 <span data-ttu-id="3a451-110">**Etapas**</span><span class="sxs-lookup"><span data-stu-id="3a451-110">**Steps**</span></span>  
  
1.  [<span data-ttu-id="3a451-111">Preparar os dados de vendas estendidos (para previsão)</span><span class="sxs-lookup"><span data-stu-id="3a451-111">Prepare the extended sales data (for prediction)</span></span>](#bkmk_newExtendData)  
  
2.  [<span data-ttu-id="3a451-112">Preparar os dados agregados (para criar o modelo)</span><span class="sxs-lookup"><span data-stu-id="3a451-112">Prepare the aggregated data (for building the model)</span></span>](#bkmk_newReplaceData)  
  
3.  [<span data-ttu-id="3a451-113">Preparar a série de dados (para previsão cruzada)</span><span class="sxs-lookup"><span data-stu-id="3a451-113">Prepare the series data (for cross-prediction)</span></span>](#bkmk_CrossData2)  
  
4.  [<span data-ttu-id="3a451-114">Fazer a previsão usando EXTEND</span><span class="sxs-lookup"><span data-stu-id="3a451-114">Predict using EXTEND</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
5.  [<span data-ttu-id="3a451-115">Criar o modelo de previsão cruzada</span><span class="sxs-lookup"><span data-stu-id="3a451-115">Create the cross-prediction model</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
6.  [<span data-ttu-id="3a451-116">Fazer a previsão usando REPLACE</span><span class="sxs-lookup"><span data-stu-id="3a451-116">Predict using REPLACE</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
7.  [<span data-ttu-id="3a451-117">Revisar as novas previsões</span><span class="sxs-lookup"><span data-stu-id="3a451-117">Review the new predictions</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
##  <a name="creating-the-new-extended-sales-data"></a><a name="bkmk_newExtendData"></a><span data-ttu-id="3a451-118">Criando os novos dados de vendas estendidos</span><span class="sxs-lookup"><span data-stu-id="3a451-118">Creating the New Extended Sales Data</span></span>  
 <span data-ttu-id="3a451-119">Para atualizar seus dados de vendas, você precisará obter os números de vendas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="3a451-119">To update your sales data, you will need to get the latest sales figures.</span></span> <span data-ttu-id="3a451-120">De interesse em particular são os dados da região do Pacífico, que iniciou uma promoção de vendas regional para chamar a atenção para as novas lojas e aumentar o reconhecimento de seus produtos.</span><span class="sxs-lookup"><span data-stu-id="3a451-120">Of particular interest are the data just in from the Pacific region, which launched a regional sales promotion to call attention to the new stores and raise awareness of their products.</span></span>  
  
 <span data-ttu-id="3a451-121">Para este cenário, vamos pressupor que os dados foram importados de uma pasta de trabalho do Excel que contém apenas três meses de novos dados para algumas regiões.</span><span class="sxs-lookup"><span data-stu-id="3a451-121">For this scenario, we'll assume that the data has been imported from an Excel workbook that contains just three months of new data for a couple of regions.</span></span> <span data-ttu-id="3a451-122">Você criará uma tabela para os dados usando um script Transact-SQL e, em seguida, definirá uma exibição da fonte de dados a ser usada para previsão.</span><span class="sxs-lookup"><span data-stu-id="3a451-122">You'll create a table for the data using a Transact-SQL script, and then define a data source view to use for prediction.</span></span>  
  
#### <a name="create-the-table-with-new-sales-data"></a><span data-ttu-id="3a451-123">Criar a tabela com os novos dados de vendas</span><span class="sxs-lookup"><span data-stu-id="3a451-123">Create the table with new sales data</span></span>  
  
1.  <span data-ttu-id="3a451-124">Em uma janela de consulta do Transact-SQL, execute a instrução a seguir para adicionar os dados de vendas ao banco de dados AdventureWorksDW (ou qualquer outro banco de dados).</span><span class="sxs-lookup"><span data-stu-id="3a451-124">In a Transact-SQL query window, execute the following statement to add the sales data to the AdventureWorksDW database (or any other database).</span></span>  
  
    ```  
    USE [database name];  
    GO  
    IF OBJECT_ID ([dbo].[NewSalesData]) IS NOT NULL   
        DROP TABLE [dbo].[NewSalesData];  
    GO  
    CREATE TABLE [dbo].[NewSalesData]([Series] [nvarchar](255) NULL,  
    [NewDate] [datetime] NULL,  
    [NewQty] [float] NULL,  
    [NewAmount] [money] NULL) ON [PRIMARY]  
  
    GO  
    ```  
  
2.  <span data-ttu-id="3a451-125">Insira os novos valores usando o script a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a451-125">Insert the new values using the following script.</span></span>  
  
    ```  
    INSERT INTO [NewSalesData]  
    (Series,NewDate,NewQty,NewAmount)  
    VALUES('T1000 Pacific', '7/25/08', 55, '$130,170.22'),  
    ('T1000 Pacific', '8/25/08', 50, '$114,435.36 '),  
    ('T1000 Pacific', '9/25/08', 50, '$117,296.24 '),  
    ('T1000 Europe', '7/25/08', 37, '$88,210.00 '),  
    ('T1000 Europe', '8/25/08', 41, '$97,746.00 '),  
    ('T1000 Europe', '9/25/08', 37, '$88,210.00 '),  
    ('T1000 North America', '7/25/08', 69, '$164,500.00 '),  
    ('T1000 North America', '8/25/08', 66, '$157,348.00 '),  
    ('T1000 North America', '9/25/08', 58, '$138,276.00 '),  
    ('M200 Pacific', '7/25/08', 65, '$149,824.35'),  
    ('M200 Pacific', '8/25/08', 54,  '$124,619.46'),  
    ('M200 Pacific', '9/25/08', 61, '$141,143.39'),  
    ('M200 Europe', '7/25/08', 75, '$173,026.00'),  
    ('M200 Europe', '8/25/08', 76, '$175,212.00'),  
    ('M200 Europe', '9/25/08', 84, '$193,731.00'),  
    ('M200 North America', '7/25/08', 94, '$216,916.00'),  
    ('M200 North America', '8/25/08', 94, '$216,891.00'),  
    ('M200 North America', '9/25/08', 91,'$209,943.00');  
    ```  
  
    > [!WARNING]  
    >  <span data-ttu-id="3a451-126">Os aspas são usadas com os valores de moeda para evitar problemas com o separador de vírgula e o símbolo de moeda.</span><span class="sxs-lookup"><span data-stu-id="3a451-126">The quotation marks are used with the currency values to prevent problems with the comma separator and the currency symbol.</span></span> <span data-ttu-id="3a451-127">Você também pode transmitir os valores de moeda neste formato: `130170.22`</span><span class="sxs-lookup"><span data-stu-id="3a451-127">You could also pass in the currency values in this format: `130170.22`</span></span>  
    >   
    >  <span data-ttu-id="3a451-128">Observe que as datas usadas no banco de dados de exemplo foram alteradas para esta versão.</span><span class="sxs-lookup"><span data-stu-id="3a451-128">Note that the dates used in the sample database have changed for this release.</span></span> <span data-ttu-id="3a451-129">Se você estiver usando uma edição anterior do AdventureWorks, poderá precisar ajustar as datas inseridas de acordo.</span><span class="sxs-lookup"><span data-stu-id="3a451-129">If you are using an earlier edition of AdventureWorks, you might need to adjust the inserted dates accordingly.</span></span>  
  
###  <a name="create-a-data-source-view-using-the-new-sales-data"></a><a name="bkmk_newReplaceData"></a><span data-ttu-id="3a451-130">Criar uma exibição da fonte de dados usando os novos dados de vendas</span><span class="sxs-lookup"><span data-stu-id="3a451-130">Create a data source view using the new sales data</span></span>  
  
1.  <span data-ttu-id="3a451-131">Em **Gerenciador de soluções**, clique com o botão direito do mouse em **exibições da fonte de dados**e selecione **nova exibição da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="3a451-131">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="3a451-132">No Assistente de Exibição da Fonte de Dados, faça as seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="3a451-132">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="3a451-133">**Fonte de dados**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a451-133">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="3a451-134">**Selecionar tabelas e exibições**: selecione a tabela que você acabou de criar, NewSalesData.</span><span class="sxs-lookup"><span data-stu-id="3a451-134">**Select Tables and Views**: Select the table that you just created, NewSalesData.</span></span>  
  
3.  <span data-ttu-id="3a451-135">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3a451-135">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="3a451-136">Na superfície de design da exibição da fonte de dados, clique com o botão direito do mouse em NewSalesData e selecione **explorar dados** para verificar os dados.</span><span class="sxs-lookup"><span data-stu-id="3a451-136">In the Data Source View design surface, right-click NewSalesData, and then select **Explore Data** to verify the data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="3a451-137">Você usará estes dados somente para previsão. Portanto, não importa se os dados estão incompletos.</span><span class="sxs-lookup"><span data-stu-id="3a451-137">You will use this data for prediction only, so it does not matter that the data is incomplete.</span></span>  
  
##  <a name="creating-the-data-for-the-cross-prediction-model"></a><a name="bkmk_CrossData2"></a><span data-ttu-id="3a451-138">Criando os dados para o modelo de previsão cruzada</span><span class="sxs-lookup"><span data-stu-id="3a451-138">Creating the Data for the Cross-Prediction Model</span></span>  
 <span data-ttu-id="3a451-139">Os dados que foram usados no modelo de previsão original já foram agrupados de certa forma pela exibição vTimeSeries, que dividiu vários modelos de bicicleta em um número menor de categorias e mesclou os resultados de países individuais em regiões.</span><span class="sxs-lookup"><span data-stu-id="3a451-139">The data that was used in the original forecasting model was already grouped somewhat by the view vTimeSeries, which collapsed several bike models into a smaller number of categories, and merged results from individual countries into regions.</span></span> <span data-ttu-id="3a451-140">Para criar um modelo que possa ser usado para projeções mundiais, você criará mais algumas agregações simples diretamente no Designer de Exibição da Fonte de Dados.</span><span class="sxs-lookup"><span data-stu-id="3a451-140">To create a model that can be used for world-wide projections, you will create some additional simple aggregations directly in the Data Source View Designer.</span></span> <span data-ttu-id="3a451-141">A nova exibição da fonte de dados contém apenas a soma e a média das vendas de todos os produtos para todas as regiões.</span><span class="sxs-lookup"><span data-stu-id="3a451-141">The new data source view will contain just a sum and an average of the sales of all products for all regions.</span></span>  
  
 <span data-ttu-id="3a451-142">Depois de criar a fonte de dados usada no modelo, você deve criar uma nova exibição da fonte de dados para usar na previsão.</span><span class="sxs-lookup"><span data-stu-id="3a451-142">After you have created the data source used for the model, you must create a new data source view to use for prediction.</span></span> <span data-ttu-id="3a451-143">Por exemplo, se você desejar prever vendas para a Europa usando o novo modelo mundial, deverá preencher os dados somente para a região da Europa.</span><span class="sxs-lookup"><span data-stu-id="3a451-143">For example, if you want to predict sales for Europe using the new worldwide model, you must feed in data for the Europe region only.</span></span> <span data-ttu-id="3a451-144">Dessa forma, você definirá uma nova exibição de fonte de dados que filtra os dados originais, e alterará a condição de filtro para cada conjunto de consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="3a451-144">So you will set up a new data source view that filters the original data, and change the filter condition for each set of prediction queries.</span></span>  
  
#### <a name="to-create-the-model-data-using-a-custom-data-source-view"></a><span data-ttu-id="3a451-145">Para criar os dados do modelo usando uma exibição de fonte de dados personalizada</span><span class="sxs-lookup"><span data-stu-id="3a451-145">To create the model data using a custom data source view</span></span>  
  
1.  <span data-ttu-id="3a451-146">Em **Gerenciador de soluções**, clique com o botão direito do mouse em **exibições da fonte de dados**e selecione **nova exibição da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="3a451-146">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="3a451-147">Na página de boas-vindas do assistente, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3a451-147">On the welcome page of the wizard, click **Next**.</span></span>  
  
3.  <span data-ttu-id="3a451-148">Na página **Selecionar Fonte de Dados** , selecione [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3a451-148">On the **Select Data Source** page, select [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="3a451-149">Na página, **selecione tabelas e exibições**, não adicionar nenhuma tabela – basta clicar em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3a451-149">In the page, **Select Tables and Views**, do not add any tables-just click **Next**.</span></span>  
  
5.  <span data-ttu-id="3a451-150">Na página, **concluindo o assistente**, digite o nome `AllRegions` e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="3a451-150">On the page, **Completing the Wizard**, type the name `AllRegions`, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="3a451-151">Em seguida, clique com o botão direito do mouse na superfície de design da exibição da fonte de dados em branco e selecione **nova consulta nomeada**.</span><span class="sxs-lookup"><span data-stu-id="3a451-151">Next, right-click the blank data source view design surface, and then select **New Named Query**.</span></span>  
  
7.  <span data-ttu-id="3a451-152">Na caixa de diálogo **criar consulta nomeada** , para **nome**, tipo `AllRegions` e **Descrição**, digite **Soma e média de vendas para todos os modelos e regiões**.</span><span class="sxs-lookup"><span data-stu-id="3a451-152">In the **Create Named Query** dialog box, for **Name**, type `AllRegions`, and for **Description**, type **Sum and average of sales for all models and regions**.</span></span>  
  
8.  <span data-ttu-id="3a451-153">No painel de texto do SQL, digite a seguinte instrução e clique em OK:</span><span class="sxs-lookup"><span data-stu-id="3a451-153">In the SQL text pane, type the following statement and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate,   
    SUM([Quantity]) as SumQty, AVG([Quantity]) as AvgQty,  
    SUM([Amount]) AS SumAmt, AVG([Amount]) AS AvgAmt,  
    'All Regions' as [Region]  
    FROM dbo.vTimeSeries   
    GROUP BY ReportingDate  
    ```  
  
9. <span data-ttu-id="3a451-154">Clique com o botão direito do mouse na `AllRegions` tabela e selecione **explorar dados**.</span><span class="sxs-lookup"><span data-stu-id="3a451-154">Right-click the `AllRegions` table, and then select **Explore Data**.</span></span>  
  
###  <a name="to-create-the-series-data-for-cross-prediction"></a><a name="bkmk_CrossData"></a><span data-ttu-id="3a451-155">Para criar os dados de série para previsão cruzada</span><span class="sxs-lookup"><span data-stu-id="3a451-155">To create the series data for cross-prediction</span></span>  
  
1.  <span data-ttu-id="3a451-156">Em **Gerenciador de soluções**, clique com o botão direito do mouse em **exibições da fonte de dados**e selecione **nova exibição da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="3a451-156">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="3a451-157">No Assistente de Exibição da Fonte de Dados, faça as seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="3a451-157">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="3a451-158">**Fonte de dados**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a451-158">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="3a451-159">**Selecionar Tabelas e Exibições**: não selecione nenhuma tabela.</span><span class="sxs-lookup"><span data-stu-id="3a451-159">**Select Tables and Views**: Do not select any tables</span></span>  
  
     <span data-ttu-id="3a451-160">**Nome**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="3a451-160">**Name**: `T1000 Pacific Region`</span></span>  
  
3.  <span data-ttu-id="3a451-161">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3a451-161">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="3a451-162">Clique com o botão direito do mouse na superfície de design vazia para **T1000 Pacífico Region. dsv**e selecione **nova consulta nomeada**.</span><span class="sxs-lookup"><span data-stu-id="3a451-162">Right-click the empty design surface for **T1000 Pacific Region.dsv**, and then select **New Named Query**.</span></span>  
  
     <span data-ttu-id="3a451-163">A caixa de diálogo **Criar Consulta Nomeada** é aberta.</span><span class="sxs-lookup"><span data-stu-id="3a451-163">The **Create Named Query** dialog box appears.</span></span> <span data-ttu-id="3a451-164">Digite o nome novamente e, em seguida, adicione a seguinte descrição:</span><span class="sxs-lookup"><span data-stu-id="3a451-164">Retype the name, and then add the following description:</span></span>  
  
     <span data-ttu-id="3a451-165">**Nome**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="3a451-165">**Name**: `T1000 Pacific Region`</span></span>  
  
     <span data-ttu-id="3a451-166">**Descrição**: **Filtrar `vTimeSeries` por região e modelo**</span><span class="sxs-lookup"><span data-stu-id="3a451-166">**Description**: **Filter`vTimeSeries`by region and model**</span></span>  
  
5.  <span data-ttu-id="3a451-167">No painel de texto, digite a seguinte consulta e clique em OK:</span><span class="sxs-lookup"><span data-stu-id="3a451-167">In the text pane, type the following query, and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate, ModelRegion, Quantity, Amount  
    FROM dbo.vTimeSeries  
    WHERE (ModelRegion = N'T1000 Pacific')  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="3a451-168">Como você precisará criar previsões para cada série separadamente, talvez você queira copiar o texto da consulta e salvá-lo em um arquivo de texto para que seja possível reutilizá-lo na outra série de dados.</span><span class="sxs-lookup"><span data-stu-id="3a451-168">Since you will need to create predictions for each series separately, you might want to copy the query text and save it to a text file so that you can re-use it for the other data series.</span></span>  
  
6.  <span data-ttu-id="3a451-169">Na superfície de design da exibição da fonte de dados, clique com o botão direito do mouse em T1000 Pacífico e, em seguida, selecione **explorar dados** para verificar se os dados foram filtrados corretamente.</span><span class="sxs-lookup"><span data-stu-id="3a451-169">In the Data Source View design surface, right-click T1000 Pacific, and then select **Explore Data** to verify that the data is filtered correctly.</span></span>  
  
     <span data-ttu-id="3a451-170">Você usará esses dados como a entrada para o modelo ao criar consultas da previsão cruzada.</span><span class="sxs-lookup"><span data-stu-id="3a451-170">You will use this data as the input to the model when creating cross-prediction queries.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3a451-171">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="3a451-171">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3a451-172">Previsões de série temporal usando dados atualizados &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="3a451-172">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="3a451-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a451-173">See Also</span></span>  
 <span data-ttu-id="3a451-174">[Algoritmo do Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="3a451-174">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 <span data-ttu-id="3a451-175">[Referência técnica do algoritmo do Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3a451-175">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="3a451-176">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="3a451-176">Data Source Views in Multidimensional Models</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models)  
  
  
