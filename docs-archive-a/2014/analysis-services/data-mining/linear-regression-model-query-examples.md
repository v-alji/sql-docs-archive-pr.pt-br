---
title: Exemplos de consulta de modelo de regressão linear | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- linear regression algorithms [Analysis Services]
- linear regression [Analysis Services]
- content queries [DMX]
ms.assetid: fd3cf312-57a1-44b6-b772-fce6fc1c26d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 02d4b7309d7b5ea3d6295089f0fb2e778b1c9b4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583255"
---
# <a name="linear-regression-model-query-examples"></a><span data-ttu-id="32b03-102">Exemplos de consulta de modelo de regressão linear</span><span class="sxs-lookup"><span data-stu-id="32b03-102">Linear Regression Model Query Examples</span></span>
  <span data-ttu-id="32b03-103">Ao criar uma consulta para um modelo de mineração de dados, você pode criar uma consulta de conteúdo que fornece detalhes de padrões encontrados em análises ou uma consulta de previsão que usa os padrões no modelo para fazer previsões para novos dados.</span><span class="sxs-lookup"><span data-stu-id="32b03-103">When you create a query against a data mining model, you can create a content query, which provides details about the patterns discovered in analysis, or you can create a prediction query, which uses the patterns in the model to make predictions for new data.</span></span> <span data-ttu-id="32b03-104">Por exemplo, uma consulta de conteúdo pode fornecer mais detalhes sobre a fórmula de regressão, enquanto uma consulta de previsão pode informar se um novo ponto de dados se ajusta ao modelo.</span><span class="sxs-lookup"><span data-stu-id="32b03-104">For example, a content query might provide additional details about the regression formula, while a prediction query might tell you if a new data point fits the model.</span></span> <span data-ttu-id="32b03-105">Você também pode recuperar metadados sobre o modelo usando uma consulta.</span><span class="sxs-lookup"><span data-stu-id="32b03-105">You can also retrieve metadata about the model by using a query.</span></span>  
  
 <span data-ttu-id="32b03-106">Esta seção explica como criar consultas para modelos baseados no algoritmo Regressão Linear da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32b03-106">This section explains how to create queries for models that are based on the Microsoft Linear Regression algorithm.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32b03-107">Como a regressão linear se baseia em um caso especial do algoritmo Árvores de Decisão da Microsoft, há muitas semelhanças. Além disso, alguns modelos de árvore de decisão que usam atributos previsíveis contínuos podem conter fórmulas de regressão.</span><span class="sxs-lookup"><span data-stu-id="32b03-107">Because linear regression is based on a special case of the Microsoft Decision Trees algorithm, there are many similarities, and some decision tree models that use continuous predictable attributes can contain regression formulas.</span></span> <span data-ttu-id="32b03-108">Para obter mais informações, consulte [Referência técnica do algoritmo Árvores de Decisão da Microsoft](microsoft-decision-trees-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="32b03-108">For more information, see [Microsoft Decision Trees Algorithm Technical Reference](microsoft-decision-trees-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="32b03-109">**Consultas de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="32b03-109">**Content queries**</span></span>  
  
 [<span data-ttu-id="32b03-110">Usando o conjunto de linhas de esquema de mineração de dados para determinar parâmetros usados para um modelo</span><span class="sxs-lookup"><span data-stu-id="32b03-110">Using the Data Mining Schema Rowset to determine parameters used for a model</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="32b03-111">Usando o DMX para retornar a fórmula de regressão do modelo</span><span class="sxs-lookup"><span data-stu-id="32b03-111">Using DMX to return the regression formula for the model</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="32b03-112">Retornando apenas o coeficiente do modelo</span><span class="sxs-lookup"><span data-stu-id="32b03-112">Returning only the coefficient for the model</span></span>](#bkmk_Query3)  
  
 <span data-ttu-id="32b03-113">**Consultas de previsão**</span><span class="sxs-lookup"><span data-stu-id="32b03-113">**Prediction queries**</span></span>  
  
 [<span data-ttu-id="32b03-114">Prevendo o resultado com o uso de uma consulta singleton</span><span class="sxs-lookup"><span data-stu-id="32b03-114">Predicting income using a singleton query</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="32b03-115">Usando funções de previsão com um modelo de regressão</span><span class="sxs-lookup"><span data-stu-id="32b03-115">Using prediction functions with a regression model</span></span>](#bkmk_Query5)  
  
##  <a name="finding-information-about-the-linear-regression-model"></a><a name="bkmk_top"></a><span data-ttu-id="32b03-116">Localizando informações sobre o modelo de regressão linear</span><span class="sxs-lookup"><span data-stu-id="32b03-116">Finding Information about the Linear Regression Model</span></span>  
 <span data-ttu-id="32b03-117">A estrutura de um modelo de regressão linear é extremamente simples: o modelo de mineração representa os dados como um único nó, que define a fórmula de regressão.</span><span class="sxs-lookup"><span data-stu-id="32b03-117">The structure of a linear regression model is extremely simple: the mining model represents the data as a single node, which defines the regression formula.</span></span> <span data-ttu-id="32b03-118">Para obter mais informações, consulte [Conteúdo do modelo de mineração para modelos de regressão logística &#40;Analysis Services – Data Mining&#41;](mining-model-content-for-logistic-regression-models.md).</span><span class="sxs-lookup"><span data-stu-id="32b03-118">For more information, see [Mining Model Content for Logistic Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-logistic-regression-models.md).</span></span>  
  
 [<span data-ttu-id="32b03-119">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="32b03-119">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-1-using-the-data-mining-schema-rowset-to-determine-parameters-used-for-a-model"></a><a name="bkmk_Query1"></a><span data-ttu-id="32b03-120">Exemplo de consulta 1: usando o conjunto de linhas de esquema de mineração de dados para determinar os parâmetros usados para um modelo</span><span class="sxs-lookup"><span data-stu-id="32b03-120">Sample Query 1: Using the Data Mining Schema Rowset to Determine Parameters Used for a Model</span></span>  
 <span data-ttu-id="32b03-121">Ao consultar o conjunto de linhas do esquema de mineração de dados, você pode encontrar metadados sobre o modelo.</span><span class="sxs-lookup"><span data-stu-id="32b03-121">By querying the data mining schema rowset, you can find metadata about the model.</span></span> <span data-ttu-id="32b03-122">Isso pode incluir quando o modelo foi criado, quando o modelo foi processado pela última vez, o nome da estrutura de mineração na qual o modelo se baseia e o nome da coluna designada como o atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="32b03-122">This might include when the model was created, when the model was last processed, the name of the mining structure that the model is based on, and the name of the column designated as the predictable attribute.</span></span> <span data-ttu-id="32b03-123">Você também pode retornar os parâmetros que foram usados quando o modelo foi criado.</span><span class="sxs-lookup"><span data-stu-id="32b03-123">You can also return the parameters that were used when the model was first created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM_PredictIncome'  
```  
  
 <span data-ttu-id="32b03-124">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="32b03-124">Sample results:</span></span>  
  
|<span data-ttu-id="32b03-125">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32b03-125">MINING_PARAMETERS</span></span>|  
|------------------------|  
|<span data-ttu-id="32b03-126">COMPLEXITY_PENALTY=0.9,</span><span class="sxs-lookup"><span data-stu-id="32b03-126">COMPLEXITY_PENALTY=0.9,</span></span><br /><br /> <span data-ttu-id="32b03-127">MAXIMUM_INPUT_ATTRIBUTES = 255</span><span class="sxs-lookup"><span data-stu-id="32b03-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="32b03-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="32b03-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="32b03-129">MINIMUM_SUPPORT = 10</span><span class="sxs-lookup"><span data-stu-id="32b03-129">MINIMUM_SUPPORT=10,</span></span><br /><br /> <span data-ttu-id="32b03-130">SCORE_METHOD=4,</span><span class="sxs-lookup"><span data-stu-id="32b03-130">SCORE_METHOD=4,</span></span><br /><br /> <span data-ttu-id="32b03-131">SPLIT_METHOD=3,</span><span class="sxs-lookup"><span data-stu-id="32b03-131">SPLIT_METHOD=3,</span></span><br /><br /> <span data-ttu-id="32b03-132">FORCE_REGRESSOR=</span><span class="sxs-lookup"><span data-stu-id="32b03-132">FORCE_REGRESSOR=</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="32b03-133">A configuração de parâmetro "`FORCE_REGRESSOR =` " indica que o valor atual do parâmetro FORCE_REGRESSOR é nulo.</span><span class="sxs-lookup"><span data-stu-id="32b03-133">The parameter setting, "`FORCE_REGRESSOR =` ", indicates that the current value for the FORCE_REGRESSOR parameter is null.</span></span>  
  
 [<span data-ttu-id="32b03-134">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="32b03-134">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-2-retrieving-the-regression-formula-for-the-model"></a><a name="bkmk_Query2"></a><span data-ttu-id="32b03-135">Exemplo de consulta 2: Recuperando a fórmula de regressão para o modelo</span><span class="sxs-lookup"><span data-stu-id="32b03-135">Sample Query 2: Retrieving the Regression Formula for the Model</span></span>  
 <span data-ttu-id="32b03-136">A consulta a seguir retorna o conteúdo do modelo de mineração de um modelo de regressão linear criado com o uso dos mesmos dados de Mala Direta utilizados no [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="32b03-136">The following query returns the mining model content for a linear regression model that was built by using the same Targeted Mailing data source that was used in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="32b03-137">Este modelo prevê a renda do cliente com base na idade.</span><span class="sxs-lookup"><span data-stu-id="32b03-137">This model predicts customer income based on age.</span></span>  
  
 <span data-ttu-id="32b03-138">A consulta retorna o conteúdo do nó que contém a fórmula de regressão.</span><span class="sxs-lookup"><span data-stu-id="32b03-138">The query returns the contents of the node that contains the regression formula.</span></span> <span data-ttu-id="32b03-139">Cada variável e coeficiente são armazenados em uma linha separada da tabela aninhada NODE_DISTRIBUTION.</span><span class="sxs-lookup"><span data-stu-id="32b03-139">Each variable and coefficient is stored in a separate row of the nested NODE_DISTRIBUTION table.</span></span> <span data-ttu-id="32b03-140">Para exibir a fórmula de regressão completa, use o [Visualizador de Árvore da Microsoft](browse-a-model-using-the-microsoft-tree-viewer.md), clique no nó **(Tudo)** e abra a **Legenda de Mineração**.</span><span class="sxs-lookup"><span data-stu-id="32b03-140">If you want to view the complete regression formula, use the [Microsoft Tree Viewer](browse-a-model-using-the-microsoft-tree-viewer.md), click the **(All)** node, and open the **Mining Legend**.</span></span>  
  
```  
SELECT FLATTENED NODE_DISTRIBUTION as t  
FROM LR_PredictIncome.CONTENT  
```  
  
> [!NOTE]  
>  <span data-ttu-id="32b03-141">Se você referenciar colunas individuais da tabela aninhada usando uma consulta como `SELECT <column name> from NODE_DISTRIBUTION`, algumas colunas, como **SUPPORT** ou **PROBABILITY**, deverão ser colocadas entre colchetes para distingui-las das palavras-chave reservadas de mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="32b03-141">If you reference individual columns of the nested table by using a query such as `SELECT <column name> from NODE_DISTRIBUTION`, some columns, such as **SUPPORT** or **PROBABILITY**, must be enclosed in brackets to distinguish them from reserved keywords of the same name.</span></span>  
  
 <span data-ttu-id="32b03-142">Resultados esperados:</span><span class="sxs-lookup"><span data-stu-id="32b03-142">Expected results:</span></span>  
  
|<span data-ttu-id="32b03-143">T.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="32b03-143">t.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="32b03-144">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="32b03-144">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="32b03-145">t.SUPPORT</span><span class="sxs-lookup"><span data-stu-id="32b03-145">t.SUPPORT</span></span>|<span data-ttu-id="32b03-146">t.PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="32b03-146">t.PROBABILITY</span></span>|<span data-ttu-id="32b03-147">t.VARIANCE</span><span class="sxs-lookup"><span data-stu-id="32b03-147">t.VARIANCE</span></span>|<span data-ttu-id="32b03-148">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="32b03-148">t.VALUETYPE</span></span>|  
|-----------------------|------------------------|---------------|-------------------|----------------|-----------------|  
|<span data-ttu-id="32b03-149">Renda Anual</span><span class="sxs-lookup"><span data-stu-id="32b03-149">Yearly Income</span></span>|<span data-ttu-id="32b03-150">Ausente</span><span class="sxs-lookup"><span data-stu-id="32b03-150">Missing</span></span>|<span data-ttu-id="32b03-151">0</span><span class="sxs-lookup"><span data-stu-id="32b03-151">0</span></span>|<span data-ttu-id="32b03-152">0.000457142857142857</span><span class="sxs-lookup"><span data-stu-id="32b03-152">0.000457142857142857</span></span>|<span data-ttu-id="32b03-153">0</span><span class="sxs-lookup"><span data-stu-id="32b03-153">0</span></span>|<span data-ttu-id="32b03-154">1</span><span class="sxs-lookup"><span data-stu-id="32b03-154">1</span></span>|  
|<span data-ttu-id="32b03-155">Renda Anual</span><span class="sxs-lookup"><span data-stu-id="32b03-155">Yearly Income</span></span>|<span data-ttu-id="32b03-156">57220.8876687257</span><span class="sxs-lookup"><span data-stu-id="32b03-156">57220.8876687257</span></span>|<span data-ttu-id="32b03-157">17484</span><span class="sxs-lookup"><span data-stu-id="32b03-157">17484</span></span>|<span data-ttu-id="32b03-158">0.999542857142857</span><span class="sxs-lookup"><span data-stu-id="32b03-158">0.999542857142857</span></span>|<span data-ttu-id="32b03-159">1041275619.52776</span><span class="sxs-lookup"><span data-stu-id="32b03-159">1041275619.52776</span></span>|<span data-ttu-id="32b03-160">3</span><span class="sxs-lookup"><span data-stu-id="32b03-160">3</span></span>|  
|<span data-ttu-id="32b03-161">Idade</span><span class="sxs-lookup"><span data-stu-id="32b03-161">Age</span></span>|<span data-ttu-id="32b03-162">471.687717702463</span><span class="sxs-lookup"><span data-stu-id="32b03-162">471.687717702463</span></span>|<span data-ttu-id="32b03-163">0</span><span class="sxs-lookup"><span data-stu-id="32b03-163">0</span></span>|<span data-ttu-id="32b03-164">0</span><span class="sxs-lookup"><span data-stu-id="32b03-164">0</span></span>|<span data-ttu-id="32b03-165">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="32b03-165">126.969442359327</span></span>|<span data-ttu-id="32b03-166">7</span><span class="sxs-lookup"><span data-stu-id="32b03-166">7</span></span>|  
|<span data-ttu-id="32b03-167">Idade</span><span class="sxs-lookup"><span data-stu-id="32b03-167">Age</span></span>|<span data-ttu-id="32b03-168">234.680904692439</span><span class="sxs-lookup"><span data-stu-id="32b03-168">234.680904692439</span></span>|<span data-ttu-id="32b03-169">0</span><span class="sxs-lookup"><span data-stu-id="32b03-169">0</span></span>|<span data-ttu-id="32b03-170">0</span><span class="sxs-lookup"><span data-stu-id="32b03-170">0</span></span>|<span data-ttu-id="32b03-171">0</span><span class="sxs-lookup"><span data-stu-id="32b03-171">0</span></span>|<span data-ttu-id="32b03-172">8</span><span class="sxs-lookup"><span data-stu-id="32b03-172">8</span></span>|  
|<span data-ttu-id="32b03-173">Idade</span><span class="sxs-lookup"><span data-stu-id="32b03-173">Age</span></span>|<span data-ttu-id="32b03-174">45.4269617936399</span><span class="sxs-lookup"><span data-stu-id="32b03-174">45.4269617936399</span></span>|<span data-ttu-id="32b03-175">0</span><span class="sxs-lookup"><span data-stu-id="32b03-175">0</span></span>|<span data-ttu-id="32b03-176">0</span><span class="sxs-lookup"><span data-stu-id="32b03-176">0</span></span>|<span data-ttu-id="32b03-177">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="32b03-177">126.969442359327</span></span>|<span data-ttu-id="32b03-178">9</span><span class="sxs-lookup"><span data-stu-id="32b03-178">9</span></span>|  
||<span data-ttu-id="32b03-179">35793.5477381267</span><span class="sxs-lookup"><span data-stu-id="32b03-179">35793.5477381267</span></span>|<span data-ttu-id="32b03-180">0</span><span class="sxs-lookup"><span data-stu-id="32b03-180">0</span></span>|<span data-ttu-id="32b03-181">0</span><span class="sxs-lookup"><span data-stu-id="32b03-181">0</span></span>|<span data-ttu-id="32b03-182">1012968919.28372</span><span class="sxs-lookup"><span data-stu-id="32b03-182">1012968919.28372</span></span>|<span data-ttu-id="32b03-183">11</span><span class="sxs-lookup"><span data-stu-id="32b03-183">11</span></span>|  
  
 <span data-ttu-id="32b03-184">Em comparação, na **Legenda de Mineração**, a fórmula de regressão aparece da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="32b03-184">In comparison, in the **Mining Legend**, the regression formula appears as follows:</span></span>  
  
 <span data-ttu-id="32b03-185">Renda Anual = 57,220.919 + 471.688 \* (Idade - 45.427)</span><span class="sxs-lookup"><span data-stu-id="32b03-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span></span>  
  
 <span data-ttu-id="32b03-186">Você pode observar que, na **Legenda de Mineração**, alguns números são arredondados; no entanto, a tabela NODE_DISTRIBUTION e a **Legenda de Mineração** contêm basicamente os mesmos valores.</span><span class="sxs-lookup"><span data-stu-id="32b03-186">You can see that in the **Mining Legend**, some numbers are rounded; however, the NODE_DISTRIBUTION table and the **Mining Legend** essentially contain the same values.</span></span>  
  
 <span data-ttu-id="32b03-187">Os valores na coluna VALUETYPE informa que tipo de informações estão em cada linha, o que será útil se você estiver processando os resultados programaticamente.</span><span class="sxs-lookup"><span data-stu-id="32b03-187">The values in the VALUETYPE column tell you what kind of information is contained in each row, which is useful if you are processing the results programmatically.</span></span> <span data-ttu-id="32b03-188">A tabela a seguir mostra os tipos de valores produzidos para uma fórmula de regressão linear.</span><span class="sxs-lookup"><span data-stu-id="32b03-188">The following table shows the value types that are output for a linear regression formula.</span></span>  
  
|<span data-ttu-id="32b03-189">VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="32b03-189">VALUETYPE</span></span>|  
|---------------|  
|<span data-ttu-id="32b03-190">1 (Ausente)</span><span class="sxs-lookup"><span data-stu-id="32b03-190">1 (Missing)</span></span>|  
|<span data-ttu-id="32b03-191">3 (Contínuo)</span><span class="sxs-lookup"><span data-stu-id="32b03-191">3 (Continuous)</span></span>|  
|<span data-ttu-id="32b03-192">7 (Coeficiente)</span><span class="sxs-lookup"><span data-stu-id="32b03-192">7 (Coefficient)</span></span>|  
|<span data-ttu-id="32b03-193">8 (Ganho de pontos)</span><span class="sxs-lookup"><span data-stu-id="32b03-193">8 (Score Gain)</span></span>|  
|<span data-ttu-id="32b03-194">9 (Estatísticas)</span><span class="sxs-lookup"><span data-stu-id="32b03-194">9 (Statistics)</span></span>|  
|<span data-ttu-id="32b03-195">7 (Coeficiente)</span><span class="sxs-lookup"><span data-stu-id="32b03-195">7 (Coefficient)</span></span>|  
|<span data-ttu-id="32b03-196">8 (Ganho de pontos)</span><span class="sxs-lookup"><span data-stu-id="32b03-196">8 (Score Gain)</span></span>|  
|<span data-ttu-id="32b03-197">9 (Estatísticas)</span><span class="sxs-lookup"><span data-stu-id="32b03-197">9 (Statistics)</span></span>|  
|<span data-ttu-id="32b03-198">11 (Interceptação)</span><span class="sxs-lookup"><span data-stu-id="32b03-198">11 (Intercept)</span></span>|  
  
 <span data-ttu-id="32b03-199">Para obter mais informações sobre o significado de cada tipo de valor para modelos de regressão, consulte [Conteúdo do modelo de mineração para modelos de regressão linear &#40;Analysis Services – Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="32b03-199">For more information about the meaning of each value type for regression models, see [Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="32b03-200">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="32b03-200">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-3-returning-only-the-coefficient-for-the-model"></a><a name="bkmk_Query3"></a><span data-ttu-id="32b03-201">Exemplo de consulta 3: retornando apenas o coeficiente do modelo</span><span class="sxs-lookup"><span data-stu-id="32b03-201">Sample Query 3: Returning Only the Coefficient for the Model</span></span>  
 <span data-ttu-id="32b03-202">Ao usar a enumeração VALUETYPE, você só pode retornar o coeficiente da equação de regressão, conforme mostrado na seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="32b03-202">By using the VALUETYPE enumeration, you can return only the coefficient for the regression equation, as shown in the following query:</span></span>  
  
```  
SELECT FLATTENED MODEL_NAME,  
    (SELECT ATTRIBUTE_VALUE, VALUETYPE  
     FROM NODE_DISTRIBUTION  
     WHERE VALUETYPE = 11)   
AS t  
FROM LR_PredictIncome.CONTENT  
```  
  
 <span data-ttu-id="32b03-203">Essa consulta retorna duas linhas, um a do conteúdo do modelo de mineração e a outra da tabela aninhada que contém o coeficiente.</span><span class="sxs-lookup"><span data-stu-id="32b03-203">This query returns two rows, one from the mining model content, and the row from the nested table that contains the coefficient.</span></span> <span data-ttu-id="32b03-204">A coluna ATTRIBUTE_NAME não é incluída aqui porque sempre fica em branco para o coeficiente.</span><span class="sxs-lookup"><span data-stu-id="32b03-204">The ATTRIBUTE_NAME column is not included here because it is always blank for the coefficient.</span></span>  
  
|<span data-ttu-id="32b03-205">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="32b03-205">MODEL_NAME</span></span>|<span data-ttu-id="32b03-206">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="32b03-206">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="32b03-207">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="32b03-207">t.VALUETYPE</span></span>|  
|-----------------|------------------------|-----------------|  
|<span data-ttu-id="32b03-208">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="32b03-208">LR_PredictIncome</span></span>|||  
|<span data-ttu-id="32b03-209">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="32b03-209">LR_PredictIncome</span></span>|<span data-ttu-id="32b03-210">35793.5477381267</span><span class="sxs-lookup"><span data-stu-id="32b03-210">35793.5477381267</span></span>|<span data-ttu-id="32b03-211">11</span><span class="sxs-lookup"><span data-stu-id="32b03-211">11</span></span>|  
  
 [<span data-ttu-id="32b03-212">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="32b03-212">Return to Top</span></span>](#bkmk_top)  
  
## <a name="making-predictions-from-a-linear-regression-model"></a><span data-ttu-id="32b03-213">Fazendo previsões de um modelo de regressão linear</span><span class="sxs-lookup"><span data-stu-id="32b03-213">Making Predictions from a Linear Regression Model</span></span>  
 <span data-ttu-id="32b03-214">Você pode criar consultas de previsão em modelos de regressão linear usando a guia Previsão do Modelo de Mineração no Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="32b03-214">You can build prediction queries on linear regression models by using the Mining Model Prediction tab in Data Mining Designer.</span></span> <span data-ttu-id="32b03-215">O construtor de consultas de previsão está disponível no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32b03-215">The prediction query builder is available in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32b03-216">Também é possível criar consultas em modelos de regressão usando os Suplementos de Mineração de Dados para Excel do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32b03-216">You can also create queries on regression models by using the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Data Mining Add-ins for Excel or the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Data Mining Add-ins for Excel.</span></span> <span data-ttu-id="32b03-217">Mesmo que os Suplementos de Mineração de Dados para Excel não criem modelos de regressão, você pode procurar e consultar qualquer modelo de mineração armazenado em uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32b03-217">Even though the Data Mining Add-ins for Excel do not create regression models, you can browse and query any mining model that is stored on an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="32b03-218">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="32b03-218">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-4-predicting-income-using-a-singleton-query"></a><a name="bkmk_Query4"></a><span data-ttu-id="32b03-219">Exemplo de consulta 4: prevendo a renda usando uma consulta singleton</span><span class="sxs-lookup"><span data-stu-id="32b03-219">Sample Query 4: Predicting Income using a Singleton Query</span></span>  
 <span data-ttu-id="32b03-220">A maneira mais fácil de criar uma consulta single em um modelo de regressão é usando a caixa de diálogo **Entrada de Consulta Singleton** .</span><span class="sxs-lookup"><span data-stu-id="32b03-220">The easiest way to create a single query on a regression model is by using the **Singleton Query Input** dialog box.</span></span> <span data-ttu-id="32b03-221">Por exemplo, você pode criar a seguinte consulta DMX selecionando o modelo de regressão apropriado, escolhendo **consulta singleton**e, em seguida, digitando `20` como o valor de **idade**.</span><span class="sxs-lookup"><span data-stu-id="32b03-221">For example, you can build the following DMX query by selecting the appropriate regression model, choosing **Singleton Query**, and then typing `20` as the value for **Age**.</span></span>  
  
```  
SELECT [LR_PredictIncome].[Yearly Income]  
From   [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="32b03-222">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="32b03-222">Sample results:</span></span>  
  
|<span data-ttu-id="32b03-223">Renda Anual</span><span class="sxs-lookup"><span data-stu-id="32b03-223">Yearly Income</span></span>|  
|-------------------|  
|<span data-ttu-id="32b03-224">45227.302092176</span><span class="sxs-lookup"><span data-stu-id="32b03-224">45227.302092176</span></span>|  
  
 [<span data-ttu-id="32b03-225">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="32b03-225">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-5-using-prediction-functions-with-a-regression-model"></a><a name="bkmk_Query5"></a><span data-ttu-id="32b03-226">Exemplo de consulta 5: usando funções de previsão com um modelo de regressão</span><span class="sxs-lookup"><span data-stu-id="32b03-226">Sample Query 5: Using Prediction Functions with a Regression Model</span></span>  
 <span data-ttu-id="32b03-227">Você pode usar muitas das funções de previsão padrão com modelos de regressão linear.</span><span class="sxs-lookup"><span data-stu-id="32b03-227">You can use many of the standard prediction functions with linear regression models.</span></span> <span data-ttu-id="32b03-228">O exemplo a seguir demonstra como adicionar algumas estatísticas descritivas aos resultados da consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="32b03-228">The following example illustrates how to add some descriptive statistics to the prediction query results.</span></span> <span data-ttu-id="32b03-229">Com base nesses resultados, você pode observar que há um desvio considerável da média para este modelo.</span><span class="sxs-lookup"><span data-stu-id="32b03-229">From these results, you can see that there is considerable deviation from the mean for this model.</span></span>  
  
```  
SELECT  
  ([LR_PredictIncome].[Yearly Income]) as [PredIncome],  
  (PredictStdev([LR_PredictIncome].[Yearly Income])) as [StDev1]  
From  
  [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="32b03-230">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="32b03-230">Sample results:</span></span>  
  
|<span data-ttu-id="32b03-231">Renda Anual</span><span class="sxs-lookup"><span data-stu-id="32b03-231">Yearly Income</span></span>|<span data-ttu-id="32b03-232">StDev1</span><span class="sxs-lookup"><span data-stu-id="32b03-232">StDev1</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="32b03-233">45227.302092176</span><span class="sxs-lookup"><span data-stu-id="32b03-233">45227.302092176</span></span>|<span data-ttu-id="32b03-234">31827.1726561396</span><span class="sxs-lookup"><span data-stu-id="32b03-234">31827.1726561396</span></span>|  
  
 [<span data-ttu-id="32b03-235">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="32b03-235">Return to Top</span></span>](#bkmk_top)  
  
## <a name="list-of-prediction-functions"></a><span data-ttu-id="32b03-236">Lista de funções de previsão</span><span class="sxs-lookup"><span data-stu-id="32b03-236">List of Prediction Functions</span></span>  
 <span data-ttu-id="32b03-237">Todos os algoritmos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] dão suporte a um conjunto comum de funções.</span><span class="sxs-lookup"><span data-stu-id="32b03-237">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="32b03-238">Entretanto, o algoritmo Regressão Linear da [!INCLUDE[msCoName](../../includes/msconame-md.md)] oferece suporte às funções adicionais relacionadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="32b03-238">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32b03-239">Função de previsão</span><span class="sxs-lookup"><span data-stu-id="32b03-239">Prediction Function</span></span>|<span data-ttu-id="32b03-240">Uso</span><span class="sxs-lookup"><span data-stu-id="32b03-240">Usage</span></span>|  
|[<span data-ttu-id="32b03-241">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="32b03-241">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="32b03-242">Determina se um nó é um filho de outro nó no modelo.</span><span class="sxs-lookup"><span data-stu-id="32b03-242">Determines whether one node is a child of another node in the model.</span></span>|  
|[<span data-ttu-id="32b03-243">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="32b03-243">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="32b03-244">Indica se o nó especificado contém o caso atual.</span><span class="sxs-lookup"><span data-stu-id="32b03-244">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="32b03-245">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="32b03-245">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="32b03-246">Retorna um valor previsto ou conjunto de valores de uma coluna especificada.</span><span class="sxs-lookup"><span data-stu-id="32b03-246">Returns a predicted value, or set of values, for a specified column.</span></span>|  
|[<span data-ttu-id="32b03-247">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="32b03-247">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="32b03-248">Retorna Node_ID para cada caso.</span><span class="sxs-lookup"><span data-stu-id="32b03-248">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="32b03-249">PredictStdev &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="32b03-249">PredictStdev &#40;DMX&#41;</span></span>](/sql/dmx/predictstdev-dmx)|<span data-ttu-id="32b03-250">Retorna o desvio padrão previsto para o valor previsto.</span><span class="sxs-lookup"><span data-stu-id="32b03-250">Returns standard deviation for the predicted value.</span></span>|  
|[<span data-ttu-id="32b03-251">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="32b03-251">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="32b03-252">Retorna o valor de suporte para um estado especificado.</span><span class="sxs-lookup"><span data-stu-id="32b03-252">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="32b03-253">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="32b03-253">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="32b03-254">Retorna a variação de uma coluna especificada.</span><span class="sxs-lookup"><span data-stu-id="32b03-254">Returns the variance of a specified column.</span></span>|  
  
 <span data-ttu-id="32b03-255">Para obter uma lista das funções comuns a todos os algoritmos do [!INCLUDE[msCoName](../../includes/msconame-md.md)], consulte [Algoritmos de mineração de dados &#40;Analysis Services – Mineração de dados&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="32b03-255">For a list of the functions that are common to all [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span> <span data-ttu-id="32b03-256">Para obter mais informações sobre como usar essas funções, consulte [Referência de função de DMX &#40;extensões DMX&#41;](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="32b03-256">For more information about how to use these functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b03-257">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32b03-257">See Also</span></span>  
 <span data-ttu-id="32b03-258">[Algoritmo de regressão linear da Microsoft](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="32b03-258">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="32b03-259">[Consultas de mineração de dados](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="32b03-259">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="32b03-260">[Referência técnica do algoritmo regressão linear da Microsoft](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="32b03-260">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="32b03-261">Conteúdo do modelo de mineração para modelos de regressão linear &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="32b03-261">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
