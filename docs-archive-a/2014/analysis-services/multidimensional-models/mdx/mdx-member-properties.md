---
title: Usando propriedades de membro (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DIMENSION PROPERTIES keyword
- Properties function
- member properties [MDX]
- members [MDX], properties
ms.assetid: 26b5ad08-3799-4a5e-89f3-dca25e637d45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5b7fdf989fc23ea70be7d7863f5d4c6ac0b61d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680093"
---
# <a name="using-member-properties-mdx"></a><span data-ttu-id="26e65-102">Usando propriedades do membro (MDX)</span><span class="sxs-lookup"><span data-stu-id="26e65-102">Using Member Properties (MDX)</span></span>
  <span data-ttu-id="26e65-103">As propriedades do membro incluem informações básicas sobre cada membro de cada tupla.</span><span class="sxs-lookup"><span data-stu-id="26e65-103">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="26e65-104">Entre as informações básicas estão nome do membro, nível pai, número de filhos, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="26e65-104">This basic information includes the member name, parent level, the number of children, and so on.</span></span> <span data-ttu-id="26e65-105">As propriedades do membro estão disponíveis para todos os membros de um determinado nível.</span><span class="sxs-lookup"><span data-stu-id="26e65-105">Member properties are available for all members at a given level.</span></span> <span data-ttu-id="26e65-106">Em termos de organização, elas são tratadas como dados organizados dimensionalmente, armazenados em uma única dimensão.</span><span class="sxs-lookup"><span data-stu-id="26e65-106">In terms of organization, member properties are treated as dimensionally organized data, stored on a single dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26e65-107">No [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], as propriedades do membro são conhecidas como relações de atributo.</span><span class="sxs-lookup"><span data-stu-id="26e65-107">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], member properties are know as attribute relationships.</span></span> <span data-ttu-id="26e65-108">Para obter mais informações, consulte [Relações de atributos](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="26e65-108">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
 <span data-ttu-id="26e65-109">As propriedades do membro são *intrínsecas* ou *personalizadas*:</span><span class="sxs-lookup"><span data-stu-id="26e65-109">Member properties are either *intrinsic* or *custom*:</span></span>  
  
 <span data-ttu-id="26e65-110">Propriedades do membro intrínsecas</span><span class="sxs-lookup"><span data-stu-id="26e65-110">Intrinsic member properties</span></span>  
 <span data-ttu-id="26e65-111">Todos os membros suportam propriedades intrínsecas, como o valor formatado de um membro, enquanto dimensões e níveis fornecem propriedades do membro da dimensão e do nível intrínsecas adicionais, como a identificação de um membro.</span><span class="sxs-lookup"><span data-stu-id="26e65-111">All members support intrinsic member properties, such as the formatted value of a member, while dimensions and levels supply additional intrinsic dimension and level member properties, such as the ID of a member.</span></span>  
  
 <span data-ttu-id="26e65-112">Para obter mais informações, consulte [Propriedades intrínsecas do membro &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="26e65-112">For more information, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
 <span data-ttu-id="26e65-113">Propriedades do membro definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="26e65-113">User-defined member properties</span></span>  
 <span data-ttu-id="26e65-114">Com frequência, os membros possuem propriedades adicionais associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="26e65-114">Members often have additional properties associated with them.</span></span> <span data-ttu-id="26e65-115">Por exemplo, o nível Produtos pode oferecer as propriedades SKU, SRP, Importância e Volume para cada produto.</span><span class="sxs-lookup"><span data-stu-id="26e65-115">For example, the Products level may offer the SKU, SRP, Weight, and Volume properties for each product.</span></span> <span data-ttu-id="26e65-116">Essas propriedades não são membros, mas contêm informações adicionais sobre os membros do nível Produtos.</span><span class="sxs-lookup"><span data-stu-id="26e65-116">These properties are not members, but contain additional information about members at the Products level.</span></span>  
  
 <span data-ttu-id="26e65-117">Para obter mais informações, consulte [Propriedades do membro definidas pelo usuário &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="26e65-117">For more information, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
 <span data-ttu-id="26e65-118">As propriedades intrínsecas e definidas pelo usuário podem ser recuperadas por meio do uso da `PROPERTIES` palavra-chave ou da função [Properties](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="26e65-118">Both intrinsic and user-defined member properties can be retrieved through the use of the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
## <a name="using-the-properties-keyword"></a><span data-ttu-id="26e65-119">Usando a palavra-chave PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="26e65-119">Using the PROPERTIES Keyword</span></span>  
 <span data-ttu-id="26e65-120">A palavra-chave `PROPERTIES` especifica as propriedades do membro que serão usadas em uma determinada dimensão de eixo.</span><span class="sxs-lookup"><span data-stu-id="26e65-120">The `PROPERTIES` keyword specifies the member properties that are to be used for a given axis dimension.</span></span> <span data-ttu-id="26e65-121">A `PROPERTIES` palavra-chave é incluída na `<axis specification>` cláusula da instrução MDX [Select](/sql/mdx/mdx-data-manipulation-select) :</span><span class="sxs-lookup"><span data-stu-id="26e65-121">The `PROPERTIES` keyword is buried within the `<axis specification>` clause of the MDX [SELECT](/sql/mdx/mdx-data-manipulation-select) statement:</span></span>  
  
```  
SELECT [<axis_specification>  
       [, <axis_specification>...]]  
  FROM [<cube_specification>]  
[WHERE [<slicer_specification>]]  
```  
  
 <span data-ttu-id="26e65-122">A cláusula `<axis_specification>` inclui uma cláusula `<dim_props>` opcional, como mostrada na sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="26e65-122">The `<axis_specification>` clause includes an optional `<dim_props>` clause, as shown in the following syntax:</span></span>  
  
```  
<axis_specification> ::= <set> [<dim_props>] ON <axis_name>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="26e65-123">Para obter mais informações sobre os valores `<set>` e `<axis_name>`, consulte [Especificando o conteúdo de um eixo de consulta &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="26e65-123">For more information about the `<set>` and `<axis_name>` values, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
 <span data-ttu-id="26e65-124">A cláusula `<dim_props>` permite a consulta de uma dimensão, de um nível e de propriedades do membro usando a palavra-chave `PROPERTIES`.</span><span class="sxs-lookup"><span data-stu-id="26e65-124">The `<dim_props>` clause lets you query dimension, level, and member properties using the `PROPERTIES` keyword.</span></span> <span data-ttu-id="26e65-125">A sintaxe a seguir mostra a formatação da cláusula `<dim_props>` :</span><span class="sxs-lookup"><span data-stu-id="26e65-125">The following syntax shows the formatting of the `<dim_props>` clause:</span></span>  
  
```  
<dim_props> ::= [DIMENSION] PROPERTIES <property> [,<property>...]  
```  
  
 <span data-ttu-id="26e65-126">A quebra da sintaxe `<property>` varia de acordo com a propriedade que você está consultando:</span><span class="sxs-lookup"><span data-stu-id="26e65-126">The breakdown of the `<property>` syntax varies depending on the property that you are querying:</span></span>  
  
-   <span data-ttu-id="26e65-127">Propriedades do membro intrínsecas sensíveis a contexto devem ser precedidas pelo nome da dimensão ou do nível.</span><span class="sxs-lookup"><span data-stu-id="26e65-127">Context sensitive intrinsic member properties must be preceded with the name of the dimension or level.</span></span> <span data-ttu-id="26e65-128">No entanto, propriedades do membro intrínsecas não sensíveis a contexto não podem ser qualificadas pelo nome da dimensão ou do nível.</span><span class="sxs-lookup"><span data-stu-id="26e65-128">However, non-context sensitive intrinsic member properties cannot be qualified by the dimension or level name.</span></span> <span data-ttu-id="26e65-129">Para obter mais informações sobre como usar a `PROPERTIES` palavra-chave com propriedades intrínsecas do membro, consulte [propriedades intrínsecas do membro &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="26e65-129">For more information about how to use the `PROPERTIES` keyword with intrinsic member properties, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
-   <span data-ttu-id="26e65-130">Propriedades do membro definidas pelo usuário devem ser precedidas pelo nome do nível no qual residem.</span><span class="sxs-lookup"><span data-stu-id="26e65-130">User-defined member properties should be preceded by the name of the level in which they reside.</span></span> <span data-ttu-id="26e65-131">Para obter mais informações sobre como usar a `PROPERTIES` palavra-chave com propriedades de membro definidas pelo usuário, consulte [Propriedades do membro definidas pelo usuário &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="26e65-131">For more information about how to use the `PROPERTIES` keyword with user-defined member properties, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e65-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26e65-132">See Also</span></span>  
 [<span data-ttu-id="26e65-133">Criando e usando valores de propriedade &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="26e65-133">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)  
  
  
