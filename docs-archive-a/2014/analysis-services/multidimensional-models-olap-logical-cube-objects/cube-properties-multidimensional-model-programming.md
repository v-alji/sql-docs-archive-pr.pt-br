---
title: Propriedades do cubo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Collation property
- ID property
- ErrorConfiguration property
- cubes [Analysis Services], properties
- Description property
- DefaultMeasure property
- ProcessingMode property
- AggregationPrefix property
- EstimatedRows property
- Visible property
- StorageLocation property
- StorageMode property
- ScriptErrorHandlingMode property
- Source property
- ScriptCacheProcessingMode property
- Language property
- Name property
- properties [Analysis Services], cubes
- ProcessingPriority property
- ProactiveCaching property
ms.assetid: 72ca3387-620d-4473-8e23-7fe1f2b3d5bf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 27d4202774107795eaddf76c27e21010d534d977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570314"
---
# <a name="cube-properties"></a><span data-ttu-id="60b7e-102">Propriedades do cubo</span><span class="sxs-lookup"><span data-stu-id="60b7e-102">Cube Properties</span></span>
  <span data-ttu-id="60b7e-103">Os cubos têm várias propriedades que você pode definir para afetar o comportamento de todo o cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-103">Cubes have a number of properties that you can set to affect cube-wide behavior.</span></span> <span data-ttu-id="60b7e-104">Essas propriedades são resumidas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="60b7e-104">These properties are summarized in the following table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60b7e-105">Algumas propriedades são definidas automaticamente na criação do cubo e não podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="60b7e-105">Some properties are set automatically when the cube is created and cannot be changed.</span></span>  
  
 <span data-ttu-id="60b7e-106">Para obter mais informações sobre como definir propriedades de cubo, consulte [Designer de cubo &#40;Analysis Services&#41;de dados multidimensionais ](../cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="60b7e-106">For more information about how to set cube properties, see [Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
|<span data-ttu-id="60b7e-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="60b7e-107">Property</span></span>|<span data-ttu-id="60b7e-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="60b7e-108">Description</span></span>|  
|--------------|-----------------|  
|`AggregationPrefix`|<span data-ttu-id="60b7e-109">Especifica o prefixo comum usado para nomes de agregação.</span><span class="sxs-lookup"><span data-stu-id="60b7e-109">Specifies the common prefix that is used for aggregation names.</span></span>|  
|`Collation`|<span data-ttu-id="60b7e-110">Especifica o identificador de localidade (LCID) e o sinalizador de comparação, separados por um sublinhado: por exemplo, Latin1_General_C1_AS.</span><span class="sxs-lookup"><span data-stu-id="60b7e-110">Specifies the locale identifier (LCID) and the comparison flag, separated by an underscore: for example, Latin1_General_C1_AS.</span></span>|  
|`DefaultMeasure`|<span data-ttu-id="60b7e-111">Contém uma linguagem MDX que define a medida padrão para o cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-111">Contains a Multidimensional Expressions (MDX) expression that defines the default measure for the cube.</span></span>|  
|`Description`|<span data-ttu-id="60b7e-112">Fornece uma descrição do cubo que pode ser exposta em aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="60b7e-112">Provides a description of the cube, which may be exposed in client applications.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="60b7e-113">Contêm configurações de tratamento de erros que podem ser definidas para tratar chaves duplicadas, chaves desconhecidas, limites de erros, ação devido à detecção de erros, arquivo de log de erros e tratamento de chaves nulas.</span><span class="sxs-lookup"><span data-stu-id="60b7e-113">Contains configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`EstimatedRows`|<span data-ttu-id="60b7e-114">Especifica o número de linhas estimadas no cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-114">Specifies the number of estimated rows in the cube.</span></span>|  
|`ID`|<span data-ttu-id="60b7e-115">Contém o identificador exclusivo (ID) do cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-115">Contains the unique identifier (ID) of the cube.</span></span>|  
|`Language`|<span data-ttu-id="60b7e-116">Especifica o identificador de idioma padrão do cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-116">Specifies the default language identifier of the cube.</span></span>|  
|`Name`|<span data-ttu-id="60b7e-117">Especifica o nome amigável do cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-117">Specifies the user-friendly name of the cube.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="60b7e-118">Define configurações de cache pró-ativas para o cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-118">Defines proactive cache settings for the cube.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="60b7e-119">Indica se a indexação e a agregação devem ocorrer durante ou após o processamento.</span><span class="sxs-lookup"><span data-stu-id="60b7e-119">Indicates whether indexing and aggregating should occur during or after processing.</span></span> <span data-ttu-id="60b7e-120">As opções são **regular** ou `lazy` .</span><span class="sxs-lookup"><span data-stu-id="60b7e-120">Options are **regular** or `lazy`.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="60b7e-121">Determina a prioridade de processamento do cubo durante as operações em segundo plano, como agregações lentas e indexação.</span><span class="sxs-lookup"><span data-stu-id="60b7e-121">Determines the processing priority of the cube during background operations, such as lazy aggregations and indexing.</span></span> <span data-ttu-id="60b7e-122">O valor padrão é **0**.</span><span class="sxs-lookup"><span data-stu-id="60b7e-122">The default value is **0**.</span></span>|  
|`ScriptCacheProcessingMode`|<span data-ttu-id="60b7e-123">Indica se o cache de script deve ser criado durante ou após o processamento.</span><span class="sxs-lookup"><span data-stu-id="60b7e-123">Indicates whether the script cache should be built during or after processing.</span></span> <span data-ttu-id="60b7e-124">As opções são **regular** e `lazy` .</span><span class="sxs-lookup"><span data-stu-id="60b7e-124">Options are **regular** and `lazy`.</span></span>|  
|`ScriptErrorHandlingMode`|<span data-ttu-id="60b7e-125">Determina o tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="60b7e-125">Determines error handling.</span></span> <span data-ttu-id="60b7e-126">As opções são `IgnoreNone` ou`IgnoreAll`</span><span class="sxs-lookup"><span data-stu-id="60b7e-126">Options are `IgnoreNone` or `IgnoreAll`</span></span>|  
|`Source`|<span data-ttu-id="60b7e-127">Mostra a exibição da fonte de dados usada para o cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-127">Displays the data source view used for the cube.</span></span>|  
|`StorageLocation`|<span data-ttu-id="60b7e-128">Especifica o local de armazenamento do sistema de arquivos para o cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-128">Specifies the file system storage location for the cube.</span></span> <span data-ttu-id="60b7e-129">Se nenhum for especificado, o local será herdado do banco de dados que contém o objeto de cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-129">If none is specified, the location is inherited from the database that contains the cube object.</span></span>|  
|`StorageMode`|<span data-ttu-id="60b7e-130">Especifica o modo de armazenamento para o cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-130">Specifies the storage mode for the cube.</span></span> <span data-ttu-id="60b7e-131">Os valores são `MOLAP` , `ROLAP` ou`HOLAP``.`</span><span class="sxs-lookup"><span data-stu-id="60b7e-131">Values are `MOLAP`, `ROLAP`, or `HOLAP``.`</span></span>|  
|`Visible`|<span data-ttu-id="60b7e-132">Determina a visibilidade do cubo.</span><span class="sxs-lookup"><span data-stu-id="60b7e-132">Determines the visibility of the cube.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="60b7e-133">Para obter mais informações sobre como definir valores para a Propriedade ErrorConfiguration ao trabalhar com valores nulos e outros problemas de integridade de dados, consulte [tratamento de problemas de integridade de dados no Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="60b7e-133">For more information about setting values for the ErrorConfiguration property when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b7e-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60b7e-134">See Also</span></span>  
 [<span data-ttu-id="60b7e-135">Cache pró-ativo &#40;partições&#41;</span><span class="sxs-lookup"><span data-stu-id="60b7e-135">Proactive Caching &#40;Partitions&#41;</span></span>](partitions-proactive-caching.md)  
  
  
