---
title: Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], adding
- adding tasks
- adding containers
- tasks [Integration Services], adding
ms.assetid: 653084c6-87a3-45d5-b458-914ecf24d56a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8338a4143358d732a974287e587f482dc5c36a22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574862"
---
# <a name="add-or-delete-a-task-or-a-container-in-a-control-flow"></a><span data-ttu-id="6a2e3-102">Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="6a2e3-102">Add or Delete a Task or a Container in a Control Flow</span></span>
  <span data-ttu-id="6a2e3-103">Quando você está trabalhando no designer de fluxo de controle, a Caixa de Ferramentas do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer lista as tarefas que o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fornece para criar o fluxo de controle em um pacote.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-103">When you are working in the control flow designer, the Toolbox in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer lists the tasks that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides for building control flow in a package.</span></span> <span data-ttu-id="6a2e3-104">Para obter mais informações a Barra de Ferramentas, consulte [Caixa de Ferramentas do SSIS](../ssis-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="6a2e3-104">For more information about the Toolbox, see [SSIS Toolbox](../ssis-toolbox.md).</span></span>  
  
 <span data-ttu-id="6a2e3-105">Um pacote pode incluir várias instâncias da mesma tarefa.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-105">A package can include multiple instances of the same task.</span></span> <span data-ttu-id="6a2e3-106">Cada instância de uma tarefa é identificada exclusivamente no pacote e você pode configurar cada instância de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-106">Each instance of a task is uniquely identified in the package, and you can configure each instance differently.</span></span>  
  
 <span data-ttu-id="6a2e3-107">Se você excluir a tarefa, as restrições de precedência que conectam a tarefa às outras tarefas e contêineres no fluxo de controle também serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-107">If you delete a task, the precedence constraints that connect the task to other tasks and containers in the control flow are also deleted.</span></span>  
  
 <span data-ttu-id="6a2e3-108">Os procedimentos a seguir descrevem como adicionar ou excluir uma tarefa ou um contêiner no fluxo de controle de um pacote.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-108">The following procedures describe how to add or delete a task or container in the control flow of a package.</span></span>  
  
### <a name="to-add-a-task-or-a-container-to-a-control-flow"></a><span data-ttu-id="6a2e3-109">Para adicionar uma tarefa ou um contêiner a um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="6a2e3-109">To add a task or a container to a control flow</span></span>  
  
1.  <span data-ttu-id="6a2e3-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="6a2e3-111">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="6a2e3-112">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="6a2e3-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="6a2e3-113">Para abrir a **Caixa de Ferramentas**, clique em **Caixa de Ferramentas** no menu **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="6a2e3-113">To open the **Toolbox**, click **Toolbox** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="6a2e3-114">Expanda **Itens do Fluxo de Controle** e **Tarefas de Manutenção**.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-114">Expand **Control Flow Items** and **Maintenance Tasks**.</span></span>  
  
6.  <span data-ttu-id="6a2e3-115">Arraste as tarefas e os contêineres da **Caixa de Ferramentas** para a superfície de design da guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="6a2e3-115">Drag tasks and containers from the **Toolbox** to the design surface of the **Control Flow** tab.</span></span>  
  
7.  <span data-ttu-id="6a2e3-116">Conecte uma tarefa ou um contêiner dentro do pacote do fluxo de controle arrastando seu conector até outro componente no fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-116">Connect a task or container within the package control flow by dragging its connector to another component in the control flow.</span></span>  
  
8.  <span data-ttu-id="6a2e3-117">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="6a2e3-117">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-task-or-a-container-from-a-control-flow"></a><span data-ttu-id="6a2e3-118">Para excluir uma tarefa ou um contêiner de um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="6a2e3-118">To delete a task or a container from a control flow</span></span>  
  
1.  <span data-ttu-id="6a2e3-119">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="6a2e3-120">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-120">In Solution Explorer, double-click the package to open it.</span></span> <span data-ttu-id="6a2e3-121">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6a2e3-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="6a2e3-122">Clique na guia **Fluxo de Controle** , clique com o botão direito do mouse na tarefa ou no contêiner a ser removido e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-122">Click the **Control Flow** tab, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
    -   <span data-ttu-id="6a2e3-123">Abra o **Explorador de Pacotes**.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-123">Open **Package Explorer**.</span></span> <span data-ttu-id="6a2e3-124">Na pasta **Executáveis** , clique com o botão direito do mouse na tarefa ou no contêiner a ser removido e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="6a2e3-124">From the **Executables** folder, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="6a2e3-125">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="6a2e3-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a2e3-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a2e3-126">See Also</span></span>  
 <span data-ttu-id="6a2e3-127">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="6a2e3-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="6a2e3-128">[Contêineres de Integration Services](integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="6a2e3-128">[Integration Services Containers](integration-services-containers.md) </span></span>  
 [<span data-ttu-id="6a2e3-129">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="6a2e3-129">Control Flow</span></span>](control-flow.md)  
  
  
