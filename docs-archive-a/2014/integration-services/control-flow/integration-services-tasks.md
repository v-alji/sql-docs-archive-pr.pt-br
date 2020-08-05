---
title: Tarefas do Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [Integration Services], tasks
- files [Integration Services], task options
- workflow tasks [Integration Services]
- Integration Services, tasks
- adding package tasks
- tasks [Integration Services], listed
- SSIS tasks
- SSIS, tasks
- control flow [Integration Services], tasks
- tasks [Integration Services]
- grouping tasks
- tasks [Integration Services], about tasks
- SQL Server Integration Services tasks
- data preparation tasks [Integration Services]
- directory operations [Integration Services]
ms.assetid: 75c8901d-6966-4af3-abe5-10af6dd9313b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5fa58dec1e05a0333c295efc7f00a1d6df935792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572628"
---
# <a name="integration-services-tasks"></a><span data-ttu-id="deb37-102">Tarefas do Integration Services</span><span class="sxs-lookup"><span data-stu-id="deb37-102">Integration Services Tasks</span></span>
  <span data-ttu-id="deb37-103">As tarefas são elementos de fluxo de controle que definem unidades de trabalho que são executadas em um fluxo de controle de pacote.</span><span class="sxs-lookup"><span data-stu-id="deb37-103">Tasks are control flow elements that define units of work that are performed in a package control flow.</span></span> <span data-ttu-id="deb37-104">Um pacote do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é composto por uma ou mais tarefas.</span><span class="sxs-lookup"><span data-stu-id="deb37-104">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package is made up of one or more tasks.</span></span> <span data-ttu-id="deb37-105">Se o pacote contiver mais de uma tarefa, elas estarão conectadas e sequenciadas no fluxo de controle por restrições de precedência.</span><span class="sxs-lookup"><span data-stu-id="deb37-105">If the package contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span>  
  
 <span data-ttu-id="deb37-106">Você também poderá escrever tarefas personalizadas que usam uma linguagem de programação que oferece suporte a COM, como Visual Basic, ou uma linguagem de programação .NET, como C#.</span><span class="sxs-lookup"><span data-stu-id="deb37-106">You can also write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span>  
  
 <span data-ttu-id="deb37-107">O Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)], a ferramenta gráfica no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para trabalhar com pacotes, fornece a superfície de design para criar fluxo de controle de pacote e oferece editores personalizados para configurar tarefas.</span><span class="sxs-lookup"><span data-stu-id="deb37-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the graphical tool in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] for working with packages, provides the design surface for creating package control flow, and provides custom editors for configuring tasks.</span></span> <span data-ttu-id="deb37-108">Você também pode programar o modelo de objeto do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para criar pacotes programaticamente.</span><span class="sxs-lookup"><span data-stu-id="deb37-108">You can also program the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model to create packages programmatically.</span></span>  
  
## <a name="types-of-tasks"></a><span data-ttu-id="deb37-109">Tipos de tarefas</span><span class="sxs-lookup"><span data-stu-id="deb37-109">Types of Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="deb37-110">inclui os tipos de tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="deb37-110">includes the following types of tasks.</span></span>  
  
 <span data-ttu-id="deb37-111">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="deb37-111">Data Flow Task</span></span>  
 <span data-ttu-id="deb37-112">A tarefa que executa fluxos de dados para extrair dados, aplica transformações no nível de coluna e carrega dados.</span><span class="sxs-lookup"><span data-stu-id="deb37-112">The task that runs data flows to extract data, apply column level transformations, and load data.</span></span>  
  
 <span data-ttu-id="deb37-113">Tarefas de preparação de dados</span><span class="sxs-lookup"><span data-stu-id="deb37-113">Data Preparation Tasks</span></span>  
 <span data-ttu-id="deb37-114">Essas tarefas executam os seguintes processos: copiam arquivos e diretórios; baixam arquivos e dados; executam métodos da Web; aplicam operações a documentos XML; e criam perfis de dados para limpeza.</span><span class="sxs-lookup"><span data-stu-id="deb37-114">These tasks do the following processes: copy files and directories; download files and data; run Web methods; apply operations to XML documents; and profile data for cleansing.</span></span>  
  
 <span data-ttu-id="deb37-115">Tarefas de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="deb37-115">Workflow Tasks</span></span>  
 <span data-ttu-id="deb37-116">As tarefas que se comunicam com outros processos para executar pacotes, executar programas ou arquivos em lote, enviar e receber mensagens entre pacotes, enviar mensagens de email, ler dados WMI (Instrumentação de Gerenciamento do Windows) e observar eventos WMI.</span><span class="sxs-lookup"><span data-stu-id="deb37-116">The tasks that communicate with other processes to run packages, run programs or batch files, send and receive messages between packages, send e-mail messages, read Windows Management Instrumentation (WMI) data, and watch for WMI events.</span></span>  
  
 <span data-ttu-id="deb37-117">Tarefas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="deb37-117">SQL Server Tasks</span></span>  
 <span data-ttu-id="deb37-118">As tarefas que acessam, copiam, inserem, excluem e modificam objetos e dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="deb37-118">The tasks that access, copy, insert, delete, and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects and data.</span></span>  
  
 <span data-ttu-id="deb37-119">Tarefas de script</span><span class="sxs-lookup"><span data-stu-id="deb37-119">Scripting Tasks</span></span>  
 <span data-ttu-id="deb37-120">As tarefas que estendem a funcionalidade de pacotes usando scripts.</span><span class="sxs-lookup"><span data-stu-id="deb37-120">The tasks that extend package functionality by using scripts.</span></span>  
  
 <span data-ttu-id="deb37-121">Tarefas Analysis Services</span><span class="sxs-lookup"><span data-stu-id="deb37-121">Analysis Services Tasks</span></span>  
 <span data-ttu-id="deb37-122">As tarefas que criam, modificam, excluem e processam objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="deb37-122">The tasks that create, modify, delete, and process [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="deb37-123">Tarefas de manutenção</span><span class="sxs-lookup"><span data-stu-id="deb37-123">Maintenance Tasks</span></span>  
 <span data-ttu-id="deb37-124">As tarefas que executam funções administrativas como fazer backup e reduzir bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , recriar e reorganizar índices e executar trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="deb37-124">The tasks that perform administrative functions such as backing up and shrinking [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, rebuilding and reorganizing indexes, and running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="deb37-125">Tarefas personalizadas</span><span class="sxs-lookup"><span data-stu-id="deb37-125">Custom Tasks</span></span>  
 <span data-ttu-id="deb37-126">Além disso, você pode gravar tarefas personalizadas que usam uma linguagem de programação que dá suporte a COM, como o Visual Basic, ou uma linguagem de programação .NET, como o C#.</span><span class="sxs-lookup"><span data-stu-id="deb37-126">Additionally, you can write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span> <span data-ttu-id="deb37-127">Para acessar sua tarefa personalizada no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] , você poderá criar e registrar uma interface do usuário para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="deb37-127">If you want to access your custom task in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can create and register a user interface for the task.</span></span> <span data-ttu-id="deb37-128">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="deb37-128">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="configuration-of-tasks"></a><span data-ttu-id="deb37-129">Configuração de tarefas</span><span class="sxs-lookup"><span data-stu-id="deb37-129">Configuration of Tasks</span></span>  
 <span data-ttu-id="deb37-130">Um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pode conter uma única tarefa, como uma tarefa Execute SQL, que exclui registros de uma tabela de banco de dados quando o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="deb37-130">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can contain a single task, such as an Execute SQL task that deletes records in a database table when the package runs.</span></span> <span data-ttu-id="deb37-131">Porém, normalmente os pacotes contêm várias tarefas e cada tarefa é definida para ser executada dentro do contexto do fluxo de controle do pacote.</span><span class="sxs-lookup"><span data-stu-id="deb37-131">However, packages typically contain several tasks, and each task is set to run within the context of the package control flow.</span></span> <span data-ttu-id="deb37-132">Manipuladores de evento, que são fluxos de trabalho executados como resposta a eventos de tempo de execução, também podem ter tarefas.</span><span class="sxs-lookup"><span data-stu-id="deb37-132">Event handlers, which are workflows that run in response to run-time events, can also have tasks.</span></span>  
  
 <span data-ttu-id="deb37-133">Para obter mais informações sobre como adicionar uma tarefa a um pacote usando o Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="deb37-133">For more information about adding a task to a package using [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span></span>  
  
 <span data-ttu-id="deb37-134">Para obter mais informações sobre como adicionar uma tarefa a um pacote programaticamente, consulte [Adicionando tarefas programaticamente](../building-packages-programmatically/adding-tasks-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="deb37-134">For more information about adding a task to a package programmatically, see [Adding Tasks Programmatically](../building-packages-programmatically/adding-tasks-programmatically.md).</span></span>  
  
 <span data-ttu-id="deb37-135">Toda tarefa pode ser configurada individualmente usando as caixas de diálogo personalizadas de cada tarefa que o Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] oferece, ou a janela Propriedades incluída no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="deb37-135">Each task can be configured individually using the custom dialog boxes for each task that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides, or the Properties window included in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="deb37-136">Um pacote pode incluir várias tarefas do mesmo tipo, por exemplo, seis tarefas Execute SQL, sendo que cada tarefa pode ser configurada de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="deb37-136">A package can include multiple tasks of the same type-for example, six Execute SQL tasks-and each task can be configured differently.</span></span> <span data-ttu-id="deb37-137">Para obter mais informações, consulte [Definir as propriedades de tarefas ou contêineres](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="deb37-137">For more information, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="tasks-connections-and-groups"></a><span data-ttu-id="deb37-138">Conexões e grupos de tarefas</span><span class="sxs-lookup"><span data-stu-id="deb37-138">Tasks Connections and Groups</span></span>  
 <span data-ttu-id="deb37-139">Se a tarefa contiver mais de uma tarefa, elas estarão conectadas e sequenciadas no fluxo de controle por restrições de precedência.</span><span class="sxs-lookup"><span data-stu-id="deb37-139">If the task contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span> <span data-ttu-id="deb37-140">Para obter informações, consulte [Restrições de precedência](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="deb37-140">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="deb37-141">As tarefas podem ser agrupadas e executadas como uma única unidade de trabalho ou repetidas em um loop.</span><span class="sxs-lookup"><span data-stu-id="deb37-141">Tasks can be grouped together and performed as a single unit of work, or repeated in a loop.</span></span> <span data-ttu-id="deb37-142">Para obter mais informações, consulte [Contêiner Loop Foreach](foreach-loop-container.md), [Contêiner Loop For](for-loop-container.md)e [Contêiner Sequência](sequence-container.md).</span><span class="sxs-lookup"><span data-stu-id="deb37-142">For more information, see [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md), and [Sequence Container](sequence-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="deb37-143">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="deb37-143">Related Tasks</span></span>  
 [<span data-ttu-id="deb37-144">Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="deb37-144">Add or Delete a Task or a Container in a Control Flow</span></span>](add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
  
