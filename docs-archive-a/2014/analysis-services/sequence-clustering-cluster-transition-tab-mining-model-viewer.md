---
title: Guia transição de cluster do clustering de sequências (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.sequenceclustering.transition.f1
ms.assetid: 40aef457-d69f-4905-a2d3-924c37bd3d97
author: minewiskan
ms.author: owend
ms.openlocfilehash: f777e48c2f69911e61420fd3b7a0a137a04e7c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686404"
---
# <a name="sequence-clustering-cluster-transition-tab-mining-model-viewer"></a><span data-ttu-id="8aa5b-102">Guia Transição de Cluster do clustering de sequências (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="8aa5b-102">Sequence Clustering Cluster Transition Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="8aa5b-103">A guia **Transições de Estado** no **Visualizador MSC** fornece uma visão mais detalhada das transições entre pares atributo-valor ou estados no cluster selecionado.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-103">The **State Transitions** tab in the **Microsoft Sequence Clustering Viewer** provides a closer look at the transitions between attribute-value pairs, or states, in the selected cluster.</span></span>  
  
 <span data-ttu-id="8aa5b-104">Use esta exibição de um modelo de clustering de sequência para exibir padrões.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-104">Use this view of a sequence clustering model to view patterns.</span></span> <span data-ttu-id="8aa5b-105">No diagrama, um link representa a probabilidade de uma transição e um nó representa um estado de sequência.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-105">In the diagram, a link represents the probability of a transition, and a node represents a sequence state.</span></span>  
  
 <span data-ttu-id="8aa5b-106">**Para obter mais informações:** [Algoritmo MSC](data-mining/microsoft-sequence-clustering-algorithm.md), [Procurar um modelo usando o Visualizador de Cluster de Sequência da Microsoft](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="8aa5b-106">**For More Information:** [Microsoft Sequence Clustering Algorithm](data-mining/microsoft-sequence-clustering-algorithm.md), [Browse a Model Using the Microsoft Sequence Cluster Viewer](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="8aa5b-107">Opções</span><span class="sxs-lookup"><span data-stu-id="8aa5b-107">Options</span></span>  
 <span data-ttu-id="8aa5b-108">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-108">**Refresh viewer content**</span></span>  
 <span data-ttu-id="8aa5b-109">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-109">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="8aa5b-110">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-110">**Mining Model**</span></span>  
 <span data-ttu-id="8aa5b-111">Escolha um modelo de mineração para exibir o que está presente na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-111">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="8aa5b-112">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-112">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="8aa5b-113">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-113">**Viewer**</span></span>  
 <span data-ttu-id="8aa5b-114">Escolha um visualizador que será usado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-114">Choose a viewer to use in exploring the selected mining model.</span></span> <span data-ttu-id="8aa5b-115">Você pode usar o visualizador personalizado, ou o **Visualizador de Árvore de Conteúdo Genérica da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-115">You can use the custom viewer, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="8aa5b-116">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-116">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="8aa5b-117">**Ampliar**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-117">**Zoom In**</span></span>  
 <span data-ttu-id="8aa5b-118">Amplie a imagem do diagrama, para ver melhor os estados.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-118">Zoom in to the diagram, to see the states better.</span></span>  
  
 <span data-ttu-id="8aa5b-119">**Reduzir**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-119">**Zoom Out**</span></span>  
 <span data-ttu-id="8aa5b-120">Reduza o diagrama para obter uma exibição geral dos estados no cluster.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-120">Zoom out from the diagram, to get an overall view of the states in the cluster.</span></span>  
  
 <span data-ttu-id="8aa5b-121">**Copiar Exibição do Gráfico**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-121">**Copy Graph View**</span></span>  
 <span data-ttu-id="8aa5b-122">Copie a seção visível do diagrama para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-122">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="8aa5b-123">**Copiar Todo o Gráfico**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-123">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="8aa5b-124">Copie todo o diagrama na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-124">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="8aa5b-125">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-125">**Cluster**</span></span>  
 <span data-ttu-id="8aa5b-126">Escolha um cluster para ser exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-126">Choose a cluster to display in the viewer.</span></span> <span data-ttu-id="8aa5b-127">Por padrão, **População (Todos)** é selecionada, o que significa que os estados e as transições do modelo inteiro são incluídos no gráfico.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-127">By default, **Population (All)** is selected, which means that states and transitions from the entire model are included in the graph.</span></span> <span data-ttu-id="8aa5b-128">Quando você escolhe um cluster específico, somente os estados e as transições que estão naquele cluster são exibidos.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-128">When you choose a particular cluster, only the states and transitions that are in that cluster are displayed.</span></span>  
  
 <span data-ttu-id="8aa5b-129">**Dica:** Você pode renomear clusters usando a guia **diagrama de cluster** . Basta selecionar um cluster, clicar com o botão direito do mouse e selecionar **renomear**.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-129">**Tip:** You can rename clusters by using the **Cluster Diagram** tab. Just select a cluster, right-click, and select **Rename**.</span></span> <span data-ttu-id="8aa5b-130">Renomear clusters com um rótulo mais descritivo facilita a comparação de clusters na guia **de Transições de Estado** .</span><span class="sxs-lookup"><span data-stu-id="8aa5b-130">Renaming clusters with a more descriptive label makes it easier to compare clusters in the **State Transitions** tab.</span></span>  
  
 <span data-ttu-id="8aa5b-131">**Mostrar Rótulos de Borda**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-131">**Show Edge Labels**</span></span>  
 <span data-ttu-id="8aa5b-132">Selecione esta opção para exibir números em cada borda no gráfico que denota a probabilidade da transição.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-132">Select this option to display numbers on each edge in the graph that denote the probability of the transition.</span></span>  
  
 <span data-ttu-id="8aa5b-133">**Links**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-133">**Links**</span></span>  
 <span data-ttu-id="8aa5b-134">Use o controle deslizante para controlar o número de estados e transições que são exibidos no gráfico.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-134">Use the slider to control the number of states and transitions that are displayed in the chart.</span></span> <span data-ttu-id="8aa5b-135">Abaixar o controle deslizante mostra somente os estados e as transições com a probabilidade mais alta.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-135">Lowering the slider shows only the states and transitions with the highest probability.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa5b-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8aa5b-136">See Also</span></span>  
 <span data-ttu-id="8aa5b-137">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8aa5b-137">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="8aa5b-138">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="8aa5b-138">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="8aa5b-139">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="8aa5b-139">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
