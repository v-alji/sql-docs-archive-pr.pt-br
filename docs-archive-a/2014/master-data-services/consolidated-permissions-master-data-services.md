---
title: Permissões consolidadas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], consolidated member attribute permissions
- consolidated members [Master Data Services], attribute permissions
- permissions [Master Data Services], consolidated members
- members [Master Data Services], consolidated member permissions
ms.assetid: 084055a3-5fd3-43f3-b620-ac6afab42a3d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4c93e74acc84d6e742139263bedc011c4028efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584185"
---
# <a name="consolidated-permissions-master-data-services"></a><span data-ttu-id="46815-102">Permissões consolidadas (Serviços de Dados Mestre)</span><span class="sxs-lookup"><span data-stu-id="46815-102">Consolidated Permissions (Master Data Services)</span></span>
  <span data-ttu-id="46815-103">Permissões consolidadas se aplicam aos valores de atributos para todos os membros consolidados de uma entidade.</span><span class="sxs-lookup"><span data-stu-id="46815-103">Consolidated permissions apply to the attribute values for all consolidated members of an entity.</span></span>  
  
 <span data-ttu-id="46815-104">As permissões consolidadas se aplicam apenas a entidades habilitadas para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="46815-104">Consolidated permissions apply only to entities that are enabled for explicit hierarchies and collections.</span></span>  
  
 <span data-ttu-id="46815-105">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="46815-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="46815-106">As permissões de folha aplicam-se apenas à área funcional **Gerenciador** da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="46815-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="46815-107">As permissões atribuídas aos atributos **Name** e **Code** não são impostas.</span><span class="sxs-lookup"><span data-stu-id="46815-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="46815-108">Permissão</span><span class="sxs-lookup"><span data-stu-id="46815-108">Permission</span></span>|<span data-ttu-id="46815-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="46815-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="46815-110">**Somente leitura**</span><span class="sxs-lookup"><span data-stu-id="46815-110">**Read-only**</span></span>|<span data-ttu-id="46815-111">Os membros consolidados são exibidos, mas o usuário não pode adicionar, remover ou alterá-los.</span><span class="sxs-lookup"><span data-stu-id="46815-111">Consolidated members are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="46815-112">**Atualização**</span><span class="sxs-lookup"><span data-stu-id="46815-112">**Update**</span></span>|<span data-ttu-id="46815-113">Os membros consolidados são exibidos e o usuário pode adicionar, remover ou alterá-los.</span><span class="sxs-lookup"><span data-stu-id="46815-113">Consolidated members are displayed and the user can add, remove, and change them.</span></span>|  
|<span data-ttu-id="46815-114">**Deny**</span><span class="sxs-lookup"><span data-stu-id="46815-114">**Deny**</span></span>|<span data-ttu-id="46815-115">Os membros consolidados da entidade não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="46815-115">Consolidated members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="46815-116">Permissões de atributo</span><span class="sxs-lookup"><span data-stu-id="46815-116">Attribute Permissions</span></span>  
 <span data-ttu-id="46815-117">As permissões de atributo se aplicam aos valores de atributo da entidade específica.</span><span class="sxs-lookup"><span data-stu-id="46815-117">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="46815-118">Os usuários com permissões somente de atributo não podem adicionar ou remover membros.</span><span class="sxs-lookup"><span data-stu-id="46815-118">Users with only attribute permissions cannot add or remove members.</span></span>  
  
|<span data-ttu-id="46815-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="46815-119">Permission</span></span>|<span data-ttu-id="46815-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="46815-120">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="46815-121">**Somente leitura**</span><span class="sxs-lookup"><span data-stu-id="46815-121">**Read-only**</span></span>|<span data-ttu-id="46815-122">O atributo é exibido, mas o usuário não pode alterar valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="46815-122">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="46815-123">**Atualização**</span><span class="sxs-lookup"><span data-stu-id="46815-123">**Update**</span></span>|<span data-ttu-id="46815-124">O atributo é exibido e o usuário pode alterar valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="46815-124">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="46815-125">**Deny**</span><span class="sxs-lookup"><span data-stu-id="46815-125">**Deny**</span></span>|<span data-ttu-id="46815-126">O atributo não é exibido.</span><span class="sxs-lookup"><span data-stu-id="46815-126">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="46815-127">Observação: você não pode negar acesso explicitamente para os atributos Name e Code.</span><span class="sxs-lookup"><span data-stu-id="46815-127">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46815-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46815-128">See Also</span></span>  
 <span data-ttu-id="46815-129">[Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="46815-129">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="46815-130">[Permissões de folha &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="46815-130">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="46815-131">[Permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="46815-131">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="46815-132">[Membros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="46815-132">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="46815-133">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="46815-133">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
