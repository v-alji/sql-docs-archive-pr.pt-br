---
title: Guia rede de dependências (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.dependencynetwork.f1
ms.assetid: e58ce1b7-20d6-42cb-ade5-916da8471e09
author: minewiskan
ms.author: owend
ms.openlocfilehash: 94ce82524445ffb8999c671c736087362ef0adfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679083"
---
# <a name="dependency-network-tab-mining-model-viewer"></a><span data-ttu-id="6fa91-102">Guia Rede de Dependências (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="6fa91-102">Dependency Network Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="6fa91-103">A guia **Rede de Dependências** provê uma exibição gráfica de todos os atributos que o modelo de mineração contém, e mostra como os atributos estão relacionados.</span><span class="sxs-lookup"><span data-stu-id="6fa91-103">The **Dependency Net** tab provides a graphical view of all attributes that the mining model contains, and shows how the attributes are related.</span></span>  
  
 <span data-ttu-id="6fa91-104">A guia **Rede de Dependência**  é usada para vários tipos de modelos de mineração, inclusive modelos de Naïve Bayes, modelos de árvore de decisão e modelos de associação.</span><span class="sxs-lookup"><span data-stu-id="6fa91-104">The **Dependency Net**  tab is used for several types of mining models, including Naïve Bayes models, decision tree models, and association models.</span></span> <span data-ttu-id="6fa91-105">Para obter mais informações sobre como interpretar o conteúdo da guia **Rede de Dependência**  no contexto destes modelos, consulte os links seguintes:</span><span class="sxs-lookup"><span data-stu-id="6fa91-105">For more information about how to interpret the contents of the **Dependency Net**  tab in the context of these models, see the following links:</span></span>  
  
 [<span data-ttu-id="6fa91-106">Procurar um modelo usando a Exibição de Árvore da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fa91-106">Browse a Model Using the Microsoft Tree Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
 [<span data-ttu-id="6fa91-107">Procurar um modelo usando o Visualizador do Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="6fa91-107">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)  
  
 [<span data-ttu-id="6fa91-108">Procurar um modelo usando o Visualizador de Regras de Associação da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fa91-108">Browse a Model Using the Microsoft Association Rules Viewer</span></span>](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)  
  
## <a name="options"></a><span data-ttu-id="6fa91-109">Opções</span><span class="sxs-lookup"><span data-stu-id="6fa91-109">Options</span></span>  
 <span data-ttu-id="6fa91-110">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="6fa91-110">**Refresh viewer content**</span></span>  
 <span data-ttu-id="6fa91-111">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="6fa91-111">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="6fa91-112">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="6fa91-112">**Mining Model**</span></span>  
 <span data-ttu-id="6fa91-113">Escolha um modelo de mineração a ser exibido, dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="6fa91-113">Choose a mining model to view, from those in the current mining structure.</span></span> <span data-ttu-id="6fa91-114">O modelo de mineração será aberto em um visualizador personalizado.</span><span class="sxs-lookup"><span data-stu-id="6fa91-114">The mining model will open in a custom viewer.</span></span> <span data-ttu-id="6fa91-115">O tipo de visualizador personalizado que é usado para cada modelo é determinado pelo algoritmo que você usou para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="6fa91-115">The type of custom viewer that is used for each model is determined by the algorithm that you used to create the model.</span></span>  
  
 <span data-ttu-id="6fa91-116">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="6fa91-116">**Viewer**</span></span>  
 <span data-ttu-id="6fa91-117">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="6fa91-117">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="6fa91-118">Para cada modelo, você pode usar o visualizador personalizado fornecido para cada modelo de mineração, ou o Visualizador de Conteúdo de Mineração da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fa91-118">For each model, you can use either the custom viewer is provided for each mining model, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="6fa91-119">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="6fa91-119">You can also use plug-in viewers if available.</span></span> <span data-ttu-id="6fa91-120">O Visualizador de Conteúdo de Mineração da Microsoft pode ser usado com todos os modelos e representa o conteúdo do modelo em uma tabela de HTML.</span><span class="sxs-lookup"><span data-stu-id="6fa91-120">The Microsoft Content Tree Viewer can be used with all models, and represents the model content in an HTML table.</span></span>  
  
 <span data-ttu-id="6fa91-121">**Ampliar**</span><span class="sxs-lookup"><span data-stu-id="6fa91-121">**Zoom In**</span></span>  
 <span data-ttu-id="6fa91-122">Amplie o diagrama para que você possa ver os atributos com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="6fa91-122">Zoom in to the diagram, so that you can see the attributes in more detail.</span></span>  
  
 <span data-ttu-id="6fa91-123">**Reduzir**</span><span class="sxs-lookup"><span data-stu-id="6fa91-123">**Zoom Out**</span></span>  
 <span data-ttu-id="6fa91-124">Reduza o diagrama, para que você possa ver mais atributos e os links entre eles.</span><span class="sxs-lookup"><span data-stu-id="6fa91-124">Zoom out from the diagram, so that you can see more attributes and the links between them.</span></span>  
  
 <span data-ttu-id="6fa91-125">**Copiar Exibição do Gráfico**</span><span class="sxs-lookup"><span data-stu-id="6fa91-125">**Copy Graph View**</span></span>  
 <span data-ttu-id="6fa91-126">Copie a seção visível do diagrama para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="6fa91-126">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="6fa91-127">**Copiar Todo o Gráfico**</span><span class="sxs-lookup"><span data-stu-id="6fa91-127">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="6fa91-128">Copie todo o diagrama na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="6fa91-128">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="6fa91-129">**Links**</span><span class="sxs-lookup"><span data-stu-id="6fa91-129">**Links**</span></span>  
 <span data-ttu-id="6fa91-130">Ajuste os links (bordas) e nós exibidos pelo visualizador, regulando o controle deslizante à direita dos atributos.</span><span class="sxs-lookup"><span data-stu-id="6fa91-130">Adjust how many links (edges) and nodes the viewer shows by adjusting the slider to the right of the attributes.</span></span> <span data-ttu-id="6fa91-131">Arrastar a barra de controle deslizante para baixo aumenta o valor de limite, de forma que só os links mais fortes sejam mostrados.</span><span class="sxs-lookup"><span data-stu-id="6fa91-131">Dragging the slider bar down increases the threshold value, so that only the strongest links are shown.</span></span> <span data-ttu-id="6fa91-132">Para cada tipo de modelo, um valor ligeiramente diferente é usado para representar os links no gráfico:</span><span class="sxs-lookup"><span data-stu-id="6fa91-132">For each model type, a slightly different value is used to represent the links in the graph:</span></span>  
  
-   <span data-ttu-id="6fa91-133">Em um modelo de **árvore de decisão** , as bordas representam a força preditiva da conexão, determinada em parte pela pontuação de divisão.</span><span class="sxs-lookup"><span data-stu-id="6fa91-133">In a **decision tree** model, the edges represent the predictive strength of the connection, determined partly by the split score.</span></span>  
  
-   <span data-ttu-id="6fa91-134">Em um modelo de **Naïve Bayes** , os links entre dois nós podem ir nas duas direções: ou seja, o nó A pode prever o nó B e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="6fa91-134">In a **Naïve Bayes** model, the links between two nodes can go either way: that is, node A can predict the node B, and vice versa.</span></span> <span data-ttu-id="6fa91-135">A contagem associada com a borda representa a força preditiva da conexão.</span><span class="sxs-lookup"><span data-stu-id="6fa91-135">The score associated with the edge represents the predictive strength of the connection.</span></span>  
  
-   <span data-ttu-id="6fa91-136">Em um **modelo de associação**, as bordas entre nós representam a contagem de importância da regra que conecta dois conjuntos de itens.</span><span class="sxs-lookup"><span data-stu-id="6fa91-136">In an **association model**, the edges between nodes represent the importance score of the rule that connects two itemsets.</span></span>  
  
 <span data-ttu-id="6fa91-137">Uma regra geral para todos os tipos de modelos é que, quanto mais forte o link, mais forte a relação previsível entre os dois atributos.</span><span class="sxs-lookup"><span data-stu-id="6fa91-137">A general rule for all model types is that the stronger the link, the stronger the predictive relationship between the two attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa91-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6fa91-138">See Also</span></span>  
 <span data-ttu-id="6fa91-139">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6fa91-139">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="6fa91-140">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="6fa91-140">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="6fa91-141">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="6fa91-141">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
