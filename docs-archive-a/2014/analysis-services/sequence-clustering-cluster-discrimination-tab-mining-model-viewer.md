---
title: Guia discriminação do cluster de clustering de sequências (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.sequenceclustering.discrimination.f1
ms.assetid: 7dd16479-2633-4f4b-83bf-cf55972a2241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9839a6185933fd87929331558ed63c1d81c6a748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686408"
---
# <a name="sequence-clustering-cluster-discrimination-tab-mining-model-viewer"></a><span data-ttu-id="64990-102">Guia Discriminação de Cluster do clustering de sequências (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="64990-102">Sequence Clustering Cluster Discrimination Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="64990-103">A guia  **Discriminação do Cluster** no **Visualizador de Cluster de Sequência da Microsoft** compara clusters selecionados de um modelo de clustering de sequências.</span><span class="sxs-lookup"><span data-stu-id="64990-103">The  **Cluster Discrimination** tab in the **Microsoft Sequence Clustering Viewer** compares selected clusters from a sequence clustering model.</span></span>  
  
 <span data-ttu-id="64990-104">Use esta exibição de um modelo de clustering de sequência para comparar dois clusters e ver quais estados e transições são diferentes.</span><span class="sxs-lookup"><span data-stu-id="64990-104">Use this view of a sequence clustering model to compare two clusters and see which states and transitions are different.</span></span>  
  
 <span data-ttu-id="64990-105">**Para obter mais informações:** [Algoritmo MSC](data-mining/microsoft-sequence-clustering-algorithm.md), [Procurar um modelo usando o Visualizador de Cluster de Sequência da Microsoft](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="64990-105">**For More Information:** [Microsoft Sequence Clustering Algorithm](data-mining/microsoft-sequence-clustering-algorithm.md), [Browse a Model Using the Microsoft Sequence Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="64990-106">Opções</span><span class="sxs-lookup"><span data-stu-id="64990-106">Options</span></span>  
 <span data-ttu-id="64990-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="64990-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="64990-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="64990-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="64990-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="64990-109">**Mining Model**</span></span>  
 <span data-ttu-id="64990-110">Escolha um modelo de mineração para exibir o que está presente na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="64990-110">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="64990-111">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="64990-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="64990-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="64990-112">**Viewer**</span></span>  
 <span data-ttu-id="64990-113">Escolha um visualizador que será usado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="64990-113">Choose a viewer to use in exploring the selected mining model.</span></span> <span data-ttu-id="64990-114">Você pode usar o visualizador personalizado, ou o **Visualizador de Árvore de Conteúdo Genérica da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="64990-114">You can use the custom viewer, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="64990-115">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="64990-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="64990-116">**Cluster 1**</span><span class="sxs-lookup"><span data-stu-id="64990-116">**Cluster 1**</span></span>  
 <span data-ttu-id="64990-117">Selecione um cluster desses no modelo.</span><span class="sxs-lookup"><span data-stu-id="64990-117">Select a cluster from those in the model.</span></span>  
  
 <span data-ttu-id="64990-118">**Cluster 2**</span><span class="sxs-lookup"><span data-stu-id="64990-118">**Cluster 2**</span></span>  
 <span data-ttu-id="64990-119">Selecione um segundo cluster no modelo de mineração para comparar com o **Cluster 1**.</span><span class="sxs-lookup"><span data-stu-id="64990-119">Select a second cluster in the mining model, to compare to **Cluster 1**.</span></span>  
  
 <span data-ttu-id="64990-120">Se você não selecionar outro cluster, por padrão o cluster selecionado será comparado com seu complemento, ou seja, todos os casos no modelo que não estão no Cluster 1.</span><span class="sxs-lookup"><span data-stu-id="64990-120">If you do not select another cluster, by default the selected cluster is compared to its complement, meaning all cases in the model that are not in Cluster 1.</span></span>  
  
 <span data-ttu-id="64990-121">**Pontuações de discriminação para \<cluster 1> e\<cluster 2>**</span><span class="sxs-lookup"><span data-stu-id="64990-121">**Discrimination scores for \<cluster 1> and \<cluster 2>**</span></span>  
 <span data-ttu-id="64990-122">Este gráfico fornece a comparação detalhada dos clusters que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="64990-122">This chart provides the detailed comparison of the clusters that you selected.</span></span> <span data-ttu-id="64990-123">Em geral, um modelo de clustering raramente atribui estados ou valores exclusivamente a um único cluster.</span><span class="sxs-lookup"><span data-stu-id="64990-123">In general, a clustering model rarely assigns states or values exclusively to a single cluster.</span></span> <span data-ttu-id="64990-124">Portanto, o visualizador apenas indica que um atributo específico ou estado *favorece* um cluster específico.</span><span class="sxs-lookup"><span data-stu-id="64990-124">Therefore, the viewer indicates only that a particular attribute or state *favors* a particular cluster.</span></span>  
  
 <span data-ttu-id="64990-125">Em geral, um determinado cluster pode conter mais de um estado: por exemplo, um estado comum pode ser a compra de uma Garrafa de Água e Suporte de Garrafa de Água na sequência.</span><span class="sxs-lookup"><span data-stu-id="64990-125">Overall, a certain cluster might contain more of one state: for example, a common state might be the purchase of a Water Bottle and Water Bottle Cage in sequence.</span></span> <span data-ttu-id="64990-126">Porém, a sequência pode estar presente em outros clusters que têm características de definição mais importantes.</span><span class="sxs-lookup"><span data-stu-id="64990-126">However, the sequence might be present in other clusters that have more important defining characteristics.</span></span> <span data-ttu-id="64990-127">Por exemplo, outro cluster pode ser caracterizado mais fortemente por tempos de transação muito curtos, e uma análise revelaria que os itens Garrafa de Água e Suporte de Garrafa de Água estão posicionados para geralmente poderem ser agrupados neste cluster, mas não sempre.</span><span class="sxs-lookup"><span data-stu-id="64990-127">For example, another cluster might be characterized most strongly by very short transaction times, and an analysis would reveal that [Water Bottle and Waterthe items are positioned to might usually be grouped in this cluster, but not always.</span></span>  
  
|<span data-ttu-id="64990-128">Valor</span><span class="sxs-lookup"><span data-stu-id="64990-128">Value</span></span>|<span data-ttu-id="64990-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="64990-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="64990-130">**Variáveis**</span><span class="sxs-lookup"><span data-stu-id="64990-130">**Variables**</span></span>|<span data-ttu-id="64990-131">Um atributo no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="64990-131">An attribute in the mining model.</span></span>|  
|<span data-ttu-id="64990-132">**Valores**</span><span class="sxs-lookup"><span data-stu-id="64990-132">**Values**</span></span>|<span data-ttu-id="64990-133">Um estado do atributo listado em **Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="64990-133">A state of the attribute that is listed in **Variables**.</span></span>|  
|<span data-ttu-id="64990-134">**Enfatiza\<cluster 1>**</span><span class="sxs-lookup"><span data-stu-id="64990-134">**Favors \<cluster 1>**</span></span>|<span data-ttu-id="64990-135">Contém uma barra sombreada que indica a força de o atributo e o estado listados em **Variáveis** e **Valor** favorecerem o cluster selecionado em **Cluster 1.**</span><span class="sxs-lookup"><span data-stu-id="64990-135">Contains a shaded bar that indicates how strongly the attribute and the state that are listed in **Variables** and **Value** favor the cluster that is selected in **Cluster 1**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64990-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64990-136">See Also</span></span>  
 <span data-ttu-id="64990-137">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="64990-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="64990-138">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="64990-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="64990-139">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="64990-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
