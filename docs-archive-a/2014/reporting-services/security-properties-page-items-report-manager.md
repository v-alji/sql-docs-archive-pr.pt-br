---
title: Página Propriedades de segurança, itens (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 351b8503-354f-4b1b-a7ac-f1245d978da0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 297ae2ceefad89d64c59b5da25d51d541917c894
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572373"
---
# <a name="security-properties-page-items-report-manager"></a><span data-ttu-id="6586c-102">Página Propriedades de Segurança, Itens (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="6586c-102">Security Properties Page, Items (Report Manager)</span></span>
  <span data-ttu-id="6586c-103">Use a página Propriedades de Segurança para exibir ou modificar as definições de segurança que determinam acesso a pastas, relatórios, modelos, recursos e fontes de dados compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="6586c-103">Use the Security properties page to view or modify the security settings that determine access to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="6586c-104">Essa página está disponível para itens que você tem permissão para proteger.</span><span class="sxs-lookup"><span data-stu-id="6586c-104">This page is available for items that you have permission to secure.</span></span>  
  
 <span data-ttu-id="6586c-105">O acesso aos itens é definido por atribuições de função que especificam as tarefas que um grupo ou usuário podem executar.</span><span class="sxs-lookup"><span data-stu-id="6586c-105">Access to items is defined through role assignments that specify the tasks that a group or user can perform.</span></span> <span data-ttu-id="6586c-106">Uma atribuição de função consiste em um nome de usuário ou grupo e em uma ou mais definições de função que especificam uma coleção de tarefas.</span><span class="sxs-lookup"><span data-stu-id="6586c-106">A role assignment consists of one user or group name and one or more role definitions that specify a collection of tasks.</span></span>  
  
 <span data-ttu-id="6586c-107">As configurações de segurança são herdadas da pasta raiz até subpastas e itens dentro dessas pastas.</span><span class="sxs-lookup"><span data-stu-id="6586c-107">Security settings are inherited from the root folder down to subfolders and items within those folders.</span></span> <span data-ttu-id="6586c-108">A menos que você interrompa explicitamente a segurança herdada, subpastas e itens herdam o contexto de segurança de um item pai.</span><span class="sxs-lookup"><span data-stu-id="6586c-108">Unless you explicitly break inherited security, subfolders and items inherit the security context of a parent item.</span></span> <span data-ttu-id="6586c-109">Se você redefinir política de segurança para uma pasta no meio da hierarquia, todos os itens filhos, incluindo subpastas, assumirão as novas definições de segurança.</span><span class="sxs-lookup"><span data-stu-id="6586c-109">If you redefine a security policy for a folder in the middle of the hierarchy, all its child items, including subfolders, assume the new security settings.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="6586c-110">Navegação</span><span class="sxs-lookup"><span data-stu-id="6586c-110">Navigation</span></span>  
 <span data-ttu-id="6586c-111">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="6586c-111">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-security-page-for-an-item"></a><span data-ttu-id="6586c-112">Para abrir a página Segurança de um item</span><span class="sxs-lookup"><span data-stu-id="6586c-112">To open the Security page for an item</span></span>  
  
1.  <span data-ttu-id="6586c-113">Abra o Gerenciador de Relatórios e localize o item cujas configurações de segurança você deseja definir.</span><span class="sxs-lookup"><span data-stu-id="6586c-113">Open Report Manager, and locate the item for which you want to configure security settings.</span></span>  
  
2.  <span data-ttu-id="6586c-114">Focalize o item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="6586c-114">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="6586c-115">No menu suspenso, execute uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="6586c-115">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="6586c-116">Clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="6586c-116">Click **Security**.</span></span> <span data-ttu-id="6586c-117">Esse procedimento abre a página de propriedades de Segurança do item.</span><span class="sxs-lookup"><span data-stu-id="6586c-117">This opens the Security properties page for the item.</span></span>  
  
    -   <span data-ttu-id="6586c-118">Clique em **Gerenciar** para abrir a página Propriedades Gerais do item.</span><span class="sxs-lookup"><span data-stu-id="6586c-118">Click **Manage** to open the General properties page for the item.</span></span> <span data-ttu-id="6586c-119">Em seguida, selecione a guia **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="6586c-119">Then select the **Security** tab.</span></span>  
  
 <span data-ttu-id="6586c-120">**Editar Segurança de Item**</span><span class="sxs-lookup"><span data-stu-id="6586c-120">**Edit Item Security**</span></span>  
 <span data-ttu-id="6586c-121">Clique para alterar a maneira como a segurança é definida para o item atual.</span><span class="sxs-lookup"><span data-stu-id="6586c-121">Click to change how security is defined for the current item.</span></span> <span data-ttu-id="6586c-122">Se você estiver editando segurança para uma pasta, suas alterações se aplicarão ao conteúdo da pasta atual e de quaisquer subpastas.</span><span class="sxs-lookup"><span data-stu-id="6586c-122">If you are editing security for a folder, your changes apply to the contents of the current folder and any subfolders.</span></span>  
  
 <span data-ttu-id="6586c-123">Esse botão não está disponível para a pasta Base.</span><span class="sxs-lookup"><span data-stu-id="6586c-123">This button is not available for the Home folder.</span></span>  
  
 <span data-ttu-id="6586c-124">Os botões a seguir ficam disponíveis quando você edita segurança de item.</span><span class="sxs-lookup"><span data-stu-id="6586c-124">The following buttons become available when you edit item security.</span></span>  
  
 <span data-ttu-id="6586c-125">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="6586c-125">**Delete**</span></span>  
 <span data-ttu-id="6586c-126">Marque a caixa de seleção próximo ao grupo ou nome de usuário que você quer excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="6586c-126">Select the check box next to the group or user name that you want to delete and click **Delete**.</span></span> <span data-ttu-id="6586c-127">Você não pode excluir uma atribuição de função se ela for a única ou se for uma atribuição de função interna (por exemplo, "Built-in\Administrators") que define os parâmetros de segurança do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="6586c-127">You cannot delete a role assignment if it is the only one remaining, or if it is a built-in role assignment (for example, "Built-in\Administrators") that defines the security baseline for the report server.</span></span> <span data-ttu-id="6586c-128">A exclusão de uma atribuição de função não exclui uma conta de grupo ou usuário, nem as definições da função.</span><span class="sxs-lookup"><span data-stu-id="6586c-128">Deleting a role assignment does not delete a group or user account or role definitions.</span></span>  
  
 <span data-ttu-id="6586c-129">**Nova atribuição de função**</span><span class="sxs-lookup"><span data-stu-id="6586c-129">**New Role Assignment**</span></span>  
 <span data-ttu-id="6586c-130">Clique para abrir a página Atribuição de Nova Função que é usada para criar atribuições de função adicionais para o item atual.</span><span class="sxs-lookup"><span data-stu-id="6586c-130">Click to open the New Role Assignment page, which is used to create additional role assignments for the current item.</span></span> <span data-ttu-id="6586c-131">Para obter mais informações, consulte a [página atribuição de nova função: editar atribuição de função &#40;Report Manager&#41;](../../2014/reporting-services/new-role-assignment-edit-role-assignment-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6586c-131">For more information, see [New Role Assignment: Edit Role Assignment Page &#40;Report Manager&#41;](../../2014/reporting-services/new-role-assignment-edit-role-assignment-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="6586c-132">**Reverter em Segurança Pai**</span><span class="sxs-lookup"><span data-stu-id="6586c-132">**Revert to Parent Security**</span></span>  
 <span data-ttu-id="6586c-133">Clique para redefinir as configurações de segurança às da pasta pai imediata.</span><span class="sxs-lookup"><span data-stu-id="6586c-133">Click to reset the security settings to that of the immediate parent folder.</span></span> <span data-ttu-id="6586c-134">Se a segurança não puder ser quebrada na hierarquia de pastas do servidor de relatórios, as configurações de segurança na pasta de alto nível, Base, serão usadas.</span><span class="sxs-lookup"><span data-stu-id="6586c-134">If inheritance is unbroken throughout the report server folder hierarchy, the security settings of the top-level folder, Home, are used.</span></span>  
  
 <span data-ttu-id="6586c-135">**Grupo ou Usuário**</span><span class="sxs-lookup"><span data-stu-id="6586c-135">**Group or User**</span></span>  
 <span data-ttu-id="6586c-136">Lista os grupos e usuários que fazem parte de uma atribuição de função existente para o item atual.</span><span class="sxs-lookup"><span data-stu-id="6586c-136">Lists the groups and users that are part of an existing role assignment for the current item.</span></span> <span data-ttu-id="6586c-137">Atribuições de função existentes para a pasta atual são definidas para os grupos e usuários que aparecem nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="6586c-137">Existing role assignments for the current folder are defined for the groups and users that appear in this column.</span></span> <span data-ttu-id="6586c-138">Você pode clicar em um grupo ou nome de usuário para exibir ou editar detalhes da atribuição de função.</span><span class="sxs-lookup"><span data-stu-id="6586c-138">You can click a group or user name to view or edit role assignment details.</span></span>  
  
 <span data-ttu-id="6586c-139">**Funções**</span><span class="sxs-lookup"><span data-stu-id="6586c-139">**Roles**</span></span>  
 <span data-ttu-id="6586c-140">Lista uma ou mais definições de função que fazem parte de uma atribuição de função existente.</span><span class="sxs-lookup"><span data-stu-id="6586c-140">Lists one or more role definitions that are part of an existing role assignment.</span></span> <span data-ttu-id="6586c-141">Se várias funções forem atribuídas a um grupo ou conta de usuário, aquele grupo de usuários pode desempenhar todas as tarefas que pertencem àquelas funções.</span><span class="sxs-lookup"><span data-stu-id="6586c-141">If multiple roles are assigned to a group or user account, that group or user can perform all tasks that belong to those roles.</span></span> <span data-ttu-id="6586c-142">Para exibir as tarefas associadas a uma função, use o SQL Server Management Studio para exibir as tarefas de cada definição de função.</span><span class="sxs-lookup"><span data-stu-id="6586c-142">To view the tasks that are associated with a role, use SQL Server Management Studio to view the tasks in each role definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6586c-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6586c-143">See Also</span></span>  
 <span data-ttu-id="6586c-144">[Ajuda F1 Report Manager](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="6586c-144">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="6586c-145">[Funções predefinidas](security/role-definitions-predefined-roles.md) </span><span class="sxs-lookup"><span data-stu-id="6586c-145">[Predefined Roles](security/role-definitions-predefined-roles.md) </span></span>  
 <span data-ttu-id="6586c-146">[Concedendo permissões em um servidor de relatório no modo nativo](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="6586c-146">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="6586c-147">[Atribuições de função](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="6586c-147">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="6586c-148">Definições de Funções</span><span class="sxs-lookup"><span data-stu-id="6586c-148">Role Definitions</span></span>](security/role-definitions.md)  
  
  
