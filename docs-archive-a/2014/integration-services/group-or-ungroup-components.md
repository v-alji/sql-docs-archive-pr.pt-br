---
title: Agrupar ou desagrupar componentes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- grouping containers
- tasks [Integration Services], grouping
- containers [Integration Services], grouping
- grouping tasks
ms.assetid: 34320838-c271-4f8c-90b3-1254690890bb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6811dffca41a12fe0afeeeb334e0107ac127c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570130"
---
# <a name="group-or-ungroup-components"></a><span data-ttu-id="6da0d-102">Agrupa ou desagrupa componentes</span><span class="sxs-lookup"><span data-stu-id="6da0d-102">Group or Ungroup Components</span></span>
  <span data-ttu-id="6da0d-103">As guias **Fluxo de Controle**, **Fluxo de dados**e **Manipuladores de Eventos** no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] dão suporte a agrupamento recolhível.</span><span class="sxs-lookup"><span data-stu-id="6da0d-103">The **Control Flow**, **Data Flow**, and **Event Handlers** tabs in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer supports collapsible grouping.</span></span> <span data-ttu-id="6da0d-104">Se um pacote tem muitos componentes, as guias podem ficar cheias, tornando difícil visualizar todos os componentes ao mesmo tempo e localizar o item com o qual você quer trabalhar.</span><span class="sxs-lookup"><span data-stu-id="6da0d-104">If a package has many components, the tabs can become crowded, making it difficult to view all the components at one time and to locate the item with which you want to work.</span></span> <span data-ttu-id="6da0d-105">O recurso de agrupamento desmontável, que pode conservar espaço na superfície de trabalho, e assim tornar mais fácil o trabalho com pacotes grandes.</span><span class="sxs-lookup"><span data-stu-id="6da0d-105">The collapsible grouping feature can conserve space on the work surface and make it easier to work with large packages.</span></span>  
  
 <span data-ttu-id="6da0d-106">Você seleciona os componentes que deseja agrupar, então os agrupa e, depois, expande ou recolhe os grupos para se adequarem ao seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="6da0d-106">You select the components that you want to group, group them, and then expand or collapse the groups to suit your work.</span></span> <span data-ttu-id="6da0d-107">Expandir um grupo lhe dá acesso às propriedades dos componentes no grupo.</span><span class="sxs-lookup"><span data-stu-id="6da0d-107">Expanding a group provides access to the properties of the components in the group.</span></span> <span data-ttu-id="6da0d-108">As restrições de precedência que conectam tarefas e contêineres são automaticamente incluídas no grupo.</span><span class="sxs-lookup"><span data-stu-id="6da0d-108">The precedence constraints that connect tasks and containers are automatically included in the group.</span></span>  
  
 <span data-ttu-id="6da0d-109">As seguintes são considerações para agrupar componentes.</span><span class="sxs-lookup"><span data-stu-id="6da0d-109">The following are considerations for grouping components.</span></span>  
  
-   <span data-ttu-id="6da0d-110">Para agrupar componentes, o fluxo de controle, fluxo de dados ou manipulador de eventos deverá conter mais de um componente.</span><span class="sxs-lookup"><span data-stu-id="6da0d-110">To group components, the control flow, data flow, or event handler must contain more than one component.</span></span>  
  
-   <span data-ttu-id="6da0d-111">Os grupos também podem ser aninhados, tornando possível criar grupos dentro de grupos.</span><span class="sxs-lookup"><span data-stu-id="6da0d-111">Groups can also be nested, making it possible to create groups within groups.</span></span> <span data-ttu-id="6da0d-112">A superfície do design pode implementar vários grupos não aninhados, mas um componente pode pertencer somente a um grupo, exceto se os grupos estiverem aninhados.</span><span class="sxs-lookup"><span data-stu-id="6da0d-112">The design surface can implement multiple un-nested groups, but a component can belong to only one group, unless the groups are nested.</span></span>  
  
-   <span data-ttu-id="6da0d-113">Quando um pacote é salvo, o [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer salva o agrupamento, mas o agrupamento não tem nenhum efeito na execução de pacote.</span><span class="sxs-lookup"><span data-stu-id="6da0d-113">When a package is saved, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the grouping, but the grouping has no effect on package execution.</span></span> <span data-ttu-id="6da0d-114">A habilidade de agrupar componentes é um recurso de tempo de design, ela não afeta o comportamento de tempo de execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="6da0d-114">The ability to group components is a design-time feature; it does not affect the run-time behavior of the package.</span></span>  
  
### <a name="to-group-components"></a><span data-ttu-id="6da0d-115">Para agrupar componentes</span><span class="sxs-lookup"><span data-stu-id="6da0d-115">To group components</span></span>  
  
1.  <span data-ttu-id="6da0d-116">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="6da0d-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="6da0d-117">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="6da0d-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="6da0d-118">Clique na guia **Fluxo de Controle**, **Fluxo de Dados**ou **Manipuladores de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="6da0d-118">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="6da0d-119">Na superfície de design da guia, selecione os componentes que você deseja agrupar, clique com o botão direito do mouse no componente selecionado e clique em **Agrupar**.</span><span class="sxs-lookup"><span data-stu-id="6da0d-119">On the design surface of the tab, select the components you want to group, right-click a selected component, and then click **Group**.</span></span>  
  
5.  <span data-ttu-id="6da0d-120">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="6da0d-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-ungroup-components"></a><span data-ttu-id="6da0d-121">Para desagrupar componentes</span><span class="sxs-lookup"><span data-stu-id="6da0d-121">To ungroup components</span></span>  
  
1.  <span data-ttu-id="6da0d-122">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="6da0d-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="6da0d-123">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="6da0d-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="6da0d-124">Clique na guia **Fluxo de Controle**, **Fluxo de Dados**ou **Manipuladores de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="6da0d-124">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="6da0d-125">Na superfície de design da guia, selecione o grupo que contém o componente que você deseja desagrupar, clique com o botão direito do mouse no componente selecionado e clique em **Desagrupar**.</span><span class="sxs-lookup"><span data-stu-id="6da0d-125">On the design surface of the tab, select the group that contains the component you want to ungroup, right-click, and then click **Ungroup**.</span></span>  
  
5.  <span data-ttu-id="6da0d-126">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="6da0d-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da0d-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6da0d-127">See Also</span></span>  
 [<span data-ttu-id="6da0d-128">Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="6da0d-128">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
     
 [<span data-ttu-id="6da0d-129">Como conectar tarefas e contêineres por meio de uma restrição de precedência padrão</span><span class="sxs-lookup"><span data-stu-id="6da0d-129">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md)  
  
  
