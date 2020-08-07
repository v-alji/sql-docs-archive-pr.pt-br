---
title: Contêiner da Sequência | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sequencecontainer.f1
helpviewer_keywords:
- Sequence container
- grouping control flows
- containers [Integration Services], Sequence
- subset control flow [Integration Services]
ms.assetid: 7731f91e-b8b3-4d96-a0d9-73f568547cb3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b972f923e2134363ba1b378beebebbeb1e5d6bb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575255"
---
# <a name="sequence-container"></a><span data-ttu-id="6b355-102">Contêiner de sequência</span><span class="sxs-lookup"><span data-stu-id="6b355-102">Sequence Container</span></span>
  <span data-ttu-id="6b355-103">O contêiner da sequência define um fluxo de controle que é um subconjunto do fluxo de controle do pacote.</span><span class="sxs-lookup"><span data-stu-id="6b355-103">The Sequence container defines a control flow that is a subset of the package control flow.</span></span> <span data-ttu-id="6b355-104">Os contêineres da sequência agrupam o pacote em vários fluxos de controle separados, cada um contendo uma ou mais tarefas e contêineres, que são executados dentro do fluxo de controle de pacote geral.</span><span class="sxs-lookup"><span data-stu-id="6b355-104">Sequence containers group the package into multiple separate control flows, each containing one or more tasks and containers that run within the overall package control flow.</span></span>  
  
 <span data-ttu-id="6b355-105">O contêiner Sequência pode incluir múltiplas tarefas além de outros contêineres.</span><span class="sxs-lookup"><span data-stu-id="6b355-105">The Sequence container can include multiple tasks in addition to other containers.</span></span> <span data-ttu-id="6b355-106">Adicionar tarefas e contêineres a um contêiner de Sequência é semelhante a adicioná-los a um pacote, exceto que você arrasta as tarefas e contêineres para o contêiner de Sequência e não para o contêiner de pacote.</span><span class="sxs-lookup"><span data-stu-id="6b355-106">Adding tasks and containers to a Sequence container is similar to adding them to a package, except you drag the tasks and containers to the Sequence container instead of to the package container.</span></span> <span data-ttu-id="6b355-107">Se o contêiner Sequência incluir mais de uma tarefa ou contêiner, você pode conectá-los usando restrições de precedência, exatamente como faria em um pacote.</span><span class="sxs-lookup"><span data-stu-id="6b355-107">If the Sequence container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="6b355-108">Para obter informações, consulte [Restrições de precedência](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="6b355-108">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="6b355-109">São muitos os benefícios para utilizar um contêiner da sequência:</span><span class="sxs-lookup"><span data-stu-id="6b355-109">There are many benefits of using a Sequence container:</span></span>  
  
-   <span data-ttu-id="6b355-110">Desabilitar grupos de tarefas para focalizar a depuração de pacote em um subconjunto do fluxo de controle de pacote.</span><span class="sxs-lookup"><span data-stu-id="6b355-110">Disabling groups of tasks to focus package debugging on one subset of the package control flow.</span></span>  
  
-   <span data-ttu-id="6b355-111">Gerenciar as propriedades de várias tarefas em um local definindo-se as propriedades em um contêiner da sequência em vez de em tarefas individuais.</span><span class="sxs-lookup"><span data-stu-id="6b355-111">Managing properties on multiple tasks in one location by setting properties on a Sequence container instead of on the individual tasks.</span></span>  
  
     <span data-ttu-id="6b355-112">Por exemplo, você pode definir a propriedade `Disable` do contêiner da sequência como `True` para desabilitar todas as tarefas e contêineres no contêiner da sequência.</span><span class="sxs-lookup"><span data-stu-id="6b355-112">For example, you can set the `Disable` property of the Sequence container to `True` to disable all the tasks and containers in the Sequence container.</span></span>  
  
-   <span data-ttu-id="6b355-113">Fornecer o escopo para variáveis que um grupo de tarefas relacionadas e contêineres usa.</span><span class="sxs-lookup"><span data-stu-id="6b355-113">Providing scope for variables that a group of related tasks and containers use.</span></span>  
  
-   <span data-ttu-id="6b355-114">Agrupar muitas tarefas para que você possa gerenciá-las mais facilmente com o recolhimento e a expansão do contêiner de sequência.</span><span class="sxs-lookup"><span data-stu-id="6b355-114">Grouping many tasks so you can more easily managed them by collapsing and expanding the Sequence container.</span></span>  
  
     <span data-ttu-id="6b355-115">Você também pode criar grupos que expandem e recolhem usando a caixa **Grupo** .</span><span class="sxs-lookup"><span data-stu-id="6b355-115">You can also create task groups, which expand and collapse using the **Group** box.</span></span> <span data-ttu-id="6b355-116">Entretanto, a caixa **Grupo** é um recurso de tempo de design que não tem propriedades ou comportamento de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="6b355-116">However, the **Group** box is a design-time feature that has no properties or run-time behavior.</span></span> <span data-ttu-id="6b355-117">Para obter mais informações, consulte [Agrupar ou desagrupar componentes](../group-or-ungroup-components.md)</span><span class="sxs-lookup"><span data-stu-id="6b355-117">For more information, see [Group or Ungroup Components](../group-or-ungroup-components.md)</span></span>  
  
-   <span data-ttu-id="6b355-118">Definir um atributo de transação no contêiner de sequência para definir uma transação para um subconjunto do fluxo de controle do pacote.</span><span class="sxs-lookup"><span data-stu-id="6b355-118">Set a transaction attribute on the Sequence container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="6b355-119">Desse modo, é possível gerenciar as transações em um nível mais granular.</span><span class="sxs-lookup"><span data-stu-id="6b355-119">In this way, you can manage transactions at a more granular level.</span></span>  
  
     <span data-ttu-id="6b355-120">Por exemplo, se um contêiner da sequência incluir duas tarefas relacionadas, uma que exclui dados de uma tabela e outra que insere, você poderá configurar uma transação para assegurar que a ação de exclusão seja revertida se a ação de inserção falhar.</span><span class="sxs-lookup"><span data-stu-id="6b355-120">For example, if a Sequence container includes two related tasks, one task that deletes data in a table and another task that inserts data into a table, you can configure a transaction to ensure that the delete action is rolled back if the insert action fails.</span></span> <span data-ttu-id="6b355-121">Para obter mais informações, consulte [Transações do Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="6b355-121">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-sequence-container"></a><span data-ttu-id="6b355-122">Configuração do contêiner da sequência</span><span class="sxs-lookup"><span data-stu-id="6b355-122">Configuration of the Sequence Container</span></span>  
 <span data-ttu-id="6b355-123">O contêiner da sequência não tem nenhuma interface do usuário personalizada e você somente poderá configurá-lo na janela **Propriedades** do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="6b355-123">The Sequence container has no custom user interface and you can configure it only in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="6b355-124">Para obter mais informações sobre como definir essas propriedades programaticamente, consulte a documentação da classe **T:Microsoft.SqlServer.Dts.Runtime.Sequence** no Guia do Desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="6b355-124">For information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.Sequence** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6b355-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6b355-125">Related Tasks</span></span>  
 <span data-ttu-id="6b355-126">Para obter informações sobre como definir as propriedades do componente no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="6b355-126">For information about how to set properties of the component in the [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b355-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6b355-127">See Also</span></span>  
 <span data-ttu-id="6b355-128">[Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="6b355-128">[Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="6b355-129">[Como conectar tarefas e contêineres por meio de uma restrição de precedência padrão](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="6b355-129">[Connect Tasks and Containers by Using a Default Precedence Constraint](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="6b355-130">Contêineres do Integration Services</span><span class="sxs-lookup"><span data-stu-id="6b355-130">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
