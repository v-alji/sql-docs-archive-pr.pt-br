---
title: Conteúdo do modelo de mineração para modelos de clustering (Analysis Services-Mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- nearest neighbor [Data Mining]
- clustering [Data Mining]
- mining model content, clustering models
- clustering algorithms [Analysis Services]
ms.assetid: aed1b7d3-8f20-4eeb-b156-0229f942cefd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 400575d5c6ce8094b67500d15a86137302282fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572840"
---
# <a name="mining-model-content-for-clustering-models-analysis-services---data-mining"></a><span data-ttu-id="81e2f-102">Conteúdo do modelo de mineração para modelos de clustering (Analysis Services – Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="81e2f-102">Mining Model Content for Clustering Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="81e2f-103">Este tópico descreve o conteúdo do modelo de mineração que é específico para modelos que usam o algoritmo Microsoft Clustering.</span><span class="sxs-lookup"><span data-stu-id="81e2f-103">This topic describes mining model content that is specific to models that use the Microsoft Clustering algorithm.</span></span> <span data-ttu-id="81e2f-104">Para obter uma explicação geral sobre o conteúdo do modelo de mineração para todos os tipos de modelo, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="81e2f-104">For a general explanation of mining model content for all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-a-clustering-model"></a><span data-ttu-id="81e2f-105">Entendendo a estrutura de um modelo de clustering</span><span class="sxs-lookup"><span data-stu-id="81e2f-105">Understanding the Structure of a Clustering Model</span></span>  
 <span data-ttu-id="81e2f-106">Um modelo de clustering tem uma estrutura simples.</span><span class="sxs-lookup"><span data-stu-id="81e2f-106">A clustering model has a simple structure.</span></span> <span data-ttu-id="81e2f-107">Cada modelo tem um único nó pai que representa o modelo e seus metadados, e cada nó pai possui uma lista simples de clusters (NODE_TYPE = 5).</span><span class="sxs-lookup"><span data-stu-id="81e2f-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of clusters (NODE_TYPE = 5).</span></span> <span data-ttu-id="81e2f-108">Essa organização é mostrada na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="81e2f-108">This organization is shown in the following image.</span></span>  
  
 <span data-ttu-id="81e2f-109">![estrutura de conteúdo do modelo para clustering](../media/modelcontentstructure-clust.gif "estrutura de conteúdo do modelo para clustering")</span><span class="sxs-lookup"><span data-stu-id="81e2f-109">![structure of model content for clustering](../media/modelcontentstructure-clust.gif "structure of model content for clustering")</span></span>  
  
 <span data-ttu-id="81e2f-110">Cada nó filho representa um único cluster e contém estatísticas detalhadas sobre os atributos dos casos desse cluster.</span><span class="sxs-lookup"><span data-stu-id="81e2f-110">Each child node represents a single cluster and contains detailed statistics about the attributes of the cases in that cluster.</span></span> <span data-ttu-id="81e2f-111">Isso inclui a contagem do número de casos do cluster e a distribuição de valores que distinguem cada cluster.</span><span class="sxs-lookup"><span data-stu-id="81e2f-111">This includes a count of the number of cases in the cluster, and the distribution of values that distinguish the cluster from other clusters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81e2f-112">Não é necessária iteração com os nós para obter a contagem ou a descrição dos clusters; o nó pai do modelo também conta e lista os clusters.</span><span class="sxs-lookup"><span data-stu-id="81e2f-112">You do not need to iterate through the nodes to get a count or description of the clusters; the model parent node also counts and lists the clusters.</span></span>  
  
 <span data-ttu-id="81e2f-113">O nó pai contém estatísticas úteis que descrevem a distribuição real de todos os casos em treinamento.</span><span class="sxs-lookup"><span data-stu-id="81e2f-113">The parent node contains useful statistics that describe the actual distribution of all the training cases.</span></span> <span data-ttu-id="81e2f-114">Essas estatísticas são encontradas na coluna da tabela aninhada, NODE_DISTRIBUTION.</span><span class="sxs-lookup"><span data-stu-id="81e2f-114">These statistics are found in the nested table column, NODE_DISTRIBUTION.</span></span> <span data-ttu-id="81e2f-115">Por exemplo, a tabela a seguir mostra várias linhas da tabela NODE_DISTRIBUTION que descrevem a distribuição dos dados demográficos dos clientes do modelo de clustering `TM_Clustering`que você cria no [Tutorial Básico de Data Mining](../../tutorials/basic-data-mining-tutorial.md):</span><span class="sxs-lookup"><span data-stu-id="81e2f-115">For example, the following table shows several rows from the NODE_DISTRIBUTION table that describe the distribution of customer demographics for the clustering model, `TM_Clustering`, that you create in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md):</span></span>  
  
|<span data-ttu-id="81e2f-116">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="81e2f-116">ATTRIBUTE_NAME</span></span>|<span data-ttu-id="81e2f-117">ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="81e2f-117">ATRIBUTE_VALUE</span></span>|<span data-ttu-id="81e2f-118">SUPPORT</span><span class="sxs-lookup"><span data-stu-id="81e2f-118">SUPPORT</span></span>|<span data-ttu-id="81e2f-119">PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="81e2f-119">PROBABILITY</span></span>|<span data-ttu-id="81e2f-120">variance</span><span class="sxs-lookup"><span data-stu-id="81e2f-120">VARIANCE</span></span>|<span data-ttu-id="81e2f-121">VALUE_TYPE</span><span class="sxs-lookup"><span data-stu-id="81e2f-121">VALUE_TYPE</span></span>|  
|---------------------|---------------------|-------------|-----------------|--------------|-----------------|  
|<span data-ttu-id="81e2f-122">Idade</span><span class="sxs-lookup"><span data-stu-id="81e2f-122">Age</span></span>|<span data-ttu-id="81e2f-123">Ausente</span><span class="sxs-lookup"><span data-stu-id="81e2f-123">Missing</span></span>|<span data-ttu-id="81e2f-124">0</span><span class="sxs-lookup"><span data-stu-id="81e2f-124">0</span></span>|<span data-ttu-id="81e2f-125">0</span><span class="sxs-lookup"><span data-stu-id="81e2f-125">0</span></span>|<span data-ttu-id="81e2f-126">0</span><span class="sxs-lookup"><span data-stu-id="81e2f-126">0</span></span>|<span data-ttu-id="81e2f-127">1 (Ausente)</span><span class="sxs-lookup"><span data-stu-id="81e2f-127">1 (Missing)</span></span>|  
|<span data-ttu-id="81e2f-128">Idade</span><span class="sxs-lookup"><span data-stu-id="81e2f-128">Age</span></span>|<span data-ttu-id="81e2f-129">44.9016152716593</span><span class="sxs-lookup"><span data-stu-id="81e2f-129">44.9016152716593</span></span>|<span data-ttu-id="81e2f-130">12939</span><span class="sxs-lookup"><span data-stu-id="81e2f-130">12939</span></span>|<span data-ttu-id="81e2f-131">1</span><span class="sxs-lookup"><span data-stu-id="81e2f-131">1</span></span>|<span data-ttu-id="81e2f-132">125.663453102554</span><span class="sxs-lookup"><span data-stu-id="81e2f-132">125.663453102554</span></span>|<span data-ttu-id="81e2f-133">3 (Contínuo)</span><span class="sxs-lookup"><span data-stu-id="81e2f-133">3 (Continuous)</span></span>|  
|<span data-ttu-id="81e2f-134">Sexo</span><span class="sxs-lookup"><span data-stu-id="81e2f-134">Gender</span></span>|<span data-ttu-id="81e2f-135">Ausente</span><span class="sxs-lookup"><span data-stu-id="81e2f-135">Missing</span></span>|<span data-ttu-id="81e2f-136">0</span><span class="sxs-lookup"><span data-stu-id="81e2f-136">0</span></span>|<span data-ttu-id="81e2f-137">0</span><span class="sxs-lookup"><span data-stu-id="81e2f-137">0</span></span>|<span data-ttu-id="81e2f-138">0</span><span class="sxs-lookup"><span data-stu-id="81e2f-138">0</span></span>|<span data-ttu-id="81e2f-139">1 (Ausente)</span><span class="sxs-lookup"><span data-stu-id="81e2f-139">1 (Missing)</span></span>|  
|<span data-ttu-id="81e2f-140">Sexo</span><span class="sxs-lookup"><span data-stu-id="81e2f-140">Gender</span></span>|<span data-ttu-id="81e2f-141">F</span><span class="sxs-lookup"><span data-stu-id="81e2f-141">F</span></span>|<span data-ttu-id="81e2f-142">6350</span><span class="sxs-lookup"><span data-stu-id="81e2f-142">6350</span></span>|<span data-ttu-id="81e2f-143">0.490764355823479</span><span class="sxs-lookup"><span data-stu-id="81e2f-143">0.490764355823479</span></span>|<span data-ttu-id="81e2f-144">0</span><span class="sxs-lookup"><span data-stu-id="81e2f-144">0</span></span>|<span data-ttu-id="81e2f-145">4 (Discreto)</span><span class="sxs-lookup"><span data-stu-id="81e2f-145">4 (Discrete)</span></span>|  
|<span data-ttu-id="81e2f-146">Sexo</span><span class="sxs-lookup"><span data-stu-id="81e2f-146">Gender</span></span>|<span data-ttu-id="81e2f-147">M</span><span class="sxs-lookup"><span data-stu-id="81e2f-147">M</span></span>|<span data-ttu-id="81e2f-148">6589</span><span class="sxs-lookup"><span data-stu-id="81e2f-148">6589</span></span>|<span data-ttu-id="81e2f-149">0.509235644176521</span><span class="sxs-lookup"><span data-stu-id="81e2f-149">0.509235644176521</span></span>|<span data-ttu-id="81e2f-150">0</span><span class="sxs-lookup"><span data-stu-id="81e2f-150">0</span></span>|<span data-ttu-id="81e2f-151">4 (Discreto)</span><span class="sxs-lookup"><span data-stu-id="81e2f-151">4 (Discrete)</span></span>|  
  
 <span data-ttu-id="81e2f-152">A partir desses resultados, você pode ver que foram usados 12.939 casos para construir o modelo, que a proporção de homens para mulheres é de cerca de 50-50 e que a idade média é de 44 anos.</span><span class="sxs-lookup"><span data-stu-id="81e2f-152">From these results, you can see that there were 12939 cases used to build the model, that the ratio of males to females was about 50-50, and that the mean age was 44.</span></span> <span data-ttu-id="81e2f-153">As estatísticas descritivas variam de acordo com o fato de o atributo que está sendo reportado ser um tipo de dados numérico contínuo, como idade, ou um tipo de valor discreto, como gênero.</span><span class="sxs-lookup"><span data-stu-id="81e2f-153">The descriptive statistics vary depending on whether the attribute being reported is a continuous numeric data type, such as age, or a discrete value type, such as gender.</span></span> <span data-ttu-id="81e2f-154">As medidas estatísticas *mean* e *variance* são computadas para os tipos de dados contínuos, enquanto *probability* e *support* são computadas para tipos de dados discretos.</span><span class="sxs-lookup"><span data-stu-id="81e2f-154">The statistical measures *mean* and *variance* are computed for continuous data types, whereas *probability* and *support* are computed for discrete data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81e2f-155">A variância representa a variação total do cluster.</span><span class="sxs-lookup"><span data-stu-id="81e2f-155">The variance represents the total variance for the cluster.</span></span> <span data-ttu-id="81e2f-156">Quando esse valor é pequeno, indica que a maioria dos valores da coluna estão bem próximos da média.</span><span class="sxs-lookup"><span data-stu-id="81e2f-156">When the value for variance is small, it indicates that most values in the column were fairly close to the mean.</span></span> <span data-ttu-id="81e2f-157">Para obter o desvio padrão, calcule a raiz quadrada da variância.</span><span class="sxs-lookup"><span data-stu-id="81e2f-157">To obtain the standard deviation, calculate the square root of the variance.</span></span>  
  
 <span data-ttu-id="81e2f-158">Observe que para cada atributo existe um tipo de valor `Missing` que indica quantos casos não tinham dados para esse atributo.</span><span class="sxs-lookup"><span data-stu-id="81e2f-158">Note that for each of the attributes there is a `Missing` value type that tells you how many cases had no data for that attribute.</span></span> <span data-ttu-id="81e2f-159">Dados ausentes podem ser importantes e afetar os cálculos de várias formas, dependendo do tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="81e2f-159">Missing data can be significant and affects calculations in different ways, depending on the data type.</span></span> <span data-ttu-id="81e2f-160">Para obter mais informações, consulte [Valores ausentes &#40;Analysis Services – Data Mining&#41;](missing-values-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="81e2f-160">For more information, see [Missing Values &#40;Analysis Services - Data Mining&#41;](missing-values-analysis-services-data-mining.md).</span></span>  
  
## <a name="model-content-for-a-clustering-model"></a><span data-ttu-id="81e2f-161">Conteúdo do modelo para um modelo de clustering</span><span class="sxs-lookup"><span data-stu-id="81e2f-161">Model Content for a Clustering Model</span></span>  
 <span data-ttu-id="81e2f-162">Esta seção fornece detalhes e exemplos somente para as colunas de conteúdo do modelo de mineração que são relevantes para os modelos de clustering.</span><span class="sxs-lookup"><span data-stu-id="81e2f-162">This section provides detail and examples only for those columns in the mining model content that are relevant for clustering models.</span></span>  
  
 <span data-ttu-id="81e2f-163">Para obter informações sobre as colunas de uso general no conjunto de linhas de esquema, como MODEL_CATALOG e MODEL_NAME, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="81e2f-163">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="81e2f-164">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="81e2f-164">MODEL_CATALOG</span></span>  
 <span data-ttu-id="81e2f-165">Nome do banco de dados no qual o modelo é armazenado.</span><span class="sxs-lookup"><span data-stu-id="81e2f-165">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="81e2f-166">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="81e2f-166">MODEL_NAME</span></span>  
 <span data-ttu-id="81e2f-167">Nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="81e2f-167">Name of the model.</span></span>  
  
 <span data-ttu-id="81e2f-168">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="81e2f-168">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="81e2f-169">Sempre em branco em modelos de clustering porque não há nenhum atributo previsível no nó.</span><span class="sxs-lookup"><span data-stu-id="81e2f-169">Always blank in clustering models because there is no predictable attribute in the mode.</span></span>  
  
 <span data-ttu-id="81e2f-170">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="81e2f-170">NODE_NAME</span></span>  
 <span data-ttu-id="81e2f-171">Sempre igual a NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="81e2f-171">Always same as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="81e2f-172">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="81e2f-172">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="81e2f-173">Um identificador exclusivo do nó no modelo.</span><span class="sxs-lookup"><span data-stu-id="81e2f-173">A unique identifier for the node within the model.</span></span> <span data-ttu-id="81e2f-174">Esse valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="81e2f-174">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="81e2f-175">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="81e2f-175">NODE_TYPE</span></span>  
 <span data-ttu-id="81e2f-176">Um modelo de clustering gera os seguintes tipos de nó:</span><span class="sxs-lookup"><span data-stu-id="81e2f-176">A clustering model outputs the following node types:</span></span>  
  
|<span data-ttu-id="81e2f-177">ID e nome do nó</span><span class="sxs-lookup"><span data-stu-id="81e2f-177">Node ID and Name</span></span>|<span data-ttu-id="81e2f-178">Descrição</span><span class="sxs-lookup"><span data-stu-id="81e2f-178">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="81e2f-179">1 (Modelo)</span><span class="sxs-lookup"><span data-stu-id="81e2f-179">1 (Model)</span></span>|<span data-ttu-id="81e2f-180">Nó raiz do modelo.</span><span class="sxs-lookup"><span data-stu-id="81e2f-180">Root node for model.</span></span>|  
|<span data-ttu-id="81e2f-181">5 (Cluster)</span><span class="sxs-lookup"><span data-stu-id="81e2f-181">5 (Cluster)</span></span>|<span data-ttu-id="81e2f-182">Contém a contagem de casos do cluster, as características dos casos do cluster e estatísticas que descrevem os valores do cluster.</span><span class="sxs-lookup"><span data-stu-id="81e2f-182">Contains a count of cases in the cluster, the characteristics of cases in the cluster, and statistics that describe the values in the cluster.</span></span>|  
  
 <span data-ttu-id="81e2f-183">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="81e2f-183">NODE_CAPTION</span></span>  
 <span data-ttu-id="81e2f-184">Um nome amigável para exibição.</span><span class="sxs-lookup"><span data-stu-id="81e2f-184">A friendly name for display purposes.</span></span> <span data-ttu-id="81e2f-185">Quando você criar um modelo, o valor de NODE_UNIQUE_NAME será usado automaticamente como legenda.</span><span class="sxs-lookup"><span data-stu-id="81e2f-185">When you create a model, the value of NODE_UNIQUE_NAME is automatically used as the caption.</span></span> <span data-ttu-id="81e2f-186">No entanto, é possível alterar o valor de NODE_CAPTION para atualizar o nome para exibição do cluster, seja de maneira programática ou usando o visualizador.</span><span class="sxs-lookup"><span data-stu-id="81e2f-186">However, you can change the value for NODE_CAPTION to update the display name for the cluster, either programmatically or by using the viewer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81e2f-187">Quando você reprocessar o modelo, todas as alterações de nome serão substituídas pelos valores novos.</span><span class="sxs-lookup"><span data-stu-id="81e2f-187">When you reprocess the model, all name changes will be overwritten by the new values.</span></span> <span data-ttu-id="81e2f-188">Não é possível persistir nomes no modelo ou monitorar alterações na associação do cluster entre versões diferentes de um modelo.</span><span class="sxs-lookup"><span data-stu-id="81e2f-188">You cannot persist names in the model, or track changes in cluster membership between different versions of a model.</span></span>  
  
 <span data-ttu-id="81e2f-189">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="81e2f-189">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="81e2f-190">Uma estimativa do número de filhos do nó.</span><span class="sxs-lookup"><span data-stu-id="81e2f-190">An estimate of the number of children that the node has.</span></span>  
  
 <span data-ttu-id="81e2f-191">**Nó pai** Indica o número de clusters no modelo.</span><span class="sxs-lookup"><span data-stu-id="81e2f-191">**Parent node** Indicates the number of clusters in the model.</span></span>  
  
 <span data-ttu-id="81e2f-192">**Nós de cluster** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="81e2f-192">**Cluster nodes** Always 0.</span></span>  
  
 <span data-ttu-id="81e2f-193">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="81e2f-193">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="81e2f-194">O nome exclusivo do nó pai.</span><span class="sxs-lookup"><span data-stu-id="81e2f-194">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="81e2f-195">**Nó pai** Sempre NULL</span><span class="sxs-lookup"><span data-stu-id="81e2f-195">**Parent node** Always NULL</span></span>  
  
 <span data-ttu-id="81e2f-196">**Nós de cluster** Normalmente, 000.</span><span class="sxs-lookup"><span data-stu-id="81e2f-196">**Cluster nodes** Usually 000.</span></span>  
  
 <span data-ttu-id="81e2f-197">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="81e2f-197">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="81e2f-198">Uma descrição do nó.</span><span class="sxs-lookup"><span data-stu-id="81e2f-198">A description of the node.</span></span>  
  
 <span data-ttu-id="81e2f-199">**Nó pai** Sempre **(Tudo)**.</span><span class="sxs-lookup"><span data-stu-id="81e2f-199">**Parent node** Always **(All)**.</span></span>  
  
 <span data-ttu-id="81e2f-200">**Nós de cluster** Uma lista separada por vírgula dos principais atributos que distinguem cada cluster.</span><span class="sxs-lookup"><span data-stu-id="81e2f-200">**Cluster nodes** A comma-separated list of the primary attributes that distinguish the cluster from other clusters.</span></span>  
  
 <span data-ttu-id="81e2f-201">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="81e2f-201">NODE_RULE</span></span>  
 <span data-ttu-id="81e2f-202">Não é usado para modelos de clustering.</span><span class="sxs-lookup"><span data-stu-id="81e2f-202">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="81e2f-203">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="81e2f-203">MARGINAL_RULE</span></span>  
 <span data-ttu-id="81e2f-204">Não é usado para modelos de clustering.</span><span class="sxs-lookup"><span data-stu-id="81e2f-204">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="81e2f-205">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="81e2f-205">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="81e2f-206">A probabilidade associada a este nó.</span><span class="sxs-lookup"><span data-stu-id="81e2f-206">The probability associated with this node.</span></span> <span data-ttu-id="81e2f-207">**Nó pai** Sempre 1.</span><span class="sxs-lookup"><span data-stu-id="81e2f-207">**Parent node** Always 1.</span></span>  
  
 <span data-ttu-id="81e2f-208">**Nós de cluster** A probabilidade representa a probabilidade composta dos atributos, com alguns ajustes de acordo com o algoritmo usado na criação do modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="81e2f-208">**Cluster nodes** The probability represents the compound probability of the attributes, with some adjustments depending on the algorithm used to create the clustering model.</span></span>  
  
 <span data-ttu-id="81e2f-209">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="81e2f-209">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="81e2f-210">A probabilidade de que o nó seja alcançado a partir do nó pai.</span><span class="sxs-lookup"><span data-stu-id="81e2f-210">The probability of reaching the node from the parent node.</span></span> <span data-ttu-id="81e2f-211">Em um modelo de clustering, a probabilidade marginal é sempre igual à probabilidade de nó.</span><span class="sxs-lookup"><span data-stu-id="81e2f-211">In a clustering model, the marginal probability is always the same as the node probability.</span></span>  
  
 <span data-ttu-id="81e2f-212">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="81e2f-212">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="81e2f-213">Um tabela que contém o histograma de probabilidade do nó.</span><span class="sxs-lookup"><span data-stu-id="81e2f-213">A table that contains the probability histogram of the node.</span></span>  
  
 <span data-ttu-id="81e2f-214">**Nó pai** Consulte a Introdução deste tópico.</span><span class="sxs-lookup"><span data-stu-id="81e2f-214">**Parent node** See the Introduction to this topic.</span></span>  
  
 <span data-ttu-id="81e2f-215">**Nós de cluster** Representa a distribuição de atributos e valores para casos incluídos no cluster.</span><span class="sxs-lookup"><span data-stu-id="81e2f-215">**Cluster nodes** Represents the distribution of attributes and values for cases that are included in this cluster.</span></span>  
  
 <span data-ttu-id="81e2f-216">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="81e2f-216">NODE_SUPPORT</span></span>  
 <span data-ttu-id="81e2f-217">O número de casos com suporte para este nó.</span><span class="sxs-lookup"><span data-stu-id="81e2f-217">The number of cases that support this node.</span></span> <span data-ttu-id="81e2f-218">**Nó pai** Indica o número de casos em treinamento do modelo inteiro.</span><span class="sxs-lookup"><span data-stu-id="81e2f-218">**Parent node** Indicates the number of training cases for the entire model.</span></span>  
  
 <span data-ttu-id="81e2f-219">**Nós de cluster** Indica o tamanho do cluster como o número de casos.</span><span class="sxs-lookup"><span data-stu-id="81e2f-219">**Cluster nodes** Indicates the size of the cluster as a number of cases.</span></span>  
  
 <span data-ttu-id="81e2f-220">**Observação** Se o modelo usar clustering K-Means, cada caso poderá pertencer somente a um cluster.</span><span class="sxs-lookup"><span data-stu-id="81e2f-220">**Note** If the model uses K-Means clustering, each case can belong to only one cluster.</span></span> <span data-ttu-id="81e2f-221">No entanto, se o modelo usar clustering EM, cada são pode pertencer a clusters diferentes e ao caso é atribuída uma distância ponderada para cada cluster a que ele pertence.</span><span class="sxs-lookup"><span data-stu-id="81e2f-221">However, if the model uses EM clustering, each case can belong to different cluster, and the case is assigned a weighted distance for each cluster to which it belongs.</span></span> <span data-ttu-id="81e2f-222">Portanto, para modelos EM, a soma de suporte para um cluster individual é maior que o suporte para o modelo inteiro.</span><span class="sxs-lookup"><span data-stu-id="81e2f-222">Therefore, for EM models the sum of support for an individual cluster is greater than support for the overall model.</span></span>  
  
 <span data-ttu-id="81e2f-223">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="81e2f-223">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="81e2f-224">Não é usado para modelos de clustering.</span><span class="sxs-lookup"><span data-stu-id="81e2f-224">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="81e2f-225">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="81e2f-225">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="81e2f-226">Exibe uma pontuação associada ao nó.</span><span class="sxs-lookup"><span data-stu-id="81e2f-226">Displays a score associated with the node.</span></span>  
  
 <span data-ttu-id="81e2f-227">**Nó pai** A pontuação BIC (Bayesian Information Criterion) para o modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="81e2f-227">**Parent node** The Bayesian Information Criterion (BIC) score for the clustering model.</span></span>  
  
 <span data-ttu-id="81e2f-228">**Nós de cluster** Sempre 0.</span><span class="sxs-lookup"><span data-stu-id="81e2f-228">**Cluster nodes** Always 0.</span></span>  
  
 <span data-ttu-id="81e2f-229">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="81e2f-229">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="81e2f-230">Um rótulo usado para exibição.</span><span class="sxs-lookup"><span data-stu-id="81e2f-230">A label used for display purposes.</span></span> <span data-ttu-id="81e2f-231">Não é possível alterar essa legenda.</span><span class="sxs-lookup"><span data-stu-id="81e2f-231">You cannot change this caption.</span></span>  
  
 <span data-ttu-id="81e2f-232">**Nó pai** O tipo de modelo: modelo de clustering</span><span class="sxs-lookup"><span data-stu-id="81e2f-232">**Parent node** The type of model: Cluster model</span></span>  
  
 <span data-ttu-id="81e2f-233">**Nós de cluster** O nome do cluster.</span><span class="sxs-lookup"><span data-stu-id="81e2f-233">**Cluster nodes** The name of the cluster.</span></span> <span data-ttu-id="81e2f-234">Exemplo: Cluster 1.</span><span class="sxs-lookup"><span data-stu-id="81e2f-234">Example: Cluster 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81e2f-235">Comentários</span><span class="sxs-lookup"><span data-stu-id="81e2f-235">Remarks</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="81e2f-236">oferece vários métodos para a criação de um modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="81e2f-236">provides multiple methods for creating a clustering model.</span></span> <span data-ttu-id="81e2f-237">Se você não souber qual método foi usado para criar o modelo com que você está trabalhando, pode recuperar os metadados do modelo programaticamente, usando um cliente ADOMD ou AMO ou consultando o conjunto de linhas do esquema de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="81e2f-237">If you do not know which method was used to create the model that you are working with, you can retrieve the model metadata programmatically, by using an ADOMD client or AMO, or by querying the data mining schema rowset.</span></span> <span data-ttu-id="81e2f-238">Para obter mais informações, consulte [Como consultar os parâmetros usados para criar um modelo de mineração](query-the-parameters-used-to-create-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="81e2f-238">For more information, see [Query the Parameters Used to Create a Mining Model](query-the-parameters-used-to-create-a-mining-model.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81e2f-239">A estrutura e o conteúdo do modelo permanecem inalterados, independentemente do método ou dos parâmetros de clustering usados.</span><span class="sxs-lookup"><span data-stu-id="81e2f-239">The structure and content of the model stay the same, regardless of which clustering method or parameters you use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e2f-240">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81e2f-240">See Also</span></span>  
 <span data-ttu-id="81e2f-241">[Conteúdo do modelo de mineração &#40;Analysis Services Mineração de dados&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="81e2f-241">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="81e2f-242">[Visualizadores de modelo de mineração de dados](data-mining-model-viewers.md) </span><span class="sxs-lookup"><span data-stu-id="81e2f-242">[Data Mining Model Viewers](data-mining-model-viewers.md) </span></span>  
 <span data-ttu-id="81e2f-243">[Algoritmo Microsoft Clustering](microsoft-clustering-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="81e2f-243">[Microsoft Clustering Algorithm](microsoft-clustering-algorithm.md) </span></span>  
 [<span data-ttu-id="81e2f-244">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="81e2f-244">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
