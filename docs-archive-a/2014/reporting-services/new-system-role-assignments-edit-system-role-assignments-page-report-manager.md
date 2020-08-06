---
title: 'Atribuições de nova função do sistema: página Editar atribuições de função do sistema (Report Manager) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 62a22ab9-1eb4-4ce5-8dd7-06b5ed2d9a2a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e04ec18b8ee27c5897156753c1e4f7991991eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570504"
---
# <a name="new-system-role-assignments-edit-system-role-assignments-page-report-manager"></a><span data-ttu-id="42d35-102">Atribuições de nova função do sistema: página Editar atribuições de função do sistema (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="42d35-102">New System Role Assignments: Edit System Role Assignments Page (Report Manager)</span></span>
  <span data-ttu-id="42d35-103">Use a página Atribuição de Nova Função do Sistema ou Editar Atribuições de Função do Sistema para definir a segurança do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="42d35-103">Use the New System Role Assignments or Edit System Role Assignments page to define security for the report server.</span></span> <span data-ttu-id="42d35-104">Toda a segurança é definida por atribuições de função que mapeiam usuários específicos ou grupos até as tarefas que eles podem executar.</span><span class="sxs-lookup"><span data-stu-id="42d35-104">All security is defined through role assignments that map specific users or groups to the tasks that they can perform.</span></span> <span data-ttu-id="42d35-105">A lista de tarefas é representada como uma definição de função que você seleciona ao fazer a atribuição da função.</span><span class="sxs-lookup"><span data-stu-id="42d35-105">The task list is represented as a role definition that you select when making the role assignment.</span></span>  
  
 <span data-ttu-id="42d35-106">No nível do sistema, as atribuições de função que você cria ou modifica se aplicam ao servidor de relatórios como um todo.</span><span class="sxs-lookup"><span data-stu-id="42d35-106">At the system level, the role assignments that you create or modify apply to the report server as a whole.</span></span> <span data-ttu-id="42d35-107">Por exemplo, a capacidade de criar agendas compartilhadas é especificada no nível do sistema porque agendas compartilhadas são usadas em todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="42d35-107">For example, the ability to create shared schedules is specified at the system level because shared schedules are used throughout the system.</span></span>  
  
 <span data-ttu-id="42d35-108">Por padrão, o Reporting Services fornece duas funções predefinidas de nível de sistema:</span><span class="sxs-lookup"><span data-stu-id="42d35-108">By default, Reporting Services provides two predefined system level roles:</span></span>  
  
-   <span data-ttu-id="42d35-109">A função Usuário do Sistema inclui tarefas que permitem aos usuários exibir as propriedades e as agendas compartilhadas do servidor de relatório, bem como executar definições de relatório, o que lhes permite exibir relatórios de clickthrough que foram publicados no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="42d35-109">System User includes tasks that allow users to view report server properties and shared schedules, and to execute report definitions, which allows users to view clickthrough reports that have been published to the report server.</span></span> <span data-ttu-id="42d35-110">A maioria dos usuários deve ter essa função atribuída.</span><span class="sxs-lookup"><span data-stu-id="42d35-110">Most users should be assigned to this role.</span></span>  
  
-   <span data-ttu-id="42d35-111">O Administrador de Sistema inclui tarefas para criar e gerenciar agendas compartilhadas, definir propriedades do servidor e criar atribuições de função de nível de sistema para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="42d35-111">System Administrator includes tasks for creating and managing shared schedules, setting server properties, and creating system-level role assignments for other users.</span></span> <span data-ttu-id="42d35-112">Poucos usuários necessitam de permissões nesse nível.</span><span class="sxs-lookup"><span data-stu-id="42d35-112">Few users require permissions at this level.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="42d35-113">Navegação</span><span class="sxs-lookup"><span data-stu-id="42d35-113">Navigation</span></span>  
 <span data-ttu-id="42d35-114">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="42d35-114">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-system-role-assignments-or-edit-system-role-assignments-page"></a><span data-ttu-id="42d35-115">Para abrir a página Atribuição de Nova Função do Sistema ou a página Editar Atribuições de Função do Sistema</span><span class="sxs-lookup"><span data-stu-id="42d35-115">To open the New System Role Assignments or Edit System Role Assignments page</span></span>  
  
1.  <span data-ttu-id="42d35-116">Abra o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="42d35-116">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="42d35-117">Na parte superior da página, no canto direito, clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="42d35-117">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="42d35-118">Esse procedimento abre a página Propriedades Gerais do site.</span><span class="sxs-lookup"><span data-stu-id="42d35-118">This opens the General properties page for the site.</span></span>  
  
3.  <span data-ttu-id="42d35-119">Selecione a guia **segurança** . Você deve ter permissões de Gerenciador de conteúdo e de administrador do sistema para acessar esta página.</span><span class="sxs-lookup"><span data-stu-id="42d35-119">Select the **Security** tab. You must have Content Manager and System Administrator permissions to access this page.</span></span>  
  
4.  <span data-ttu-id="42d35-120">Para criar uma atribuição de nova função, clique em **Atribuição de Nova Função** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="42d35-120">To create a new role assignment, click **New Role Assignment** in the toolbar.</span></span> <span data-ttu-id="42d35-121">Para editar uma atribuição de função existente, clique em **Editar** , ao lado de um grupo ou usuário na página de propriedades de Segurança.</span><span class="sxs-lookup"><span data-stu-id="42d35-121">To edit an existing role assignment, click **Edit** next to a group or user on the Security properties page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="42d35-122">Opções</span><span class="sxs-lookup"><span data-stu-id="42d35-122">Options</span></span>  
 <span data-ttu-id="42d35-123">**Grupo ou Usuário**</span><span class="sxs-lookup"><span data-stu-id="42d35-123">**Group or User**</span></span>  
 <span data-ttu-id="42d35-124">Digite o nome de uma conta de grupo ou usuário do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="42d35-124">Type the name of a group or user account in your domain.</span></span> <span data-ttu-id="42d35-125">Se o servidor de relatório estiver sendo executado em uma conta local, você deve especificar grupos ou usuários locais.</span><span class="sxs-lookup"><span data-stu-id="42d35-125">If the report server is running under a local account, you must specify local groups or users.</span></span> <span data-ttu-id="42d35-126">Se o servidor de relatório estiver sendo executado em uma conta de domínio, você deverá especificar grupos ou usuários de domínio.</span><span class="sxs-lookup"><span data-stu-id="42d35-126">If the report server is running under a domain account, you must specify domain groups or users.</span></span> <span data-ttu-id="42d35-127">Insira a conta neste formato: \<domain> \\<conta \> .</span><span class="sxs-lookup"><span data-stu-id="42d35-127">Enter the account in this format: \<domain>\\<account\>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42d35-128">Esta caixa só está disponível na página Atribuição de Nova Função.</span><span class="sxs-lookup"><span data-stu-id="42d35-128">This box is available only on the New Role Assignment page.</span></span>  
  
 <span data-ttu-id="42d35-129">**Funções**</span><span class="sxs-lookup"><span data-stu-id="42d35-129">**Roles**</span></span>  
 <span data-ttu-id="42d35-130">Fornece uma lista de funções no nível de sistema que você pode atribuir a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="42d35-130">Provides a list of system-level roles that you can assign to other users.</span></span> <span data-ttu-id="42d35-131">Você pode especificar várias funções para uma única atribuição de função.</span><span class="sxs-lookup"><span data-stu-id="42d35-131">You can specify multiple roles for a single role assignment.</span></span>  
  
 <span data-ttu-id="42d35-132">O Gerenciador de Relatórios não exibe as tarefas em cada função nem fornece um modo de adicionar ou modificar as tarefas.</span><span class="sxs-lookup"><span data-stu-id="42d35-132">Report Manager does not display the tasks in each role or provide a way to add or modify the tasks.</span></span> <span data-ttu-id="42d35-133">Você deve usar as funções como elas são definidas.</span><span class="sxs-lookup"><span data-stu-id="42d35-133">You must use the roles as they are defined.</span></span> <span data-ttu-id="42d35-134">Para criar, modificar ou excluir funções, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42d35-134">To create, modify, or delete roles, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="42d35-135">Para obter mais informações, consulte [Criar, excluir ou modificar uma função &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span><span class="sxs-lookup"><span data-stu-id="42d35-135">For more information, see [Create, Delete, or Modify a Role &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span></span>  
  
 <span data-ttu-id="42d35-136">Observe que se você estiver usando o [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] com Advanced Services, deve usar as funções padrão fornecidas.</span><span class="sxs-lookup"><span data-stu-id="42d35-136">Note that if you are using [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services, you must use the default roles that are provided.</span></span>  
  
 <span data-ttu-id="42d35-137">**Descrições**</span><span class="sxs-lookup"><span data-stu-id="42d35-137">**Descriptions**</span></span>  
 <span data-ttu-id="42d35-138">Exibe informações adicionais sobre a função.</span><span class="sxs-lookup"><span data-stu-id="42d35-138">Shows additional information about the role.</span></span> <span data-ttu-id="42d35-139">Para funções predefinidas como Usuário do Sistema ou Administrador do Sistema, a descrição resume as tarefas às quais cada função dá suporte.</span><span class="sxs-lookup"><span data-stu-id="42d35-139">For predefined roles such as System User or System Administrator, the description summarizes the tasks that each role supports.</span></span>  
  
 <span data-ttu-id="42d35-140">**Excluir atribuição de função**</span><span class="sxs-lookup"><span data-stu-id="42d35-140">**Delete Role Assignment**</span></span>  
 <span data-ttu-id="42d35-141">Clique para excluir uma atribuição de função existente de um usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="42d35-141">Click to delete an existing role assignment for a user or a group.</span></span> <span data-ttu-id="42d35-142">Não será possível excluir uma atribuição de função se ela for a única que resta (cada item deve ter pelo menos uma atribuição de função).</span><span class="sxs-lookup"><span data-stu-id="42d35-142">You cannot delete a role assignment if it is the only one left (each item must have a minimum of one role assignment).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42d35-143">Este botão só está disponível na página Editar Atribuição de Função.</span><span class="sxs-lookup"><span data-stu-id="42d35-143">This button is available only on the Edit Role Assignment page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d35-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42d35-144">See Also</span></span>  
 <span data-ttu-id="42d35-145">[Ajuda F1 Report Manager](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="42d35-145">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="42d35-146">[Atribuições de função](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="42d35-146">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="42d35-147">Definições de Funções</span><span class="sxs-lookup"><span data-stu-id="42d35-147">Role Definitions</span></span>](security/role-definitions.md)  
  
  
