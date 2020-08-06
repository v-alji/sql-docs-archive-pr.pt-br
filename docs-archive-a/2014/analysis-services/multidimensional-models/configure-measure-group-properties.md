---
title: Configurar propriedades do grupo de medidas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- properties [Analysis Services], measure groups
ms.assetid: fa66bdb6-60b8-413c-ac2a-00e4d09f60a2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 03dad3d8ee33ea8a78b08f9a354d0db3d177198c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683791"
---
# <a name="configure-measure-group-properties"></a><span data-ttu-id="6e310-102">Configurar propriedades do grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="6e310-102">Configure Measure Group Properties</span></span>
  <span data-ttu-id="6e310-103">Os grupos de medidas têm propriedades que lhe permitem definir como eles funcionam.</span><span class="sxs-lookup"><span data-stu-id="6e310-103">Measures groups have properties that enable you to define how measure groups function.</span></span>  
  
## <a name="measure-group-properties"></a><span data-ttu-id="6e310-104">Propriedades do grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="6e310-104">Measure Group Properties</span></span>  
 <span data-ttu-id="6e310-105">As propriedades do grupo de medidas determinam o comportamento de todo o grupo de medidas e definem o comportamento padrão de determinadas propriedades das medidas de um grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="6e310-105">Measure group properties determine behaviors for the entire measure group and set the default behaviors for certain properties of measures within a measure group.</span></span>  
  
|<span data-ttu-id="6e310-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="6e310-106">Property</span></span>|<span data-ttu-id="6e310-107">Definição</span><span class="sxs-lookup"><span data-stu-id="6e310-107">Definition</span></span>|  
|--------------|----------------|  
|`AggregationPrefix`|<span data-ttu-id="6e310-108">Aplica-se ao armazenamento ROLAP.</span><span class="sxs-lookup"><span data-stu-id="6e310-108">Applies to ROLAP storage.</span></span> <span data-ttu-id="6e310-109">Atribui um prefixo comum às exibições indexadas no SQL Server, usado para armazenar agregações para as partições associadas a esse grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="6e310-109">Assigns a common prefix to the indexed views in SQL Server, used to store aggregations for the partitions associated with this measure group.</span></span>|  
|`DataAggregation`|<span data-ttu-id="6e310-110">Essa propriedade é reservada para uso futuro e atualmente não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="6e310-110">This property is reserved for future use and currently has no effect.</span></span> <span data-ttu-id="6e310-111">Portanto, é recomendável que você não modifique essa configuração.</span><span class="sxs-lookup"><span data-stu-id="6e310-111">Therefore, it is recommended that you do not modify this setting.</span></span>|  
|`Description`|<span data-ttu-id="6e310-112">Você pode usar essa propriedade para documentar o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="6e310-112">You can use this property to document the measure group.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="6e310-113">As definições configuráveis de tratamento de erros para tratamento de chaves duplicadas, chaves desconhecidas, chaves nulas, limites de erro, ação devido à detecção de erros, arquivo de log de erros.</span><span class="sxs-lookup"><span data-stu-id="6e310-113">Configurable error handling settings for handling of duplicate keys, unknown keys, null keys, error limits, action upon error detection, and the error log file.</span></span> <span data-ttu-id="6e310-114">Consulte [Configuração de erros para cubo, partição e processamento da dimensão &#40;SSAS – multidimensional&#41;](error-configuration-for-cube-partition-and-dimension-processing.md).</span><span class="sxs-lookup"><span data-stu-id="6e310-114">See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](error-configuration-for-cube-partition-and-dimension-processing.md).</span></span>|  
|`EstimatedRows`|<span data-ttu-id="6e310-115">Especifica o número de linhas estimado da tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="6e310-115">Specifies the estimated number of rows in the fact table.</span></span>|  
|`EstimatedSize`|<span data-ttu-id="6e310-116">Especifica o tamanho estimado (em bytes) do grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="6e310-116">Specifies the estimated size (in bytes) of the measure group.</span></span>|  
|`ID`|<span data-ttu-id="6e310-117">Especifica o identificador do objeto.</span><span class="sxs-lookup"><span data-stu-id="6e310-117">Specifies the identifier of the object.</span></span>|  
|`IgnoreUnrelatedDimensions`|<span data-ttu-id="6e310-118">Determina se as dimensão não relacionadas são forçadas para seu nível superior quando os membros das dimensões que não estão relacionados ao grupo de medidas são incluídos em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="6e310-118">Determines whether unrelated dimensions are forced to their top level when members of dimensions that are unrelated to the measure group are included in a query.</span></span> <span data-ttu-id="6e310-119">A configuração padrão é `True` .</span><span class="sxs-lookup"><span data-stu-id="6e310-119">Default setting is `True`.</span></span>|  
|`Name`|<span data-ttu-id="6e310-120">Nome da medida.</span><span class="sxs-lookup"><span data-stu-id="6e310-120">Name of the measure.</span></span> <span data-ttu-id="6e310-121">Esta propriedade é somente para leitura.</span><span class="sxs-lookup"><span data-stu-id="6e310-121">This property is read-only.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="6e310-122">As definições configuráveis de tratamento de erros para tratamento de chaves duplicadas, chaves desconhecidas, chaves nulas, limites de erro, ação devido à detecção de erros, arquivo de log de erros.</span><span class="sxs-lookup"><span data-stu-id="6e310-122">Configurable error handling settings for handling of duplicate keys, unknown keys, null keys, error limits, action upon error detection, and the error log file.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="6e310-123">Indica se a indexação e a agregação devem ocorrer durante ou após o processamento.</span><span class="sxs-lookup"><span data-stu-id="6e310-123">Indicates whether indexing and aggregating should occur during or after processing.</span></span> <span data-ttu-id="6e310-124">As opções são Regular e LazyAggregations.</span><span class="sxs-lookup"><span data-stu-id="6e310-124">Options are Regular and LazyAggregations.</span></span> <span data-ttu-id="6e310-125">LazyAggregations pode ser usado para executar a agregação como uma tarefa em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6e310-125">LazyAggregations can be used to run aggregation as a background task.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="6e310-126">Determina a prioridade de processamento do cubo durante as operações em segundo plano, como agregações lentas e indexação.</span><span class="sxs-lookup"><span data-stu-id="6e310-126">Determines the processing priority of the cube during background operations, such as lazy aggregations and indexing.</span></span> <span data-ttu-id="6e310-127">O valor padrão é **0**.</span><span class="sxs-lookup"><span data-stu-id="6e310-127">The default value is **0**.</span></span>|  
|`StorageLocation`|<span data-ttu-id="6e310-128">O local de armazenamento do sistema de arquivos para o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="6e310-128">The file system storage location for the measure group.</span></span> <span data-ttu-id="6e310-129">Se nenhum for especificado, o local será herdado do cubo que contém o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="6e310-129">If none is specified, the location is inherited from the cube that contains the measure group.</span></span>|  
|`StorageMode`|<span data-ttu-id="6e310-130">O modo de armazenamento para o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="6e310-130">The storage mode for the measure group.</span></span> <span data-ttu-id="6e310-131">Os valores disponíveis são MOLAP, ROLAP ou HOLAP.</span><span class="sxs-lookup"><span data-stu-id="6e310-131">Available values are MOLAP, ROLAP, or HOLAP.</span></span>|  
|`Type`|<span data-ttu-id="6e310-132">Especifica o tipo do grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="6e310-132">Specifies the type of the measure group.</span></span>|  
  
  
