---
title: Aplicar funções de previsão a um modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Model Prediction [Analysis Services], selecting mining models
ms.assetid: cf9a97e2-c249-441b-af12-c977c1a91c44
author: minewiskan
ms.author: owend
ms.openlocfilehash: fde9de00adaa1712a9db6e18aabc6a83dd660efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569734"
---
# <a name="apply-prediction-functions-to-a-model"></a><span data-ttu-id="bdd8e-102">Aplicar funções de previsão a um modelo</span><span class="sxs-lookup"><span data-stu-id="bdd8e-102">Apply Prediction Functions to a Model</span></span>
  <span data-ttu-id="bdd8e-103">Para criar uma consulta de previsão, você primeiro deve selecionar o modelo de mineração no qual a consulta será baseada.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-103">To create a prediction query, you must first select the mining model on which the query will be based.</span></span> <span data-ttu-id="bdd8e-104">Você pode selecionar qualquer modelo de mineração existente no projeto atual.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-104">You can select any mining model that exists in the current project.</span></span>  
  
 <span data-ttu-id="bdd8e-105">Depois de selecionar um modelo, adicione uma *função de previsão* à consulta.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-105">After you have selected a model, add a *prediction function* to the query.</span></span> <span data-ttu-id="bdd8e-106">Ele é importado para entender que as funções de previsão são usadas para muitos propósitos: Sim, você pode prever valores, mas também pode obter estatísticas relacionadas, bem como informações que foram usadas para gerar a previsão.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-106">It is import to understand that prediction functions are used for many purposes-yes, you can predict values, but you can also get related statistics, as well as information that was used in generating the prediction.</span></span> <span data-ttu-id="bdd8e-107">As funções de previsão podem retornar os seguintes tipos de valores:</span><span class="sxs-lookup"><span data-stu-id="bdd8e-107">Prediction functions can return the following types of values:</span></span>  
  
-   <span data-ttu-id="bdd8e-108">O nome do atributo previsível e o valor previsto.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-108">The name of the predictable attribute, and the value that is predicted.</span></span>  
  
-   <span data-ttu-id="bdd8e-109">As estatísticas sobre a distribuição e a variância dos valores previstos.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-109">Statistics about the distribution and variance of the predicted values.</span></span>  
  
-   <span data-ttu-id="bdd8e-110">A probabilidade de um resultado especificado, ou de todos os possíveis resultados.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-110">The probability of a specified outcome, or of all possible outcomes.</span></span>  
  
-   <span data-ttu-id="bdd8e-111">As pontuações ou valores superiores ou inferiores.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-111">The top or bottom scores or values.</span></span>  
  
-   <span data-ttu-id="bdd8e-112">Os valores associados a um nó, objeto ou atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-112">Values associated with a specified node, object, or attribute.</span></span>  
  
 <span data-ttu-id="bdd8e-113">Há uma ampla variedade de funções de previsão que podem ser usadas, mas você deve escolher a função que se adapta ao tipo de modelo criado.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-113">There is a wide variety of prediction functions that you can use, but you must choose the function that suits the type of model you created.</span></span> <span data-ttu-id="bdd8e-114">Geralmente esta escolha depende do algoritmo utilizado para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-114">Usually this choice depends on the algorithm used to create the model.</span></span>  
  
-   <span data-ttu-id="bdd8e-115">Para obter uma lista das funções de previsão com suporte em quase todos os tipos de modelo, consulte [Funções de previsão geral &#40;DMX&#41;](/sql/dmx/general-prediction-functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="bdd8e-115">For a list of the prediction functions that are supported for almost all model types, see [General Prediction Functions &#40;DMX&#41;](/sql/dmx/general-prediction-functions-dmx).</span></span>  
  
-   <span data-ttu-id="bdd8e-116">Além disso, os algoritmos individuais dão suporte a uma variedade de funções especializadas.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-116">Additionally, individual algorithms support a variety of specialized functions.</span></span> <span data-ttu-id="bdd8e-117">Por exemplo, se você criar um modelo de mineração baseado no algoritmo de clustering da Microsoft, poderá usar funções de previsão especializadas para localizar informações sobre os clusters, como a distância de um valor de dados para o centroide do cluster.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-117">For example, if you create a mining model based on the Microsoft Clustering algorithm, you can use specialized prediction functions to find information about the clusters, such as the distance from a data value to the cluster centroid.</span></span>  
  
     <span data-ttu-id="bdd8e-118">Para obter exemplos de como consultar um tipo específico de modelo de mineração, consulte o tópico de referência do algoritmo, em [Algoritmos de Data Mining &#40;Analysis Services – Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="bdd8e-118">For examples of how to query a specific type of mining model, see the algorithm reference topic, in [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="choose-a-mining-model-to-use-for-prediction"></a><span data-ttu-id="bdd8e-119">Escolha um modelo de mineração para usar para previsão</span><span class="sxs-lookup"><span data-stu-id="bdd8e-119">Choose a mining model to use for prediction</span></span>  
  
1.  <span data-ttu-id="bdd8e-120">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse no modelo e selecione **Criar Consulta de Previsão**.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-120">From [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the model, and select **Build Prediction Query**.</span></span>  
  
     <span data-ttu-id="bdd8e-121">--OU --</span><span class="sxs-lookup"><span data-stu-id="bdd8e-121">--OR --</span></span>  
  
     <span data-ttu-id="bdd8e-122">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique na guia **Previsão de Modelo de Mineração**e clique em **Selecionar Modelo** na tabela  **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="bdd8e-122">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the tab, **Mining Model Prediction**, and then click **Select Model** in the  **Mining Model** table.</span></span>  
  
2.  <span data-ttu-id="bdd8e-123">Na caixa de diálogo **Selecionar o Modelo de Mineração** , selecione um modelo de mineração e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-123">In the **Select Mining Model** dialog box, select a mining model, and then click **OK**.</span></span>  
  
     <span data-ttu-id="bdd8e-124">Você pode escolher qualquer modelo dentro do banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] atual.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-124">You can choose any model within the current [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="bdd8e-125">Para criar uma consulta usando um modelo em um banco de dados diferente, você deverá abrir uma nova janela de consulta no contexto desse banco de dados ou abrir o arquivo de solução que contém esse modelo.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-125">To create a query using a model in a different database, you must either open a new query window in the context of that database, or open the solution file that contains that model.</span></span>  
  
### <a name="add-prediction-functions-to-a-query"></a><span data-ttu-id="bdd8e-126">Adicionar funções de previsão a uma consulta</span><span class="sxs-lookup"><span data-stu-id="bdd8e-126">Add prediction functions to a query</span></span>  
  
1.  <span data-ttu-id="bdd8e-127">No **Construtor de Consultas de Previsão**, configure os dados de entrada usados para previsão, fornecendo valores na caixa de diálogo **Entrada de Consulta Singleton** ou mapeando o modelo para uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-127">In the **Prediction Query Builder**, configure the input data used for prediction, either by providing values in the **Singleton Query Input** dialog box, or by mapping the model to an external data source.</span></span>  
  
     <span data-ttu-id="bdd8e-128">Para obter mais informações, consulte [Escolher e mapear dados de entrada para uma consulta de previsão](choose-and-map-input-data-for-a-prediction-query.md).</span><span class="sxs-lookup"><span data-stu-id="bdd8e-128">For more information, see [Choose and Map Input Data for a Prediction Query](choose-and-map-input-data-for-a-prediction-query.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="bdd8e-129">Não é necessário que você forneça entradas para gerar previsões.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-129">It is not required that you provide inputs to generate predictions.</span></span> <span data-ttu-id="bdd8e-130">Quando não houver nenhuma entrada, o algoritmo geralmente retornará os valores de previsão mais prováveis em todas as possíveis entradas.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-130">When there is no input, the algorithm will typically return the mostly likely predicted value across all possible inputs.</span></span>  
  
2.  <span data-ttu-id="bdd8e-131">Clique na coluna **Origem** e escolha um valor da lista:</span><span class="sxs-lookup"><span data-stu-id="bdd8e-131">Click the **Source** column, and choose a value from the list:</span></span>  
  
    |||  
    |-|-|  
    |**\<model name>**|<span data-ttu-id="bdd8e-132">Selecione esta opção para incluir os valores do modelo de mineração na saída.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-132">Select this option to include values from the mining model in the output.</span></span> <span data-ttu-id="bdd8e-133">Somente é possível adicionar colunas previsíveis.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-133">You can only add predictable columns.</span></span><br /><br /> <span data-ttu-id="bdd8e-134">Quando você adicionar uma coluna do modelo, o resultado retornado é a lista não distinta de valores nessa coluna.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-134">When you add a column from the model, the result returned is the non-distinct list of values in that column.</span></span><br /><br /> <span data-ttu-id="bdd8e-135">As colunas que você adiciona com esta opção são incluídas na parte de SELECT da instrução DMX resultante.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-135">The columns that you add with this option are included in the SELECT portion of the resulting DMX statement.</span></span>|  
    |<span data-ttu-id="bdd8e-136">**Prediction Function**</span><span class="sxs-lookup"><span data-stu-id="bdd8e-136">**Prediction Function**</span></span>|<span data-ttu-id="bdd8e-137">Selecione esta opção para procurar uma lista de funções de previsão.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-137">Select this option to browse a list of prediction functions.</span></span><br /><br /> <span data-ttu-id="bdd8e-138">Os valores ou funções que você seleciona são adicionados à parte SELECT da instrução DMX resultante.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-138">The values or functions you select are added to the SELECT portion of the resulting DMX statement.</span></span><br /><br /> <span data-ttu-id="bdd8e-139">A lista de funções de previsão não é filtrada ou restringida pelo tipo de modelo que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-139">The list of prediction functions is not filtered or constrained by the type of model you have selected.</span></span> <span data-ttu-id="bdd8e-140">Portanto, se você tiver alguma dúvida sobre se a função tem suporte para o tipo modelo atual, bastará adicionar a função à lista e ver se há erro.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-140">Therefore, if you have any doubt about whether the function is supported for the current model type, you can just add the function to the list and see if there is an error.</span></span><br /><br /> <span data-ttu-id="bdd8e-141">Os itens de lista que são precedidos por $ (como $AdjustedProbability) representam colunas da tabela aninhada que são produzidas quando você usa a função `PredictHistogram`.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-141">List items that are preceded by $ (such as $AdjustedProbability) represent columns from the nested table that is output when you use the function, `PredictHistogram`.</span></span> <span data-ttu-id="bdd8e-142">Estes são atalhos que você pode usar para retornar uma única coluna e não uma tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-142">These are shortcuts that you can use to return a single column and not a nested table.</span></span>|  
    |<span data-ttu-id="bdd8e-143">**Expressão personalizada**</span><span class="sxs-lookup"><span data-stu-id="bdd8e-143">**Custom Expression**</span></span>|<span data-ttu-id="bdd8e-144">Selecione essa opção para digitar uma expressão personalizada e atribuir um alias à saída.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-144">Select this option to type a custom expression and then assign an alias to the output.</span></span><br /><br /> <span data-ttu-id="bdd8e-145">A expressão personalizada é adicionada à parte SELECT da consulta de previsão DMX resultante.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-145">The custom expression is added to the SELECT portion of the resulting DMX prediction query.</span></span><br /><br /> <span data-ttu-id="bdd8e-146">Esta opção será útil se você desejar adicionar texto para saída com cada linha, chamar funções VB ou chamar procedimentos armazenados personalizados.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-146">This option is useful if you want to add text for output with each row, to call VB functions, or to call custom stored procedures.</span></span><br /><br /> <span data-ttu-id="bdd8e-147">Para obter mais informações sobre como usar funções VBA e Excel no DMX, consulte [Funções VBA no MDX e no DAX](/sql/mdx/vba-functions-in-mdx-and-dax).</span><span class="sxs-lookup"><span data-stu-id="bdd8e-147">For information about using VBA and Excel functions from DMX, see [VBA functions in MDX and DAX](/sql/mdx/vba-functions-in-mdx-and-dax).</span></span>|  
  
3.  <span data-ttu-id="bdd8e-148">Depois de adicionar cada função ou expressão, alterne para a exibição do DMX para ver como a função é adicionada dentro da instrução DMX.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-148">After adding each function or expression, switch to DMX view to see how the function is added within the DMX statement.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="bdd8e-149">O Construtor de Consultas de Previsão não valida o DMX até você clicar em **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-149">The Prediction Query Builder does not validate the DMX until you click **Results**.</span></span> <span data-ttu-id="bdd8e-150">Você poderá eventualmente descobrir que a expressão gerada pelo construtor de consultas não é um DMX válido.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-150">Often, you will find that the expression that is produced by the query builder is not valid DMX.</span></span> <span data-ttu-id="bdd8e-151">As causas típicas fazem referência a uma coluna que não está relacionada à coluna previsível ou tentando prever uma coluna em uma tabela aninhada, que requer uma instrução sub-SELECT.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-151">Typical causes are referencing a column that is not related to the predictable column, or trying to predict a column in a nested table, which requires a sub-SELECT statement.</span></span> <span data-ttu-id="bdd8e-152">Neste momento, você pode alternar a exibição do DMX e continuar editando a instrução.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-152">At this point, you can switch to DMX view and continue editing the statement.</span></span>  
  
### <a name="example-create-a-query-on-a-clustering-model"></a><span data-ttu-id="bdd8e-153">Exemplo: criar uma consulta em um modelo de clustering</span><span class="sxs-lookup"><span data-stu-id="bdd8e-153">Example: Create a query on a clustering model</span></span>  
  
1.  <span data-ttu-id="bdd8e-154">Se você não tiver um modelo de clustering disponível para criar esta consulta de exemplo, crie o modelo [TM_Clustering] usando o [Tutorial Básico de Data Mining](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="bdd8e-154">If you do not have a clustering model available for building this sample query, create the model, [TM_Clustering], using the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span>  
  
2.  <span data-ttu-id="bdd8e-155">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse no modelo [TM_Clustering] e selecione **Criar Consulta de Previsão**.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-155">From [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the model, [TM_Clustering], and select **Build Prediction Query**.</span></span>  
  
3.  <span data-ttu-id="bdd8e-156">No menu **Modelo de Mineração** , selecione **Consulta Singleton**.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-156">From the **Mining Model** menu, select **Singleton Query**.</span></span>  
  
4.  <span data-ttu-id="bdd8e-157">Na caixa de diálogo **Entrada de Consulta Singleton** , defina os valores a seguir como entradas:</span><span class="sxs-lookup"><span data-stu-id="bdd8e-157">In the **Singleton Query Input** dialog box, set the following values as inputs:</span></span>  
  
    -   <span data-ttu-id="bdd8e-158">Gênero = M</span><span class="sxs-lookup"><span data-stu-id="bdd8e-158">Gender = M</span></span>  
  
    -   <span data-ttu-id="bdd8e-159">Distância do Trabalho = 5 a 10 milhas</span><span class="sxs-lookup"><span data-stu-id="bdd8e-159">Commute Distance = 5-10 miles</span></span>  
  
5.  <span data-ttu-id="bdd8e-160">Na grade de consulta, para **Origem**, selecione modelo de mineração do TM_Clustering e adicione a coluna [Bike Buyer].</span><span class="sxs-lookup"><span data-stu-id="bdd8e-160">In the query grid, for **Source**, select TM_Clustering mining model, and add the column, [Bike Buyer].</span></span>  
  
6.  <span data-ttu-id="bdd8e-161">Para **origem**, selecione **função de previsão**e adicione a função, `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="bdd8e-161">For **Source**, select **Prediction Function**, and add the function, `Cluster`.</span></span>  
  
7.  <span data-ttu-id="bdd8e-162">Para **origem**, selecione **função de previsão**, adicione a função, `PredictSupport` e arraste a coluna modelo [comprador de bicicleta] para a caixa **critérios/argumento** .</span><span class="sxs-lookup"><span data-stu-id="bdd8e-162">For **Source**, select **Prediction Function**, add the function, `PredictSupport`, and drag the model column [Bike Buyer] into the **Criteria/Argument** box.</span></span> <span data-ttu-id="bdd8e-163">Digite **Support** na coluna **Alias** .</span><span class="sxs-lookup"><span data-stu-id="bdd8e-163">Type **Support** in the **Alias** column.</span></span>  
  
     <span data-ttu-id="bdd8e-164">Copie a expressão que representa a função de previsão e referência de coluna na caixa **Critérios/Argumento** .</span><span class="sxs-lookup"><span data-stu-id="bdd8e-164">Copy the expression representing the prediction function and column reference from the **Criteria/Argument** box.</span></span>  
  
8.  <span data-ttu-id="bdd8e-165">Para **Origem**, selecione **Expressão Personalizada**, digite um alias e, em seguida, faça referência à função CEILING do Excel usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="bdd8e-165">For **Source**, select **Custom Expression**, type an alias, and then reference the Excel CEILING function by using the following syntax:</span></span>  
  
    ```  
    Excel![CEILING](<arguments) as <return type>  
    ```  
  
     <span data-ttu-id="bdd8e-166">Cole a referência de coluna como o argumento para a função.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-166">Paste the column reference in as the argument to the function.</span></span>  
  
     <span data-ttu-id="bdd8e-167">Por exemplo, a expressão a seguir retorna CEILING do valor de suporte:</span><span class="sxs-lookup"><span data-stu-id="bdd8e-167">For example, the following expression returns the CEILING of the support value:</span></span>  
  
    ```  
    EXCEL!CEILING(PredictSupport([TM_Clustering].[Bike Buyer]),2)  
    ```  
  
     <span data-ttu-id="bdd8e-168">Digite CEILING na coluna **Alias** .</span><span class="sxs-lookup"><span data-stu-id="bdd8e-168">Type CEILING in the **Alias** column.</span></span>  
  
9. <span data-ttu-id="bdd8e-169">Clique em **Alternar para a exibição de texto da consulta** para examinar a instrução DMX que foi gerada e, em seguida, clique em **Alternar para a exibição de resultado da consulta** para ver a saída das colunas pela consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-169">Click **Switch to query text view** to review the DMX statement that was generated, and then click **Switch to query result view** to see the columns output by the prediction query.</span></span>  
  
     <span data-ttu-id="bdd8e-170">A tabela a seguir mostra os resultados esperados:</span><span class="sxs-lookup"><span data-stu-id="bdd8e-170">The following table shows the expected results:</span></span>  
  
    |<span data-ttu-id="bdd8e-171">Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="bdd8e-171">Bike Buyer</span></span>|<span data-ttu-id="bdd8e-172">$Cluster</span><span class="sxs-lookup"><span data-stu-id="bdd8e-172">$Cluster</span></span>|<span data-ttu-id="bdd8e-173">SUPPORT</span><span class="sxs-lookup"><span data-stu-id="bdd8e-173">SUPPORT</span></span>|<span data-ttu-id="bdd8e-174">CEILING</span><span class="sxs-lookup"><span data-stu-id="bdd8e-174">CEILING</span></span>|  
    |----------------|--------------|-------------|-------------|  
    |<span data-ttu-id="bdd8e-175">0</span><span class="sxs-lookup"><span data-stu-id="bdd8e-175">0</span></span>|<span data-ttu-id="bdd8e-176">Cluster 8</span><span class="sxs-lookup"><span data-stu-id="bdd8e-176">Cluster 8</span></span>|<span data-ttu-id="bdd8e-177">954</span><span class="sxs-lookup"><span data-stu-id="bdd8e-177">954</span></span>|<span data-ttu-id="bdd8e-178">953.948638926372</span><span class="sxs-lookup"><span data-stu-id="bdd8e-178">953.948638926372</span></span>|  
  
 <span data-ttu-id="bdd8e-179">Se você quiser adicionar outras cláusulas em outro lugar na instrução, por exemplo, se quiser adicionar uma cláusula WHERE, você não poderá adicioná-la usando a grade; Você deve alternar para a exibição DMX primeiro.</span><span class="sxs-lookup"><span data-stu-id="bdd8e-179">If you want to add other clauses elsewhere in the statement-for example, if you want to add a WHERE clause-you cannot add it by using the grid; you must switch to DMX view first.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd8e-180">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bdd8e-180">See Also</span></span>  
 [<span data-ttu-id="bdd8e-181">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="bdd8e-181">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
