---
title: Exibindo modelos de mineração de dados no Visio (suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- diagram, modifying
- templates [Visio]
- shapes, data mining
- diagram
ms.assetid: 5841adea-6650-4fae-8526-26af33edbede
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3c1e63c058295b93e2562c64a6df90a30273a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572199"
---
# <a name="viewing-data-mining-models-in-visio-data-mining-add-ins"></a><span data-ttu-id="af4fe-102">Exibindo modelos de mineração de dados no Visio (suplementos de mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="af4fe-102">Viewing Data Mining Models in Visio (Data Mining Add-ins)</span></span>
  <span data-ttu-id="af4fe-103">As formas do Visio para mineração de dados permitem que você se conecte a um servidor e crie um diagrama representando um modelo de mineração de dados existente.</span><span class="sxs-lookup"><span data-stu-id="af4fe-103">The Visio shapes for data mining let you connect to a server and create a diagram representing an existing data mining model.</span></span> <span data-ttu-id="af4fe-104">Os diagramas podem ser então personalizados usando controles do Visio, mas você também pode detalhar os dados, expor algumas das estatísticas subjacentes e trabalhar com o modelo subjacente.</span><span class="sxs-lookup"><span data-stu-id="af4fe-104">The diagrams can then be customized using Visio controls, but you can also drill down into data, expose some of the underlying statistics, and work with the underlying model.</span></span>  
  
## <a name="building-a-model-diagram"></a><span data-ttu-id="af4fe-105">Criando um diagrama modelo</span><span class="sxs-lookup"><span data-stu-id="af4fe-105">Building a Model Diagram</span></span>  
 <span data-ttu-id="af4fe-106">Quando você abre o arquivo que contém as formas do Visio para Data Mining, o painel **formas** mostra as formas a seguir.</span><span class="sxs-lookup"><span data-stu-id="af4fe-106">When you open the file containing the Visio shapes for data mining, the **Shapes** pane shows the following shapes.</span></span>  
  
 <span data-ttu-id="af4fe-107">Se você não visualizar as formas de mineração de dados quando abrir o Visio, abra o arquivo de modelo da pasta de instalação.</span><span class="sxs-lookup"><span data-stu-id="af4fe-107">If you do not see the data mining shapes when you open Visio, open the template file from the installation folder.</span></span>  
  
 <span data-ttu-id="af4fe-108">![DM](media/dm-stencil.gif "DM")</span><span class="sxs-lookup"><span data-stu-id="af4fe-108">![DM](media/dm-stencil.gif "DM")</span></span>  
  
 <span data-ttu-id="af4fe-109">Para usar uma forma, arraste-a para a página.</span><span class="sxs-lookup"><span data-stu-id="af4fe-109">To use a shape, drag it to the page.</span></span> <span data-ttu-id="af4fe-110">Cada uma das formas abre um assistente diferente, que o ajuda a selecionar dados da fonte, definir opções para o tipo de diagrama específico e especificar sombreamento e outras opções de exibição.</span><span class="sxs-lookup"><span data-stu-id="af4fe-110">Each of the shapes opens a different wizard, which helps you select source data, set options for the specific diagram type, and specify shading and other display options.</span></span>  
  
 <span data-ttu-id="af4fe-111">A tabela a seguir lista os tipos de modelos que podem ser usados com cada tipo de diagrama.</span><span class="sxs-lookup"><span data-stu-id="af4fe-111">The following table lists the types of models that you can use with each type of diagram.</span></span>  
  
|<span data-ttu-id="af4fe-112">Formas do Visio</span><span class="sxs-lookup"><span data-stu-id="af4fe-112">Visio shape</span></span>|<span data-ttu-id="af4fe-113">Modelos com suporte</span><span class="sxs-lookup"><span data-stu-id="af4fe-113">Supported models</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="af4fe-114">Árvore de Decisão</span><span class="sxs-lookup"><span data-stu-id="af4fe-114">Decision Tree</span></span>|<span data-ttu-id="af4fe-115">Use essa forma para modelos baseados na árvore de decisão ou em algoritmos de regressão linear.</span><span class="sxs-lookup"><span data-stu-id="af4fe-115">Use this shape for models based on the decision tree or linear regression algorithms.</span></span>|  
|<span data-ttu-id="af4fe-116">Rede de Dependências</span><span class="sxs-lookup"><span data-stu-id="af4fe-116">Dependency Network</span></span>|<span data-ttu-id="af4fe-117">Use essa forma para modelos baseados em qualquer um destes algoritmos: Naive Bayes, Árvores de Decisão ou Regras de Associação.</span><span class="sxs-lookup"><span data-stu-id="af4fe-117">Use this shape for models based on any of the following algorithms: Naive Bayes, Decision Trees, or Association Rules.</span></span>|  
|<span data-ttu-id="af4fe-118">Cluster</span><span class="sxs-lookup"><span data-stu-id="af4fe-118">Cluster</span></span>|<span data-ttu-id="af4fe-119">Use essa forma para modelos baseados em algoritmos de clustering.</span><span class="sxs-lookup"><span data-stu-id="af4fe-119">Use this shape for models based on clustering algorithms.</span></span>|  
  
 <span data-ttu-id="af4fe-120">Dependendo do tipo de dados no modelo de mineração, o assistente poderá oferecer opções diferentes.</span><span class="sxs-lookup"><span data-stu-id="af4fe-120">Depending on the type of data in your mining model, the wizard may offer different options.</span></span> <span data-ttu-id="af4fe-121">Por exemplo, colunas que contêm números contínuos são visualizadas de maneira diferente que variáveis categóricas.</span><span class="sxs-lookup"><span data-stu-id="af4fe-121">For example, columns that contain continuous numbers are visualized differently than categorical variables.</span></span>  
  
## <a name="working-with-completed-shapes"></a><span data-ttu-id="af4fe-122">Trabalhando com formas completas</span><span class="sxs-lookup"><span data-stu-id="af4fe-122">Working with Completed Shapes</span></span>  
 <span data-ttu-id="af4fe-123">Quando o diagrama estiver concluído, você poderá usá-lo para procurar o modelo de mineração de dados ou aprimorar o diagrama para uso em apresentações.</span><span class="sxs-lookup"><span data-stu-id="af4fe-123">After the diagram is complete, you can use it to browse the data mining model or enhance the diagram for use in presentations.</span></span>  
  
### <a name="visio-menus"></a><span data-ttu-id="af4fe-124">Menus do Visio</span><span class="sxs-lookup"><span data-stu-id="af4fe-124">Visio Menus</span></span>  
 <span data-ttu-id="af4fe-125">O Visio fornece uma variedade de controles de renderização, temas e menus de atalho para ajudar a aprimorar um diagrama.</span><span class="sxs-lookup"><span data-stu-id="af4fe-125">Visio provides a variety of rendering controls, themes, and shortcut menus to help enhance a diagram.</span></span>  
  
-   <span data-ttu-id="af4fe-126">Use os temas do Visio para alterar as cores do diagrama.</span><span class="sxs-lookup"><span data-stu-id="af4fe-126">Use Visio themes to alter diagram colors.</span></span>  
  
-   <span data-ttu-id="af4fe-127">Alterar conectores ou layout do diagrama.</span><span class="sxs-lookup"><span data-stu-id="af4fe-127">Change connectors or diagram layout.</span></span>  
  
### <a name="data-mining-menus"></a><span data-ttu-id="af4fe-128">Menus de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="af4fe-128">Data Mining Menus</span></span>  
 <span data-ttu-id="af4fe-129">Essas barras de ferramentas e itens de menu são fornecidos pelos suplementos que são específicos para cada forma ou tipo de modelo</span><span class="sxs-lookup"><span data-stu-id="af4fe-129">These toolbars and menu items are provided by the add-ins that are specific to each shape or model type</span></span>  
  
-   <span data-ttu-id="af4fe-130">Cada tipo de diagrama tem um menu de atalho para a forma que permita seu acesso a opções especiais.</span><span class="sxs-lookup"><span data-stu-id="af4fe-130">Each diagram type has a shortcut menu for the shape that lets you access special options.</span></span> <span data-ttu-id="af4fe-131">Embora várias opções nesse menu sejam comuns a todas as formas do Visio, algumas são exclusivas dos modelos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="af4fe-131">Although many options in this menu are common to all Visio shapes, some options are unique to the data mining templates</span></span>  
  
     <span data-ttu-id="af4fe-132">Por exemplo, em um diagrama de árvore de decisão, você pode clicar em um nó individual e recolher os nós filho para tornar esse diagrama mais simples ou mover os nós filho para outra página.</span><span class="sxs-lookup"><span data-stu-id="af4fe-132">For example, in a decision tree diagram, you can click an individual node and then collapse the child nodes to make the diagram simpler, or move child nodes to a separate page.</span></span>  
  
-   <span data-ttu-id="af4fe-133">Como a forma está associada aos dados do modelo, você também poderá fazer algumas explorações usando o diagrama:</span><span class="sxs-lookup"><span data-stu-id="af4fe-133">Because the shape is bound to the model data, you can also do some amount of exploration using the diagram:</span></span>  
  
     <span data-ttu-id="af4fe-134">Filtre os nós exibidos ou altere o nível da árvore ou a profundidade do grafo.</span><span class="sxs-lookup"><span data-stu-id="af4fe-134">Filter the nodes that are displayed, or change the level of the tree or depth of the graph.</span></span>  
  
     <span data-ttu-id="af4fe-135">Amplie o zoom em seções específicas, pesquise os nós que contenham um determinado atributo, ou filtre um grafo de dependência por suas extremidades (probabilidade).</span><span class="sxs-lookup"><span data-stu-id="af4fe-135">Zoom in on specific sections, search for nodes that contain a certain attribute, or filter a dependency graph by its edges (probability).</span></span>  
  
## <a name="walkthroughs"></a><span data-ttu-id="af4fe-136">Passo a passo</span><span class="sxs-lookup"><span data-stu-id="af4fe-136">Walkthroughs</span></span>  
 <span data-ttu-id="af4fe-137">Por obter exemplos de como trabalhar com um diagrama preenchido e interpretá-lo, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="af4fe-137">For examples of how to work with and interpret a completed diagram, see these topics:</span></span>  
  
 [<span data-ttu-id="af4fe-138">Passo a passo do diagrama de cluster</span><span class="sxs-lookup"><span data-stu-id="af4fe-138">Cluster Diagram Walkthrough</span></span>](cluster-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="af4fe-139">Passo a passo do diagrama de rede de dependências</span><span class="sxs-lookup"><span data-stu-id="af4fe-139">Dependency Net Diagram Walkthrough</span></span>](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="af4fe-140">Passo a passo do diagrama de árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="af4fe-140">Decision Tree Diagram Walkthrough</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
## <a name="see-also"></a><span data-ttu-id="af4fe-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af4fe-141">See Also</span></span>  
 [<span data-ttu-id="af4fe-142">Pesquisando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="af4fe-142">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
