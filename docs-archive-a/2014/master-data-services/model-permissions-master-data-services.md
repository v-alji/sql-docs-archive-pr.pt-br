---
title: Permissões de modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], permissions
- permissions [Master Data Services], models
ms.assetid: 210f440b-2cc1-4c49-94b1-3a97e2af7bc3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2846918b515bba16d12d48cd7058cf25863bf569
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574082"
---
# <a name="model-permissions-master-data-services"></a><span data-ttu-id="e5958-102">Permissões de modelo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e5958-102">Model Permissions (Master Data Services)</span></span>
  <span data-ttu-id="e5958-103">As permissões de modelo se aplicam a todas as entidades, hierarquias derivadas, hierarquias explícitas e coleções existentes dentro do modelo.</span><span class="sxs-lookup"><span data-stu-id="e5958-103">Model permissions apply to all entities, derived hierarchies, explicit hierarchies, and collections that exist within the model.</span></span> <span data-ttu-id="e5958-104">As permissões atribuídas ao modelo podem ser substituídas para qualquer objeto individual.</span><span class="sxs-lookup"><span data-stu-id="e5958-104">Permissions assigned to the model can be overridden for any individual object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5958-105">Se um usuário for administrador de modelo, o modelo será exibido em todas as áreas funcionais da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5958-105">If a user is a model administrator, the model is displayed in all functional areas of the user interface.</span></span> <span data-ttu-id="e5958-106">Caso contrário, o modelo será exibido apenas na área funcional **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="e5958-106">Otherwise, the model is displayed in the **Explorer** functional area only.</span></span> <span data-ttu-id="e5958-107">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e5958-107">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
|<span data-ttu-id="e5958-108">Permissão</span><span class="sxs-lookup"><span data-stu-id="e5958-108">Permission</span></span>|<span data-ttu-id="e5958-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5958-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="e5958-110">**Somente leitura**</span><span class="sxs-lookup"><span data-stu-id="e5958-110">**Read-only**</span></span>|<span data-ttu-id="e5958-111">No **Explorer**, o modelo é exibido, mas o usuário não pode adicionar ou remover membros e não pode atualizar valores de atributo, associações de hierarquia ou associações de coleção.</span><span class="sxs-lookup"><span data-stu-id="e5958-111">In **Explorer**, the model is displayed but the user cannot add or remove members, and cannot update attribute values, hierarchy memberships, or collection memberships.</span></span>|  
|<span data-ttu-id="e5958-112">**Atualização**</span><span class="sxs-lookup"><span data-stu-id="e5958-112">**Update**</span></span>|<span data-ttu-id="e5958-113">No **Explorer**, o modelo é exibido e o usuário pode adicionar e remover membros, pode atualizar valores de atributo, associações de hierarquia e associações de coleção.</span><span class="sxs-lookup"><span data-stu-id="e5958-113">In **Explorer**, the model is displayed and the user can add and remove members, can update attribute values, hierarchy memberships, and collection memberships.</span></span>|  
|<span data-ttu-id="e5958-114">**Deny**</span><span class="sxs-lookup"><span data-stu-id="e5958-114">**Deny**</span></span>|<span data-ttu-id="e5958-115">O modelo não é exibido.</span><span class="sxs-lookup"><span data-stu-id="e5958-115">The model is not displayed.</span></span>|  
  
 <span data-ttu-id="e5958-116">Quando você atribui permissão a um modelo, o usuário obtém acesso a todas as versões do modelo.</span><span class="sxs-lookup"><span data-stu-id="e5958-116">When you assign permission to a model, the user gets access to all versions of the model.</span></span> <span data-ttu-id="e5958-117">Não é possível atribuir permissão a uma versão individual.</span><span class="sxs-lookup"><span data-stu-id="e5958-117">You cannot assign permission to an individual version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5958-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5958-118">See Also</span></span>  
 <span data-ttu-id="e5958-119">[Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e5958-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="e5958-120">[Permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e5958-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="e5958-121">[Permissões de entidade &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e5958-121">[Entity Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="e5958-122">Permissões de coleção &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e5958-122">Collection Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collection-permissions-master-data-services.md)  
  
  
