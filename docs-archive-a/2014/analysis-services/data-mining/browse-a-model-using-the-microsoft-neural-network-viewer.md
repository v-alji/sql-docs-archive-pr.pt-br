---
title: Procurar um modelo usando o Visualizador de rede neural da Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining model content, viewing
- classification mining model [Analysis Services]
- Microsoft Neural Network Viewer
- regression algorithms [Analysis Services]
- Neural Network Viewer [Analysis Services]
- neural network model [Analysis Services]
ms.assetid: 2343d746-c4f4-499b-9d3c-17d63310a9a3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 77e08955d09b7995e34ac94b75f809a303ca0d2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583928"
---
# <a name="browse-a-model-using-the-microsoft-neural-network-viewer"></a><span data-ttu-id="f408f-102">Procurar um modelo usando o Visualizador de Rede Neural da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f408f-102">Browse a Model Using the Microsoft Neural Network Viewer</span></span>
  <span data-ttu-id="f408f-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visualizador de rede neural no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] exibe modelos de mineração criados com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] algoritmo rede neural.</span><span class="sxs-lookup"><span data-stu-id="f408f-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm.</span></span> <span data-ttu-id="f408f-104">O algoritmo de Rede Neural da [!INCLUDE[msCoName](../../includes/msconame-md.md)] cria modelos de mineração para classificação e regressão que podem analisar várias entradas e saídas, e é muito útil para análises abertas e exploração.</span><span class="sxs-lookup"><span data-stu-id="f408f-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network algorithm creates classification and regression mining models that can analyze multiple inputs and outputs, and is very useful for open-ended analyses and exploration.</span></span> <span data-ttu-id="f408f-105">Para obter mais informações sobre esse algoritmo, consulte [Microsoft Neural Network Algorithm](microsoft-neural-network-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="f408f-105">For more information about this algorithm, see [Microsoft Neural Network Algorithm](microsoft-neural-network-algorithm.md).</span></span>  
  
 <span data-ttu-id="f408f-106">Ao explorar um modelo usando o Visualizador de Rede Neural da [!INCLUDE[msCoName](../../includes/msconame-md.md)] , você costuma obter um atributo e um estado de destino e, depois, usa o visualizador para ver como os atributos de entrada afetam o resultado</span><span class="sxs-lookup"><span data-stu-id="f408f-106">When you explore a model using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network Viewer, you typically pick some target attribute and state, and then use the viewer to see how input attributes affect the outcome</span></span>  
  
 <span data-ttu-id="f408f-107">Por exemplo, digamos que você conheça estes fatos sobre uma classe de clientes em potencial:</span><span class="sxs-lookup"><span data-stu-id="f408f-107">For example, suppose you know these facts about a class of potential customers:</span></span>  
  
-   <span data-ttu-id="f408f-108">Meia idade (entre 40 e 50 anos de idade).</span><span class="sxs-lookup"><span data-stu-id="f408f-108">Middle aged (40 to 50 years old).</span></span>  
  
-   <span data-ttu-id="f408f-109">Tem casa própria.</span><span class="sxs-lookup"><span data-stu-id="f408f-109">Owns a home.</span></span>  
  
-   <span data-ttu-id="f408f-110">Tem dois filhos que ainda moram em casa.</span><span class="sxs-lookup"><span data-stu-id="f408f-110">Has two children who still live at home.</span></span>  
  
 <span data-ttu-id="f408f-111">Como correlacionar estes atributos à probabilidade de que o cliente faça uma compra?</span><span class="sxs-lookup"><span data-stu-id="f408f-111">How can you correlate these attributes with the likelihood that the customer will make a purchase?</span></span>  
  
 <span data-ttu-id="f408f-112">Criando um modelo de rede neural usando o comportamento de compra como o resultado final, você pode explorar várias combinações em atributos de clientes, como renda alta, e descobrir como a combinação de atributos tem maior probabilidade de influenciar o comportamento de compra.</span><span class="sxs-lookup"><span data-stu-id="f408f-112">By building a neural network model using purchasing behavior as the target outcome, you can explore multiple combinations on customer attributes, such as high income, and discover which combination of attributes is most likely to influence purchasing behavior.</span></span> <span data-ttu-id="f408f-113">Por exemplo, talvez você descubra que o fator determinante é a distância percorrida por eles até o trabalho.</span><span class="sxs-lookup"><span data-stu-id="f408f-113">For example, you might discover that the determining factor is the distance that they commute to work.</span></span>  
  
 <span data-ttu-id="f408f-114">Se precisar obter mais informações detalhadas de exibição, como as equações que representam cada padrão descoberto, você poderá alternar exibições e usar o Visualizador de Árvores de Conteúdo Genérico da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f408f-114">If you need to more view detailed information, such as the equations that represent each pattern that was discovered, you can switch views and use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="f408f-115">Para obter mais informações, consulte [Procurar um modelo usando o Visualizador de Árvore de Conteúdo Genérica da Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) ou [Visualizador de Árvore de Conteúdo Genérica da Microsoft &#40;Mineração de Dados&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f408f-115">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="f408f-116">Guias do Visualizador</span><span class="sxs-lookup"><span data-stu-id="f408f-116">Viewer Tabs</span></span>  
 <span data-ttu-id="f408f-117">Quando você navega em um modelo de mineração do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], ele é exibido na guia **Visualizador do Modelo de Mineração** do Designer de Mineração de Dados no visualizador adequado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="f408f-117">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="f408f-118">O Visualizador de Rede Neural da [!INCLUDE[msCoName](../../includes/msconame-md.md)] oferece as seguintes guias para uso na exploração de modelos de mineração de rede neural:</span><span class="sxs-lookup"><span data-stu-id="f408f-118">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Neural Network Viewer provides the following tabs for use in exploring neural network mining models:</span></span>  
  
-   [<span data-ttu-id="f408f-119">Entradas</span><span class="sxs-lookup"><span data-stu-id="f408f-119">Inputs</span></span>](#BKMK_Inputs)  
  
-   [<span data-ttu-id="f408f-120">Saídas</span><span class="sxs-lookup"><span data-stu-id="f408f-120">Outputs</span></span>](#BKMK_Outputs)  
  
-   [<span data-ttu-id="f408f-121">Variáveis</span><span class="sxs-lookup"><span data-stu-id="f408f-121">Variables</span></span>](#BKMK_Characteristics)  
  
###  <a name="inputs"></a><a name="BKMK_Inputs"></a><span data-ttu-id="f408f-122">Informações</span><span class="sxs-lookup"><span data-stu-id="f408f-122">Inputs</span></span>  
 <span data-ttu-id="f408f-123">Use a guia **Entradas** para escolher os atributos e valores usados pelo modelo como entradas.</span><span class="sxs-lookup"><span data-stu-id="f408f-123">Use the **Inputs** tab to choose the attributes and values that the model used as inputs.</span></span> <span data-ttu-id="f408f-124">Por padrão, o visualizador é aberto com todos os atributos incluídos.</span><span class="sxs-lookup"><span data-stu-id="f408f-124">By default, the viewer opens with all attributes included.</span></span> <span data-ttu-id="f408f-125">Nesta exibição padrão, o modelo escolhe os valores de atributo mais importantes para exibição.</span><span class="sxs-lookup"><span data-stu-id="f408f-125">In this default view, the model chooses which attribute values are the most important to display.</span></span>  
  
 <span data-ttu-id="f408f-126">Para selecionar um atributo de entrada, clique dentro da coluna **Atributo** da grade **Entrada** e selecione um atributo na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="f408f-126">To select an input attribute, click inside the **Attribute** column of the **Input** grid, and select an attribute from the drop-down list.</span></span> <span data-ttu-id="f408f-127">(Somente os atributos incluídos no modelo são incluídos na lista.)</span><span class="sxs-lookup"><span data-stu-id="f408f-127">(Only attributes that are included in the model are included in the list.)</span></span>  
  
 <span data-ttu-id="f408f-128">O primeiro valor específico é exibido na coluna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="f408f-128">The first distinct value appears under the **Value** column.</span></span> <span data-ttu-id="f408f-129">Quando você clica no valor padrão, uma lista com todos os possíveis estados do atributo associado é exibida.</span><span class="sxs-lookup"><span data-stu-id="f408f-129">Clicking the default value reveals a list that contains all the possible states of the associated attribute.</span></span> <span data-ttu-id="f408f-130">Você pode selecionar o estado que deseja verificar.</span><span class="sxs-lookup"><span data-stu-id="f408f-130">You can select the state that you want to investigate.</span></span> <span data-ttu-id="f408f-131">É possível selecionar quantos atributos desejar.</span><span class="sxs-lookup"><span data-stu-id="f408f-131">You can select as many attributes as you want.</span></span>  
  
 [<span data-ttu-id="f408f-132">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="f408f-132">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="outputs"></a><a name="BKMK_Outputs"></a><span data-ttu-id="f408f-133">Produz</span><span class="sxs-lookup"><span data-stu-id="f408f-133">Outputs</span></span>  
 <span data-ttu-id="f408f-134">Use a guia **Saídas** para escolher o atributo de resultado a ser investigado.</span><span class="sxs-lookup"><span data-stu-id="f408f-134">Use the **Outputs** tab to choose the outcome attribute to investigate.</span></span> <span data-ttu-id="f408f-135">Você pode escolher dois estados de resultado a serem comparados, assumindo que as colunas foram definidas como atributos previsíveis quando o modelo foi criado.</span><span class="sxs-lookup"><span data-stu-id="f408f-135">You can choose any two outcome states to compare, assuming the columns were defined as predictable attributes when the model was created.</span></span>  
  
 <span data-ttu-id="f408f-136">Use a lista **OutputAttribute** para selecionar um atributo.</span><span class="sxs-lookup"><span data-stu-id="f408f-136">Use the **OutputAttribute** list to select an attribute.</span></span> <span data-ttu-id="f408f-137">Você pode selecionar dois estados associados ao atributo nas listas **Valor 1** e **Valor 2** .</span><span class="sxs-lookup"><span data-stu-id="f408f-137">You can then select two states that are associated with the attribute from the **Value 1** and **Value 2** lists.</span></span> <span data-ttu-id="f408f-138">Esses dois estados do atributo de saída serão comparados no painel **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="f408f-138">These two states of the output attribute will be compared in the **Variables** pane.</span></span>  
  
 [<span data-ttu-id="f408f-139">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="f408f-139">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="variables"></a><a name="BKMK_Characteristics"></a><span data-ttu-id="f408f-140">As</span><span class="sxs-lookup"><span data-stu-id="f408f-140">Variables</span></span>  
 <span data-ttu-id="f408f-141">A grade na guia **Variáveis** contém as seguintes colunas: **Atributo**, **Valor**, **Preferências [valor 1]** e **Preferências [valor 2]**.</span><span class="sxs-lookup"><span data-stu-id="f408f-141">The grid in the **Variables** tab contains the following columns: **Attribute**, **Value**, **Favors [value 1]**, and **Favors [value 2]**.</span></span> <span data-ttu-id="f408f-142">Por padrão, as colunas são classificadas pela força de **Preferências [valor 1]**.</span><span class="sxs-lookup"><span data-stu-id="f408f-142">By default, the columns are sorted by the strength of **Favors [value 1]**.</span></span> <span data-ttu-id="f408f-143">Clicar no cabeçalho de uma coluna altera a ordem de classificação para a coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="f408f-143">Clicking a column heading changes the sort order to the selected column.</span></span>  
  
 <span data-ttu-id="f408f-144">Uma barra à direita do atributo mostra qual estado do atributo de saída o estado atributo de entrada especificado prefere.</span><span class="sxs-lookup"><span data-stu-id="f408f-144">A bar to the right of the attribute shows which state of the output attribute the specified input attribute state favors.</span></span> <span data-ttu-id="f408f-145">O tamanho da barra mostra como o estado de saída favorece significativamente o estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="f408f-145">The size of the bar shows how strongly the output state favors the input state.</span></span>  
  
 [<span data-ttu-id="f408f-146">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="f408f-146">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="f408f-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f408f-147">See Also</span></span>  
 <span data-ttu-id="f408f-148">[Algoritmo rede neural da Microsoft](microsoft-neural-network-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="f408f-148">[Microsoft Neural Network Algorithm](microsoft-neural-network-algorithm.md) </span></span>  
 <span data-ttu-id="f408f-149">[Tarefas e instruções do Visualizador do modelo de mineração](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="f408f-149">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="f408f-150">[Tarefas e instruções do Visualizador do modelo de mineração](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="f408f-150">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="f408f-151">[Ferramentas de mineração de dados](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f408f-151">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="f408f-152">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="f408f-152">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  
