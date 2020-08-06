---
title: Tarefas e permissões | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], tasks
- role-based security [Reporting Services], permissions
- security [Reporting Services], tasks
- security [Reporting Services], permissions
- role-based security [Reporting Services], tasks
- predefined tasks [Reporting Services]
- tasks [Reporting Services]
ms.assetid: d7ff90b5-b976-4270-b9ad-9d7b801d8263
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01cbf00850c5dd57e7ca1575a1a0cb826c009714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684469"
---
# <a name="tasks-and-permissions"></a><span data-ttu-id="2c7f4-102">Tarefas e permissões</span><span class="sxs-lookup"><span data-stu-id="2c7f4-102">Tasks and Permissions</span></span>
  <span data-ttu-id="2c7f4-103">No [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], *tarefas* são ações que um usuário ou administrador podem executar.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], *tasks* are actions that a user or administrator can perform.</span></span> <span data-ttu-id="2c7f4-104">Tarefas são predefinidas.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-104">Tasks are predefined.</span></span> <span data-ttu-id="2c7f4-105">Não é possível criar tarefas personalizadas ou modificar aquelas fornecidas de programaticamente ou através de uma ferramenta.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-105">You cannot create custom tasks or modify the ones provided either programmatically or through a tool.</span></span> <span data-ttu-id="2c7f4-106">Há vinte e cinco tarefas no total.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-106">There are twenty-five tasks in all.</span></span> <span data-ttu-id="2c7f4-107">Essas tarefas incluem o conjunto inteiro de operações disponível em segurança com base em função.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-107">These tasks comprise the entire set of operations that are available in role-based security.</span></span> <span data-ttu-id="2c7f4-108">Alguns exemplos de tarefas são "Exibir relatórios", "Administrar relatórios", e "Administrar propriedades de servidor de relatório".</span><span class="sxs-lookup"><span data-stu-id="2c7f4-108">Some examples of tasks include "View reports," "Manage reports," and "Manage report server properties."</span></span>  
  
 <span data-ttu-id="2c7f4-109">Cada tarefa consiste em um conjunto de permissões, que também são predefinidas.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-109">Each task consists of a set of permissions, which are also predefined.</span></span> <span data-ttu-id="2c7f4-110">Por exemplo, a tarefa "Administrar pastas" contém permissões para criar e excluir pastas e exibir e atualizar propriedades de pasta.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-110">For example, the "Manage folders" task contains permissions to create and delete folders and view and update folder properties.</span></span> <span data-ttu-id="2c7f4-111">São documentadas permissões para cada tarefa para fornecer uma descrição mais exata de cada tarefa.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-111">Permissions for each task are documented to provide a more exact description of each task.</span></span> <span data-ttu-id="2c7f4-112">Não é possível interagir diretamente com permissões ou especificá-las em atribuições de função.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-112">It is not possible to interact with permissions directly or to specify them in role assignments.</span></span> <span data-ttu-id="2c7f4-113">São concedidas permissões aos usuários indiretamente através das tarefas incluídas em definições de função.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-113">Users are granted permissions indirectly through the tasks that are included in role definitions.</span></span>  
  
 <span data-ttu-id="2c7f4-114">Tarefas podem ser realizadas somente se fizerem parte de uma função incluída em uma atribuição de função.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-114">Tasks can be performed only if they are part of a role and that role is included in a role assignment.</span></span> <span data-ttu-id="2c7f4-115">Portanto, se a tarefa Exibir Modelos não estiver incluída em uma função, ou se essa função não estiver incluída em uma atribuição de função, os usuários não poderão exibir modelos de relatório.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-115">Thus, if the View Models task is not included in a role, or that role is not included in a role assignment, users cannot view report models.</span></span> <span data-ttu-id="2c7f4-116">O diagrama a seguir ilustra como as permissões são combinadas em tarefas e como tarefas são combinadas em funções que podem ser usadas para atribuições de função específicas.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-116">The following diagram shows how permissions are combined into tasks, and how tasks are combined into roles that can be used for specific role assignments.</span></span>  
  
 <span data-ttu-id="2c7f4-117">![Diagrama de permissões e tarefas](../media/report-securityobjects.gif "Diagrama de permissões e tarefas")</span><span class="sxs-lookup"><span data-stu-id="2c7f4-117">![Permissions and task diagram](../media/report-securityobjects.gif "Permissions and task diagram")</span></span>  
<span data-ttu-id="2c7f4-118">Diagrama de permissões e tarefas</span><span class="sxs-lookup"><span data-stu-id="2c7f4-118">Permissions and task diagram</span></span>  
  
## <a name="system-and-item-level-tasks"></a><span data-ttu-id="2c7f4-119">Tarefas de nível de item e sistema</span><span class="sxs-lookup"><span data-stu-id="2c7f4-119">System and Item Level Tasks</span></span>  
 <span data-ttu-id="2c7f4-120">As tarefas podem ser divididas em duas categorias: nível de sistema e nível de item.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-120">Tasks fall into two categories: system level and item level.</span></span> <span data-ttu-id="2c7f4-121">Uma função só pode incluir tarefas de uma única categoria.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-121">A role can include tasks only from a single category.</span></span> <span data-ttu-id="2c7f4-122">A tabela a seguir descreve cada categoria de tarefas.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-122">The following table describes each category of tasks.</span></span>  
  
|<span data-ttu-id="2c7f4-123">Categoria</span><span class="sxs-lookup"><span data-stu-id="2c7f4-123">Category</span></span>|<span data-ttu-id="2c7f4-124">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2c7f4-124">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="2c7f4-125">Tarefas em nível de item</span><span class="sxs-lookup"><span data-stu-id="2c7f4-125">Item-Level Tasks</span></span>](tasks-and-permissions-item-level-tasks.md)|<span data-ttu-id="2c7f4-126">Ações executadas em itens gerenciados por um servidor de relatório, como pastas, relatórios, modelos de relatório e recursos.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-126">Actions that are performed on items managed by a report server, such as folders, reports, report models, and resources.</span></span><br /><br /> <span data-ttu-id="2c7f4-127">Tarefas de nível de item entram no escopo do namespace da pasta de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-127">Item-level tasks are scoped to the report server folder namespace.</span></span> <span data-ttu-id="2c7f4-128">Todos os itens acessados pelas pastas em um servidor de relatório ou através de URL protegidos por atribuições de função que incluem tarefas de nível de item.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-128">All items that you access through the folders on a report server or through URL access are secured by role assignments that include item-level tasks.</span></span>|  
|[<span data-ttu-id="2c7f4-129">Tarefas em nível de sistema</span><span class="sxs-lookup"><span data-stu-id="2c7f4-129">System-Level Tasks</span></span>](tasks-and-permissions-system-level-tasks.md)|<span data-ttu-id="2c7f4-130">Ações executadas no nível de sistema, como tarefas de gerenciamento ou agendas compartilhadas que podem ser usadas com vários itens.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-130">Actions that are performed at the system level, such as managing jobs or shared schedules that can be used with many items.</span></span> <span data-ttu-id="2c7f4-131">Tarefas de nível de Sistema entram no escopo fora do namespace de pasta de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2c7f4-131">System-level tasks are scoped outside of the report server folder namespace.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c7f4-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c7f4-132">See Also</span></span>  
 <span data-ttu-id="2c7f4-133">[Definições de função](role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="2c7f4-133">[Role Definitions](role-definitions.md) </span></span>  
 <span data-ttu-id="2c7f4-134">[funções predefinidas](role-definitions-predefined-roles.md) </span><span class="sxs-lookup"><span data-stu-id="2c7f4-134">[Predefined Roles](role-definitions-predefined-roles.md) </span></span>  
 [<span data-ttu-id="2c7f4-135">Conceder permissões em um servidor de relatório no Modo Nativo</span><span class="sxs-lookup"><span data-stu-id="2c7f4-135">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
