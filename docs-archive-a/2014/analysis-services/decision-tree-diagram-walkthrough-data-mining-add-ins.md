---
title: Explicação do diagrama de árvore de decisão (suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- shapes, data mining
- diagram, decision tree
- Visio shapes, decision tree
- decision tree [data mining]
ms.assetid: 9566f6a2-c750-4125-ba5e-42c7251a78c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: bbe54db1ab3d00d074917db770a9a731f884f49a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572821"
---
# <a name="decision-tree-diagram-walkthrough--data-mining-add-ins"></a><span data-ttu-id="8e67a-102">Explicação do diagrama de árvore de decisão (suplementos de mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="8e67a-102">Decision Tree Diagram Walkthrough  (Data Mining Add-ins)</span></span>
  <span data-ttu-id="8e67a-103">Se você criou um modelo de árvore de decisão, pode criar um diagrama personalizado no Visio usando a forma da Árvore de Decisão ou a forma de Rede de Dependências.</span><span class="sxs-lookup"><span data-stu-id="8e67a-103">If you have created a decision tree model, you can create a customized diagram in Visio by using either the Decision Tree shape or the Dependency Network shape.</span></span> <span data-ttu-id="8e67a-104">Este tópico descreve as personalizações que você pode executar usando a forma de **árvore de decisão** e esses controles:</span><span class="sxs-lookup"><span data-stu-id="8e67a-104">This topic describes the customizations you can perform using the **Decision Tree** shape and these controls:</span></span>  
  
-   <span data-ttu-id="8e67a-105">Controles de renderização para o diagrama de árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="8e67a-105">Rendering controls for the decision tree diagram</span></span>  
  
     <span data-ttu-id="8e67a-106">Essas opções fazem parte do **Assistente de árvore de decisão** que é iniciado quando você solta uma forma no espaço de trabalho do Visio.</span><span class="sxs-lookup"><span data-stu-id="8e67a-106">These options are part of the **Decision Tree Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="8e67a-107">Barra de ferramentas **layout de mineração de dados**</span><span class="sxs-lookup"><span data-stu-id="8e67a-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="8e67a-108">Essas opções são adicionadas ao workspace do Visio para ajudá-lo a interagir com a forma.</span><span class="sxs-lookup"><span data-stu-id="8e67a-108">These options are added to the Visio workspace to help you interact with the shape.</span></span>  
  
## <a name="build-a-decision-tree-diagram"></a><span data-ttu-id="8e67a-109">Criar um diagrama de árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="8e67a-109">Build a Decision Tree Diagram</span></span>  
 <span data-ttu-id="8e67a-110">Descartar a forma da árvore de decisão na página do Visio para iniciar o **Assistente de forma da árvore de decisão do Visio** e definir opções de diagrama.</span><span class="sxs-lookup"><span data-stu-id="8e67a-110">You drop the Decision Tree shape onto the Visio page to launch the **Decision Tree Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-decision-tree-wizard"></a><span data-ttu-id="8e67a-111">Use o Assistente de Árvore de Decisão</span><span class="sxs-lookup"><span data-stu-id="8e67a-111">Use the Decision Tree Wizard</span></span>  
  
1.  <span data-ttu-id="8e67a-112">Se você não vir **as formas de mineração de dados da Microsoft** na lista **formas** , clique em **mais formas**, selecione **Abrir Estêncil**e abra o modelo no local de instalação padrão.</span><span class="sxs-lookup"><span data-stu-id="8e67a-112">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="8e67a-113">\<drive>: \Program Files (x85) \Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="8e67a-113">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="8e67a-114">Arraste a forma **árvore de decisão** para a página.</span><span class="sxs-lookup"><span data-stu-id="8e67a-114">Drag the **Decision Tree** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="8e67a-115">Na página inicial do assistente de **forma da árvore de decisão do Visio**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8e67a-115">On the welcome page of the **Decision Tree Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="8e67a-116">Na página **selecionar uma fonte de dados** do **Assistente de cluster**, escolha uma conexão com um [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor que tenha o modelo que você deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="8e67a-116">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="8e67a-117">Selecione um modelo de mineração apropriado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8e67a-117">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="8e67a-118">Esse tipo de diagrama dá suporte a modelos criados usando as árvores de decisão ou o algoritmo de regressão linear.</span><span class="sxs-lookup"><span data-stu-id="8e67a-118">This diagram type supports models created using the Decision Trees or Linear Regression algorithm.</span></span>  
  
6.  <span data-ttu-id="8e67a-119">Na página **selecionar árvore de decisão** , escolha uma árvore individual a ser exibida.</span><span class="sxs-lookup"><span data-stu-id="8e67a-119">On the **Select Decision Tree** page, choose an individual tree to display.</span></span>  
  
     <span data-ttu-id="8e67a-120">Uma árvore modela as interações que levam a um determinado resultado que você modelou; Portanto, mesmo que seu modelo contenha vários resultados, você poderá exibir apenas uma árvore por vez.</span><span class="sxs-lookup"><span data-stu-id="8e67a-120">A tree models the interactions that lead to a particular outcome you've modeled; therefore, even if your model contains multiple outcomes, you can display only one tree at a time.</span></span>  
  
7.  <span data-ttu-id="8e67a-121">Na caixa de diálogo **selecionar árvore de decisão** , você também pode definir estas opções de renderização:</span><span class="sxs-lookup"><span data-stu-id="8e67a-121">In the **Select Decision Tree** dialog box, you can also set these rendering options:</span></span>  
  
     <span data-ttu-id="8e67a-122">**Profundidade de renderização máxima**</span><span class="sxs-lookup"><span data-stu-id="8e67a-122">**Maximum Rendering Depth**</span></span>  
     <span data-ttu-id="8e67a-123">Use esta opção para controlar quantos nós são exibidos.</span><span class="sxs-lookup"><span data-stu-id="8e67a-123">Use this option to control how many nodes are displayed.</span></span>  
  
     <span data-ttu-id="8e67a-124">Uma árvore de decisão pode ser muito profunda, criando um diagrama que não caiba na página.</span><span class="sxs-lookup"><span data-stu-id="8e67a-124">A decision tree might go very deep, creating a diagram that does not fit on the page.</span></span> <span data-ttu-id="8e67a-125">Use este controle para focalizar nos nós mais à esquerda, que são mais importantes.</span><span class="sxs-lookup"><span data-stu-id="8e67a-125">Use this control to focus on the leftmost nodes, which are more important.</span></span>  
  
     <span data-ttu-id="8e67a-126">O padrão é três níveis de nós.</span><span class="sxs-lookup"><span data-stu-id="8e67a-126">The default is three levels of nodes.</span></span>  
  
     <span data-ttu-id="8e67a-127">**Selecionar cor e exibir o texto para os valores**</span><span class="sxs-lookup"><span data-stu-id="8e67a-127">**Select color and display text for values**</span></span>  
     <span data-ttu-id="8e67a-128">Escolher a cor que representará cada um dos resultados.</span><span class="sxs-lookup"><span data-stu-id="8e67a-128">Choose the color that will represent each one of the outcomes.</span></span> <span data-ttu-id="8e67a-129">Se você não especificar cores, elas serão geradas automaticamente usando as cores de tema do vídeo atual.</span><span class="sxs-lookup"><span data-stu-id="8e67a-129">If you do not specify colors, they are automatically generated using the current video theme colors.</span></span>  
  
8.  <span data-ttu-id="8e67a-130">Clique em **avançado** para personalizar as seguintes opções para cada um dos nós no diagrama de árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="8e67a-130">Click **Advanced** to customize the following options for each of the nodes in the decision tree diagram.</span></span>  
  
     <span data-ttu-id="8e67a-131">Variável e **estado** de **sombreamento**</span><span class="sxs-lookup"><span data-stu-id="8e67a-131">**Shading Variable** and **State**</span></span>  
     <span data-ttu-id="8e67a-132">Escolha o resultado pretendido que você deseja exibir no diagrama da árvore.</span><span class="sxs-lookup"><span data-stu-id="8e67a-132">Choose the target outcome that you want to show in the tree diagram.</span></span>  
  
     <span data-ttu-id="8e67a-133">**Mostrar Histograma**</span><span class="sxs-lookup"><span data-stu-id="8e67a-133">**Show Histogram**</span></span>  
     <span data-ttu-id="8e67a-134">Adiciona um gráfico para cada nó que mostra as regras que definem esse nó.</span><span class="sxs-lookup"><span data-stu-id="8e67a-134">Adds a chart to each node that shows the rules that define that node.</span></span>  
  
     <span data-ttu-id="8e67a-135">**Mostrar Rótulo**</span><span class="sxs-lookup"><span data-stu-id="8e67a-135">**Show Label**</span></span>  
     <span data-ttu-id="8e67a-136">Adiciona nomes de coluna ao histograma.</span><span class="sxs-lookup"><span data-stu-id="8e67a-136">Adds column names to the histogram.</span></span>  
  
     <span data-ttu-id="8e67a-137">**Mostrar Probabilidade**</span><span class="sxs-lookup"><span data-stu-id="8e67a-137">**Show Probability**</span></span>  
     <span data-ttu-id="8e67a-138">Exibe a probabilidade de cada valor.</span><span class="sxs-lookup"><span data-stu-id="8e67a-138">Displays the probability of each value.</span></span>  
  
     <span data-ttu-id="8e67a-139">**Mostrar Suporte**</span><span class="sxs-lookup"><span data-stu-id="8e67a-139">**Show Support**</span></span>  
     <span data-ttu-id="8e67a-140">Exibe o suporte para cada valor.</span><span class="sxs-lookup"><span data-stu-id="8e67a-140">Displays the support for each value.</span></span>  
  
     <span data-ttu-id="8e67a-141">**Mostrar Rodapé**</span><span class="sxs-lookup"><span data-stu-id="8e67a-141">**Show Footer**</span></span>  
     <span data-ttu-id="8e67a-142">Adiciona um rodapé que soma todos os valores exibidos.</span><span class="sxs-lookup"><span data-stu-id="8e67a-142">Adds a footer that sums all displayed values.</span></span>  
  
     <span data-ttu-id="8e67a-143">**Mostrar Cabeçalho**</span><span class="sxs-lookup"><span data-stu-id="8e67a-143">**Show Header**</span></span>  
     <span data-ttu-id="8e67a-144">Adiciona títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="8e67a-144">Adds column headings.</span></span>  
  
     <span data-ttu-id="8e67a-145">**Mostrar estados sem nenhum suporte**</span><span class="sxs-lookup"><span data-stu-id="8e67a-145">**Show states with zero support**</span></span>  
     <span data-ttu-id="8e67a-146">Permite que você exiba valores ausentes.</span><span class="sxs-lookup"><span data-stu-id="8e67a-146">Lets you display missing values.</span></span>  
  
9. <span data-ttu-id="8e67a-147">Clique em **concluir** para criar o grafo.</span><span class="sxs-lookup"><span data-stu-id="8e67a-147">Click **Finish** to create the graph.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="8e67a-148">Em alguns ambientes, os conectores no gráfico podem não ser renderizados no Office 2013.</span><span class="sxs-lookup"><span data-stu-id="8e67a-148">In some environments, connectors in the chart might fail to render in Office 2013.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="8e67a-149">Explorar e modificar o diagrama completo</span><span class="sxs-lookup"><span data-stu-id="8e67a-149">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="8e67a-150">Depois de concluir o **Assistente de forma da árvore de decisão do Visio**, o Visio cria um diagrama de árvore na página que exibe graficamente as regras que levam ao resultado previsto.</span><span class="sxs-lookup"><span data-stu-id="8e67a-150">After you have completed the **Decision Tree Visio Shape Wizard**, Visio creates a tree diagram on the page that graphically displays the rules that lead to the predicted outcome.</span></span>  
  
 <span data-ttu-id="8e67a-151">Você pode continuar modificando a forma usando os seguintes controles para diagramas da árvore de decisão:</span><span class="sxs-lookup"><span data-stu-id="8e67a-151">You can continue to modify the shape by using the following controls for decision tree diagrams:</span></span>  
  
#### <a name="using-the-decision-tree-option-menus"></a><span data-ttu-id="8e67a-152">Usando os menus de opção da árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="8e67a-152">Using the decision tree option menus</span></span>  
  
1.  <span data-ttu-id="8e67a-153">Clique na faixa de **bits suplementos** e, em seguida, exiba uma das barras de ferramentas personalizadas usadas para trabalhar com diagramas de Data Mining:</span><span class="sxs-lookup"><span data-stu-id="8e67a-153">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="8e67a-154">**Layout**</span><span class="sxs-lookup"><span data-stu-id="8e67a-154">**Layout**</span></span>  
     <span data-ttu-id="8e67a-155">Otimiza a organização da árvore para caber na página atual.</span><span class="sxs-lookup"><span data-stu-id="8e67a-155">Optimizes the arrangement of the tree to fit the current page.</span></span>  
  
     <span data-ttu-id="8e67a-156">**Redimensionar Página**</span><span class="sxs-lookup"><span data-stu-id="8e67a-156">**Resize Page**</span></span>  
     <span data-ttu-id="8e67a-157">Esse controle foi planejado para versões anteriores do HTML.</span><span class="sxs-lookup"><span data-stu-id="8e67a-157">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="8e67a-158">Em vez disso, use os controles redimensionamento de página do Visio,</span><span class="sxs-lookup"><span data-stu-id="8e67a-158">Use the Visio page resizing controls instead,</span></span>  
  
     <span data-ttu-id="8e67a-159">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8e67a-159">**Description**</span></span>  
     <span data-ttu-id="8e67a-160">Quando um nó da árvore é selecionado, clique nessa opção para exibir detalhes sobre os casos no nó.</span><span class="sxs-lookup"><span data-stu-id="8e67a-160">When a node of the tree is selected, click this option to display details about the cases in the node.</span></span>  
  
2.  <span data-ttu-id="8e67a-161">Use a opção **página Refazer layout** na faixa de opções **design** do Visio para experimentar diferentes layouts de árvore.</span><span class="sxs-lookup"><span data-stu-id="8e67a-161">Use the **Re-Layout Page** option in the Visio **Design** ribbon to experiment with different tree layouts.</span></span>  
  
3.  <span data-ttu-id="8e67a-162">Use a opção **conectores** na guia **design** para alterar os conectores usados entre os nós na árvore.</span><span class="sxs-lookup"><span data-stu-id="8e67a-162">Use the **Connectors** option on the **Design** tab to change the connectors used between nodes in the tree.</span></span>  
  
4.  <span data-ttu-id="8e67a-163">Use o controle de **panorâmica e zoom** , na área do **painel de tarefas** da faixa de **modos do modo de exibição** do Visio, para se concentrar em uma área específica do diagrama.</span><span class="sxs-lookup"><span data-stu-id="8e67a-163">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a particular area of the diagram.</span></span>  
  
5.  <span data-ttu-id="8e67a-164">Clique com o botão direito do mouse em qualquer nó na árvore, e escolha dessas opções de menu de atalho específicas dos diagramas de árvore de decisão:</span><span class="sxs-lookup"><span data-stu-id="8e67a-164">Right-click any node in the tree, and choose from these shortcut menu options specific to decision tree diagrams:</span></span>  
  
     <span data-ttu-id="8e67a-165">**Aperfeiçoar o Layout de Página**</span><span class="sxs-lookup"><span data-stu-id="8e67a-165">**Improve Page Layout**</span></span>  
     <span data-ttu-id="8e67a-166">Distribui os nós uniformemente na página e ajusta a exibição da página para visualização de todos os nós.</span><span class="sxs-lookup"><span data-stu-id="8e67a-166">Distributes the nodes evenly on the page and adjusts the page view to see all nodes.</span></span>  
  
     <span data-ttu-id="8e67a-167">**Mover Filhos para a Nova Página**</span><span class="sxs-lookup"><span data-stu-id="8e67a-167">**Move Children to New Page**</span></span>  
     <span data-ttu-id="8e67a-168">Move os filhos do nó selecionado atualmente para uma nova página.</span><span class="sxs-lookup"><span data-stu-id="8e67a-168">Moves the children of the currently selected node to a new page.</span></span>  
  
     <span data-ttu-id="8e67a-169">**Recolher Nós Filho**</span><span class="sxs-lookup"><span data-stu-id="8e67a-169">**Collapse Child Nodes**</span></span>  
     <span data-ttu-id="8e67a-170">Oculta os filhos do nó selecionado no momento.</span><span class="sxs-lookup"><span data-stu-id="8e67a-170">Hides the children of the currently selected node.</span></span>  
  
     <span data-ttu-id="8e67a-171">**Expandir Nós Filho**</span><span class="sxs-lookup"><span data-stu-id="8e67a-171">**Expand Child Nodes**</span></span>  
     <span data-ttu-id="8e67a-172">Exibe os filhos do nó selecionado no momento.</span><span class="sxs-lookup"><span data-stu-id="8e67a-172">Displays the children of the currently selected node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e67a-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e67a-173">See Also</span></span>  
 [<span data-ttu-id="8e67a-174">Solução de problemas de diagramas de mineração de dados do Visio &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="8e67a-174">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
