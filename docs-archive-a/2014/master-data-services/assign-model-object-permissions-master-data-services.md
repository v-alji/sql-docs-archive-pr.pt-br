---
title: Atribuir permissões de objeto modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], assigning object permissions
- permissions [Master Data Services], assigning model object permissions
ms.assetid: 4b80148d-2318-415c-9479-28c240e48bcd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 92ac8ef3ac63b7128c4cbb7e9305ee6bd56ca010
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574767"
---
# <a name="assign-model-object-permissions-master-data-services"></a><span data-ttu-id="59a94-102">Atribuir permissões de objeto modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="59a94-102">Assign Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="59a94-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], atribua permissões a objetos modelo quando você precisar fornecer a um usuário ou grupo o acesso aos dados na área funcional **Explorer** do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], ou quando precisar tornar um usuário ou grupo um administrador.</span><span class="sxs-lookup"><span data-stu-id="59a94-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign permissions to model objects when you need to give a user or group access to data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], or when you need to make a user or group an administrator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59a94-104">Quando você atribui permissão a um modelo, a permissão a todos os outros modelos é negada implicitamente.</span><span class="sxs-lookup"><span data-stu-id="59a94-104">When you assign permission to a model, permission to all other models is implicitly denied.</span></span> <span data-ttu-id="59a94-105">Se você não atribuir permissões a objetos de modelo, o usuário ou grupo não poderá acessar nenhum dado no **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="59a94-105">If you do not assign model object permissions, the user or group cannot access any data in **Explorer**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="59a94-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="59a94-106">Prerequisites</span></span>  
 <span data-ttu-id="59a94-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="59a94-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="59a94-108">Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .</span><span class="sxs-lookup"><span data-stu-id="59a94-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="59a94-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="59a94-109">You must be a model administrator.</span></span> <span data-ttu-id="59a94-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="59a94-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-model-object-permissions"></a><span data-ttu-id="59a94-111">Para atribuir permissões de objeto de modelo</span><span class="sxs-lookup"><span data-stu-id="59a94-111">To assign model object permissions</span></span>  
  
1.  <span data-ttu-id="59a94-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.</span><span class="sxs-lookup"><span data-stu-id="59a94-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="59a94-113">Na página **Usuários** ou **Grupos** , selecione a linha do usuário ou grupo que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="59a94-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="59a94-114">Clique em **Editar usuário selecionado**.</span><span class="sxs-lookup"><span data-stu-id="59a94-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="59a94-115">Clique na guia **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="59a94-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="59a94-116">Opcionalmente, selecione um modelo na lista **Modelo** .</span><span class="sxs-lookup"><span data-stu-id="59a94-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="59a94-117">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="59a94-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="59a94-118">Expanda a árvore e clique no objeto de modelo ao qual deseja atribuir permissões.</span><span class="sxs-lookup"><span data-stu-id="59a94-118">Expand the tree, and click the model object you want to assign permissions to.</span></span>  
  
8.  <span data-ttu-id="59a94-119">No menu, selecione **somente leitura**, **Atualizar**ou **negar**.</span><span class="sxs-lookup"><span data-stu-id="59a94-119">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
9. <span data-ttu-id="59a94-120">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="59a94-120">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="59a94-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="59a94-121">Next Steps</span></span>  
  
-   <span data-ttu-id="59a94-122">(Opcional) [Atribuir permissões de membro de hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="59a94-122">(Optional) [Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a94-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="59a94-123">See Also</span></span>  
 <span data-ttu-id="59a94-124">[Excluir permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="59a94-124">[Delete Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="59a94-125">[Permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="59a94-125">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="59a94-126">Criar um administrador de modelo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="59a94-126">Create a Model Administrator &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-administrator-master-data-services.md)  
  
  
