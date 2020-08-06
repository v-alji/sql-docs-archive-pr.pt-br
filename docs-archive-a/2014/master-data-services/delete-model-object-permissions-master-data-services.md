---
title: Excluir permissões de objeto modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting model object permissions [Master Data Services]
- permissions [Master Data Services], deleting model object permissions
- models [Master Data Services], deleting object permissions
ms.assetid: 859c5952-f600-4940-8064-1afd13f7f6dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 98da869476e597d76a83b0b86cc9e6e4274a25e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680537"
---
# <a name="delete-model-object-permissions-master-data-services"></a><span data-ttu-id="83366-102">Excluir permissões de objeto modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="83366-102">Delete Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="83366-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua as permissões do objeto de modelo para remover as atribuições feitas.</span><span class="sxs-lookup"><span data-stu-id="83366-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83366-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="83366-104">Prerequisites</span></span>  
 <span data-ttu-id="83366-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="83366-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="83366-106">Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .</span><span class="sxs-lookup"><span data-stu-id="83366-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="83366-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="83366-107">You must be a model administrator.</span></span> <span data-ttu-id="83366-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="83366-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-model-object-permissions"></a><span data-ttu-id="83366-109">Para excluir permissões de objeto de modelo</span><span class="sxs-lookup"><span data-stu-id="83366-109">To delete model object permissions</span></span>  
  
1.  <span data-ttu-id="83366-110">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.</span><span class="sxs-lookup"><span data-stu-id="83366-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="83366-111">Na página **Usuários** ou **Grupos** , selecione a linha do usuário ou grupo que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="83366-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="83366-112">Clique em **Editar usuário selecionado**.</span><span class="sxs-lookup"><span data-stu-id="83366-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="83366-113">Clique na guia **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="83366-113">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="83366-114">Opcionalmente, selecione um modelo na lista **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="83366-114">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="83366-115">No painel **Resumo de permissões de modelo** , selecione a linha para a permissão que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="83366-115">In the **Model Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
7.  <span data-ttu-id="83366-116">Clique em **excluir permissão selecionada**.</span><span class="sxs-lookup"><span data-stu-id="83366-116">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="83366-117">Você não poderá remover uma permissão de um usuário se a permissão for herdada de um grupo.</span><span class="sxs-lookup"><span data-stu-id="83366-117">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="83366-118">Em vez disso, você deve remover a permissão do grupo.</span><span class="sxs-lookup"><span data-stu-id="83366-118">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83366-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83366-119">See Also</span></span>  
 <span data-ttu-id="83366-120">[Permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="83366-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="83366-121">Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="83366-121">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
  
