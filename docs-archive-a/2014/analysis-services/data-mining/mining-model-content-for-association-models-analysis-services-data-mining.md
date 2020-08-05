---
title: Conteúdo do modelo de mineração para modelos de associação (Analysis Services-Mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- mining model content, association models
- rules [Data Mining]
- associations [Analysis Services]
ms.assetid: d5849bcb-4b8f-4f71-9761-7dc5bb465224
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8904ce155526aee595db19094fd2bad48770e83e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572838"
---
# <a name="mining-model-content-for-association-models-analysis-services---data-mining"></a><span data-ttu-id="e96e4-102">Conteúdo do modelo de mineração para modelos de associação (Analysis Services – Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="e96e4-102">Mining Model Content for Association Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="e96e4-103">Este tópico descreve o conteúdo do modelo de mineração específico para modelos que usam o algoritmo Regras de Associação da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e96e4-103">This topic describes mining model content that is specific to models that use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span> <span data-ttu-id="e96e4-104">Para obter uma explicação sobre a terminologia geral e estatística relacionada ao conteúdo do modelo de mineração que se aplica a todos os tipos de modelo, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="e96e4-104">For an explanation of general and statistical terminology related to mining model content that applies to all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-an-association-model"></a><span data-ttu-id="e96e4-105">Entendendo a estrutura de um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="e96e4-105">Understanding the Structure of an Association Model</span></span>  
 <span data-ttu-id="e96e4-106">Um modelo de associação tem uma estrutura simples.</span><span class="sxs-lookup"><span data-stu-id="e96e4-106">An association model has a simple structure.</span></span> <span data-ttu-id="e96e4-107">Cada modelo tem um único nó pai que representa o modelo e seus metadados, e cada nó pai possui uma lista simples de conjuntos de itens e regras.</span><span class="sxs-lookup"><span data-stu-id="e96e4-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of itemsets and rules.</span></span> <span data-ttu-id="e96e4-108">Os conjuntos de itens e as regras não são organizados em árvores, são ordenados com os conjuntos de itens primeiro e depois as regras, como mostra o diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="e96e4-108">The itemsets and rules are not organized in trees, they are ordered with itemsets first and rules next as shown in the following diagram.</span></span>  
  
 <span data-ttu-id="e96e4-109">![estrutura de conteúdo do modelo para modelos de associação](../media/modelcontentstructure-assoc.gif "estrutura de conteúdo do modelo para modelos de associação")</span><span class="sxs-lookup"><span data-stu-id="e96e4-109">![structure of model content for association models](../media/modelcontentstructure-assoc.gif "structure of model content for association models")</span></span>  
  
 <span data-ttu-id="e96e4-110">Cada conjunto de item é contido em seu próprio nó (NODE_TYPE = 7).</span><span class="sxs-lookup"><span data-stu-id="e96e4-110">Each itemset is contained in its own node (NODE_TYPE = 7).</span></span> <span data-ttu-id="e96e4-111">O *nó* inclui a definição do conjunto de itens, o número de casos que contém esse conjunto de itens e outras informações.</span><span class="sxs-lookup"><span data-stu-id="e96e4-111">The *node* includes the definition of the itemset, the number of cases that contain this itemset, and other information.</span></span>  
  
 <span data-ttu-id="e96e4-112">Cada regra também é contida em seu próprio nó (NODE_TYPE = 8).</span><span class="sxs-lookup"><span data-stu-id="e96e4-112">Each rule is also contained in its own node (NODE_TYPE = 8).</span></span> <span data-ttu-id="e96e4-113">Uma *regra* descreve um padrão geral de como os itens são associados.</span><span class="sxs-lookup"><span data-stu-id="e96e4-113">A *rule* describes a general pattern for how items are associated.</span></span> <span data-ttu-id="e96e4-114">Uma regra é como uma instrução IF-THEN.</span><span class="sxs-lookup"><span data-stu-id="e96e4-114">A rule is like an IF-THEN statement.</span></span> <span data-ttu-id="e96e4-115">O lado esquerdo da regra mostra uma condição existente ou um conjunto de condições.</span><span class="sxs-lookup"><span data-stu-id="e96e4-115">The left-hand side of the rule shows an existing condition or set of conditions.</span></span> <span data-ttu-id="e96e4-116">O lado direito da regra mostra o item em seu conjunto de dados que geralmente é associado às condições à esquerda.</span><span class="sxs-lookup"><span data-stu-id="e96e4-116">The right-hand side of the rule shows the item in your data set that is usually associated with the conditions on the left side.</span></span>  
  
 <span data-ttu-id="e96e4-117">**Observação** Para extrair regras ou conjuntos de itens, você pode usar uma consulta para retornar somente os tipos de nós desejados.</span><span class="sxs-lookup"><span data-stu-id="e96e4-117">**Note** If you want to extract either the rules or the itemsets, you can use a query to return only the node types that you want.</span></span> <span data-ttu-id="e96e4-118">Para obter mais informações, consulte [Exemplos de consulta de um modelo associação](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e96e4-118">For more information, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
## <a name="model-content-for-an-association-model"></a><span data-ttu-id="e96e4-119">Conteúdo de um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="e96e4-119">Model Content for an Association Model</span></span>  
 <span data-ttu-id="e96e4-120">Esta seção fornece detalhes e exemplos somente para as colunas de conteúdo do modelo de mineração que são relevantes para os modelos de associação.</span><span class="sxs-lookup"><span data-stu-id="e96e4-120">This section provides detail and examples only for those columns in the mining model content that are relevant for association models.</span></span>  
  
 <span data-ttu-id="e96e4-121">Para obter informações sobre as colunas de uso general no conjunto de linhas de esquema, como MODEL_CATALOG e MODEL_NAME, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="e96e4-121">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="e96e4-122">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e96e4-122">MODEL_CATALOG</span></span>  
 <span data-ttu-id="e96e4-123">Nome do banco de dados no qual o modelo é armazenado.</span><span class="sxs-lookup"><span data-stu-id="e96e4-123">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="e96e4-124">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="e96e4-124">MODEL_NAME</span></span>  
 <span data-ttu-id="e96e4-125">Nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-125">Name of the model.</span></span>  
  
 <span data-ttu-id="e96e4-126">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="e96e4-126">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="e96e4-127">Os nomes dos atributos que correspondem a este nó.</span><span class="sxs-lookup"><span data-stu-id="e96e4-127">The names of the attributes that correspond to this node.</span></span>  
  
 <span data-ttu-id="e96e4-128">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="e96e4-128">NODE_NAME</span></span>  
 <span data-ttu-id="e96e4-129">O nome do nó.</span><span class="sxs-lookup"><span data-stu-id="e96e4-129">The name of the node.</span></span> <span data-ttu-id="e96e4-130">Em um modelo de associação, essa coluna contém o mesmo valor que NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="e96e4-130">For an association model, this column contains the same value as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="e96e4-131">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="e96e4-131">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="e96e4-132">Nome exclusivo do nó.</span><span class="sxs-lookup"><span data-stu-id="e96e4-132">The unique name of the node.</span></span>  
  
 <span data-ttu-id="e96e4-133">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e96e4-133">NODE_TYPE</span></span>  
 <span data-ttu-id="e96e4-134">O modelo de associação produz apenas os seguintes tipos de nó:</span><span class="sxs-lookup"><span data-stu-id="e96e4-134">A association model outputs only the following node types:</span></span>  
  
|<span data-ttu-id="e96e4-135">ID do tipo de nó</span><span class="sxs-lookup"><span data-stu-id="e96e4-135">Node Type ID</span></span>|<span data-ttu-id="e96e4-136">Type</span><span class="sxs-lookup"><span data-stu-id="e96e4-136">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="e96e4-137">1 (Modelo)</span><span class="sxs-lookup"><span data-stu-id="e96e4-137">1 (Model)</span></span>|<span data-ttu-id="e96e4-138">Raiz ou nó pai.</span><span class="sxs-lookup"><span data-stu-id="e96e4-138">Root or parent node.</span></span>|  
|<span data-ttu-id="e96e4-139">7 (Conjunto de itens)</span><span class="sxs-lookup"><span data-stu-id="e96e4-139">7 (Itemset)</span></span>|<span data-ttu-id="e96e4-140">Um conjunto de itens ou coleção de pares atributo-valor.</span><span class="sxs-lookup"><span data-stu-id="e96e4-140">An itemset, or collection of attribute-value pairs.</span></span> <span data-ttu-id="e96e4-141">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="e96e4-141">Examples:</span></span><br /><br /> `Product 1 = Existing, Product 2 = Existing`<br /><br /> <span data-ttu-id="e96e4-142">ou o</span><span class="sxs-lookup"><span data-stu-id="e96e4-142">or</span></span><br /><br /> <span data-ttu-id="e96e4-143">`Gender = Male`.</span><span class="sxs-lookup"><span data-stu-id="e96e4-143">`Gender = Male`.</span></span>|  
|<span data-ttu-id="e96e4-144">8 (Regra)</span><span class="sxs-lookup"><span data-stu-id="e96e4-144">8 (Rule)</span></span>|<span data-ttu-id="e96e4-145">Uma regra que define como itens relacionam-se entre si.</span><span class="sxs-lookup"><span data-stu-id="e96e4-145">A rule defining how items relate to each other.</span></span><br /><br /> <span data-ttu-id="e96e4-146">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="e96e4-146">Example:</span></span><br /><br /> <span data-ttu-id="e96e4-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span><span class="sxs-lookup"><span data-stu-id="e96e4-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span></span>|  
  
 <span data-ttu-id="e96e4-148">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="e96e4-148">NODE_CAPTION</span></span>  
 <span data-ttu-id="e96e4-149">Um rótulo ou uma legenda associada ao nó.</span><span class="sxs-lookup"><span data-stu-id="e96e4-149">A label or a caption associated with the node.</span></span>  
  
 <span data-ttu-id="e96e4-150">**Nó do conjunto de itens** Uma lista de itens separada por vírgula.</span><span class="sxs-lookup"><span data-stu-id="e96e4-150">**Itemset node** A comma-separated list of items.</span></span>  
  
 <span data-ttu-id="e96e4-151">**Nó de regra** Contém os lados esquerdo e direito da regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-151">**Rule node** Contains the left and right-hand sides of the rule.</span></span>  
  
 <span data-ttu-id="e96e4-152">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e96e4-152">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="e96e4-153">Indica o número de filhos do nó atual.</span><span class="sxs-lookup"><span data-stu-id="e96e4-153">Indicates the number of children of the current node.</span></span>  
  
 <span data-ttu-id="e96e4-154">**Nó pai** Indica o número total de conjuntos de itens mais regras.</span><span class="sxs-lookup"><span data-stu-id="e96e4-154">**Parent node** Indicates the total number of itemsets plus rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e96e4-155">Para obter uma análise da contagem de conjuntos de itens e regras, consulte NODE_DESCRIPTION do nó raiz do modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-155">To get a breakdown of the count for itemsets and rules, see the NODE_DESCRIPTION for the root node of the model.</span></span>  
  
 <span data-ttu-id="e96e4-156">**Nó do conjunto de itens ou de regra** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="e96e4-156">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="e96e4-157">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="e96e4-157">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="e96e4-158">O nome exclusivo do nó pai.</span><span class="sxs-lookup"><span data-stu-id="e96e4-158">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="e96e4-159">**Nó pai** Sempre nulo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-159">**Parent node** Always NULL.</span></span>  
  
 <span data-ttu-id="e96e4-160">**Nó do conjunto de itens ou de regra** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="e96e4-160">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="e96e4-161">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e96e4-161">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="e96e4-162">Uma descrição amigável do conteúdo do nó.</span><span class="sxs-lookup"><span data-stu-id="e96e4-162">A user-friendly description of the contents of the node.</span></span>  
  
 <span data-ttu-id="e96e4-163">**Nó pai** Inclui uma lista separada por vírgula das seguintes informações sobre o modelo:</span><span class="sxs-lookup"><span data-stu-id="e96e4-163">**Parent node** Includes a comma-separated list of the following information about the model:</span></span>  
  
|<span data-ttu-id="e96e4-164">Item</span><span class="sxs-lookup"><span data-stu-id="e96e4-164">Item</span></span>|<span data-ttu-id="e96e4-165">Descrição</span><span class="sxs-lookup"><span data-stu-id="e96e4-165">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="e96e4-166">ITEMSET_COUNT</span><span class="sxs-lookup"><span data-stu-id="e96e4-166">ITEMSET_COUNT</span></span>|<span data-ttu-id="e96e4-167">Contagem de todos os conjuntos de itens do modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-167">Count of all itemsets in model.</span></span>|  
|<span data-ttu-id="e96e4-168">RULE_COUNT</span><span class="sxs-lookup"><span data-stu-id="e96e4-168">RULE_COUNT</span></span>|<span data-ttu-id="e96e4-169">Contagem de todas as regras do modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-169">Count of all rules in model.</span></span>|  
|<span data-ttu-id="e96e4-170">MIN_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="e96e4-170">MIN_SUPPORT</span></span>|<span data-ttu-id="e96e4-171">O suporte mínimo localizado para qualquer conjunto de itens único.</span><span class="sxs-lookup"><span data-stu-id="e96e4-171">The minimum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="e96e4-172">**Observação** Esse valor pode ser diferente daquele que você definiu para o parâmetro *MINIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="e96e4-172">**Note** This value might differ from the value that you set for the *MINIMUM _SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="e96e4-173">MAX_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="e96e4-173">MAX_SUPPORT</span></span>|<span data-ttu-id="e96e4-174">O suporte máximo localizado para qualquer conjunto de itens único.</span><span class="sxs-lookup"><span data-stu-id="e96e4-174">The maximum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="e96e4-175">**Observação** Esse valor pode ser diferente daquele que você definiu para o parâmetro *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="e96e4-175">**Note** This value might differ from the value that you set for the *MAXIMUM_SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="e96e4-176">MIN_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="e96e4-176">MIN_ITEMSET_SIZE</span></span>|<span data-ttu-id="e96e4-177">O tamanho do menor conjunto de itens, representado por uma contagem de itens.</span><span class="sxs-lookup"><span data-stu-id="e96e4-177">The size of the smallest itemset, represented as a count of items.</span></span><br /><br /> <span data-ttu-id="e96e4-178">Um valor de 0 indica que o estado `Missing` foi tratado como um item independente.</span><span class="sxs-lookup"><span data-stu-id="e96e4-178">A value of 0 indicates that the `Missing` state was treated as an independent item.</span></span><br /><br /> <span data-ttu-id="e96e4-179">**Observação** O valor padrão do parâmetro *MINIMUM_ITEMSET_SIZE* é 1.</span><span class="sxs-lookup"><span data-stu-id="e96e4-179">**Note** The default value of the *MINIMUM_ITEMSET_SIZE* parameter is 1.</span></span>|  
|<span data-ttu-id="e96e4-180">MAX_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="e96e4-180">MAX_ITEMSET_SIZE</span></span>|<span data-ttu-id="e96e4-181">Indica o tamanho do maior conjunto de dados localizado.</span><span class="sxs-lookup"><span data-stu-id="e96e4-181">Indicates the size of the largest itemset that was found.</span></span><br /><br /> <span data-ttu-id="e96e4-182">**Observação** Esse valor é restrito pelo valor que você definiu para o parâmetro *MAX_ITEMSET_SIZE* ao criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-182">**Note** This value is constrained by the value that you set for the *MAX_ITEMSET_SIZE* parameter when you created the model.</span></span> <span data-ttu-id="e96e4-183">Esse valor nunca pode exceder aquele valor; no entanto, pode ser menor.</span><span class="sxs-lookup"><span data-stu-id="e96e4-183">This value can never exceed that value; however, it can be less.</span></span> <span data-ttu-id="e96e4-184">O valor padrão é 3.</span><span class="sxs-lookup"><span data-stu-id="e96e4-184">The default value is 3.</span></span>|  
|<span data-ttu-id="e96e4-185">MIN_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="e96e4-185">MIN_PROBABILITY</span></span>|<span data-ttu-id="e96e4-186">A probabilidade mínima detectada para qualquer conjunto de itens único ou regra do modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-186">The minimum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="e96e4-187">Exemplo: 0,400390625</span><span class="sxs-lookup"><span data-stu-id="e96e4-187">Example: 0.400390625</span></span><br /><br /> <span data-ttu-id="e96e4-188">**Observação** Para conjuntos de itens, esse valor é sempre maior que valor que você definiu para o parâmetro *MINIMUM_PROBABILITY* ao criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-188">**Note** For itemsets, this value is always greater than the value that you set for the *MINIMUM_PROBABILITY* parameter when you created the model.</span></span>|  
|<span data-ttu-id="e96e4-189">MAX_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="e96e4-189">MAX_PROBABILITY</span></span>|<span data-ttu-id="e96e4-190">A probabilidade máxima detectada para qualquer conjunto de itens único ou regra do modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-190">The maximum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="e96e4-191">Example: 1</span><span class="sxs-lookup"><span data-stu-id="e96e4-191">Example: 1</span></span><br /><br /> <span data-ttu-id="e96e4-192">**Observação** Não há nenhum parâmetro para restringir a probabilidade máxima de conjuntos de itens.</span><span class="sxs-lookup"><span data-stu-id="e96e4-192">**Note** There is no parameter to constrain maximum probability of itemsets.</span></span> <span data-ttu-id="e96e4-193">Para eliminar itens que são muito frequentes, use o parâmetro *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="e96e4-193">If you want to eliminate items that are too frequent, use the *MAXIMUM_SUPPORT* parameter instead.</span></span>|  
|<span data-ttu-id="e96e4-194">MIN_LIFT</span><span class="sxs-lookup"><span data-stu-id="e96e4-194">MIN_LIFT</span></span>|<span data-ttu-id="e96e4-195">O valor mínimo de comparação de precisão fornecido pelo modelo para qualquer conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="e96e4-195">The minimum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="e96e4-196">Exemplo: 0,14309369632511</span><span class="sxs-lookup"><span data-stu-id="e96e4-196">Example: 0.14309369632511</span></span><br /><br /> <span data-ttu-id="e96e4-197">Observação: saber o valor mínimo de comparação de precisão pode ajudar a determinar se a comparação de precisão de algum conjunto de dados é significativa.</span><span class="sxs-lookup"><span data-stu-id="e96e4-197">Note: Knowing the minimum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
|<span data-ttu-id="e96e4-198">MAX_LIFT</span><span class="sxs-lookup"><span data-stu-id="e96e4-198">MAX_LIFT</span></span>|<span data-ttu-id="e96e4-199">O valor máximo de comparação de precisão fornecido pelo modelo para qualquer conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="e96e4-199">The maximum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="e96e4-200">Exemplo: 1,95758227647523 **Observação** Saber o valor máximo de comparação de precisão pode ajudar a determinar se a comparação de precisão de qualquer conjunto de dados é significante.</span><span class="sxs-lookup"><span data-stu-id="e96e4-200">Example: 1.95758227647523 **Note** Knowing the maximum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
  
 <span data-ttu-id="e96e4-201">**Nó do conjunto de itens** Os nós de conjuntos de itens contêm uma lista dos itens, exibida como uma cadeia de caracteres de texto separada por vírgula.</span><span class="sxs-lookup"><span data-stu-id="e96e4-201">**Itemset node** Itemset nodes contain a list of the items, displayed as a comma-separated text string.</span></span>  
  
 <span data-ttu-id="e96e4-202">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="e96e4-202">Example:</span></span>  
  
 `Touring Tire = Existing, Water Bottle = Existing`  
  
 <span data-ttu-id="e96e4-203">Significa que foram comprados juntamente pneus de passeio e garrafas de água.</span><span class="sxs-lookup"><span data-stu-id="e96e4-203">This means touring tires and water bottles were purchased together.</span></span>  
  
 <span data-ttu-id="e96e4-204">**Nó de regra** Os nós de regras contêm um lado esquerdo e um direito, separados por uma seta.</span><span class="sxs-lookup"><span data-stu-id="e96e4-204">**Rule node** Rule nodes contains a left-hand and right-hand side of the rule, separated by an arrow.</span></span>  
  
 <span data-ttu-id="e96e4-205">Exemplo: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span><span class="sxs-lookup"><span data-stu-id="e96e4-205">Example: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span></span>  
  
 <span data-ttu-id="e96e4-206">Significa que, se alguém comprou pneus de passeio e uma garrafa de água, provavelmente vai comprar um boné de ciclismo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-206">This means that if someone bought a touring tire and a water bottle, they were also likely to buy a cycling cap.</span></span>  
  
 <span data-ttu-id="e96e4-207">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="e96e4-207">NODE_RULE</span></span>  
 <span data-ttu-id="e96e4-208">Um fragmento XML que descreve a regra ou o conjunto de itens que foi inserido no nó.</span><span class="sxs-lookup"><span data-stu-id="e96e4-208">An XML fragment that describes the rule or itemset that is embedded in the node.</span></span>  
  
 <span data-ttu-id="e96e4-209">**Nó pai** Em branco.</span><span class="sxs-lookup"><span data-stu-id="e96e4-209">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="e96e4-210">**Nó do conjunto de itens** Em branco.</span><span class="sxs-lookup"><span data-stu-id="e96e4-210">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="e96e4-211">**Nó da regra** O fragmento XML inclui informações adicionais úteis sobre a regra, como suporte, confiança e o número de itens, e a ID do nó que representa o lado esquerdo da regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-211">**Rule node** The XML fragment includes additional useful information about the rule, such as support, confidence, and the number of items, and the ID of the node that represents the left-hand side of the rule.</span></span>  
  
 <span data-ttu-id="e96e4-212">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="e96e4-212">MARGINAL_RULE</span></span>  
 <span data-ttu-id="e96e4-213">Em branco.</span><span class="sxs-lookup"><span data-stu-id="e96e4-213">Blank.</span></span>  
  
 <span data-ttu-id="e96e4-214">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="e96e4-214">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="e96e4-215">Uma pontuação de probabilidade ou confiança associada ao conjunto de itens ou à regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-215">A probability or confidence score associated with the itemset or rule.</span></span>  
  
 <span data-ttu-id="e96e4-216">**Nó pai** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="e96e4-216">**Parent node** Always 0.</span></span>  
  
 <span data-ttu-id="e96e4-217">**Nó do conjunto de itens** Probabilidade do conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="e96e4-217">**Itemset node** Probability of the itemset.</span></span>  
  
 <span data-ttu-id="e96e4-218">**Nó da regra** Valor de confiança da regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-218">**Rule node** Confidence value for the rule.</span></span>  
  
 <span data-ttu-id="e96e4-219">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="e96e4-219">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="e96e4-220">Mesmo que NODE_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="e96e4-220">Same as NODE_PROBABILITY.</span></span>  
  
 <span data-ttu-id="e96e4-221">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="e96e4-221">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="e96e4-222">A tabela contém informações muito diferentes, dependendo de o nó ser um conjunto de itens ou uma regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-222">The table contains very different information, depending on whether the node is an itemset or a rule.</span></span>  
  
 <span data-ttu-id="e96e4-223">**Nó pai** Em branco.</span><span class="sxs-lookup"><span data-stu-id="e96e4-223">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="e96e4-224">**Nó do conjunto de itens** Lista cada item do conjunto de itens com uma probabilidade e um valor de suporte.</span><span class="sxs-lookup"><span data-stu-id="e96e4-224">**Itemset node** Lists each item in the itemset together with a probability and support value.</span></span> <span data-ttu-id="e96e4-225">Por exemplo, se o conjunto de itens contiver dois produtos, o nome de cada um será listado juntamente com a contagem de casos que incluem esses produtos.</span><span class="sxs-lookup"><span data-stu-id="e96e4-225">For example, if the itemset contains two products, the name of each product is listed, together with the count of cases that include each product.</span></span>  
  
 <span data-ttu-id="e96e4-226">**Nó de regra** Contém duas linhas.</span><span class="sxs-lookup"><span data-stu-id="e96e4-226">**Rule node** Contains two rows.</span></span> <span data-ttu-id="e96e4-227">A primeira mostra o atributo do lado direito da regra, que é o item do predicado, com uma pontuação de confiança.</span><span class="sxs-lookup"><span data-stu-id="e96e4-227">The first row shows the attribute from the right-hand side of the rule, which is the predicted item, together with a confidence score.</span></span>  
  
 <span data-ttu-id="e96e4-228">A segunda linha é exclusiva em modelos de associação e contém um ponteiro para o conjunto de itens no lado direito da regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-228">The second row is unique to association models; it contains a pointer to the itemset on the right-hand side of the rule.</span></span> <span data-ttu-id="e96e4-229">O ponteiro é representado na coluna ATTRIBUTE_VALUE como uma ID do conjunto de itens que contém apenas o item do lado direito.</span><span class="sxs-lookup"><span data-stu-id="e96e4-229">The pointer is represented in the ATTRIBUTE_VALUE column as the ID of the itemset that contains only the right-hand item.</span></span>  
  
 <span data-ttu-id="e96e4-230">Por exemplo, se a regra for `If {A,B} Then {C}`, a tabela conterá o nome do item `{C}`e a ID do nó que só contém o conjunto de itens do item C.</span><span class="sxs-lookup"><span data-stu-id="e96e4-230">For example, if the rule is `If {A,B} Then {C}`, the table contains the name of the item `{C}`, and the ID of the node that contains the itemset for item C.</span></span>  
  
 <span data-ttu-id="e96e4-231">Esse ponteiro é útil pois é possível determinar a partir do nó do conjunto de itens entre todos os casos quantos contêm o produto no lado direito.</span><span class="sxs-lookup"><span data-stu-id="e96e4-231">This pointer is useful because you can determine from the itemset node how many cases in all include the right-hand side product.</span></span> <span data-ttu-id="e96e4-232">Os casos sujeitos à regra `If {A,B} Then {C}` formam um subconjunto dos casos listados no conjunto de itens para `{C}`.</span><span class="sxs-lookup"><span data-stu-id="e96e4-232">The cases that are subject to the rule `If {A,B} Then {C}` are a subset of the cases listed in the itemset for `{C}`.</span></span>  
  
 <span data-ttu-id="e96e4-233">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="e96e4-233">NODE_SUPPORT</span></span>  
 <span data-ttu-id="e96e4-234">O número de casos com suporte para este nó.</span><span class="sxs-lookup"><span data-stu-id="e96e4-234">The number of cases that support this node.</span></span>  
  
 <span data-ttu-id="e96e4-235">**Nó pai** Número de casos no modelo.</span><span class="sxs-lookup"><span data-stu-id="e96e4-235">**Parent node** Number of cases in the model.</span></span>  
  
 <span data-ttu-id="e96e4-236">**Nó do conjunto de itens** Número de casos que contém todos os itens do conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="e96e4-236">**Itemset node** Number of cases that contains all items in the itemset.</span></span>  
  
 <span data-ttu-id="e96e4-237">**Nó de regra** O número de casos que contém todos os itens incluídos na regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-237">**Rule node** The number of cases that contain all items included in the rule.</span></span>  
  
 <span data-ttu-id="e96e4-238">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="e96e4-238">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="e96e4-239">Contém informações diferentes que dependem de o nó se um conjunto de itens ou uma regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-239">Contains different information depending on whether the node is an itemset or rule.</span></span>  
  
 <span data-ttu-id="e96e4-240">**Nó pai** Em branco.</span><span class="sxs-lookup"><span data-stu-id="e96e4-240">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="e96e4-241">**Nó do conjunto de itens** Em branco.</span><span class="sxs-lookup"><span data-stu-id="e96e4-241">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="e96e4-242">**Nó da regra** A ID do conjunto de itens que contém os itens do lado esquerdo da regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-242">**Rule node** The ID of the itemset that contains the items in the left-hand side of the rule.</span></span> <span data-ttu-id="e96e4-243">Por exemplo, se a regra for `If {A,B} Then {C}`, essa coluna conterá a ID do conjunto de itens que contém apenas `{A,B}`.</span><span class="sxs-lookup"><span data-stu-id="e96e4-243">For example, if the rule is `If {A,B} Then {C}`, this column contains the ID of the itemset that contains only `{A,B}`.</span></span>  
  
 <span data-ttu-id="e96e4-244">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="e96e4-244">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="e96e4-245">**Nó pai** Em branco.</span><span class="sxs-lookup"><span data-stu-id="e96e4-245">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="e96e4-246">**Nó do conjunto de itens** Pontuação de importância do conjunto de itens.</span><span class="sxs-lookup"><span data-stu-id="e96e4-246">**Itemset node** Importance score for the itemset.</span></span>  
  
 <span data-ttu-id="e96e4-247">**Nó da regra** Pontuação de importância da regra.</span><span class="sxs-lookup"><span data-stu-id="e96e4-247">**Rule node** Importance score for the rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e96e4-248">A importância é calculada de forma diferente para conjuntos de itens e regras.</span><span class="sxs-lookup"><span data-stu-id="e96e4-248">Importance is calculated differently for itemsets and rules.</span></span> <span data-ttu-id="e96e4-249">Para obter mais informações, consulte [Referência técnica do algoritmo de associação da Microsoft](microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e96e4-249">For more information, see [Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="e96e4-250">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="e96e4-250">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="e96e4-251">Em branco.</span><span class="sxs-lookup"><span data-stu-id="e96e4-251">Blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96e4-252">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e96e4-252">See Also</span></span>  
 <span data-ttu-id="e96e4-253">[Conteúdo do modelo de mineração &#40;Analysis Services Mineração de dados&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e96e4-253">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="e96e4-254">[Algoritmo de associação da Microsoft](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="e96e4-254">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 [<span data-ttu-id="e96e4-255">Exemplos de consulta de um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="e96e4-255">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
  
