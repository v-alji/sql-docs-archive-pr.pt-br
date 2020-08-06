---
title: Tarefas em nível do sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- system-level tasks [Reporting Services]
ms.assetid: 7023b388-40b2-4590-b227-115cf380a1e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98f9390664064cd293b80d094d65c903869bc709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684473"
---
# <a name="system-level-tasks"></a><span data-ttu-id="2ea03-102">Tarefas de nível de sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-102">System-Level Tasks</span></span>
  <span data-ttu-id="2ea03-103">Uma tarefa em nível do sistema é uma coleção de permissões relacionadas a operações que se aplicam ao site do servidor de relatório como um todo.</span><span class="sxs-lookup"><span data-stu-id="2ea03-103">A system-level task is a collection of permissions that relate to operations that apply to the report server site as a whole.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2ea03-104">também inclui tarefas em nível de item que se aplicam a itens específicos.</span><span class="sxs-lookup"><span data-stu-id="2ea03-104">also includes item-level tasks that apply to specific items.</span></span> <span data-ttu-id="2ea03-105">Para obter mais informações, consulte [Tarefas em nível de item](tasks-and-permissions-item-level-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="2ea03-105">For more information, see [Item-Level Tasks](tasks-and-permissions-item-level-tasks.md).</span></span> <span data-ttu-id="2ea03-106">Para obter mais informações sobre tarefas e permissões em geral, consulte [Tasks and Permissions](tasks-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2ea03-106">For more information about tasks and permissions in general, see [Tasks and Permissions](tasks-and-permissions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ea03-107">Se você estiver trabalhando programaticamente com essas tarefas, deve usar métodos ofereçam suporte a tarefas de nível de sistema.</span><span class="sxs-lookup"><span data-stu-id="2ea03-107">If you are working with these tasks programmatically, you must use methods that support system-level tasks.</span></span> <span data-ttu-id="2ea03-108">Para obter mais informações, consulte <xref:ReportService2010.ReportingService2010.ListTasks%2A> e <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ea03-108">For more information, see <xref:ReportService2010.ReportingService2010.ListTasks%2A> and <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span></span>  
  
## <a name="permissions-in-system-level-tasks"></a><span data-ttu-id="2ea03-109">Permissões em tarefas de nível de sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-109">Permissions in System-Level Tasks</span></span>  
 <span data-ttu-id="2ea03-110">A tabela a seguir identifica a coleção de permissões de cada tarefa de sistema.</span><span class="sxs-lookup"><span data-stu-id="2ea03-110">The following table identifies the collection of permissions for each system task.</span></span> <span data-ttu-id="2ea03-111">As permissões são listadas somente para fins informativos, para fornecer uma descrição mais precisa da funcionalidade disponível em cada tarefa.</span><span class="sxs-lookup"><span data-stu-id="2ea03-111">Permissions are listed for informational purposes only, to provide a more exact description of the functionality available through each task.</span></span>  
  
|<span data-ttu-id="2ea03-112">Tarefa</span><span class="sxs-lookup"><span data-stu-id="2ea03-112">Task</span></span>|<span data-ttu-id="2ea03-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="2ea03-113">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2ea03-114">Executar definições de relatório</span><span class="sxs-lookup"><span data-stu-id="2ea03-114">Execute report definitions</span></span>|<span data-ttu-id="2ea03-115">Executar Definições de Relatório (o nome da permissão e da tarefa são iguais)</span><span class="sxs-lookup"><span data-stu-id="2ea03-115">Execute Report Definitions (the permission and task name are the same)</span></span>|  
|<span data-ttu-id="2ea03-116">Gerar eventos</span><span class="sxs-lookup"><span data-stu-id="2ea03-116">Generate events</span></span>|<span data-ttu-id="2ea03-117">Gerar eventos</span><span class="sxs-lookup"><span data-stu-id="2ea03-117">Generate Events</span></span>|  
|<span data-ttu-id="2ea03-118">Gerenciar trabalhos</span><span class="sxs-lookup"><span data-stu-id="2ea03-118">Manage jobs</span></span>|<span data-ttu-id="2ea03-119">Ler Propriedades do Sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-119">Read System Properties</span></span><br /><br /> <span data-ttu-id="2ea03-120">Atualizar Propriedades do Sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-120">Update System Properties</span></span>|  
|<span data-ttu-id="2ea03-121">Gerenciar propriedades de servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="2ea03-121">Manage report server properties</span></span>|<span data-ttu-id="2ea03-122">Ler Propriedades do Sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-122">Read System Properties</span></span><br /><br /> <span data-ttu-id="2ea03-123">Atualizar Propriedades do Sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-123">Update System Properties</span></span>|  
|<span data-ttu-id="2ea03-124">Gerenciar funções</span><span class="sxs-lookup"><span data-stu-id="2ea03-124">Manage roles</span></span>|<span data-ttu-id="2ea03-125">Criar Funções</span><span class="sxs-lookup"><span data-stu-id="2ea03-125">Create Roles</span></span><br /><br /> <span data-ttu-id="2ea03-126">Excluir Funções</span><span class="sxs-lookup"><span data-stu-id="2ea03-126">Delete Roles</span></span><br /><br /> <span data-ttu-id="2ea03-127">Ler Propriedades de Função</span><span class="sxs-lookup"><span data-stu-id="2ea03-127">Read Role Properties</span></span><br /><br /> <span data-ttu-id="2ea03-128">Atualizar Propriedades de Função</span><span class="sxs-lookup"><span data-stu-id="2ea03-128">Update Role Properties</span></span>|  
|<span data-ttu-id="2ea03-129">Gerenciar agendas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="2ea03-129">Manage shared schedules</span></span>|<span data-ttu-id="2ea03-130">Criar Agendas</span><span class="sxs-lookup"><span data-stu-id="2ea03-130">Create Schedules</span></span>|  
|<span data-ttu-id="2ea03-131">Gerenciar segurança de servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="2ea03-131">Manage report server security</span></span>|<span data-ttu-id="2ea03-132">Ler Políticas de Segurança do Sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-132">Read System Security Policies</span></span><br /><br /> <span data-ttu-id="2ea03-133">Atualizar Políticas de Segurança do Sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-133">Update System Security Policies</span></span>|  
|<span data-ttu-id="2ea03-134">Exibir propriedades do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="2ea03-134">View report server properties</span></span>|<span data-ttu-id="2ea03-135">Ler Propriedades do Sistema</span><span class="sxs-lookup"><span data-stu-id="2ea03-135">Read System Properties</span></span>|  
|<span data-ttu-id="2ea03-136">Exibir agendas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="2ea03-136">View shared schedules</span></span>|<span data-ttu-id="2ea03-137">Ler Agendas</span><span class="sxs-lookup"><span data-stu-id="2ea03-137">Read Schedules</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ea03-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ea03-138">See Also</span></span>  
 [<span data-ttu-id="2ea03-139">Conceder permissões em um servidor de relatório no Modo Nativo</span><span class="sxs-lookup"><span data-stu-id="2ea03-139">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
