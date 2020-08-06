---
title: Definir as propriedades de uma tarefa ou contêiner | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], properties
ms.assetid: 52d47ca4-fb8c-493d-8b2b-48bb269f859b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0a4c556b94af02c2f874f2740a70b1294c35e653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685832"
---
# <a name="set-the-properties-of-a-task-or-container"></a><span data-ttu-id="8e88e-102">Definir as propriedades de uma tarefa ou de um contêiner</span><span class="sxs-lookup"><span data-stu-id="8e88e-102">Set the Properties of a Task or Container</span></span>
  <span data-ttu-id="8e88e-103">Você pode definir a maioria das propriedades de tarefas e contêineres usando a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="8e88e-103">You can set most properties of tasks and containers by using the **Properties** window.</span></span> <span data-ttu-id="8e88e-104">As exceções são as propriedades de coleções de tarefas e as propriedades que são muito complexas para se definir usando a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="8e88e-104">The exceptions are properties of task collections and properties that are too complex to set by using the **Properties** window.</span></span> <span data-ttu-id="8e88e-105">Por exemplo, você não pode configurar o enumerador que o contêiner Loop Foreach usa na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="8e88e-105">For example, you cannot configure the enumerator that the Foreach Loop container uses in the **Properties** window.</span></span> <span data-ttu-id="8e88e-106">Você deve usar um editor de tarefa ou de contêiner para definir essas propriedades complexas.</span><span class="sxs-lookup"><span data-stu-id="8e88e-106">You must use a task or container editor to set these complex properties.</span></span> <span data-ttu-id="8e88e-107">A maioria dos editores de tarefas e contêineres possui vários nós, e cada nó contém propriedades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8e88e-107">Most task and container editors have multiple nodes and each node contains related properties.</span></span> <span data-ttu-id="8e88e-108">O nome do nó indica o assunto das propriedades contidas no nó.</span><span class="sxs-lookup"><span data-stu-id="8e88e-108">The name of the node indicates the subject of the properties that the node contains.</span></span>  
  
 <span data-ttu-id="8e88e-109">Os procedimentos a seguir descrevem como definir as propriedades de uma tarefa ou de um contêiner usando as janelas **Propriedades** ou o editor de tarefas ou de contêineres correspondente.</span><span class="sxs-lookup"><span data-stu-id="8e88e-109">The following procedures describe how to set the properties of a task or container by using either the **Properties** windows, or the corresponding task or container editor.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-the-properties-window"></a><span data-ttu-id="8e88e-110">Para definir as propriedades de uma tarefa ou de um contêiner usando a janela Propriedades</span><span class="sxs-lookup"><span data-stu-id="8e88e-110">To set the properties of a task or container by using the Properties window</span></span>  
  
1.  <span data-ttu-id="8e88e-111">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="8e88e-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8e88e-112">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="8e88e-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8e88e-113">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="8e88e-113">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="8e88e-114">Na superfície de design da guia **Fluxo de Controle** , clique com o botão direito do mouse na tarefa ou no contêiner e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8e88e-114">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="8e88e-115">Na janela **Propriedades** , atualize o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="8e88e-115">In the **Properties** window, update the property value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e88e-116">A maioria das propriedades pode ser definida digitando um valor diretamente na caixa de texto ou selecionando um valor de uma lista.</span><span class="sxs-lookup"><span data-stu-id="8e88e-116">Most properties can be set by typing a value directly in the text box, or by selecting a value from a list.</span></span> <span data-ttu-id="8e88e-117">Porém, algumas propriedades são mais complexas e têm um editor de propriedade personalizado.</span><span class="sxs-lookup"><span data-stu-id="8e88e-117">However, some properties are more complex and have a custom property editor.</span></span> <span data-ttu-id="8e88e-118">Para definir a propriedade, clique na caixa de texto e clique no botão de criação **(…)** para abrir o editor personalizado.</span><span class="sxs-lookup"><span data-stu-id="8e88e-118">To set the property, click in the text box, and then click the build **(...)** button to open the custom editor.</span></span>  
  
6.  <span data-ttu-id="8e88e-119">Como alternativa, crie expressões de propriedade para atualizar as propriedades da tarefa ou do contêiner dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="8e88e-119">Optionally, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="8e88e-120">Para obter mais informações, consulte [Adicionar ou alterar uma expressão de propriedade](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="8e88e-120">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="8e88e-121">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="8e88e-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-a-task-or-container-editor"></a><span data-ttu-id="8e88e-122">Para definir as propriedades de uma tarefa ou de um contêiner usando um editor de tarefas ou de contêineres</span><span class="sxs-lookup"><span data-stu-id="8e88e-122">To set the properties of a task or container by using a task or container editor</span></span>  
  
1.  <span data-ttu-id="8e88e-123">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="8e88e-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8e88e-124">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="8e88e-124">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8e88e-125">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="8e88e-125">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="8e88e-126">Na superfície de design da guia **Fluxo de Controle** , clique com o botão direito do mouse na tarefa ou no contêiner e clique em **Editar** para abrir o editor correspondente.</span><span class="sxs-lookup"><span data-stu-id="8e88e-126">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Edit** to open the corresponding task or container editor.</span></span>  
  
     <span data-ttu-id="8e88e-127">Para obter informações sobre como configurar um contêiner Loop For, consulte [Para configurar um contêiner Loop For](control-flow/for-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8e88e-127">For information about how to configure the For Loop container, see [Configure a For Loop Container](control-flow/for-loop-container.md).</span></span>  
  
     <span data-ttu-id="8e88e-128">Para obter informações sobre como configurar o contêiner Loop Foreach, consulte [configurar um contêiner Loop Foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8e88e-128">For information about how to configure the Foreach Loop container, see [Configure a Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e88e-129">O contêiner Sequência não tem um editor personalizado.</span><span class="sxs-lookup"><span data-stu-id="8e88e-129">The Sequence container has no custom editor.</span></span>  
  
5.  <span data-ttu-id="8e88e-130">Se o editor de tarefas ou de contêineres tiver vários nós, clique no nó que contém a propriedade a ser definida.</span><span class="sxs-lookup"><span data-stu-id="8e88e-130">If the task or container editor has multiple nodes, click the node that contains the property that you want to set.</span></span>  
  
6.  <span data-ttu-id="8e88e-131">Você também pode clicar em **Expressões** e, na página **Expressões** , criar expressões de propriedade para atualizar as propriedades da tarefa ou do contêiner dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="8e88e-131">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="8e88e-132">Para obter mais informações, consulte [Adicionar ou alterar uma expressão de propriedade](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="8e88e-132">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="8e88e-133">Atualize o valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="8e88e-133">Update the property value.</span></span>  
  
8.  <span data-ttu-id="8e88e-134">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="8e88e-134">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e88e-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e88e-135">See Also</span></span>  
 <span data-ttu-id="8e88e-136">[Tarefas do Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="8e88e-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="8e88e-137">Contêineres do Integration Services</span><span class="sxs-lookup"><span data-stu-id="8e88e-137">Integration Services Containers</span></span>](control-flow/integration-services-containers.md)  
  
  
