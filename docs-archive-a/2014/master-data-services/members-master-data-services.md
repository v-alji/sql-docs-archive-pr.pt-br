---
title: Membros (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services]
- consolidated members [Master Data Services]
- consolidated members [Master Data Services], about consolidated members
- members [Master Data Services], about members
- leaf members [Master Data Services], about leaf members
- members [Master Data Services]
ms.assetid: 0fda32b9-677d-4ba2-bb28-f76f2383a30f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 89d2edb21b58575dffc21d9a6470171251889cc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680024"
---
# <a name="members-master-data-services"></a><span data-ttu-id="91348-102">Membros (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="91348-102">Members (Master Data Services)</span></span>
  <span data-ttu-id="91348-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], os membros são os dados mestres físicos.</span><span class="sxs-lookup"><span data-stu-id="91348-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], members are the physical master data.</span></span> <span data-ttu-id="91348-104">Por exemplo, um membro pode ser uma Road-150 bike em uma entidade Product ou um cliente específico em uma entidade Customer.</span><span class="sxs-lookup"><span data-stu-id="91348-104">For example, a member can be a Road-150 bike in a Product entity or a specific customer in a Customer entity.</span></span>

## <a name="how-members-relate-to-other-model-objects"></a><span data-ttu-id="91348-105">Como os membros se relacionam com outros objetos modelo</span><span class="sxs-lookup"><span data-stu-id="91348-105">How Members Relate to Other Model Objects</span></span>
 <span data-ttu-id="91348-106">Você pode considerar os membros como linhas em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="91348-106">You can think of members as rows in a table.</span></span> <span data-ttu-id="91348-107">Membros relacionados estão contidos em uma entidade e cada membro é definido por valores de atributos.</span><span class="sxs-lookup"><span data-stu-id="91348-107">Related members are contained in an entity, and each member is defined by attribute values.</span></span>

 <span data-ttu-id="91348-108">Neste exemplo, a tabela representa uma entidade, as linhas da tabela representam membros e as colunas representam atributos.</span><span class="sxs-lookup"><span data-stu-id="91348-108">In this example, the table represents an entity, the rows in the table represent members, and the columns in the table represent attributes.</span></span> <span data-ttu-id="91348-109">Cada célula representa um valor de atributo de um membro específico.</span><span class="sxs-lookup"><span data-stu-id="91348-109">Each cell represents an attribute value for a specific member.</span></span>

 <span data-ttu-id="91348-110">![Entidade de Master Data Services representada como tabela](../../2014/master-data-services/media/mds-conc-entity-table.gif "Entidade de Master Data Services representada como tabela")</span><span class="sxs-lookup"><span data-stu-id="91348-110">![Master Data Services Entity Represented as Table](../../2014/master-data-services/media/mds-conc-entity-table.gif "Master Data Services Entity Represented as Table")</span></span>

## <a name="member-types"></a><span data-ttu-id="91348-111">Tipos de membro</span><span class="sxs-lookup"><span data-stu-id="91348-111">Member Types</span></span>
 <span data-ttu-id="91348-112">Há três tipos de membros: membros folha, membros consolidados e membros de coleção.</span><span class="sxs-lookup"><span data-stu-id="91348-112">There are three types of members: leaf members, consolidated members, and collection members.</span></span>

 <span data-ttu-id="91348-113">Os membros folha são os membros padrão de uma entidade.</span><span class="sxs-lookup"><span data-stu-id="91348-113">Leaf members are the default members in an entity.</span></span>

-   <span data-ttu-id="91348-114">Em hierarquias derivadas, os membros folha são o único tipo de membro.</span><span class="sxs-lookup"><span data-stu-id="91348-114">In derived hierarchies, leaf members are the only type of member.</span></span> <span data-ttu-id="91348-115">Os membros folha de uma entidade são usados como pais dos membros folha de outra entidade.</span><span class="sxs-lookup"><span data-stu-id="91348-115">Leaf members from one entity are used as parents of leaf members from another entity.</span></span>

-   <span data-ttu-id="91348-116">Em hierarquias explícitas, os membros folha são o nível mais baixo e não podem ter filhos.</span><span class="sxs-lookup"><span data-stu-id="91348-116">In explicit hierarchies, leaf members are the lowest level and cannot have children.</span></span>

 <span data-ttu-id="91348-117">Os membros consolidados existem apenas quando hierarquias e coleções explícitas são habilitadas para a entidade.</span><span class="sxs-lookup"><span data-stu-id="91348-117">Consolidated members exist only when explicit hierarchies and collections are enabled for the entity.</span></span>

-   <span data-ttu-id="91348-118">Hierarquias derivadas não contêm membros consolidados.</span><span class="sxs-lookup"><span data-stu-id="91348-118">Derived hierarchies do not contain consolidated members.</span></span>

-   <span data-ttu-id="91348-119">Em hierarquias explícitas, membros consolidados podem ser os pais de outros membros dentro da hierarquia ou podem ser filhos.</span><span class="sxs-lookup"><span data-stu-id="91348-119">In explicit hierarchies, consolidated members can be parents of other members within the hierarchy, or they can be children.</span></span>

## <a name="use-hierarchies-and-collections-to-organize-members"></a><span data-ttu-id="91348-120">Usar hierarquias e coleções para organizar os membros</span><span class="sxs-lookup"><span data-stu-id="91348-120">Use Hierarchies and Collections to Organize Members</span></span>
 <span data-ttu-id="91348-121">As hierarquias e as coleções podem ser usadas para agrupar membros para relatório ou análise.</span><span class="sxs-lookup"><span data-stu-id="91348-121">Hierarchies and collections can be used to group members for reporting or analysis.</span></span> <span data-ttu-id="91348-122">Para obter mais informações, consulte [Hierarquias &#40;Master Data Services&#41;](hierarchies-master-data-services.md) e [Coleções &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="91348-122">For more information, see [Hierarchies &#40;Master Data Services&#41;](hierarchies-master-data-services.md) and [Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span></span>

## <a name="member-example"></a><span data-ttu-id="91348-123">Exemplo de membro</span><span class="sxs-lookup"><span data-stu-id="91348-123">Member Example</span></span>
 <span data-ttu-id="91348-124">No exemplo a seguir, cada membro é composto de um valor dos atributos Name, Code, Subcategory, StandardCost, ListPrice e FilePhoto.</span><span class="sxs-lookup"><span data-stu-id="91348-124">In the following example, each member is made up of a Name, Code, Subcategory, StandardCost, ListPrice, and FilePhoto attribute value.</span></span>

 <span data-ttu-id="91348-125">![Tabela da entidade de produto bicicleta](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Tabela da entidade de produto bicicleta")</span><span class="sxs-lookup"><span data-stu-id="91348-125">![Bike Product Entity Table](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Bike Product Entity Table")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="91348-126">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="91348-126">Related Tasks</span></span>

|<span data-ttu-id="91348-127">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="91348-127">Task Description</span></span>|<span data-ttu-id="91348-128">Tópico</span><span class="sxs-lookup"><span data-stu-id="91348-128">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="91348-129">Criar um novo membro folha.</span><span class="sxs-lookup"><span data-stu-id="91348-129">Create a new leaf member.</span></span>|[<span data-ttu-id="91348-130">Criar um membro folha &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-130">Create a Leaf Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)|
|<span data-ttu-id="91348-131">Criar um novo membro consolidado.</span><span class="sxs-lookup"><span data-stu-id="91348-131">Create a new consolidated member.</span></span>|[<span data-ttu-id="91348-132">Criar um membro consolidado &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-132">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)|
|<span data-ttu-id="91348-133">Excluir um membro ou uma coleção existente.</span><span class="sxs-lookup"><span data-stu-id="91348-133">Delete an existing member or collection.</span></span>|[<span data-ttu-id="91348-134">Excluir um membro ou uma coleção &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-134">Delete a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="91348-135">Reativar um membro ou coleção excluído.</span><span class="sxs-lookup"><span data-stu-id="91348-135">Reactivate a deleted member or collection.</span></span>|[<span data-ttu-id="91348-136">Reativar um membro ou uma coleção &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-136">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="91348-137">Atualizar os valores de atributos de um membro.</span><span class="sxs-lookup"><span data-stu-id="91348-137">Update the attribute values of a member.</span></span>|[<span data-ttu-id="91348-138">Alterar o tipo de atributo &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-138">Change the Attribute Type &#40;MDS Add-in for Excel&#41;</span></span>](microsoft-excel-add-in/change-the-attribute-type-mds-add-in-for-excel.md)|
|<span data-ttu-id="91348-139">Mover membros dentro de uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="91348-139">Move members within a hierarchy.</span></span>|[<span data-ttu-id="91348-140">Mover membros dentro de uma hierarquia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-140">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="91348-141">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="91348-141">Related Content</span></span>

-   [<span data-ttu-id="91348-142">Visão geral de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="91348-142">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)

-   [<span data-ttu-id="91348-143">Entidades &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-143">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)

-   [<span data-ttu-id="91348-144">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-144">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="91348-145">Hierarquias &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-145">Hierarchies &#40;Master Data Services&#41;</span></span>](hierarchies-master-data-services.md)

-   [<span data-ttu-id="91348-146">Coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-146">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)

-   [<span data-ttu-id="91348-147">Permissões de folha &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-147">Leaf Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-permissions-master-data-services.md)

-   [<span data-ttu-id="91348-148">Permissões consolidadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-148">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)

-   [<span data-ttu-id="91348-149">Operadores de filtro &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91348-149">Filter Operators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/filter-operators-master-data-services.md)


