---
title: Excluir permissões de membro de hierarquia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting member permissions [Master Data Services]
- members [Master Data Services], deleting permissions
- permissions [Master Data Services], deleting member permissions
ms.assetid: 7f22d5e2-70c1-422c-99c2-e995a47d812a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8b6e7fbfc4379733d5cb809ce4d46d2c12d05a48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680538"
---
# <a name="delete-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="17cd3-102">Excluir permissões de membro de hierarquia (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="17cd3-102">Delete Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="17cd3-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua as permissões do objeto de modelo para remover as atribuições feitas.</span><span class="sxs-lookup"><span data-stu-id="17cd3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="17cd3-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="17cd3-104">Prerequisites</span></span>  
 <span data-ttu-id="17cd3-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="17cd3-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="17cd3-106">Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .</span><span class="sxs-lookup"><span data-stu-id="17cd3-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="17cd3-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="17cd3-107">You must be a model administrator.</span></span> <span data-ttu-id="17cd3-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="17cd3-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-hierarchy-member-permissions"></a><span data-ttu-id="17cd3-109">Para excluir permissões de membro de hierarquia</span><span class="sxs-lookup"><span data-stu-id="17cd3-109">To delete hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="17cd3-110">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.</span><span class="sxs-lookup"><span data-stu-id="17cd3-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="17cd3-111">Na página **Usuários** ou **Grupos** , selecione a linha do usuário ou grupo que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="17cd3-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="17cd3-112">Clique em **Editar usuário selecionado**.</span><span class="sxs-lookup"><span data-stu-id="17cd3-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="17cd3-113">Clique na guia **Membros da Hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="17cd3-113">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="17cd3-114">Na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="17cd3-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="17cd3-115">Na lista **Versão** , selecione uma versão.</span><span class="sxs-lookup"><span data-stu-id="17cd3-115">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="17cd3-116">No painel **Resumo de permissão de membro de hierarquia** , selecione a linha para a permissão que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="17cd3-116">In the **Hierarchy Member Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
8.  <span data-ttu-id="17cd3-117">Clique em **excluir permissão selecionada**.</span><span class="sxs-lookup"><span data-stu-id="17cd3-117">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="17cd3-118">Você não poderá remover uma permissão de um usuário se a permissão for herdada de um grupo.</span><span class="sxs-lookup"><span data-stu-id="17cd3-118">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="17cd3-119">Em vez disso, você deve remover a permissão do grupo.</span><span class="sxs-lookup"><span data-stu-id="17cd3-119">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17cd3-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="17cd3-120">See Also</span></span>  
 <span data-ttu-id="17cd3-121">[Permissões de membro de hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="17cd3-121">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="17cd3-122">Atribuir permissões de membro de hierarquia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="17cd3-122">Assign Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)  
  
  
