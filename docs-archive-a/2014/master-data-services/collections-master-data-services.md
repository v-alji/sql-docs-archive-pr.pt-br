---
title: Coleções (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services]
- collections [Master Data Services], about collections
ms.assetid: 5aa1d1e0-b4e5-4897-8e74-01dcf418df73
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce49c57aad5da52dabba32a0f3fb9b6f4f45b209
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680552"
---
# <a name="collections-master-data-services"></a><span data-ttu-id="116d8-102">Coleções (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="116d8-102">Collections (Master Data Services)</span></span>
  <span data-ttu-id="116d8-103">Uma coleção é um grupo de membros folha e consolidados de uma única entidade.</span><span class="sxs-lookup"><span data-stu-id="116d8-103">A collection is a group of leaf and consolidated members from a single entity.</span></span> <span data-ttu-id="116d8-104">Use coleções quando não precisar de uma hierarquia completa e desejar exibir agrupamentos diferentes de membros para relatório ou análise, ou quando precisar criar uma taxonomia.</span><span class="sxs-lookup"><span data-stu-id="116d8-104">Use collections when you do not need a complete hierarchy and you want to view different groupings of members for reporting or analysis, or when you need to create a taxonomy.</span></span>  
  
## <a name="what-collections-contain"></a><span data-ttu-id="116d8-105">O que as coleções contêm</span><span class="sxs-lookup"><span data-stu-id="116d8-105">What Collections Contain</span></span>  
 <span data-ttu-id="116d8-106">Coleções não limitam o número ou o tipo de membros que podem ser incluídos, desde que os membros estejam dentro da mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="116d8-106">Collections do not limit the number or type of members you can include, as long as the members are within the same entity.</span></span> <span data-ttu-id="116d8-107">Uma coleção pode conter membros folha e consolidados de várias hierarquias explícitas obrigatórias e não obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="116d8-107">A collection can contain leaf and consolidated members from multiple mandatory and non-mandatory explicit hierarchies.</span></span>  
  
 <span data-ttu-id="116d8-108">Quando você cria uma coleção, não está criando uma estrutura hierárquica; você está criando uma lista simples de membros.</span><span class="sxs-lookup"><span data-stu-id="116d8-108">When you create a collection, you are not creating a hierarchical structure; you are creating a flat list of members.</span></span> <span data-ttu-id="116d8-109">Quando você seleciona um nó de uma hierarquia e adiciona-o à coleção, o membro consolidado selecionado é o único membro acrescentado à coleção.</span><span class="sxs-lookup"><span data-stu-id="116d8-109">When you select a node from a hierarchy and add it to the collection, the consolidated member you selected is the only member added to the collection.</span></span>  
  
 <span data-ttu-id="116d8-110">Uma coleção também pode conter outras coleções.</span><span class="sxs-lookup"><span data-stu-id="116d8-110">A collection can also contain other collections.</span></span> <span data-ttu-id="116d8-111">É possível usar coleções de coleções para criar taxonomias.</span><span class="sxs-lookup"><span data-stu-id="116d8-111">You can use collections of collections to create taxonomies.</span></span>  
  
 <span data-ttu-id="116d8-112">Quando cria uma coleção, você é listado automaticamente como o proprietário.</span><span class="sxs-lookup"><span data-stu-id="116d8-112">When you create a collection you are automatically listed as the owner.</span></span> <span data-ttu-id="116d8-113">Se você for um administrador, poderá criar outros atributos para a coleção conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="116d8-113">If you are an administrator, you can create other attributes for your collection as needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="116d8-114">Para poder criar uma coleção, a entidade deve estar habilitada para hierarquias explícitas.</span><span class="sxs-lookup"><span data-stu-id="116d8-114">Before you can create a collection, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="116d8-115">Para obter mais informações, consulte [habilitar uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="116d8-115">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
## <a name="subscription-views-for-collections"></a><span data-ttu-id="116d8-116">Exibições de assinatura para coleções</span><span class="sxs-lookup"><span data-stu-id="116d8-116">Subscription Views for Collections</span></span>  
 <span data-ttu-id="116d8-117">Há dois tipos de exibições de assinatura que mostram coleções.</span><span class="sxs-lookup"><span data-stu-id="116d8-117">There are two types of subscription views that show collections.</span></span> <span data-ttu-id="116d8-118">O formato **Atributos da coleção** mostra uma lista de coleções e todos os atributos relacionados às coleções (como descrição ou proprietário).</span><span class="sxs-lookup"><span data-stu-id="116d8-118">The **Collection attributes** format shows a list of collections and any attributes related to the collections (like description or owner).</span></span> <span data-ttu-id="116d8-119">O formato **Coleções** mostra todos os membros em todas as coleções, bem como cada peso de membros e a ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="116d8-119">The **Collections** format shows all members in all collections, as well as each members weight and sort order.</span></span> <span data-ttu-id="116d8-120">Para obter mais informações, consulte [exportando dados &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="116d8-120">For more information, see [Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span></span>  
  
 <span data-ttu-id="116d8-121">Se você definir valores de peso para membros específicos em uma coleção, estes valores estarão disponíveis em exibições de assinatura relacionadas.</span><span class="sxs-lookup"><span data-stu-id="116d8-121">If you set weight values for specific members in a collection, these values are available in related subscription views.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="116d8-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="116d8-122">Related Tasks</span></span>  
  
|<span data-ttu-id="116d8-123">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="116d8-123">Task Description</span></span>|<span data-ttu-id="116d8-124">Tópico</span><span class="sxs-lookup"><span data-stu-id="116d8-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="116d8-125">Habilitar uma entidade para hierarquias explícitas e coleções.</span><span class="sxs-lookup"><span data-stu-id="116d8-125">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="116d8-126">Habilite uma entidade para hierarquias explícitas e coleções &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="116d8-126">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|  
|<span data-ttu-id="116d8-127">Criar uma nova coleção.</span><span class="sxs-lookup"><span data-stu-id="116d8-127">Create a new collection.</span></span>|[<span data-ttu-id="116d8-128">Criar uma coleção &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="116d8-128">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)|  
|<span data-ttu-id="116d8-129">Adicionar membros a uma coleção existente.</span><span class="sxs-lookup"><span data-stu-id="116d8-129">Add members to an existing collection.</span></span>|[<span data-ttu-id="116d8-130">Adicionar membros a uma coleção &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="116d8-130">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="116d8-131">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="116d8-131">Related Content</span></span>  
  
-   [<span data-ttu-id="116d8-132">Hierarquias explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="116d8-132">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
-   [<span data-ttu-id="116d8-133">Exportando dados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="116d8-133">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
