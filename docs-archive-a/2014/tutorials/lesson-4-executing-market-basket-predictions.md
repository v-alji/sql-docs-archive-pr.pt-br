---
title: 'Lição 4: executando previsões de cesta de mercado | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b3238f1b-ea04-4253-ade2-838a806b62fe
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 3b49fc242eb8b2242269c5af33cc094937bbe0de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572878"
---
# <a name="lesson-4-executing-market-basket-predictions"></a><span data-ttu-id="9c0b5-102">Lição 4: Executando previsões de Market Basket</span><span class="sxs-lookup"><span data-stu-id="9c0b5-102">Lesson 4: Executing Market Basket Predictions</span></span>
  <span data-ttu-id="9c0b5-103">Nesta lição, você usará a instrução DMX `SELECT` para criar previsões com base nos modelos de associação criados na [lição 2: adicionando modelos de mineração à estrutura de mineração da cesta de compras](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="9c0b5-103">In this lesson, you will use the DMX `SELECT` statement to create predictions based on the association models you created in [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="9c0b5-104">Uma consulta de previsão é criada usando a instrução `SELECT` do DMX e adicionando uma cláusula `PREDICTION JOIN`.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-104">A prediction query is created by using the DMX `SELECT` statement and adding a `PREDICTION JOIN` clause.</span></span> <span data-ttu-id="9c0b5-105">Para obter mais informações sobre a sintaxe de uma junção de previsão, consulte [selecionar do modelo de &#60;&#62; junção de previsão &#40;&#41;DMX ](/sql/dmx/select-from-model-cases-dmx).</span><span class="sxs-lookup"><span data-stu-id="9c0b5-105">For more information about the syntax of a prediction join, see [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span></span>  
  
 <span data-ttu-id="9c0b5-106">O formulário de \*\* \<model> junção de previsão de seleção\*\* da `SELECT` instrução contém três partes:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-106">The **SELECT FROM \<model> PREDICTION JOIN** form of the `SELECT` statement contains three parts:</span></span>  
  
-   <span data-ttu-id="9c0b5-107">Uma lista de colunas de modelo de mineração e funções de previsão que são retornadas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-107">A list of the mining model columns and prediction functions that are returned in the result set.</span></span> <span data-ttu-id="9c0b5-108">Essa lista também pode conter colunas de entrada de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-108">This list can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="9c0b5-109">Uma consulta de origem que define os dados que estão sendo usados para criar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-109">A source query that defines the data that is being used to create a prediction.</span></span> <span data-ttu-id="9c0b5-110">Por exemplo, se você estiver criando muitas previsões em um lote, a consulta de origem poderá recuperar uma lista de clientes.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-110">For example, if you are creating many predictions in a batch, the source query could retrieve a list of customers.</span></span>  
  
-   <span data-ttu-id="9c0b5-111">Um mapeamento entre as colunas de modelo de mineração e os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-111">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="9c0b5-112">Se os nomes de colunas corresponderem, será possível usar a sintaxe `NATURAL PREDICTION JOIN` e omitir os mapeamentos de coluna.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-112">If the columns names match, you can use the `NATURAL PREDICTION JOIN` syntax and omit the column mappings.</span></span>  
  
 <span data-ttu-id="9c0b5-113">É possível melhorar a consulta usando as funções de previsão.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-113">You can enhance the query by using prediction functions.</span></span> <span data-ttu-id="9c0b5-114">As funções de previsão fornecem informações adicionais, como a probabilidade de uma previsão, ou suporte à previsão no conjunto de dados de treinamento.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-114">Prediction functions provide additional information, such as the probability of a prediction occurring, or the support for a prediction in the training dataset.</span></span> <span data-ttu-id="9c0b5-115">Para obter mais informações sobre funções de previsão, consulte [funções &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="9c0b5-115">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="9c0b5-116">Também é possível usar o construtor de consultas de previsão no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para criar as consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-116">You can also use the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create prediction queries.</span></span>  
  
## <a name="singleton-prediction-join-statement"></a><span data-ttu-id="9c0b5-117">Instrução singleton PREDICTION JOIN</span><span class="sxs-lookup"><span data-stu-id="9c0b5-117">Singleton PREDICTION JOIN Statement</span></span>  
 <span data-ttu-id="9c0b5-118">A primeira etapa é criar uma consulta singleton, usando a sintaxe **SELECT FROM \<model> preditiva Join** e fornecendo um único conjunto de valores como entrada.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-118">The first step is to create a singleton query, by using the **SELECT FROM \<model> PREDICTION JOIN** syntax and supplying a single set of values as input.</span></span> <span data-ttu-id="9c0b5-119">Segue um exemplo genérico da instrução singleton:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-119">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list>  
    FROM [<mining model>]   
[NATURAL] PREDICTION JOIN  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
AS [<input alias>]  
```  
  
 <span data-ttu-id="9c0b5-120">A primeira linha do código define as colunas do modelo de mineração que a consulta retorna e especifica o nome do modelo de mineração usado para gerar a previsão:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-120">The first line of the code defines the columns from the mining model that the query returns, and specifies the name of the mining model used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>]   
```  
  
 <span data-ttu-id="9c0b5-121">A próxima linha do código indica a operação a ser executada.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-121">The next line of the code indicates the operation to perform.</span></span> <span data-ttu-id="9c0b5-122">Como você especificará os valores de cada coluna e digitará os nomes das colunas exatamente da maneira correspondente ao modelo, a sintaxe `NATURAL PREDICTION JOIN` poderá ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-122">Because you will specify values for each of the columns and type the column names exactly so as to match the model, you can use the `NATURAL PREDICTION JOIN` syntax.</span></span> <span data-ttu-id="9c0b5-123">No entanto, se os nomes de coluna fossem diferentes, você teria de especificar mapeamentos entre as colunas no modelo e as colunas dos dados novos adicionando uma cláusula `ON`.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-123">However, if the column names were different, you would have to specify mappings between the columns in the model and the columns in the new data by adding an `ON` clause.</span></span>  
  
```  
[NATURAL] PREDICTION JOIN  
```  
  
 <span data-ttu-id="9c0b5-124">As próximas linhas do código definem os produtos no carrinho de compras com o objetivo de prever os produtos adicionais que serão adicionados pelo cliente:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-124">The next lines of the code define the products in the shopping cart that will be used to predict additional products that a customer will add:</span></span>  
  
```  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9c0b5-125">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="9c0b5-125">Lesson Tasks</span></span>  
 <span data-ttu-id="9c0b5-126">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-126">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="9c0b5-127">Crie uma consulta que prevê o que os outros itens que um cliente provavelmente comprará, com base nos itens já existentes em seu carrinho de compras.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-127">Create a query that predicts what other items a customer will likely purchase, based on items already existing in their shopping cart.</span></span> <span data-ttu-id="9c0b5-128">Você criará essa consulta usando o modelo de mineração com o *MINIMUM_PROBABILITY*padrão.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-128">You will create this query by using the mining model with the default *MINIMUM_PROBABILITY*.</span></span>  
  
-   <span data-ttu-id="9c0b5-129">Criar uma consulta que prevê quais os outros itens que um cliente provavelmente comprará, com base nos itens já existentes em seu carrinho de compras.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-129">Create a query that predicts what other items a customer will likely purchase based on items already existing in their shopping cart.</span></span> <span data-ttu-id="9c0b5-130">Essa consulta se baseia em um modelo diferente, no qual *MINIMUM_PROBABILITY* foi definido como 0, 1.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-130">This query is based on a different model, in which *MINIMUM_PROBABILITY* has been set to 0.01.</span></span> <span data-ttu-id="9c0b5-131">Como o valor padrão para *MINIMUM_PROBABILITY* em modelos de associação é 0,3, a consulta nesse modelo deve retornar mais itens possíveis do que a consulta no modelo padrão.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-131">Because the default value for *MINIMUM_PROBABILITY* in association models is 0.3, the query on this model should return more possible items than the query on the default model.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-the-default-minimum_probability"></a><span data-ttu-id="9c0b5-132">Criar uma previsão usando um modelo com o padrão MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="9c0b5-132">Create a Prediction by Using a Model with the Default MINIMUM_PROBABILITY</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="9c0b5-133">Para criar uma consulta de associação</span><span class="sxs-lookup"><span data-stu-id="9c0b5-133">To create an association query</span></span>  
  
1.  <span data-ttu-id="9c0b5-134">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX** para abrir o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-134">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="9c0b5-135">Copie o exemplo genérico da instrução `PREDICTION JOIN` na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-135">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="9c0b5-136">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-136">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="9c0b5-137">por:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-137">with:</span></span>  
  
    ```  
    PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
     <span data-ttu-id="9c0b5-138">Você pode apenas incluir o nome da coluna [Products], mas usando a função [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) , você pode limitar o número de produtos retornados pelo algoritmo a três.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-138">You could just include the column name [Products], but by using the [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) function, you can limit the number of products that are returned by the algorithm to three.</span></span> <span data-ttu-id="9c0b5-139">Também poderá usar `INCLUDE_STATISTICS` que retorna o suporte e a probabilidade, além de permitir ajustar a probabilidade para cada produto.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-139">You can also use `INCLUDE_STATISTICS`, which returns the support, probability, and adjusted probability for each product.</span></span> <span data-ttu-id="9c0b5-140">Essas estatísticas ajudam a definir a taxa de exatidão da previsão.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-140">These statistics help you rate the accuracy of the prediction.</span></span>  
  
4.  <span data-ttu-id="9c0b5-141">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="9c0b5-142">por:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-142">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="9c0b5-143">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-143">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="9c0b5-144">por:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-144">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="9c0b5-145">Essa instrução usa a instrução `UNION` para especificar três produtos que devem ser incluídos no carrinho de compras junto com os produtos previstos.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-145">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="9c0b5-146">A coluna Model na instrução `SELECT` corresponde à coluna de modelo contida na tabela de produtos aninhados.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-146">The Model column in the `SELECT` statement corresponds to the model column that is contained in the nested products table.</span></span>  
  
     <span data-ttu-id="9c0b5-147">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-147">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Default Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="9c0b5-148">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-148">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="9c0b5-149">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="9c0b5-149">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="9c0b5-150">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="9c0b5-150">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="9c0b5-151">A consulta retorna uma tabela que contém três produtos: HL Mountain Tire, Fender Set - Mountain e ML Mountain Tire.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-151">The query returns a table that contains three products: HL Mountain Tire, Fender Set - Mountain, and ML Mountain Tire.</span></span> <span data-ttu-id="9c0b5-152">A tabela lista esses produtos retornados em ordem de probabilidade.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-152">The table lists these returned products in order of probability.</span></span> <span data-ttu-id="9c0b5-153">O produto retornado que provavelmente será incluído no mesmo carrinho de compras juntamente com os três produtos especificados na consulta aparece no topo da tabela.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-153">The returned product that is most likely to be included in the same shopping cart as the three products specified in the query appears at the top of the table.</span></span> <span data-ttu-id="9c0b5-154">Os dois produtos que seguem são provavelmente o próximo item que será incluído no carrinho de compra.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-154">The two products that follow are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="9c0b5-155">A tabela também contém estatísticas que descrevem a exatidão da previsão.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-155">The table also contains statistics describing the accuracy of the prediction.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-a-minimum_probability-of-001"></a><span data-ttu-id="9c0b5-156">Criar uma previsão usando um modelo com uma MINIMUM_PROBABILITY de 0,01</span><span class="sxs-lookup"><span data-stu-id="9c0b5-156">Create a Prediction by Using a Model with a MINIMUM_PROBABILITY of 0.01</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="9c0b5-157">Para criar uma consulta de associação</span><span class="sxs-lookup"><span data-stu-id="9c0b5-157">To create an association query</span></span>  
  
1.  <span data-ttu-id="9c0b5-158">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX** para abrir o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-158">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="9c0b5-159">Copie o exemplo genérico da instrução `PREDICTION JOIN` na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-159">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="9c0b5-160">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-160">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="9c0b5-161">por:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-161">with:</span></span>  
  
    ```  
    PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
4.  <span data-ttu-id="9c0b5-162">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-162">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="9c0b5-163">por:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-163">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="9c0b5-164">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-164">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="9c0b5-165">por:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-165">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="9c0b5-166">Essa instrução usa a instrução `UNION` para especificar três produtos que devem ser incluídos no carrinho de compras junto com os produtos previstos.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-166">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="9c0b5-167">A coluna `[Model]` na instrução `SELECT` corresponde à coluna na tabela de produtos aninhados.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-167">The `[Model]` column in the `SELECT` statement corresponds to the column in the nested products table.</span></span>  
  
     <span data-ttu-id="9c0b5-168">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="9c0b5-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Modified Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="9c0b5-169">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="9c0b5-170">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Modified Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="9c0b5-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="9c0b5-171">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="9c0b5-171">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="9c0b5-172">A consulta retorna uma tabela que contém três produtos: tubo de pneu para mountain bike, garrafa de água e kit para montanhismo.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-172">The query returns a table that contains three products: HL Mountain Tire, Water Bottle, and Fender Set - Mountain.</span></span> <span data-ttu-id="9c0b5-173">A tabela lista esses produtos em ordem de probabilidade.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-173">The table lists these products in order of probability.</span></span> <span data-ttu-id="9c0b5-174">O produto que aparece no topo da tabela é o produto que provavelmente será incluído no mesmo carrinho de compras juntamente com os três produtos especificados na consulta.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-174">The product that appears at the top of the table is the product that is most likely to be included in the same shopping cart as the three products specified in the query.</span></span> <span data-ttu-id="9c0b5-175">Os produtos restantes são provavelmente os próximos que serão incluídos no carrinho de compras.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-175">The remaining products are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="9c0b5-176">A tabela também contém estatísticas que descrevem a precisão da previsão.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-176">The table also contains statistics that describe the accuracy of the prediction.</span></span>  
  
     <span data-ttu-id="9c0b5-177">Você pode ver nos resultados dessa consulta que o valor do parâmetro *MINIMUM_PROBABILITY* afeta os resultados retornados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-177">You can see from the results of this query that the value of the *MINIMUM_PROBABILITY* parameter affects the results returned by the query.</span></span>  
  
 <span data-ttu-id="9c0b5-178">Esta é a última etapa no tutorial da cesta básica.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-178">This is the last step in the Market Basket tutorial.</span></span> <span data-ttu-id="9c0b5-179">Agora você tem um conjunto de modelos que pode ser usado para prever os produtos que os clientes podem comprar ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9c0b5-179">You now have a set of models that you can use to predict the products that customers might purchase at the same time.</span></span>  
  
 <span data-ttu-id="9c0b5-180">Para saber como usar o DMX em outro cenário de previsão, confira [tutorial de compra do DMX para bicicletas](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9c0b5-180">To learn how to use DMX in another predictive scenario, see [Bike Buyer DMX Tutorial](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c0b5-181">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c0b5-181">See Also</span></span>  
 <span data-ttu-id="9c0b5-182">[Exemplos de consulta de modelo de associação](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="9c0b5-182">[Association Model Query Examples](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span></span>  
 [<span data-ttu-id="9c0b5-183">Interfaces de Consulta de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="9c0b5-183">Data Mining Query Interfaces</span></span>](../../2014/analysis-services/data-mining/data-mining-query-tools.md)  
  
  
