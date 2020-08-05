---
title: Adicionar um manipulador de eventos a um pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- event handlers [Integration Services], creating
ms.assetid: 5e56885d-8658-480a-bed9-3f2f8003fd78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 007d81a395e06ac5a97210cd3e3ed6eea91aee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573263"
---
# <a name="add-an-event-handler-to-a-package"></a><span data-ttu-id="f80f8-102">Adicionar um manipulador de eventos a um pacote</span><span class="sxs-lookup"><span data-stu-id="f80f8-102">Add an Event Handler to a Package</span></span>
  <span data-ttu-id="f80f8-103">No momento da execução, contêineres e tarefas elevam os eventos.</span><span class="sxs-lookup"><span data-stu-id="f80f8-103">At run time, containers and tasks raise events.</span></span> <span data-ttu-id="f80f8-104">Você pode criar manipuladores de eventos personalizados que respondam a esses eventos, executando um fluxo de trabalho quando o evento for gerado.</span><span class="sxs-lookup"><span data-stu-id="f80f8-104">You can create custom event handlers that respond to these events by running a workflow when the event is raised.</span></span> <span data-ttu-id="f80f8-105">Por exemplo, você pode criar um manipulador de eventos que envia uma mensagem de e-mail quando uma tarefa falha.</span><span class="sxs-lookup"><span data-stu-id="f80f8-105">For example, you can create an event handler that sends an e-mail message when a task fails.</span></span>  
  
 <span data-ttu-id="f80f8-106">Um manipulador de eventos é semelhante a um pacote.</span><span class="sxs-lookup"><span data-stu-id="f80f8-106">An event handler is similar to a package.</span></span> <span data-ttu-id="f80f8-107">Como um pacote, um manipulador de eventos pode fornecer escopo para variáveis e incluir um fluxo de controle e fluxos de dados opcionais.</span><span class="sxs-lookup"><span data-stu-id="f80f8-107">Like a package, an event handler can provide scope for variables, and includes a control flow and optional data flows.</span></span> <span data-ttu-id="f80f8-108">Você pode criar manipuladores de eventos para pacotes, o contêiner Loop Foreach, o contêiner Loop For, o contêiner Sequência e todas as tarefas.</span><span class="sxs-lookup"><span data-stu-id="f80f8-108">You can build event handlers for packages, the Foreach Loop container, the For Loop container, the Sequence container, and all tasks.</span></span>  
  
 <span data-ttu-id="f80f8-109">Você cria manipuladores de eventos usando a superfície de design da guia **Manipuladores de Eventos** no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f80f8-109">You create event handlers by using the design surface of the **Event Handlers** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="f80f8-110">Quando a guia **Manipuladores de Eventos** está ativa, os nós **Itens de Fluxo de Controle** e **Tarefas de Plano de Manutenção** da Caixa de Ferramentas no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] contêm a tarefa e contêineres para criar o fluxo de controle do manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f80f8-110">When the **Event Handlers** tab is active, the **Control Flow Items** and **Maintenance Plan Tasks** nodes of the Toolbox in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer contain the task and containers for building the control flow in the event handler.</span></span> <span data-ttu-id="f80f8-111">Os nós **Origens de Fluxo de Dados**, **Transformações**e **Destinos de Fluxos de Dados** contêm as fontes de dados, transformações e destinos para criar os fluxos de dados no manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f80f8-111">The **Data Flow Sources**, **Transformations**, **and Data Flow Destinations** nodes contain the data sources, transformations, and destinations for building the data flows in the event handler.</span></span> <span data-ttu-id="f80f8-112">Para obter mais informações, consulte [Fluxo de Controle](control-flow/control-flow.md) e [Fluxo de Dados](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="f80f8-112">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="f80f8-113">A guia **Manipuladores de Eventos** também inclui a área Gerenciadores de **Conexões** , em que você pode criar e modificar os gerenciadores de conexões que os manipuladores de eventos usam para conectar servidores e fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="f80f8-113">The **Event Handlers** tab also includes the **Connections** Managers area where you can create and modify the connection managers that event handlers use to connect to servers and data sources.</span></span> <span data-ttu-id="f80f8-114">Para obter mais informações, consulte [Criar gerenciadores de conexões](../../2014/integration-services/create-connection-managers.md).</span><span class="sxs-lookup"><span data-stu-id="f80f8-114">For more information, see [Create Connection Managers](../../2014/integration-services/create-connection-managers.md).</span></span>  
  
### <a name="to-create-an-event-handler"></a><span data-ttu-id="f80f8-115">Para criar um manipulador de eventos</span><span class="sxs-lookup"><span data-stu-id="f80f8-115">To create an event handler</span></span>  
  
1.  <span data-ttu-id="f80f8-116">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="f80f8-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f80f8-117">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="f80f8-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f80f8-118">Clique na guia **Manipuladores de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="f80f8-118">Click the **Event Handlers** tab.</span></span>  
  
     <span data-ttu-id="f80f8-119">![Captura de tela da superfície de design com manipulador de Eventos](media/eventhandlers.gif "Captura de tela da superfície de design com manipulador de Eventos")</span><span class="sxs-lookup"><span data-stu-id="f80f8-119">![Screenshot of design surface with event handler](media/eventhandlers.gif "Screenshot of design surface with event handler")</span></span>  
  
     <span data-ttu-id="f80f8-120">Criar o fluxo de controle e os fluxos de dados em um manipulador de eventos é semelhante a criar o fluxo de controle e os fluxos de dados em um pacote.</span><span class="sxs-lookup"><span data-stu-id="f80f8-120">Creating the control flow and data flows in an event handler is similar to creating the control flow and data flows in a package.</span></span> <span data-ttu-id="f80f8-121">Para obter mais informações, consulte [Fluxo de Controle](control-flow/control-flow.md) e [Fluxo de Dados](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="f80f8-121">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
4.  <span data-ttu-id="f80f8-122">Na lista **Executável** , selecione o executável para o qual você quer criar um manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f80f8-122">In the **Executable** list, select the executable for which you want to create an event handler.</span></span>  
  
5.  <span data-ttu-id="f80f8-123">Na lista **Manipulador de Eventos** , selecione o manipulador de eventos que você quer criar.</span><span class="sxs-lookup"><span data-stu-id="f80f8-123">In the **Event handler** list, select the event handler you want to build.</span></span>  
  
6.  <span data-ttu-id="f80f8-124">Clique no link na superfície de design da guia **Manipulador de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="f80f8-124">Click the link on the design surface of the **Event Handler** tab.</span></span>  
  
7.  <span data-ttu-id="f80f8-125">Adicione itens de fluxo de controle ao manipulador de eventos e conecte itens usando uma restrição de precedência arrastando a restrição de um item de controle de fluxo para outro.</span><span class="sxs-lookup"><span data-stu-id="f80f8-125">Add control flow items to the event handler, and connect items using a precedence constraint by dragging the constraint from one control flow item to another.</span></span> <span data-ttu-id="f80f8-126">Para obter mais informações, consulte [Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="f80f8-126">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
8.  <span data-ttu-id="f80f8-127">Opcionalmente, adicione uma tarefa de Fluxo de Dados e, na superfície da guia **Fluxo de Dados** , crie um fluxo de dados para o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f80f8-127">Optionally, add a Data Flow task, and on the design surface of the **Data Flow** tab, create a data flow for the event handler.</span></span> <span data-ttu-id="f80f8-128">Para obter mais informações, consulte [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="f80f8-128">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
9. <span data-ttu-id="f80f8-129">No menu **Arquivo** , clique em **Salvar Itens Selecionados** para salvar o pacote.</span><span class="sxs-lookup"><span data-stu-id="f80f8-129">On the **File** menu, click **Save Selected Items** to save the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f80f8-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f80f8-130">See Also</span></span>  
 <span data-ttu-id="f80f8-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="f80f8-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span></span>  
 [<span data-ttu-id="f80f8-132">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f80f8-132">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
