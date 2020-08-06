---
title: Hierarquias explícitas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, about explicit hierarchies
- hierarchies [Master Data Services], explicit hierarchies
- explicit hierarchies
ms.assetid: e6f44e37-e1f0-4c38-a816-1935a856d5a4
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f37f341dc2c003683e696f2767a6b644047d5a0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680533"
---
# <a name="explicit-hierarchies-master-data-services"></a><span data-ttu-id="f24bc-102">Hierarquias explícitas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f24bc-102">Explicit Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="f24bc-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], uma hierarquia explícita organiza os membros de uma única entidade de qualquer maneira que você especifique.</span><span class="sxs-lookup"><span data-stu-id="f24bc-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], an explicit hierarchy organizes members from a single entity in any way you specify.</span></span> <span data-ttu-id="f24bc-104">A estrutura pode ser desbalanceada e, ao contrário de hierarquias derivadas, hierarquias explícitas não são baseadas em relações de atributos baseadas em domínio.</span><span class="sxs-lookup"><span data-stu-id="f24bc-104">The structure can be ragged and unlike derived hierarchies, explicit hierarchies are not based on domain-based attribute relationships.</span></span>

## <a name="consolidated-members-group-other-members"></a><span data-ttu-id="f24bc-105">Membros consolidados agrupam outros membros</span><span class="sxs-lookup"><span data-stu-id="f24bc-105">Consolidated Members Group Other Members</span></span>
 <span data-ttu-id="f24bc-106">Uma hierarquia explícita usa membros consolidados que você cria com o objetivo de agrupar outros membros.</span><span class="sxs-lookup"><span data-stu-id="f24bc-106">An explicit hierarchy uses consolidated members that you create for the purpose of grouping other members.</span></span> <span data-ttu-id="f24bc-107">Esses membros consolidados podem pertencer somente a uma hierarquia explícita por vez.</span><span class="sxs-lookup"><span data-stu-id="f24bc-107">These consolidated members can belong to only one explicit hierarchy at a time.</span></span> <span data-ttu-id="f24bc-108">Uma hierarquia explícita também inclui todos os membros folha da entidade associada.</span><span class="sxs-lookup"><span data-stu-id="f24bc-108">An explicit hierarchy also includes all of the leaf members from the associated entity.</span></span>

 <span data-ttu-id="f24bc-109">Uma hierarquia explícita pode ser imperfeita, o que significa que a hierarquia pode terminar simultaneamente em níveis diferentes.</span><span class="sxs-lookup"><span data-stu-id="f24bc-109">An explicit hierarchy can be ragged, which means that the hierarchy can end at different levels simultaneously.</span></span> <span data-ttu-id="f24bc-110">Cada membro consolidado pode ter um número ilimitado de membros consolidados e membros folha sob ele ou pode não ter nenhum.</span><span class="sxs-lookup"><span data-stu-id="f24bc-110">Each consolidated member can have an unlimited number of consolidated and leaf members underneath, or can have none.</span></span> <span data-ttu-id="f24bc-111">Os membros folha podem estar sob um único membro consolidado ou sob vários níveis de membros consolidados.</span><span class="sxs-lookup"><span data-stu-id="f24bc-111">The leaf members can be under a single consolidated member or under multiple levels of consolidated members.</span></span>

> [!NOTE]
>  <span data-ttu-id="f24bc-112">Antes de você criar uma hierarquia explícita, a entidade deve estar habilitada para hierarquias explícitas.</span><span class="sxs-lookup"><span data-stu-id="f24bc-112">Before you can create an explicit hierarchy, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="f24bc-113">Para obter mais informações, consulte [habilitar uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f24bc-113">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>

## <a name="types-of-explicit-hierarchies"></a><span data-ttu-id="f24bc-114">Tipos de hierarquias explícitas</span><span class="sxs-lookup"><span data-stu-id="f24bc-114">Types of Explicit Hierarchies</span></span>
 <span data-ttu-id="f24bc-115">Há dois tipos de hierarquias explícitas: obrigatória e não obrigatória.</span><span class="sxs-lookup"><span data-stu-id="f24bc-115">There are two types of explicit hierarchies: mandatory and non-mandatory.</span></span>

### <a name="mandatory-explicit-hierarchy"></a><span data-ttu-id="f24bc-116">Hierarquia explícita obrigatória</span><span class="sxs-lookup"><span data-stu-id="f24bc-116">Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="f24bc-117">Uma hierarquia explícita obrigatória é uma hierarquia na qual todos os membros folha devem ser incluídos na árvore hierárquica.</span><span class="sxs-lookup"><span data-stu-id="f24bc-117">A mandatory explicit hierarchy is a hierarchy in which all leaf members must be included in the hierarchy tree.</span></span> <span data-ttu-id="f24bc-118">Por padrão, todos os membros são incluídos na raiz da árvore.</span><span class="sxs-lookup"><span data-stu-id="f24bc-118">By default, all members are included at the root of the tree.</span></span> <span data-ttu-id="f24bc-119">Você pode reorganizar os membros conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="f24bc-119">You can rearrange the members as needed.</span></span>

### <a name="non-mandatory-explicit-hierarchy"></a><span data-ttu-id="f24bc-120">Hierarquia explícita não obrigatória</span><span class="sxs-lookup"><span data-stu-id="f24bc-120">Non-Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="f24bc-121">Uma hierarquia explícita não obrigatória é uma hierarquia em que todos os membros folha se encontram em um nó **Não Utilizado** criado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="f24bc-121">A non-mandatory explicit hierarchy is a hierarchy in which all leaf members are in a system-created **Unused** node.</span></span> <span data-ttu-id="f24bc-122">Você pode mover os membros para fora desse nó, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f24bc-122">You can move members out of this node as you need them.</span></span> <span data-ttu-id="f24bc-123">O restante dos membros pode permanecer no nó **Não Utilizado** .</span><span class="sxs-lookup"><span data-stu-id="f24bc-123">The rest of the members can remain in the **Unused** node.</span></span>

 <span data-ttu-id="f24bc-124">Quando você usar hierarquias explícitas não obrigatórias, qualquer relatório ou análise feita na hierarquia talvez não corresponda ao relatório ou à análise feita em hierarquias obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="f24bc-124">When you use non-mandatory explicit hierarchies, any reporting or analysis done on the hierarchy may not match reporting or analysis done on mandatory hierarchies.</span></span>

## <a name="rules"></a><span data-ttu-id="f24bc-125">Regras</span><span class="sxs-lookup"><span data-stu-id="f24bc-125">Rules</span></span>
 <span data-ttu-id="f24bc-126">As regras a seguir se aplicam a hierarquias explícitas (obrigatórias e não obrigatórias).</span><span class="sxs-lookup"><span data-stu-id="f24bc-126">The following rules apply to explicit hierarchies (both mandatory and non-mandatory).</span></span>

-   <span data-ttu-id="f24bc-127">Cada membro folha só pode ser incluído uma vez na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="f24bc-127">Each leaf member can be included in the hierarchy only once.</span></span>

-   <span data-ttu-id="f24bc-128">Todos os membros consolidados devem ser incluídos em uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="f24bc-128">All consolidated members must be included in a hierarchy.</span></span>

-   <span data-ttu-id="f24bc-129">Os membros consolidados não podem estar em mais de uma hierarquia explícita.</span><span class="sxs-lookup"><span data-stu-id="f24bc-129">Consolidated members cannot be in more than one explicit hierarchy.</span></span>

-   <span data-ttu-id="f24bc-130">Os membros consolidados na árvore hierárquica não têm de conter membros folha sob eles.</span><span class="sxs-lookup"><span data-stu-id="f24bc-130">Consolidated members in the hierarchy tree do not have to contain leaf members underneath them.</span></span>

-   <span data-ttu-id="f24bc-131">Se você excluir uma hierarquia explícita, todos os membros consolidados que foram usados na hierarquia serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="f24bc-131">If you delete an explicit hierarchy, all consolidated members that were used in the hierarchy are deleted.</span></span>

-   <span data-ttu-id="f24bc-132">Se você excluir um membro consolidado que estava em uma hierarquia explícita, todos os membros folha que foram agrupados por esse membro consolidado serão movidos para a raiz.</span><span class="sxs-lookup"><span data-stu-id="f24bc-132">If you delete a consolidated member that was in an explicit hierarchy, all leaf members that were grouped by that consolidated member are moved to the root.</span></span>

## <a name="explicit-hierarchies-versus-derived-hierarchies"></a><span data-ttu-id="f24bc-133">Hierarquias explícitas versus hierarquias derivadas</span><span class="sxs-lookup"><span data-stu-id="f24bc-133">Explicit Hierarchies versus Derived Hierarchies</span></span>
 <span data-ttu-id="f24bc-134">A tabela a seguir mostra algumas das diferenças entre hierarquias explícitas e derivadas.</span><span class="sxs-lookup"><span data-stu-id="f24bc-134">The following table shows some of the differences between explicit and derived hierarchies.</span></span>

|<span data-ttu-id="f24bc-135">Hierarquias explícitas</span><span class="sxs-lookup"><span data-stu-id="f24bc-135">Explicit Hierarchies</span></span>|<span data-ttu-id="f24bc-136">Hierarquias derivadas</span><span class="sxs-lookup"><span data-stu-id="f24bc-136">Derived Hierarchies</span></span>|
|--------------------------|-------------------------|
|<span data-ttu-id="f24bc-137">A estrutura é definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f24bc-137">Structure is defined by the user</span></span>|<span data-ttu-id="f24bc-138">A estrutura é derivada das relações entre atributos baseados em domínio</span><span class="sxs-lookup"><span data-stu-id="f24bc-138">Structure is derived from the relationships between domain-based attributes</span></span>|
|<span data-ttu-id="f24bc-139">Contém os membros de uma única entidade</span><span class="sxs-lookup"><span data-stu-id="f24bc-139">Contains members from a single entity</span></span>|<span data-ttu-id="f24bc-140">Contém os membros de várias entidades</span><span class="sxs-lookup"><span data-stu-id="f24bc-140">Contains members from multiple entities</span></span>|
|<span data-ttu-id="f24bc-141">Usa membros consolidados para agrupar outros membros</span><span class="sxs-lookup"><span data-stu-id="f24bc-141">Uses consolidated members to group other members</span></span>|<span data-ttu-id="f24bc-142">Usa membros folha de uma entidade para agrupar membros folha de outra entidade</span><span class="sxs-lookup"><span data-stu-id="f24bc-142">Uses leaf members from one entity to group leaf members from another entity</span></span>|
|<span data-ttu-id="f24bc-143">Pode ser irregular</span><span class="sxs-lookup"><span data-stu-id="f24bc-143">Can be ragged</span></span>|<span data-ttu-id="f24bc-144">Sempre contém um número consistente de níveis</span><span class="sxs-lookup"><span data-stu-id="f24bc-144">Always contains a consistent number of levels</span></span>|

## <a name="explicit-hierarchy-example"></a><span data-ttu-id="f24bc-145">Exemplo de hierarquia explícita</span><span class="sxs-lookup"><span data-stu-id="f24bc-145">Explicit Hierarchy Example</span></span>
 <span data-ttu-id="f24bc-146">No exemplo a seguir, a entidade Produto contém estes membros folha: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450} e BK-R650 {Road-650}.</span><span class="sxs-lookup"><span data-stu-id="f24bc-146">In the following example, the Product entity contains these leaf members: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450}, and BK-R650 {Road-650}.</span></span>

 <span data-ttu-id="f24bc-147">Para resumir esses membros folha a pontos de consolidação específicos, você pode criar membros consolidados na entidade Produto.</span><span class="sxs-lookup"><span data-stu-id="f24bc-147">To summarize these leaf members at specific consolidation points, you can create consolidated members in the Product entity.</span></span> <span data-ttu-id="f24bc-148">Insira os membros consolidados em níveis na árvore hierárquica em que você deseja resumir os membros folha.</span><span class="sxs-lookup"><span data-stu-id="f24bc-148">Insert the consolidated members at levels in the hierarchy tree where you want to summarize the leaf members.</span></span> <span data-ttu-id="f24bc-149">Não há nenhuma limitação em relação a onde você insere seus membros consolidados; no entanto, cada membro (folha ou consolidado) só pode ser usado uma vez.</span><span class="sxs-lookup"><span data-stu-id="f24bc-149">There is no limitation on where you insert your consolidated members; however, each member (leaf or consolidated) can be used only once.</span></span>

 <span data-ttu-id="f24bc-150">![Exemplo de hierarquia explícita de mountain bike](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Exemplo de hierarquia explícita de mountain bike")</span><span class="sxs-lookup"><span data-stu-id="f24bc-150">![Mountain Bike Explicit Hierarchy Example](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Mountain Bike Explicit Hierarchy Example")</span></span>

 <span data-ttu-id="f24bc-151">Membros consolidados podem ser usados para agrupar membros em qualquer nível, e membros folha e membros consolidados são classificados na ordem que você determinar.</span><span class="sxs-lookup"><span data-stu-id="f24bc-151">Consolidated members can be used to group members at any level, and leaf and consolidated members are sorted in the order you determine.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="f24bc-152">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f24bc-152">Related Tasks</span></span>

|<span data-ttu-id="f24bc-153">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="f24bc-153">Task Description</span></span>|<span data-ttu-id="f24bc-154">Tópico</span><span class="sxs-lookup"><span data-stu-id="f24bc-154">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="f24bc-155">Habilitar uma entidade para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="f24bc-155">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="f24bc-156">Habilite uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f24bc-156">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="f24bc-157">Criar uma nova hierarquia.</span><span class="sxs-lookup"><span data-stu-id="f24bc-157">Create a new explicit hierarchy.</span></span>|[<span data-ttu-id="f24bc-158">Criar uma hierarquia explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f24bc-158">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="f24bc-159">Alterar o nome de uma hierarquia explícita existente.</span><span class="sxs-lookup"><span data-stu-id="f24bc-159">Change the name of an existing explicity hierarchy.</span></span>|[<span data-ttu-id="f24bc-160">Alterar o nome de uma hierarquia explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f24bc-160">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="f24bc-161">Excluir uma hierarquia explícita existente.</span><span class="sxs-lookup"><span data-stu-id="f24bc-161">Delete an existing explicit hierarchy.</span></span>|[<span data-ttu-id="f24bc-162">Excluir uma hierarquia explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f24bc-162">Delete an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-explicit-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="f24bc-163">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="f24bc-163">Related Content</span></span>

-   [<span data-ttu-id="f24bc-164">Hierarquias derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f24bc-164">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="f24bc-165">Coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f24bc-165">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)


