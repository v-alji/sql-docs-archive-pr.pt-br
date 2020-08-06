---
title: Propriedades de função do sistema (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.systemroleproperties.f1
ms.assetid: 0210fc2a-74fb-41dd-8e39-4830047ec417
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b37ebb1cb95d6628884d81156c9c1bc29bff86fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571262"
---
# <a name="system-role-properties-management-studio"></a><span data-ttu-id="b68a4-102">Propriedades de Função do Sistema (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b68a4-102">System Role Properties (Management Studio)</span></span>
  <span data-ttu-id="b68a4-103">Use a página Funções do Sistema para exibir as definições de funções do sistema atualmente definidas no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b68a4-103">Use the System Roles page to view the system role definitions that are currently defined for the report server.</span></span> <span data-ttu-id="b68a4-104">Uma definição de função do sistema contém uma coleção de tarefas nomeada executada com relação a todo o site e não com relação a um item individual.</span><span class="sxs-lookup"><span data-stu-id="b68a4-104">A system role definition contains a named collection of tasks that are performed relative to the entire site, instead of an individual item.</span></span> <span data-ttu-id="b68a4-105">Definições de função são atribuídas a um usuário ou a grupos para criar uma atribuição de função resultante.</span><span class="sxs-lookup"><span data-stu-id="b68a4-105">Role definitions are assigned to a user or groups to create a resulting role assignment.</span></span> <span data-ttu-id="b68a4-106">As tarefas na definição de função especificam o que o usuário ou grupo pode fazer.</span><span class="sxs-lookup"><span data-stu-id="b68a4-106">The tasks in the role definition specify what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="b68a4-107">tem duas definições de função do sistema predefinidas: **Administrador do Sistema** e **Usuário do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="b68a4-107">has two predefined system role definitions: **System Administrator** and **System User**.</span></span> <span data-ttu-id="b68a4-108">Você pode modificar essas definições de função alterando a lista de tarefas ou pode criar uma nova definição de função que ofereça suporte a diferentes combinações de tarefas.</span><span class="sxs-lookup"><span data-stu-id="b68a4-108">You can modify these role definitions by changing the task list, or you can create a new system role that supports a different combination of tasks.</span></span> <span data-ttu-id="b68a4-109">A edição de uma definição de função afeta todas as atribuições de função que incluem a definição da função.</span><span class="sxs-lookup"><span data-stu-id="b68a4-109">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b68a4-110">Atribuições de função do sistema só são usadas em um servidor de relatório executado no modo nativo.</span><span class="sxs-lookup"><span data-stu-id="b68a4-110">System role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="b68a4-111">Se o servidor de relatório for configurado para integração do SharePoint, essa página não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="b68a4-111">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b68a4-112">Opções</span><span class="sxs-lookup"><span data-stu-id="b68a4-112">Options</span></span>  
 <span data-ttu-id="b68a4-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b68a4-113">**Name**</span></span>  
 <span data-ttu-id="b68a4-114">Especifica o nome da definição de função do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b68a4-114">Specifies the name of the system role definition.</span></span>  
  
 <span data-ttu-id="b68a4-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b68a4-115">**Description**</span></span>  
 <span data-ttu-id="b68a4-116">Mostra uma descrição da definição da função no sistema.</span><span class="sxs-lookup"><span data-stu-id="b68a4-116">Shows a description of the system role definition.</span></span> <span data-ttu-id="b68a4-117">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], essa descrição só está visível nesta página.</span><span class="sxs-lookup"><span data-stu-id="b68a4-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="b68a4-118">Os usuários que exibirem esse item no Gerenciador de Relatórios poderão ver essa descrição ao navegar na hierarquia de pastas.</span><span class="sxs-lookup"><span data-stu-id="b68a4-118">Users who view this item through Report Manager may see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="b68a4-119">**Tarefa**</span><span class="sxs-lookup"><span data-stu-id="b68a4-119">**Task**</span></span>  
 <span data-ttu-id="b68a4-120">Lista todas as tarefas no nível de sistema que podem ser selecionadas para essa definição de função.</span><span class="sxs-lookup"><span data-stu-id="b68a4-120">Lists all system-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="b68a4-121">Você pode adicionar ou remover itens da lista de tarefas predefinidas para definir como os usuários acessam um determinado item com essa função.</span><span class="sxs-lookup"><span data-stu-id="b68a4-121">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="b68a4-122">Você não pode criar tarefas novas nem modificar tarefas existentes.</span><span class="sxs-lookup"><span data-stu-id="b68a4-122">You cannot create new tasks, and you cannot modify existing tasks.</span></span>  
  
 <span data-ttu-id="b68a4-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b68a4-123">**Description**</span></span>  
 <span data-ttu-id="b68a4-124">Fornece informações sobre cada tarefa.</span><span class="sxs-lookup"><span data-stu-id="b68a4-124">Provides information about each task.</span></span> <span data-ttu-id="b68a4-125">Você não pode modificar descrições de tarefa.</span><span class="sxs-lookup"><span data-stu-id="b68a4-125">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68a4-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b68a4-126">See Also</span></span>  
 <span data-ttu-id="b68a4-127">[Servidor de Relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b68a4-127">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="b68a4-128">[Tarefas em nível de sistema](../security/tasks-and-permissions-system-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b68a4-128">[System-Level Tasks](../security/tasks-and-permissions-system-level-tasks.md) </span></span>  
 <span data-ttu-id="b68a4-129">[Tarefas e permissões](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="b68a4-129">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="b68a4-130">Funções predefinidas</span><span class="sxs-lookup"><span data-stu-id="b68a4-130">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
