---
title: Explicação do diagrama de rede de dependências (suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, dependency network
- shapes, data mining
- shapes, network
- dependencies
- diagram, dependency network
- data mining layout toolbar
- dependency network
ms.assetid: aac732a8-5262-4649-b7d7-3ccf6f9cfa8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07f97dac7ffb0211f0ff1e1b58c2e0792d026174
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582675"
---
# <a name="dependency-network-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="51a95-102">Passo a passo do diagrama de rede de dependências (Suplementos de Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="51a95-102">Dependency Network Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="51a95-103">Vários tipos diferentes de modelos de mineração de dados usam um gráfico de rede como uma maneira de explorar relações nos dados.</span><span class="sxs-lookup"><span data-stu-id="51a95-103">Several different types of data mining models use a network graph as a way of exploring relationships in the data.</span></span> <span data-ttu-id="51a95-104">Você pode importar esses modelos para o Visio usando a forma de **rede de dependência** e, em seguida, continuar a personalizar e aprimorar o layout.</span><span class="sxs-lookup"><span data-stu-id="51a95-104">You can import these models into Visio using the **Dependency Network** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="51a95-105">As **formas de mineração de dados para o Visio** incluem os seguintes controles personalizados para trabalhar com diagramas de rede de dependência:</span><span class="sxs-lookup"><span data-stu-id="51a95-105">The **Data Mining Shapes for Visio** include the following custom controls for working with dependency network diagrams:</span></span>  
  
-   <span data-ttu-id="51a95-106">Controles de renderização para o gráfico da rede</span><span class="sxs-lookup"><span data-stu-id="51a95-106">Rendering controls for the network graph</span></span>  
  
     <span data-ttu-id="51a95-107">Essas opções fazem parte do assistente que é iniciado quando você solta uma forma no workspace do Visio.</span><span class="sxs-lookup"><span data-stu-id="51a95-107">These options are part of the wizard that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="51a95-108">Barra de ferramentas **layout de mineração de dados**</span><span class="sxs-lookup"><span data-stu-id="51a95-108">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="51a95-109">Essas opções são adicionadas ao workspace do Visio para ajudá-lo a interagir com o gráfico de rede de dependências.</span><span class="sxs-lookup"><span data-stu-id="51a95-109">These options are added to the Visio workspace to help you interact with the dependency network graph.</span></span>  
  
## <a name="build-a-dependency-network-graph"></a><span data-ttu-id="51a95-110">Criar um gráfico de rede de dependências</span><span class="sxs-lookup"><span data-stu-id="51a95-110">Build a Dependency Network Graph</span></span>  
 <span data-ttu-id="51a95-111">Você solta uma forma na página do Visio para iniciar o **Assistente de forma de rede de dependência do Visio** e definir opções de diagrama.</span><span class="sxs-lookup"><span data-stu-id="51a95-111">You drop a shape onto the Visio page to launch the **Dependency Net Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-dependency-net-visio-shape-wizard"></a><span data-ttu-id="51a95-112">Usar o Assistente para Criar Formas da Rede de Dependências do Visio</span><span class="sxs-lookup"><span data-stu-id="51a95-112">Use the Dependency Net Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="51a95-113">Se você não vir **as formas de mineração de dados da Microsoft** na lista **formas** , clique em **mais formas**, selecione **Abrir Estêncil**e abra o modelo no local de instalação padrão.</span><span class="sxs-lookup"><span data-stu-id="51a95-113">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="51a95-114">\<drive>: \Program Files (x85) \Microsoft SQL Server 2012 DM Add-ins</span><span class="sxs-lookup"><span data-stu-id="51a95-114">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="51a95-115">Arraste a forma **rede de dependências** até a página para iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="51a95-115">Drag the **Dependency Network** shape onto the page to start the wizard.</span></span> <span data-ttu-id="51a95-116">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="51a95-116">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="51a95-117">Na página Bem-vindo do **Assistente de forma da rede de dependência do Visio**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="51a95-117">On the welcome page of the **Dependency Network Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="51a95-118">Na página **selecionar uma fonte de dados** do **Assistente de forma de rede de dependência do Visio**, escolha uma conexão com um [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor que tenha o modelo que você deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="51a95-118">On the **Select a Data Source** page of the **Dependency Network Visio Shape Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="51a95-119">Selecione um modelo de mineração apropriado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="51a95-119">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="51a95-120">Para selecionar um modelo apropriado, você pode examinar o nome, a descrição, as colunas e o tipo de dados no painel **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="51a95-120">To select an appropriate model, you can review the name, description, columns, and type of data in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="51a95-121">Essa forma dá suporte a modelos criados usando esses algoritmos:</span><span class="sxs-lookup"><span data-stu-id="51a95-121">This shape supports models created by using these algorithms:</span></span>  
  
    -   <span data-ttu-id="51a95-122">Naïve Bayes</span><span class="sxs-lookup"><span data-stu-id="51a95-122">Naïve Bayes</span></span>  
  
    -   <span data-ttu-id="51a95-123">Árvores de decisão</span><span class="sxs-lookup"><span data-stu-id="51a95-123">Decision Trees</span></span>  
  
    -   <span data-ttu-id="51a95-124">Regras de associação</span><span class="sxs-lookup"><span data-stu-id="51a95-124">Association Rules</span></span>  
  
6.  <span data-ttu-id="51a95-125">Na página, **Selecione os nós a serem renderizados**, personalize o tamanho do grafo e, opcionalmente, filtre para incluir apenas determinados nós.</span><span class="sxs-lookup"><span data-stu-id="51a95-125">On the page, **Select Nodes to Render**, customize the size of the graph, and optionally filter to only include certain nodes.</span></span>  
  
     <span data-ttu-id="51a95-126">Com um grande conjunto de grandes, um grafo de dependência pode se tornar enorme e conter muitos objetos relacionados, representados como *nós*.</span><span class="sxs-lookup"><span data-stu-id="51a95-126">With a large dataset, a dependency graph can become huge, and contain many related objects, represented as *nodes*.</span></span> <span data-ttu-id="51a95-127">Ao usar essa caixa de diálogo, você poderá criar um gráfico de rede personalizado que inclui apenas os nós de interesse.</span><span class="sxs-lookup"><span data-stu-id="51a95-127">By using this dialog box, you can create a custom network graph that includes only the nodes of interest.</span></span>  
  
     <span data-ttu-id="51a95-128">[espaço reservado de arte]</span><span class="sxs-lookup"><span data-stu-id="51a95-128">[art placeholder]</span></span>  
  
     <span data-ttu-id="51a95-129">**Número de nós da busca**</span><span class="sxs-lookup"><span data-stu-id="51a95-129">**Number of nodes to fetch**</span></span>  
     <span data-ttu-id="51a95-130">Se o modelo contiver um número de nós inferior ao especificado, essa configuração não terá efeito.</span><span class="sxs-lookup"><span data-stu-id="51a95-130">If the model contains fewer than the specified number of nodes, this setting has no effect.</span></span> <span data-ttu-id="51a95-131">Se o modelo contiver mais nós do que o especificado, apenas os nós mais fortes serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="51a95-131">If the model contains more nodes than the specified number, only the strongest nodes are displayed.</span></span>  
  
     <span data-ttu-id="51a95-132">**Nome contém**</span><span class="sxs-lookup"><span data-stu-id="51a95-132">**Name contains**</span></span>  
     <span data-ttu-id="51a95-133">Deixe esta caixa em branco e clique na seta verde para recuperar todos os nós no modelo.</span><span class="sxs-lookup"><span data-stu-id="51a95-133">Leave this box blank and click the green arrow to retrieve all nodes in the model.</span></span>  
  
     <span data-ttu-id="51a95-134">Ou digite uma cadeia de caracteres e clique na seta verde para retornar apenas os nós que contêm a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="51a95-134">Or, type a string and click the green arrow to return only those nodes that contain the specified string.</span></span>  
  
     <span data-ttu-id="51a95-135">A maioria dos modelos que você pode criar com os dados de exemplo não são grandes. Portanto, para este exemplo, aumente o número de nós para 10 e clique na seta verde para executar uma consulta e obter a lista de todos os nós.</span><span class="sxs-lookup"><span data-stu-id="51a95-135">Most of the models that you can create with the sample data are not big, so for this example, increase the number of nodes to 10, and then click the green arrow to run a query and get the list of all nodes.</span></span>  
  
7.  <span data-ttu-id="51a95-136">Clique em **avançado** para definir as opções de sombreamento e forma para o grafo.</span><span class="sxs-lookup"><span data-stu-id="51a95-136">Click **Advanced** to set shading and shape options for the graph.</span></span>  
  
8.  <span data-ttu-id="51a95-137">Clique em **fechar** para sair da caixa de diálogo opções **avançadas** e, em seguida, clique em **concluir** para criar o grafo.</span><span class="sxs-lookup"><span data-stu-id="51a95-137">Click **Close** to exit the **Advanced** options dialog box, and then click **Finish** to create the graph.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="51a95-138">Explorar e modificar o diagrama completo</span><span class="sxs-lookup"><span data-stu-id="51a95-138">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="51a95-139">Depois que o Visio criou o grafo de rede de dependências, você poderá continuar a modificar e aumentar o grafo usando os recursos no Visio.</span><span class="sxs-lookup"><span data-stu-id="51a95-139">After Visio has created the network dependency graph, you can continue to modify and enhance the graph by using the features in Visio.</span></span>  
  
 <span data-ttu-id="51a95-140">O gráfico a seguir mostra o layout padrão de um gráfico de rede de dependências.</span><span class="sxs-lookup"><span data-stu-id="51a95-140">The following graphic shows the default layout of a dependency network graph.</span></span>  
  
 <span data-ttu-id="51a95-141">[espaço reservado de arte]</span><span class="sxs-lookup"><span data-stu-id="51a95-141">[art placeholder]</span></span>  
  
1.  <span data-ttu-id="51a95-142">Use o controle de **panorâmica e zoom** , na área do **painel de tarefas** da faixa de **modos do modo de exibição** do Visio, para se concentrar em uma seção do grafo e movê-lo pelo diagrama.</span><span class="sxs-lookup"><span data-stu-id="51a95-142">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a section of the graph and move around the diagram.</span></span>  
  
2.  <span data-ttu-id="51a95-143">Experimente layouts de grafo diferentes fornecidos pela opção de **página Refazer layout** do Visio.</span><span class="sxs-lookup"><span data-stu-id="51a95-143">Experiment with different graph layouts provided by the Visio **Re-Layout Page** option.</span></span>  
  
3.  <span data-ttu-id="51a95-144">Clique na faixa de **bits suplementos** e, em seguida, exiba uma das barras de ferramentas personalizadas usadas para trabalhar com diagramas de Data Mining:</span><span class="sxs-lookup"><span data-stu-id="51a95-144">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="51a95-145">**Layout**</span><span class="sxs-lookup"><span data-stu-id="51a95-145">**Layout**</span></span>  
     <span data-ttu-id="51a95-146">Otimiza o layout dos nós na página e altera a exibição para que todos os nós fiquem visíveis.</span><span class="sxs-lookup"><span data-stu-id="51a95-146">Optimizes the layout of nodes on the page, and changes the view so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="51a95-147">**Redimensionar Página**</span><span class="sxs-lookup"><span data-stu-id="51a95-147">**Resize Page**</span></span>  
     <span data-ttu-id="51a95-148">Altera o tamanho da página para que todos os nós fiquem visíveis.</span><span class="sxs-lookup"><span data-stu-id="51a95-148">Changes the size of the page so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="51a95-149">**Intensidade da Borda**</span><span class="sxs-lookup"><span data-stu-id="51a95-149">**Edge Strength**</span></span>  
     <span data-ttu-id="51a95-150">Alterna a exibição da intensidade da borda para todo o gráfico.</span><span class="sxs-lookup"><span data-stu-id="51a95-150">Toggles display of edge strength for the entire graph.</span></span> <span data-ttu-id="51a95-151">Uma borda é uma conexão entre dois nós.</span><span class="sxs-lookup"><span data-stu-id="51a95-151">An edge is a connection between nodes.</span></span> <span data-ttu-id="51a95-152">Você pode usar o controle deslizante para filtrar as conexões que não são intensas.</span><span class="sxs-lookup"><span data-stu-id="51a95-152">You can use the slider control to filter out connections that are not strong.</span></span>  
  
     <span data-ttu-id="51a95-153">**Controle deslizante**</span><span class="sxs-lookup"><span data-stu-id="51a95-153">**Slider**</span></span>  
     <span data-ttu-id="51a95-154">O **controle deslizante** ajuda a controlar a força das relações que são exibidas no diagrama de rede de dependência.</span><span class="sxs-lookup"><span data-stu-id="51a95-154">The **Slider** helps you control the strength of the relationships that are displayed in the dependency network diagram.</span></span>  
  
     <span data-ttu-id="51a95-155">Cada nó exibido no gráfico representa um estado.</span><span class="sxs-lookup"><span data-stu-id="51a95-155">Each node in the graph represents a state.</span></span> <span data-ttu-id="51a95-156">Uma seta representa uma transição entre dois estados e a probabilidade associada a ela.</span><span class="sxs-lookup"><span data-stu-id="51a95-156">An arrow represents a transition between two states and the probability that is associated with the transition.</span></span> <span data-ttu-id="51a95-157">Para reduzir o número de nós no gráfico, mova a barra de controle deslizante para cima.</span><span class="sxs-lookup"><span data-stu-id="51a95-157">To reduce the number of nodes in the graph, move the slider bar up.</span></span>  
  
     <span data-ttu-id="51a95-158">Para aumentar o número de nós no gráfico, mova a barra de controle deslizante para baixo.</span><span class="sxs-lookup"><span data-stu-id="51a95-158">To increase the number of nodes in the graph, move the slider bar down.</span></span>  
  
     <span data-ttu-id="51a95-159">**Adicionar itens**</span><span class="sxs-lookup"><span data-stu-id="51a95-159">**Add Items**</span></span>  
     <span data-ttu-id="51a95-160">Abre a caixa de diálogo **selecionar nós a serem renderizados** para que você possa selecionar novos nós para adicionar ao grafo.</span><span class="sxs-lookup"><span data-stu-id="51a95-160">Opens the **Select Nodes to Render** dialog box so that you can select new nodes to add to the graph.</span></span>  
  
4.  <span data-ttu-id="51a95-161">Você pode fazer gráficos simples ou elaborados como quiser e adicionar anotações, enquanto permanece conectado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="51a95-161">You can make the graphs as simple or elaborate as you like, and add annotations, while staying connected to the model.</span></span>  
  
     <span data-ttu-id="51a95-162">[espaço reservado para arte]</span><span class="sxs-lookup"><span data-stu-id="51a95-162">[ art placeholder]</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="51a95-163">O realce de nós dependentes e outras opções do menu de atalho que estavam disponíveis em versões anteriores dos Suplementos não funcionam no Office 2013.</span><span class="sxs-lookup"><span data-stu-id="51a95-163">Highlighting of dependent nodes and other shortcut menu options that were available in previous versions of the Add-Ins do not work in Office 2013.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51a95-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51a95-164">See Also</span></span>  
 [<span data-ttu-id="51a95-165">Solução de problemas de diagramas de mineração de dados do Visio &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="51a95-165">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
