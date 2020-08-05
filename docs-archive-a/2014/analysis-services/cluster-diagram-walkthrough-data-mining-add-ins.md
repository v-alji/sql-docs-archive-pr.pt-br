---
title: Instruções do diagrama de cluster (suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ee8cce3cd2498d765c9b69e7f352b49cb0f115
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571692"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="f15f5-102">Passo a passo do diagrama de Cluster (Suplementos de Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="f15f5-102">Cluster Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="f15f5-103">Depois de criar um modelo de clustering, você pode importá-lo para o Visio usando a forma de **cluster** e, em seguida, continuar a personalizar e aprimorar o layout.</span><span class="sxs-lookup"><span data-stu-id="f15f5-103">After you have created a clustering model, you can import it into Visio using the **Cluster** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="f15f5-104">As **formas de mineração de dados para o Visio** incluem os seguintes controles personalizados para trabalhar com diagramas de Data Mining:</span><span class="sxs-lookup"><span data-stu-id="f15f5-104">The **Data Mining Shapes for Visio** include the following custom controls for working with data mining diagrams:</span></span>  
  
-   <span data-ttu-id="f15f5-105">Controles de renderização para o diagrama de cluster</span><span class="sxs-lookup"><span data-stu-id="f15f5-105">Rendering controls for the cluster diagram</span></span>  
  
     <span data-ttu-id="f15f5-106">Essas opções fazem parte do **Assistente de cluster** que é iniciado quando você solta uma forma no espaço de trabalho do Visio.</span><span class="sxs-lookup"><span data-stu-id="f15f5-106">These options are part of the **Cluster Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="f15f5-107">Barra de ferramentas **layout de mineração de dados**</span><span class="sxs-lookup"><span data-stu-id="f15f5-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="f15f5-108">Essas opções são adicionadas ao workspace do Visio para ajudá-lo a interagir com a forma de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="f15f5-108">These options are added to the Visio workspace to help you interact with the data mining shape.</span></span> <span data-ttu-id="f15f5-109">As opções são diferentes dependendo do tipo de modelo de mineração de dados que você está usando.</span><span class="sxs-lookup"><span data-stu-id="f15f5-109">The options are different depending on which type of data mining model you are using.</span></span>  
  
## <a name="build-a-cluster-diagram"></a><span data-ttu-id="f15f5-110">Criar um diagrama de cluster</span><span class="sxs-lookup"><span data-stu-id="f15f5-110">Build a Cluster Diagram</span></span>  
 <span data-ttu-id="f15f5-111">Este passo a passo demonstra como criar e personalizar um diagrama de clustering no Visio.</span><span class="sxs-lookup"><span data-stu-id="f15f5-111">This walkthrough demonstrates how to build and customize a clustering diagram in Visio.</span></span>  
  
 <span data-ttu-id="f15f5-112">Para acompanhar, você já deverá ter um modelo de clustering disponível.</span><span class="sxs-lookup"><span data-stu-id="f15f5-112">To follow along, you should have a clustering model already available.</span></span> <span data-ttu-id="f15f5-113">Se você não tiver um modelo, use o [Assistente de Cluster &#40;suplementos de mineração de dados para o assistente de&#41;do Excel](cluster-wizard-data-mining-add-ins-for-excel.md) e crie um modelo usando o conjunto de dados de treinamento na pasta de trabalho de exemplo, usando todos os padrões.</span><span class="sxs-lookup"><span data-stu-id="f15f5-113">If you do not have a model, use the [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) wizard and create a model using the Training data set in the sample workbook, using all the defaults.</span></span>  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a><span data-ttu-id="f15f5-114">Use o assistente para Criar Formas Cluster do Visio</span><span class="sxs-lookup"><span data-stu-id="f15f5-114">Use the Cluster Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="f15f5-115">Se você não vir **as formas de mineração de dados da Microsoft** na lista **formas** , clique em **mais formas**, selecione **Abrir Estêncil**e abra o modelo no local de instalação padrão.</span><span class="sxs-lookup"><span data-stu-id="f15f5-115">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="f15f5-116">\<drive>: \Program files\Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="f15f5-116">\<drive>:\Program files\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="f15f5-117">Arraste a forma de **cluster** para a página.</span><span class="sxs-lookup"><span data-stu-id="f15f5-117">Drag the **Cluster** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="f15f5-118">Na página inicial do assistente de **forma do Visio do cluster**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f15f5-118">On the welcome page of the **Cluster Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="f15f5-119">Na página **selecionar uma fonte de dados** do **Assistente de cluster**, escolha uma conexão com um [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor que contenha os modelos de Data Mining que você deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="f15f5-119">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that contains the data mining models you want to visualize.</span></span>  
  
5.  <span data-ttu-id="f15f5-120">Selecione um modelo de mineração apropriado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f15f5-120">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="f15f5-121">Para ter certeza de escolher um modelo de clustering, examine a descrição no painel **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="f15f5-121">To make sure you choose a clustering model, review the description in the **Properties** pane.</span></span>  
  
6.  <span data-ttu-id="f15f5-122">Se a conexão for bem-sucedida, na página **Opções do diagrama de cluster**, você decide qual tipo de diagrama de cluster deve ser incluído na apresentação do Visio:</span><span class="sxs-lookup"><span data-stu-id="f15f5-122">If the connection is successful, on the page, **Options for cluster diagram**, you decide which type of cluster diagram to include in your Visio presentation:</span></span>  
  
     <span data-ttu-id="f15f5-123">**Mostrar formas de cluster somente**</span><span class="sxs-lookup"><span data-stu-id="f15f5-123">**Show cluster shapes only**</span></span>  
     <span data-ttu-id="f15f5-124">Essa opção cria um diagrama de cluster simples, com cada cluster representado por um retângulo ou outra forma que você escolher</span><span class="sxs-lookup"><span data-stu-id="f15f5-124">This option creates a simple cluster diagram, with each cluster represented by a rectangle or other shape you choose</span></span>  
  
     <span data-ttu-id="f15f5-125">**Mostrar clusters com gráfico de características**</span><span class="sxs-lookup"><span data-stu-id="f15f5-125">**Show clusters with characteristics chart**</span></span>  
     <span data-ttu-id="f15f5-126">Essa opção cria o mesmo gráfico que o anterior, mas dentro das formas estão os histogramas que descrevem as características do cluster.</span><span class="sxs-lookup"><span data-stu-id="f15f5-126">This option creates the same chart as above, but inside the shapes are histograms that describe the characteristics of the cluster.</span></span>  
  
     <span data-ttu-id="f15f5-127">![Exemplo de gráfico de características de cluster no Visio](media/dm13-visio-cluster-samplecharshape.gif "Exemplo de gráfico de características de cluster no Visio")</span><span class="sxs-lookup"><span data-stu-id="f15f5-127">![Example of cluster characteristics chart in Visio](media/dm13-visio-cluster-samplecharshape.gif "Example of cluster characteristics chart in Visio")</span></span>  
  
     <span data-ttu-id="f15f5-128">**Mostrar clusters com gráfico de discriminação**</span><span class="sxs-lookup"><span data-stu-id="f15f5-128">**Show clusters with discrimination chart**</span></span>  
     <span data-ttu-id="f15f5-129">Essa opção cria o mesmo gráfico que o diagrama de cluster, mas lista as características do cluster atual que o distinguem mais fortemente de outros clusters.</span><span class="sxs-lookup"><span data-stu-id="f15f5-129">This option creates the same chart as the cluster diagram, but instead lists the characteristics of the current cluster that most strongly distinguish it from other clusters.</span></span>  
  
     <span data-ttu-id="f15f5-130">Você pode alternar para outro tipo de gráfico depois que o assistente tiver criado o diagrama, clicando com o botão direito do mouse em um cluster e selecionando um novo tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="f15f5-130">You can switch to another chart type after the wizard has built the diagram, by right-clicking a cluster and selecting a new chart type.</span></span> <span data-ttu-id="f15f5-131">Por enquanto, escolha a opção **Mostrar clusters com o gráfico de características**.</span><span class="sxs-lookup"><span data-stu-id="f15f5-131">For now, choose the option, **Show clusters with characteristics chart**.</span></span>  
  
7.  <span data-ttu-id="f15f5-132">Deixe a opção **número de linhas no gráfico**, como 5.</span><span class="sxs-lookup"><span data-stu-id="f15f5-132">Leave the option, **Number of rows in the chart**, as 5.</span></span>  
  
     <span data-ttu-id="f15f5-133">Essa opção não altera o número de clusters no modelo; Ele simplesmente limita o número de atributos que podem ser exibidos como recursos de cada cluster.</span><span class="sxs-lookup"><span data-stu-id="f15f5-133">This option doesn't change the number of clusters in the model; it simply limits the number of attributes that can be displayed as features of each cluster.</span></span>  
  
     <span data-ttu-id="f15f5-134">No entanto, a opção atua como um filtro nos dados do gráfico, portanto, você não pode aumentar o número de itens posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f15f5-134">However, the option acts as a filter on the chart data, so you can't increase the number of items later.</span></span>  
  
8.  <span data-ttu-id="f15f5-135">Clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="f15f5-135">Click **Advanced**.</span></span>  
  
     <span data-ttu-id="f15f5-136">A caixa de diálogo **Opções de cluster** é onde você personaliza a aparência visual das formas usadas no diagrama.</span><span class="sxs-lookup"><span data-stu-id="f15f5-136">The **Cluster Options** dialog box is where you customize the visual appearance of shapes used in the diagram.</span></span> <span data-ttu-id="f15f5-137">Você pode alterar as cores usadas no gráfico e a forma usada para clusters.</span><span class="sxs-lookup"><span data-stu-id="f15f5-137">You can change the colors used in the graph, and the shape used for clusters.</span></span>  
  
     <span data-ttu-id="f15f5-138">O controle de **variável de sombreamento** não funciona no Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f15f5-138">The **Shading Variable** control does not work in Office 2013.</span></span>  
  
     <span data-ttu-id="f15f5-139">![clique em Avançado para escolher as cores da forma](media/dm13-visio-clusteroptions-advanced.gif "clique em Avançado para escolher as cores da forma")</span><span class="sxs-lookup"><span data-stu-id="f15f5-139">![click Advanced to choose shape colors](media/dm13-visio-clusteroptions-advanced.gif "click Advanced to choose shape colors")</span></span>  
  
     <span data-ttu-id="f15f5-140">**Dica:** Algumas cores podem ser alteradas mais tarde usando temas do Visio e controles de edição de formas.</span><span class="sxs-lookup"><span data-stu-id="f15f5-140">**Tip:** Some colors can be altered later by using Visio themes and shape editing controls.</span></span> <span data-ttu-id="f15f5-141">No entanto, os temas do Visio também substituirão algumas dessas seleções de cor. Portanto, é recomendável começar com as cores padrão e gradualmente aplicar alterações.</span><span class="sxs-lookup"><span data-stu-id="f15f5-141">However, Visio themes will also override some of these color selections, so we recommend starting with the default colors and gradually applying changes.</span></span>  
  
9. <span data-ttu-id="f15f5-142">Clique em **concluir** para criar o grafo.</span><span class="sxs-lookup"><span data-stu-id="f15f5-142">Click **Finish** to create the graph.</span></span>  
  
     <span data-ttu-id="f15f5-143">O assistente recupera informações do modelo de mineração de dados, renderiza as formas e preenche cada cluster com atributos e valores.</span><span class="sxs-lookup"><span data-stu-id="f15f5-143">The wizard retrieves information from the data mining model, renders the shapes, and populates each cluster with attributes and values.</span></span>  
  
     <span data-ttu-id="f15f5-144">![uma rede de dependências](media/dm13-visiodepnet-defaultgraph.gif "uma rede de dependências")</span><span class="sxs-lookup"><span data-stu-id="f15f5-144">![a dependency network](media/dm13-visiodepnet-defaultgraph.gif "a dependency network")</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="f15f5-145">Explorar e modificar o diagrama completo</span><span class="sxs-lookup"><span data-stu-id="f15f5-145">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="f15f5-146">Depois que o diagrama estiver concluído, você poderá continuar a personalizar a aparência usando os controles do Visio, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="f15f5-146">After the diagram is complete, you can continue to customize the appearance using the Visio controls, as shown in the following example.</span></span>  
  
 <span data-ttu-id="f15f5-147">![diagrama de cluster personalizando usando Visio](media/dm13-visio-clustercomplete1.gif "diagrama de cluster personalizando usando Visio")</span><span class="sxs-lookup"><span data-stu-id="f15f5-147">![cluster diagram customized using Visio](media/dm13-visio-clustercomplete1.gif "cluster diagram customized using Visio")</span></span>  
  
 <span data-ttu-id="f15f5-148">Todas as formas básicas de cluster são geradas pelo assistente; use as seguintes ferramentas para atualizar e personalizar o diagrama:</span><span class="sxs-lookup"><span data-stu-id="f15f5-148">All of the basic cluster shapes are generated by the wizard; use the following tools to update and personalize the diagram:</span></span>  
  
1.  <span data-ttu-id="f15f5-149">Arraste o controle deslizante no controle de **Opções de cluster** para filtrar relações mais fracas e simplificar o diagrama.</span><span class="sxs-lookup"><span data-stu-id="f15f5-149">Drag the slider in the **Cluster Options** control, to filter out weaker relationships and simplify the diagram.</span></span>  
  
2.  <span data-ttu-id="f15f5-150">Use a opção de **página Refazer layout** do Visio para fazer experiências com layouts de cluster diferentes.</span><span class="sxs-lookup"><span data-stu-id="f15f5-150">Use the Visio **Re-Layout Page** option to experiment with different cluster layouts.</span></span>  
  
3.  <span data-ttu-id="f15f5-151">Use a opção **conectores** na guia **design** para alterar o estilo do conector para manter as linhas do cruzamento em clusters.</span><span class="sxs-lookup"><span data-stu-id="f15f5-151">Use the **Connectors** option on the **Design** tab to change the connector style to keep lines from crossing over clusters.</span></span>  
  
4.  <span data-ttu-id="f15f5-152">Clique na faixa de **bits suplementos** e, em seguida, exiba uma das barras de ferramentas personalizadas usadas para trabalhar com diagramas de Data Mining:</span><span class="sxs-lookup"><span data-stu-id="f15f5-152">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="f15f5-153">**Layout**</span><span class="sxs-lookup"><span data-stu-id="f15f5-153">**Layout**</span></span>  
     <span data-ttu-id="f15f5-154">Otimiza a organização dos clusters para caberem na página atual.</span><span class="sxs-lookup"><span data-stu-id="f15f5-154">Optimizes the arrangement of clusters to fit in the current page.</span></span>  
  
     <span data-ttu-id="f15f5-155">**Redimensionar Página**</span><span class="sxs-lookup"><span data-stu-id="f15f5-155">**Resize Page**</span></span>  
     <span data-ttu-id="f15f5-156">Esse controle foi planejado para versões anteriores do HTML.</span><span class="sxs-lookup"><span data-stu-id="f15f5-156">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="f15f5-157">Use os controles de dimensionamento de página do Visio.</span><span class="sxs-lookup"><span data-stu-id="f15f5-157">Use the Visio page resizing controls instead.</span></span>  
  
     <span data-ttu-id="f15f5-158">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f15f5-158">**Description**</span></span>  
     <span data-ttu-id="f15f5-159">Se um cluster estiver selecionado, clique nessa opção para exibir detalhes sobre o cluster.</span><span class="sxs-lookup"><span data-stu-id="f15f5-159">If a cluster is selected, click this option to display details about the cluster.</span></span>  
  
     <span data-ttu-id="f15f5-160">![clique em Descrição para obter informações sobre o cluster](media/dm13-visio-cluster-description-control.gif "clique em Descrição para obter informações sobre o cluster")</span><span class="sxs-lookup"><span data-stu-id="f15f5-160">![click Description to get details about the cluster](media/dm13-visio-cluster-description-control.gif "click Description to get details about the cluster")</span></span>  
  
     <span data-ttu-id="f15f5-161">**Intensidade da Borda**</span><span class="sxs-lookup"><span data-stu-id="f15f5-161">**Edge Strength**</span></span>  
     <span data-ttu-id="f15f5-162">Exibe pontuações de confiança nas linhas que conectam os clusters.</span><span class="sxs-lookup"><span data-stu-id="f15f5-162">Displays confidence scores on the lines connecting clusters.</span></span>  
  
     <span data-ttu-id="f15f5-163">No entanto, se você aplicar qualquer formatação especial diferente do padrão gerado pelo assistente, inclusive os planos de fundo, esses números poderão não ser visíveis.</span><span class="sxs-lookup"><span data-stu-id="f15f5-163">However, if you apply any special formatting other than the default generated by the wizard, including some backgrounds, these numbers might not be visible.</span></span>  
  
     <span data-ttu-id="f15f5-164">**Controle deslizante**</span><span class="sxs-lookup"><span data-stu-id="f15f5-164">**Slider**</span></span>  
     <span data-ttu-id="f15f5-165">Filtra as linhas entre clusters.</span><span class="sxs-lookup"><span data-stu-id="f15f5-165">Filters the lines between clusters.</span></span> <span data-ttu-id="f15f5-166">Mover o controle deslizante para cima remove tudo exceto as associações mais importantes.</span><span class="sxs-lookup"><span data-stu-id="f15f5-166">Moving the slider up removes all but the most important associations.</span></span>  
  
     <span data-ttu-id="f15f5-167">**Sombreamento**</span><span class="sxs-lookup"><span data-stu-id="f15f5-167">**Shading**</span></span>  
     <span data-ttu-id="f15f5-168">Esse controle não funciona no Office 2013.</span><span class="sxs-lookup"><span data-stu-id="f15f5-168">This control does not work in Office 2013.</span></span>  
  
5.  <span data-ttu-id="f15f5-169">Use o controle de **panorâmica e zoom** , na área do **painel de tarefas** da faixa de visão do Visio **View** , para se concentrar em um conjunto de clusters e movê-lo pelo diagrama.</span><span class="sxs-lookup"><span data-stu-id="f15f5-169">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a set of clusters and move around the diagram.</span></span>  
  
6.  <span data-ttu-id="f15f5-170">Clique com o botão direito do mouse em qualquer cluster para ver as opções específicas para a forma do cluster:</span><span class="sxs-lookup"><span data-stu-id="f15f5-170">Right-click any cluster to see options specific to the cluster shape:</span></span>  
  
    -   <span data-ttu-id="f15f5-171">Altere o estilo do gráfico.</span><span class="sxs-lookup"><span data-stu-id="f15f5-171">Change the chart style.</span></span>  
  
    -   <span data-ttu-id="f15f5-172">Adicione um gráfico de características do cluster.</span><span class="sxs-lookup"><span data-stu-id="f15f5-172">Add a cluster characteristics chart.</span></span>  
  
    -   <span data-ttu-id="f15f5-173">Adicione um gráfico de discriminação do cluster.</span><span class="sxs-lookup"><span data-stu-id="f15f5-173">Add a cluster discrimination chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f15f5-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f15f5-174">See Also</span></span>  
 [<span data-ttu-id="f15f5-175">Solução de problemas de diagramas de mineração de dados do Visio &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="f15f5-175">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
