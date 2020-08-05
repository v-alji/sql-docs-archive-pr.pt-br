---
title: Guia árvore de decisão (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.decisiontree.f1
ms.assetid: dc88606f-ba7c-4f8d-af65-bfa17ec16e2b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5f6f84a2b43c251d2710125acfc2ff90f067cdc6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572820"
---
# <a name="decision-tree-tab-mining-model-viewer"></a><span data-ttu-id="fd679-102">Guia Árvore de Decisão (Visualizador do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="fd679-102">Decision Tree Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="fd679-103">O painel **DecisionTree** exibe uma representação visual das regras de decisão criadas em um modelo de árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="fd679-103">The **DecisionTree** pane displays a visual representation of the decision rules that are created in a decision tree model.</span></span> <span data-ttu-id="fd679-104">As regras de decisão descrevem caminhos para um determinado resultado.</span><span class="sxs-lookup"><span data-stu-id="fd679-104">Decision rules describe path paths towards a certain outcome.</span></span>  
  
 <span data-ttu-id="fd679-105">**Para obter mais informações:** [Algoritmo Árvores de Decisão da Microsoft](data-mining/microsoft-decision-trees-algorithm.md), [Procurar um modelo usando o Visualizador de Árvore da Microsoft](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="fd679-105">**For More Information:** [Microsoft Decision Trees Algorithm](data-mining/microsoft-decision-trees-algorithm.md), [Browse a Model Using the Microsoft Tree Viewer](data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd679-106">Opções</span><span class="sxs-lookup"><span data-stu-id="fd679-106">Options</span></span>  
 <span data-ttu-id="fd679-107">**Atualizar conteúdo do visualizador**</span><span class="sxs-lookup"><span data-stu-id="fd679-107">**Refresh viewer content**</span></span>  
 <span data-ttu-id="fd679-108">Recarregue o modelo de mineração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="fd679-108">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="fd679-109">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="fd679-109">**Mining Model**</span></span>  
 <span data-ttu-id="fd679-110">Escolha um modelo de mineração dentre eles na estrutura de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="fd679-110">Choose a mining model from those in the current mining structure.</span></span> <span data-ttu-id="fd679-111">O modelo de mineração será aberto no visualizador associado.</span><span class="sxs-lookup"><span data-stu-id="fd679-111">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="fd679-112">**Visualizador**</span><span class="sxs-lookup"><span data-stu-id="fd679-112">**Viewer**</span></span>  
 <span data-ttu-id="fd679-113">Escolha um visualizador a ser utilizado para explorar o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="fd679-113">Choose a viewer to use to explore the selected mining model.</span></span> <span data-ttu-id="fd679-114">Você pode usar o visualizador personalizado, ou Visualizador de Conteúdo de Mineração da [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd679-114">You can use the custom viewer, or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer.</span></span> <span data-ttu-id="fd679-115">Você também pode usar visualizadores de plug-in se houver.</span><span class="sxs-lookup"><span data-stu-id="fd679-115">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="fd679-116">**Ampliar**</span><span class="sxs-lookup"><span data-stu-id="fd679-116">**Zoom In**</span></span>  
 <span data-ttu-id="fd679-117">Aproxime para obter uma exibição mais detalhada dos nós e das ramificações na árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="fd679-117">Zoom in to get a more detailed view of the nodes and branches in the decision tree.</span></span> <span data-ttu-id="fd679-118">Em um modelo complexo, as árvores de decisão podem ter muitos níveis de ramificação.</span><span class="sxs-lookup"><span data-stu-id="fd679-118">In a complex model, decision trees can have many levels of branching.</span></span>  
  
 <span data-ttu-id="fd679-119">**Reduzir**</span><span class="sxs-lookup"><span data-stu-id="fd679-119">**Zoom Out**</span></span>  
 <span data-ttu-id="fd679-120">Reduza para obter uma exibição geral da estrutura da árvore.</span><span class="sxs-lookup"><span data-stu-id="fd679-120">Zoom out to get an overall view of the tree structure.</span></span>  
  
 <span data-ttu-id="fd679-121">**Copiar Exibição do Gráfico**</span><span class="sxs-lookup"><span data-stu-id="fd679-121">**Copy Graph View**</span></span>  
 <span data-ttu-id="fd679-122">Copie a seção visível do diagrama para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="fd679-122">Copy the visible section of the diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="fd679-123">**Copiar Todo o Gráfico**</span><span class="sxs-lookup"><span data-stu-id="fd679-123">**Copy Entire Graph**</span></span>  
 <span data-ttu-id="fd679-124">Copie todo o diagrama na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="fd679-124">Copy the complete diagram to the clipboard.</span></span>  
  
 <span data-ttu-id="fd679-125">**Dimensionar diagrama para ajustar à janela**</span><span class="sxs-lookup"><span data-stu-id="fd679-125">**Scale diagram to fit window**</span></span>  
 <span data-ttu-id="fd679-126">Reduza o diagrama até que a estrutura de árvore inteira se ajuste na tela.</span><span class="sxs-lookup"><span data-stu-id="fd679-126">Zoom out from the diagram until the whole tree structure fits within the screen.</span></span>  
  
 <span data-ttu-id="fd679-127">**Histogramas**</span><span class="sxs-lookup"><span data-stu-id="fd679-127">**Histograms**</span></span>  
 <span data-ttu-id="fd679-128">Selecione, para cada nó, o número de estados que podem ser exibidos no histograma.</span><span class="sxs-lookup"><span data-stu-id="fd679-128">Select the number of states that can be displayed in the histogram for each node.</span></span> <span data-ttu-id="fd679-129">Se o número de estados no modelo for menor que o valor que você selecionar, nenhuma barra adicional será exibida.</span><span class="sxs-lookup"><span data-stu-id="fd679-129">If the number of states in the model is fewer than the value you select, no additional bars are displayed.</span></span>  
  
 <span data-ttu-id="fd679-130">**Três**</span><span class="sxs-lookup"><span data-stu-id="fd679-130">**Tree**</span></span>  
 <span data-ttu-id="fd679-131">Escolha uma árvore para ser exibida no visualizador.</span><span class="sxs-lookup"><span data-stu-id="fd679-131">Choose a tree to display in the viewer.</span></span> <span data-ttu-id="fd679-132">Se você criar um modelo que tem vários atributos previsíveis, o algoritmo criará uma árvore separada para cada atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="fd679-132">If you create a model that has multiple predictable attributes, the algorithm creates a separate tree for each predictable attribute.</span></span>  
  
 <span data-ttu-id="fd679-133">**Tela de fundo**</span><span class="sxs-lookup"><span data-stu-id="fd679-133">**Background**</span></span>  
 <span data-ttu-id="fd679-134">Escolha um valor do atributo previsível para ser usado na representação da cor de fundo de cada nó.</span><span class="sxs-lookup"><span data-stu-id="fd679-134">Choose a value of the predictable attribute to use in representing the background color of each node.</span></span> <span data-ttu-id="fd679-135">Por exemplo, nos modelos de exemplo da AdventureWorks, se você definir **Segundo plano** como 1 ([Comprador de Bicicleta] = Sim), os nós serão escurecidos se tiverem uma proporção maior proporção de compradores de bicicleta.</span><span class="sxs-lookup"><span data-stu-id="fd679-135">For example, in the sample AdventureWorks models, if you set **Background** to 1 ([Bike Buyer] = Yes), the nodes are shaded darker if they have a greater proportion of bike buyers.</span></span> <span data-ttu-id="fd679-136">Esta opção fornece uma sugestão visual adicional sobre o significado das ramificações e nós na árvore.</span><span class="sxs-lookup"><span data-stu-id="fd679-136">This option provides an additional visual cue about the meaning of the branches and nodes in the tree.</span></span>  
  
 <span data-ttu-id="fd679-137">**Expansão padrão**</span><span class="sxs-lookup"><span data-stu-id="fd679-137">**Default Expansion**</span></span>  
 <span data-ttu-id="fd679-138">Escolha um valor da lista para definir o padrão para o número de níveis exibidos no gráfico de árvore.</span><span class="sxs-lookup"><span data-stu-id="fd679-138">Choose a value from the list to set the default for the number of levels displayed in the tree graph.</span></span>  
  
 <span data-ttu-id="fd679-139">**Mostrar Nível**</span><span class="sxs-lookup"><span data-stu-id="fd679-139">**Show Level**</span></span>  
 <span data-ttu-id="fd679-140">Mova a barra do controle deslizante para a direita ou esquerda para ajustar o número de níveis exibidos no gráfico de árvore.</span><span class="sxs-lookup"><span data-stu-id="fd679-140">Move the slider bar right or left to adjust the number of levels that are displayed in the tree graph.</span></span> <span data-ttu-id="fd679-141">Para ver todos os nós no modelo, deslize a barra completamente para a direita.</span><span class="sxs-lookup"><span data-stu-id="fd679-141">To see all the nodes in the model, slide the bar all the way to the right.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd679-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd679-142">See Also</span></span>  
 <span data-ttu-id="fd679-143">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="fd679-143">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="fd679-144">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="fd679-144">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="fd679-145">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="fd679-145">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
