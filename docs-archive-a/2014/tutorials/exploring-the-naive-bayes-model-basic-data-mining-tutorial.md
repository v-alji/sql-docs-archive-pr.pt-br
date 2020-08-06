---
title: Explorando o modelo Naive Bayes (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b06708d5-4477-4a51-bf8d-0b1e3c1f9ebb
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a26fa972e1ed50e2f4107026210a5935fcb86d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681974"
---
# <a name="exploring-the-naive-bayes-model-basic-data-mining-tutorial"></a><span data-ttu-id="a6910-102">Explorando o modelo Naive Bayes (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="a6910-102">Exploring the Naive Bayes Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="a6910-103">O [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Naive Bayes fornece vários métodos para exibir a interação entre a compra de bicicletas e os atributos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a6910-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm provides several methods for displaying the interaction between bike buying and the input attributes.</span></span>  
  
 <span data-ttu-id="a6910-104">O [!INCLUDE[msCoName](../includes/msconame-md.md)] Visualizador do Naive Bayes fornece as seguintes guias para uso em explorando os modelos de mineração do Naive Bayes:</span><span class="sxs-lookup"><span data-stu-id="a6910-104">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for use in exploring Naive Bayes mining models:</span></span>  
  
 
  
##  <a name="dependency-network"></a><a name="DependencyNetwork"></a><span data-ttu-id="a6910-105">Rede de dependências</span><span class="sxs-lookup"><span data-stu-id="a6910-105">Dependency Network</span></span>  
 <span data-ttu-id="a6910-106">A guia **rede de dependências** funciona da mesma maneira que a guia **rede de dependências** para o [!INCLUDE[msCoName](../includes/msconame-md.md)] Visualizador de árvore.</span><span class="sxs-lookup"><span data-stu-id="a6910-106">The **Dependency Network** tab works in the same way as the **Dependency Network** tab for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer.</span></span> <span data-ttu-id="a6910-107">Cada nó no visualizador representa um atributo e as linhas entre os nós representam as relações.</span><span class="sxs-lookup"><span data-stu-id="a6910-107">Each node in the viewer represents an attribute, and the lines between nodes represent relationships.</span></span> <span data-ttu-id="a6910-108">No visualizador, você pode ver todos os atributos que afetam o estado do atributo de previsão, Comprador de Bicicletas.</span><span class="sxs-lookup"><span data-stu-id="a6910-108">In the viewer, you can see all the attributes that affect the state of the predictable attribute, Bike Buyer.</span></span>  
  
#### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="a6910-109">Para explorar o modelo na guia Rede de Dependências</span><span class="sxs-lookup"><span data-stu-id="a6910-109">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="a6910-110">Use a lista **modelo de mineração** na parte superior da guia Visualizador do modelo de **mineração** para alternar para o `TM_NaiveBayes` modelo.</span><span class="sxs-lookup"><span data-stu-id="a6910-110">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_NaiveBayes` model.</span></span>  
  
2.  <span data-ttu-id="a6910-111">Use a lista de **visualizadores** para alternar para **o Visualizador do Microsoft Naive Bayes**.</span><span class="sxs-lookup"><span data-stu-id="a6910-111">Use the **Viewer** list to switch to **Microsoft Naive Bayes Viewer**.</span></span>  
  
3.  <span data-ttu-id="a6910-112">Clique no `Bike Buyer` nó para identificar suas dependências.</span><span class="sxs-lookup"><span data-stu-id="a6910-112">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="a6910-113">O sombreamento rosa indica que todos os atributos influenciam a compra de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="a6910-113">The pink shading indicates that all of the attributes have an effect on bike buying.</span></span>  
  
4.  <span data-ttu-id="a6910-114">Ajuste o controle deslizante para identificar o atributo mais influente.</span><span class="sxs-lookup"><span data-stu-id="a6910-114">Adjust the slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="a6910-115">À medida que você abaixa o controle deslizante, somente os atributos com o efeito maior sobre a coluna [Comprador de Bicicleta] permanecem.</span><span class="sxs-lookup"><span data-stu-id="a6910-115">As you lower the slider, only the attributes that have the greatest effect on the [Bike Buyer] column remain.</span></span> <span data-ttu-id="a6910-116">Ao ajustar o controle deslizante, você poderá descobrir que alguns dos atributos mais influentes são: o número de carros, distância do trabalho e número total de crianças.</span><span class="sxs-lookup"><span data-stu-id="a6910-116">By adjusting the slider, you can discover that a few of the most influential attributes are: number of cars owned, commute distance, and total number of children.</span></span>  
 
  
##  <a name="attribute-profiles"></a><a name="AttributeProfiles"></a> <span data-ttu-id="a6910-117">Perfis de Atributo</span><span class="sxs-lookup"><span data-stu-id="a6910-117">Attribute Profiles</span></span>  
 <span data-ttu-id="a6910-118">A guia **perfis de atributo** descreve como Estados diferentes dos atributos de entrada afetam o resultado do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="a6910-118">The **Attribute Profiles** tab describes how different states of the input attributes affect the outcome of the predictable attribute.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-profiles-tab"></a><span data-ttu-id="a6910-119">Para explorar o modelo na guia Perfis de Atributo</span><span class="sxs-lookup"><span data-stu-id="a6910-119">To explore the model in the Attribute Profiles tab</span></span>  
  
1.  <span data-ttu-id="a6910-120">Na caixa **previsível** , verifique se `Bike Buyer` está selecionado.</span><span class="sxs-lookup"><span data-stu-id="a6910-120">In the **Predictable** box, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="a6910-121">Se a **legenda de mineração** estiver bloqueando a exibição dos **perfis de atributo**, mova-o para fora do caminho.</span><span class="sxs-lookup"><span data-stu-id="a6910-121">If the **Mining Legend** is blocking display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="a6910-122">Na caixa barras de **histograma** , selecione **5**.</span><span class="sxs-lookup"><span data-stu-id="a6910-122">In the **Histogram** bars box, select **5**.</span></span>  
  
     <span data-ttu-id="a6910-123">Em nosso modelo, 5 é o número máximo de estados para qualquer variável.</span><span class="sxs-lookup"><span data-stu-id="a6910-123">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
     <span data-ttu-id="a6910-124">Os atributos que afetam o estado desse atributo previsível estão listados juntos com os valores de cada estado dos atributos de entrada e suas distribuições em cada estado do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="a6910-124">The attributes that affect the state of this predictable attribute are listed together with the values of each state of the input attributes and their distributions in each state of the predictable attribute.</span></span>  
  
4.  <span data-ttu-id="a6910-125">Na coluna **atributos** , encontre **número de carros de propriedade**.</span><span class="sxs-lookup"><span data-stu-id="a6910-125">In the **Attributes** column, find **Number Cars Owned**.</span></span>  <span data-ttu-id="a6910-126">Observe as diferenças nos histogramas de compradores de bicicleta (coluna rotulada 1) e não compradores de bicicleta (coluna rotulada 0).</span><span class="sxs-lookup"><span data-stu-id="a6910-126">Notice the differences in the histograms for bike buyers (column labeled 1) and non-buyers (column labeled 0).</span></span> <span data-ttu-id="a6910-127">Uma pessoa com nenhum ou com um carro tem muito mais probabilidade de comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="a6910-127">A person with zero or one car is much more likely to buy a bike.</span></span>  
  
5.  <span data-ttu-id="a6910-128">Clique duas vezes na célula **número de carros** no comprador de bicicletas (coluna rotulada 1).</span><span class="sxs-lookup"><span data-stu-id="a6910-128">Double-click the **Number Cars Owned** cell in the bike buyer (column labeled 1) column.</span></span>  
  
     <span data-ttu-id="a6910-129">A **legenda de mineração** exibe uma exibição mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="a6910-129">The **Mining Legend** displays a more detailed view.</span></span>  
  
  
##  <a name="attribute-characteristics"></a><a name="AttributeCharacteristics"></a> <span data-ttu-id="a6910-130">Características do Atributo</span><span class="sxs-lookup"><span data-stu-id="a6910-130">Attribute Characteristics</span></span>  
 <span data-ttu-id="a6910-131">Com a guia **características do atributo** , você pode selecionar um atributo e um valor para ver com que frequência os valores de outros atributos aparecem nos casos de valores selecionados.</span><span class="sxs-lookup"><span data-stu-id="a6910-131">With the **Attribute Characteristics** tab, you can select an attribute and value to see how frequently values for other attributes appear in the selected value cases.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-characteristics-tab"></a><span data-ttu-id="a6910-132">Para explorar o modelo na guia Características do Atributo</span><span class="sxs-lookup"><span data-stu-id="a6910-132">To explore the model in the Attribute Characteristics tab</span></span>  
  
1.  <span data-ttu-id="a6910-133">Na lista **atributo** , verifique se `Bike Buyer` está selecionado.</span><span class="sxs-lookup"><span data-stu-id="a6910-133">In the **Attribute** list, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="a6910-134">Defina o **valor** como **1**.</span><span class="sxs-lookup"><span data-stu-id="a6910-134">Set the **Value** to **1**.</span></span>  
  
     <span data-ttu-id="a6910-135">No visualizador, você verá que clientes sem filhos em casa, com pequenas distâncias até o trabalho e que moram na região da América do Norte têm mais probabilidade de comprarem uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="a6910-135">In the viewer, you will see that customers who have no children at home, short commutes, and live in the North America region are more likely to buy a bike.</span></span>  
  
  
##  <a name="attribute-discrimination"></a><a name="AttributeDiscrimination"></a> <span data-ttu-id="a6910-136">Distinção de Atributo</span><span class="sxs-lookup"><span data-stu-id="a6910-136">Attribute Discrimination</span></span>  
 <span data-ttu-id="a6910-137">Com a guia **discriminação de atributo** , você pode investigar a relação entre dois valores discretos de compra de bicicletas e outros valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="a6910-137">With the **Attribute Discrimination** tab, you can investigate the relationship between two discrete values of bike buying and other attribute values.</span></span> <span data-ttu-id="a6910-138">Como o `TM_NaiveBayes` modelo tem apenas dois Estados, 1 e 0, você não precisa fazer nenhuma alteração no visualizador.</span><span class="sxs-lookup"><span data-stu-id="a6910-138">Because the `TM_NaiveBayes` model has only two states, 1 and 0, you do not have to make any changes to the viewer.</span></span>  
  
 <span data-ttu-id="a6910-139">No visualizador, você pode ver que as pessoas que não têm carro tendem a comprar bicicletas, e que as pessoas que têm dois carros tendem a não comprar bicicletas.</span><span class="sxs-lookup"><span data-stu-id="a6910-139">In the viewer, you can see that people who do not own cars tend to buy bicycles, and people who own two cars tend not to buy bicycles.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a6910-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a6910-140">Related Tasks</span></span>  
 <span data-ttu-id="a6910-141">Consulte os tópicos a seguir para explorar os outros modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="a6910-141">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="a6910-142">Exploração do modelo de árvore de decisão &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="a6910-142">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="a6910-143">Explorando o modelo de clustering &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="a6910-143">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="a6910-144">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="a6910-144">Next Lesson</span></span>  
 [<span data-ttu-id="a6910-145">Lição 5: testando modelos &#40;o tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="a6910-145">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="a6910-146">Tarefa anterior da lição</span><span class="sxs-lookup"><span data-stu-id="a6910-146">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="a6910-147">Explorando o modelo de clustering &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="a6910-147">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6910-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a6910-148">See Also</span></span>  
 <span data-ttu-id="a6910-149">[Procurar um modelo usando o Visualizador do Microsoft Naive Bayes](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="a6910-149">[Browse a Model Using the Microsoft Naive Bayes Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span></span>  
 <span data-ttu-id="a6910-150">[Guia discriminação de atributo &#40;Visualizador do modelo de mineração&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="a6910-150">[Attribute Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="a6910-151">[Guia perfis de atributo &#40;Visualizador do modelo de mineração&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="a6910-151">[Attribute Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="a6910-152">[Guia características do atributo &#40;o Visualizador do modelo de mineração&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="a6910-152">[Attribute Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="a6910-153">Guia rede de dependências &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="a6910-153">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md)  
  
  
