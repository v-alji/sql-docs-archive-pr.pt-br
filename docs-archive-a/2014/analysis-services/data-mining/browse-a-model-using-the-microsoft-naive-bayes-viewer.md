---
title: Procurar um modelo usando o Microsoft Naive Bayes Viewer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discrimination [Analysis Services]
- naive bayes model [Analysis Services]
- Bayesian classifiers
- mining model content, viewing
- predictive modeling [Analysis Services]
- Naive Bayes Viewer [Analysis Services]
- data mining [Analysis Services], predictive modeling
- Microsoft Naive Bayes Viewer
- histograms [Analysis Services]
- mining models [Analysis Services], predictive modeling
- dependencies [Analysis Services]
ms.assetid: 19743095-63c1-4486-8c1d-2efc143243be
author: minewiskan
ms.author: owend
ms.openlocfilehash: 03469e73d82a389426f91d8757630f50fe78fc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583931"
---
# <a name="browse-a-model-using-the-microsoft-naive-bayes-viewer"></a><span data-ttu-id="56372-102">Procurar um modelo usando o Visualizador do Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="56372-102">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>
  <span data-ttu-id="56372-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visualizador do Naive Bayes no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] exibe modelos de mineração criados com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] algoritmo Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="56372-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm.</span></span> <span data-ttu-id="56372-104">O algoritmo Naive Bayes da [!INCLUDE[msCoName](../../includes/msconame-md.md)] é um algoritmo de classificação altamente adaptável para tarefas de modelagem com previsão.</span><span class="sxs-lookup"><span data-stu-id="56372-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm is a classification algorithm that is highly adaptable to predictive modeling tasks.</span></span> <span data-ttu-id="56372-105">Para obter mais informações sobre esse algoritmo, consulte [Referência técnica do algoritmo Naive Bayes da Microsoft](microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="56372-105">For more information about this algorithm, see [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="56372-106">Como um dos principais objetivos de um modelo Naive Bayes é fornecer uma maneira de explorar rapidamente os dados em um conjunto de dados, o Visualizador Naive Bayes da [!INCLUDE[msCoName](../../includes/msconame-md.md)] fornece vários métodos para exibir a interação entre atributos previsíveis e os atributos de entrada.</span><span class="sxs-lookup"><span data-stu-id="56372-106">Because one of the main purposes of a naive Bayes model is to provide a way to quickly explore the data in a dataset, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides several methods for displaying the interaction between predictable attributes and input attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56372-107">Se desejar exibir informações detalhadas sobre as equações usadas no modelo e os padrões descobertos, você poderá alternar para o Visualizador de Árvore de Conteúdo Genérica da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56372-107">If you want to view detailed information about the equations used in the model and the patterns that were discovered, you can switch to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="56372-108">Para obter mais informações, consulte [Procurar um modelo usando o Visualizador de Árvore de Conteúdo Genérica da Microsoft](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) ou [Visualizador de Árvore de Conteúdo Genérica da Microsoft &#40;Mineração de Dados&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="56372-108">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="56372-109">Guias do Visualizador</span><span class="sxs-lookup"><span data-stu-id="56372-109">Viewer Tabs</span></span>  
 <span data-ttu-id="56372-110">Quando você navega em um modelo de mineração do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], ele é exibido na guia **Visualizador do Modelo de Mineração** do Designer de Mineração de Dados no visualizador adequado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="56372-110">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="56372-111">O Visualizador Naive Bayes da [!INCLUDE[msCoName](../../includes/msconame-md.md)] fornece as seguintes guias para explorar dados:</span><span class="sxs-lookup"><span data-stu-id="56372-111">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for exploring data:</span></span>  
  
-   [<span data-ttu-id="56372-112">Rede de Dependências</span><span class="sxs-lookup"><span data-stu-id="56372-112">Dependency Network</span></span>](#BKMK_Dependency)  
  
-   [<span data-ttu-id="56372-113">Perfis de atributo</span><span class="sxs-lookup"><span data-stu-id="56372-113">Attribute Profiles</span></span>](#BKMK_Profiles)  
  
-   [<span data-ttu-id="56372-114">Características do atributo</span><span class="sxs-lookup"><span data-stu-id="56372-114">Attribute Characteristics</span></span>](#BKMK_Characteristics)  
  
-   [<span data-ttu-id="56372-115">Discriminação de atributo</span><span class="sxs-lookup"><span data-stu-id="56372-115">Attribute Discrimination</span></span>](#BKMK_Discrimination)  
  
##  <a name="dependency-network"></a><a name="BKMK_Dependency"></a><span data-ttu-id="56372-116">Rede de dependências</span><span class="sxs-lookup"><span data-stu-id="56372-116">Dependency Network</span></span>  
 <span data-ttu-id="56372-117">A guia **Rede de Dependências** exibe as dependências entre os atributos de entrada e os atributos previsíveis em um modelo.</span><span class="sxs-lookup"><span data-stu-id="56372-117">The **Dependency Network** tab displays the dependencies between the input attributes and the predictable attributes in a model.</span></span> <span data-ttu-id="56372-118">O controle deslizante à esquerda do visualizador funciona como um filtro vinculado aos pontos fortes das dependências.</span><span class="sxs-lookup"><span data-stu-id="56372-118">The slider at the left of the viewer acts as a filter that is tied to the strengths of the dependencies.</span></span> <span data-ttu-id="56372-119">Diminuindo o controle deslizante, somente os links mais fortes serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="56372-119">Lowering the slider shows only the strongest links.</span></span>  
  
 <span data-ttu-id="56372-120">Quando você selecionar um nó, o visualizador destacará as dependências específicas ao nó.</span><span class="sxs-lookup"><span data-stu-id="56372-120">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="56372-121">Por exemplo, se você escolher um nó previsível, o visualizador também realçará cada nó que ajuda a prever o nó previsível.</span><span class="sxs-lookup"><span data-stu-id="56372-121">For example, if you choose a predictable node, the viewer also highlights each node that helps predict the predictable node.</span></span>  
  
 <span data-ttu-id="56372-122">A legenda na parte inferior do visualizador vincula os nós de cores ao tipo de dependência no gráfico.</span><span class="sxs-lookup"><span data-stu-id="56372-122">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="56372-123">Por exemplo, quando você seleciona um nó previsível, ele fica sombreado na cor turquesa e os nós que preveem o nó selecionado são sombreados em laranja.</span><span class="sxs-lookup"><span data-stu-id="56372-123">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="56372-124">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="56372-124">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-profiles"></a><a name="BKMK_Profiles"></a> <span data-ttu-id="56372-125">Perfis de Atributo</span><span class="sxs-lookup"><span data-stu-id="56372-125">Attribute Profiles</span></span>  
 <span data-ttu-id="56372-126">A guia **Perfis de Atributos** exibe histogramas em uma grade.</span><span class="sxs-lookup"><span data-stu-id="56372-126">The **Attribute Profiles** tab displays histograms in a grid.</span></span> <span data-ttu-id="56372-127">Você pode usar essa grade para comparar o atributo previsível selecionado na caixa **Previsível** com todos os outros atributos que estão no modelo.</span><span class="sxs-lookup"><span data-stu-id="56372-127">You can use this grid to compare the predictable attribute that you select in the **Predictable** box to all other attributes that are in the model.</span></span> <span data-ttu-id="56372-128">Cada coluna na guia representa um estado do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="56372-128">Each column in the tab represents a state of the predictable attribute.</span></span> <span data-ttu-id="56372-129">Se o atributo previsível tiver muitos estados, você poderá alterar o número de estados exibidos no histograma ajustando as **Barras de histograma**.</span><span class="sxs-lookup"><span data-stu-id="56372-129">If the predictable attribute has many states, you can change the number of states that appear in the histogram by adjusting the **Histogram bars**.</span></span> <span data-ttu-id="56372-130">Se o número que você escolher for menor do que o número total de estados no atributo, os estados estarão listados na ordem de suporte, com os outros estados coletados em um único recipiente cinza.</span><span class="sxs-lookup"><span data-stu-id="56372-130">If the number you choose is less than the total number of states in the attribute, the states are listed in order of support, with the remaining states collected into a single gray bucket.</span></span>  
  
 <span data-ttu-id="56372-131">Para exibir uma Legenda de Mineração que relaciona as cores do histograma aos estados de um atributo, clique na caixa de seleção **Mostrar Legenda** .</span><span class="sxs-lookup"><span data-stu-id="56372-131">To display a Mining Legend that relates the colors of the histogram to the states of an attribute, click the **Show Legend** check box.</span></span> <span data-ttu-id="56372-132">A Legenda de Mineração também exibe a distribuição de casos para cada par atributo-valor selecionado.</span><span class="sxs-lookup"><span data-stu-id="56372-132">The Mining Legend also displays the distribution of cases for each attribute-value pair that you select.</span></span>  
  
 <span data-ttu-id="56372-133">Para copiar o conteúdo da grade para a Área de Transferência como uma tabela HTML, clique com o botão direito do mouse na guia **Perfis de Atributo** e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="56372-133">To copy the contents of the grid to the Clipboard as an HTML table, right-click the **Attribute Profiles** tab and select **Copy**.</span></span>  
  
 [<span data-ttu-id="56372-134">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="56372-134">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-characteristics"></a><a name="BKMK_Characteristics"></a> <span data-ttu-id="56372-135">Características do Atributo</span><span class="sxs-lookup"><span data-stu-id="56372-135">Attribute Characteristics</span></span>  
 <span data-ttu-id="56372-136">Para usar a guia **Características do Atributo** , selecione um atributo previsível na lista **Atributo** e selecione um estado do atributo selecionado na lista **Valor** .</span><span class="sxs-lookup"><span data-stu-id="56372-136">To use the **Attribute Characteristics** tab, select a predictable attribute from the **Attribute** list and select a state of the selected attribute from the **Value** list.</span></span> <span data-ttu-id="56372-137">Quando você define essas variáveis, a guia **Características do Atributo** exibe os estados dos atributos associados ao caso selecionado do atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="56372-137">When you set these variables, the **Attribute Characteristics** tab displays the states of the attributes that are associated with the selected case of the selected attribute.</span></span> <span data-ttu-id="56372-138">Os atributos são classificados por importância.</span><span class="sxs-lookup"><span data-stu-id="56372-138">The attributes are sorted by importance.</span></span>  
  
 [<span data-ttu-id="56372-139">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="56372-139">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-discrimination"></a><a name="BKMK_Discrimination"></a> <span data-ttu-id="56372-140">Distinção de Atributo</span><span class="sxs-lookup"><span data-stu-id="56372-140">Attribute Discrimination</span></span>  
 <span data-ttu-id="56372-141">Para usar a guia **Discriminação de Atributo** , selecione um atributo previsível e dois de seus estados nas listas **Atributo**, **Valor 1**e **Valor 2** .</span><span class="sxs-lookup"><span data-stu-id="56372-141">To use the **Attribute Discrimination** tab, select a predictable attribute and two of its states from the **Attribute**, **Value 1**, and **Value 2** lists.</span></span> <span data-ttu-id="56372-142">A grade da guia **Discriminação de Atributo** exibe as seguintes informações nas colunas:</span><span class="sxs-lookup"><span data-stu-id="56372-142">The grid on the **Attribute Discrimination** tab then displays the following information in columns:</span></span>  
  
 <span data-ttu-id="56372-143">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="56372-143">**Attribute**</span></span>  
 <span data-ttu-id="56372-144">Lista outros atributos do conjunto de dados que contêm um estado que altamente favorece um estado do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="56372-144">Lists other attributes in the dataset that contain a state that highly favors one state of the predictable attribute.</span></span>  
  
 <span data-ttu-id="56372-145">**Valores**</span><span class="sxs-lookup"><span data-stu-id="56372-145">**Values**</span></span>  
 <span data-ttu-id="56372-146">Mostra o valor do atributo na coluna **Atributo**.</span><span class="sxs-lookup"><span data-stu-id="56372-146">Shows the value of the attribute in the **Attribute** column.</span></span>  
  
 <span data-ttu-id="56372-147">**Enfatiza\<value 1>**</span><span class="sxs-lookup"><span data-stu-id="56372-147">**Favors \<value 1>**</span></span>  
 <span data-ttu-id="56372-148">Mostra uma barra colorida que indica como o valor do atributo favorece significativamente o valor do atributo previsível mostrado em **Valor 1**.</span><span class="sxs-lookup"><span data-stu-id="56372-148">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 1**.</span></span>  
  
 <span data-ttu-id="56372-149">**Enfatiza\<value 2>**</span><span class="sxs-lookup"><span data-stu-id="56372-149">**Favors \<value 2>**</span></span>  
 <span data-ttu-id="56372-150">Mostra uma barra colorida que indica como o valor do atributo favorece significativamente o valor do atributo previsível mostrado em **Valor 2**.</span><span class="sxs-lookup"><span data-stu-id="56372-150">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 2**.</span></span>  
  
 [<span data-ttu-id="56372-151">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="56372-151">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="56372-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56372-152">See Also</span></span>  
 <span data-ttu-id="56372-153">[Algoritmo do Microsoft Naive Bayes](microsoft-naive-bayes-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="56372-153">[Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md) </span></span>  
 <span data-ttu-id="56372-154">[Tarefas e instruções do Visualizador do modelo de mineração](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="56372-154">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="56372-155">[Ferramentas de mineração de dados](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="56372-155">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="56372-156">Visualizadores do Modelo de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="56372-156">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  
