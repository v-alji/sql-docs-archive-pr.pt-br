---
title: Propriedades da dimensão do banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- metadata [Analysis Services]
- dimensions [Analysis Services], characteristics
- properties [Analysis Services], dimensions
ms.assetid: 075548ef-08a3-413c-8ee0-4a074c276fcc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 504e190f4c513a8c999c4d7d7ab9eaabb83298c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576034"
---
# <a name="database-dimension-properties"></a><span data-ttu-id="c9064-102">Propriedades de dimensão do banco de dados</span><span class="sxs-lookup"><span data-stu-id="c9064-102">Database Dimension Properties</span></span>
  <span data-ttu-id="c9064-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , as características de uma dimensão são definidas pelos metadados da dimensão, com base nas configurações de várias propriedades de dimensão e nos atributos ou hierarquias contidos na dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the characteristics of a dimension are defined by the metadata for the dimension, based on the settings of various dimension properties, and on the attributes or hierarchies that are contained by the dimension.</span></span> <span data-ttu-id="c9064-104">A tabela a seguir descreve as propriedades de dimensão no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9064-104">The following table describes the dimension properties in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="c9064-105">Propriedade</span><span class="sxs-lookup"><span data-stu-id="c9064-105">Property</span></span>|<span data-ttu-id="c9064-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9064-106">Description</span></span>|  
|--------------|-----------------|  
|`AttributeAllMemberName`|<span data-ttu-id="c9064-107">Especifica o nome de todos os membros para atributos em uma dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-107">Specifies the name of the All member for attributes in a dimension.</span></span>|  
|`Collation`|<span data-ttu-id="c9064-108">Determina a ordenação usada pela dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-108">Determines the collation used by the dimension.</span></span>|  
|`CurrentStorageMode`|<span data-ttu-id="c9064-109">Contém o modo de armazenamento atual para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-109">Contains the current storage mode for the dimension.</span></span>|  
|`DependsOnDimension`|<span data-ttu-id="c9064-110">Contém o ID de outra dimensão da qual a dimensão depende, se houver.</span><span class="sxs-lookup"><span data-stu-id="c9064-110">Contains the ID of another dimension on which the dimension depends, if any.</span></span>|  
|`Description`|<span data-ttu-id="c9064-111">Contém a descrição da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-111">Contains the description of the dimension.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="c9064-112">Contém definições configuráveis de tratamento de erros para tratamento de chaves duplicadas, chaves desconhecidas, limites de erro, ação devido à detecção de erros, arquivo de log de erros e tratamento de chaves nulas.</span><span class="sxs-lookup"><span data-stu-id="c9064-112">Configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`ID`|<span data-ttu-id="c9064-113">Contém o identificador exclusivo (ID) da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-113">Contains the unique identifier (ID) of the dimension.</span></span>|  
|`Language`|<span data-ttu-id="c9064-114">Especifica o idioma padrão para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-114">Specifies the default language for the dimension.</span></span>|  
|`MdxMissingMemberMode`|<span data-ttu-id="c9064-115">Determina como são tratados membros ausentes para linguagens MDX.</span><span class="sxs-lookup"><span data-stu-id="c9064-115">Determines how missing members are handled for Multidimensional Expressions (MDX) statements.</span></span>|  
|`MiningModelID`|<span data-ttu-id="c9064-116">Contém o ID do modelo de mineração com o qual a dimensão de mineração de dados está associada.</span><span class="sxs-lookup"><span data-stu-id="c9064-116">Contains the ID of the mining model with which the data mining dimension is associated.</span></span> <span data-ttu-id="c9064-117">Essa propriedade só será aplicável se a dimensão for uma dimensão de modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="c9064-117">This property is applicable only if the dimension is a mining model dimension.</span></span>|  
|`Name`|<span data-ttu-id="c9064-118">Especifica o nome da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-118">Specifies the name of the dimension.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="c9064-119">Define configurações de cache pró-ativas para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-119">Defines the proactive cache settings for the dimension.</span></span>|  
|`ProcessingGroup`|<span data-ttu-id="c9064-120">Especifica o grupo de processamento.</span><span class="sxs-lookup"><span data-stu-id="c9064-120">Specifies the processing group.</span></span> <span data-ttu-id="c9064-121">Os valores são ByAttribute ou ByTable.</span><span class="sxs-lookup"><span data-stu-id="c9064-121">Values are ByAttribute or ByTable.</span></span> <span data-ttu-id="c9064-122">O padrão é `ByAttribute`.</span><span class="sxs-lookup"><span data-stu-id="c9064-122">Default is `ByAttribute`.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="c9064-123">Indica se o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deve fazer indexação e agregação durante ou após o processamento.</span><span class="sxs-lookup"><span data-stu-id="c9064-123">Indicates whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should index and aggregate during or after processing.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="c9064-124">Determina a prioridade de processamento da dimensão durante as operações em segundo plano, como agregações lentas, indexação ou cluster.</span><span class="sxs-lookup"><span data-stu-id="c9064-124">Determines the processing priority of the dimension during background operations such as lazy aggregation, indexing, or clustering.</span></span>|  
|`Source`|<span data-ttu-id="c9064-125">Identifica a exibição da fonte de dados à qual a dimensão está associada.</span><span class="sxs-lookup"><span data-stu-id="c9064-125">Identifies the data source view to which the dimension is bound.</span></span>|  
|`StorageMode`|<span data-ttu-id="c9064-126">Determina o modo de armazenamento da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-126">Determines the storage mode for the dimension.</span></span>|  
|`Type`|<span data-ttu-id="c9064-127">Especifica o tipo da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-127">Specifies the type of the dimension.</span></span>|  
|`UnknownMember`|<span data-ttu-id="c9064-128">Indica se o membro desconhecido é visível.</span><span class="sxs-lookup"><span data-stu-id="c9064-128">Indicates whether the unknown member is visible.</span></span>|  
|`UnknownMemberName`|<span data-ttu-id="c9064-129">Especifica a legenda, no idioma padrão da dimensão, para o membro desconhecido da dimensão.</span><span class="sxs-lookup"><span data-stu-id="c9064-129">Specifies the caption, in the default language of the dimension, for the unknown member of the dimension.</span></span>|  
|`WriteEnabled`|<span data-ttu-id="c9064-130">Indica se write-backs de dimensão estão disponíveis (sujeito a permissões de segurança).</span><span class="sxs-lookup"><span data-stu-id="c9064-130">Indicates whether dimension writebacks are available (subject to security permissions).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="c9064-131">Para obter mais informações sobre como definir valores para as propriedades ErrorConfiguration e UnknownMember ao trabalhar com valores nulos e outros problemas de integridade de dados, consulte [tratamento de problemas de integridade de dados no Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="c9064-131">For more information about setting values for the ErrorConfiguration and UnknownMember properties when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9064-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9064-132">See Also</span></span>  
 <span data-ttu-id="c9064-133">[Atributos e hierarquias de atributo](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="c9064-133">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="c9064-134">[Hierarquias de usuário](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="c9064-134">[User Hierarchies](user-hierarchies.md) </span></span>  
 <span data-ttu-id="c9064-135">[Relações de dimensão](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="c9064-135">[Dimension Relationships](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 [<span data-ttu-id="c9064-136">Dimensões &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="c9064-136">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
