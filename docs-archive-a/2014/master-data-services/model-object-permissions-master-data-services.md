---
title: Permissões de objeto de modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], model objects
- models [Master Data Services], object permissions
ms.assetid: fab6335b-4cae-47de-ae7c-6c4743e0680f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4cc64d753b680cfabc3707a29c6d9de631708c20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582490"
---
# <a name="model-object-permissions-master-data-services"></a><span data-ttu-id="3f6bb-102">Permissões de objeto de modelo (Serviços de Dados Mestre)</span><span class="sxs-lookup"><span data-stu-id="3f6bb-102">Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="3f6bb-103">As permissões do objeto de modelo são obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-103">Model object permissions are mandatory.</span></span> <span data-ttu-id="3f6bb-104">Elas determinam os atributos que um usuário pode acessar na área funcional **Explorer** da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-104">They determine the attributes a user can access in the **Explorer** functional area of the UI.</span></span>  
  
 <span data-ttu-id="3f6bb-105">Por exemplo, se você atribuir uma permissão **Atualizar** de usuário à entidade Produto, o usuário poderá atualizar todos os atributos dessa entidade.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-105">For example, if you assign a user **Update** permission to the Product entity, the user can update all of the attributes of the Product entity.</span></span> <span data-ttu-id="3f6bb-106">Se você atribuir a permissão **Atualizar** a um único atributo, o usuário só poderá atualizar esse atributo.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-106">If you assign **Update** permission to a single attribute, the user can update that attribute only.</span></span>  
  
 <span data-ttu-id="3f6bb-107">Para determinar a segurança atribuída em cada valor de atributo individual, permissões de objeto modelo são combinadas com permissões de membro de hierarquia, que determinam os membros que um usuário pode acessar.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-107">To determine security assigned on each individual attribute value, model object permissions are combined with hierarchy member permissions, which determine the members a user can access.</span></span>  
  
 <span data-ttu-id="3f6bb-108">Para conceder a um usuário acesso a uma área funcional diferente do **Explorer**, o usuário deve ser um administrador de modelo, que também envolve a atribuição de permissões de objeto de modelo.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-108">To give a user access to a functional area other than **Explorer**, the user must be a model administrator, which also involves assigning model object permissions.</span></span> <span data-ttu-id="3f6bb-109">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3f6bb-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
 <span data-ttu-id="3f6bb-110">As permissões de objeto de modelo são atribuídas na [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] interface do usuário, na área funcional **permissões de usuário e grupo** na guia **modelos** . Nessa guia, o modelo é representado como uma estrutura de árvore.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-110">Model object permissions are assigned in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), in the **User and Group Permissions** functional area on the **Models** tab. On this tab, the model is represented as a tree structure.</span></span> <span data-ttu-id="3f6bb-111">Quando você atribui uma permissão a um objeto na árvore, todos os objetos abaixo herdam a permissão.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-111">When you assign permission to an object in the tree, all objects below inherit that permission.</span></span> <span data-ttu-id="3f6bb-112">Você pode substituir essa herança atribuindo permissões aos objetos individuais.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-112">You can override that inheritance by assigning permission to individual objects.</span></span>  
  
 <span data-ttu-id="3f6bb-113">Você pode atribuir permissão **somente leitura**, **Atualizar**ou **negar** a objetos de modelo.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-113">You can assign **Read-only**, **Update**, or **Deny** permission to model objects.</span></span> <span data-ttu-id="3f6bb-114">Se você não atribuir nenhuma permissão na guia **Modelos** , o usuário não poderá exibir modelos nem dados no [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f6bb-114">If you do not assign any permissions on the **Models** tab, the user cannot view any models or data in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="3f6bb-115">Melhor prática</span><span class="sxs-lookup"><span data-stu-id="3f6bb-115">Best Practice</span></span>  
 <span data-ttu-id="3f6bb-116">Em geral, você deve atribuir a permissão **Atualizar** ao objeto de modelo e atribuir explicitamente permissão a objetos abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-116">In general, you should assign **Update** permission to the model object, and then explicitly assign permission to objects underneath.</span></span> <span data-ttu-id="3f6bb-117">Se você não atribuir permissão a objetos subjacentes, as permissões serão herdadas e o usuário será um administrador.</span><span class="sxs-lookup"><span data-stu-id="3f6bb-117">If you do not assign permission to objects underneath, the permissions are inherited and the user is an administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6bb-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3f6bb-118">See Also</span></span>  
 <span data-ttu-id="3f6bb-119">[Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3f6bb-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="3f6bb-120">[Permissões de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3f6bb-120">[Model Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="3f6bb-121">[Permissões de área funcional &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3f6bb-121">[Functional Area Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="3f6bb-122">[Permissões de membro de hierarquia &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3f6bb-122">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="3f6bb-123">Como as permissões são determinadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3f6bb-123">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
