---
title: Atributos baseados em domínio (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], about domain-based attributes
- domain-based attributes [Master Data Services]
- attributes [Master Data Services], domain-based attributes
ms.assetid: df6f33ff-97f6-466c-af74-9780b2247473
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9182974923848d49ed3e9ecfb58a14949784a2c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584162"
---
# <a name="domain-based-attributes-master-data-services"></a><span data-ttu-id="9b380-102">Atributos baseados em domínio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9b380-102">Domain-Based Attributes (Master Data Services)</span></span>
  <span data-ttu-id="9b380-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], um atributo baseado em domínio é um atributo com valores que são preenchidos por membros de outra entidade.</span><span class="sxs-lookup"><span data-stu-id="9b380-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a domain-based attribute is an attribute with values that are populated by members from another entity.</span></span> <span data-ttu-id="9b380-104">Você pode pensar em um atributo baseado em domínio como uma lista restrita; atributos baseados em domínio impedem os usuários de inserir valores de atributo que não são válidos.</span><span class="sxs-lookup"><span data-stu-id="9b380-104">You can think of a domain-based attribute as a constrained list; domain-based attributes prevent users from entering attribute values that are not valid.</span></span> <span data-ttu-id="9b380-105">Para selecionar um valor de atributo, o usuário deve escolher as opções de uma lista.</span><span class="sxs-lookup"><span data-stu-id="9b380-105">To select an attribute value, the user must pick from a list.</span></span>

## <a name="domain-based-attribute-example"></a><span data-ttu-id="9b380-106">Exemplo de atributo baseado em domínio</span><span class="sxs-lookup"><span data-stu-id="9b380-106">Domain-Based Attribute Example</span></span>
 <span data-ttu-id="9b380-107">Na imagem a seguir, a entidade Product possui um atributo baseado em domínio chamado Subcategory.</span><span class="sxs-lookup"><span data-stu-id="9b380-107">In the following image, the Product entity has a domain-based attribute called Subcategory.</span></span> <span data-ttu-id="9b380-108">O atributo Subcategory é preenchido com os valores da entidade Subcategory.</span><span class="sxs-lookup"><span data-stu-id="9b380-108">The Subcategory attribute is populated by values from the Subcategory entity.</span></span>

 <span data-ttu-id="9b380-109">A entidade Subcategory possui um atributo baseado em domínio chamado Category.</span><span class="sxs-lookup"><span data-stu-id="9b380-109">The Subcategory entity has a domain-based attribute called Category.</span></span> <span data-ttu-id="9b380-110">O atributo Category é preenchido com os valores da entidade Category.</span><span class="sxs-lookup"><span data-stu-id="9b380-110">The Category attribute is populated by values from the Category entity.</span></span>

 <span data-ttu-id="9b380-111">![Atributos baseados em domínio em uma entidade](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Atributos baseados em domínio em uma entidade")</span><span class="sxs-lookup"><span data-stu-id="9b380-111">![Domain-Based Attributes in an Entity](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Domain-Based Attributes in an Entity")</span></span>

## <a name="use-same-entity-for-multiple-domain-based-attributes"></a><span data-ttu-id="9b380-112">Usar a mesma entidade para vários atributos baseados em domínio</span><span class="sxs-lookup"><span data-stu-id="9b380-112">Use Same Entity for Multiple Domain-Based Attributes</span></span>
 <span data-ttu-id="9b380-113">Você pode usar a mesma entidade como um atributo baseado em domínio de várias entidades.</span><span class="sxs-lookup"><span data-stu-id="9b380-113">You can use the same entity as a domain-based attribute of multiple entities.</span></span> <span data-ttu-id="9b380-114">Por exemplo, você pode criar uma entidade chamada YesNoIndicator com os membros Sim, Não e Talvez.</span><span class="sxs-lookup"><span data-stu-id="9b380-114">For example, you can create an entity called YesNoIndicator with the members: Yes, No, and Maybe.</span></span> <span data-ttu-id="9b380-115">Você pode criar um atributo baseado em domínio chamado InStock e usar a entidade YesNoIndicator como origem.</span><span class="sxs-lookup"><span data-stu-id="9b380-115">You can create a domain-based attribute named InStock and use the YesNoIndicator entity as the source.</span></span> <span data-ttu-id="9b380-116">Você também pode criar outro atributo baseado em domínio chamado Approved e usar a entidade YesNoIndicator como uma origem.</span><span class="sxs-lookup"><span data-stu-id="9b380-116">You can also create another domain-based attribute named Approved and use the YesNoIndicator entity as a source.</span></span> <span data-ttu-id="9b380-117">Sempre que quiser que os usuários escolham as opções de uma lista dos membros da entidade YesNoIndicator, você pode usar a entidade como atributo com base em domínio.</span><span class="sxs-lookup"><span data-stu-id="9b380-117">Any time you want users to choose from a list of the YesNoIndicator entity's members, you can use the entity as a domain-based attribute.</span></span>

## <a name="domain-based-attributes-form-derived-hierarchies"></a><span data-ttu-id="9b380-118">Atributos baseados em domínio formam hierarquias derivadas</span><span class="sxs-lookup"><span data-stu-id="9b380-118">Domain-Based Attributes Form Derived Hierarchies</span></span>
 <span data-ttu-id="9b380-119">As relações de atributos baseados em domínio são a base das hierarquias derivadas.</span><span class="sxs-lookup"><span data-stu-id="9b380-119">Domain-based attribute relationships are the basis for derived hierarchies.</span></span> <span data-ttu-id="9b380-120">Para obter mais informações, consulte [Hierarquias derivadas &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9b380-120">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span></span>

## <a name="related-tasks"></a><span data-ttu-id="9b380-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="9b380-121">Related Tasks</span></span>

|<span data-ttu-id="9b380-122">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="9b380-122">Task Description</span></span>|<span data-ttu-id="9b380-123">Tópico</span><span class="sxs-lookup"><span data-stu-id="9b380-123">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="9b380-124">Criar um novo atributo baseado em domínio que é originado de uma entidade existente.</span><span class="sxs-lookup"><span data-stu-id="9b380-124">Create a new domain-based attribute that is sourced from an existing entity.</span></span>|[<span data-ttu-id="9b380-125">Criar um atributo baseado em domínio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b380-125">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)|
|<span data-ttu-id="9b380-126">Criar uma nova entidade.</span><span class="sxs-lookup"><span data-stu-id="9b380-126">Create a new entity.</span></span>|[<span data-ttu-id="9b380-127">Criar uma entidade &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b380-127">Create an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-entity-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="9b380-128">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="9b380-128">Related Content</span></span>

-   [<span data-ttu-id="9b380-129">Hierarquias derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b380-129">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="9b380-130">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b380-130">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="9b380-131">Entidades &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b380-131">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)


