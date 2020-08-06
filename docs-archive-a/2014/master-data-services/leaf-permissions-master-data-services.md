---
title: Permissões de folha (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], permissions
- members [Master Data Services], leaf member permissions
- permissions [Master Data Services], leaf members
- leaf members [Master Data Services], attribute permissions
- attributes [Master Data Services], leaf member attribute permissions
ms.assetid: bde16e8c-bcd4-4041-8130-55c5450e5f72
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 794e1d138b91e896b8df16765ae8984c6e60aca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684241"
---
# <a name="leaf-permissions-master-data-services"></a><span data-ttu-id="9a1fd-102">Permissões de folha (Serviços de Dados Mestre)</span><span class="sxs-lookup"><span data-stu-id="9a1fd-102">Leaf Permissions (Master Data Services)</span></span>
  <span data-ttu-id="9a1fd-103">Permissões de folha se aplicam aos valores de atributos para todos os membros folha de uma entidade.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-103">Leaf permissions apply to the attribute values for all leaf members of an entity.</span></span>  
  
 <span data-ttu-id="9a1fd-104">Para entidades sem hierarquias explícitas habilitadas, atribuir permissão a **Folha** é o mesmo que atribuir permissão à entidade.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-104">For entities without explicit hierarchies enabled, assigning permission to **Leaf** is the same as assigning permission to the entity.</span></span>  
  
 <span data-ttu-id="9a1fd-105">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="9a1fd-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="9a1fd-106">As permissões de folha aplicam-se apenas à área funcional **Gerenciador** da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="9a1fd-107">As permissões atribuídas aos atributos **Name** e **Code** não são impostas.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="9a1fd-108">Permissão</span><span class="sxs-lookup"><span data-stu-id="9a1fd-108">Permission</span></span>|<span data-ttu-id="9a1fd-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="9a1fd-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="9a1fd-110">**Somente leitura**</span><span class="sxs-lookup"><span data-stu-id="9a1fd-110">**Read-only**</span></span>|<span data-ttu-id="9a1fd-111">Os membros folha são exibidos, mas o usuário não pode adicionar, remover ou alterá-los.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-111">Leaf members are displayed but the user cannot add, remove, or change them.</span></span><br /><br /> <span data-ttu-id="9a1fd-112">Se existem membros consolidados, os nomes e os códigos são exibidos, mas o usuário não pode adicionar, remover ou alterá-los.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-112">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="9a1fd-113">**Atualização**</span><span class="sxs-lookup"><span data-stu-id="9a1fd-113">**Update**</span></span>|<span data-ttu-id="9a1fd-114">Os membros de folha são exibidos e o usuário pode adicionar, remover ou alterá-los.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-114">Leaf members are displayed and the user can add, remove, and change them.</span></span><br /><br /> <span data-ttu-id="9a1fd-115">Se existem membros consolidados, os nomes e os códigos são exibidos, mas o usuário não pode adicionar, remover ou alterá-los.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-115">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="9a1fd-116">**Deny**</span><span class="sxs-lookup"><span data-stu-id="9a1fd-116">**Deny**</span></span>|<span data-ttu-id="9a1fd-117">Os membros de folha da entidade não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-117">Leaf members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="9a1fd-118">Permissões de atributo</span><span class="sxs-lookup"><span data-stu-id="9a1fd-118">Attribute Permissions</span></span>  
 <span data-ttu-id="9a1fd-119">As permissões de atributo se aplicam aos valores de atributo da entidade específica.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-119">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="9a1fd-120">Os usuários apenas com permissões de atributo não podem adicionar ou remover membros.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-120">Users with attribute permissions only cannot add or remove members.</span></span>  
  
|<span data-ttu-id="9a1fd-121">Permissão</span><span class="sxs-lookup"><span data-stu-id="9a1fd-121">Permission</span></span>|<span data-ttu-id="9a1fd-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="9a1fd-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="9a1fd-123">**Somente leitura**</span><span class="sxs-lookup"><span data-stu-id="9a1fd-123">**Read-only**</span></span>|<span data-ttu-id="9a1fd-124">O atributo é exibido, mas o usuário não pode alterar valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-124">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="9a1fd-125">**Atualização**</span><span class="sxs-lookup"><span data-stu-id="9a1fd-125">**Update**</span></span>|<span data-ttu-id="9a1fd-126">O atributo é exibido e o usuário pode alterar valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-126">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="9a1fd-127">**Deny**</span><span class="sxs-lookup"><span data-stu-id="9a1fd-127">**Deny**</span></span>|<span data-ttu-id="9a1fd-128">O atributo não é exibido.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-128">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="9a1fd-129">Observação: você não pode negar acesso explicitamente para os atributos Name e Code.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-129">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="9a1fd-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9a1fd-130">Example</span></span>  
 <span data-ttu-id="9a1fd-131">Para a entidade Product, atribua a permissão **Atualizar** ao atributo Subcategory.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-131">For the Product entity, assign **Update** permission to Subcategory attribute.</span></span> <span data-ttu-id="9a1fd-132">Negue permissão a todos os demais atributos.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-132">Deny permission to all other attributes.</span></span>  
  
|<span data-ttu-id="9a1fd-133">Nome</span><span class="sxs-lookup"><span data-stu-id="9a1fd-133">Name</span></span>|<span data-ttu-id="9a1fd-134">Código</span><span class="sxs-lookup"><span data-stu-id="9a1fd-134">Code</span></span>|<span data-ttu-id="9a1fd-135">Subcategory (atualizar)</span><span class="sxs-lookup"><span data-stu-id="9a1fd-135">Subcategory (Update)</span></span>|  
|----------|----------|----------------------------|  
|<span data-ttu-id="9a1fd-136">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="9a1fd-136">Mountain-100</span></span>|<span data-ttu-id="9a1fd-137">BK-M101</span><span class="sxs-lookup"><span data-stu-id="9a1fd-137">BK-M101</span></span>|<span data-ttu-id="9a1fd-138">{5}Bicicletas de Mountain Bike</span><span class="sxs-lookup"><span data-stu-id="9a1fd-138">{5} Mountain Bikes</span></span>|  
|<span data-ttu-id="9a1fd-139">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="9a1fd-139">Mountain-100</span></span>|<span data-ttu-id="9a1fd-140">BK-M201</span><span class="sxs-lookup"><span data-stu-id="9a1fd-140">BK-M201</span></span>|<span data-ttu-id="9a1fd-141">{5}Bicicletas de Mountain Bike</span><span class="sxs-lookup"><span data-stu-id="9a1fd-141">{5} Mountain Bikes</span></span>|  
  
 <span data-ttu-id="9a1fd-142">No **Gerenciador**, você pode atualizar qualquer valor de atributo na coluna Subcategory.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-142">In **Explorer**, you can update any attribute value in the Subcategory column.</span></span> <span data-ttu-id="9a1fd-143">Se você não tiver permissão a um atributo, ele não será exibido.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-143">If you do not have permission to an attribute, the attribute is not displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a1fd-144">Nesse exemplo, Subcategory é um atributo baseado em domínio, baseado na entidade SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-144">In this example, Subcategory is a domain-based attribute, based on the SubcategoryList entity.</span></span> <span data-ttu-id="9a1fd-145">Você pode selecionar uma subcategoria diferente para Mountain-100, mas não pode adicionar nem excluir os membros da entidade SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="9a1fd-145">You can select a different subcategory for Mountain-100 but you cannot add members to or delete members from the SubcategoryList entity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1fd-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a1fd-146">See Also</span></span>  
 <span data-ttu-id="9a1fd-147">[Atribuir permissões de objeto de modelo &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a1fd-147">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9a1fd-148">[Permissões consolidadas &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a1fd-148">[Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9a1fd-149">[Permissões de objeto de modelo &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a1fd-149">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9a1fd-150">[Membros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a1fd-150">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="9a1fd-151">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a1fd-151">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
