---
title: Hierarquias (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services]
- hierarchies [Master Data Services], about hierarchies
ms.assetid: 70dbb1fc-ead7-45be-9552-a45e3ccd8d21
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 126a01c03134c6859426c09fda398408694795f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575186"
---
# <a name="hierarchies-master-data-services"></a><span data-ttu-id="8eda6-102">Hierarquias (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8eda6-102">Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="8eda6-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], uma hierarquia é uma estrutura de árvore que você pode usar para:</span><span class="sxs-lookup"><span data-stu-id="8eda6-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a hierarchy is a tree structure that you can use to:</span></span>

-   <span data-ttu-id="8eda6-104">Agrupar membros semelhantes para fins organizacionais.</span><span class="sxs-lookup"><span data-stu-id="8eda6-104">Group similar members for organizational purposes.</span></span>

-   <span data-ttu-id="8eda6-105">Consolidar e resumir membros para relatório e análise.</span><span class="sxs-lookup"><span data-stu-id="8eda6-105">Consolidate and summarize members for reporting and analysis.</span></span>

## <a name="what-hierarchies-contain"></a><span data-ttu-id="8eda6-106">O que as hierarquias contêm</span><span class="sxs-lookup"><span data-stu-id="8eda6-106">What Hierarchies Contain</span></span>
 <span data-ttu-id="8eda6-107">Cada hierarquia contém os membros de uma ou mais entidades.</span><span class="sxs-lookup"><span data-stu-id="8eda6-107">Each hierarchy contains members from one or more entities.</span></span> <span data-ttu-id="8eda6-108">Quando um membro é adicionado, alterado ou excluído, todas as hierarquias são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="8eda6-108">When a member is added, changed, or deleted, all hierarchies are updated.</span></span> <span data-ttu-id="8eda6-109">Isso assegura que os dados sejam precisos em todas as hierarquias.</span><span class="sxs-lookup"><span data-stu-id="8eda6-109">This ensures that the data is accurate in all hierarchies.</span></span> <span data-ttu-id="8eda6-110">As hierarquias também ajudam a garantir que cada membro é contado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="8eda6-110">Hierarchies also help ensure that each member is counted once and only once.</span></span>

 <span data-ttu-id="8eda6-111">Se você quiser criar um agrupamento de um subconjunto de membros, use uma coleção.</span><span class="sxs-lookup"><span data-stu-id="8eda6-111">If you want to create a grouping of a subset of members, consider using a collection.</span></span> <span data-ttu-id="8eda6-112">Para obter mais informações, consulte [Coleções &#40;Master Data Services&#41;](collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8eda6-112">For more information, see [Collections &#40;Master Data Services&#41;](collections-master-data-services.md).</span></span>

## <a name="kinds-of-hierarchies"></a><span data-ttu-id="8eda6-113">Tipos de hierarquia</span><span class="sxs-lookup"><span data-stu-id="8eda6-113">Kinds of Hierarchies</span></span>
 <span data-ttu-id="8eda6-114">Você pode criar várias hierarquias para exibir e organizar seus membros de formas diferentes.</span><span class="sxs-lookup"><span data-stu-id="8eda6-114">You can create multiple hierarchies to view and organize your members in different ways.</span></span> <span data-ttu-id="8eda6-115">Você pode criar:</span><span class="sxs-lookup"><span data-stu-id="8eda6-115">You can create:</span></span>

-   <span data-ttu-id="8eda6-116">Hierarquias desbalanceadas de uma única entidade, que são chamadas de hierarquias explícitas.</span><span class="sxs-lookup"><span data-stu-id="8eda6-116">Ragged hierarchies from a single entity, which are called explicit hierarchies.</span></span> <span data-ttu-id="8eda6-117">Para obter mais informações, consulte [Hierarquias explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8eda6-117">For more information, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>

-   <span data-ttu-id="8eda6-118">Hierarquias baseadas em nível de várias entidades, com base nas relações existentes entre as entidades e seus atributos, que são chamadas de hierarquias derivadas.</span><span class="sxs-lookup"><span data-stu-id="8eda6-118">Level-based hierarchies from multiple entities, based on the existing relationships between entities and their attributes, which are called derived hierarchies.</span></span> <span data-ttu-id="8eda6-119">Para obter mais informações, consulte [Hierarquias derivadas &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8eda6-119">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="8eda6-120">Todos os membros em uma hierarquia devem estar dentro do mesmo modelo.</span><span class="sxs-lookup"><span data-stu-id="8eda6-120">All members in a hierarchy must be within the same model.</span></span>

## <a name="hierarchies-are-not-taxonomies"></a><span data-ttu-id="8eda6-121">Hierarquias não são taxonomias</span><span class="sxs-lookup"><span data-stu-id="8eda6-121">Hierarchies Are Not Taxonomies</span></span>
 <span data-ttu-id="8eda6-122">Uma hierarquia é diferente de uma taxonomia.</span><span class="sxs-lookup"><span data-stu-id="8eda6-122">A hierarchy is different from a taxonomy.</span></span> <span data-ttu-id="8eda6-123">Uma taxonomia organiza os membros por vários atributos ao mesmo tempo, enquanto uma hierarquia organiza os membros por um atributo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="8eda6-123">A taxonomy organizes members by multiple attributes at the same time, while a hierarchy organizes members by one attribute at a time.</span></span> <span data-ttu-id="8eda6-124">Uma taxonomia pode incluir o mesmo membro várias vezes, enquanto uma hierarquia inclui um membro somente uma vez.</span><span class="sxs-lookup"><span data-stu-id="8eda6-124">A taxonomy can include the same member multiple times, while a hierarchy includes a member only once.</span></span>

 <span data-ttu-id="8eda6-125">Por exemplo, a mesma bicicleta pode ser incluída duas vezes em uma taxonomia: uma vez porque é vermelha e uma vez porque é tamanho 38.</span><span class="sxs-lookup"><span data-stu-id="8eda6-125">For example, the same bike can be included in a taxonomy twice: once because it's red, and once because it's a size 38.</span></span> <span data-ttu-id="8eda6-126">Em uma hierarquia, a bicicleta é incluída apenas uma vez, de modo que você deve decidir se deseja mostrá-la em relação à cor ou ao tamanho.</span><span class="sxs-lookup"><span data-stu-id="8eda6-126">In a hierarchy, the bike is included only once, so you must decide whether to show it in relation to its color or its size.</span></span>

## <a name="hierarchy-example"></a><span data-ttu-id="8eda6-127">Exemplo de hierarquia</span><span class="sxs-lookup"><span data-stu-id="8eda6-127">Hierarchy Example</span></span>
 <span data-ttu-id="8eda6-128">No exemplo a seguir, os membros de produto são agrupados por membros de subcategoria.</span><span class="sxs-lookup"><span data-stu-id="8eda6-128">In the following example, product members are grouped by subcategory members.</span></span>

 <span data-ttu-id="8eda6-129">![Hierarquia agrupada por exemplo de subcategoria](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Hierarquia agrupada por exemplo de subcategoria")</span><span class="sxs-lookup"><span data-stu-id="8eda6-129">![Hierarchy Grouped by Subcategory Example](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Hierarchy Grouped by Subcategory Example")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="8eda6-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8eda6-130">Related Tasks</span></span>

|<span data-ttu-id="8eda6-131">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="8eda6-131">Task Description</span></span>|<span data-ttu-id="8eda6-132">Tópico</span><span class="sxs-lookup"><span data-stu-id="8eda6-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="8eda6-133">Habilitar uma entidade para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="8eda6-133">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="8eda6-134">Habilite uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-134">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="8eda6-135">Criar uma hierarquia explícita.</span><span class="sxs-lookup"><span data-stu-id="8eda6-135">Create a explicit hierarchy.</span></span>|[<span data-ttu-id="8eda6-136">Criar uma hierarquia explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-136">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="8eda6-137">Criar uma hierarquia derivada.</span><span class="sxs-lookup"><span data-stu-id="8eda6-137">Create a derived hierarchy.</span></span>|[<span data-ttu-id="8eda6-138">Criar uma hierarquia derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-138">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="8eda6-139">Ocultar ou excluir níveis em uma hierarquia derivada existente.</span><span class="sxs-lookup"><span data-stu-id="8eda6-139">Hide or delete levels in an existing derived hierarchy.</span></span>|[<span data-ttu-id="8eda6-140">Ocultar ou excluir níveis em uma hierarquia derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-140">Hide or Delete Levels in a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hide-or-delete-levels-in-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="8eda6-141">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="8eda6-141">Related Content</span></span>

-   [<span data-ttu-id="8eda6-142">Hierarquias explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-142">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)

-   [<span data-ttu-id="8eda6-143">Hierarquias derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-143">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="8eda6-144">Hierarquias recursivas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-144">Recursive Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/recursive-hierarchies-master-data-services.md)

-   [<span data-ttu-id="8eda6-145">Hierarquias derivadas com limites explícitos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-145">Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md)

-   [<span data-ttu-id="8eda6-146">Coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8eda6-146">Collections &#40;Master Data Services&#41;</span></span>](collections-master-data-services.md)


