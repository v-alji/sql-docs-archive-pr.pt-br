---
title: 'Lição 5: executando consultas de previsão | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0037bd2f-aa2d-464b-bf86-b0210f0438b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a5f4d6dd79f62541e207df688349f694680e2421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681962"
---
# <a name="lesson-5-executing-prediction-queries"></a><span data-ttu-id="91d77-102">Lição 5: Executando previsão de consultas</span><span class="sxs-lookup"><span data-stu-id="91d77-102">Lesson 5: Executing Prediction Queries</span></span>
  <span data-ttu-id="91d77-103">Nesta lição, você usará o formulário [selecionar de \<model> junção de previsão (DMX)](/sql/dmx/select-from-model-cases-dmx) da instrução SELECT para criar dois tipos diferentes de previsões com base no modelo de árvore de decisão criado na [lição 2: adicionando modelos de mineração à estrutura de mineração de associação](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="91d77-103">In this lesson, you will use the [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement to create two different types of predictions based on the decision tree model you created in [Lesson 2: Adding Mining Models to the Association Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="91d77-104">Esses tipos de prognóstico estão definidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="91d77-104">These prediction types are defined below.</span></span>  
  
 <span data-ttu-id="91d77-105">Consulta singleton</span><span class="sxs-lookup"><span data-stu-id="91d77-105">Singleton Query</span></span>  
 <span data-ttu-id="91d77-106">Use uma consulta singleton para fornecer valores ad hoc ao fazer previsões.</span><span class="sxs-lookup"><span data-stu-id="91d77-106">Use a singleton query to provide ad hoc values when making predictions.</span></span> <span data-ttu-id="91d77-107">Por exemplo, você pode determinar se um único cliente tem probabilidade de ser um comprador de bicicleta, passando entradas à consulta, como a distância para o trabalho, o código de área ou o número de filhos do cliente.</span><span class="sxs-lookup"><span data-stu-id="91d77-107">For example, you can determine whether a single customer is likely to be a bike buyer, by passing inputs to the query such as the commute distance, the area code, or the number of children of the customer.</span></span> <span data-ttu-id="91d77-108">A consulta singleton retorna um valor que indica a probabilidade de a pessoa comprar uma bicicleta com base nessas entradas.</span><span class="sxs-lookup"><span data-stu-id="91d77-108">The singleton query returns a value that indicates how likely the person is to purchase a bicycle based on those inputs.</span></span>  
  
 <span data-ttu-id="91d77-109">Consulta por lotes</span><span class="sxs-lookup"><span data-stu-id="91d77-109">Batch Query</span></span>  
 <span data-ttu-id="91d77-110">Use uma consulta por lotes para determinar que clientes em potencial em uma tabela possam vir a comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="91d77-110">Use a batch query to determine who in a table of potential customers is likely to purchase a bicycle.</span></span> <span data-ttu-id="91d77-111">Por exemplo, se seu departamento de marketing lhe fornecer uma lista de clientes e de atributos de cliente, então você poderá usar um prognóstico por lotes para determinar quais clientes da tabela são prováveis compradores de bicicleta.</span><span class="sxs-lookup"><span data-stu-id="91d77-111">For example, if your marketing department provides you with a list of customers and customer attributes, then you can use a batch prediction to determine who from the table is likely to purchase a bicycle.</span></span>  
  
 <span data-ttu-id="91d77-112">O formulário de [seleção de \<model> junção de previsão (DMX)](/sql/dmx/select-from-model-cases-dmx) da instrução SELECT contém três partes:</span><span class="sxs-lookup"><span data-stu-id="91d77-112">The [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement contains three parts:</span></span>  
  
-   <span data-ttu-id="91d77-113">Uma lista de colunas de modelo de mineração e funções de previsão retornadas nos resultados.</span><span class="sxs-lookup"><span data-stu-id="91d77-113">A list of the mining model columns and prediction functions that are returned in the results.</span></span> <span data-ttu-id="91d77-114">Os resultados também podem conter colunas de entrada dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="91d77-114">The results can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="91d77-115">A consulta de origem que define os dados usados para criar um prognóstico.</span><span class="sxs-lookup"><span data-stu-id="91d77-115">The source query defining the data that is being used to create a prediction.</span></span> <span data-ttu-id="91d77-116">Por exemplo, uma consulta por lotes poderia ser uma lista de clientes.</span><span class="sxs-lookup"><span data-stu-id="91d77-116">For example, in a batch query this could be a list of customers.</span></span>  
  
-   <span data-ttu-id="91d77-117">Um mapeamento entre as colunas de modelo de mineração e os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="91d77-117">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="91d77-118">Se esses nomes coincidirem, então você pode usar a sintaxe NATURAL e não incluir os mapeamentos de coluna.</span><span class="sxs-lookup"><span data-stu-id="91d77-118">If these names match, then you can use NATURAL syntax and leave out the column mappings.</span></span>  
  
 <span data-ttu-id="91d77-119">É possível melhorar a consulta ainda mais, usando as funções de prognóstico.</span><span class="sxs-lookup"><span data-stu-id="91d77-119">You can further enhance the query by using prediction functions.</span></span> <span data-ttu-id="91d77-120">As funções de prognóstico fornecem informações adicionais, como a probabilidade de um prognóstico se confirmar, e dão suporte ao prognóstico no conjunto de dados de treinamento.</span><span class="sxs-lookup"><span data-stu-id="91d77-120">Prediction functions provide additional information, such as the probability of a prediction occurring, and provide support for the prediction in the training dataset.</span></span> <span data-ttu-id="91d77-121">Para obter mais informações sobre funções de previsão, consulte [funções &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="91d77-121">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="91d77-122">Os prognósticos neste tutorial se baseiam na tabela ProspectiveBuyer no banco de dados de exemplo [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91d77-122">The predictions in this tutorial are based on the ProspectiveBuyer table in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database.</span></span> <span data-ttu-id="91d77-123">A tabela ProspectiveBuyer contém uma lista de clientes em potencial e as características associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="91d77-123">The ProspectiveBuyer table contains a list of potential customers and their associated characteristics.</span></span> <span data-ttu-id="91d77-124">Os clientes nesta tabela independem dos clientes usados para criar o modelo de mineração da árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="91d77-124">The customers in this table are independent of the customers that were used to create the decision tree mining model.</span></span>  
  
 <span data-ttu-id="91d77-125">Ainda é possível criar prognósticos usando o construtor de consultas de prognóstico do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91d77-125">You can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="91d77-126">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="91d77-126">Lesson Tasks</span></span>  
 <span data-ttu-id="91d77-127">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="91d77-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="91d77-128">Crie uma consulta singleton para determinar a probabilidade de um determinado cliente vir a comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="91d77-128">Create a singleton query to determine whether a specific customer is likely to purchase a bicycle.</span></span>  
  
-   <span data-ttu-id="91d77-129">Crie uma consulta em lotes para determinar quais clientes, listados em uma tabela de clientes, têm probabilidade de comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="91d77-129">Create a batch query to determine which customers, listed in a table of customers, are likely to purchase a bicycle.</span></span>  
  
## <a name="singleton-query"></a><span data-ttu-id="91d77-130">Consulta singleton</span><span class="sxs-lookup"><span data-stu-id="91d77-130">Singleton Query</span></span>  
 <span data-ttu-id="91d77-131">A primeira etapa é usar o [modelo selecionar de &#60;&#62; junção de previsão &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) em uma consulta de Previsão Singleton.</span><span class="sxs-lookup"><span data-stu-id="91d77-131">The first step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a singleton prediction query.</span></span> <span data-ttu-id="91d77-132">Segue um exemplo genérico da instrução singleton:</span><span class="sxs-lookup"><span data-stu-id="91d77-132">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
```  
  
 <span data-ttu-id="91d77-133">A primeira linha do código define as colunas do modelo de mineração que a consulta deve retornar e especifica o nome do modelo de mineração usado para gerar a previsão:</span><span class="sxs-lookup"><span data-stu-id="91d77-133">The first line of the code defines the columns from the mining model that the query should return, and specifies the mining model that is used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
```  
  
 <span data-ttu-id="91d77-134">Nas linhas seguintes do código são definidas as características do cliente usadas para criar um prognóstico:</span><span class="sxs-lookup"><span data-stu-id="91d77-134">The next lines of the code define the characteristics of the customer that you use to create a prediction:</span></span>  
  
```  
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="91d77-135">Se você especificar NATURAL PREDICTION JOIN, o servidor faz a correspondência entre cada coluna do modelo com uma coluna dos dados de entrada, com base em nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="91d77-135">If you specify NATURAL PREDICTION JOIN, the server matches each column from the model to a column from the input, based on column names.</span></span> <span data-ttu-id="91d77-136">Se os nomes da coluna não coincidirem, as colunas serão ignoradas.</span><span class="sxs-lookup"><span data-stu-id="91d77-136">If column names do not match, the columns are ignored.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query"></a><span data-ttu-id="91d77-137">Para criar uma consulta de prognóstico singleton</span><span class="sxs-lookup"><span data-stu-id="91d77-137">To create a singleton prediction query</span></span>  
  
1.  <span data-ttu-id="91d77-138">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="91d77-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="91d77-139">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="91d77-139">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="91d77-140">Copie o exemplo genérico da instrução singleton, no campo em branco da consulta.</span><span class="sxs-lookup"><span data-stu-id="91d77-140">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="91d77-141">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="91d77-141">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="91d77-142">por:</span><span class="sxs-lookup"><span data-stu-id="91d77-142">with:</span></span>  
  
    ```  
    [Bike Buyer] AS Buyer, PredictHistogram([Bike Buyer]) AS Statistics  
    ```  
  
     <span data-ttu-id="91d77-143">A instrução AS é usada para designar um alias para as colunas que retornaram na consulta.</span><span class="sxs-lookup"><span data-stu-id="91d77-143">The AS statement is used to alias columns returned by the query.</span></span> <span data-ttu-id="91d77-144">A função [PredictHistogram](/sql/dmx/predicthistogram-dmx) retorna estatísticas sobre a previsão, incluindo a probabilidade e o suporte.</span><span class="sxs-lookup"><span data-stu-id="91d77-144">The [PredictHistogram](/sql/dmx/predicthistogram-dmx) function returns statistics about the prediction, including the probability and the support.</span></span> <span data-ttu-id="91d77-145">Para obter mais informações sobre as funções que podem ser usadas em uma instrução de previsão, consulte [funções &#40;&#41;DMX ](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="91d77-145">For more information about the functions that can be used in a prediction statement, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
4.  <span data-ttu-id="91d77-146">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="91d77-146">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="91d77-147">por:</span><span class="sxs-lookup"><span data-stu-id="91d77-147">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="91d77-148">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="91d77-148">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column name>], ...)  AS t  
    ```  
  
     <span data-ttu-id="91d77-149">por:</span><span class="sxs-lookup"><span data-stu-id="91d77-149">with:</span></span>  
  
    ```  
    (SELECT 35 AS [Age],  
      '5-10 Miles' AS [Commute Distance],  
      '1' AS [House Owner Flag],  
      2 AS [Number Cars Owned],  
      2 AS [Total Children]) AS t  
    ```  
  
     <span data-ttu-id="91d77-150">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="91d77-150">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
       [Bike Buyer] AS Buyer,  
       PredictHistogram([Bike Buyer]) AS Statistics  
    FROM  
       [Decision Tree]  
    NATURAL PREDICTION JOIN  
    (SELECT 35 AS [Age],  
       '5-10 Miles' AS [Commute Distance],  
       '1' AS [House Owner Flag],  
       2 AS [Number Cars Owned],  
       2 AS [Total Children]) AS t  
    ```  
  
6.  <span data-ttu-id="91d77-151">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="91d77-151">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="91d77-152">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Singleton_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="91d77-152">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_Query.dmx`.</span></span>  
  
8.  <span data-ttu-id="91d77-153">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="91d77-153">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="91d77-154">A consulta retorna um prognóstico sobre a possibilidade de um cliente, com as características especificadas, comprar uma bicicleta, além de as estatísticas sobre tal prognóstico.</span><span class="sxs-lookup"><span data-stu-id="91d77-154">The query returns a prediction about whether a customer with the specified characteristics will purchase a bicycle, as well as statistics about that prediction.</span></span>  
  
## <a name="batch-query"></a><span data-ttu-id="91d77-155">Consulta por lotes</span><span class="sxs-lookup"><span data-stu-id="91d77-155">Batch Query</span></span>  
 <span data-ttu-id="91d77-156">A próxima etapa é usar o [modelo selecionar de &#60;&#62; junção de previsão &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) em uma consulta de previsão de lote.</span><span class="sxs-lookup"><span data-stu-id="91d77-156">The next step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a batch prediction query.</span></span> <span data-ttu-id="91d77-157">Segue um exemplo genérico de uma instrução por lotes:</span><span class="sxs-lookup"><span data-stu-id="91d77-157">The following is a generic example of a batch statement:</span></span>  
  
```  
SELECT TOP <number> <select list>   
FROM [<mining model name>]  
PREDICTION JOIN  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
ON <on clause, mapping,>  
WHERE <where clause, boolean expression,>  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="91d77-158">Assim como na consulta singleton, as primeiras duas linhas do código definem as colunas do modelo de mineração que a consulta retorna, assim como o nome do modelo de mineração usado para gerar o prognóstico:</span><span class="sxs-lookup"><span data-stu-id="91d77-158">As in the singleton query, the first two lines of the code define the columns from mining model that the query returns, as well as the name of the mining model that is used to generate the prediction.</span></span> <span data-ttu-id="91d77-159">A \<number> instrução Top especifica que a consulta retornará apenas o número ou os resultados especificados por \<number> .</span><span class="sxs-lookup"><span data-stu-id="91d77-159">The TOP \<number> statement specifies that the query will only return the number or the results specified by \<number>.</span></span>  
  
 <span data-ttu-id="91d77-160">As próximas linhas do código definem os dados de origem nos quais os prognóstico se baseiam:</span><span class="sxs-lookup"><span data-stu-id="91d77-160">The next lines of the code define the source data that the predictions are based on:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
```  
  
 <span data-ttu-id="91d77-161">Você dispõe de várias opções de métodos para recuperar os dados de origem; mas, neste tutorial, usará o OPENQUERY.</span><span class="sxs-lookup"><span data-stu-id="91d77-161">You have several options for the method of retrieving the source data, but in this tutorial, you will use OPENQUERY.</span></span> <span data-ttu-id="91d77-162">Para obter mais informações sobre as opções disponíveis, consulte [&#60;&#62;de consulta de dados de origem ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="91d77-162">For more information about the options available, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
 <span data-ttu-id="91d77-163">A linha seguinte define o mapeamento entre as colunas de origem do modelo de mineração e as colunas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="91d77-163">The next line defines the mapping between the source columns in the mining model and the columns in the source data:</span></span>  
  
```  
ON <column mappings>  
```  
  
 <span data-ttu-id="91d77-164">A cláusula WHERE filtra os resultados retornados pela consulta de prognóstico:</span><span class="sxs-lookup"><span data-stu-id="91d77-164">The WHERE clause filters the results returned by the prediction query:</span></span>  
  
```  
WHERE <where clause, boolean expression,>  
```  
  
 <span data-ttu-id="91d77-165">A última e opcional linha do código especifica a coluna segundo a qual os resultados serão ordenados:</span><span class="sxs-lookup"><span data-stu-id="91d77-165">The last and optional line of the code specifies the column that the results will be ordered by:</span></span>  
  
```  
ORDER BY <expression> [DESC|ASC]  
```  
  
 <span data-ttu-id="91d77-166">Use ORDER BY em combinação com a \<number> instrução top para filtrar os resultados retornados.</span><span class="sxs-lookup"><span data-stu-id="91d77-166">Use ORDER BY in combination with the TOP \<number> statement, to filter the results that are returned.</span></span> <span data-ttu-id="91d77-167">Por exemplo, neste prognóstico você devolverá os dez principais compradores de bicicleta, ordenados pela probabilidade de maior acerto.</span><span class="sxs-lookup"><span data-stu-id="91d77-167">For example, in this prediction you will return the top ten bike buyers, ordered by the probability of the prediction being correct.</span></span> <span data-ttu-id="91d77-168">Use a sintaxe [DESC|ASC] para controlar a ordem de exibição dos resultados.</span><span class="sxs-lookup"><span data-stu-id="91d77-168">You can use [DESC|ASC] syntax to control the order in which the results are displayed.</span></span>  
  
#### <a name="to-create-a-batch-prediction-query"></a><span data-ttu-id="91d77-169">Para criar uma consulta de prognóstico por lotes</span><span class="sxs-lookup"><span data-stu-id="91d77-169">To create a batch prediction query</span></span>  
  
1.  <span data-ttu-id="91d77-170">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="91d77-170">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="91d77-171">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="91d77-171">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="91d77-172">Copie o exemplo genérico da instrução por lotes, no campo em branco da consulta.</span><span class="sxs-lookup"><span data-stu-id="91d77-172">Copy the generic example of the batch statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="91d77-173">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="91d77-173">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="91d77-174">por:</span><span class="sxs-lookup"><span data-stu-id="91d77-174">with:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    ```  
  
     <span data-ttu-id="91d77-175">A cláusula TOP 10 especifica que apenas os dez primeiros resultados serão retornados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="91d77-175">The TOP 10 clause specifies that only the top ten results will be returned by the query.</span></span> <span data-ttu-id="91d77-176">Nesta consulta, a instrução ORDER BY ordena os resultados segundo a maior probabilidade de acerto do prognóstico, de forma que apenas os dez resultados mais prováveis retornem.</span><span class="sxs-lookup"><span data-stu-id="91d77-176">The ORDER BY statement in this query orders the results by the probability of the prediction being correct, so only the ten most likely results will be returned.</span></span>  
  
4.  <span data-ttu-id="91d77-177">Substitua o seguinte espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="91d77-177">Replace the following placeholder:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="91d77-178">Pelo nome do modelo:</span><span class="sxs-lookup"><span data-stu-id="91d77-178">With the name of the model:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="91d77-179">Substitua a seguinte instrução OPENQUERY genérica:</span><span class="sxs-lookup"><span data-stu-id="91d77-179">Replace the following generic OPENQUERY statement:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="91d77-180">Por uma instrução que referencia o data warehouse atual do Adventureworks, como:</span><span class="sxs-lookup"><span data-stu-id="91d77-180">With a statement that references the current Adventureworks data warehouse, such as:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2014],  
      'SELECT  
        [LastName],  
        [FirstName],  
        [MaritalStatus],  
        [Gender],  
        [YearlyIncome],  
        [TotalChildren],  
        [NumberChildrenAtHome],  
        [Education],  
        [Occupation],  
        [HouseOwnerFlag],  
        [NumberCarsOwned]  
      FROM  
        [dbo].[ProspectiveBuyer]  
      ') AS t  
    ```  
  
6.  <span data-ttu-id="91d77-181">Substitua a seguinte sintaxe genérica:</span><span class="sxs-lookup"><span data-stu-id="91d77-181">Replace the following generic syntax:</span></span>  
  
    ```  
    <ON clause, mapping,>   
    WHERE <where clause, boolean expression,>  
    ORDER BY <expression>  
    ```  
  
     <span data-ttu-id="91d77-182">Pelos mapeamentos de coluna necessários para este modelo e conjunto de dados de entrada:</span><span class="sxs-lookup"><span data-stu-id="91d77-182">With the column mappings needed for this model and input data set:</span></span>  
  
    ```  
    [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
     <span data-ttu-id="91d77-183">Especifique `DESC` para listar os resultados mais prováveis primeiro.</span><span class="sxs-lookup"><span data-stu-id="91d77-183">Specify `DESC` in order to list the results with the highest probability first.</span></span>  
  
     <span data-ttu-id="91d77-184">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="91d77-184">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    FROM  
      [Decision Tree]  
    PREDICTION JOIN  
      OPENQUERY([Adventure Works DW 2014],  
        'SELECT  
          [LastName],  
          [FirstName],  
          [MaritalStatus],  
          [Gender],  
          [YearlyIncome],  
          [TotalChildren],  
          [NumberChildrenAtHome],  
          [Education],  
          [Occupation],  
          [HouseOwnerFlag],  
          [NumberCarsOwned]  
        FROM  
          [dbo].[ProspectiveBuyer]  
        ') AS t  
    ON  
      [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
7.  <span data-ttu-id="91d77-185">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="91d77-185">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="91d77-186">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Batch_Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="91d77-186">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Batch_Prediction.dmx`.</span></span>  
  
9. <span data-ttu-id="91d77-187">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="91d77-187">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="91d77-188">A consulta retorna uma tabela contendo nomes de cliente, um prognóstico sobre a possibilidade de cada cliente comprar uma bicicleta e a probabilidade deste prognóstico.</span><span class="sxs-lookup"><span data-stu-id="91d77-188">The query returns a table containing customer names, a prediction of whether each customer will purchase a bicycle, and the probability of the prediction.</span></span>  
  
 <span data-ttu-id="91d77-189">Este é o último passo no tutorial de Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="91d77-189">This is the last step in the Bike Buyer tutorial.</span></span> <span data-ttu-id="91d77-190">Você tem um conjunto de modelos de mineração que lhe permite explorar as semelhanças entre seus clientes e prever se os clientes em potencial comprarão uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="91d77-190">You now have a set of mining models that you can use to explore similarities between you customers and predict whether potential customers will purchase a bicycle.</span></span>  
  
 <span data-ttu-id="91d77-191">Para saber como usar o DMX em um cenário de cesta de compras, confira [tutorial de carrinho do mercado DMX](../../2014/tutorials/market-basket-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="91d77-191">To learn how to use DMX in a Market Basket scenario, see [Market Basket DMX Tutorial](../../2014/tutorials/market-basket-dmx-tutorial.md).</span></span>  
  
  
