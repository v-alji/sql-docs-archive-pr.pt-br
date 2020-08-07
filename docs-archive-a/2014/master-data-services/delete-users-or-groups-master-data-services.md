---
title: Excluir usuários ou grupos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting groups [Master Data Services]
- groups [Master Data Services], deleting
- users [Master Data Services], deleting
- deleting users [Master Data Services]
ms.assetid: 0bbf9d2c-b826-48bb-8aa9-9905db6e717f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: be302bc974994d0f4f17a8e61244065c76fa93ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582492"
---
# <a name="delete-users-or-groups-master-data-services"></a><span data-ttu-id="a8408-102">Excluir usuários ou grupos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a8408-102">Delete Users or Groups (Master Data Services)</span></span>
  <span data-ttu-id="a8408-103">Exclua usuários ou grupos quando não desejar mais que eles acessem o [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8408-103">Delete users or groups when you no longer want them to access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="a8408-104">Observe o seguinte comportamento ao excluir usuários e grupos:</span><span class="sxs-lookup"><span data-stu-id="a8408-104">Note the following behavior when deleting users and groups:</span></span>  
  
-   <span data-ttu-id="a8408-105">Se você excluir um usuário que é membro de um grupo com acesso ao [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], ele ainda poderá acessar o [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] até que você o remova do Active Directory ou do grupo local.</span><span class="sxs-lookup"><span data-stu-id="a8408-105">If you delete a user who is a member of a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], then the user can still access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] until you remove the user from the Active Directory or local group.</span></span>  
  
-   <span data-ttu-id="a8408-106">Se você excluir um grupo, todos os usuários do grupo que acessaram o [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] serão exibidos na lista **Usuários** até que você os exclua.</span><span class="sxs-lookup"><span data-stu-id="a8408-106">If you delete a group, all users from the group who have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] are displayed in the **Users** list until you delete them.</span></span>  
  
-   <span data-ttu-id="a8408-107">As alterações na segurança não são propagadas no MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] durante 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="a8408-107">Changes to security are not propagated to the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] for 20 minutes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8408-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a8408-108">Prerequisites</span></span>  
 <span data-ttu-id="a8408-109">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="a8408-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="a8408-110">Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .</span><span class="sxs-lookup"><span data-stu-id="a8408-110">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="a8408-111">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="a8408-111">You must be a model administrator.</span></span> <span data-ttu-id="a8408-112">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a8408-112">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-users-or-groups"></a><span data-ttu-id="a8408-113">Para excluir usuários ou grupos</span><span class="sxs-lookup"><span data-stu-id="a8408-113">To delete users or groups</span></span>  
  
1.  <span data-ttu-id="a8408-114">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.</span><span class="sxs-lookup"><span data-stu-id="a8408-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="a8408-115">Para excluir um usuário, permaneça na página **Usuários** .</span><span class="sxs-lookup"><span data-stu-id="a8408-115">To delete a user, remain on the **Users** page.</span></span> <span data-ttu-id="a8408-116">Para excluir um grupo, na barra de menus, clique em **Gerenciar Grupos**.</span><span class="sxs-lookup"><span data-stu-id="a8408-116">To delete a group, from the menu bar, click **ManageGroups.**</span></span>  
  
3.  <span data-ttu-id="a8408-117">Na grade, selecione a linha correspondente ao usuário ou grupo que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="a8408-117">In the grid,select the row for the user or group that you want to delete.</span></span>  
  
4.  <span data-ttu-id="a8408-118">Clique em **Excluir usuário selecionado** ou **Excluir grupo selecionado**.</span><span class="sxs-lookup"><span data-stu-id="a8408-118">Click **Delete selected user** or **Delete selected group**.</span></span>  
  
5.  <span data-ttu-id="a8408-119">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8408-119">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8408-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8408-120">See Also</span></span>  
 [<span data-ttu-id="a8408-121">Segurança &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a8408-121">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  
