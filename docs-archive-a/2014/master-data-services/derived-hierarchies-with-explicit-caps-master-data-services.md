---
title: Hierarquias derivadas com extremidades explícitas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], derived hierarchies with explicit caps
- explicit hierarchies, derived hierarchies with explicit caps
- derived hierarchies, derived hierarchies with explicit caps
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d2460ddf098f0547c2876dd9689f5d2bf9b461a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570727"
---
# <a name="derived-hierarchies-with-explicit-caps-master-data-services"></a><span data-ttu-id="8c402-102">Hierarquias derivadas com nível superior (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8c402-102">Derived Hierarchies with Explicit Caps (Master Data Services)</span></span>
  <span data-ttu-id="8c402-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], quando os níveis de uma hierarquia explícita são usados como os níveis mais altos de uma hierarquia derivada, isso é chamado de hierarquia derivada com níveis superiores.</span><span class="sxs-lookup"><span data-stu-id="8c402-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when the levels from an explicit hierarchy are used as the top levels of a derived hierarchy, this is called a derived hierarchy with an explicit cap.</span></span>

 <span data-ttu-id="8c402-104">A hierarquia explícita deve ser baseada na mesma entidade que a entidade do alto da hierarquia derivada.</span><span class="sxs-lookup"><span data-stu-id="8c402-104">The explicit hierarchy must be based on the same entity as the entity at the top of the derived hierarchy.</span></span>

 <span data-ttu-id="8c402-105">Na interface do usuário do [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , é possível criar este tipo de hierarquia arrastando uma hierarquia explícita até a parte superior de uma hierarquia derivada.</span><span class="sxs-lookup"><span data-stu-id="8c402-105">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), you create this type of hierarchy by dragging an explicit hierarchy to the top of a derived hierarchy.</span></span>

 <span data-ttu-id="8c402-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="8c402-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span></span>

## <a name="derived-hierarchy-with-explicit-cap-example"></a><span data-ttu-id="8c402-107">Hierarquia derivada com exemplo de extremidade explícita</span><span class="sxs-lookup"><span data-stu-id="8c402-107">Derived Hierarchy with Explicit Cap Example</span></span>
 <span data-ttu-id="8c402-108">Neste exemplo, os membros na hierarquia explícita são da entidade Subcategoria.</span><span class="sxs-lookup"><span data-stu-id="8c402-108">In this example, the members in the explicit hierarchy are from the Subcategory entity.</span></span> <span data-ttu-id="8c402-109">Na hierarquia derivada, os membros da hierarquia de nível superior também são da entidade Subcategoria.</span><span class="sxs-lookup"><span data-stu-id="8c402-109">In the derived hierarchy, the top-level members are also from the Subcategory entity.</span></span>

 <span data-ttu-id="8c402-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span><span class="sxs-lookup"><span data-stu-id="8c402-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span></span>

 <span data-ttu-id="8c402-111">Ao usar a hierarquia explícita na parte superior de uma hierarquia derivada, a hierarquia derivada torna-se irregular.</span><span class="sxs-lookup"><span data-stu-id="8c402-111">By using the explicit hierarchy at the top of a derived hierarchy, the derived hierarchy becomes ragged.</span></span>

## <a name="rules"></a><span data-ttu-id="8c402-112">Regras</span><span class="sxs-lookup"><span data-stu-id="8c402-112">Rules</span></span>

-   <span data-ttu-id="8c402-113">Você não pode ter mais de uma hierarquia explícita em uma hierarquia derivada com nível superior.</span><span class="sxs-lookup"><span data-stu-id="8c402-113">You cannot have more than one explicit hierarchy in a derived hierarchy with explicit cap.</span></span>

-   <span data-ttu-id="8c402-114">Você pode usar a mesma hierarquia explícita como um nível superior para várias hierarquias derivadas.</span><span class="sxs-lookup"><span data-stu-id="8c402-114">You can use the same explicit hierarchy as a cap for multiple derived hierarchies.</span></span>

-   <span data-ttu-id="8c402-115">Você não pode atribuir permissões de membro de hierarquia a hierarquias derivadas com níveis superiores.</span><span class="sxs-lookup"><span data-stu-id="8c402-115">You cannot assign hierarchy member permissions to derived hierarchies with explicit caps.</span></span> <span data-ttu-id="8c402-116">Se você atribuir permissões individualmente à hierarquia explícita ou à hierarquia derivada, as permissões afetarão ambas as hierarquias.</span><span class="sxs-lookup"><span data-stu-id="8c402-116">If you assign permissions to either the explicit hierarchy or the derived hierarchy individually, the permissions affect both hierarchies.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="8c402-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8c402-117">Related Tasks</span></span>

|<span data-ttu-id="8c402-118">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="8c402-118">Task Description</span></span>|<span data-ttu-id="8c402-119">Tópico</span><span class="sxs-lookup"><span data-stu-id="8c402-119">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="8c402-120">Criar uma hierarquia derivada.</span><span class="sxs-lookup"><span data-stu-id="8c402-120">Create a derived hierarchy.</span></span>|[<span data-ttu-id="8c402-121">Criar uma hierarquia derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8c402-121">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="8c402-122">Criar uma hierarquia explícita.</span><span class="sxs-lookup"><span data-stu-id="8c402-122">Create an explicit hierarchy.</span></span>|[<span data-ttu-id="8c402-123">Criar uma hierarquia explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8c402-123">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="8c402-124">Excluir uma hierarquia derivada existente.</span><span class="sxs-lookup"><span data-stu-id="8c402-124">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="8c402-125">Excluir uma hierarquia derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8c402-125">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="8c402-126">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="8c402-126">Related Content</span></span>

-   [<span data-ttu-id="8c402-127">Hierarquias derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8c402-127">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="8c402-128">Hierarquias explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8c402-128">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)


