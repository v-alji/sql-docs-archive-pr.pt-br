---
title: Propriedades de Função de Usuário (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.userroleproperties.f1
ms.assetid: c8b22236-a8b1-4e15-b1ff-4e1909b602d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f79953abdf5e3d1cdb03de8c5feeb6b2de34ab7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680774"
---
# <a name="user-role-properties-management-studio"></a><span data-ttu-id="29e45-102">Propriedades de Função do Usuário (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="29e45-102">User Role Properties (Management Studio)</span></span>
  <span data-ttu-id="29e45-103">Use essa página para exibir quais tarefas são incluídas em uma definição de função de nível de item.</span><span class="sxs-lookup"><span data-stu-id="29e45-103">Use this page to view which tasks are included in an item-level role definition.</span></span> <span data-ttu-id="29e45-104">Essa página também pode ser usada para alterar a lista de tarefas ou modificar uma descrição de função.</span><span class="sxs-lookup"><span data-stu-id="29e45-104">You can also use this page to change the task list or modify a role description.</span></span>  
  
 <span data-ttu-id="29e45-105">Uma definição de função de nível de item é uma coleção nomeada de tarefas que os usuários executam referentes a um item específico (ou seja, uma pasta, um relatório, recurso ou fonte de dados compartilhada).</span><span class="sxs-lookup"><span data-stu-id="29e45-105">An item-level role definition is a named collection of tasks that users perform relative to a specific item (that is, a folder, report, resource, or shared data source).</span></span> <span data-ttu-id="29e45-106">Definições de função são atribuídas a um usuário ou grupo para criar uma atribuição de função no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="29e45-106">Role definitions are assigned to a user or group to create a role assignment in Report Manager.</span></span> <span data-ttu-id="29e45-107">As tarefas na definição de função descrevem o que o usuário ou grupo pode fazer.</span><span class="sxs-lookup"><span data-stu-id="29e45-107">The tasks in the role definition describe what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="29e45-108">inclui várias definições predefinidas de função de nível de item com as que você pode trabalhar.</span><span class="sxs-lookup"><span data-stu-id="29e45-108">includes a number of predefined item-level role definitions that you can work with.</span></span> <span data-ttu-id="29e45-109">Você pode modificar as definições de função alterando a lista de tarefas de cada um.</span><span class="sxs-lookup"><span data-stu-id="29e45-109">You can modify the role definitions by changing the task list of each one.</span></span> <span data-ttu-id="29e45-110">A edição de uma definição de função afeta todas as atribuições de função que incluem a definição da função.</span><span class="sxs-lookup"><span data-stu-id="29e45-110">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29e45-111">Atribuições de função de usuário só são usadas em um servidor de relatório que executa em modo nativo.</span><span class="sxs-lookup"><span data-stu-id="29e45-111">User role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="29e45-112">Se o servidor de relatório estiver configurado para integração do SharePoint, essa página exibirá informações somente leitura sobre as funções e o nível de permissão definidos no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29e45-112">If the report server is configured for SharePoint integration, this page displays read-only information about the roles and permission levels that are defined on the SharePoint site.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29e45-113">Opções</span><span class="sxs-lookup"><span data-stu-id="29e45-113">Options</span></span>  
 <span data-ttu-id="29e45-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="29e45-114">**Name**</span></span>  
 <span data-ttu-id="29e45-115">Especifica o nome da definição de função.</span><span class="sxs-lookup"><span data-stu-id="29e45-115">Specifies the name of the role definition.</span></span>  
  
 <span data-ttu-id="29e45-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="29e45-116">**Description**</span></span>  
 <span data-ttu-id="29e45-117">Exibe uma descrição da definição da função.</span><span class="sxs-lookup"><span data-stu-id="29e45-117">Shows a description of the role definition.</span></span> <span data-ttu-id="29e45-118">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], esta descrição só é visível nesta página.</span><span class="sxs-lookup"><span data-stu-id="29e45-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="29e45-119">No Gerenciador de Relatórios, essa descrição ajuda os usuários a decidir se a função deve ser usada em atribuição de função.</span><span class="sxs-lookup"><span data-stu-id="29e45-119">In Report Manager, this description helps users decide whether to use the role in a role assignment.</span></span>  
  
 <span data-ttu-id="29e45-120">**Tarefa**</span><span class="sxs-lookup"><span data-stu-id="29e45-120">**Task**</span></span>  
 <span data-ttu-id="29e45-121">Lista todas as tarefas de nível de item que podem ser selecionadas para essa definição de função.</span><span class="sxs-lookup"><span data-stu-id="29e45-121">Lists all item-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="29e45-122">Você pode adicionar ou remover itens da lista de tarefas predefinidas para definir como os usuários acessam um determinado item com essa função.</span><span class="sxs-lookup"><span data-stu-id="29e45-122">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="29e45-123">Você não pode criar tarefas novas nem modificar tarefas existentes.</span><span class="sxs-lookup"><span data-stu-id="29e45-123">You cannot create new tasks, and you cannot modify existing tasks.</span></span> <span data-ttu-id="29e45-124">A lista de tarefas de uma definição de função só aparece no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29e45-124">The task list of a role definition appears only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="29e45-125">**Descrição da tarefa**</span><span class="sxs-lookup"><span data-stu-id="29e45-125">**Task Description**</span></span>  
 <span data-ttu-id="29e45-126">Fornece informações sobre cada tarefa.</span><span class="sxs-lookup"><span data-stu-id="29e45-126">Provides information about each task.</span></span> <span data-ttu-id="29e45-127">Você não pode modificar descrições de tarefa.</span><span class="sxs-lookup"><span data-stu-id="29e45-127">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e45-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29e45-128">See Also</span></span>  
 <span data-ttu-id="29e45-129">[Tarefas em nível de item](../security/tasks-and-permissions-item-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="29e45-129">[Item-Level Tasks](../security/tasks-and-permissions-item-level-tasks.md) </span></span>  
 <span data-ttu-id="29e45-130">[Definições de função](../security/role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="29e45-130">[Role Definitions](../security/role-definitions.md) </span></span>  
 <span data-ttu-id="29e45-131">[Servidor de Relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="29e45-131">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="29e45-132">[Tarefas e permissões](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="29e45-132">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="29e45-133">Funções predefinidas</span><span class="sxs-lookup"><span data-stu-id="29e45-133">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
