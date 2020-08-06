---
title: Relações de atributo | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- member properties [Analysis Services], attribute relationships
- security [Analysis Services], properties
- PROPERTIES keyword
- storage [Analysis Services], attribute relationships
- natural hierarchies [Analysis Services]
- dimensions [Analysis Services], member properties
- queries [MDX], attribute relationships
- user-defined hierarchies [Analysis Services]
- attributes [Analysis Services], relationships
- member properties [Analysis Services]
- members [Analysis Services], attribute relationships
- storing data [Analysis Services], attribute relationships
- relationships [Analysis Services], attributes
ms.assetid: 2491422a-4cf5-4b23-b6ab-289222b22ce8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 122638a2728a8a85ee58661196797383da20eef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681229"
---
# <a name="attribute-relationships"></a><span data-ttu-id="eb348-102">Relações de Atributo</span><span class="sxs-lookup"><span data-stu-id="eb348-102">Attribute Relationships</span></span>
  <span data-ttu-id="eb348-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , os atributos dentro de uma dimensão são sempre relacionados direta ou indiretamente ao atributo de chave.</span><span class="sxs-lookup"><span data-stu-id="eb348-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes within a dimension are always related either directly or indirectly to the key attribute.</span></span> <span data-ttu-id="eb348-104">Quando você define uma dimensão com base em um esquema em estrela, onde todos os atributos de dimensão são derivados da mesma tabela relacional, uma relação de atributo é automaticamente definida entre o atributo de chave e cada atributo não chave da dimensão.</span><span class="sxs-lookup"><span data-stu-id="eb348-104">When you define a dimension based on a star schema, which is where all dimension attributes are derived from the same relational table, an attribute relationship is automatically defined between the key attribute and each non-key attribute of the dimension.</span></span> <span data-ttu-id="eb348-105">Quando você define uma dimensão com base em um esquema de floco de neve, onde todos os atributos de dimensão derivam de várias tabelas relacionadas, uma relação de atributo é automaticamente definida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="eb348-105">When you define a dimension based on a snowflake schema, which is where dimension attributes are derived from multiple related tables, an attribute relationship is automatically defined as follows:</span></span>  
  
-   <span data-ttu-id="eb348-106">Entre o atributo de chave e cada atributo não chave vinculado às colunas na tabela de dimensões principal.</span><span class="sxs-lookup"><span data-stu-id="eb348-106">Between the key attribute and each non-key attribute bound to columns in the main dimension table.</span></span>  
  
-   <span data-ttu-id="eb348-107">Entre o atributo de chave e atributo vinculado à chave estrangeira na tabela secundária que vincula as tabelas de dimensões subjacentes.</span><span class="sxs-lookup"><span data-stu-id="eb348-107">Between the key attribute and the attribute bound to the foreign key in the secondary table that links the underlying dimension tables.</span></span>  
  
-   <span data-ttu-id="eb348-108">Entre o atributo vinculado à chave estrangeira na tabela secundária e cada atributo não chave vinculado às colunas da tabela secundária.</span><span class="sxs-lookup"><span data-stu-id="eb348-108">Between the attribute bound to foreign key in the secondary table and each non-key attribute bound to columns from the secondary table.</span></span>  
  
 <span data-ttu-id="eb348-109">Porém, há vários motivos pelos quais talvez queira alterar essas relações de atributo padrão.</span><span class="sxs-lookup"><span data-stu-id="eb348-109">However, there are a number of reasons why you might want to change these default attribute relationships.</span></span> <span data-ttu-id="eb348-110">Por exemplo, você pode querer definir uma hierarquia natural, uma ordem de classificação personalizada ou uma granularidade de dimensão com base em um atributo não chave.</span><span class="sxs-lookup"><span data-stu-id="eb348-110">For example, you might want to define a natural hierarchy, a custom sort order, or dimension granularity based on a non-key attribute.</span></span> <span data-ttu-id="eb348-111">Para obter mais informações, consulte [referência de propriedades de atributo de dimensão](../multidimensional-models/dimension-attribute-properties-reference.md).</span><span class="sxs-lookup"><span data-stu-id="eb348-111">For more information, see [Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb348-112">Relações de atributo são conhecidas em MDX como propriedades do membro.</span><span class="sxs-lookup"><span data-stu-id="eb348-112">Attribute relationships are known in Multidimensional Expressions (MDX) as member properties.</span></span>  
  
## <a name="natural-hierarchy-relationships"></a><span data-ttu-id="eb348-113">Relações de hierarquia natural</span><span class="sxs-lookup"><span data-stu-id="eb348-113">Natural Hierarchy Relationships</span></span>  
 <span data-ttu-id="eb348-114">Uma hierarquia é uma hierarquia natural quando cada atributo incluído na hierarquia definida pelo usuário possui uma relação um para muitos com o atributo imediatamente abaixo dele.</span><span class="sxs-lookup"><span data-stu-id="eb348-114">A hierarchy is a natural hierarchy when each attribute included in the user-defined hierarchy has a one to many relationship with the attribute immediately below it.</span></span> <span data-ttu-id="eb348-115">Por exemplo, considere uma dimensão Cliente com base em uma tabela fonte relacional com oito colunas:</span><span class="sxs-lookup"><span data-stu-id="eb348-115">For example, consider a Customer dimension based on a relational source table with eight columns:</span></span>  
  
-   <span data-ttu-id="eb348-116">CustomerKey</span><span class="sxs-lookup"><span data-stu-id="eb348-116">CustomerKey</span></span>  
  
-   <span data-ttu-id="eb348-117">CustomerName</span><span class="sxs-lookup"><span data-stu-id="eb348-117">CustomerName</span></span>  
  
-   <span data-ttu-id="eb348-118">Idade</span><span class="sxs-lookup"><span data-stu-id="eb348-118">Age</span></span>  
  
-   <span data-ttu-id="eb348-119">Sexo</span><span class="sxs-lookup"><span data-stu-id="eb348-119">Gender</span></span>  
  
-   <span data-ttu-id="eb348-120">Email</span><span class="sxs-lookup"><span data-stu-id="eb348-120">Email</span></span>  
  
-   <span data-ttu-id="eb348-121">City</span><span class="sxs-lookup"><span data-stu-id="eb348-121">City</span></span>  
  
-   <span data-ttu-id="eb348-122">País</span><span class="sxs-lookup"><span data-stu-id="eb348-122">Country</span></span>  
  
-   <span data-ttu-id="eb348-123">Região</span><span class="sxs-lookup"><span data-stu-id="eb348-123">Region</span></span>  
  
 <span data-ttu-id="eb348-124">A dimensão Analysis Services correspondente tem sete atributos:</span><span class="sxs-lookup"><span data-stu-id="eb348-124">The corresponding Analysis Services dimension has seven attributes:</span></span>  
  
-   <span data-ttu-id="eb348-125">Cliente (com base em CustomerKey, com CustomerName que fornece os nomes dos membros)</span><span class="sxs-lookup"><span data-stu-id="eb348-125">Customer (based on CustomerKey, with CustomerName supplying member names)</span></span>  
  
-   <span data-ttu-id="eb348-126">Idade, Sexo, Email, Cidade, Região, País</span><span class="sxs-lookup"><span data-stu-id="eb348-126">Age, Gender, Email, City, Region, Country</span></span>  
  
 <span data-ttu-id="eb348-127">As relações representando hierarquias naturais são impostas pela criação de uma relação de atributo entre o atributo para um nível e o atributo para o nível abaixo dele.</span><span class="sxs-lookup"><span data-stu-id="eb348-127">Relationships representing natural hierarchies are enforced by creating an attribute relationship between the attribute for a level and the attribute for the level below it.</span></span> <span data-ttu-id="eb348-128">Para o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], isso especifica uma relação natural e agregação de potencial.</span><span class="sxs-lookup"><span data-stu-id="eb348-128">For [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], this specifies a natural relationship and potential aggregation.</span></span> <span data-ttu-id="eb348-129">Na dimensão Cliente, uma hierarquia natural existe para os atributos País, Região, Cidade e Cliente.</span><span class="sxs-lookup"><span data-stu-id="eb348-129">In the Customer dimension, a natural hierarchy exists for the Country, Region, City, and Customer attributes.</span></span> <span data-ttu-id="eb348-130">A hierarquia natural para `{Country, Region, City, Customer}` é descrita adicionando-se as seguintes relações de atributo:</span><span class="sxs-lookup"><span data-stu-id="eb348-130">The natural hierarchy for `{Country, Region, City, Customer}` is described by adding the following attribute relationships:</span></span>  
  
-   <span data-ttu-id="eb348-131">O atributo País como uma relação com o atributo Região.</span><span class="sxs-lookup"><span data-stu-id="eb348-131">The Country attribute as an attribute relationship to the Region attribute.</span></span>  
  
-   <span data-ttu-id="eb348-132">O atributo Região como uma relação com o atributo Cidade.</span><span class="sxs-lookup"><span data-stu-id="eb348-132">The Region attribute as an attribute relationship to the City attribute.</span></span>  
  
-   <span data-ttu-id="eb348-133">O atributo Cidade como uma relação com o atributo Cliente.</span><span class="sxs-lookup"><span data-stu-id="eb348-133">The City attribute as an attribute relationship to the Customer attribute.</span></span>  
  
 <span data-ttu-id="eb348-134">Para navegar pelos dados no cubo, você também pode criar uma hierarquia definida pelo usuário que não represente uma hierarquia natural nos dados (que é chamada de hierarquia *ad hoc* ou *relatório* ).</span><span class="sxs-lookup"><span data-stu-id="eb348-134">For navigating data in the cube, you can also create a user-defined hierarchy that does not represent a natural hierarchy in the data (which is called an *ad hoc* or *reporting* hierarchy).</span></span> <span data-ttu-id="eb348-135">Por exemplo, você pode criar uma hierarquia definida pelo usuário com base em `{Age, Gender}`.</span><span class="sxs-lookup"><span data-stu-id="eb348-135">For example, you could create a user-defined hierarchy based on `{Age, Gender}`.</span></span> <span data-ttu-id="eb348-136">Os usuários não veem nenhuma diferença em como as duas hierarquias se comportam, embora a hierarquia natural se beneficie das estruturas de agregação e indexação – ocultas do usuário-essa conta para as relações naturais nos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="eb348-136">Users do not see any difference in how the two hierarchies behave, although the natural hierarchy benefits from aggregating and indexing structures - hidden from the user - that account for the natural relationships in the source data.</span></span>  
  
 <span data-ttu-id="eb348-137">A propriedade `SourceAttribute` de um nível determina qual atributo é usado para descrever o nível.</span><span class="sxs-lookup"><span data-stu-id="eb348-137">The `SourceAttribute` property of a level determines which attribute is used to describe the level.</span></span> <span data-ttu-id="eb348-138">A propriedade `KeyColumns` no atributo especifica a coluna na exibição da fonte de dados que fornece os membros.</span><span class="sxs-lookup"><span data-stu-id="eb348-138">The `KeyColumns` property on the attribute specifies the column in the data source view that supplies the members.</span></span> <span data-ttu-id="eb348-139">A propriedade `NameColumn` no atributo pode especificar um nome de coluna diferente para os membros.</span><span class="sxs-lookup"><span data-stu-id="eb348-139">The `NameColumn` property on the attribute can specify a different name column for the members.</span></span>  
  
 <span data-ttu-id="eb348-140">Para definir um nível em uma hierarquia definida pelo usuário usando [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , o **Designer de dimensão** permite que você selecione um atributo de dimensão, uma coluna em uma tabela de dimensão ou uma coluna de uma tabela relacionada incluída na exibição da fonte de dados para o cubo.</span><span class="sxs-lookup"><span data-stu-id="eb348-140">To define a level in a user-defined hierarchy using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the **Dimension Designer** allows you to select a dimension attribute, a column in a dimension table, or a column from a related table included in the data source view for the cube.</span></span> <span data-ttu-id="eb348-141">Para obter mais informações sobre como criar hierarquias definidas pelo usuário, consulte [criar hierarquias definidas pelo usuário](../multidimensional-models/user-defined-hierarchies-create.md).</span><span class="sxs-lookup"><span data-stu-id="eb348-141">For more information about creating user-defined hierarchies, see [Create User-Defined Hierarchies](../multidimensional-models/user-defined-hierarchies-create.md).</span></span>  
  
 <span data-ttu-id="eb348-142">No Analysis Services, uma suposição é normalmente feita sobre o conteúdo dos membros.</span><span class="sxs-lookup"><span data-stu-id="eb348-142">In Analysis Services, an assumption is usually made about the content of members.</span></span> <span data-ttu-id="eb348-143">Os membros folha não têm nenhum descendente e contêm dados derivados de fontes de dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="eb348-143">Leaf members have no descendents and contain data derived from underlying data sources.</span></span> <span data-ttu-id="eb348-144">Os membros não folha têm descendentes e contêm dados derivados de agregações executadas em membros filhos.</span><span class="sxs-lookup"><span data-stu-id="eb348-144">Nonleaf members have descendents and contain data derived from aggregations performed on child members.</span></span> <span data-ttu-id="eb348-145">Em níveis de agregação, os membros são com base em agregações de níveis subordinados.</span><span class="sxs-lookup"><span data-stu-id="eb348-145">In aggregated levels, members are based on aggregations of subordinate levels.</span></span> <span data-ttu-id="eb348-146">Portanto, quando a propriedade `IsAggregatable` estiver configurada como `False` no atributo de origem de um nível, nenhum atributo agregável poderá ser adicionado como nível acima dele.</span><span class="sxs-lookup"><span data-stu-id="eb348-146">Therefore, when the `IsAggregatable` property is set to `False` on a source attribute for a level, no aggregatable attributes should be added as levels above it.</span></span>  
  
## <a name="defining-an-attribute-relationship"></a><span data-ttu-id="eb348-147">Definindo uma relação de atributo</span><span class="sxs-lookup"><span data-stu-id="eb348-147">Defining an Attribute Relationship</span></span>  
 <span data-ttu-id="eb348-148">A principal restrição ao criar uma relação de atributo é certificar-se de que o atributo referenciado pela relação de atributo, não possui mais que um valor para qualquer membro no atributo ao qual a relação de atributo pertence.</span><span class="sxs-lookup"><span data-stu-id="eb348-148">The main constraint when you create an attribute relationship is to make sure that the attribute referred to by the attribute relationship has no more than one value for any member in the attribute to which the attribute relationship belongs.</span></span> <span data-ttu-id="eb348-149">Por exemplo, se você definir uma relação entre um atributo Cidade e um atributo Estado, cada cidade pode apenas estar relacionada a um único estado.</span><span class="sxs-lookup"><span data-stu-id="eb348-149">For example, if you define a relationship between a City attribute and a State attribute, each city can only relate to a single state.</span></span>  
  
## <a name="attribute-relationship-queries"></a><span data-ttu-id="eb348-150">Consultas de relação de atributo</span><span class="sxs-lookup"><span data-stu-id="eb348-150">Attribute Relationship Queries</span></span>  
 <span data-ttu-id="eb348-151">Você pode usar consultas MDX para recuperar dados de relações de atributo, na forma de propriedades de membro com a palavra-chave `PROPERTIES` da instrução MDX `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="eb348-151">You can use MDX queries to retrieve data from attribute relationships, in the form of member properties, with the `PROPERTIES` keyword of the MDX `SELECT` statement.</span></span> <span data-ttu-id="eb348-152">Para obter mais informações sobre como usar o MDX para recuperar propriedades do membro, consulte [usando propriedades do membro &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="eb348-152">For more information about how to use MDX to retrieve member properties, see [Using Member Properties &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb348-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb348-153">See Also</span></span>  
 <span data-ttu-id="eb348-154">[Atributos e hierarquias de atributo](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="eb348-154">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="eb348-155">[Referência de propriedades de atributo de dimensão](../multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="eb348-155">[Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="eb348-156">[Hierarquias de usuário](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="eb348-156">[User Hierarchies](user-hierarchies.md) </span></span>  
 [<span data-ttu-id="eb348-157">Propriedades de hierarquia do usuário</span><span class="sxs-lookup"><span data-stu-id="eb348-157">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
