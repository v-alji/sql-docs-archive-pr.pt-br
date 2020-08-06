---
title: Sobrepondo permissões de usuário e grupo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services], resolving permissions
- permissions [Master Data Services], user and group overlaps
- groups [Master Data Services], resolving permissions
ms.assetid: 31c3cf7d-17d4-4474-b6a7-ffcb9fc45b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7044bf6260170cbc598719ec204ddb6f861f6301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680006"
---
# <a name="overlapping-user-and-group-permissions-master-data-services"></a><span data-ttu-id="d5d5b-102">Sobrepondo permissões de usuário e grupo (Serviços de Dados Mestre)</span><span class="sxs-lookup"><span data-stu-id="d5d5b-102">Overlapping User and Group Permissions (Master Data Services)</span></span>
  <span data-ttu-id="d5d5b-103">As permissões de um usuário são baseadas em:</span><span class="sxs-lookup"><span data-stu-id="d5d5b-103">A user's permissions are based on:</span></span>  
  
-   <span data-ttu-id="d5d5b-104">Permissões das associações a grupos.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-104">Permissions from group memberships.</span></span>  
  
-   <span data-ttu-id="d5d5b-105">Permissões atribuídas explicitamente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-105">Permissions assigned explicitly to the user.</span></span>  
  
 <span data-ttu-id="d5d5b-106">Se um usuário for um membro de vários grupos, e esses grupos tiverem acesso ao Master Data Manager, as seguinte regras se aplicarão:</span><span class="sxs-lookup"><span data-stu-id="d5d5b-106">If a user is a member of multiple groups, and those groups have access to Master Data Manager, the following rules apply:</span></span>  
  
-   <span data-ttu-id="d5d5b-107">**Negar** substitui todas as outras permissões.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-107">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="d5d5b-108">A **atualização** substitui **somente leitura**.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-108">**Update** overrides **Read-only**.</span></span>  
  
 <span data-ttu-id="d5d5b-109">Essas regras se aplicam às guias **Modelos** e **Membros da Hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="d5d5b-109">These rules apply to both the **Models** and **Hierarchy Members** tabs.</span></span> <span data-ttu-id="d5d5b-110">As permissões são resolvidas para cada guia e, em seguida, combinadas.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-110">Permissions are resolved for each tab and then combined.</span></span> <span data-ttu-id="d5d5b-111">Para obter mais informações, consulte [Como as permissões são determinadas &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d5d5b-111">For more information, see [How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5d5b-112">Você pode visualizar a resolução do usuário e do grupo sobrepondo permissões na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-112">You can view the resolution of user and group overlapping permissions in the user interface.</span></span> <span data-ttu-id="d5d5b-113">As guias **Modelos** e **Membros da Hierarquia** têm uma lista suspensa na qual é possível escolher **Efetivo** para exibir as permissões efetivas.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-113">Both the **Models** and **Hierarchy Members** tab have a drop-down list from which you can choose **Effective** to view effective permissions.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="d5d5b-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="d5d5b-114">Example 1</span></span>  
 <span data-ttu-id="d5d5b-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span><span class="sxs-lookup"><span data-stu-id="d5d5b-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span></span>  
  
 <span data-ttu-id="d5d5b-116">O usuário pertence ao Grupo 1 e ao Grupo 2.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-116">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="d5d5b-117">O usuário tem permissão **somente leitura** para a entidade produto.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-117">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="d5d5b-118">O Grupo 1 tem permissão **Atualizar** para a entidade Produto.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-118">Group 1 has **Update** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="d5d5b-119">O grupo 2 tem permissão **somente leitura** para a entidade produto.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-119">Group 2 has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="d5d5b-120">Resultado: a permissão efetiva do usuário é **Atualizar** para a entidade Produto.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-120">Result: The user's effective permission is **Update** to the Product entity.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="d5d5b-121">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="d5d5b-121">Example 2</span></span>  
 <span data-ttu-id="d5d5b-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span><span class="sxs-lookup"><span data-stu-id="d5d5b-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span></span>  
  
 <span data-ttu-id="d5d5b-123">O usuário pertence ao Grupo 1 e ao Grupo 2.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-123">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="d5d5b-124">O usuário tem permissão **somente leitura** para a entidade produto.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-124">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="d5d5b-125">O Grupo 1 tem permissão **Atualizar** para a entidade Produto.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-125">Group 1 has **Update** permission to Product entity.</span></span>  
  
 <span data-ttu-id="d5d5b-126">O Grupo 2 tem permissão **Negar** para a entidade Produto.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-126">Group 2 has **Deny** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="d5d5b-127">Resultado: a permissão efetiva do usuário é **Negar** para a entidade Produto.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-127">Result: The user's effective permission is **Deny** to the Product entity.</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="d5d5b-128">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="d5d5b-128">Example 3</span></span>  
 <span data-ttu-id="d5d5b-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span><span class="sxs-lookup"><span data-stu-id="d5d5b-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span></span>  
  
 <span data-ttu-id="d5d5b-130">O usuário pertence ao Grupo 1 e ao Grupo 2.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-130">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="d5d5b-131">O usuário permissão **Atualizar** para um grupo de membros em um nó de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-131">The user has **Update** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="d5d5b-132">O grupo 1 tem permissão **somente leitura** para um grupo de membros em um nó de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-132">Group 1 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="d5d5b-133">O grupo 2 tem permissão **somente leitura** para um grupo de membros em um nó de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-133">Group 2 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="d5d5b-134">Resultado: a permissão efetiva do usuário é **Atualizar** para os membros.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-134">Result: The user's effective permission is **Update** to the members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d5b-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5d5b-135">See Also</span></span>  
 <span data-ttu-id="d5d5b-136">[Como as permissões são determinadas &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d5d5b-136">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="d5d5b-137">Sobrepondo permissões de modelo e membro &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d5d5b-137">Overlapping Model and Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)  
  
  
