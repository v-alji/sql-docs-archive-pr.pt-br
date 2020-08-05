---
title: Guia discriminação de cluster (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.clustering.discrimination.f1
ms.assetid: ae7cfff7-ab1c-4cf5-9a91-97b21d15d85f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 35435736bcdf1b1962de6babace2def953bbfff0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571693"
---
# <a name="cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="01bf3-102">Guia Distinção de Cluster (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="01bf3-102">Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="01bf3-103">Use a guia **Distinção de Cluster** para comparar dois clusters existentes em um modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="01bf3-103">Use the **Cluster Discrimination** tab to compare two clusters that exist in a clustering model.</span></span> <span data-ttu-id="01bf3-104">Você pode ver como as diferentes combinações de atributos e valores são representadas dentro dos clusters.</span><span class="sxs-lookup"><span data-stu-id="01bf3-104">You can see how different combinations of attributes and values are represented within the clusters.</span></span>  
  
 <span data-ttu-id="01bf3-105">**Para obter mais informações:** [Algoritmo MSC](data-mining/microsoft-clustering-algorithm.md), [Procurar um modelo usando o Visualizador de Cluster da Microsoft](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="01bf3-105">**For More Information:** [Microsoft Clustering Algorithm](data-mining/microsoft-clustering-algorithm.md), [Browse a Model Using the Microsoft Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="01bf3-106">Opções</span><span class="sxs-lookup"><span data-stu-id="01bf3-106">Options</span></span>  
 <span data-ttu-id="01bf3-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="01bf3-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="01bf3-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="01bf3-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="01bf3-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="01bf3-109">**Mining Model**</span></span>  
 <span data-ttu-id="01bf3-110">Escolha um modelo de mineração dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="01bf3-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="01bf3-111">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="01bf3-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="01bf3-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="01bf3-112">**Viewer**</span></span>  
 <span data-ttu-id="01bf3-113">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="01bf3-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="01bf3-114">Você pode usar o visualizador personalizado para modelos de clustering, ou Visualizador de Conteúdo de Mineração da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01bf3-114">You can use the custom viewer for clustering models, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="01bf3-115">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="01bf3-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="01bf3-116">**Cluster 1**</span><span class="sxs-lookup"><span data-stu-id="01bf3-116">**Cluster 1**</span></span>  
 <span data-ttu-id="01bf3-117">Selecione um cluster, para que você possa compará-lo com outro cluster.</span><span class="sxs-lookup"><span data-stu-id="01bf3-117">Select a cluster, so that you can compare it to another cluster.</span></span>  
  
 <span data-ttu-id="01bf3-118">**Cluster 2**</span><span class="sxs-lookup"><span data-stu-id="01bf3-118">**Cluster 2**</span></span>  
 <span data-ttu-id="01bf3-119">Selecione um segundo cluster da lista de clusters no modelo de mineração para comparar com o **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-119">Select a second cluster from the list of clusters in the mining model, to compare to **Cluster 1**.</span></span> <span data-ttu-id="01bf3-120">Você também pode comparar um cluster com seu complemento, ou seja, todos os casos no modelo exceto os que estiverem no cluster selecionado.</span><span class="sxs-lookup"><span data-stu-id="01bf3-120">You can also compare a cluster to its complement, meaning all cases in the model except those in the selected cluster.</span></span>  
  
 <span data-ttu-id="01bf3-121">**Pontuações de discriminação para \<cluster 1> e\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="01bf3-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="01bf3-122">As colunas no gráfico fornecem informações sobre como cada par atributo-valor está relacionado com os dois clusters selecionados.</span><span class="sxs-lookup"><span data-stu-id="01bf3-122">The columns in the graph provide information about how each attribute-value pair is related to the two selected clusters.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01bf3-123">**Variáveis**</span><span class="sxs-lookup"><span data-stu-id="01bf3-123">**Variables**</span></span>|<span data-ttu-id="01bf3-124">Um atributo no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="01bf3-124">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="01bf3-125">**Valores**</span><span class="sxs-lookup"><span data-stu-id="01bf3-125">**Values**</span></span>|<span data-ttu-id="01bf3-126">Um valor do atributo selecionado em **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-126">A value of the attribute selected in **Variables**.</span></span>|  
|<span data-ttu-id="01bf3-127">**Enfatiza\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="01bf3-127">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="01bf3-128">O gráfico de barra à esquerda representa a probabilidade de o par atributo-valor selecionado ser representativo do cluster selecionado em **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-128">The bar graph on the left represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 1**.</span></span> <span data-ttu-id="01bf3-129">Você pode passar o mouse sobre a barra para ver o valor, representado como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="01bf3-129">You can pause the mouse over the bar to see the value, represented as a percentage.</span></span> <span data-ttu-id="01bf3-130">Observe que, mesmo se o valor for zero, não significa que o atributo-Value está necessariamente ausente do cluster, apenas que a distribuição favorece fortemente um cluster sobre o outro.</span><span class="sxs-lookup"><span data-stu-id="01bf3-130">Note that even if the value is zero, it doesn't mean the attribute-value is necessarily missing from the cluster, just that the distribution strongly favors one cluster over the other.</span></span>|  
|<span data-ttu-id="01bf3-131">**Enfatiza\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="01bf3-131">**Favors \<cluster 2>**</span></span>|<span data-ttu-id="01bf3-132">O gráfico de barra à direita representa a probabilidade de o par atributo-valor selecionado ser representativo do cluster selecionado em **Cluster 2**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-132">The bar graph on the right represents the probability that the selected attribute-value pair is representative of the cluster selected in **Cluster 2**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01bf3-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="01bf3-133">See Also</span></span>  
 <span data-ttu-id="01bf3-134">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="01bf3-134">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="01bf3-135">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="01bf3-135">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="01bf3-136">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="01bf3-136">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
