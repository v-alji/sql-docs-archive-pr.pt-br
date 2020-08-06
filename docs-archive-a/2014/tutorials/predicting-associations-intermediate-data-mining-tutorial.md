---
title: Prevendo associações (tutorial de mineração de dados intermediários) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9140c5f2-b340-45a6-9c27-d870d15aafea
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: bee5ca4ded1b2fd5cbda0712cb766c825b9d0318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568960"
---
# <a name="predicting-associations-intermediate-data-mining-tutorial"></a><span data-ttu-id="684b0-102">Prevendo associações (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="684b0-102">Predicting Associations (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="684b0-103">Depois que os modelos forem processados, você pode usar as informações sobre associações armazenadas no modelo para criar previsões.</span><span class="sxs-lookup"><span data-stu-id="684b0-103">After the models have been processed, you can use the information about associations stored in the model to create predictions.</span></span> <span data-ttu-id="684b0-104">Na tarefa final desta lição, você aprenderá a criar consultas de previsão em modelos de associação criados por você.</span><span class="sxs-lookup"><span data-stu-id="684b0-104">In the final task of this lesson, you learn how to build prediction queries against the association models that you created.</span></span> <span data-ttu-id="684b0-105">Esta lição supõe que você já saiba usar o Construtor de Consultas de Previsão e que deseja aprender a criar consultas de previsão em modelos de associação.</span><span class="sxs-lookup"><span data-stu-id="684b0-105">This lesson assumes that you are familiar with how to use the Prediction Query Builder and want to learn how to build prediction queries against association models.</span></span> <span data-ttu-id="684b0-106">Para obter mais informações sobre como usar Construtor de Consultas de previsão, consulte [interfaces de consulta de mineração de dados](../../2014/analysis-services/data-mining/data-mining-query-tools.md).</span><span class="sxs-lookup"><span data-stu-id="684b0-106">For more information how to use Prediction Query Builder, see [Data Mining Query Interfaces](../../2014/analysis-services/data-mining/data-mining-query-tools.md).</span></span>  
  
## <a name="creating-a-singleton-prediction-query"></a><span data-ttu-id="684b0-107">Criando uma consulta de previsão singleton</span><span class="sxs-lookup"><span data-stu-id="684b0-107">Creating a Singleton Prediction Query</span></span>  
 <span data-ttu-id="684b0-108">As consultas de previsão em um modelo de associação podem ser muito úteis:</span><span class="sxs-lookup"><span data-stu-id="684b0-108">Prediction queries on an association model can be very useful:</span></span>  
  
-   <span data-ttu-id="684b0-109">Itens recomendados a um cliente, com base em compras prévias ou relacionadas</span><span class="sxs-lookup"><span data-stu-id="684b0-109">Recommend items to a customer, based on prior or related purchases</span></span>  
  
-   <span data-ttu-id="684b0-110">Localizar eventos relacionados.</span><span class="sxs-lookup"><span data-stu-id="684b0-110">Find related events.</span></span>  
  
-   <span data-ttu-id="684b0-111">Identificar relações entre ou em conjuntos de transações.</span><span class="sxs-lookup"><span data-stu-id="684b0-111">Identify relationships in or across sets of transactions.</span></span>  
  
 <span data-ttu-id="684b0-112">Para criar uma consulta de previsão, primeiro selecione o modelo de associação que deseja usar e especifique os dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="684b0-112">To build a prediction query, you first select the association model you want to use, and then you specify the input data.</span></span> <span data-ttu-id="684b0-113">As entradas podem vir de uma fonte de dados externa, como uma lista de valores, ou você pode criar uma consulta singleton e fornecer valores à medida que avança.</span><span class="sxs-lookup"><span data-stu-id="684b0-113">Inputs can come from an external data source, such as a list of values, or you can build a singleton query and provide values as you go.</span></span>  
  
 <span data-ttu-id="684b0-114">Para este cenário, primeiro você criará algumas consultas de previsão singleton, para ter uma ideia de como funciona a previsão.</span><span class="sxs-lookup"><span data-stu-id="684b0-114">For this scenario, you will first create some singleton prediction queries, to get an idea of how prediction works.</span></span> <span data-ttu-id="684b0-115">Em seguida, você criará uma consulta para previsões em lote que poderá ser usada para fazer recomendações baseadas em compras atuais de um cliente.</span><span class="sxs-lookup"><span data-stu-id="684b0-115">Then you will create a query for batch predictions that you could use for making recommendations based on a customer's current purchases.</span></span>  
  
#### <a name="to-create-a-prediction-query-on-an-association-model"></a><span data-ttu-id="684b0-116">Para criar uma consulta de previsão em um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="684b0-116">To create a prediction query on an association model</span></span>  
  
1.  <span data-ttu-id="684b0-117">Clique na guia **previsão do modelo de mineração** do designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="684b0-117">Click the **Mining Model Prediction** tab of Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="684b0-118">No painel **modelo de mineração** , clique em **selecionar modelo**.</span><span class="sxs-lookup"><span data-stu-id="684b0-118">In the **Mining Model** pane, click **Select Model**.</span></span> <span data-ttu-id="684b0-119">(ignore esta etapa e a próxima se o modelo correto já estiver selecionado).</span><span class="sxs-lookup"><span data-stu-id="684b0-119">(You can skip this step and the next step if the correct model is already selected.)</span></span>  
  
3.  <span data-ttu-id="684b0-120">Na caixa de diálogo **selecionar modelo de mineração** , expanda o nó que representa a **Associação**da estrutura de mineração e selecione a **Associação**de modelo.</span><span class="sxs-lookup"><span data-stu-id="684b0-120">In the **Select Mining Model** dialog box, expand the node that represents the mining structure **Association**, and select the model **Association**.</span></span> <span data-ttu-id="684b0-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="684b0-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="684b0-122">Por ora, ignore o painel de entrada.</span><span class="sxs-lookup"><span data-stu-id="684b0-122">For now, you can ignore the input pane.</span></span>  
  
4.  <span data-ttu-id="684b0-123">Na grade, clique na célula vazia em **origem** e selecione **função de previsão.**</span><span class="sxs-lookup"><span data-stu-id="684b0-123">In the grid, click the empty cell under **Source** and select **Prediction Function.**</span></span> <span data-ttu-id="684b0-124">Na célula em **campo**, selecione `PredictAssociation` .</span><span class="sxs-lookup"><span data-stu-id="684b0-124">In the cell under **Field**, select `PredictAssociation`.</span></span>  
  
     <span data-ttu-id="684b0-125">Você também pode usar a função **Predict** para prever associações.</span><span class="sxs-lookup"><span data-stu-id="684b0-125">You can also use the **Predict** function to predict associations.</span></span> <span data-ttu-id="684b0-126">Se você fizer isso, certifique-se de escolher a versão da função **Predict** que usa uma coluna de tabela como argumento.</span><span class="sxs-lookup"><span data-stu-id="684b0-126">If you do, be sure to choose the version of the **Predict** function that takes a table column as argument.</span></span>  
  
5.  <span data-ttu-id="684b0-127">No painel **modelo de mineração** , selecione a tabela aninhada `vAssocSeqLineItems` e arraste-a para a grade, para a caixa **critérios/argumento** da `PredictAssociation` função.</span><span class="sxs-lookup"><span data-stu-id="684b0-127">In the **Mining Model** pane, select the nested table `vAssocSeqLineItems`, and drag it into the grid, to the **Criteria/Argument** box for the `PredictAssociation` function.</span></span>  
  
     <span data-ttu-id="684b0-128">Arrastar e soltar nomes de tabela e de coluna permite que você crie instruções complexas sem erros de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="684b0-128">Dragging and dropping table and column names lets you build complex statements without syntax errors.</span></span> <span data-ttu-id="684b0-129">No entanto, ele substitui o conteúdo atual da célula, que inclui outros argumentos opcionais para a `PredictAssociation` função.</span><span class="sxs-lookup"><span data-stu-id="684b0-129">However, it replaces the current contents of the cell, which include other optional arguments for the `PredictAssociation` function.</span></span> <span data-ttu-id="684b0-130">Para exibir os outros argumentos, você pode adicionar temporariamente uma segunda instância da função à grade para referência.</span><span class="sxs-lookup"><span data-stu-id="684b0-130">To view the other arguments, you can temporarily add a second instance of the function to the grid for reference.</span></span>  
  
6.  <span data-ttu-id="684b0-131">Clique na caixa **critérios/argumento** e digite o seguinte texto após o nome da tabela:`,3`</span><span class="sxs-lookup"><span data-stu-id="684b0-131">Click the **Criteria/Argument** box and type the following text after the table name: `,3`</span></span>  
  
     <span data-ttu-id="684b0-132">O texto completo na caixa **critérios/argumento** deve ser o seguinte:</span><span class="sxs-lookup"><span data-stu-id="684b0-132">The complete text in the **Criteria/Argument** box should be as follows:</span></span>  
  
     `[Association].[v Assoc Seq Line Items],3`  
  
7.  <span data-ttu-id="684b0-133">Clique no botão **resultados** no canto superior do construtor de consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="684b0-133">Click the **Results** button in the upper corner of the Prediction Query Builder.</span></span>  
  
 <span data-ttu-id="684b0-134">Os resultados esperados contêm uma única coluna com a **expressão**de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="684b0-134">The expected results contain a single column with the heading **Expression**.</span></span> <span data-ttu-id="684b0-135">A coluna **expressão** contém uma tabela aninhada com uma única coluna e as três linhas a seguir.</span><span class="sxs-lookup"><span data-stu-id="684b0-135">The **Expression** column contains a nested table with a single column and the following three rows.</span></span> <span data-ttu-id="684b0-136">Como você não especificou um valor de entrada, estas previsões representam as associações de produto mais prováveis para o modelo como um todo.</span><span class="sxs-lookup"><span data-stu-id="684b0-136">Because you did not specify an input value, these predictions represent the most likely product associations for the model as a whole.</span></span>  
  
|<span data-ttu-id="684b0-137">Modelo</span><span class="sxs-lookup"><span data-stu-id="684b0-137">Model</span></span>|  
|-----------|  
|<span data-ttu-id="684b0-138">Women's Mountain Shorts</span><span class="sxs-lookup"><span data-stu-id="684b0-138">Women's Mountain Shorts</span></span>|  
|<span data-ttu-id="684b0-139">Water Bottle</span><span class="sxs-lookup"><span data-stu-id="684b0-139">Water Bottle</span></span>|  
|<span data-ttu-id="684b0-140">Touring-3000</span><span class="sxs-lookup"><span data-stu-id="684b0-140">Touring-3000</span></span>|  
  
 <span data-ttu-id="684b0-141">Em seguida, você usará o painel **entrada de consulta singleton** para especificar um produto como entrada para a consulta e exibir os produtos que provavelmente estão associados a esse item.</span><span class="sxs-lookup"><span data-stu-id="684b0-141">Next, you will use the **Singleton Query Input** pane to specify a product as input to the query, and view the products that are most likely associated with that item.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query-with-nested-table-inputs"></a><span data-ttu-id="684b0-142">Para criar uma consulta de previsão singleton com entradas de tabela aninhada</span><span class="sxs-lookup"><span data-stu-id="684b0-142">To create a singleton prediction query with nested table inputs</span></span>  
  
1.  <span data-ttu-id="684b0-143">Clique no botão **design** no canto do construtor de consultas de previsão para voltar para a grade de construção da consulta.</span><span class="sxs-lookup"><span data-stu-id="684b0-143">Click the **Design** button in the corner of the Prediction Query Builder to switch back to the query building grid.</span></span>  
  
2.  <span data-ttu-id="684b0-144">No menu **modelo de mineração** , selecione **consulta singleton**.</span><span class="sxs-lookup"><span data-stu-id="684b0-144">On the **Mining Model** menu, select **Singleton Query**.</span></span>  
  
3.  <span data-ttu-id="684b0-145">Na caixa de diálogo **modelo de mineração** , selecione o modelo de **Associação** .</span><span class="sxs-lookup"><span data-stu-id="684b0-145">In the **Mining Model** dialog box, select the **Association** model.</span></span>  
  
4.  <span data-ttu-id="684b0-146">Na grade, clique na célula vazia em **origem** e selecione **função de previsão.**</span><span class="sxs-lookup"><span data-stu-id="684b0-146">In the grid, click the empty cell under **Source** and select **Prediction Function.**</span></span> <span data-ttu-id="684b0-147">Na célula em **campo**, selecione `PredictAssociation` .</span><span class="sxs-lookup"><span data-stu-id="684b0-147">In the cell under **Field**, select `PredictAssociation`.</span></span>  
  
5.  <span data-ttu-id="684b0-148">No painel **modelo de mineração** , selecione a tabela aninhada `vAssocSeqLineItems` e arraste-a para a grade, para a caixa **critérios/argumento** da `PredictAssociation` função.</span><span class="sxs-lookup"><span data-stu-id="684b0-148">In the **Mining Model** pane, select the nested table `vAssocSeqLineItems`, and drag it into the grid, to the **Criteria/Argument** box for the `PredictAssociation` function.</span></span> <span data-ttu-id="684b0-149">Digite `,3` após o nome da tabela aninhada, assim como no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="684b0-149">Type `,3` after the nested table name just as in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="684b0-150">Na caixa de diálogo **entrada de consulta singleton** , clique na caixa **valor** ao lado de **itens de linha vAssoc Seq**e clique no botão **(...)** .</span><span class="sxs-lookup"><span data-stu-id="684b0-150">In the **Singleton Query Input** dialog box, click the **Value** box next to **vAssoc Seq Line Items**, and then click the **(...)** button.</span></span>  
  
7.  <span data-ttu-id="684b0-151">Na caixa de diálogo **entrada de tabela aninhada** , selecione `Touring Tire` no painel **coluna de chave** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="684b0-151">In the **Nested Table Input** dialog box, select `Touring Tire` in the **Key column** pane, and then click **Add**.</span></span>  
  
8.  <span data-ttu-id="684b0-152">Clique no botão **resultados** .</span><span class="sxs-lookup"><span data-stu-id="684b0-152">Click the **Results** button.</span></span>  
  
 <span data-ttu-id="684b0-153">Os resultados mostrarão as previsões para produtos que têm mais probabilidade de estarem associados ao Pneu de Passeio.</span><span class="sxs-lookup"><span data-stu-id="684b0-153">The results now show the predictions for products that are most likely associated with the Touring Tire.</span></span>  
  
|<span data-ttu-id="684b0-154">Modelo</span><span class="sxs-lookup"><span data-stu-id="684b0-154">Model</span></span>|  
|-----------|  
|<span data-ttu-id="684b0-155">Tubo de pneu para passeio</span><span class="sxs-lookup"><span data-stu-id="684b0-155">Touring Tire Tube</span></span>|  
|<span data-ttu-id="684b0-156">Sport-100</span><span class="sxs-lookup"><span data-stu-id="684b0-156">Sport-100</span></span>|  
|<span data-ttu-id="684b0-157">Water Bottle</span><span class="sxs-lookup"><span data-stu-id="684b0-157">Water Bottle</span></span>|  
  
 <span data-ttu-id="684b0-158">No entanto, você já sabe, pela exploração do modelo, que o Tubo de Pneu para Passeio é frequentemente comprado com o Pneu de Passeio; você está mais interessado em saber que produtos poderá recomendar aos clientes que compram esses itens juntos.</span><span class="sxs-lookup"><span data-stu-id="684b0-158">However, you already know from exploring the model that the Touring Tire Tube is frequently purchased with the Touring Tire; you are more interested in knowing what products you can recommend to customers who purchase these items together.</span></span> <span data-ttu-id="684b0-159">Altere a consulta para que ela preveja produtos relacionados baseados em dois itens da cesta.</span><span class="sxs-lookup"><span data-stu-id="684b0-159">You will change the query so that it predicts related products based on two items in the basket.</span></span> <span data-ttu-id="684b0-160">Você também modificará a consulta para adicionar a probabilidade de cada produto previsto.</span><span class="sxs-lookup"><span data-stu-id="684b0-160">You will also modify the query to add the probability for each predicted product.</span></span>  
  
#### <a name="to-add-inputs-and-probabilities-to-the-singleton-prediction-query"></a><span data-ttu-id="684b0-161">Para adicionar entradas e probabilidades à consulta de previsão singleton</span><span class="sxs-lookup"><span data-stu-id="684b0-161">To add inputs and probabilities to the singleton prediction query</span></span>  
  
1.  <span data-ttu-id="684b0-162">Clique no botão **design** no canto do construtor de consultas de previsão para voltar para a grade de construção da consulta.</span><span class="sxs-lookup"><span data-stu-id="684b0-162">Click the **Design** button in the corner of the Prediction Query Builder to switch back to the query building grid.</span></span>  
  
2.  <span data-ttu-id="684b0-163">Na caixa de diálogo **entrada de consulta singleton** , clique na caixa **valor** ao lado de **itens de linha vAssoc Seq**e clique no botão **(...)** .</span><span class="sxs-lookup"><span data-stu-id="684b0-163">In the **Singleton Query Input** dialog box, click the **Value** box next to **vAssoc Seq Line Items**, and then click the **(...)** button.</span></span>  
  
3.  <span data-ttu-id="684b0-164">No painel **coluna de chave** , selecione `Touring Tire` e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="684b0-164">In the **Key column** pane, select `Touring Tire`, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="684b0-165">Na grade, clique na célula vazia em **origem** e selecione **função de previsão.**</span><span class="sxs-lookup"><span data-stu-id="684b0-165">In the grid, click the empty cell under **Source** and select **Prediction Function.**</span></span> <span data-ttu-id="684b0-166">Na célula em **campo**, selecione `PredictAssociation` .</span><span class="sxs-lookup"><span data-stu-id="684b0-166">In the cell under **Field**, select `PredictAssociation`.</span></span>  
  
5.  <span data-ttu-id="684b0-167">No painel **modelo de mineração** , selecione a tabela aninhada `vAssocSeqLineItems` e arraste-a para a grade, para a caixa **critérios/argumento** da `PredictAssociation` função.</span><span class="sxs-lookup"><span data-stu-id="684b0-167">In the **Mining Model** pane, select the nested table `vAssocSeqLineItems`, and drag it into the grid, to the **Criteria/Argument** box for the `PredictAssociation` function.</span></span> <span data-ttu-id="684b0-168">Digite `,3` após o nome da tabela aninhada, assim como no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="684b0-168">Type `,3` after the nested table name just as in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="684b0-169">Na caixa de diálogo **entrada de tabela aninhada** , selecione `Touring Tire Tube` no painel **coluna de chave** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="684b0-169">In the **Nested Table Input** dialog box, select `Touring Tire Tube` in the **Key column** pane, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="684b0-170">Na grade, na linha da `PredictAssociation` função, clique na caixa **critérios/argumento** e altere os argumentos para adicionar o argumento, INCLUDE_STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="684b0-170">In the grid, in the row for the `PredictAssociation` function, click the **Criteria/Argument** box, and change the arguments to add the argument, INCLUDE_STATISTICS.</span></span>  
  
     <span data-ttu-id="684b0-171">O texto completo na caixa **critérios/argumento** deve ser o seguinte:</span><span class="sxs-lookup"><span data-stu-id="684b0-171">The complete text in the **Criteria/Argument** box should be as follows:</span></span>  
  
     `[Association].[v Assoc Seq Line Items], INCLUDE_STATISTICS, 3`  
  
8.  <span data-ttu-id="684b0-172">Clique no botão **resultados** .</span><span class="sxs-lookup"><span data-stu-id="684b0-172">Click the **Results** button.</span></span>  
  
 <span data-ttu-id="684b0-173">Os resultados da tabela aninhada foram alterados para mostrar as previsões, além do suporte e da probabilidade.</span><span class="sxs-lookup"><span data-stu-id="684b0-173">The results in the nested table now change to show the predictions, together with support and probability.</span></span> <span data-ttu-id="684b0-174">Para obter mais informações sobre como interpretar esses valores, consulte [conteúdo do modelo de mineração para modelos de associação &#40;&#41;de mineração de dados de Analysis Services ](../../2014/analysis-services/data-mining/mining-model-content-for-association-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="684b0-174">For more information about how to interpret these values, see [Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-association-models-analysis-services-data-mining.md).</span></span>  
  
|<span data-ttu-id="684b0-175">Modelo</span><span class="sxs-lookup"><span data-stu-id="684b0-175">Model</span></span>|<span data-ttu-id="684b0-176">$SUPPORT</span><span class="sxs-lookup"><span data-stu-id="684b0-176">$SUPPORT</span></span>|<span data-ttu-id="684b0-177">$PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="684b0-177">$PROBABILITY</span></span>|<span data-ttu-id="684b0-178">$ADJUSTEDPROBABILITY</span><span class="sxs-lookup"><span data-stu-id="684b0-178">$ADJUSTEDPROBABILITY</span></span>|  
|-----------|--------------|------------------|--------------------------|  
|<span data-ttu-id="684b0-179">Sport-100</span><span class="sxs-lookup"><span data-stu-id="684b0-179">Sport-100</span></span>|<span data-ttu-id="684b0-180">4334</span><span class="sxs-lookup"><span data-stu-id="684b0-180">4334</span></span>|<span data-ttu-id="684b0-181">0,291...</span><span class="sxs-lookup"><span data-stu-id="684b0-181">0.291...</span></span>|<span data-ttu-id="684b0-182">0,252...</span><span class="sxs-lookup"><span data-stu-id="684b0-182">0.252...</span></span>|  
|<span data-ttu-id="684b0-183">Water Bottle</span><span class="sxs-lookup"><span data-stu-id="684b0-183">Water Bottle</span></span>|<span data-ttu-id="684b0-184">2866</span><span class="sxs-lookup"><span data-stu-id="684b0-184">2866</span></span>|<span data-ttu-id="684b0-185">0,192...</span><span class="sxs-lookup"><span data-stu-id="684b0-185">0.192...</span></span>|<span data-ttu-id="684b0-186">0,175...</span><span class="sxs-lookup"><span data-stu-id="684b0-186">0.175...</span></span>|  
|<span data-ttu-id="684b0-187">Patch Kit</span><span class="sxs-lookup"><span data-stu-id="684b0-187">Patch Kit</span></span>|<span data-ttu-id="684b0-188">2113</span><span class="sxs-lookup"><span data-stu-id="684b0-188">2113</span></span>|<span data-ttu-id="684b0-189">0,142...</span><span class="sxs-lookup"><span data-stu-id="684b0-189">0.142...</span></span>|<span data-ttu-id="684b0-190">0,132</span><span class="sxs-lookup"><span data-stu-id="684b0-190">0.132</span></span>|  
  
## <a name="working-with-results"></a><span data-ttu-id="684b0-191">Trabalhando com resultados</span><span class="sxs-lookup"><span data-stu-id="684b0-191">Working with Results</span></span>  
 <span data-ttu-id="684b0-192">Quando houver muitas tabelas aninhadas nos resultados, talvez seja melhor mesclá-los para obter uma exibição melhor.</span><span class="sxs-lookup"><span data-stu-id="684b0-192">When there are many nested tables in the results, you might want to flatten the results for easier viewing.</span></span> <span data-ttu-id="684b0-193">Para isso, modifique a consulta manualmente e adicione a palavra-chave `FLATTENED`.</span><span class="sxs-lookup"><span data-stu-id="684b0-193">To do this, you can manually modify the query and add the `FLATTENED` keyword.</span></span>  
  
#### <a name="to-flatten-nested-rowsets-in-a-prediction-query"></a><span data-ttu-id="684b0-194">Para mesclar conjuntos de linhas aninhadas em uma consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="684b0-194">To flatten nested rowsets in a prediction query</span></span>  
  
1.  <span data-ttu-id="684b0-195">Clique no botão **SQL** no canto da Construtor de consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="684b0-195">Click the **SQL** button in the corner of the Prediction Query Builder.</span></span>  
  
     <span data-ttu-id="684b0-196">A grade se transformará em um painel aberto, onde você poderá exibir e modificar a instrução DMX criada pelo Construtor de Consultas de Previsão.</span><span class="sxs-lookup"><span data-stu-id="684b0-196">The grid changes to an open pane where you can view and modify the DMX statement that was created by the Prediction Query Builder.</span></span>  
  
2.  <span data-ttu-id="684b0-197">Após a palavra-chave `SELECT`, digite `FLATTENED`.</span><span class="sxs-lookup"><span data-stu-id="684b0-197">After the `SELECT` keyword, type `FLATTENED`.</span></span>  
  
     <span data-ttu-id="684b0-198">O texto completo da consulta deve ser o seguinte:</span><span class="sxs-lookup"><span data-stu-id="684b0-198">The complete text of the query should be as follows:</span></span>  
  
    ```  
    SELECT FLATTENED  
      PredictAssociation([Association].[v Assoc Seq Line Items],INCLUDE_STATISTICS,3)  
    FROM  
      [Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Touring Tire' AS [Model]  
      UNION SELECT 'Touring Tire Tube' AS [Model]) AS [v Assoc Seq Line Items]) AS t  
    ```  
  
3.  <span data-ttu-id="684b0-199">Clique no botão **resultados** no canto superior do construtor de consultas de previsão.</span><span class="sxs-lookup"><span data-stu-id="684b0-199">Click the **Results** button in the upper corner of the Prediction Query Builder.</span></span>  
  
 <span data-ttu-id="684b0-200">Observe que, depois de editar manualmente uma consulta, você não conseguirá voltar ao modo Design sem perder as alterações.</span><span class="sxs-lookup"><span data-stu-id="684b0-200">Note that after you have manually edited a query, you will not be able to switch back to Design view without losing the changes.</span></span> <span data-ttu-id="684b0-201">Se quiser salvar a consulta, copie a instrução DMX criada manualmente em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="684b0-201">If you wish to save the query, you can copy the DMX statement that you created manually to a text file.</span></span> <span data-ttu-id="684b0-202">Quando você voltar ao modo Design, a consulta será revertida para a última versão válida desse modo.</span><span class="sxs-lookup"><span data-stu-id="684b0-202">When you change back to Design view, the query is reverted to the last version that was valid in Design view.</span></span>  
  
## <a name="creating-multiple-predictions"></a><span data-ttu-id="684b0-203">Criando várias previsões</span><span class="sxs-lookup"><span data-stu-id="684b0-203">Creating Multiple Predictions</span></span>  
 <span data-ttu-id="684b0-204">Suponha que você queira saber quais são as melhores previsões para clientes individuais com base em compras passadas.</span><span class="sxs-lookup"><span data-stu-id="684b0-204">Suppose you want to know the best predictions for individual customers, based on past purchases.</span></span> <span data-ttu-id="684b0-205">Você pode usar dados externos como entrada para a consulta de previsão, como tabelas com a ID do cliente a as compras de produtos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="684b0-205">You can use external data as input to the prediction query, such as tables containing the customer ID and the most recent product purchases.</span></span> <span data-ttu-id="684b0-206">É necessário que as tabelas de dados já estejam definidas como uma exibição da fonte de dados do Analysis Services; além disso, os dados de entrada devem conter tabelas de caso e aninhadas como as usadas no modelo.</span><span class="sxs-lookup"><span data-stu-id="684b0-206">The requirements are that the data tables be already defined as an Analysis Services data source view; moreover, the input data must contain case and nested tables like those used in the model.</span></span> <span data-ttu-id="684b0-207">Elas não precisam ter os mesmos nomes, mas a estrutura deve ser similar.</span><span class="sxs-lookup"><span data-stu-id="684b0-207">They need not have the same names, but the structure must be similar.</span></span> <span data-ttu-id="684b0-208">Para fins deste tutorial, serão usadas as tabelas originais nas quais o modelo foi treinado.</span><span class="sxs-lookup"><span data-stu-id="684b0-208">For the purpose of this tutorial, you will use the original tables on which the model was trained.</span></span>  
  
#### <a name="to-change-the-input-method-for-the-prediction-query"></a><span data-ttu-id="684b0-209">Para alterar o método de entrada da consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="684b0-209">To change the input method for the prediction query</span></span>  
  
1.  <span data-ttu-id="684b0-210">No menu **modelo de mineração** , selecione **consulta singleton** novamente para desmarcar a marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="684b0-210">In the **Mining Model** menu, select **Singleton Query** again, to clear the check mark.</span></span>  
  
2.  <span data-ttu-id="684b0-211">Será exibida uma mensagem de erro avisando que a sua consulta singleton será perdida.</span><span class="sxs-lookup"><span data-stu-id="684b0-211">An error message appears warning that your singleton query will be lost.</span></span> <span data-ttu-id="684b0-212">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="684b0-212">Click **Yes**.</span></span>  
  
     <span data-ttu-id="684b0-213">O nome da caixa de diálogo de entrada é alterado para **selecionar tabela (s) de entrada**.</span><span class="sxs-lookup"><span data-stu-id="684b0-213">The name of the input dialog box changes to **Select Input Table(s)**.</span></span>  
  
 <span data-ttu-id="684b0-214">Como você está interessado na criação de uma consulta de previsão que ofereça ID do Cliente e uma lista de produtos como entrada, adicione a tabela de clientes como uma tabela de caso e a tabela de compras como a tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="684b0-214">Because you are interested in creating a prediction query that provides Customer ID and a list of products as input, you will add the customer table as the case table, and the purchases table as the nested table.</span></span> <span data-ttu-id="684b0-215">Em seguida, adicione funções de previsão para criar recomendações.</span><span class="sxs-lookup"><span data-stu-id="684b0-215">Then you will add prediction functions to create recommendations.</span></span>  
  
#### <a name="to-create-a-prediction-query-using-nested-table-inputs"></a><span data-ttu-id="684b0-216">Para criar uma consulta de previsão usando entradas de tabela aninhada</span><span class="sxs-lookup"><span data-stu-id="684b0-216">To create a prediction query using nested table inputs</span></span>  
  
1.  <span data-ttu-id="684b0-217">No painel Modelo de Mineração, selecione o modelo Associação Filtrada.</span><span class="sxs-lookup"><span data-stu-id="684b0-217">In the Mining Model pane, select the Association Filtered model.</span></span>  
  
2.  <span data-ttu-id="684b0-218">Na caixa de diálogo **selecionar tabela (s) de entrada** , clique em **selecionar tabela de casos**.</span><span class="sxs-lookup"><span data-stu-id="684b0-218">In the **Select Input Table(s)** dialog box, click **Select Case Table**.</span></span>  
  
3.  <span data-ttu-id="684b0-219">Na caixa de diálogo **selecionar tabela** , para **fonte de dados**, selecione AdventureWorksDW2008.</span><span class="sxs-lookup"><span data-stu-id="684b0-219">In the **Select Table** dialog box, for **Data Source**, select AdventureWorksDW2008.</span></span> <span data-ttu-id="684b0-220">Na lista **nome da tabela/exibição** , selecione vAssocSeqOrders e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="684b0-220">In the **Table/View Name** list, select vAssocSeqOrders, and then click **OK**.</span></span>  
  
     <span data-ttu-id="684b0-221">A tabela vAssocSeqOrders será adicionada ao painel.</span><span class="sxs-lookup"><span data-stu-id="684b0-221">The table vAssocSeqOrders is added to the pane.</span></span>  
  
4.  <span data-ttu-id="684b0-222">Na caixa de diálogo **selecionar tabela (s) de entrada** , clique em **selecionar tabela aninhada**.</span><span class="sxs-lookup"><span data-stu-id="684b0-222">In the **Select Input Table(s)** dialog box, click **Select Nested Table**.</span></span>  
  
5.  <span data-ttu-id="684b0-223">Na caixa de diálogo **selecionar tabela** , para **fonte de dados**, selecione AdventureWorksDW2008.</span><span class="sxs-lookup"><span data-stu-id="684b0-223">In the **Select Table** dialog box, for **Data Source**, select AdventureWorksDW2008.</span></span> <span data-ttu-id="684b0-224">Na lista **nome da tabela/exibição** , selecione vAssocSeqLineItems e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="684b0-224">In the **Table/View name** list, select vAssocSeqLineItems, and then click **OK**.</span></span>  
  
     <span data-ttu-id="684b0-225">A tabela vAssocSeqLineItems será adicionada ao painel.</span><span class="sxs-lookup"><span data-stu-id="684b0-225">The table vAssocSeqLineItems is added to the pane.</span></span>  
  
6.  <span data-ttu-id="684b0-226">Na caixa de diálogo **especificar junção aninhada** , arraste o campo OrderNumber da tabela de casos e solte-o no campo OrderNumber na tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="684b0-226">In the **Specify Nested Join** dialog box, drag the OrderNumber field from the case table and drop it onto the OrderNumber field in the nested table.</span></span>  
  
     <span data-ttu-id="684b0-227">Você também pode clicar em **Adicionar relação** e criar a relação selecionando colunas em uma lista.</span><span class="sxs-lookup"><span data-stu-id="684b0-227">You can also click **Add Relationship** and create the relationship by selecting columns from a list.</span></span>  
  
7.  <span data-ttu-id="684b0-228">Na caixa de diálogo **especificar relação** , verifique se os campos OrderNumber estão mapeados corretamente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="684b0-228">In the **Specify Relationship** dialog box, verify that the OrderNumber fields are mapped correctly, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="684b0-229">Clique em **OK** para fechar a caixa de diálogo **especificar junção aninhada** .</span><span class="sxs-lookup"><span data-stu-id="684b0-229">Click **OK** to close the **Specify Nested Join** dialog box.</span></span>  
  
     <span data-ttu-id="684b0-230">As tabelas de casos e aninhada são atualizadas no painel de design para mostrarem as junções que conectam as colunas de dados externos às colunas do modelo.</span><span class="sxs-lookup"><span data-stu-id="684b0-230">The case and nested tables are updated in the design pane to show the joins connecting the external data columns to the columns in the model.</span></span> <span data-ttu-id="684b0-231">Se as relações estiverem erradas, você poderá clicar com o botão direito do mouse na linha de junção e selecionar **Modificar Conexões** para editar o mapeamento de coluna ou clicar com o botão direito do mouse na linha de junção e selecionar **excluir** para remover completamente a relação.</span><span class="sxs-lookup"><span data-stu-id="684b0-231">If the relationships are wrong, you can right-click the join line and select **Modify Connections** to edit the column mapping, or you can right-click the join line and select **Delete** to remove the relationship completely.</span></span>  
  
9. <span data-ttu-id="684b0-232">Adicione uma nova linha à grade.</span><span class="sxs-lookup"><span data-stu-id="684b0-232">Add a new row to the grid.</span></span> <span data-ttu-id="684b0-233">Para **origem**, selecione **tabela vAssocSeqOrders**.</span><span class="sxs-lookup"><span data-stu-id="684b0-233">For **Source**, select **vAssocSeqOrders table**.</span></span> <span data-ttu-id="684b0-234">Para **campo**, selecione CustomerKey.</span><span class="sxs-lookup"><span data-stu-id="684b0-234">For **Field**, select CustomerKey.</span></span>  
  
10. <span data-ttu-id="684b0-235">Adicione uma nova linha à grade.</span><span class="sxs-lookup"><span data-stu-id="684b0-235">Add a new row to the grid.</span></span> <span data-ttu-id="684b0-236">Para **origem**, selecione **tabela vAssocSeqOrders**.</span><span class="sxs-lookup"><span data-stu-id="684b0-236">For **Source**, select **vAssocSeqOrders table**.</span></span> <span data-ttu-id="684b0-237">Para **campo**, selecione região.</span><span class="sxs-lookup"><span data-stu-id="684b0-237">For **Field**, select Region.</span></span>  
  
11. <span data-ttu-id="684b0-238">Adicione uma nova linha à grade.</span><span class="sxs-lookup"><span data-stu-id="684b0-238">Add a new row to the grid.</span></span> <span data-ttu-id="684b0-239">Para **origem**, selecione **função de previsão**e, para **campo**, selecione `PredictAssociation` .</span><span class="sxs-lookup"><span data-stu-id="684b0-239">For **Source**, select **Prediction Function**, and for **Field**, select `PredictAssociation`.</span></span>  
  
12. <span data-ttu-id="684b0-240">Arraste vAssocSeqLineItems para a caixa **critérios/argumento** da `PredictAssociation` linha.</span><span class="sxs-lookup"><span data-stu-id="684b0-240">Drag vAssocSeqLineItems, into the **Criteria/Argument** box of the `PredictAssociation` row.</span></span> <span data-ttu-id="684b0-241">Clique no final da caixa **critérios/argumento** e digite o seguinte texto:`INCLUDE_STATISTICS,3`</span><span class="sxs-lookup"><span data-stu-id="684b0-241">Click at the end of the **Criteria/Argument** box and then type the following text: `INCLUDE_STATISTICS,3`</span></span>  
  
     <span data-ttu-id="684b0-242">O texto completo na caixa **critérios/argumento** deve ser:`[Association].[v Assoc Seq Line Items], INCLUDE_STATISTICS, 3`</span><span class="sxs-lookup"><span data-stu-id="684b0-242">The complete text in the **Criteria/Argument** box should be: `[Association].[v Assoc Seq Line Items], INCLUDE_STATISTICS, 3`</span></span>  
  
13. <span data-ttu-id="684b0-243">Clique no botão **resultado** para exibir as previsões para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="684b0-243">Click the **Result** button to view the predictions for each customer.</span></span>  
  
 <span data-ttu-id="684b0-244">Você pode tentar criar uma consulta de previsão similar nos vários modelos para ver se a filtragem altera os resultados da previsão.</span><span class="sxs-lookup"><span data-stu-id="684b0-244">You might try creating a similar prediction query on the multiple models, to see whether filtering changes the prediction results.</span></span> <span data-ttu-id="684b0-245">Para obter mais informações sobre como criar previsões e outros tipos de consultas, consulte [exemplos de consulta de modelo de associação](../../2014/analysis-services/data-mining/association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="684b0-245">For more information about creating predictions and other types of queries, see [Association Model Query Examples](../../2014/analysis-services/data-mining/association-model-query-examples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="684b0-246">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="684b0-246">See Also</span></span>  
 <span data-ttu-id="684b0-247">[Conteúdo do modelo de mineração para modelos de associação &#40;mineração de dados Analysis Services&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-association-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="684b0-247">[Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-association-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="684b0-248">[&#41;&#40;DMX PredictAssociation](/sql/dmx/predictassociation-dmx) </span><span class="sxs-lookup"><span data-stu-id="684b0-248">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) </span></span>  
 [<span data-ttu-id="684b0-249">Criar uma consulta de previsão usando o construtor de consultas de previsão</span><span class="sxs-lookup"><span data-stu-id="684b0-249">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
