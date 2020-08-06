---
title: Modificar ou excluir uma atribuição de função (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing role assignments
- roles [Reporting Services], assignments
- system roles [Reporting Services]
- modifying role assignments
- deleting role assignments
ms.assetid: 523bdd32-92cb-4b48-a3a9-d58b2385bde7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d67c5cdb7647d50008f72890e4ac3e3c7eed456e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680812"
---
# <a name="modify-or-delete-a-role-assignment-report-manager"></a><span data-ttu-id="75878-102">Modificar ou excluir uma atribuição de função (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="75878-102">Modify or Delete a Role Assignment (Report Manager)</span></span>
  <span data-ttu-id="75878-103">Uma atribuição de função mapeia uma conta de grupo ou usuário para uma definição de função predefinida que inclui as tarefas que podem ser executadas.</span><span class="sxs-lookup"><span data-stu-id="75878-103">A role assignment maps a group or user account to a predefined role definition that includes tasks that can be performed.</span></span> <span data-ttu-id="75878-104">Ela determina os tipos de operações que um usuário pode executar com relação a uma pasta, relatório, modelo ou outro tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="75878-104">It determines the types of operations that a user can perform relative to a folder, report, model, or other content type.</span></span> <span data-ttu-id="75878-105">Para criar, modificar ou excluir atribuições de função, use o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="75878-105">To create, modify, or delete role assignments, you use Report Manager.</span></span> <span data-ttu-id="75878-106">Após criar uma atribuição de função para um determinado usuário ou grupo, você pode modificá-la posteriormente selecionando uma função diferente.</span><span class="sxs-lookup"><span data-stu-id="75878-106">After you create a role assignment for a particular user or group, you can modify it later by selecting a different role.</span></span> <span data-ttu-id="75878-107">Para revogar permissões em um servidor de relatório, exclua uma atribuição de função desse servidor.</span><span class="sxs-lookup"><span data-stu-id="75878-107">If you want to revoke permissions to a report server, you can delete a role assignment from the report server.</span></span>  
  
 <span data-ttu-id="75878-108">Dependendo de seu objetivo, abordagens alternativas podem ser mais apropriadas.</span><span class="sxs-lookup"><span data-stu-id="75878-108">Depending on your objective, alternative approaches might be more appropriate.</span></span> <span data-ttu-id="75878-109">Os exemplos incluem a personalização ou a criação de uma nova definição de função ou a modificação da associação de uma conta de grupo no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75878-109">Examples include customizing or creating a new role definition, or modifying the membership of a group account in Active Directory.</span></span>  
  
 <span data-ttu-id="75878-110">Por exemplo, suponha que você tenha um grupo de usuários que precisa gerenciar todo o conteúdo, mas não deve ter o conjunto completo de permissões associadas ao Gerenciador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="75878-110">For example, suppose you have a group of users who need to fully manage their content, but should not have the full set of permissions associated with Content Manager.</span></span> <span data-ttu-id="75878-111">Nesse caso, você poderia criar uma nova definição de função chamada Gerenciador de Conteúdo do Departamento que inclui todas as tarefas do Gerenciador de Conteúdo, exceto **Definir políticas de segurança para itens**.</span><span class="sxs-lookup"><span data-stu-id="75878-111">In this case, you could create a new role definition called Department Content Manager that includes all of the tasks in Content Manager except **Set security policies for items**.</span></span>  
  
 <span data-ttu-id="75878-112">Similarmente, se você for um administrador de sistema ou rede e for mais fácil gerenciar as contas de grupo do Active Directory do que as atribuições de função do Gerenciador de Relatórios, reduza a sobrecarga do gerenciamento das atribuições de função criando uma única atribuição de função para uma conta de grupo e, em seguida, ajuste a associação do grupo quando os usuários não precisarem mais acessar os relatórios.</span><span class="sxs-lookup"><span data-stu-id="75878-112">Similarly, if you are a system or network administrator and it is easier for you to manage Active Directory group accounts than role assignments in Report Manager, you could reduce the overhead of managing role assignments by creating a single role assignment for a group account, and then adjust group membership when users no longer require access to reports.</span></span>  
  
 <span data-ttu-id="75878-113">Se você considerar a modificação ou a exclusão de uma atribuição de função como a melhor abordagem, verifique as atribuições de função de sistema e de item.</span><span class="sxs-lookup"><span data-stu-id="75878-113">If you determine that modifying or deleting a role assignment is the best approach, remember to check for both system role assignments and item role assignments.</span></span> <span data-ttu-id="75878-114">Cada tipo de atribuição de função é configurado em páginas diferentes do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="75878-114">Each type of role assignment is configured through different pages in Report Manager.</span></span>  
  
### <a name="to-modify-or-delete-a-system-role-assignment"></a><span data-ttu-id="75878-115">Para modificar ou excluir uma atribuição de função de sistema</span><span class="sxs-lookup"><span data-stu-id="75878-115">To modify or delete a system role assignment</span></span>  
  
1.  <span data-ttu-id="75878-116">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="75878-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="75878-117">Clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="75878-117">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="75878-118">Clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="75878-118">Click **Security**.</span></span> <span data-ttu-id="75878-119">Todas as atribuições de função do nível de sistema definidas atualmente para a implantação de servidor ou de expansão são listadas pelo nome de conta.</span><span class="sxs-lookup"><span data-stu-id="75878-119">All system-level role assignments currently defined for the server or scale-out deployment are listed by account name.</span></span>  
  
4.  <span data-ttu-id="75878-120">Localize a atribuição de função que deseja modificar ou excluir.</span><span class="sxs-lookup"><span data-stu-id="75878-120">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="75878-121">Para adicionar ou remover a função para um usuário ou grupo específico, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="75878-121">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="75878-122">Para excluir uma atribuição de função, marque a caixa de seleção próximo ao nome de usuário ou grupo e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="75878-122">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
### <a name="to-modify-or-delete-an-item-role-assignment"></a><span data-ttu-id="75878-123">Para modificar ou excluir uma atribuição de função de item</span><span class="sxs-lookup"><span data-stu-id="75878-123">To modify or delete an item role assignment</span></span>  
  
1.  <span data-ttu-id="75878-124">Inicie o **Gerenciador de Relatórios** e localize o item para o qual você deseja editar ou excluir uma atribuição de função.</span><span class="sxs-lookup"><span data-stu-id="75878-124">Start **Report Manager** and locate the item for which you want to edit or delete a role assignment.</span></span>  
  
2.  <span data-ttu-id="75878-125">Focalize o item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="75878-125">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="75878-126">No menu suspenso, clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="75878-126">In the drop-down menu, click **Security**.</span></span>  
  
4.  <span data-ttu-id="75878-127">Localize a atribuição de função que deseja modificar ou excluir.</span><span class="sxs-lookup"><span data-stu-id="75878-127">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="75878-128">Para adicionar ou remover a função para um usuário ou grupo específico, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="75878-128">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="75878-129">Para excluir uma atribuição de função, marque a caixa de seleção próximo ao nome de usuário ou grupo e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="75878-129">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75878-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="75878-130">See Also</span></span>  
 <span data-ttu-id="75878-131">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="75878-131">(create-and-manage-role-assignments.md)</span></span>   
 <span data-ttu-id="75878-132">[Atribuições de função](role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="75878-132">[Role Assignments](role-assignments.md) </span></span>  
 <span data-ttu-id="75878-133">[Página Configurações do site &#40;Report Manager&#41;](../site-settings-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="75878-133">[Site Settings Page &#40;Report Manager&#41;](../site-settings-page-report-manager.md) </span></span>  
 [<span data-ttu-id="75878-134">Atribuições de nova função do sistema: página Editar Atribuições de Função do Sistema &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="75878-134">New System Role Assignments: Edit System Role Assignments Page &#40;Report Manager&#41;</span></span>](../new-system-role-assignments-edit-system-role-assignments-page-report-manager.md)  
  
  
