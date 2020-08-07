---
title: Como as permissões são determinadas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], determining permissions
ms.assetid: 1dc0b43a-d023-4e7d-b027-8b1459fd058c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3ea3306b772224bc8602659c7e17e8dc1634f0d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575182"
---
# <a name="how-permissions-are-determined-master-data-services"></a><span data-ttu-id="1d05f-102">Como as permissões são determinadas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1d05f-102">How Permissions Are Determined (Master Data Services)</span></span>
  <span data-ttu-id="1d05f-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a maneira mais simples de configurar a segurança é atribuir permissões de objeto modelo a um grupo do qual o usuário é membro.</span><span class="sxs-lookup"><span data-stu-id="1d05f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], the simplest way to configure security is to assign model object permissions to a group that the user is a member of.</span></span>

 <span data-ttu-id="1d05f-104">A segurança se torna mais complexa quando:</span><span class="sxs-lookup"><span data-stu-id="1d05f-104">Security becomes more complex when:</span></span>

-   <span data-ttu-id="1d05f-105">As permissões de objeto modelo e de membro da hierarquia são atribuídas.</span><span class="sxs-lookup"><span data-stu-id="1d05f-105">Both model object and hierarchy member permissions are assigned.</span></span>

-   <span data-ttu-id="1d05f-106">O usuário pertence a grupos e a permissão é atribuída ao usuário e aos grupos.</span><span class="sxs-lookup"><span data-stu-id="1d05f-106">The user belongs to groups and permission is assigned to both the user and groups.</span></span>

-   <span data-ttu-id="1d05f-107">O usuário pertence a grupos e a permissão é atribuída a vários grupos.</span><span class="sxs-lookup"><span data-stu-id="1d05f-107">The user belongs to groups and permission is assigned to multiple groups.</span></span>

## <a name="permissions-assigned-to-a-single-group-or-user"></a><span data-ttu-id="1d05f-108">Permissões atribuídas a um único grupo ou usuário</span><span class="sxs-lookup"><span data-stu-id="1d05f-108">Permissions assigned to a single group or user</span></span>
 <span data-ttu-id="1d05f-109">Se você atribuir permissões a um único grupo ou usuário, as permissões serão determinadas com base no seguinte fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1d05f-109">If you assign permissions to a single group or user, permissions are determined based on the following workflow.</span></span>

 <span data-ttu-id="1d05f-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span><span class="sxs-lookup"><span data-stu-id="1d05f-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span></span>

### <a name="step-1-effective-attribute-permissions-are-determined"></a><span data-ttu-id="1d05f-111">Etapa 1: permissões de atributo efetivas são determinadas.</span><span class="sxs-lookup"><span data-stu-id="1d05f-111">Step 1: Effective attribute permissions are determined.</span></span>
 <span data-ttu-id="1d05f-112">A lista a seguir descreve como as permissões de atributo efetivas são determinadas:</span><span class="sxs-lookup"><span data-stu-id="1d05f-112">The following list describes how effective attribute permissions are determined:</span></span>

-   <span data-ttu-id="1d05f-113">As permissões atribuídas a objetos modelo determinam quais atributos um usuário pode acessar.</span><span class="sxs-lookup"><span data-stu-id="1d05f-113">Permissions assigned to model objects determine which attributes a user can access.</span></span>

-   <span data-ttu-id="1d05f-114">Todos os objetos modelo herdam automaticamente a permissão do objeto mais próximo em um nível alto da estrutura do modelo.</span><span class="sxs-lookup"><span data-stu-id="1d05f-114">All model objects automatically inherit permission from the closest object at a higher level in the model structure.</span></span>

-   <span data-ttu-id="1d05f-115">Qualquer objeto no mesmo nível da entidade é negado implicitamente.</span><span class="sxs-lookup"><span data-stu-id="1d05f-115">Any objects at the same level as the entity are implicitly denied.</span></span>

-   <span data-ttu-id="1d05f-116">Qualquer objeto em um nível mais alto recebe acesso de navegação.</span><span class="sxs-lookup"><span data-stu-id="1d05f-116">Any objects at a higher level are given navigational access.</span></span> <span data-ttu-id="1d05f-117">Para obter mais informações sobre acesso de navegação, consulte [acesso de navegação &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d05f-117">For more information about navigational access, see [Navigational Access &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span></span>

 <span data-ttu-id="1d05f-118">Neste exemplo, a permissão **somente leitura** é atribuída a uma entidade e essa permissão é herdada por seu atributo, que está em um nível inferior na estrutura do modelo.</span><span class="sxs-lookup"><span data-stu-id="1d05f-118">In this example, **Read-only** permission is assigned to an entity and that permission is inherited by its attribute, which is at a lower level in the model structure.</span></span> <span data-ttu-id="1d05f-119">O modelo fornece acesso de navegação a essa entidade e seu atributo.</span><span class="sxs-lookup"><span data-stu-id="1d05f-119">The model provides navigational access to this entity and its attribute.</span></span> <span data-ttu-id="1d05f-120">A outra entidade no modelo não tem nenhuma permissão explícita atribuída e não herda nenhuma permissão, portanto, é negada implicitamente.</span><span class="sxs-lookup"><span data-stu-id="1d05f-120">The other entity in the model has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="1d05f-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="1d05f-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>

### <a name="step-2-if-hierarchy-member-permissions-are-assigned-effective-member-permissions-are-determined"></a><span data-ttu-id="1d05f-122">Etapa 2: se permissões de membro de hierarquia forem atribuídas, as permissões de membro efetivas serão determinadas.</span><span class="sxs-lookup"><span data-stu-id="1d05f-122">Step 2: If hierarchy member permissions are assigned, effective member permissions are determined.</span></span>
 <span data-ttu-id="1d05f-123">A lista a seguir descreve como as permissões de membro da hierarquia efetivas são determinadas:</span><span class="sxs-lookup"><span data-stu-id="1d05f-123">The following list describes how effective hierarchy member permissions are determined:</span></span>

-   <span data-ttu-id="1d05f-124">As permissões atribuídas a nós da hierarquia determinam quais membros um usuário pode acessar.</span><span class="sxs-lookup"><span data-stu-id="1d05f-124">Permissions assigned to hierarchy nodes determine which members a user can access.</span></span>

-   <span data-ttu-id="1d05f-125">Todos os nós de uma hierarquia herdam automaticamente a permissão do objeto mais próximo em um nível alto da estrutura da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="1d05f-125">All nodes in a hierarchy automatically inherit permission from the closest object at a higher level in the hierarchy structure.</span></span>

-   <span data-ttu-id="1d05f-126">Qualquer nó no mesmo nível é negado implicitamente.</span><span class="sxs-lookup"><span data-stu-id="1d05f-126">Any nodes at the same level are implicitly denied.</span></span>

-   <span data-ttu-id="1d05f-127">Qualquer nó em níveis mais altos que não tenha permissões atribuídas é negado implicitamente.</span><span class="sxs-lookup"><span data-stu-id="1d05f-127">Any nodes at higher levels that do not have permissions assigned are implicitly denied.</span></span>

 <span data-ttu-id="1d05f-128">Neste exemplo, a permissão **somente leitura** é atribuída a um nó da hierarquia e essa permissão é herdada por um nó em um nível inferior na estrutura da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="1d05f-128">In this example, **Read-only** permission is assigned to one node of the hierarchy and that permission is inherited by a node at a lower level in the hierarchy structure.</span></span> <span data-ttu-id="1d05f-129">A raiz não tem nenhuma permissão atribuída, portanto é negada implicitamente.</span><span class="sxs-lookup"><span data-stu-id="1d05f-129">The root has no permission assigned, so it is implicitly denied.</span></span> <span data-ttu-id="1d05f-130">O outro nó na estrutura da hierarquia não tem nenhuma permissão explícita atribuída e não herda nenhuma permissão, portanto, é negado implicitamente.</span><span class="sxs-lookup"><span data-stu-id="1d05f-130">The other node in the hierarchy structure has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="1d05f-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="1d05f-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span></span>

### <a name="step-3-the-intersection-of-attribute-and-member-permissions-is-determined"></a><span data-ttu-id="1d05f-132">Etapa 3: a interseção de permissões de atributo e de membro é determinada.</span><span class="sxs-lookup"><span data-stu-id="1d05f-132">Step 3: The intersection of attribute and member permissions is determined.</span></span>
 <span data-ttu-id="1d05f-133">Se as permissões de atributo efetivas forem diferentes das permissões de membro efetivas, as permissões deverão ser determinadas para cada valor de atributo individual.</span><span class="sxs-lookup"><span data-stu-id="1d05f-133">If the effective attribute permissions are different than the effective member permissions, permissions must be determined for each individual attribute value.</span></span> <span data-ttu-id="1d05f-134">Para obter mais informações, consulte [Sobrepondo permissões de modelo e membro &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d05f-134">For more information, see [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span></span>

## <a name="permissions-assigned-to-multiple-groups"></a><span data-ttu-id="1d05f-135">Permissões atribuídas a vários grupos</span><span class="sxs-lookup"><span data-stu-id="1d05f-135">Permissions assigned to multiple groups</span></span>
 <span data-ttu-id="1d05f-136">Se um usuário pertencer a um ou mais grupos e as permissões forem atribuídas ao usuário e aos grupos, o fluxo de trabalho se tornará mais complexo.</span><span class="sxs-lookup"><span data-stu-id="1d05f-136">If a user belongs to one or more groups and permissions are assigned to both the user and the groups, the workflow becomes more complex.</span></span>

 <span data-ttu-id="1d05f-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span><span class="sxs-lookup"><span data-stu-id="1d05f-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span></span>

 <span data-ttu-id="1d05f-138">Nesse caso, a sobreposição das permissões do usuário e do grupo deve ser resolvida antes das permissões do objeto modelo e do membro da hierarquia poderem ser comparadas.</span><span class="sxs-lookup"><span data-stu-id="1d05f-138">In this case, overlapping user and group permissions must be resolved before model object and hierarchy member permissions can be compared.</span></span> <span data-ttu-id="1d05f-139">Para obter mais informações, consulte [Sobrepondo permissões de usuário e grupo &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d05f-139">For more information, see [Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d05f-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d05f-140">See Also</span></span>
 <span data-ttu-id="1d05f-141">A [sobreposição de permissões de usuário e de grupo &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [permissões de modelo e de membro sobrepostas &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="1d05f-141">[Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span></span>


