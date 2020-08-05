---
title: Adicionar Enumeração a um fluxo de controle | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding enumerations
- Foreach Loop containers
- control flow [Integration Services], enumerations
- repeating workflows
- enumerations [Integration Services]
ms.assetid: f212b5fb-3cc4-422e-9b7c-89eb769a812a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59b8569880fdf1a49f5f2ca1f6841841f9790af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573251"
---
# <a name="add-enumeration-to-a-control-flow"></a><span data-ttu-id="8d5e8-102">Adicionar enumeração a um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="8d5e8-102">Add Enumeration to a Control Flow</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="8d5e8-103">inclui o contêiner do Loop Foreach, um elemento de fluxo de controle que torna simples a inclusão de um constructo de loop que enumera arquivos e objetos no fluxo de controle de um pacote.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-103">includes the Foreach Loop container, a control flow element that makes it simple to include a looping construct that enumerates files and objects in the control flow of a package.</span></span> <span data-ttu-id="8d5e8-104">Para obter mais informações, consulte [Contêiner Loop Foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8d5e8-104">For more information, see [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="8d5e8-105">O contêiner Loop Foreach não fornece nenhuma funcionalidade, ele só fornece a estrutura na qual você cria o fluxo de controle repetível, especifica o tipo do enumerados e configura o enumerador.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-105">The Foreach Loop container provides no functionality; it provides only the structure in which you build the repeatable control flow, specify an enumerator type, and configure the enumerator.</span></span> <span data-ttu-id="8d5e8-106">Para fornecer funcionalidade de contêiner, você deve incluir no mínimo uma tarefa no contêiner Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-106">To provide container functionality, you must include at least one task in the Foreach Loop container.</span></span> <span data-ttu-id="8d5e8-107">Para obter mais informações, consulte [Tarefas do Integration Services](control-flow/integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="8d5e8-107">For more information, see [Integration Services Tasks](control-flow/integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="8d5e8-108">O contêiner Loop Foreach pode incluir um fluxo de controle com várias tarefas e outros contêineres.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-108">The Foreach Loop container can include a control flow with multiple tasks and other containers.</span></span> <span data-ttu-id="8d5e8-109">Adicionar tarefas e contêineres ao contêiner Loop Foreach é semelhante a adicioná-las a um pacote, exceto que você arrasta as tarefas e contêineres para o contêiner Loop Foreach e não para o pacote.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-109">Adding tasks and containers to a Foreach Loop container is similar to adding them to a package, except you drag the tasks and containers to the Foreach Loop container instead of to the package.</span></span> <span data-ttu-id="8d5e8-110">Se o contêiner Loop Foreach incluir mais de uma tarefa ou contêiner, você poderá conectá-los usando as restrições de precedência, assim como faria em um pacote.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-110">If the Foreach Loop container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="8d5e8-111">Para obter informações, consulte [Restrições de precedência](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="8d5e8-111">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
### <a name="to-implement-a-foreach-loop-container-in-a-control-flow"></a><span data-ttu-id="8d5e8-112">Para implementar um contêiner Loop Foreach em um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="8d5e8-112">To implement a Foreach Loop container in a control flow</span></span>  
  
1.  <span data-ttu-id="8d5e8-113">Adicione o contêiner Loop Foreach ao pacote.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-113">Add the Foreach Loop container to the package.</span></span> <span data-ttu-id="8d5e8-114">Para obter mais informações, consulte [Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="8d5e8-114">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="8d5e8-115">.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-115">.</span></span>  
  
2.  <span data-ttu-id="8d5e8-116">Adicione tarefas e contêineres ao contêiner Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-116">Add tasks and containers to the Foreach Loop container.</span></span> <span data-ttu-id="8d5e8-117">Para obter mais informações, consulte [Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="8d5e8-117">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="8d5e8-118">.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-118">.</span></span>  
  
3.  <span data-ttu-id="8d5e8-119">Conecte tarefas e contêineres no contêiner Loop Foreach usando restrições de precedência.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-119">Connect tasks and containers in the Foreach Loop container using precedence constraints.</span></span> <span data-ttu-id="8d5e8-120">Para obter mais informações, consulte [Como conectar tarefas e contêineres utilizando uma restrição de precedência padrão](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="8d5e8-120">For more information, see [Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span></span>  
  
4.  <span data-ttu-id="8d5e8-121">Configure o contêiner Loop Foreach.</span><span class="sxs-lookup"><span data-stu-id="8d5e8-121">Configure the Foreach Loop container.</span></span> <span data-ttu-id="8d5e8-122">Para obter mais informações, consulte [Configurar um contêiner Loop Foreach](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8d5e8-122">For more information, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d5e8-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d5e8-123">See Also</span></span>  
 <span data-ttu-id="8d5e8-124">[Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8d5e8-124">[Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="8d5e8-125">[Agrupar ou desagrupar componentes](group-or-ungroup-components.md) </span><span class="sxs-lookup"><span data-stu-id="8d5e8-125">[Group or Ungroup Components](group-or-ungroup-components.md) </span></span>  
 <span data-ttu-id="8d5e8-126">[Restrições de precedência](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="8d5e8-126">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="8d5e8-127">[Adicionar iteração a um fluxo de controle](add-iteration-to-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8d5e8-127">[Add Iteration to a Control Flow](add-iteration-to-a-control-flow.md) </span></span>  
 [<span data-ttu-id="8d5e8-128">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="8d5e8-128">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
