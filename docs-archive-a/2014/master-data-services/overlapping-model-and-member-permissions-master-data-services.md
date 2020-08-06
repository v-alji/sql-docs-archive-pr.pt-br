---
title: Sobrepondo permissões de modelo e membro (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], effective permissions
- permissions [Master Data Services], model and member overlaps
- members [Master Data Services], effective permissions
ms.assetid: 9fd7a555-43bf-4796-a8b6-1ca63a291216
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ec5f4019f25a777e4c70433bd9a7e72fca2277e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570086"
---
# <a name="overlapping-model-and-member-permissions-master-data-services"></a><span data-ttu-id="20594-102">Sobrepondo permissões de modelo e membro (Serviços de Dados Mestre)</span><span class="sxs-lookup"><span data-stu-id="20594-102">Overlapping Model and Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="20594-103">A permissão atribuída a um membro pode sobrepor a permissão atribuída a um objeto de modelo.</span><span class="sxs-lookup"><span data-stu-id="20594-103">Permission assigned to a member can overlap with permission assigned to a model object.</span></span> <span data-ttu-id="20594-104">Quando ocorrem sobreposições, a permissão mais restritiva tem efeito.</span><span class="sxs-lookup"><span data-stu-id="20594-104">When overlaps occur, the more restrictive permission takes effect.</span></span>  
  
 <span data-ttu-id="20594-105">Se um membro tiver uma permissão que seja diferente daquela correspondente ao objeto de modelo, as seguintes regras se aplicarão:</span><span class="sxs-lookup"><span data-stu-id="20594-105">If a member has permission that is different than its corresponding model object, the following rules apply:</span></span>  
  
-   <span data-ttu-id="20594-106">**Negar** substitui todas as outras permissões.</span><span class="sxs-lookup"><span data-stu-id="20594-106">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="20594-107">**Somente leitura** substitui a **atualização**.</span><span class="sxs-lookup"><span data-stu-id="20594-107">**Read-only** overrides **Update**.</span></span>  
  
 <span data-ttu-id="20594-108">A imagem a seguir mostra quais permissões entram em vigor em um valor de atributo individual quando as permissões de atributo são diferentes das permissões de membro.</span><span class="sxs-lookup"><span data-stu-id="20594-108">The following image shows which permissions take effect on an individual attribute value when attribute permissions are different than member permissions.</span></span>  
  
 <span data-ttu-id="20594-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span><span class="sxs-lookup"><span data-stu-id="20594-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="20594-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="20594-110">Example 1</span></span>  
 <span data-ttu-id="20594-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span><span class="sxs-lookup"><span data-stu-id="20594-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span></span>  
  
 <span data-ttu-id="20594-112">Na guia **Modelos** , a entidade Produto tem a permissão **Atualizar** atribuída.</span><span class="sxs-lookup"><span data-stu-id="20594-112">On the **Models** tab, the Product entity has **Update** permission assigned.</span></span> <span data-ttu-id="20594-113">Todos os atributos da entidade herdam essa permissão.</span><span class="sxs-lookup"><span data-stu-id="20594-113">All attributes in the entity inherit that permission.</span></span>  
  
 <span data-ttu-id="20594-114">Na guia **Membros da Hierarquia** , o nó da subcategoria Mountain Bikes em uma hierarquia derivada tem a permissão **Atualizar** atribuída.</span><span class="sxs-lookup"><span data-stu-id="20594-114">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="20594-115">Resultado: no **Explorer**, o usuário tem a permissão **Atualizar** para todos os valores do atributo para todos os membros do nó Mountain Bikes.</span><span class="sxs-lookup"><span data-stu-id="20594-115">Result: In **Explorer**, the user has **Update** permission to all attribute values for all members in the Mountain Bikes node.</span></span> <span data-ttu-id="20594-116">Todos os outros membros e atributos estão ocultados.</span><span class="sxs-lookup"><span data-stu-id="20594-116">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="20594-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span><span class="sxs-lookup"><span data-stu-id="20594-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="20594-118">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="20594-118">Example 2</span></span>  
 <span data-ttu-id="20594-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span><span class="sxs-lookup"><span data-stu-id="20594-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span></span>  
  
 <span data-ttu-id="20594-120">Na guia **Modelos** , o atributo Subcategory tem a permissão **Atualizar** atribuída.</span><span class="sxs-lookup"><span data-stu-id="20594-120">On the **Models** tab, the Subcategory attribute has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="20594-121">Na guia **membros da hierarquia** , o nó subcategoria de Mountain Bikes em uma hierarquia derivada é explicitamente atribuído à permissão **somente leitura** .</span><span class="sxs-lookup"><span data-stu-id="20594-121">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy is explicitly assigned **Read-only** permission.</span></span>  
  
 <span data-ttu-id="20594-122">Resultado: no **Explorer**, o usuário tem permissão **somente leitura** para os valores de atributo de subcategoria para os membros no nó Mountain Bikes.</span><span class="sxs-lookup"><span data-stu-id="20594-122">Result: In **Explorer**, the user has **Read-only** permission to the Subcategory attribute values for the members in the Mountain Bikes node.</span></span> <span data-ttu-id="20594-123">Todos os outros membros e atributos estão ocultados.</span><span class="sxs-lookup"><span data-stu-id="20594-123">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="20594-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="20594-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="20594-125">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="20594-125">Example 3</span></span>  
 <span data-ttu-id="20594-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span><span class="sxs-lookup"><span data-stu-id="20594-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span></span>  
  
 <span data-ttu-id="20594-127">Na guia **modelos** , o atributo subcategoria tem permissão **somente leitura** atribuída.</span><span class="sxs-lookup"><span data-stu-id="20594-127">On the **Models** tab, the Subcategory attribute has **Read-only** permission assigned.</span></span>  
  
 <span data-ttu-id="20594-128">Na guia **Membros da Hierarquia** , o nó da subcategoria Mountain Bikes em uma hierarquia derivada recebe explicitamente a permissão **Atualizar** .</span><span class="sxs-lookup"><span data-stu-id="20594-128">On the **Hierarchy Members** tab, the Mountain Bikes subcategory in a derived hierarchy is explicitly assigned **Update** permission.</span></span>  
  
 <span data-ttu-id="20594-129">Resultado: no **Explorer**, o usuário tem permissão **somente leitura** para os valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="20594-129">Result: In **Explorer**, the user has **Read-only** permission to the attribute values.</span></span> <span data-ttu-id="20594-130">Todos os outros membros e atributos estão ocultados.</span><span class="sxs-lookup"><span data-stu-id="20594-130">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="20594-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="20594-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20594-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="20594-132">See Also</span></span>  
 <span data-ttu-id="20594-133">[Como as permissões são determinadas &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="20594-133">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="20594-134">Sobrepondo permissões de usuário e grupo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="20594-134">Overlapping User and Group Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md)  
  
  
