---
title: Criar, excluir ou modificar uma função (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- roles [Reporting Services], creating
- deleting roles
- removing roles
- roles [Reporting Services], definitions
- modifying roles
- roles [Reporting Services], deleting
- roles [Reporting Services], modifying
ms.assetid: 3d1d56e6-a283-44a7-8417-36cb4d2c74d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 543bddda88e41af39d3200df4728716d46b3ae8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683390"
---
# <a name="create-delete-or-modify-a-role-management-studio"></a><span data-ttu-id="b2bbc-102">Criar, excluir ou modificar uma função (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b2bbc-102">Create, Delete, or Modify a Role (Management Studio)</span></span>
  <span data-ttu-id="b2bbc-103">O Reporting Services fornece funções predefinidas que definem um nível de acesso a um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-103">Reporting Services provides predefined roles that define a level of access to a report server.</span></span> <span data-ttu-id="b2bbc-104">Cada usuário ou grupo que requer acesso ao servidor de relatório faz isso através de uma função que descreve as tarefas que podem ser executadas.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-104">Each user or group who requires access to report server does so through a role that describes the tasks that can be performed.</span></span> <span data-ttu-id="b2bbc-105">As funções são definidas para o servidor de relatório como um todo.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-105">Roles are defined for the report server as a whole.</span></span> <span data-ttu-id="b2bbc-106">Não é possível variar uma definição de função para partes específicas do servidor de relatório nem especificar que uma função seja usada de modo diferente dependendo das circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-106">You cannot vary a role definition for specific parts of the report server, or specify that a role be used differently depending on the circumstances.</span></span>  
  
 <span data-ttu-id="b2bbc-107">Para criar, modificar ou excluir funções, use o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2bbc-107">To create, modify, or delete roles, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b2bbc-108">Você só pode excluir funções que não são usadas.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-108">You can only delete roles that are not used.</span></span>  
  
 <span data-ttu-id="b2bbc-109">Para atribuir usuários e grupos às funções criadas, use o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-109">To assign users and groups to the roles that you create, use Report Manager.</span></span> <span data-ttu-id="b2bbc-110">Para obter mais informações, consulte [conceder acesso de usuário a um servidor de relatório &#40;Report Manager&#41;](grant-user-access-to-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2bbc-110">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](grant-user-access-to-a-report-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b2bbc-111">Se o servidor de relatório estiver configurado para o modo integrado do SharePoint e você estiver conectado ao site do SharePoint no qual o servidor de relatório está integrado, poderá exibir e modificar os níveis de permissão que controlam o acesso ao conteúdo e às operações do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-111">If the report server is configured for SharePoint integrated mode, and you connected to the SharePoint site that the report server is integrated with, you can view and modify the permission levels that control access to report server content and operations.</span></span>  
  
### <a name="to-create-a-role-definition"></a><span data-ttu-id="b2bbc-112">Para criar uma definição de função</span><span class="sxs-lookup"><span data-stu-id="b2bbc-112">To create a role definition</span></span>  
  
1.  <span data-ttu-id="b2bbc-113">No Pesquisador de Objetos, expanda um nó do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-113">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="b2bbc-114">Expanda a pasta Segurança.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-114">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="b2bbc-115">Se você estiver criando uma definição de função no nível do item, clique com o botão direito do mouse em **Funções**e aponte para **Nova Função**.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-115">If you are creating an item-level role definition, right-click **Roles**, and point to **New Role**.</span></span>  
  
     <span data-ttu-id="b2bbc-116">Se você estiver criando uma definição de função no nível do sistema, clique com o botão direito do mouse em **Funções do Sistema**e aponte para **Nova Função do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-116">Or, if you are creating a system-level role definition, right-click **System Roles**, and point to **New System Role**.</span></span>  
  
4.  <span data-ttu-id="b2bbc-117">Digite um nome exclusivo para a função.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-117">Type a unique name for the role.</span></span> <span data-ttu-id="b2bbc-118">Um nome deve conter pelo menos um caractere.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-118">A name must contain at least one character.</span></span> <span data-ttu-id="b2bbc-119">Ele também pode incluir espaços e alguns símbolos, mas não os caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="b2bbc-119">It can also include spaces and certain symbols, but not the characters ; ?</span></span> <span data-ttu-id="b2bbc-120">: \@ & = +, $/\* \< > | "ou/.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-120">: \@ & = + , $ / \* \< > | " or /.</span></span>  
  
5.  <span data-ttu-id="b2bbc-121">Como opção, digite uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-121">Optionally type a description.</span></span> <span data-ttu-id="b2bbc-122">No [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , essa descrição só é visível nesta página.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-122">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] this description is visible only on this page.</span></span> <span data-ttu-id="b2bbc-123">Os usuários que exibem esse item por meio do Gerenciador de Relatórios podem ver essa descrição nessa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-123">Users who view this item through Report Manager can see this description in that tool.</span></span>  
  
6.  <span data-ttu-id="b2bbc-124">Selecione as tarefas que os membros dessa função podem executar.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-124">Select the tasks that members of this role can perform.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-or-modify-a-role-definition"></a><span data-ttu-id="b2bbc-125">Para excluir ou modificar uma definição de função</span><span class="sxs-lookup"><span data-stu-id="b2bbc-125">To delete or modify a role definition</span></span>  
  
1.  <span data-ttu-id="b2bbc-126">No Pesquisador de Objetos, expanda um nó do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-126">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="b2bbc-127">Expanda a pasta Segurança.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-127">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="b2bbc-128">Para excluir ou modificar uma definição de função no nível do item, expanda a pasta Funções.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-128">To delete or modify an item-level role definition, expand the Roles folder.</span></span> <span data-ttu-id="b2bbc-129">Execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="b2bbc-129">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="b2bbc-130">Para excluir uma definição de função, clique com o botão direito do mouse no item e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-130">To delete a role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="b2bbc-131">A caixa de diálogo **Excluir Objeto** é exibida.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-131">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="b2bbc-132">Para modificar uma definição de função, clique com o botão direito do mouse no item e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-132">To modify a role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="b2bbc-133">A página Geral da caixa de diálogo **Propriedades de Função do Usuário** é exibida.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-133">The General page of the **User Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="b2bbc-134">Selecione as tarefas que os membros desta função podem executar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-134">Select the tasks that members of this role can perform, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="b2bbc-135">Para excluir ou modificar uma definição de função no nível do sistema, expanda a pasta **Funções do Sistema** .</span><span class="sxs-lookup"><span data-stu-id="b2bbc-135">To delete or modify a system-level role definition, expand the **System Roles** folder.</span></span> <span data-ttu-id="b2bbc-136">Execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="b2bbc-136">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="b2bbc-137">Para excluir uma definição de função do sistema, clique com o botão direito do mouse no item e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-137">To delete a system role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="b2bbc-138">A caixa de diálogo **Excluir Objeto** é exibida.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-138">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="b2bbc-139">Para modificar uma definição de função do sistema, clique com o botão direito do mouse no item e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-139">To modify a system role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="b2bbc-140">A página Geral da caixa de diálogo **Propriedades de Função do Sistema** é exibida.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-140">The General page of the **System Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="b2bbc-141">Selecione as tarefas que os membros desta função podem executar e clique em **OK** para aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="b2bbc-141">Select the tasks that members of this role can perform, and click **OK** to apply the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bbc-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2bbc-142">See Also</span></span>  
 <span data-ttu-id="b2bbc-143">[Conectar-se a um servidor de relatório no Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b2bbc-143">[Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="b2bbc-144">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="b2bbc-144">(create-and-manage-role-assignments.md)</span></span>   
 [<span data-ttu-id="b2bbc-145">Reporting Services no SQL Server Management Studio &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b2bbc-145">Reporting Services in SQL Server Management Studio &#40;SSRS&#41;</span></span>](../tools/reporting-services-in-sql-server-management-studio-ssrs.md)  
  
  
