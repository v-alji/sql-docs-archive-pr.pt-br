---
title: Navegando em um modelo de clustering | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- clustering [data mining]
- mining model, clustering
ms.assetid: 7f3f0949-d791-403a-88e2-54cb1a803dae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f1d508603acd29fde981bddc5642b54ca9413f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571135"
---
# <a name="browsing-a-clustering-model"></a><span data-ttu-id="c88ad-102">Procurando um modelo de clustering</span><span class="sxs-lookup"><span data-stu-id="c88ad-102">Browsing a Clustering Model</span></span>
  <span data-ttu-id="c88ad-103">Quando você abre um modelo de clustering usando **procurar**, o modelo é exibido em um visualizador interativo, semelhante ao Visualizador de clustering no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c88ad-103">When you open a clustering model using **Browse**, the model is displayed in an interactive viewer, similar to the clustering viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c88ad-104">O visualizador ajuda a explorar os clusters que foram criados e compreender características do cluster.</span><span class="sxs-lookup"><span data-stu-id="c88ad-104">The viewer helps you explore the clusters that were created, and understand cluster characteristics.</span></span> <span data-ttu-id="c88ad-105">Você também pode comparar e contrastar segmentos individuais com outros segmentos ou com a população.</span><span class="sxs-lookup"><span data-stu-id="c88ad-105">You can also compare and contrast individual segments with other segments or with the population.</span></span>  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="c88ad-106">Explorar o modelo</span><span class="sxs-lookup"><span data-stu-id="c88ad-106">Explore the Model</span></span>  
 <span data-ttu-id="c88ad-107">A janela **procurar** inclui as ferramentas a seguir para ajudá-lo a entender seu modelo de clustering e explorar os atributos dos grupos de dados subjacentes:</span><span class="sxs-lookup"><span data-stu-id="c88ad-107">The **Browse** window includes the following tools to help you understand your clustering model and explore the attributes of the underlying data groups:</span></span>  
  
-   [<span data-ttu-id="c88ad-108">Diagrama de Cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-108">Cluster Diagram</span></span>](#BKMK_ClusterDiagram)  
  
-   [<span data-ttu-id="c88ad-109">Perfis de cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-109">Cluster Profiles</span></span>](#BKMK_ClusterProfiles)  
  
-   [<span data-ttu-id="c88ad-110">Características do cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-110">Cluster Characteristics</span></span>](#BKMK_ClusterCharacteristics)  
  
-   [<span data-ttu-id="c88ad-111">Discriminação do Cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-111">Cluster Discrimination</span></span>](#BKMK_ClusterDiscrimination)  
  
 <span data-ttu-id="c88ad-112">Para experimentar um modelo de clustering, você pode usar os dados de exemplo na guia treinamento da pasta de trabalho de dados de exemplo e criar um modelo de clustering usando o [Assistente de cluster &#40;suplementos de mineração de dados para o Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) e todos os padrões.</span><span class="sxs-lookup"><span data-stu-id="c88ad-112">To experiment with a clustering model, you can use the sample data on the Training tab of the sample data workbook, and build a clustering model using [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) and all the defaults.</span></span>  
  
###  <a name="cluster-diagram"></a><a name="BKMK_ClusterDiagram"></a><span data-ttu-id="c88ad-113">Diagrama de cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-113">Cluster Diagram</span></span>  
 <span data-ttu-id="c88ad-114">A guia **diagrama de cluster** exibe todos os clusters que estão em um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="c88ad-114">The **Cluster Diagram** tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="c88ad-115">Aqui você pode ver quantos agrupamentos diferentes foram encontrados no conjunto de dados e a distância entre eles.</span><span class="sxs-lookup"><span data-stu-id="c88ad-115">Here you can see how many different groupings were found in your data set, and how near or far they are from each other.</span></span>  
  
##### <a name="explore-the-cluster-diagram"></a><span data-ttu-id="c88ad-116">Explorar o diagrama de cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-116">Explore the cluster diagram</span></span>  
  
1.  <span data-ttu-id="c88ad-117">Clique no cluster 1 no diagrama.</span><span class="sxs-lookup"><span data-stu-id="c88ad-117">Click Cluster 1 in the diagram.</span></span>  
  
     <span data-ttu-id="c88ad-118">Observe como as linhas cinza que conectam todos os clusters mudam de modo que as linhas que vão até o cluster selecionado são destacadas em azul brilhante.</span><span class="sxs-lookup"><span data-stu-id="c88ad-118">Note how the gray lines connecting all clusters change so that lines leading to the selected cluster are highlighted in bright blue.</span></span>  
  
     <span data-ttu-id="c88ad-119">![Introdução ao diagrama de cluster](media/dm13-cluster-diagram-intro.gif "Introdução ao diagrama de cluster")</span><span class="sxs-lookup"><span data-stu-id="c88ad-119">![cluster diagram intro](media/dm13-cluster-diagram-intro.gif "cluster diagram intro")</span></span>  
  
     <span data-ttu-id="c88ad-120">A intensidade da linha que conecta um cluster a outro expressa o grau de semelhança entre os clusters.</span><span class="sxs-lookup"><span data-stu-id="c88ad-120">The intensity of the line that connects one cluster to another represents the strength of the similarity of the clusters.</span></span> <span data-ttu-id="c88ad-121">Um sombreamento claro ou a ausência dele indica que os clusters não são muito parecidos.</span><span class="sxs-lookup"><span data-stu-id="c88ad-121">If the shading is light or nonexistent, the clusters are not very similar.</span></span> <span data-ttu-id="c88ad-122">Quanto mais escura a linha, mais forte a semelhança entre os dois clusters.</span><span class="sxs-lookup"><span data-stu-id="c88ad-122">As the line becomes darker, it indicates that the similarity between the two clusters is stronger.</span></span>  
  
2.  <span data-ttu-id="c88ad-123">Clique e arraste o controle deslizante para a esquerda do diagrama de cluster para ajustar o número de linhas exibido no visualizador.</span><span class="sxs-lookup"><span data-stu-id="c88ad-123">Click and drag the slider to the left of the cluster diagram, to adjust how many lines the viewer shows.</span></span>  
  
     <span data-ttu-id="c88ad-124">Quando você arrasta o controle deslizante para baixo, apenas os links mais importantes entre os clusters são mostrados.</span><span class="sxs-lookup"><span data-stu-id="c88ad-124">When you drag the slider down, only the strongest links between clusters are shown.</span></span> <span data-ttu-id="c88ad-125">Isso ajuda a se concentrar nos grupos relacionados.</span><span class="sxs-lookup"><span data-stu-id="c88ad-125">This helps you focus on related groups.</span></span>  
  
3.  <span data-ttu-id="c88ad-126">Observe o controle **variável de sombreamento** no canto superior direito da janela **diagrama de cluster** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-126">Notice the **Shading Variable** control in the upper right corner of the **Cluster Diagram** window.</span></span>  
  
     <span data-ttu-id="c88ad-127">Por padrão, ele é definido como **população**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-127">By default, it is set to **Population**.</span></span> <span data-ttu-id="c88ad-128">O que isso significa é que os clusters mais escuros têm o maior suporte.</span><span class="sxs-lookup"><span data-stu-id="c88ad-128">What this means is that the darker clusters have greater support.</span></span>  
  
4.  <span data-ttu-id="c88ad-129">Pause sobre qualquer cluster com o cursor.</span><span class="sxs-lookup"><span data-stu-id="c88ad-129">Pause over any cluster with the cursor.</span></span>  
  
     <span data-ttu-id="c88ad-130">Uma dica de ferramenta é exibida que contém a população daquele cluster.</span><span class="sxs-lookup"><span data-stu-id="c88ad-130">A ToolTip is displayed that contains the population of that cluster.</span></span>  
  
5.  <span data-ttu-id="c88ad-131">Agora, clique na lista suspensa **variável de sombreamento** e escolha a variável **idade** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-131">Now, click the **Shading Variable** dropdown list and choose the **Age** variable.</span></span> <span data-ttu-id="c88ad-132">Como você faz isso, uma lista de valores é exibida na caixa de texto **estado** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-132">As you do so, a list of values appears in the **State** text box.</span></span>  
  
     <span data-ttu-id="c88ad-133">A coluna Idade usada como entrada para este modelo contém valores numéricos contínuos, mas, para a finalidade de clustering, o algoritmo sempre discretiza números.</span><span class="sxs-lookup"><span data-stu-id="c88ad-133">The Age column used as input to this model contains continuous numeric values, but for the purpose of clustering, the algorithm always discretizes numbers.</span></span> <span data-ttu-id="c88ad-134">Aqui você pode ver os compartimentos ou grupos que o algoritmo criou, como "muito baixo ( \<=27)" and "Very High (> = 63)".</span><span class="sxs-lookup"><span data-stu-id="c88ad-134">Here you can see the bins, or groups that the algorithm created, such as "Very Low (\<=27)" and "Very High (>=63)".</span></span>  
  
6.  <span data-ttu-id="c88ad-135">Nas listas suspensas de **estado** , selecione **muito alto** e veja como o diagrama é alterado.</span><span class="sxs-lookup"><span data-stu-id="c88ad-135">From the **State** dropdown lists, select **Very High** and see how the diagram changes.</span></span>  
  
     <span data-ttu-id="c88ad-136">Ao alterar a variável de sombreamento, você pode ter uma noção de quais clusters contêm mais dessa faixa etária de destino e quais clusters contêm muito poucos clientes nessa faixa etária.</span><span class="sxs-lookup"><span data-stu-id="c88ad-136">By changing the shading variable, you can see at a glance which clusters contain more of this targeted age group, and which clusters contain very few customers in this age group.</span></span>  
  
     <span data-ttu-id="c88ad-137">![Modificar o diagrama de cluster para mostrar a idade](media/dm13-cluster-diagramshadebyage.gif "Modificar o diagrama de cluster para mostrar a idade")</span><span class="sxs-lookup"><span data-stu-id="c88ad-137">![Modify the cluster diagram to show age](media/dm13-cluster-diagramshadebyage.gif "Modify the cluster diagram to show age")</span></span>  
  
     <span data-ttu-id="c88ad-138">Quanto mais escuro o sombreamento, maior a proporção do atributo de destino e a distribuição de valor desse cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-138">The darker the shading, the larger the proportion of the target attribute and value distribution that cluster.</span></span>  
  
7.  <span data-ttu-id="c88ad-139">Localize o cluster que está sombreado mais escuro quando a **variável de sombreamento** é definida como Age >65.</span><span class="sxs-lookup"><span data-stu-id="c88ad-139">Locate the cluster that is shaded darkest when the **Shading Variable** is set to Age >65.</span></span>  
  
     <span data-ttu-id="c88ad-140">Passe o mouse sobre o cluster.</span><span class="sxs-lookup"><span data-stu-id="c88ad-140">Hover the mouse over the cluster.</span></span>  
  
     <span data-ttu-id="c88ad-141">O valor exibido na dica de ferramenta mostra a população de clientes neste cluster que tenha mais de 65.</span><span class="sxs-lookup"><span data-stu-id="c88ad-141">The value displayed in the ToolTip now shows you the population of customers in this cluster who are over 65.</span></span>  
  
8.  <span data-ttu-id="c88ad-142">Clique com o botão direito do mouse no cluster e selecione **renomear cluster**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-142">Right-click the cluster and select **Rename Cluster**.</span></span> <span data-ttu-id="c88ad-143">Digite um novo nome que seja descritivo, como **acima de 65**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-143">Type a new name that is descriptive, such as **Over 65**.</span></span> <span data-ttu-id="c88ad-144">O novo nome será salvo com o modelo no servidor e poderá ser usado para identificar o cluster nas outras exibições de clustering.</span><span class="sxs-lookup"><span data-stu-id="c88ad-144">The new name is saved with the model to the server and can be used for identifying the cluster in the other clustering views.</span></span>  
  
 [<span data-ttu-id="c88ad-145">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="c88ad-145">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-profiles"></a><a name="BKMK_ClusterProfiles"></a> <span data-ttu-id="c88ad-146">Perfis de Cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-146">Cluster Profiles</span></span>  
 <span data-ttu-id="c88ad-147">A guia **perfis de cluster** permite que você compare a composição de todos os clusters em um relance.</span><span class="sxs-lookup"><span data-stu-id="c88ad-147">The **Cluster Profiles** tab lets you compare the makeup of all clusters at a glance.</span></span> <span data-ttu-id="c88ad-148">Este é um bom local para iniciar quando você estiver se familiarizado com o modelo.</span><span class="sxs-lookup"><span data-stu-id="c88ad-148">This is a good place to start when you are getting familiar with the model.</span></span> <span data-ttu-id="c88ad-149">Esta exibição também será útil posteriormente, se você explorou um cluster específico e decidir que precisa localizar os relacionados.</span><span class="sxs-lookup"><span data-stu-id="c88ad-149">This view is also useful later on, if you have been exploring a particular cluster and decide you need to find related ones.</span></span>  
  
 <span data-ttu-id="c88ad-150">Os **perfis de cluster** também fornecem uma boa visão geral de como os clusters são diferentes uns dos outros.</span><span class="sxs-lookup"><span data-stu-id="c88ad-150">**Cluster Profiles** also gives you a good overview of how the clusters are different from each other.</span></span> <span data-ttu-id="c88ad-151">Consequentemente, pode ser conveniente usar essa exibição para dar a cada cluster um nome descritivo.</span><span class="sxs-lookup"><span data-stu-id="c88ad-151">Therefore, you might find it convenient to use this view to give each cluster a descriptive name.</span></span>  
  
##### <a name="explore-the-cluster-profiles"></a><span data-ttu-id="c88ad-152">Explorar os perfis de cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-152">Explore the cluster profiles</span></span>  
  
1.  <span data-ttu-id="c88ad-153">Clique na célula para obter ocupação, na coluna **Estados** , para ver a lista de todos os valores de ocupação.</span><span class="sxs-lookup"><span data-stu-id="c88ad-153">Click the cell for Occupations, in the **States** column, to see the list of all values for Occupation.</span></span>  
  
2.  <span data-ttu-id="c88ad-154">Agora mova o cursor sobre Ocupação nos perfis de cluster.</span><span class="sxs-lookup"><span data-stu-id="c88ad-154">Now move the cursor over Occupation in the cluster profiles.</span></span>  
  
     <span data-ttu-id="c88ad-155">A dica de ferramenta mostra a distribuição das ocupações nesse cluster.</span><span class="sxs-lookup"><span data-stu-id="c88ad-155">The ToolTip shows the distribution of occupations in that cluster.</span></span>  
  
     <span data-ttu-id="c88ad-156">![Exibir os valores detalhados em dicas de ferramenta ou na legenda](media/dm13-cluster-profile-age-tooltip.gif "Exibir os valores detalhados em dicas de ferramenta ou na legenda")</span><span class="sxs-lookup"><span data-stu-id="c88ad-156">![View detailed values in Tooltips or in Legend](media/dm13-cluster-profile-age-tooltip.gif "View detailed values in Tooltips or in Legend")</span></span>  
  
     <span data-ttu-id="c88ad-157">Observe que, em alguns clusters (como o no gráfico), a lista de ocupação não é concluída e algumas ocupaçãos são substituídas pelo rótulo, **outro**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-157">Notice that, in some clusters (such as the one in the graphic), the list of occupations is not complete, and some occupations are replaced with the label, **Other**.</span></span>  
  
     <span data-ttu-id="c88ad-158">Isso é proposital, pois pode ser difícil saber a diferença entre muitas barras pequenas em um histograma.</span><span class="sxs-lookup"><span data-stu-id="c88ad-158">This is by design, because it can be hard to tell the difference between many small bars in a histogram.</span></span> <span data-ttu-id="c88ad-159">Por padrão, somente as barras de importância mais alta são retidas e as barras restantes são agrupadas em um **outro** Bucket cinza.</span><span class="sxs-lookup"><span data-stu-id="c88ad-159">By default only the bars of highest importance are retained, and the remaining bars are grouped together into a gray **Other** bucket.</span></span>  
  
     <span data-ttu-id="c88ad-160">Para alterar o número de barras visíveis em qualquer histograma, use as **barras de histograma**de opção.</span><span class="sxs-lookup"><span data-stu-id="c88ad-160">To change the number of bars that are visible in any histogram, use the option **Histogram bars**.</span></span>  
  
3.  <span data-ttu-id="c88ad-161">Observe que a coluna **idade** é diferente das outras.</span><span class="sxs-lookup"><span data-stu-id="c88ad-161">Note that the **Age** column looks different from the others.</span></span> <span data-ttu-id="c88ad-162">Clique no losango no gráfico usado para representar a idade.</span><span class="sxs-lookup"><span data-stu-id="c88ad-162">Click the diamond in the chart used to represent Age.</span></span>  
  
     <span data-ttu-id="c88ad-163">A coluna Idade originalmente continha somente números contínuos.</span><span class="sxs-lookup"><span data-stu-id="c88ad-163">The column Age originally contained only continuous numbers.</span></span> <span data-ttu-id="c88ad-164">O algoritmo de clustering exige valores discretos e, portanto, agrupava os valores numéricos na coluna Idade em um número limitado de grupos de idade, com base na distribuição de valores.</span><span class="sxs-lookup"><span data-stu-id="c88ad-164">The clustering algorithm requires discrete values, so it grouped the numeric values in the Age column into a limited number of age groups, based on the distribution of values.</span></span>  
  
4.  <span data-ttu-id="c88ad-165">Clique em um dos gráficos de losangos em um perfil de cluster.</span><span class="sxs-lookup"><span data-stu-id="c88ad-165">Click one of the diamond charts in a cluster profile.</span></span>  
  
     <span data-ttu-id="c88ad-166">Esses gráficos de losangos são exibidos somente quando os dados de origem usam valores numéricos contínuos.</span><span class="sxs-lookup"><span data-stu-id="c88ad-166">These diamond charts are displayed only when the source data uses continuous numeric values.</span></span> <span data-ttu-id="c88ad-167">Os gráficos de losango fornecem algumas estatísticas descritivas úteis, inclusive o desvio médio e o padrão para esse valor em cada cluster:</span><span class="sxs-lookup"><span data-stu-id="c88ad-167">The diamond charts provide some useful descriptive statistics, including the mean and standard deviation for that value in each cluster:</span></span>  
  
    -   <span data-ttu-id="c88ad-168">A linha no gráfico de losangos representa o intervalo de valores para o atributo.</span><span class="sxs-lookup"><span data-stu-id="c88ad-168">The line in the diamond chart represents the range of values for the attribute.</span></span> <span data-ttu-id="c88ad-169">Os valores também são mostrados na coluna **Estados** à esquerda do gráfico de **perfis** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-169">The values are also shown in the **States** column at the left of the **Profiles** chart.</span></span>  
  
    -   <span data-ttu-id="c88ad-170">O centro do losango está posicionado na média para o nó.</span><span class="sxs-lookup"><span data-stu-id="c88ad-170">The center of the diamond is positioned at the mean for the node.</span></span>  
  
    -   <span data-ttu-id="c88ad-171">A largura do losango representa a variação do atributo nesse nó.</span><span class="sxs-lookup"><span data-stu-id="c88ad-171">The width of the diamond represents the variance of the attribute at that node.</span></span> <span data-ttu-id="c88ad-172">Portanto, um losango mais estreito indica que o nó pode criar uma previsão mais precisa.</span><span class="sxs-lookup"><span data-stu-id="c88ad-172">Therefore, a thinner diamond indicates that the node can create a more accurate prediction.</span></span>  
  
5.  <span data-ttu-id="c88ad-173">Para liberar mais espaço no grafo, clique com o botão direito do mouse em um cluster que você não precisa exibir imediatamente e selecione **Ocultar coluna**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-173">To make more room in the graph, right-click a cluster you don't need to view right away, and select **Hide Column**.</span></span> <span data-ttu-id="c88ad-174">Isso não o exclui do modelo, apenas recolhe a coluna temporariamente.</span><span class="sxs-lookup"><span data-stu-id="c88ad-174">This doesn't delete it from the model, just collapses the column temporarily.</span></span>  
  
     <span data-ttu-id="c88ad-175">Para exibir os clusters que você ocultou, você pode clicar e arrastar a borda da coluna ou selecionar o nome do cluster na lista, **mais clusters**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-175">To view clusters that you've hidden, you can click and drag the column edge, or select the cluster name from the list, **More clusters**.</span></span>  
  
6.  <span data-ttu-id="c88ad-176">Percorra a lista de atributos até localizar o comprador de bicicletas (Bike Buyer) e localize o cluster com a maior porcentagem de valores Sim.</span><span class="sxs-lookup"><span data-stu-id="c88ad-176">Scroll down the attribute list till you find Bike Buyer, and then find the cluster that has the highest percentage of Yes values.</span></span>  
  
     <span data-ttu-id="c88ad-177">Clique com o botão direito do mouse no título de coluna do cluster que você deseja renomear, selecione **renomear cluster**e digite **compradores de bicicleta**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-177">Right-click the column heading for the cluster that you want to rename, select **Rename cluster**, and type **Bike Buyers**.</span></span>  
  
     <span data-ttu-id="c88ad-178">O novo nome do cluster é persistido em todas as exibições e no servidor, até que você reprocesse o modelo.</span><span class="sxs-lookup"><span data-stu-id="c88ad-178">The new cluster name is persisted in all views, and on the server, until you reprocess the model.</span></span>  
  
     <span data-ttu-id="c88ad-179">![Renomear clusters para facilitar o uso do gráfico](media/dm13-cluster-rename.gif "Renomear clusters para facilitar o uso do gráfico")</span><span class="sxs-lookup"><span data-stu-id="c88ad-179">![Rename clusters to make chart easier to use](media/dm13-cluster-rename.gif "Rename clusters to make chart easier to use")</span></span>  
  
 <span data-ttu-id="c88ad-180">**Dicas**</span><span class="sxs-lookup"><span data-stu-id="c88ad-180">**Tips**</span></span>  
  
-   <span data-ttu-id="c88ad-181">Clique em um cabeçalho de coluna para classificar os atributos em ordem de importância para aquele cluster.</span><span class="sxs-lookup"><span data-stu-id="c88ad-181">Click a column heading to sort the attributes in order of importance for that cluster.</span></span>  
  
-   <span data-ttu-id="c88ad-182">Arraste as colunas para reordená-las no visualizador.</span><span class="sxs-lookup"><span data-stu-id="c88ad-182">Drag columns to reorder them in the viewer.</span></span>  
  
-   <span data-ttu-id="c88ad-183">Clique em qualquer célula no gráfico de perfis para exibir estatísticas detalhadas na **legenda de mineração**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-183">Click any cell in the profiles chart to view detailed statistics in the **Mining Legend**.</span></span>  
  
-   <span data-ttu-id="c88ad-184">Clique com o botão direito do mouse em qualquer célula e selecione **colunas de modelo de detalhamento** para gerar os dados subjacentes em uma nova planilha no Excel.</span><span class="sxs-lookup"><span data-stu-id="c88ad-184">Right-click any cell and select **Drillthrough model columns** to output the underlying data to a new worksheet in Excel.</span></span>  
  
-   <span data-ttu-id="c88ad-185">Clique com o botão direito do mouse no título de coluna do cluster e selecione **detalhamento para estruturar dados** para obter informações detalhadas sobre os membros do cluster que não foram incluídos no modelo.</span><span class="sxs-lookup"><span data-stu-id="c88ad-185">Right-click the cluster's column heading and select **Drillthrough to structure data** to get detailed information about the cluster members that wasn't included in the model.</span></span>  
  
     <span data-ttu-id="c88ad-186">Por exemplo, se você estiver criando perfis para clientes, poderá deixar as informações de contato nos dados subjacentes (a estrutura de mineração), mas não incluí-las no modelo, pois elas não são úteis para análise.</span><span class="sxs-lookup"><span data-stu-id="c88ad-186">For example, if you are profiling customers, you might leave the contact information in the underlying data (the mining structure) but not include it in the model, because it's not useful for analysis.</span></span> <span data-ttu-id="c88ad-187">Entretanto, depois que os clientes foram atribuídos aos clusters, você poderá exibir os dados detalhados usando o detalhamento.</span><span class="sxs-lookup"><span data-stu-id="c88ad-187">However, after customers have been assigned to clusters, you can view the detailed data by using drillthrough.</span></span>  
  
 [<span data-ttu-id="c88ad-188">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="c88ad-188">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-characteristics"></a><a name="BKMK_ClusterCharacteristics"></a> <span data-ttu-id="c88ad-189">Características do Cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-189">Cluster Characteristics</span></span>  
 <span data-ttu-id="c88ad-190">A exibição Características do Cluster permite que você realmente explore um único cluster, para localizar os atributos que caracterizam mais fortemente esse grupo de dados.</span><span class="sxs-lookup"><span data-stu-id="c88ad-190">The Cluster Characteristics view lets you really explore a single cluster, to find which attributes most strongly characterize this group of data.</span></span>  
  
##### <a name="explore-the-cluster-characteristics"></a><span data-ttu-id="c88ad-191">Explorar as características do cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-191">Explore the cluster characteristics</span></span>  
  
1.  <span data-ttu-id="c88ad-192">Selecione o cluster **Over 65** na lista de **clusters** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-192">Select the **Over 65** cluster from the **Cluster** list.</span></span>  
  
     <span data-ttu-id="c88ad-193">Depois de selecionado um cluster, é possível ver em detalhes as características particulares daquele cluster específico.</span><span class="sxs-lookup"><span data-stu-id="c88ad-193">After you select a cluster, you can see in detail the characteristics that make up that specific cluster.</span></span>  
  
     <span data-ttu-id="c88ad-194">Os atributos contidos no cluster são listados nas colunas **Variáveis** , e o estado do atributo listado é relacionado na coluna **Valores** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-194">The attributes that the cluster contains are listed in the **Variables** columns, and the state of the listed attribute is listed in the **Values** column.</span></span>  
  
     <span data-ttu-id="c88ad-195">Os Estados de atributo são listados em ordem de importância, acompanhado por sua probabilidade nesse cluster, representado como uma barra colorida na coluna **probabilidade** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-195">Attribute states are listed in order of importance, accompanied by their probability in this cluster, represented as a colored bar in the **Probability** column.</span></span>  
  
     <span data-ttu-id="c88ad-196">![Características de um modelo de clustering](media/dm13-cluster-characteristics.gif "Características de um modelo de clustering")</span><span class="sxs-lookup"><span data-stu-id="c88ad-196">![Characteristics of a clustering model](media/dm13-cluster-characteristics.gif "Characteristics of a clustering model")</span></span>  
  
2.  <span data-ttu-id="c88ad-197">Clique na coluna **variáveis** para classificar por atributo.</span><span class="sxs-lookup"><span data-stu-id="c88ad-197">Click the **Variables** column to sort by attribute.</span></span>  
  
     <span data-ttu-id="c88ad-198">Ao alterar a variável de classificação, você poderá ver mais facilmente como os valores das variáveis como renda ou propriedade de carros são distribuídos no grupo.</span><span class="sxs-lookup"><span data-stu-id="c88ad-198">By changing the sort variable, you can more easily see how values for variables such as income or car ownership are distributed in the group.</span></span>  
  
3.  <span data-ttu-id="c88ad-199">Clique em **copiar para o Excel**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-199">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="c88ad-200">Uma nova planilha é adicionada à pasta de trabalho que contém as características do cluster selecionado.</span><span class="sxs-lookup"><span data-stu-id="c88ad-200">A new worksheet is added to your workbook that contains the characteristics of the selected cluster.</span></span>  
  
4.  <span data-ttu-id="c88ad-201">Agora, escolha um cluster diferente na lista, **compradores de bicicleta**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-201">Now choose a different cluster from the list, **Bike Buyers**.</span></span>  
  
5.  <span data-ttu-id="c88ad-202">Clique em **copiar para o Excel**.</span><span class="sxs-lookup"><span data-stu-id="c88ad-202">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="c88ad-203">Observe que o gráfico das características do novo cluster é adicionado em sua própria planilha.</span><span class="sxs-lookup"><span data-stu-id="c88ad-203">Note that the new cluster characteristics chart is added on its own worksheet.</span></span> <span data-ttu-id="c88ad-204">Você pode movê-lo para a mesma planilha que o outro perfil para facilitar sua comparação, o que você fará na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="c88ad-204">You can move it onto the same worksheet as the other profile to make it easier to compare them, which you'll do in the next step.</span></span>  
  
 <span data-ttu-id="c88ad-205">**Dicas**</span><span class="sxs-lookup"><span data-stu-id="c88ad-205">**Tips**</span></span>  
  
-   <span data-ttu-id="c88ad-206">Observe que a característica principal do cliente no cluster em mais de 65 é que eles não compram seu produto!</span><span class="sxs-lookup"><span data-stu-id="c88ad-206">Note that the primary characteristic of the customer in the Over 65 cluster is that they don't buy your product!</span></span> <span data-ttu-id="c88ad-207">Se você quiser saber por que isso acontece, poderá procurar clusters e comparar grupos ou poderá criar um modelo relacionado usando um algoritmo que é bom em explorar causas e resultados, como, por exemplo, um modelo de árvore de decisão ou um modelo Naïve Bayes.</span><span class="sxs-lookup"><span data-stu-id="c88ad-207">If you want to know why this is so, you can browse clusters and compare groups, or you might create a related model using an algorithm that is good at exploring causes and outcomes, such as a decision tree model or a Naïve Bayes model.</span></span>  
  
-   <span data-ttu-id="c88ad-208">Se você quiser obter uma lista completa de atributos e probabilidades para este cluster (ou todos os clusters) poderá criar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="c88ad-208">If you want to get a complete list of attributes and probabilities for this cluster (or all clusters) you can create a query.</span></span> <span data-ttu-id="c88ad-209">Para obter exemplos de consultas em modelos de clustering, consulte [exemplos de consulta de modelo de clustering](data-mining/clustering-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="c88ad-209">For examples of queries on clustering models, see [Clustering Model Query Examples](data-mining/clustering-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="c88ad-210">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="c88ad-210">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-discrimination"></a><a name="BKMK_ClusterDiscrimination"></a><span data-ttu-id="c88ad-211">Discriminação de cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-211">Cluster Discrimination</span></span>  
 <span data-ttu-id="c88ad-212">Use a guia **discriminação de cluster** para comparar atributos entre dois clusters ou entre um cluster e todos os outros casos no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c88ad-212">You use the **Cluster Discrimination** tab to compare attributes between two clusters, or between a cluster and all the other cases in the data set.</span></span>  
  
 <span data-ttu-id="c88ad-213">Para destacar os recursos desse visualizador, vamos compará-lo com as tabelas lado a lado no Excel que você criou com base na exibição de **características do cluster** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-213">To highlight the features of this viewer, we'll compare it to the side-by-side tables in Excel that you created based on the **Cluster Characteristics** view.</span></span>  
  
##### <a name="explore-cluster-discrimination"></a><span data-ttu-id="c88ad-214">Explorar distinção de cluster</span><span class="sxs-lookup"><span data-stu-id="c88ad-214">Explore cluster discrimination</span></span>  
  
1.  <span data-ttu-id="c88ad-215">Use as listas **Cluster 1** e **Cluster 2** para selecionar os clusters a serem comparados.</span><span class="sxs-lookup"><span data-stu-id="c88ad-215">Use the **Cluster 1** and **Cluster 2** lists to select the clusters to compare.</span></span>  
  
    -   <span data-ttu-id="c88ad-216">Para o cluster 1, selecione Mais de 65.</span><span class="sxs-lookup"><span data-stu-id="c88ad-216">For Cluster 1, select Over 65.</span></span>  
  
    -   <span data-ttu-id="c88ad-217">Para o cluster 2, selecione Bike Buyers.</span><span class="sxs-lookup"><span data-stu-id="c88ad-217">For Cluster 2, select Bike Buyers.</span></span>  
  
     <span data-ttu-id="c88ad-218">A comparação deve ter aparência semelhante ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="c88ad-218">The comparison should look similar to the following graphic.</span></span>  
  
     <span data-ttu-id="c88ad-219">![comparar clusters em um modelo](media/dm13-cluster-compareclusters.gif "comparar clusters em um modelo")</span><span class="sxs-lookup"><span data-stu-id="c88ad-219">![comparing clusters in a model](media/dm13-cluster-compareclusters.gif "comparing clusters in a model")</span></span>  
  
     <span data-ttu-id="c88ad-220">Observe que, nos bastidores, o Visualizador de **discriminação de cluster** envia consultas complexas para o servidor de data mining, para extrair os atributos que são mais importantes na distinção entre os dois grupos, facilitando a comparação de dois conjuntos de clientes.</span><span class="sxs-lookup"><span data-stu-id="c88ad-220">Note that, under the covers, the **Cluster Discrimination** viewer sends complex queries to the data mining server, to extract the attributes that are most important in distinguishing between the two groups, making it easier to compare two sets of customers.</span></span>  
  
2.  <span data-ttu-id="c88ad-221">Clique em uma das colunas **favorecer...** .</span><span class="sxs-lookup"><span data-stu-id="c88ad-221">Click either of the **Favors...** columns.</span></span>  
  
     <span data-ttu-id="c88ad-222">A barra à direita do atributo e da lista de valores mostra quais recursos ou valores são mais importantes como uma característica do cluster selecionado.</span><span class="sxs-lookup"><span data-stu-id="c88ad-222">The bar to the right of the attribute and value list shows which features or values are most important as a characteristic of the selected cluster.</span></span>  
  
3.  <span data-ttu-id="c88ad-223">Agora compare as listas no Excel.</span><span class="sxs-lookup"><span data-stu-id="c88ad-223">Now compare the lists in Excel.</span></span>  
  
     <span data-ttu-id="c88ad-224">![Gráfico da rede de dependências para um modelo de associação](media/dm13-comparing-profiles-in-excel.gif "Gráfico da rede de dependências para um modelo de associação")</span><span class="sxs-lookup"><span data-stu-id="c88ad-224">![Dependency network graph for an association model](media/dm13-comparing-profiles-in-excel.gif "Dependency network graph for an association model")</span></span>  
  
     <span data-ttu-id="c88ad-225">Como as estatísticas subjacentes que foram usadas para criar a imagem no visualizador são salvas no Excel como tabelas, você pode filtrar e classificar, e exibir os valores reais de probabilidade.</span><span class="sxs-lookup"><span data-stu-id="c88ad-225">Because the underlying statistics that were used to build the image in the viewer are saved to Excel as tables, you can filter and sort, and view the actual probability values.</span></span>  
  
     <span data-ttu-id="c88ad-226">Além de usar o Excel, recomendamos que você tente o visualizador de cluster para o Visio, que também permite que você exiba não apenas pontos de dados, mas também extensivamente modifique e aprimore o gráfico.</span><span class="sxs-lookup"><span data-stu-id="c88ad-226">In addition to using Excel, we recommend that you try the cluster viewer for Visio, which also allows you to not just view data points but also extensively modify and enhance the graph.</span></span> <span data-ttu-id="c88ad-227">Para obter mais informações, consulte [passo a passos de diagrama de Cluster &#40;suplementos de mineração de dados&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c88ad-227">For more information, see [Cluster Diagram Walkthrough &#40;Data Mining Add-ins&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span></span>  
  
 <span data-ttu-id="c88ad-228">**Dicas**</span><span class="sxs-lookup"><span data-stu-id="c88ad-228">**Tips**</span></span>  
  
 <span data-ttu-id="c88ad-229">Depois de obter algumas informações sobre grupos de clientes, tente usar o cenário [What-If &#40;ferramentas de análise de tabela para o&#41;do Excel](what-if-scenario-table-analysis-tools-for-excel.md) ou [cenário de busca de metas &#40;ferramentas de análise de tabela para ferramentas de&#41;do Excel](goal-seek-scenario-table-analysis-tools-for-excel.md) , para explorar fatores no modelo que podem ser alterados para afetar o resultado.</span><span class="sxs-lookup"><span data-stu-id="c88ad-229">After getting some insights into groups of customers, try using the [What-If Scenario &#40;Table Analysis Tools for Excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) or [Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) tools, to explore factors in the model that might be changed to affect the outcome.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88ad-230">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c88ad-230">See Also</span></span>  
 <span data-ttu-id="c88ad-231">[Pesquisando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="c88ad-231">[Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="c88ad-232">Assistente de cluster &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c88ad-232">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
  
