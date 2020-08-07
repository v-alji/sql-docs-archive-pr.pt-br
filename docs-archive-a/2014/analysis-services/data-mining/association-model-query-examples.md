---
title: Exemplos de consulta de modelo de associação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- rules [Data Mining]
- association rules
- content queries [DMX]
ms.assetid: 68b39f5c-c439-44ac-8046-6f2d36649059
author: minewiskan
ms.author: owend
ms.openlocfilehash: a19eb2302639c7f13d48a8778969bbeca4fee18d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582695"
---
# <a name="association-model-query-examples"></a><span data-ttu-id="2399c-102">Exemplos de consulta de um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="2399c-102">Association Model Query Examples</span></span>
  <span data-ttu-id="2399c-103">Ao criar uma consulta em um modelo de mineração de dados, você pode criar uma consulta de conteúdo, que fornece detalhes sobre as regras e os conjuntos de itens descobertos durante a análise ou criar uma consulta de previsão, que usa as associações descobertas nos dados para fazer previsões.</span><span class="sxs-lookup"><span data-stu-id="2399c-103">When you create a query against a data mining model, you can create either a content query, which provides details about the rules and itemsets discovered during analysis, or you can create a prediction query, which uses the associations discovered in the data to make predictions.</span></span> <span data-ttu-id="2399c-104">Para um modelo de associação, normalmente, as previsões baseiam-se em regras e pode ser usadas para fazer recomendações, enquanto as consultas em conteúdo geralmente exploram a relação entre os conjuntos de itens.</span><span class="sxs-lookup"><span data-stu-id="2399c-104">For an association model, predictions typically are based on rules, and can be used to make recommendations, whereas queries on content typically explore the relationship among itemsets.</span></span> <span data-ttu-id="2399c-105">Você também pode recuperar metadados sobre o modelo.</span><span class="sxs-lookup"><span data-stu-id="2399c-105">You can also retrieve metadata about the model.</span></span>  
  
 <span data-ttu-id="2399c-106">Esta seção explica como criar esses tipos de consulta para modelos que se baseiam no algoritmo Regras de Associação da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2399c-106">This section explains how to create these kinds of queries for models that are based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span>  
  
 <span data-ttu-id="2399c-107">**Consultas de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="2399c-107">**Content Queries**</span></span>  
  
 [<span data-ttu-id="2399c-108">Obtendo dados de metadados do modelo com o DMX</span><span class="sxs-lookup"><span data-stu-id="2399c-108">Getting model metadata data by using DMX</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="2399c-109">Obtendo metadados do conjunto de linhas do esquema</span><span class="sxs-lookup"><span data-stu-id="2399c-109">Getting metadata from the schema rowset</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="2399c-110">Recuperando os parâmetros originais do modelo</span><span class="sxs-lookup"><span data-stu-id="2399c-110">Retrieving the original parameters for the model</span></span>](#bkmk_Query3)  
  
 [<span data-ttu-id="2399c-111">Recuperando uma lista de conjuntos de itens e produtos</span><span class="sxs-lookup"><span data-stu-id="2399c-111">Retrieving a list of itemsets and products</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="2399c-112">Retornando os 10 principais conjuntos de itens</span><span class="sxs-lookup"><span data-stu-id="2399c-112">Returning the top 10 itemsets</span></span>](#bkmk_Query5)  
  
 <span data-ttu-id="2399c-113">**Consultas de previsão**</span><span class="sxs-lookup"><span data-stu-id="2399c-113">**Prediction Queries**</span></span>  
  
 [<span data-ttu-id="2399c-114">Prevendo itens associados</span><span class="sxs-lookup"><span data-stu-id="2399c-114">Predicting associated items</span></span>](#bkmk_Query6)  
  
 [<span data-ttu-id="2399c-115">Determinando a confiança dos conjuntos de itens relacionados</span><span class="sxs-lookup"><span data-stu-id="2399c-115">Determining confidence for related itemsets</span></span>](#bkmk_Query7)  
  
##  <a name="finding-information-about-the-model"></a><a name="bkmk_top2"></a> <span data-ttu-id="2399c-116">Localizando informações sobre o modelo</span><span class="sxs-lookup"><span data-stu-id="2399c-116">Finding Information about the Model</span></span>  
 <span data-ttu-id="2399c-117">Todos os modelos de mineração expõem o conteúdo assimilado pelo algoritmo de acordo com um esquema padronizado, chamado de conjunto de linhas do esquema do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="2399c-117">All mining models expose the content learned by the algorithm according to a standardized schema, which is named the mining model schema rowset.</span></span> <span data-ttu-id="2399c-118">Você pode criar consultas para o conjunto de linhas do esquema do modelo de mineração usando instruções DMX (Data Mining Extensions) ou procedimentos armazenados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2399c-118">You can create queries against the mining model schema rowset either by using Data Mining Extensions (DMX) statements, or by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="2399c-119">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], você também pode consultar diretamente os conjuntos de linhas de esquema como tabelas do sistema, usando uma sintaxe similar ao SQL.</span><span class="sxs-lookup"><span data-stu-id="2399c-119">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can also query the schema rowsets directly as system tables, by using a SQL-like syntax.</span></span>  
  
###  <a name="sample-query-1-getting-model-metadata-by-using-dmx"></a><a name="bkmk_Query1"></a><span data-ttu-id="2399c-120">Exemplo de consulta 1: obtendo metadados de modelo usando DMX</span><span class="sxs-lookup"><span data-stu-id="2399c-120">Sample Query 1: Getting Model Metadata by Using DMX</span></span>  
 <span data-ttu-id="2399c-121">A consulta a seguir retorna os metadados básicos sobre o modelo de associação, `Association`, como o nome do modelo, o banco de dados onde o modelo é armazenado e o número de nós filho do modelo.</span><span class="sxs-lookup"><span data-stu-id="2399c-121">The following query returns basic metadata about the association model, `Association`, such as the name of the model, the database where the model is stored, and the number of child nodes in the model.</span></span> <span data-ttu-id="2399c-122">Esta consulta usa uma consulta de conteúdo DMX para recuperar os metadados do nó pai do modelo:</span><span class="sxs-lookup"><span data-stu-id="2399c-122">This query uses a DMX content query to retrieve the metadata from the parent node of the model:</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, NODE_CAPTION,   
NODE_SUPPORT, [CHILDREN_CARDINALITY], NODE_DESCRIPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2399c-123">É necessário colocar o nome da coluna, CHILDREN_CARDINALITY, entre colchetes para diferenciá-lo da palavra-chave reservada MDX do mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="2399c-123">You must enclose the name of the column, CHILDREN_CARDINALITY, in brackets to distinguish it from the MDX reserved keyword of the same name.</span></span>  
  
 <span data-ttu-id="2399c-124">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="2399c-124">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2399c-125">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2399c-125">MODEL_CATALOG</span></span>|<span data-ttu-id="2399c-126">Teste de Associação</span><span class="sxs-lookup"><span data-stu-id="2399c-126">Association Test</span></span>|  
|<span data-ttu-id="2399c-127">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="2399c-127">MODEL_NAME</span></span>|<span data-ttu-id="2399c-128">Associação</span><span class="sxs-lookup"><span data-stu-id="2399c-128">Association</span></span>|  
|<span data-ttu-id="2399c-129">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="2399c-129">NODE_CAPTION</span></span>|<span data-ttu-id="2399c-130">Modelo de regras de associação</span><span class="sxs-lookup"><span data-stu-id="2399c-130">Association Rules Model</span></span>|  
|<span data-ttu-id="2399c-131">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2399c-131">NODE_SUPPORT</span></span>|<span data-ttu-id="2399c-132">14879</span><span class="sxs-lookup"><span data-stu-id="2399c-132">14879</span></span>|  
|<span data-ttu-id="2399c-133">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2399c-133">CHILDREN_CARDINALITY</span></span>|<span data-ttu-id="2399c-134">942</span><span class="sxs-lookup"><span data-stu-id="2399c-134">942</span></span>|  
|<span data-ttu-id="2399c-135">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2399c-135">NODE_DESCRIPTION</span></span>|<span data-ttu-id="2399c-136">Modelo de regras de associação; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span><span class="sxs-lookup"><span data-stu-id="2399c-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span></span>|  
  
 <span data-ttu-id="2399c-137">Para obter uma definição do que essas colunas significam em um modelo de associação, consulte [Conteúdo do modelo de mineração para modelos de associação &#40;Analysis Services – Data Mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2399c-137">For a definition of what these columns mean in an association model, see [Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="2399c-138">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="2399c-138">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-2-getting-additional-metadata-from-the-schema-rowset"></a><a name="bkmk_Query2"></a> <span data-ttu-id="2399c-139">Exemplo de consulta 2: Obtendo metadados adicionais do conjunto de linhas de esquema</span><span class="sxs-lookup"><span data-stu-id="2399c-139">Sample Query 2: Getting Additional Metadata from the Schema Rowset</span></span>  
 <span data-ttu-id="2399c-140">É possível consultar o conjunto de linhas de esquema de mineração de dados para encontrar as mesmas informações retornadas em uma consulta de conteúdo DMX.</span><span class="sxs-lookup"><span data-stu-id="2399c-140">By querying the data mining schema rowset, you can find the same information that is returned in a DMX content query.</span></span> <span data-ttu-id="2399c-141">No entanto, o conjunto de linhas de esquema fornece algumas colunas adicionais, como a data em que o modelo foi processado, a estrutura de mineração e o nome da coluna usada como atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="2399c-141">However, the schema rowset provides some additional columns, such as the date the model was last processed, the mining structure, and the name of the column used as the predictable attribute.</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, SERVICE_NAME, PREDICTION_ENTITY,   
MINING_STRUCTURE, LAST_PROCESSED  
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="2399c-142">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="2399c-142">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2399c-143">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2399c-143">MODEL_CATALOG</span></span>|<span data-ttu-id="2399c-144">Adventure Works DW Multidimensional 2012</span><span class="sxs-lookup"><span data-stu-id="2399c-144">Adventure Works DW Multidimensional 2012</span></span>|  
|<span data-ttu-id="2399c-145">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="2399c-145">MODEL_NAME</span></span>|<span data-ttu-id="2399c-146">Associação</span><span class="sxs-lookup"><span data-stu-id="2399c-146">Association</span></span>|  
|<span data-ttu-id="2399c-147">SERVICE_NAME</span><span class="sxs-lookup"><span data-stu-id="2399c-147">SERVICE_NAME</span></span>|<span data-ttu-id="2399c-148">Modelo de regras de associação</span><span class="sxs-lookup"><span data-stu-id="2399c-148">Association Rules Model</span></span>|  
|<span data-ttu-id="2399c-149">PREDICTION_ENTITY</span><span class="sxs-lookup"><span data-stu-id="2399c-149">PREDICTION_ENTITY</span></span>|<span data-ttu-id="2399c-150">v Assoc Seq Line Items</span><span class="sxs-lookup"><span data-stu-id="2399c-150">v Assoc Seq Line Items</span></span>|  
|<span data-ttu-id="2399c-151">MINING_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="2399c-151">MINING_STRUCTURE</span></span>|<span data-ttu-id="2399c-152">Associação</span><span class="sxs-lookup"><span data-stu-id="2399c-152">Association</span></span>|  
|<span data-ttu-id="2399c-153">LAST_PROCESSED</span><span class="sxs-lookup"><span data-stu-id="2399c-153">LAST_PROCESSED</span></span>|<span data-ttu-id="2399c-154">9/29/2007 10:21:24 PM</span><span class="sxs-lookup"><span data-stu-id="2399c-154">9/29/2007 10:21:24 PM</span></span>|  
  
 [<span data-ttu-id="2399c-155">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="2399c-155">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-3-retrieving-original-parameters-for-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="2399c-156">Exemplo de consulta 3: Recuperando parâmetros originais do modelo</span><span class="sxs-lookup"><span data-stu-id="2399c-156">Sample Query 3: Retrieving Original Parameters for Model</span></span>  
 <span data-ttu-id="2399c-157">A consulta a seguir retorna uma única coluna que contém detalhes sobre as configurações de parâmetros que foram usados na criação do modelo.</span><span class="sxs-lookup"><span data-stu-id="2399c-157">The following query returns a single column that contains details about the parameter settings that were used when the model was created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
from $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="2399c-158">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="2399c-158">Example results:</span></span>  
  
 <span data-ttu-id="2399c-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span><span class="sxs-lookup"><span data-stu-id="2399c-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span></span>  
  
 [<span data-ttu-id="2399c-160">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="2399c-160">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="finding-information-about-rules-and-itemsets"></a><span data-ttu-id="2399c-161">Localizando informações sobre regras e conjuntos de itens</span><span class="sxs-lookup"><span data-stu-id="2399c-161">Finding Information about Rules and Itemsets</span></span>  
 <span data-ttu-id="2399c-162">Existem dois usos comuns para um modelo de associação: descobrir informações sobre conjuntos de itens frequentes e extrair detalhes sobre regras e conjuntos de itens específicos.</span><span class="sxs-lookup"><span data-stu-id="2399c-162">There are two common uses of an association model: to discover information about frequent itemsets, and to extract details about particular rules and itemsets.</span></span> <span data-ttu-id="2399c-163">Por exemplo, convém extrair uma lista de regras cuja pontuação indicou serem especialmente interessantes ou criar uma lista dos conjuntos de itens mais comuns.</span><span class="sxs-lookup"><span data-stu-id="2399c-163">For example, you might want to extract a list of rules that were scored as being especially interesting, or create a list of the most common itemsets.</span></span> <span data-ttu-id="2399c-164">Para recuperar essas informações, use uma consulta de conteúdo DMX.</span><span class="sxs-lookup"><span data-stu-id="2399c-164">You retrieve such information by using a DMX content query.</span></span> <span data-ttu-id="2399c-165">Você também procura essas informações usando o **Visualizador de Associação da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="2399c-165">You can also browse this information by using the **Microsoft Association Viewer**.</span></span>  
  
###  <a name="sample-query-4-retrieving-list-of-itemsets-and-products"></a><a name="bkmk_Query4"></a> <span data-ttu-id="2399c-166">Exemplo de consulta 4: Recuperando a lista de conjuntos de itens e produtos</span><span class="sxs-lookup"><span data-stu-id="2399c-166">Sample Query 4: Retrieving List of Itemsets and Products</span></span>  
 <span data-ttu-id="2399c-167">A consulta a seguir recupera todos os conjuntos de itens com uma tabela aninhada que lista os produtos incluídos em cada conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="2399c-167">The following query retrieves all of the itemsets, together with a nested table that lists the products included in each itemset.</span></span> <span data-ttu-id="2399c-168">A coluna NODE_NAME contém a ID exclusiva do conjunto de itens do modelo, enquanto NODE_CAPTION fornece um texto que descreve os itens.</span><span class="sxs-lookup"><span data-stu-id="2399c-168">The NODE_NAME column contains the unique ID of the itemset within the model, whereas the NODE_CAPTION provides a text description of the items.</span></span> <span data-ttu-id="2399c-169">Nesse exemplo, a tabela aninhada é simplificada, de modo que o conjunto de itens que contém dois produtos irá gerar duas linhas nos resultados.</span><span class="sxs-lookup"><span data-stu-id="2399c-169">In this example, the nested table is flattened, so that an itemset that contains two products generates two rows in the results.</span></span> <span data-ttu-id="2399c-170">É possível omitir a palavra-chave FLATTENED se o cliente oferecer suporte a dados hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="2399c-170">You can omit the FLATTENED keyword if your client supports hierarchical data.</span></span>  
  
```  
SELECT FLATTENED NODE_NAME, NODE_CAPTION,  
NODE_PROBABILITY, NODE_SUPPORT,  
(SELECT ATTRIBUTE_NAME FROM NODE_DISTRIBUTION) as PurchasedProducts  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="2399c-171">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="2399c-171">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2399c-172">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="2399c-172">NODE_NAME</span></span>|<span data-ttu-id="2399c-173">37</span><span class="sxs-lookup"><span data-stu-id="2399c-173">37</span></span>|  
|<span data-ttu-id="2399c-174">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="2399c-174">NODE_CAPTION</span></span>|<span data-ttu-id="2399c-175">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="2399c-175">Sport-100 = Existing</span></span>|  
|<span data-ttu-id="2399c-176">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="2399c-176">NODE_PROBABILITY</span></span>|<span data-ttu-id="2399c-177">0.291283016331743</span><span class="sxs-lookup"><span data-stu-id="2399c-177">0.291283016331743</span></span>|  
|<span data-ttu-id="2399c-178">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2399c-178">NODE_SUPPORT</span></span>|<span data-ttu-id="2399c-179">4334</span><span class="sxs-lookup"><span data-stu-id="2399c-179">4334</span></span>|  
|<span data-ttu-id="2399c-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="2399c-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="2399c-181">v Assoc Seq Line Items(Sport-100)</span><span class="sxs-lookup"><span data-stu-id="2399c-181">v Assoc Seq Line Items(Sport-100)</span></span>|  
  
 [<span data-ttu-id="2399c-182">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="2399c-182">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-5-returning-top-10-itemsets"></a><a name="bkmk_Query5"></a> <span data-ttu-id="2399c-183">Exemplo de consulta 5: Retornando os 10 principais conjuntos de itens</span><span class="sxs-lookup"><span data-stu-id="2399c-183">Sample Query 5: Returning Top 10 Itemsets</span></span>  
 <span data-ttu-id="2399c-184">Este exemplo demonstra como usar parte das funções de agrupamento e ordenação que o DMX fornece por padrão.</span><span class="sxs-lookup"><span data-stu-id="2399c-184">This example demonstrates how to use some of the grouping and ordering functions that DMX provides by default.</span></span> <span data-ttu-id="2399c-185">A consulta retorna os 10 principais conjuntos de itens quando ordenada pelo suporte de cada nó.</span><span class="sxs-lookup"><span data-stu-id="2399c-185">The query returns the top 10 itemsets when ordered by the support for each node.</span></span> <span data-ttu-id="2399c-186">Observe que não é necessário agrupar explicitamente os resultados como se fosse o Transact-SQL; no entanto, você pode usar apenas uma função de agregação em cada consulta.</span><span class="sxs-lookup"><span data-stu-id="2399c-186">Note that you do not need to explicitly group the results, as you would in Transact-SQL; however, you can use only one aggregate function in each query.</span></span>  
  
```  
SELECT TOP 10 (NODE_SUPPORT),NODE_NAME, NODE_CAPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="2399c-187">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="2399c-187">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2399c-188">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2399c-188">NODE_SUPPORT</span></span>|<span data-ttu-id="2399c-189">4334</span><span class="sxs-lookup"><span data-stu-id="2399c-189">4334</span></span>|  
|<span data-ttu-id="2399c-190">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="2399c-190">NODE_NAME</span></span>|<span data-ttu-id="2399c-191">37</span><span class="sxs-lookup"><span data-stu-id="2399c-191">37</span></span>|  
|<span data-ttu-id="2399c-192">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="2399c-192">NODE_CAPTION</span></span>|<span data-ttu-id="2399c-193">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="2399c-193">Sport-100 = Existing</span></span>|  
  
 [<span data-ttu-id="2399c-194">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="2399c-194">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="making-predictions-using-the-model"></a><span data-ttu-id="2399c-195">Fazendo predições com o modelo</span><span class="sxs-lookup"><span data-stu-id="2399c-195">Making Predictions using the Model</span></span>  
 <span data-ttu-id="2399c-196">Um modelo de regras de associação é usado frequentemente para gerar recomendações que se baseiam em correlações descobertas nos conjuntos de itens.</span><span class="sxs-lookup"><span data-stu-id="2399c-196">An association rules model is often used to generate recommendations, which are based on correlations discovered in the itemsets.</span></span> <span data-ttu-id="2399c-197">Portanto, quando você cria uma consulta de previsão com base em um modelo de regras de associação, está normalmente usando as regras no modelo fazer suposições com base em novos dados.</span><span class="sxs-lookup"><span data-stu-id="2399c-197">Therefore, when you create a prediction query based on an association rules model, you are typically using the rules in the model to make guesses based on new data.</span></span>  <span data-ttu-id="2399c-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) é a função que retorna recomendações e tem vários argumentos que você pode usar para personalizar os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="2399c-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) is the function that returns recommendations, and has several arguments that you can use to customize the query results.</span></span>  
  
 <span data-ttu-id="2399c-199">Outro exemplo de onde as consultas em um modelo de associação podem ser úteis é para retornar a confiança de várias regras e conjuntos de itens para que você possa comparar a eficiência de estratégias diferentes de venda cruzada.</span><span class="sxs-lookup"><span data-stu-id="2399c-199">Another example of where queries on an association model might be useful is to return the confidence for various rules and itemsets so that you can compare the effectiveness of different cross-sell strategies.</span></span> <span data-ttu-id="2399c-200">Os exemplos seguintes ilustram como criar essas consultas.</span><span class="sxs-lookup"><span data-stu-id="2399c-200">The following examples illustrate how to create such queries.</span></span>  
  
###  <a name="sample-query-6-predicting-associated-items"></a><a name="bkmk_Query6"></a> <span data-ttu-id="2399c-201">Exemplo de consulta 6: Prevendo itens associados</span><span class="sxs-lookup"><span data-stu-id="2399c-201">Sample Query 6: Predicting Associated Items</span></span>  
 <span data-ttu-id="2399c-202">Este exemplo usa o modelo de associação criado no [Tutorial de mineração de dados intermediário &#40;Analysis Services – Mineração de Dados&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2399c-202">This example uses the Association model created in the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="2399c-203">Ele demonstra como criar uma consulta de previsão que informa quais produtos recomendar para um cliente que comprou um determinado produto.</span><span class="sxs-lookup"><span data-stu-id="2399c-203">It demonstrates how to create a prediction query that tells you what products to recommend to a customer who has purchased a particular product.</span></span> <span data-ttu-id="2399c-204">Esse tipo de consulta, em que você fornece valores para o modelo em uma instrução `SELECT...UNION`, é chamada de consulta singleton.</span><span class="sxs-lookup"><span data-stu-id="2399c-204">This type of query, where you provide values to the model in a `SELECT...UNION` statement, is called a singleton query.</span></span> <span data-ttu-id="2399c-205">Como a coluna de modelo previsível que corresponde aos novos valores é uma tabela aninhada, use uma cláusula `SELECT` para mapear o novo valor à coluna da tabela aninhada, `[Model]`, e outra cláusula `SELECT` para mapear a coluna da tabela aninhada à coluna de nível de caso, `[v Assoc Seq Line Items]`.</span><span class="sxs-lookup"><span data-stu-id="2399c-205">Because the predictable model column that corresponds to the new values is a nested table, you must use one `SELECT` clause to map the new value to the nested table column, `[Model]`, and another `SELECT` clause to map the nested table column to the case-level column, `[v Assoc Seq Line Items]`.</span></span> <span data-ttu-id="2399c-206">Adicionar a palavra-chave INCLUDE-STATISTICS à consulta permitirá que você veja a probabilidade e o suporte das recomendações.</span><span class="sxs-lookup"><span data-stu-id="2399c-206">Adding the keyword INCLUDE-STATISTICS to the query lets you see the probability and support for the recommendations.</span></span>  
  
```  
SELECT PredictAssociation([Association].[vAssocSeqLineItems],INCLUDE_STATISTICS, 3)  
FROM [Association]  
NATURAL PREDICTION JOIN   
(SELECT  
(SELECT 'Classic Vest' as [Model])  
AS [v Assoc Seq Line Items])  
AS t  
```  
  
 <span data-ttu-id="2399c-207">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="2399c-207">Example results:</span></span>  
  
|<span data-ttu-id="2399c-208">Modelo</span><span class="sxs-lookup"><span data-stu-id="2399c-208">Model</span></span>|<span data-ttu-id="2399c-209">$SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2399c-209">$SUPPORT</span></span>|<span data-ttu-id="2399c-210">$PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="2399c-210">$PROBABILITY</span></span>|<span data-ttu-id="2399c-211">$ADJUSTEDPROBABILITY</span><span class="sxs-lookup"><span data-stu-id="2399c-211">$ADJUSTEDPROBABILITY</span></span>|  
|-----------|--------------|------------------|--------------------------|  
|<span data-ttu-id="2399c-212">Sport-100</span><span class="sxs-lookup"><span data-stu-id="2399c-212">Sport-100</span></span>|<span data-ttu-id="2399c-213">4334</span><span class="sxs-lookup"><span data-stu-id="2399c-213">4334</span></span>|<span data-ttu-id="2399c-214">0.291283</span><span class="sxs-lookup"><span data-stu-id="2399c-214">0.291283</span></span>|<span data-ttu-id="2399c-215">0.252696</span><span class="sxs-lookup"><span data-stu-id="2399c-215">0.252696</span></span>|  
|<span data-ttu-id="2399c-216">Water Bottle</span><span class="sxs-lookup"><span data-stu-id="2399c-216">Water Bottle</span></span>|<span data-ttu-id="2399c-217">2866</span><span class="sxs-lookup"><span data-stu-id="2399c-217">2866</span></span>|<span data-ttu-id="2399c-218">0.19262</span><span class="sxs-lookup"><span data-stu-id="2399c-218">0.19262</span></span>|<span data-ttu-id="2399c-219">0.175205</span><span class="sxs-lookup"><span data-stu-id="2399c-219">0.175205</span></span>|  
|<span data-ttu-id="2399c-220">Patch kit</span><span class="sxs-lookup"><span data-stu-id="2399c-220">Patch kit</span></span>|<span data-ttu-id="2399c-221">2113</span><span class="sxs-lookup"><span data-stu-id="2399c-221">2113</span></span>|<span data-ttu-id="2399c-222">0.142012</span><span class="sxs-lookup"><span data-stu-id="2399c-222">0.142012</span></span>|<span data-ttu-id="2399c-223">0.132389</span><span class="sxs-lookup"><span data-stu-id="2399c-223">0.132389</span></span>|  
  
 [<span data-ttu-id="2399c-224">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="2399c-224">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-7-determining-confidence-for-related-itemsets"></a><a name="bkmk_Query7"></a> <span data-ttu-id="2399c-225">Exemplo de consulta 7: Determinando a confiança dos conjuntos de itens relacionados</span><span class="sxs-lookup"><span data-stu-id="2399c-225">Sample Query 7: Determining Confidence for Related Itemsets</span></span>  
 <span data-ttu-id="2399c-226">Embora as regras sejam úteis para gerar recomendações, os conjuntos de itens são mais interessantes para uma análise mais profunda dos padrões no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="2399c-226">Whereas rules are useful for generating recommendations, itemsets are more interesting for deeper analysis of the patterns in the data set.</span></span> <span data-ttu-id="2399c-227">Por exemplo, se você não ficar satisfeito com a recomendação retornada pelo exemplo de consulta anterior, pode examinar outros conjuntos de itens que contêm Product A para poder ter uma ideia melhor se Product A é um acessório que as pessoas tendem a comprar com todos os tipos de produtos ou se A é fortemente correlacionado às compras de determinados produtos.</span><span class="sxs-lookup"><span data-stu-id="2399c-227">For example, if you were not satisfied with the recommendation that are returned by the previous sample query, you could examine other itemsets that contain Product A, to can get a better idea of whether Product A is an accessory that people tend to buy with all kinds of products, or whether A is strongly correlated with purchases of particular products.</span></span> <span data-ttu-id="2399c-228">A forma mais fácil de explorar essas relações é filtrando os conjuntos de itens no Visualizador de Associação da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ; no entanto, é possível recuperar as mesmas informações com um consulta.</span><span class="sxs-lookup"><span data-stu-id="2399c-228">The easiest way to explore these relationships is by filtering the itemsets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Viewer; however, you can retrieve the same information with a query.</span></span>  
  
 <span data-ttu-id="2399c-229">O exemplo de consulta a seguir retorna todos os conjuntos de itens que incluem o item Garrafa de Água, inclusive o item único Garrafa de água.</span><span class="sxs-lookup"><span data-stu-id="2399c-229">The following sample query returns all itemsets that include the Water Bottle item, including the single item Water bottle.</span></span>  
  
```  
SELECT TOP 100 FROM   
(  
SELECT FLATTENED NODE_CAPTION, NODE_SUPPORT,   
(SELECT ATTRIBUTE_NAME from NODE_DISTRIBUTION  
WHERE ATTRIBUTE_NAME = 'v Assoc Seq Line Items(Water Bottle)') as D  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
) AS Items  
WHERE [D.ATTRIBUTE_NAME] <> NULL  
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="2399c-230">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="2399c-230">Example results:</span></span>  
  
|<span data-ttu-id="2399c-231">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="2399c-231">NODE_CAPTION</span></span>|<span data-ttu-id="2399c-232">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2399c-232">NODE_SUPPORT</span></span>|<span data-ttu-id="2399c-233">D.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="2399c-233">D.ATTRIBUTE_NAME</span></span>|  
|-------------------|-------------------|-----------------------|  
|<span data-ttu-id="2399c-234">Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="2399c-234">Water Bottle = Existing</span></span>|<span data-ttu-id="2399c-235">2866</span><span class="sxs-lookup"><span data-stu-id="2399c-235">2866</span></span>|<span data-ttu-id="2399c-236">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="2399c-236">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="2399c-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="2399c-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="2399c-238">1136</span><span class="sxs-lookup"><span data-stu-id="2399c-238">1136</span></span>|<span data-ttu-id="2399c-239">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="2399c-239">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="2399c-240">Road Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="2399c-240">Road Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="2399c-241">1068</span><span class="sxs-lookup"><span data-stu-id="2399c-241">1068</span></span>|<span data-ttu-id="2399c-242">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="2399c-242">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="2399c-243">Water Bottle = Existing, Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="2399c-243">Water Bottle = Existing, Sport-100 = Existing</span></span>|<span data-ttu-id="2399c-244">734</span><span class="sxs-lookup"><span data-stu-id="2399c-244">734</span></span>|<span data-ttu-id="2399c-245">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="2399c-245">v Assoc Seq Line Items(Water Bottle)</span></span>|  
  
 <span data-ttu-id="2399c-246">Essa consulta retorna as duas linhas da tabela aninhada que correspondem aos critérios e todas as linhas da tabela de casos ou externa.</span><span class="sxs-lookup"><span data-stu-id="2399c-246">This query returns both the rows from the nested table that match the criteria, and all the rows from the outside or case table.</span></span> <span data-ttu-id="2399c-247">Portanto, adicione uma condição que elimine as linhas da tabela de casos que tiverem um valor nulo para o nome do atributo de destino.</span><span class="sxs-lookup"><span data-stu-id="2399c-247">Therefore, you must add a condition that eliminates the case table rows that have a null value for the target attribute name.</span></span>  
  
 [<span data-ttu-id="2399c-248">Retornar ao início</span><span class="sxs-lookup"><span data-stu-id="2399c-248">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="function-list"></a><span data-ttu-id="2399c-249">Lista de funções</span><span class="sxs-lookup"><span data-stu-id="2399c-249">Function List</span></span>  
 <span data-ttu-id="2399c-250">Todos os algoritmos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] dão suporte a um conjunto comum de funções.</span><span class="sxs-lookup"><span data-stu-id="2399c-250">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="2399c-251">Entretanto, o algoritmo Associação da [!INCLUDE[msCoName](../../includes/msconame-md.md)] oferece suporte para funções adicionais relacionadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="2399c-251">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2399c-252">Função de previsão</span><span class="sxs-lookup"><span data-stu-id="2399c-252">Prediction Function</span></span>|<span data-ttu-id="2399c-253">Uso</span><span class="sxs-lookup"><span data-stu-id="2399c-253">Usage</span></span>|  
|[<span data-ttu-id="2399c-254">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-254">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="2399c-255">Determina se um nó é um filho de outro nó no gráfico de rede neural.</span><span class="sxs-lookup"><span data-stu-id="2399c-255">Determines whether one node is a child of another node in the neural network graph.</span></span>|  
|[<span data-ttu-id="2399c-256">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-256">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="2399c-257">Indica se o nó especificado contém o caso atual.</span><span class="sxs-lookup"><span data-stu-id="2399c-257">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="2399c-258">PredictAdjustedProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-258">PredictAdjustedProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictadjustedprobability-dmx)|<span data-ttu-id="2399c-259">Retorna a probabilidade ponderada.</span><span class="sxs-lookup"><span data-stu-id="2399c-259">Returns the weighted probability.</span></span>|  
|[<span data-ttu-id="2399c-260">PredictAssociation &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-260">PredictAssociation &#40;DMX&#41;</span></span>](/sql/dmx/predictassociation-dmx)|<span data-ttu-id="2399c-261">Prevê associação de membro em um conjunto de dados associativo.</span><span class="sxs-lookup"><span data-stu-id="2399c-261">Predicts membership in an associative dataset.</span></span>|  
|[<span data-ttu-id="2399c-262">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-262">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="2399c-263">Retorna uma tabela de valores relacionados ao valor previsto atual.</span><span class="sxs-lookup"><span data-stu-id="2399c-263">Returns a table of values related to the current predicted value.</span></span>|  
|[<span data-ttu-id="2399c-264">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-264">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="2399c-265">Retorna Node_ID para cada caso.</span><span class="sxs-lookup"><span data-stu-id="2399c-265">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="2399c-266">PredictProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-266">PredictProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictprobability-dmx)|<span data-ttu-id="2399c-267">Retorna a probabilidade para o valor previsto.</span><span class="sxs-lookup"><span data-stu-id="2399c-267">Returns probability for the predicted value.</span></span>|  
|[<span data-ttu-id="2399c-268">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-268">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="2399c-269">Retorna o valor de suporte para um estado especificado.</span><span class="sxs-lookup"><span data-stu-id="2399c-269">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="2399c-270">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-270">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="2399c-271">Retorna a variância para o valor previsto.</span><span class="sxs-lookup"><span data-stu-id="2399c-271">Returns variance for the predicted value.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2399c-272">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2399c-272">See Also</span></span>  
 <span data-ttu-id="2399c-273">[Algoritmo de associação da Microsoft](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="2399c-273">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 <span data-ttu-id="2399c-274">[Referência técnica do algoritmo de associação da Microsoft](microsoft-association-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2399c-274">[Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="2399c-275">Conteúdo do modelo de mineração para modelos de associação &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="2399c-275">Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-association-models-analysis-services-data-mining.md)  
  
  
