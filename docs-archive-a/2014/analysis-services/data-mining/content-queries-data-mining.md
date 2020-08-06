---
title: Consultas de conteúdo (mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c4f4a5a8-a230-4222-bece-9d563501f65f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44b162c34f5f505462a713205d8434484473afa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583910"
---
# <a name="content-queries-data-mining"></a><span data-ttu-id="aca56-102">Consultas de conteúdo (mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="aca56-102">Content Queries (Data Mining)</span></span>
  <span data-ttu-id="aca56-103">Uma consulta de conteúdo é um modo de extrair informações sobre as estatísticas internas e a estrutura do modelo de mineração propriamente dito.</span><span class="sxs-lookup"><span data-stu-id="aca56-103">A content query is a way of extracting information about the internal statistics and structure of the mining model.</span></span> <span data-ttu-id="aca56-104">Às vezes uma consulta de conteúdo pode fornecer detalhes que não estão prontamente disponível no visualizador.</span><span class="sxs-lookup"><span data-stu-id="aca56-104">Sometimes a content query can provide details that are not readily available in the viewer.</span></span> <span data-ttu-id="aca56-105">Você também pode usar os resultados de uma consulta de conteúdo para extrair informações programaticamente por outros usos.</span><span class="sxs-lookup"><span data-stu-id="aca56-105">You can also use the results of a content query to extract information programmatically for other uses.</span></span>  
  
 <span data-ttu-id="aca56-106">Esta seção fornece informações gerais sobre os tipos de informações que podem ser recuperadas com uma consulta de conteúdo e a sintaxe DMX geral para consultas de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="aca56-106">This section provides general information about the types of information that you can retrieve by using a content query, and the general DMX syntax for content queries.</span></span>  
  
 [<span data-ttu-id="aca56-107">Consultas básicas de conteúdo</span><span class="sxs-lookup"><span data-stu-id="aca56-107">Basic Content Queries</span></span>](#bkmk_ContentQuery)  
  
-   [<span data-ttu-id="aca56-108">Consultas sobre estrutura e dados de caso</span><span class="sxs-lookup"><span data-stu-id="aca56-108">Queries on Structure and Case Data</span></span>](#bkmk_Structure)  
  
-   [<span data-ttu-id="aca56-109">Consultas em padrões de modelo</span><span class="sxs-lookup"><span data-stu-id="aca56-109">Queries on Model Patterns</span></span>](#bkmk_Patterns)  
  
 [<span data-ttu-id="aca56-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="aca56-110">Examples</span></span>](#bkmk_Examples)  
  
-   [<span data-ttu-id="aca56-111">Consulta de conteúdo em um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="aca56-111">Content Query on an Association Model</span></span>](#bkmk_Assoc)  
  
-   [<span data-ttu-id="aca56-112">Consulta de conteúdo em um modelo de árvores de decisão</span><span class="sxs-lookup"><span data-stu-id="aca56-112">Content Query on a Decision Trees Model</span></span>](#bkmk_DecTree)  
  
 [<span data-ttu-id="aca56-113">Trabalhando com resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="aca56-113">Working with the Query Results</span></span>](#bkmk_Results)  
  
##  <a name="basic-content-queries"></a><a name="bkmk_ContentQuery"></a><span data-ttu-id="aca56-114">Consultas básicas de conteúdo</span><span class="sxs-lookup"><span data-stu-id="aca56-114">Basic Content Queries</span></span>  
 <span data-ttu-id="aca56-115">Você pode criar consultas de conteúdo usando o Construtor de consulta de previsão, usar os modelos de consulta de conteúdo DMX fornecidos no SQL Server Management Studio ou escrever consultas diretamente no DMX.</span><span class="sxs-lookup"><span data-stu-id="aca56-115">You can create content queries by using the Prediction Query Builder, use the DMX content query templates that are provided in SQL Server Management Studio, or write queries directly in DMX.</span></span> <span data-ttu-id="aca56-116">Ao contrário das consultas de previsão, você não precisa unir dados externos e, dessa maneira, as consultas de conteúdo são fáceis escrever.</span><span class="sxs-lookup"><span data-stu-id="aca56-116">Unlike prediction queries you do not need to join external data, so content queries are easy to write.</span></span>  
  
 <span data-ttu-id="aca56-117">Esta seção fornece uma visão geral dos tipos de consultas de conteúdo que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="aca56-117">This section provides an overview of the types of content queries you can create.</span></span>  
  
-   <span data-ttu-id="aca56-118">Consultas na estrutura de mineração ou dados de caso permitem exibir os dados detalhados que foram usados para treinamento.</span><span class="sxs-lookup"><span data-stu-id="aca56-118">Queries on the mining structure or case data let you view the detailed data that was used for training.</span></span>  
  
-   <span data-ttu-id="aca56-119">As consultas no modelo podem retornar padrões, listas de atributos, fórmulas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="aca56-119">Queries on the model can return patterns, lists of attributes, formulas, and so forth.</span></span>  
  
###  <a name="queries-on-structure-and-case-data"></a><a name="bkmk_Structure"></a> <span data-ttu-id="aca56-120">Consultas sobre estrutura e dados do caso</span><span class="sxs-lookup"><span data-stu-id="aca56-120">Queries on Structure and Case Data</span></span>  
 <span data-ttu-id="aca56-121">O DMX dá suporte a consultas nos dados armazenados em cache que são usados para criar estruturas de mineração e modelos.</span><span class="sxs-lookup"><span data-stu-id="aca56-121">DMX supports queries on the cached data that is used to build mining structures and models.</span></span> <span data-ttu-id="aca56-122">Por padrão, este cache é criado quando você define a estrutura de mineração, e é populado quando você processa a estrutura ou modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-122">By default, this cache is created when you define the mining structure, and is populated when you process the structure or model.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="aca56-123">Este cache não poderá ser desmarcado ou excluído se você precisar separar dados em conjuntos de treinamento e teste.</span><span class="sxs-lookup"><span data-stu-id="aca56-123">This cache cannot be cleared or deleted if you need to separate data into training and testing sets.</span></span> <span data-ttu-id="aca56-124">Se o cache for desmarcado, você não poderá consultar os dados do caso.</span><span class="sxs-lookup"><span data-stu-id="aca56-124">If the cache is cleared, you cannot query the case data.</span></span>  
  
 <span data-ttu-id="aca56-125">Os exemplos a seguir mostram os padrões comuns para criar consultas nos dados de caso ou consultas nos dados na estrutura de mineração:</span><span class="sxs-lookup"><span data-stu-id="aca56-125">The following examples show the common patterns for creating queries on the case data, or queries on the data in the mining structure:</span></span>  
  
 <span data-ttu-id="aca56-126">**Obtenha todos os casos para um modelo**</span><span class="sxs-lookup"><span data-stu-id="aca56-126">**Get all the cases for a model**</span></span>  
 `SELECT FROM <model>.CASES`  
  
 <span data-ttu-id="aca56-127">Use esta instrução para recuperar colunas especificadas nos dados do caso usados para criar um modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-127">Use this statement to retrieve specified columns from the case data used to build a model.</span></span> <span data-ttu-id="aca56-128">Você deve ter permissões de detalhamento no modelo para executar esta consulta.</span><span class="sxs-lookup"><span data-stu-id="aca56-128">You must have drillthrough permissions on the model to run this query.</span></span>  
  
 <span data-ttu-id="aca56-129">**Exibir todos os dados que estão incluídos na estrutura**</span><span class="sxs-lookup"><span data-stu-id="aca56-129">**View all the data that is included in the structure**</span></span>  
 `SELECT FROM <structure>.CASES`  
  
 <span data-ttu-id="aca56-130">Use essa instrução para exibir todos os dados incluídos na estrutura, incluindo as colunas que não foram adicionadas a um modelo de mineração específico.</span><span class="sxs-lookup"><span data-stu-id="aca56-130">Use this statement to view all the data that is included in the structure, including columns that are not included in a particular mining model.</span></span> <span data-ttu-id="aca56-131">Você deve ter permissões de detalhamento no modelo, assim como na estrutura, para recuperar dados da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="aca56-131">You must have drillthrough permissions on the model, as well as on the structure, to retrieve data from the mining structure.</span></span>  
  
 <span data-ttu-id="aca56-132">**Obter intervalo de valores**</span><span class="sxs-lookup"><span data-stu-id="aca56-132">**Get range of values**</span></span>  
 `SELECT DISTINCT RangeMin(<column>), RangeMax(<column>) FROM <model>`  
  
 <span data-ttu-id="aca56-133">Use esta instrução para localizar o valor mínimo, o valor máximo e a média de uma coluna contínua, ou dos buckets de uma coluna DISCRETIZED.</span><span class="sxs-lookup"><span data-stu-id="aca56-133">Use this statement to find the minimum value, maximum value, and mean of a continuous column, or of the buckets of a DISCRETIZED column.</span></span>  
  
 <span data-ttu-id="aca56-134">**Obter valores distintos**</span><span class="sxs-lookup"><span data-stu-id="aca56-134">**Get distinct values**</span></span>  
 `SELECT DISTINCT <column>FROM <model>`  
  
 <span data-ttu-id="aca56-135">Use esta instrução para recuperar todos os valores de uma coluna DISCRETE.</span><span class="sxs-lookup"><span data-stu-id="aca56-135">Use this statement to retrieve all the values of a DISCRETE column.</span></span>  <span data-ttu-id="aca56-136">Não use esta instrução para colunas DISCRETIZED; use as funções `RangeMin` e `RangeMax`.</span><span class="sxs-lookup"><span data-stu-id="aca56-136">Do not use this statement for DISCRETIZED columns; use the `RangeMin` and `RangeMax` functions instead.</span></span>  
  
 <span data-ttu-id="aca56-137">**Localizar os casos usados para treinar um modelo ou estrutura**</span><span class="sxs-lookup"><span data-stu-id="aca56-137">**Find the cases that were used to train a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTrainingCase()`  
  
 <span data-ttu-id="aca56-138">Use esta instrução para obter o conjunto completo de dados que foram usados um modelo de treinamento.</span><span class="sxs-lookup"><span data-stu-id="aca56-138">Use this statement to get the complete set of data that was used in a training a model.</span></span>  
  
 <span data-ttu-id="aca56-139">**Localizar os casos que foram usados para testar um modelo ou estrutura**</span><span class="sxs-lookup"><span data-stu-id="aca56-139">**Find the cases that are used for testing a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTestingCase()`  
  
 <span data-ttu-id="aca56-140">Use esta instrução para obter os dados que foram colocados de lado para testar modelos de mineração relacionados a uma estrutura específica.</span><span class="sxs-lookup"><span data-stu-id="aca56-140">Use this statement to get the data that has been set aside for testing mining models related to a specific structure.</span></span>  
  
 <span data-ttu-id="aca56-141">**Detalhar de um padrão de modelo específico para dados de caso subjacentes**</span><span class="sxs-lookup"><span data-stu-id="aca56-141">**Drillthrough from a specific model pattern to underlying case data**</span></span>  
 `SELECT FROM <model>.CASESWHERE IsTrainingCase() AND IsInNode(<node>)`  
  
 <span data-ttu-id="aca56-142">Use esta instrução para recuperar dados de caso detalhado de um modelo treinado.</span><span class="sxs-lookup"><span data-stu-id="aca56-142">Use this statement to retrieve detailed case data from a trained model.</span></span> <span data-ttu-id="aca56-143">Você deve especificar um nó específico: por exemplo, você deve saber a ID do nó do cluster, a ramificação específica da árvore de decisão etc. Além disso, você deve ter permissões de detalhamento no modelo para executar esta consulta.</span><span class="sxs-lookup"><span data-stu-id="aca56-143">You must specify a specific node: for example, you must know the node ID of the cluster, the specific branch of the decision tree, etc. Moreover, you must have drillthrough permissions on the model to run this query.</span></span>  
  
###  <a name="queries-on-model-patterns-statistics-and-attributes"></a><a name="bkmk_Patterns"></a><span data-ttu-id="aca56-144">Consultas em padrões de modelo, estatísticas e atributos</span><span class="sxs-lookup"><span data-stu-id="aca56-144">Queries on Model Patterns, Statistics, and Attributes</span></span>  
 <span data-ttu-id="aca56-145">O conteúdo de um modelo de mineração de dados é útil para muitos propósitos.</span><span class="sxs-lookup"><span data-stu-id="aca56-145">The content of a data mining model is useful for many purposes.</span></span> <span data-ttu-id="aca56-146">Com uma consulta de conteúdo modelo, você pode:</span><span class="sxs-lookup"><span data-stu-id="aca56-146">With a model content query, you can:</span></span>  
  
-   <span data-ttu-id="aca56-147">Extrair fórmulas ou probabilidades para fazer seus próprios cálculos.</span><span class="sxs-lookup"><span data-stu-id="aca56-147">Extract formulas or probabilities for making your own calculations.</span></span>  
  
-   <span data-ttu-id="aca56-148">Para um modelo de associação, recupere as regras que são usadas para gerar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="aca56-148">For an association model, retrieve the rules that are used to generate a prediction.</span></span>  
  
-   <span data-ttu-id="aca56-149">Recuperar as descrições de regras específicas de forma que você possa usar as regras em um aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="aca56-149">Retrieve the descriptions of specific rules so that you can use the rules in a custom application.</span></span>  
  
-   <span data-ttu-id="aca56-150">Exibir as médias móveis detectadas por um modelo de série temporal.</span><span class="sxs-lookup"><span data-stu-id="aca56-150">View the moving averages detected by a time series model.</span></span>  
  
-   <span data-ttu-id="aca56-151">Obter a fórmula de regressão para algum segmento da linha de tendência.</span><span class="sxs-lookup"><span data-stu-id="aca56-151">Obtain the regression formula for some segment of the trend line.</span></span>  
  
-   <span data-ttu-id="aca56-152">Recuperar informações acionáveis sobre clientes identificados como fazendo parte de um cluster específico.</span><span class="sxs-lookup"><span data-stu-id="aca56-152">Retrieve actionable information about customers identified as being part of a specific cluster.</span></span>  
  
 <span data-ttu-id="aca56-153">Os exemplos a seguir mostram alguns dos padrões comuns para criar consultas no conteúdo do modelo:</span><span class="sxs-lookup"><span data-stu-id="aca56-153">The following examples show some of the common patterns for creating queries on the model content:</span></span>  
  
 <span data-ttu-id="aca56-154">**Obter padrões do modelo**</span><span class="sxs-lookup"><span data-stu-id="aca56-154">**Get patterns from the model**</span></span>  
 `SELECT FROM <model>.CONTENT`  
  
 <span data-ttu-id="aca56-155">Use esta instrução para recuperar informações detalhadas sobre nós específicos no modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-155">Use this statement to retrieve detailed information about specific nodes in the model.</span></span> <span data-ttu-id="aca56-156">Dependendo do tipo de algoritmo, o nó pode conter regras e fórmulas, suporte e estatísticas de variância, e assim sucessivamente.</span><span class="sxs-lookup"><span data-stu-id="aca56-156">Depending on the algorithm type, the node can contain rules and formulas, support and variance statistics, and so forth.</span></span>  
  
 <span data-ttu-id="aca56-157">**Recuperar atributos usados em um modelo treinado**</span><span class="sxs-lookup"><span data-stu-id="aca56-157">**Retrieve attributes used in a trained model**</span></span>  
 `CALL System.GetModelAttributes(<model>)`  
  
 <span data-ttu-id="aca56-158">Use este procedimento armazenado para recuperar a lista de atributos que foram usados por um modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-158">Use this stored procedure to retrieve the list of attributes that were used by a model.</span></span> <span data-ttu-id="aca56-159">Estas informações são úteis para determinar atributos que foram eliminados como resultado de seleção de recursos, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="aca56-159">This information is useful for determining attributes that were eliminated as a result of feature selection, for example.</span></span>  
  
 <span data-ttu-id="aca56-160">**Recuperar conteúdo armazenado em uma dimensão de mineração de dados**</span><span class="sxs-lookup"><span data-stu-id="aca56-160">**Retrieve content stored in a data mining dimension**</span></span>  
 `SELECT FROM <model>.DIMENSIONCONTENT`  
  
 <span data-ttu-id="aca56-161">Use esta instrução para recuperar os dados de uma dimensão de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="aca56-161">Use this statement to retrieve the data from a data mining dimension.</span></span>  
  
 <span data-ttu-id="aca56-162">Esse tipo de consulta destina-se principalmente ao uso interno.</span><span class="sxs-lookup"><span data-stu-id="aca56-162">This query type is principally for internal use.</span></span> <span data-ttu-id="aca56-163">No entanto, nem todos os algoritmos dão suporte a esta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="aca56-163">However, not all algorithms support this functionality.</span></span> <span data-ttu-id="aca56-164">O suporte é indicado por um sinalizador no conjunto de linhas do esquema MINING_SERVICES.</span><span class="sxs-lookup"><span data-stu-id="aca56-164">Support is indicated by a flag in the MINING_SERVICES schema rowset.</span></span>  
  
 <span data-ttu-id="aca56-165">Se você desenvolver seu próprio algoritmo de plug-in, pode usar esta instrução para verificar o conteúdo de seu modelo para testar.</span><span class="sxs-lookup"><span data-stu-id="aca56-165">If you develop your own plug-in algorithm, you might use this statement to verify the content of your model for testing.</span></span>  
  
 <span data-ttu-id="aca56-166">**Obtenha a representação PMML de um modelo.**</span><span class="sxs-lookup"><span data-stu-id="aca56-166">**Get the PMML representation of a model**</span></span>  
 `SELECT * FROM <model>.PMML`  
  
 <span data-ttu-id="aca56-167">Obtém um documento XML que representa o modelo em formato de PMML.</span><span class="sxs-lookup"><span data-stu-id="aca56-167">Gets an XML document that represents the model in PMML format.</span></span> <span data-ttu-id="aca56-168">Não há suporte para todos os tipos de modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-168">Not all model types are supported.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_Examples"></a> <span data-ttu-id="aca56-169">Exemplos</span><span class="sxs-lookup"><span data-stu-id="aca56-169">Examples</span></span>  
 <span data-ttu-id="aca56-170">Embora algum conteúdo de modelo seja padrão entre algoritmos, algumas partes do conteúdo variam enormemente dependendo do algoritmo usado para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-170">Although some model content is standard across algorithms, some parts of the content vary greatly depending on the algorithm that you used to build the model.</span></span> <span data-ttu-id="aca56-171">Desse modo, ao criar uma consulta de conteúdo, você precisa saber quais as informações do modelo mais úteis para seu modelo específico.</span><span class="sxs-lookup"><span data-stu-id="aca56-171">Therefore, when you create a content query, you must understand what information in the model is most useful to your specific model.</span></span>  
  
 <span data-ttu-id="aca56-172">Alguns exemplos são fornecidos nesta seção para ilustrar como a escolha de algoritmo afeta o tipo de informação que é armazenada no modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-172">A few examples are provided in this section to illustrate how the choice of algorithm affects the kind of information that is stored in the model.</span></span> <span data-ttu-id="aca56-173">Para obter mais informações sobre o conteúdo do modelo de mineração e o conteúdo específico para cada tipo de modelo, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="aca56-173">For more information about mining model content, and the content that is specific to each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
###  <a name="example-1-content-query-on-an-association-model"></a><a name="bkmk_Assoc"></a> <span data-ttu-id="aca56-174">Exemplo 1: Consulta de conteúdo em um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="aca56-174">Example 1: Content Query on an Association Model</span></span>  
 <span data-ttu-id="aca56-175">A instrução `SELECT FROM <model>.CONTENT`retorna tipos diferentes de informações, dependendo do tipo de modelo que você está consultando.</span><span class="sxs-lookup"><span data-stu-id="aca56-175">The statement, `SELECT FROM <model>.CONTENT`, returns different kinds of information, depending on the type of model you are querying.</span></span> <span data-ttu-id="aca56-176">Para um modelo de associação, uma informação importante é o *tipo de nó*.</span><span class="sxs-lookup"><span data-stu-id="aca56-176">For an association model, a key piece of information is the *node type*.</span></span> <span data-ttu-id="aca56-177">Os nós são como contêineres para informações no conteúdo do modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-177">Nodes are like containers for information in the model content.</span></span> <span data-ttu-id="aca56-178">Em um modelo de associação, os nós que representam regras têm o valor de NODE_TYPE igual a 8, enquanto os nós que representam conjuntos de itens têm um valor de NODE_TYPE igual a 7.</span><span class="sxs-lookup"><span data-stu-id="aca56-178">In an association model, nodes that represent rules have a NODE_TYPE value of 8, whereas nodes that represent itemsets have a NODE_TYPE value of 7.</span></span>  
  
 <span data-ttu-id="aca56-179">Assim, a consulta a seguir retorna os 10 principais conjuntos de itens, classificados por suporte (a ordem padrão).</span><span class="sxs-lookup"><span data-stu-id="aca56-179">Thus, the following query returns the top 10 itemsets, ranked by support (the default ordering).</span></span>  
  
```  
SELECT TOP 10 NODE_DESCRIPTION, NODE_PROBABILITY, SUPPORT  
FROM <model>.CONTENT WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="aca56-180">A consulta a seguir é criada com base nestas informações.</span><span class="sxs-lookup"><span data-stu-id="aca56-180">The following query builds on this information.</span></span> <span data-ttu-id="aca56-181">A consulta retorna três colunas: a ID do nó, a regra completa e o produto no lado direito do conjunto-ou seja, o produto que é previsto para ser associado a outros produtos como parte de um conjunto.</span><span class="sxs-lookup"><span data-stu-id="aca56-181">The query returns three columns: the ID of the node, the complete rule, and the product on the right-hand side of the itemset-that is, the product that is predicted to be associated with some other products as part of an itemset.</span></span>  
  
```  
SELECT FLATTENED NODE_UNIQUE_NAME, NODE_DESCRIPTION,  
     (SELECT RIGHT(ATTRIBUTE_NAME, (LEN(ATTRIBUTE_NAME)-LEN('Association model name')))   
FROM NODE_DISTRIBUTION  
WHERE LEN(ATTRIBUTE_NAME)>2  
)   
AS RightSideProduct  
FROM [<Association model name>].CONTENT  
WHERE NODE_TYPE = 8   
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="aca56-182">A palavra-chave FLATTENED indica que o conjunto de linhas aninhado deve ser convertido em uma tabela simples.</span><span class="sxs-lookup"><span data-stu-id="aca56-182">The FLATTENED keyword indicates that the nested rowset should be converted into a flattened table.</span></span> <span data-ttu-id="aca56-183">O atributo que representa o produto na lateral direita da regra está contido na tabela NODE_DISTRIBUTION; portanto, recuperamos somente a linha que contém um nome de atributo, adicionando um requisito para que o comprimento seja maior do que 2.</span><span class="sxs-lookup"><span data-stu-id="aca56-183">The attribute that represents the product on the right-hand side of the rule is contained in the NODE_DISTRIBUTION table; therefore, we retrieve only the row that contains an attribute name, by adding a requirement that the length be greater than 2.</span></span>  
  
 <span data-ttu-id="aca56-184">Uma função de cadeia de caracteres simples é usada para remover o nome do modelo da terceira coluna.</span><span class="sxs-lookup"><span data-stu-id="aca56-184">A simple string function is used to remove the name of the model from the third column.</span></span> <span data-ttu-id="aca56-185">(Normalmente, o nome do modelo é antecedido pelos valores de colunas aninhadas.)</span><span class="sxs-lookup"><span data-stu-id="aca56-185">(Usually the model name is prefixed to the values of nested columns.)</span></span>  
  
 <span data-ttu-id="aca56-186">A cláusula WHERE especifica que o valor de NODE_TYPE deve ser 8 para recuperar apenas regras.</span><span class="sxs-lookup"><span data-stu-id="aca56-186">The WHERE clause specifies that the value of NODE_TYPE should be 8, to retrieve only rules.</span></span>  
  
 <span data-ttu-id="aca56-187">Para ver mais exemplos, consulte [Exemplos de consulta de um modelo associação](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="aca56-187">For more examples, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
###  <a name="example-2-content-query-on-a-decision-trees-model"></a><a name="bkmk_DecTree"></a> <span data-ttu-id="aca56-188">Exemplo 2: Consulta de conteúdo em um modelo de árvores de decisão</span><span class="sxs-lookup"><span data-stu-id="aca56-188">Example 2: Content Query on a Decision Trees Model</span></span>  
 <span data-ttu-id="aca56-189">Um modelo de árvore de decisão pode ser usado para previsão e também para classificação.</span><span class="sxs-lookup"><span data-stu-id="aca56-189">A decision tree model can be used for prediction as well as for classification.</span></span>  <span data-ttu-id="aca56-190">Este exemplo presume que você esteja usando o modelo para prever um resultado, mas você também quer descobrir quais fatores ou regras podem ser usados para classificar o resultado.</span><span class="sxs-lookup"><span data-stu-id="aca56-190">This example assumes that you are using the model to predict an outcome, but you also want to find out which factors or rules can be used to classify the outcome.</span></span>  
  
 <span data-ttu-id="aca56-191">Em um modelo de árvore de decisão, os nós são usados para representar árvores e nós folha.</span><span class="sxs-lookup"><span data-stu-id="aca56-191">In a decision tree model, nodes are used to represent both trees and leaf nodes.</span></span> <span data-ttu-id="aca56-192">A legenda para cada nó contém a descrição do caminho ao resultado.</span><span class="sxs-lookup"><span data-stu-id="aca56-192">The caption for each node contains the description of the path to the outcome.</span></span> <span data-ttu-id="aca56-193">Portanto, para rastrear o caminho para qualquer resultado específico, você precisa identificar o nó que o contém e obter os detalhes para aquele nó.</span><span class="sxs-lookup"><span data-stu-id="aca56-193">Therefore, to trace the path for any particular outcome, you need to identify the node that contains it, and get the details for that node.</span></span>  
  
 <span data-ttu-id="aca56-194">Em sua consulta de previsão, você adiciona a função de previsão [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx), para obter a ID do nó relacionado, como mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="aca56-194">In your prediction query, you add the prediction function [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx), to get the ID of the related node, as shown in the following example:</span></span>  
  
```  
SELECT  Predict([Bike Buyer]), PredictNodeID([Bike Buyer])   
FROM [<decision tree model name>]  
PREDICTION JOIN   
<input rowset>   
```  
  
 <span data-ttu-id="aca56-195">Assim que você obtiver a ID do nó que contém o resultado, poderá recuperar a regra ou o caminho que explica a previsão criando uma consulta de conteúdo, que inclui NODE_CAPTION da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aca56-195">Once you have the ID of the node that contains the outcome, you can retrieve the rule or path that explains the prediction by creating a content query that includes the NODE_CAPTION, as follows:</span></span>  
  
```  
SELECT NODE_CAPTION  
FROM [<decision tree model name>]   
WHERE NODE_UNIQUE_NAME= '<node id>'  
```  
  
 <span data-ttu-id="aca56-196">Para obter mais exemplos, consulte [Exemplos de consulta de modelo de árvores de decisão](decision-trees-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="aca56-196">For more examples, see [Decision Trees Model Query Examples](decision-trees-model-query-examples.md).</span></span>  
  
##  <a name="working-with-the-query-results"></a><a name="bkmk_Results"></a><span data-ttu-id="aca56-197">Trabalhando com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="aca56-197">Working with the Query Results</span></span>  
 <span data-ttu-id="aca56-198">Como demonstram os exemplos, as consultas de conteúdo retornam principalmente conjuntos de linhas tabulares, mas também podem incluir informações de colunas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="aca56-198">As the examples demonstrate, content queries mostly return tabular rowsets, but can also include information from nested columns.</span></span> <span data-ttu-id="aca56-199">Você pode aplainar o conjunto de linhas que é retornado, mas isto pode tornar mais complexo o trabalho com resultados.</span><span class="sxs-lookup"><span data-stu-id="aca56-199">You can flatten the rowset that is returned, but this can make working with results more complex.</span></span> <span data-ttu-id="aca56-200">O conteúdo do nó NODE_DISTRIBUTION em particular está aninhado, mas contém muitas informações interessantes sobre o modelo.</span><span class="sxs-lookup"><span data-stu-id="aca56-200">The content of the NODE_DISTRIBUTION node in particular is nested, but contains much interesting information about the model.</span></span>  
  
 <span data-ttu-id="aca56-201">Para obter mais informações sobre como trabalhar com conjuntos de linhas hierárquicas, consulte a especificação OLEDB no MSDN.</span><span class="sxs-lookup"><span data-stu-id="aca56-201">For more information about how to work with hierarchical rowsets, see the OLEDB specification on MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca56-202">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aca56-202">See Also</span></span>  
 <span data-ttu-id="aca56-203">[Compreendendo a instrução DMX SELECT](/sql/dmx/understanding-the-dmx-select-statement) </span><span class="sxs-lookup"><span data-stu-id="aca56-203">[Understanding the DMX Select Statement](/sql/dmx/understanding-the-dmx-select-statement) </span></span>  
 [<span data-ttu-id="aca56-204">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="aca56-204">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
