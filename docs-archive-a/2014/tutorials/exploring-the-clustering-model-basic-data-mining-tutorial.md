---
title: Explorando o modelo de clustering (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ce8aa034-161b-473f-baec-9c29e0a8e5f5
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: cca9d395fece59f607c8faf209128b9d32663a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686006"
---
# <a name="exploring-the-clustering-model-basic-data-mining-tutorial"></a><span data-ttu-id="d8a01-102">Explorando o modelo de clustering (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="d8a01-102">Exploring the Clustering Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="d8a01-103">O [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de clustering agrupa casos em clusters que contêm características semelhantes.</span><span class="sxs-lookup"><span data-stu-id="d8a01-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm groups cases into clusters that contain similar characteristics.</span></span> <span data-ttu-id="d8a01-104">Esses agrupamentos são úteis para explorar dados, identificando anomalias nos dados e criar previsões.</span><span class="sxs-lookup"><span data-stu-id="d8a01-104">These groupings are useful for exploring data, identifying anomalies in the data, and creating predictions.</span></span>  
  
 <span data-ttu-id="d8a01-105">O Visualizador de Cluster da [!INCLUDE[msCoName](../includes/msconame-md.md)] fornece as seguintes guias para serem usadas na exploração de modelos de mineração de cluster:</span><span class="sxs-lookup"><span data-stu-id="d8a01-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Cluster Viewer provides the following tabs for use in exploring clustering mining models:</span></span>  
  

  
##  <a name="cluster-diagram-tab"></a><a name="ClusterDiagramTab"></a><span data-ttu-id="d8a01-106">Guia diagrama de cluster</span><span class="sxs-lookup"><span data-stu-id="d8a01-106">Cluster Diagram Tab</span></span>  
 <span data-ttu-id="d8a01-107">A guia Diagrama de Cluster exibe todos os clusters existentes em um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="d8a01-107">The Cluster Diagram tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="d8a01-108">As linhas entre os clusters representam "proximidade" e estão sombreadas com base no grau de semelhança que os clusters têm.</span><span class="sxs-lookup"><span data-stu-id="d8a01-108">The lines between the clusters represent "closeness" and are shaded based on how similar the clusters are.</span></span> <span data-ttu-id="d8a01-109">A cor real de cada cluster representa a frequência da variável e o estado no cluster.</span><span class="sxs-lookup"><span data-stu-id="d8a01-109">The actual color of each cluster represents the frequency of the variable and the state in the cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-diagram-tab"></a><span data-ttu-id="d8a01-110">Para explorar o modelo na guia Diagrama de Cluster</span><span class="sxs-lookup"><span data-stu-id="d8a01-110">To explore the model in the Cluster Diagram tab</span></span>  
  
1.  <span data-ttu-id="d8a01-111">Use a lista **modelo de mineração** na parte superior da guia Visualizador do modelo de **mineração** para alternar para o `TM_Clustering` modelo.</span><span class="sxs-lookup"><span data-stu-id="d8a01-111">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_Clustering` model.</span></span>  
  
2.  <span data-ttu-id="d8a01-112">Na lista **Visualizador** , selecione **Visualizador de cluster da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="d8a01-112">In the **Viewer** list, select **Microsoft Cluster Viewer**.</span></span>  
  
3.  <span data-ttu-id="d8a01-113">Na caixa **variável de sombreamento** , selecione **comprador de bicicleta**.</span><span class="sxs-lookup"><span data-stu-id="d8a01-113">In the **Shading Variable** box, select **Bike Buyer**.</span></span>  
  
     <span data-ttu-id="d8a01-114">A variável padrão é **população**, mas você pode alterá-la para qualquer atributo no modelo, para descobrir quais clusters contêm membros que têm os atributos desejados.</span><span class="sxs-lookup"><span data-stu-id="d8a01-114">The default variable is **Population**, but you can change this to any attribute in the model, to discover which clusters contain members that have the attributes you want.</span></span>  
  
4.  <span data-ttu-id="d8a01-115">Selecione **1** na caixa **estado** para explorar os casos em que uma bicicleta foi comprada.</span><span class="sxs-lookup"><span data-stu-id="d8a01-115">Select **1** in the **State** box to explore those cases where a bike was purchased.</span></span>  
  
     <span data-ttu-id="d8a01-116">A legenda de **densidade** descreve a densidade do par de estado de atributo selecionado na variável de sombreamento e o estado.</span><span class="sxs-lookup"><span data-stu-id="d8a01-116">The **Density** legend describes the density of the attribute state pair selected in the Shading Variable and the State.</span></span> <span data-ttu-id="d8a01-117">Neste exemplo, ele nos informa que a clusterwith do sombreamento mais escuro tem o percentual mais alto de compradores de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="d8a01-117">In this example it tells us that the clusterwith the darkest shading has the highest percentage of bike buyers.</span></span>  
  
5.  <span data-ttu-id="d8a01-118">Coloque o seu mouse sobre o cluster com o sombreamento mais escuro.</span><span class="sxs-lookup"><span data-stu-id="d8a01-118">Pause your mouse over the cluster with the darkest shading.</span></span>  
  
     <span data-ttu-id="d8a01-119">Uma dica de ferramenta exibe a porcentagem de casos que têm o atributo `Bike Buyer = 1`.</span><span class="sxs-lookup"><span data-stu-id="d8a01-119">A tooltip displays the percentage of cases that have the attribute, `Bike Buyer = 1`.</span></span>  
  
6.  <span data-ttu-id="d8a01-120">Selecione o cluster que tem a densidade mais alta, clique com o botão direito do mouse no cluster, selecione **renomear cluster** e tipo **compradores de bicicletas alto** para identificação posterior.</span><span class="sxs-lookup"><span data-stu-id="d8a01-120">Select the cluster that has the highest density, right-click the cluster, select **Rename Cluster** and type **Bike Buyers High** for later identification.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="d8a01-121">Localize o cluster com o sombreamento mais claro (e a menor densidade).</span><span class="sxs-lookup"><span data-stu-id="d8a01-121">Find the cluster that has the lightest shading (and the lowest density).</span></span> <span data-ttu-id="d8a01-122">Clique com o botão direito do mouse no cluster, selecione **renomear cluster** e tipo de **compradores de bicicleta baixo**.</span><span class="sxs-lookup"><span data-stu-id="d8a01-122">Right-click the cluster, select **Rename Cluster** and type **Bike Buyers Low**.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="d8a01-123">Clique no cluster de **compradores de bicicletas alto** e arraste-o para uma área do painel que lhe dará uma visão clara de suas conexões com os outros clusters.</span><span class="sxs-lookup"><span data-stu-id="d8a01-123">Click the **Bike Buyers High** cluster and drag it to an area of the pane that will give you a clear view of its connections to the other clusters.</span></span>  
  
     <span data-ttu-id="d8a01-124">Quando você seleciona um cluster, as linhas que conectam esse cluster a outros são realçadas para que você possa facilmente ver todas as relações desse cluster.</span><span class="sxs-lookup"><span data-stu-id="d8a01-124">When you select a cluster, the lines that connect this cluster to other clusters are highlighted, so that you can easily see all the relationships for this cluster.</span></span> <span data-ttu-id="d8a01-125">Quando o cluster não estiver selecionado, você poderá dizer pela escuridão das linhas o grau de importância das relações entre todos os clusters do diagrama.</span><span class="sxs-lookup"><span data-stu-id="d8a01-125">When the cluster is not selected, you can tell by the darkness of the lines how strong the relationships are amongst all the clusters in the diagram.</span></span> <span data-ttu-id="d8a01-126">Um sombreamento claro ou a ausência dele indica que os clusters não são muito parecidos.</span><span class="sxs-lookup"><span data-stu-id="d8a01-126">If the shading is light or nonexistent, the clusters are not very similar.</span></span>  
  
9. <span data-ttu-id="d8a01-127">Use o controle deslizante à esquerda da rede para filtrar os links menos importantes e encontrar os clusters com relações mais próximas.</span><span class="sxs-lookup"><span data-stu-id="d8a01-127">Use the slider to the left of the network, to filter out the weaker links and find the clusters with the closest relationships.</span></span> <span data-ttu-id="d8a01-128">O departamento de marketing da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] pode querer combinar clusters similares na determinação do melhor método de entrega da mala direta.</span><span class="sxs-lookup"><span data-stu-id="d8a01-128">The [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department might want to combine similar clusters together when determining the best method for delivering the targeted mailing.</span></span>  
  

  
##  <a name="cluster-profiles-tab"></a><a name="ClusterProfilesTab"></a><span data-ttu-id="d8a01-129">Guia perfis de cluster</span><span class="sxs-lookup"><span data-stu-id="d8a01-129">Cluster Profiles Tab</span></span>  
 <span data-ttu-id="d8a01-130">A guia **perfis de cluster** fornece uma visão geral do `TM_Clustering` modelo.</span><span class="sxs-lookup"><span data-stu-id="d8a01-130">The **Cluster Profiles** tab provides an overall view of the `TM_Clustering` model.</span></span> <span data-ttu-id="d8a01-131">A guia **perfis de cluster** contém uma coluna para cada cluster no modelo.</span><span class="sxs-lookup"><span data-stu-id="d8a01-131">The **Cluster Profiles** tab contains a column for each cluster in the model.</span></span> <span data-ttu-id="d8a01-132">A primeira coluna listas os atributos associados a pelo menos um cluster.</span><span class="sxs-lookup"><span data-stu-id="d8a01-132">The first column lists the attributes that are associated with at least one cluster.</span></span> <span data-ttu-id="d8a01-133">O resto do visualizador contém a distribuição dos estados de um atributo para cada cluster.</span><span class="sxs-lookup"><span data-stu-id="d8a01-133">The rest of the viewer contains the distribution of the states of an attribute for each cluster.</span></span> <span data-ttu-id="d8a01-134">A distribuição de uma variável discreta é mostrada como uma barra colorida com o número máximo de barras exibidas na lista de **barras de histograma** .</span><span class="sxs-lookup"><span data-stu-id="d8a01-134">The distribution of a discrete variable is shown as a colored bar with the maximum number of bars displayed in the **Histogram bars** list.</span></span> <span data-ttu-id="d8a01-135">São exibidos atributos contínuos com um gráfico de diamante que representa o desvio médio e padrão em cada cluster.</span><span class="sxs-lookup"><span data-stu-id="d8a01-135">Continuous attributes are displayed with a diamond chart, which represents the mean and standard deviation in each cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-profiles-tab"></a><span data-ttu-id="d8a01-136">Para explorar o modelo na guia Perfis de Cluster</span><span class="sxs-lookup"><span data-stu-id="d8a01-136">To explore the model in the Cluster Profiles tab</span></span>  
  
1.  <span data-ttu-id="d8a01-137">Defina as barras de **histograma** como **5**.</span><span class="sxs-lookup"><span data-stu-id="d8a01-137">Set **Histogram** bars to **5**.</span></span>  
  
     <span data-ttu-id="d8a01-138">Em nosso modelo, 5 é o número máximo de estados para qualquer variável.</span><span class="sxs-lookup"><span data-stu-id="d8a01-138">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
2.  <span data-ttu-id="d8a01-139">Se a **legenda de mineração** bloquear a exibição dos **perfis de atributo**, mova-o para fora do caminho.</span><span class="sxs-lookup"><span data-stu-id="d8a01-139">If the **Mining Legend** blocks the display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="d8a01-140">Selecione a coluna **alto dos compradores de bicicleta** e arraste-a para a direita da coluna de **população** .</span><span class="sxs-lookup"><span data-stu-id="d8a01-140">Select the **Bike Buyers High** column and drag it to the right of the **Population** column.</span></span>  
  
4.  <span data-ttu-id="d8a01-141">Selecione a coluna de **compradores de bicicletas de baixa** e arraste-a para a direita da coluna alto dos compradores de **bicicletas** .</span><span class="sxs-lookup"><span data-stu-id="d8a01-141">Select the **Bike Buyers Low** column and drag it to the right of the **Bike Buyers High** column.</span></span>  
  
5.  <span data-ttu-id="d8a01-142">Clique na coluna **alto dos compradores de bicicletas** .</span><span class="sxs-lookup"><span data-stu-id="d8a01-142">Click the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="d8a01-143">A coluna **Variables** é classificada em ordem de importância para esse cluster.</span><span class="sxs-lookup"><span data-stu-id="d8a01-143">The **Variables** column is sorted in order of importance for that cluster.</span></span> <span data-ttu-id="d8a01-144">Navegue pela coluna e examine as características do cluster Altos Compradores de Bicicleta.</span><span class="sxs-lookup"><span data-stu-id="d8a01-144">Scroll through the column and review characteristics of the Bike Buyer High cluster.</span></span> <span data-ttu-id="d8a01-145">Por exemplo, é mais provável que eles tenham um caminho curto para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="d8a01-145">For example, they are more likely to have a short commute.</span></span>  
  
6.  <span data-ttu-id="d8a01-146">Clique duas vezes na célula **age** na coluna **alta dos compradores de bicicletas** .</span><span class="sxs-lookup"><span data-stu-id="d8a01-146">Double-click the **Age** cell in the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="d8a01-147">A **legenda de mineração** exibe uma exibição mais detalhada e você pode ver a faixa etária desses clientes, bem como a idade média.</span><span class="sxs-lookup"><span data-stu-id="d8a01-147">The **Mining Legend** displays a more detailed view and you can see the age range of these customers as well as the mean age.</span></span>  
  
7.  <span data-ttu-id="d8a01-148">Clique com o botão direito do mouse na coluna de **compradores de bicicletas baixo** e selecione **Ocultar coluna**.</span><span class="sxs-lookup"><span data-stu-id="d8a01-148">Right-click the **Bike Buyers Low** column and select **Hide Column**.</span></span>  
  

  
##  <a name="cluster-characteristics-tab"></a><a name="ClusterCharacteristicsTab"></a><span data-ttu-id="d8a01-149">Guia características do cluster</span><span class="sxs-lookup"><span data-stu-id="d8a01-149">Cluster Characteristics Tab</span></span>  
 <span data-ttu-id="d8a01-150">Com a guia **características do cluster** , você pode examinar mais detalhadamente as características que compõem um cluster.</span><span class="sxs-lookup"><span data-stu-id="d8a01-150">With the **Cluster Characteristics** tab, you can examine in more detail the characteristics that make up a cluster.</span></span> <span data-ttu-id="d8a01-151">Em vez de comparar as características de todos os clusters (como na guia Perfis de Cluster), você pode explorar um cluster por vez.</span><span class="sxs-lookup"><span data-stu-id="d8a01-151">Instead of comparing the characteristics of all of the clusters (as in the Cluster Profiles tab), you can explore one cluster at a time.</span></span> <span data-ttu-id="d8a01-152">Por exemplo, se você selecionar **compradores de bicicleta alto** na lista de **clusters** , poderá ver as características dos clientes neste cluster.</span><span class="sxs-lookup"><span data-stu-id="d8a01-152">For example, if you select **Bike Buyers High** from the **Cluster** list, you can see the characteristics of the customers in this cluster.</span></span> <span data-ttu-id="d8a01-153">Embora a exibição seja diferente do visualizador Perfis de Cluster, as informações são as mesmas.</span><span class="sxs-lookup"><span data-stu-id="d8a01-153">Though the display is different from the Cluster Profiles viewer, the findings are the same.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8a01-154">A menos que você defina um valor inicial para **HoldoutSeed**, os resultados variarão cada vez que você processar o modelo.</span><span class="sxs-lookup"><span data-stu-id="d8a01-154">Unless you set an initial value for **holdoutseed**, results will vary each time you process the model.</span></span> <span data-ttu-id="d8a01-155">Para obter mais informações, consulte [elemento HoldoutSeed](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span><span class="sxs-lookup"><span data-stu-id="d8a01-155">For more information, see [HoldoutSeed Element](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span></span>  
  

  
##  <a name="cluster-discrimination-tab"></a><a name="ClusterDiscriminationTab"></a><span data-ttu-id="d8a01-156">Guia discriminação de cluster</span><span class="sxs-lookup"><span data-stu-id="d8a01-156">Cluster Discrimination Tab</span></span>  
 <span data-ttu-id="d8a01-157">Com a guia **discriminação de cluster** , você pode explorar as características que distinguem um cluster de outro.</span><span class="sxs-lookup"><span data-stu-id="d8a01-157">With the **Cluster Discrimination** tab, you can explore the characteristics that distinguish one cluster from another.</span></span> <span data-ttu-id="d8a01-158">Depois de selecionar dois clusters, um da lista **cluster 1** e outro na lista **cluster 2** , o visualizador calcula as diferenças entre os clusters e exibe uma lista dos atributos que distinguem os clusters.</span><span class="sxs-lookup"><span data-stu-id="d8a01-158">After you select two clusters, one from the **Cluster 1** list, and one from the **Cluster 2** list, the viewer calculates the differences between the clusters and displays a list of the attributes that distinguish the clusters most.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-discrimination-tab"></a><span data-ttu-id="d8a01-159">Para explorar o modelo na guia Distinção de Cluster</span><span class="sxs-lookup"><span data-stu-id="d8a01-159">To explore the model in the Cluster Discrimination tab</span></span>  
  
1.  <span data-ttu-id="d8a01-160">Na caixa **cluster 1** , selecione **compradores de bicicleta alto**.</span><span class="sxs-lookup"><span data-stu-id="d8a01-160">In the **Cluster 1** box, select **Bike Buyers High**.</span></span>  
  
2.  <span data-ttu-id="d8a01-161">Na caixa **cluster 2** , selecione **compradores de bicicleta baixo**.</span><span class="sxs-lookup"><span data-stu-id="d8a01-161">In the **Cluster 2** box, select **Bike Buyers Low**.</span></span>  
  
3.  <span data-ttu-id="d8a01-162">Clique em **variáveis** para classificar em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="d8a01-162">Click **Variables** to sort alphabetically.</span></span>  
  
     <span data-ttu-id="d8a01-163">Algumas das diferenças mais substanciais entre os clientes nos **compradores de bicicletas baixos** e os **compradores de bicicletas altos** são os clusters com idade, Propriedade do carro, número de filhos e região.</span><span class="sxs-lookup"><span data-stu-id="d8a01-163">Some of the more substantial differences among the customers in the **Bike Buyers Low** and **Bike Buyers High** clusters include age, car ownership, number of children, and region.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d8a01-164">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d8a01-164">Related Tasks</span></span>  
 <span data-ttu-id="d8a01-165">Consulte os tópicos a seguir para explorar os outros modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="d8a01-165">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="d8a01-166">Exploração do modelo de árvore de decisão &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="d8a01-166">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="d8a01-167">Explorando o Naive Bayes do modelo de mineração de dados &#40;Basic&#41;</span><span class="sxs-lookup"><span data-stu-id="d8a01-167">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d8a01-168">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="d8a01-168">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d8a01-169">Explorando o Naive Bayes do modelo de mineração de dados &#40;Basic&#41;</span><span class="sxs-lookup"><span data-stu-id="d8a01-169">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="d8a01-170">Tarefa anterior da lição</span><span class="sxs-lookup"><span data-stu-id="d8a01-170">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="d8a01-171">Exploração do modelo de árvore de decisão &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="d8a01-171">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8a01-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8a01-172">See Also</span></span>  
 <span data-ttu-id="d8a01-173">[Procurar um modelo usando o Visualizador de cluster da Microsoft](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d8a01-173">[Browse a Model Using the Microsoft Cluster Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span></span>  
 <span data-ttu-id="d8a01-174">[Guia discriminação de cluster &#40;Visualizador do modelo de mineração&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d8a01-174">[Cluster Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="d8a01-175">[Guia perfis de cluster &#40;Visualizador do modelo de mineração&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d8a01-175">[Cluster Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="d8a01-176">[Guia características do cluster &#40;Visualizador do modelo de mineração&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d8a01-176">[Cluster Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="d8a01-177">Guia diagrama de cluster &#40;Visualizador do modelo de mineração&#41;</span><span class="sxs-lookup"><span data-stu-id="d8a01-177">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/cluster-diagram-tab-mining-model-viewer.md)  
  
  
