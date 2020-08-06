---
title: Configurar propriedades da medida | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- additivity [Analysis Services]
- ID property
- ErrorConfiguration property
- AggregateFunction property
- DisplayFolder property
- IgnoreUnrelatedDimensions property
- FormatString property
- Description property
- semiadditive
- properties [Analysis Services], measure groups
- aggregate functions [Analysis Services]
- DataType property
- ProcessingMode property
- MeasureExpression property
- AggregationPrefix property
- Visible property
- properties [Analysis Services], measures
- StorageLocation property
- StorageMode property
- formats [Analysis Services], measures
- Source property
- aggregations [Analysis Services], measures
- measures [Analysis Services], properties
- nonadditive [Analysis Services]
- Name property
- measures [Analysis Services], display formats
- ProcessingPriority property
- measure groups [Analysis Services], properties
- Type property
- ProactiveCaching property
ms.assetid: e9031078-c4f5-4986-b0c9-4d064b622ab7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ca291a5181fdb3f7a88845431d61ffd7a1034eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683790"
---
# <a name="configure-measure-properties"></a><span data-ttu-id="63a8a-102">Configurar propriedades de medida</span><span class="sxs-lookup"><span data-stu-id="63a8a-102">Configure Measure Properties</span></span>
  <span data-ttu-id="63a8a-103">As medidas têm propriedades que lhe permitem definir como elas funcionam e controlar como elas aparecem para os usuários.</span><span class="sxs-lookup"><span data-stu-id="63a8a-103">Measures have properties that enable you to define how the measures function and to control how the measures appear to users.</span></span>  
  
 <span data-ttu-id="63a8a-104">Você pode definir propriedades em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ao criar ou editar um cubo ou uma medida.</span><span class="sxs-lookup"><span data-stu-id="63a8a-104">You can set properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] when creating or editing a cube or measure.</span></span> <span data-ttu-id="63a8a-105">Você pode também defini-las programaticamente, usando MDX ou AMO.</span><span class="sxs-lookup"><span data-stu-id="63a8a-105">You can also set them programmatically, using MDX or AMO.</span></span> <span data-ttu-id="63a8a-106">Consulte [Criar medidas e grupos de medidas em modelos multidimensionais](create-measures-and-measure-groups-in-multidimensional-models.md) ou [Instrução CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) ou [Programando objetos OLAP AMO básicos](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="63a8a-106">See [Create Measures and Measure Groups in Multidimensional Models](create-measures-and-measure-groups-in-multidimensional-models.md) or [CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) or [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects) for details.</span></span>  
  
## <a name="measure-properties"></a><span data-ttu-id="63a8a-107">Propriedades das medidas</span><span class="sxs-lookup"><span data-stu-id="63a8a-107">Measure Properties</span></span>  
 <span data-ttu-id="63a8a-108">As medidas herdam certas propriedades do grupo de medidas do qual fazem parte, exceto se essas propriedades forem substituídas no nível da medida.</span><span class="sxs-lookup"><span data-stu-id="63a8a-108">Measures inherit certain properties from the measure group of which they are a member, unless those properties are overridden at the measure level.</span></span> <span data-ttu-id="63a8a-109">As propriedades das medidas determinam como uma medida é agregada, seu tipo de dados, o nome exibido ao usuário, a pasta de exibição na qual a medida aparecerá, sua cadeia de caracteres de formato, qualquer expressão de medida, a coluna de origem subjacente e sua visibilidade aos usuários.</span><span class="sxs-lookup"><span data-stu-id="63a8a-109">Measure properties determine how a measure is aggregated, its data type, the name that is displayed to the user, the display folder in which the measure will appear, its format string, any measure expression, the underlying source column, and its visibility to users.</span></span>  
  
|<span data-ttu-id="63a8a-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="63a8a-110">Property</span></span>|<span data-ttu-id="63a8a-111">Definição</span><span class="sxs-lookup"><span data-stu-id="63a8a-111">Definition</span></span>|  
|--------------|----------------|  
|`AggregateFunction`|<span data-ttu-id="63a8a-112">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="63a8a-112">Required.</span></span> <span data-ttu-id="63a8a-113">Determina como as medidas são agregadas.</span><span class="sxs-lookup"><span data-stu-id="63a8a-113">Determines how measures are aggregated.</span></span> <span data-ttu-id="63a8a-114">`Sum` é a agregação padrão.</span><span class="sxs-lookup"><span data-stu-id="63a8a-114">`Sum` is the default aggregation.</span></span> <span data-ttu-id="63a8a-115">Para obter mais informações, consulte [Usar funções de agregação](use-aggregate-functions.md) para obter uma descrição de cada função.</span><span class="sxs-lookup"><span data-stu-id="63a8a-115">For more information, see [Use Aggregate Functions](use-aggregate-functions.md) for a description of each function.</span></span>|  
|`DataType`|<span data-ttu-id="63a8a-116">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="63a8a-116">Required.</span></span> <span data-ttu-id="63a8a-117">Especifica o tipo de dados da coluna da tabela de fatos subjacente à qual a medida está associada.</span><span class="sxs-lookup"><span data-stu-id="63a8a-117">Specifies the data type of the column in the underlying fact table to which the measure is bound.</span></span> <span data-ttu-id="63a8a-118">Esse valor é herdado da coluna de origem por padrão.</span><span class="sxs-lookup"><span data-stu-id="63a8a-118">This value is inherited from the source column by default.</span></span>|  
|`Description`|<span data-ttu-id="63a8a-119">Fornece uma descrição da medida, que pode ser exposta em aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="63a8a-119">Provides a description of the measure, which may be exposed in client applications.</span></span>|  
|`DisplayFolder`|<span data-ttu-id="63a8a-120">Especifica a pasta na qual a medida aparecerá quando os usuários conectarem-se ao cubo.</span><span class="sxs-lookup"><span data-stu-id="63a8a-120">Specifies the folder in which the measure will appear when users connect to the cube.</span></span> <span data-ttu-id="63a8a-121">Se o cubo tiver várias medidas, você pode usar as pastas de exibição para categorizar as medidas e aprimorar a experiência de navegação do usuário.</span><span class="sxs-lookup"><span data-stu-id="63a8a-121">When a cube has many measures, you can use display folders to categorize the measures and improve the user browsing experience.</span></span>|  
|`FormatString`|<span data-ttu-id="63a8a-122">Você pode selecionar o formato usado para exibir valores de medida aos usuários utilizando a propriedade `FormatString` da medida.</span><span class="sxs-lookup"><span data-stu-id="63a8a-122">You can select the format that is used to display measure values to users by using the `FormatString` property of the measure.</span></span><br /><br /> <span data-ttu-id="63a8a-123">Embora seja fornecida uma lista de formatos de exibição em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], você pode especificar vários outros formatos que não constam nela.</span><span class="sxs-lookup"><span data-stu-id="63a8a-123">Although a list of display formats is provided in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can specify many additional formats that are not in the list.</span></span> <span data-ttu-id="63a8a-124">Você pode especificar qualquer formato nomeado ou definido pelo usuário que seja válido no Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63a8a-124">You can specify any named or user-defined format that is valid in Microsoft Visual Basic.</span></span>|  
|`ID`|<span data-ttu-id="63a8a-125">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="63a8a-125">Required.</span></span> <span data-ttu-id="63a8a-126">Exibe o identificador exclusivo (ID) da medida.</span><span class="sxs-lookup"><span data-stu-id="63a8a-126">Displays the unique identifier (ID) of the measure.</span></span> <span data-ttu-id="63a8a-127">Esta propriedade é somente para leitura.</span><span class="sxs-lookup"><span data-stu-id="63a8a-127">This property is read-only.</span></span>|  
|`MeasureExpression`|<span data-ttu-id="63a8a-128">Especifica uma expressão MDX restrita definindo o valor da medida.</span><span class="sxs-lookup"><span data-stu-id="63a8a-128">Specifies a constrained MDX expression defining the value of the measure.</span></span> <span data-ttu-id="63a8a-129">A expressão é avaliada no nível de folha antes de ser agregada e leva em consideração a importância de um valor.</span><span class="sxs-lookup"><span data-stu-id="63a8a-129">The expression is evaluated at the leaf level before being aggregated, and allows for weighting of a value.</span></span> <span data-ttu-id="63a8a-130">Por exemplo, em conversão de moedas em que um valor de vendas é ponderado pela taxa de câmbio.</span><span class="sxs-lookup"><span data-stu-id="63a8a-130">For example, in currency conversion where a sales amount is weighted by the exchange rate.</span></span>|  
|`Name`|<span data-ttu-id="63a8a-131">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="63a8a-131">Required.</span></span> <span data-ttu-id="63a8a-132">Especifica o nome da medida.</span><span class="sxs-lookup"><span data-stu-id="63a8a-132">Specifies the name of the measure.</span></span>|  
|`Source`|<span data-ttu-id="63a8a-133">Obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="63a8a-133">Required.</span></span> <span data-ttu-id="63a8a-134">Especifica a coluna da exibição da fonte de dados à qual a medida está associada.</span><span class="sxs-lookup"><span data-stu-id="63a8a-134">Specifies the column in the data source view to which the measure is bound.</span></span> <span data-ttu-id="63a8a-135">Consulte [Fontes de dados e associações &#40;SSAS Multidimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="63a8a-135">See [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span></span>|  
|`Visible`|<span data-ttu-id="63a8a-136">Determina a visibilidade da medida em aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="63a8a-136">Determines the visibility of the measure in client applications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63a8a-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63a8a-137">See Also</span></span>  
 <span data-ttu-id="63a8a-138">[Configurar propriedades do grupo de medidas](configure-measure-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="63a8a-138">[Configure Measure Group Properties](configure-measure-group-properties.md) </span></span>  
 [<span data-ttu-id="63a8a-139">Modificando medidas</span><span class="sxs-lookup"><span data-stu-id="63a8a-139">Modifying Measures</span></span>](../lesson-3-1-modifying-measures.md)  
  
  
