---
title: Propriedades OLAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- AggregationPerfLog property
- DefaultPageSizeForProp property
- UseSinglePassForDimSecurityAutoExist property
- DeepCompressValue property
- CacheRowsetRows property
- Income property
- AggregationNewAlgo property
- MemoryAdjustFactor property
- DimensionLatencyAccuracy property
- InitialBonus property
- DefaultPageSizeForDataHeader property
- MaxCPUUsage property
- DistinctBuffer property
- PartitionLatencyAccuracy property
- MaxRetries property
- UseDataCacheRegistryMultiplyKey property
- ConvertDeletedToUnknown property
- DatabaseConnectionPoolMax property
- DataFileInitEnabled property
- DefaultPageSizeForHash property
- MaxRolapOrConditions property
- UseDataCacheFreeLastPageMemory property
- OLAP [Analysis Services], properties
- MapHandleAlgorithm property
- IndexBuildEnabled property
- MaxObjectsInParallel property
- IgnoreNullRolapRows property
- DimensionPropertyCacheSize property
- DefaultRefreshInterval property
- CheckDistinctRecordSortOrder property
- BufferMemoryLimit property
- EnableTableGrouping property
- ExpressNonEmptyUseEnabled property
- CopyLinkedDataCacheAndRegistry property
- UseDataSlice property
- MemoryLimitErrorEnabled property
- Enabled property
- EnableRolapOptimization property
- DatabaseConnectionPoolTimeout property
- UseDataCacheRegistryHashTable property
- AggregationsBuildEnabled property
- Tax property
- DatabaseConnectionPoolGeneralTimeout property
- DefaultPageSizeForString property
- DatabaseConnectionPoolConnectTimeout property
- MinimumBalance property
- OptimizeSchema property
- UseCalculationCacheRegistry property
- MaxTableDepth property
- DataSliceInitEnabled property
- PrefetchLowerGranularities property
- UseVBANet property
- BufferRecordLimit property
- DefaultPageSizeForIndexHeader property
- MaximumBalance property
- CalculationCacheRegistryMaxIterations property
- DefaultDrillthroughMaxRows property
- IndexBuildThreshold property
- UseDataCacheRegistry property
- MemoryAdjustConst property
- ApplyIntersect property
- IndexFileInitEnabled property
- CacheRowsetToDisk property
- DataCacheRegistryMaxIterations property
- AllowSEFiltering property
- ForceMultiPass property
- ApplySubtract property
- IndexUseEnabled property
- AggregationsUseEnabled property
- DataPlacementOptimization property
- UseMaterializedIterators property
- CacheRecordLimit property
- ROLAPDimensionProcessingEffort property
- DefaultPageSizeForIndex property
- EnableRolapDimQueryTableGrouping property
- DimensionPropertyKeyCache property
- SleepIntervalSecs property
- DefaultPageSizeForData property
- MapFormatMask property
- CalculationEvaluationPolicy property
- AggregationMemoryLimitMin property
- RecordsReportGranularity property
- MemoryLimit property
- AggregationMemoryLimitMax property
ms.assetid: 06eb0d78-96c0-42ff-b759-f4c794597c8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb89d318bfdb78935eb4d9f202db11b978c59b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573311"
---
# <a name="olap-properties"></a><span data-ttu-id="7bfbb-102">Propriedades OLAP</span><span class="sxs-lookup"><span data-stu-id="7bfbb-102">OLAP Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="7bfbb-103">oferece suporte às propriedades do servidor OLAP listadas nas seguintes tabelas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-103">supports the OLAP server properties listed in the following tables.</span></span> <span data-ttu-id="7bfbb-104">Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="7bfbb-105">**Aplica-se a:** Somente modo de servidor multidimensional</span><span class="sxs-lookup"><span data-stu-id="7bfbb-105">**Applies to:** Multidimensional server mode only</span></span>  
  
## <a name="memory"></a><span data-ttu-id="7bfbb-106">Memória</span><span class="sxs-lookup"><span data-stu-id="7bfbb-106">Memory</span></span>  
 `DefaultPageSizeForData`  
 <span data-ttu-id="7bfbb-107">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-107">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForDataHeader`  
 <span data-ttu-id="7bfbb-108">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-108">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForIndex`  
 <span data-ttu-id="7bfbb-109">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForIndexHeader`  
 <span data-ttu-id="7bfbb-110">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForString`  
 <span data-ttu-id="7bfbb-111">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-111">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForHash`  
 <span data-ttu-id="7bfbb-112">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-112">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultPageSizeForProp`  
 <span data-ttu-id="7bfbb-113">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-113">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="lazyprocessing"></a><span data-ttu-id="7bfbb-114">LazyProcessing</span><span class="sxs-lookup"><span data-stu-id="7bfbb-114">LazyProcessing</span></span>  
 `Enabled`  
 <span data-ttu-id="7bfbb-115">Uma propriedade booliana que especifica se o processamento de agregação lento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-115">A Boolean property that specifies whether lazy aggregation processing is enabled.</span></span>  
  
 `SleepIntervalSecs`  
 <span data-ttu-id="7bfbb-116">Uma propriedade de inteiro de 32 bits assinada que define o intervalo, em segundos, em que o servidor verifica se há tarefas de processamento lento pendentes.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-116">A signed 32-bit integer property that defines the interval, in seconds, that the server checks whether there are lazy processing jobs pending.</span></span>  
  
 `MaxCPUUsage`  
 <span data-ttu-id="7bfbb-117">Uma propriedade de número de ponto flutuante de precisão dupla de 64 bits assinada que define o uso máximo da CPU para processamento lento, expresso como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-117">A signed 64-bit double-precision floating-point number property that defines maximum CPU usage for lazy processing, expressed as a percentage.</span></span> <span data-ttu-id="7bfbb-118">O servidor monitora o uso médio de CPU com base em instantâneos.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-118">The server monitors average CPU use based on snapshots.</span></span> <span data-ttu-id="7bfbb-119">É comportamento normal pela CPU para controlar os picos desse limite.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-119">It is normal behavior for the CPU to spike above this threshold.</span></span>  
  
 <span data-ttu-id="7bfbb-120">O valor padrão dessa propriedade é 0,5, indicando que no máximo 50% da CPU será dedicado ao processamento lento.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-120">The default value for this property is 0.5, indicating a maximum of 50% of the CPU will be devoted to lazy processing.</span></span>  
  
 `MaxObjectsInParallel`  
 <span data-ttu-id="7bfbb-121">Uma propriedade de inteiro de 32 bits assinada, que especifica o número máximo de partições e que podem ser processadas lentamente em paralelo.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-121">A signed 32-bit integer property that specifies the maximum number of partitions that can be lazily processed in parallel.</span></span>  
  
 `MaxRetries`  
 <span data-ttu-id="7bfbb-122">Uma propriedade de inteiro de 32 bits assinada que define o número de novas tentativas no caso do processamento lento falhar antes que ocorra um erro.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-122">A signed 32-bit integer property that defines the number of retries in the event that lazy processing fails before an error is raised.</span></span>  
  
## <a name="processplan"></a><span data-ttu-id="7bfbb-123">ProcessPlan</span><span class="sxs-lookup"><span data-stu-id="7bfbb-123">ProcessPlan</span></span>  
 `CacheRowsetRows`  
 <span data-ttu-id="7bfbb-124">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-124">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CacheRowsetToDisk`  
 <span data-ttu-id="7bfbb-125">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-125">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DistinctBuffer`  
 <span data-ttu-id="7bfbb-126">Uma propriedade de inteiro de 32 bits assinada que define o tamanho de um buffer interno usado para contagens distintas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-126">A signed 32-bit integer property that defines the size of an internal buffer used for distinct counts.</span></span> <span data-ttu-id="7bfbb-127">Aumente esse valor para acelerar o processamento de contagem distinto pelo uso da memória.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-127">Increase this value to speed up distinct count processing at the cost of memory use.</span></span>  
  
 `EnableRolapDimQueryTableGrouping`  
 <span data-ttu-id="7bfbb-128">Uma propriedade booliana que especifica se o agrupamento da tabela está habilitado para dimensões ROLAP.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-128">A Boolean property that specifies whether table grouping is enabled for ROLAP dimensions.</span></span> <span data-ttu-id="7bfbb-129">Se True, ao consultar as dimensões ROLAP em runtime, as tabelas de dimensões ROLAP inteiras serão consultadas uma vez, diferentemente das consultas separadas para cada atributo.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-129">If True, when querying ROLAP dimensions at runtime, entire ROLAP dimension tables are queried at once, as opposed to separate queries for each attribute.</span></span>  
  
 `EnableTableGrouping`  
 <span data-ttu-id="7bfbb-130">Uma propriedade booliana que especifica se o agrupamento da tabela está habilitado.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-130">A Boolean property that specifies whether table grouping is enabled.</span></span> <span data-ttu-id="7bfbb-131">Se True, ao processar as dimensões, as tabelas de dimensões inteiras serão consultadas uma vez, diferentemente das consultas separadas para cada atributo.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-131">If True, when processing dimensions, entire dimension tables are queried at once, as opposed to separate queries for each attribute.</span></span>  
  
 `ForceMultiPass`  
 <span data-ttu-id="7bfbb-132">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxTableDepth`  
 <span data-ttu-id="7bfbb-133">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-133">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryAdjustConst`  
 <span data-ttu-id="7bfbb-134">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-134">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryAdjustFactor`  
 <span data-ttu-id="7bfbb-135">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-135">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryLimit`  
 <span data-ttu-id="7bfbb-136">Uma propriedade de número de ponto flutuante da precisão dupla de 64 bits assinada que define a quantidade máxima de memória para processamento, expressa como uma porcentagem da memória física.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-136">A signed 64-bit double-precision floating-point number property that defines the maximum amount of memory to be devoted to processing, expressed as a percentage of physical memory.</span></span>  
  
 <span data-ttu-id="7bfbb-137">O valor padrão dessa propriedade é 65, indicando que no máximo 65% da memória física será dedicada ao processamento de cubo e dimensão.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-137">The default value for this property is 65, indicating that 65% of physical memory may be devoted to cube and dimension processing.</span></span>  
  
 `MemoryLimitErrorEnabled`  
 <span data-ttu-id="7bfbb-138">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-138">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `OptimizeSchema`  
 <span data-ttu-id="7bfbb-139">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-139">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="proactivecaching"></a><span data-ttu-id="7bfbb-140">ProactiveCaching</span><span class="sxs-lookup"><span data-stu-id="7bfbb-140">ProactiveCaching</span></span>  
 `DefaultRefreshInterval`  
 <span data-ttu-id="7bfbb-141">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DimensionLatencyAccuracy`  
 <span data-ttu-id="7bfbb-142">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PartitionLatencyAccuracy`  
 <span data-ttu-id="7bfbb-143">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="process"></a><span data-ttu-id="7bfbb-144">Processo</span><span class="sxs-lookup"><span data-stu-id="7bfbb-144">Process</span></span>  
 `AggregationMemoryLimitMax`  
 <span data-ttu-id="7bfbb-145">Uma propriedade de número de ponto flutuante da precisão dupla de 64 bits assinada que define a quantidade máxima de memória que pode ser dedicada para processamento de agregação, expressa como uma porcentagem da memória física.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-145">A signed 64-bit double-precision floating-point number property that defines the maximum amount of memory that can be devoted to aggregation processing, expressed as a percentage of physical memory.</span></span>  
  
 <span data-ttu-id="7bfbb-146">O valor padrão dessa propriedade é 80, indicando que 80% da memória física poderá ser dedicada ao processamento de agregação.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-146">The default value for this property is 80, indicating that 80% of physical memory may be devoted to aggregation processing.</span></span>  
  
 `AggregationMemoryLimitMin`  
 <span data-ttu-id="7bfbb-147">Uma propriedade de número de ponto flutuante da precisão dupla de 64 bits assinada que define a quantidade mínima de memória que pode ser dedicada para processamento de agregação, expressa como uma porcentagem da memória física.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-147">A signed 64-bit double-precision floating-point number property that defines the minimum amount of memory that can be devoted to aggregation processing, expressed as a percentage of physical memory.</span></span> <span data-ttu-id="7bfbb-148">Um valor maior pode acelerar o processamento da agregação pelo uso da memória.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-148">A larger value may speed up aggregation processing at the cost of memory usage.</span></span>  
  
 <span data-ttu-id="7bfbb-149">O valor padrão dessa propriedade é 10, indicando que no mínimo 10% da memória física será dedicada ao processamento da agregação.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-149">The default value for this property is 10, indicating that minimally 10% of physical memory will be devoted to aggregation processing.</span></span>  
  
 `AggregationNewAlgo`  
 <span data-ttu-id="7bfbb-150">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `AggregationPerfLog2`  
 <span data-ttu-id="7bfbb-151">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `AggregationsBuildEnabled`  
 <span data-ttu-id="7bfbb-152">Uma propriedade booliana que especifica se a criação da agregação está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-152">A Boolean property that specifies whether aggregation building is enabled.</span></span> <span data-ttu-id="7bfbb-153">Esse é um mecanismo para avaliar a criação da agregação sem alterar o projeto da agregação.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-153">This is a mechanism to benchmark aggregation building without changing aggregation design.</span></span>  
  
 `BufferMemoryLimit`  
 <span data-ttu-id="7bfbb-154">Uma propriedade de número de ponto flutuante de precisão dupla de 64 bits assinada que define o limite de memória do buffer de processamento, expresso como uma porcentagem da memória física.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-154">A signed 64-bit double-precision floating-point number property that defines the processing buffer memory limit, expressed as a percent of physical memory.</span></span>  
  
 <span data-ttu-id="7bfbb-155">O valor padrão dessa propriedade é 60, indicando que até 60% da memória física pode ser usada para a memória de buffer.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-155">The default value for this property is 60, which indicates that up to 60% of physical memory can be used for buffer memory.</span></span>  
  
 `BufferRecordLimit`  
 <span data-ttu-id="7bfbb-156">Uma propriedade de inteiro de 32 bits assinada que define o número de registros que podem ser colocados em buffer durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-156">A signed 32-bit integer property that defines the number of records that can be buffered during processing.</span></span>  
  
 <span data-ttu-id="7bfbb-157">O valor padrão para essa propriedade é 1048576 (registros).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-157">The default value for this property is 1048576 (records).</span></span>  
  
 `CacheRecordLimit`  
 <span data-ttu-id="7bfbb-158">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-158">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CheckDistinctRecordSortOrder`  
 <span data-ttu-id="7bfbb-159">Uma propriedade booliana que define se a ordem de classificação para os resultados de uma consulta de contagem distinta é significativa ao processar partições.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-159">A Boolean property that defines if the sort order for the results of a distinct count query are meaningful when processing partitions.</span></span> <span data-ttu-id="7bfbb-160">True indica que a ordem de classificação não é significativa e deve ser “verificada” pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-160">True indicates the sort order is not meaningful and must be "checked" by the server.</span></span> <span data-ttu-id="7bfbb-161">Ao processar partições com medida de contagem distinta, a consulta é enviada para SQL com a classificação.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-161">When processing partitions with distinct count measure, query sent to SQL with order-by.</span></span> <span data-ttu-id="7bfbb-162">Defina como false para acelerar o processamento.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-162">Set to false to speed up processing.</span></span>  
  
 <span data-ttu-id="7bfbb-163">O valor padrão dessa propriedade é True, indicando que a ordem de classificação não é significativa e deve ser verificada.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-163">The default value for this property is True, which indicates that the sort order is not meaningful and must be checked.</span></span>  
  
 `DatabaseConnectionPoolConnectTimeout`  
 <span data-ttu-id="7bfbb-164">Uma propriedade de inteiro de 32 bits assinada que especifica o tempo limite em segundos ao abrir uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-164">A signed 32-bit integer property that specifies timeout when opening a new connection in seconds.</span></span>  
  
 `DatabaseConnectionPoolGeneralTimeout`  
 <span data-ttu-id="7bfbb-165">Uma propriedade de inteiro de 32 bits assinada que especifica o tempo limite em segundos da conexão do banco de dados para uso com as conexões OLEDB externas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-165">A signed 32-bit integer property that specifies database connection timeout for use with external OLEDB connections in seconds.</span></span>  
  
 `DatabaseConnectionPoolMax`  
 <span data-ttu-id="7bfbb-166">Uma propriedade de inteiro de 32 bits assinada que especifica o número máximo de conexões de banco de dados agrupadas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-166">A signed 32-bit integer property that specifies the maximum number of pooled database connections.</span></span>  
  
 <span data-ttu-id="7bfbb-167">O valor padrão dessa propriedade é 50 (conexões).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-167">The default value for this property is 50 (connections).</span></span>  
  
 `DatabaseConnectionPoolTimeout`  
 <span data-ttu-id="7bfbb-168">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-168">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataFileInitEnabled`  
 <span data-ttu-id="7bfbb-169">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataPlacementOptimization`  
 <span data-ttu-id="7bfbb-170">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-170">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataSliceInitEnabled`  
 <span data-ttu-id="7bfbb-171">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeepCompressValue`  
 <span data-ttu-id="7bfbb-172">Uma propriedade booliana aplicada a medidas com tipo de dados duplo que especifica se os números podem ser compactados, causando perda na precisão numérica.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-172">A Boolean property applying to measures with Double data type that specifies whether numbers can be compressed, causing a loss in numeric precision.</span></span> <span data-ttu-id="7bfbb-173">Um valor False indica que não há nenhuma compactação ou perda de precisão.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-173">A value of False indicates no compression and no precision loss.</span></span>  
  
 <span data-ttu-id="7bfbb-174">O valor padrão para essa propriedade é True, que indica que a compactação está habilitada e a precisão será perdida.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-174">The default value for this property is True, which indicates that compression is enabled and precision will be lost.</span></span>  
  
 `DimensionPropertyKeyCache`  
 <span data-ttu-id="7bfbb-175">Uma propriedade booliana que especifica se as chaves da propriedade de dimensão são colocadas em cache.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-175">A Boolean property that specifies whether dimension property keys are cached.</span></span> <span data-ttu-id="7bfbb-176">Deve ser definida como True se as chaves não forem exclusivas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-176">Must be set to True if keys are non-unique.</span></span>  
  
 `IndexBuildEnabled`  
 <span data-ttu-id="7bfbb-177">Uma propriedade booliana que especifica se os índices são criados no processamento.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-177">A Boolean property that specifies whether indexes are built upon processing.</span></span> <span data-ttu-id="7bfbb-178">Essa propriedade é para fins de avaliação de desempenho e de informação.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-178">This property is for benchmarking and informational purposes.</span></span>  
  
 `IndexBuildThreshold`  
 <span data-ttu-id="7bfbb-179">Uma propriedade de inteiro de 32 bits assinada que especifica o limite de contagem de linhas abaixo do qual os índices não serão criados para partições.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-179">A signed 32-bit integer property that specifies a row count threshold below which indexes will not be built for partitions.</span></span>  
  
 <span data-ttu-id="7bfbb-180">O valor padrão para essa propriedade é 4096 (linhas).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-180">The default value for this property is 4096 (rows).</span></span>  
  
 `IndexFileInitEnabled`  
 <span data-ttu-id="7bfbb-181">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-181">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MapFormatMask`  
 <span data-ttu-id="7bfbb-182">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-182">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RecordsReportGranularity`  
 <span data-ttu-id="7bfbb-183">Uma propriedade de inteiro de 32 bits assinada que especifica com que frequência o servidor registra os eventos de Rastreamento durante o processamento em linhas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-183">A signed 32-bit integer property that specifies how often the server records Trace events during processing, in rows.</span></span>  
  
 <span data-ttu-id="7bfbb-184">O valor padrão para essa propriedade é 1000, o que indica que um evento de Rastreamento é registrado uma vez a cada 1000 linhas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-184">The default value for this property is 1000, which indicates that a Trace event is logged once every 1000 rows.</span></span>  
  
 `ROLAPDimensionProcessingEffort`  
 <span data-ttu-id="7bfbb-185">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-185">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="query"></a><span data-ttu-id="7bfbb-186">Consulta</span><span class="sxs-lookup"><span data-stu-id="7bfbb-186">Query</span></span>  
 `AggregationsUseEnabled`  
 <span data-ttu-id="7bfbb-187">Uma propriedade booliana que define se as agregações armazenadas são usadas em runtime.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-187">A Boolean property that defines whether stored aggregations are used at runtime.</span></span> <span data-ttu-id="7bfbb-188">Essa propriedade permite que as agregações sejam desabilitadas sem alterar o projeto da agregação ou o reprocessamento, para fins de avaliação de desempenho e de informação.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-188">This property allows aggregations to be disabled without changing the aggregation design or re-processing, for informational and benchmarking purposes.</span></span>  
  
 <span data-ttu-id="7bfbb-189">O valor padrão para essa propriedade é True, indicando que as agregações estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-189">The default value for this property is True, indicating that aggregations are enabled.</span></span>  
  
 `AllowSEFiltering`  
 <span data-ttu-id="7bfbb-190">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-190">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationCacheRegistryMaxIterations`  
 <span data-ttu-id="7bfbb-191">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-191">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationEvaluationPolicy`  
 <span data-ttu-id="7bfbb-192">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-192">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ConvertDeletedToUnknown`  
 <span data-ttu-id="7bfbb-193">Uma propriedade booliana que especifica se membros excluídos da dimensão são convertidos em um membro Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-193">A Boolean property that specifies whether deleted dimension members are converted to Unknown member.</span></span>  
  
 `CopyLinkedDataCacheAndRegistry`  
 <span data-ttu-id="7bfbb-194">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-194">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCacheRegistryMaxIterations`  
 <span data-ttu-id="7bfbb-195">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-195">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DefaultDrillthroughMaxRows`  
 <span data-ttu-id="7bfbb-196">Uma propriedade de inteiro de 32 bits assinada que especifica o número máximo de linhas que retornarão de uma consulta em profundidade.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-196">A signed 32-bit integer property that specifies the maximum number of rows that will return from a drill-through query.</span></span>  
  
 <span data-ttu-id="7bfbb-197">O valor padrão para essa propriedade é 10000 (linhas).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-197">The default value for this property is 10000 (rows).</span></span>  
  
 `DimensionPropertyCacheSize`  
 <span data-ttu-id="7bfbb-198">Uma propriedade de inteiro de 32 bits assinada que especifica a quantidade de memória (em bytes) usada para membros de dimensão de cache usados em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-198">A signed 32-bit integer property that specifies the amount of memory (in bytes) used to cache dimension members used in a query.</span></span>  
  
 <span data-ttu-id="7bfbb-199">O padrão é 4.000.000 bytes (ou 4 MB) por hierarquia de atributo, por consulta ativa.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-199">The default is 4,000,000 bytes (or 4 MB) per attribute hierarchy, per active query.</span></span> <span data-ttu-id="7bfbb-200">O valor padrão fornece um tamanho de cache bem balanceado para soluções que têm hierarquias típicas.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-200">The default value provides a well-balanced cache size for solutions having typical hierarchies.</span></span> <span data-ttu-id="7bfbb-201">No entanto, as dimensões com um número muito grande de membros (em milhões) ou de hierarquias profundas serão melhor executadas se você aumentar esse valor.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-201">However, dimensions with a very large number of members (in the millions) or deep hierarchies perform better if you increase this value.</span></span>  
  
 <span data-ttu-id="7bfbb-202">Implicações de aumentar o tamanho do cache:</span><span class="sxs-lookup"><span data-stu-id="7bfbb-202">Implications of increasing cache size:</span></span>  
  
-   <span data-ttu-id="7bfbb-203">O custo da utilização de memória aumenta quando você permite que mais memória seja usada pelo cache de dimensão.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-203">Memory utilization costs increase when you allow more memory to be used by the dimension cache.</span></span> <span data-ttu-id="7bfbb-204">O uso real depende da execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-204">Actual usage depends on query execution.</span></span> <span data-ttu-id="7bfbb-205">Nem todas as consultas usarão o máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-205">Not all queries will use the allowable maximum.</span></span>  
  
     <span data-ttu-id="7bfbb-206">Observe que a memória usada por esses caches é considerada não reduzível e será incluída para explicar o **TotalMemoryLimit**.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-206">Note that the memory used by these caches is considered nonshrinkable and will be included when accounting against the **TotalMemoryLimit**.</span></span>  
  
-   <span data-ttu-id="7bfbb-207">Afeta todos os bancos de dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-207">Affects all databases on the server.</span></span> <span data-ttu-id="7bfbb-208">**DimensionPropertyCachesize** é uma propriedade para todo o servidor.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-208">**DimensionPropertyCachesize** is a server-wide property.</span></span> <span data-ttu-id="7bfbb-209">Alterar essa propriedade afeta todos os bancos de dados em execução na instância atual.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-209">Changing this property affects all databases running on the current instance.</span></span>  
  
 <span data-ttu-id="7bfbb-210">Abordagem para calcular os requisitos de cache de dimensão:</span><span class="sxs-lookup"><span data-stu-id="7bfbb-210">Approach for estimating dimension cache requirements:</span></span>  
  
1.  <span data-ttu-id="7bfbb-211">Comece aumentando o tamanho bastante para determinar se é vantagem aumentar o tamanho do cache de dimensão.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-211">Start by increasing the size by a large number to determine whether there is a benefit to increasing the dimension cache size.</span></span> <span data-ttu-id="7bfbb-212">Por exemplo, talvez você queira dobrar o valor padrão como uma etapa inicial.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-212">For example, you might want to double the default value as an initial step.</span></span>  
  
2.  <span data-ttu-id="7bfbb-213">Se uma melhoria de desempenho é evidente, reduza incrementalmente o valor até que você alcance um equilíbrio entre o bom desempenho e a utilização de memória.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-213">If a performance improvement is evident, incrementally reduce the value until you reach a balance between performance and memory utilization.</span></span>  
  
 `ExpressNonEmptyUseEnabled`  
 <span data-ttu-id="7bfbb-214">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `IgnoreNullRolapRows`  
 <span data-ttu-id="7bfbb-215">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-215">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `IndexUseEnabled`  
 <span data-ttu-id="7bfbb-216">Uma propriedade booliana que define se os índices são usados em runtime.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-216">A Boolean property that defines whether indexes are used at runtime.</span></span> <span data-ttu-id="7bfbb-217">Essa propriedade é para fins de avaliação de desempenho e de informações.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-217">This property is for informational and benchmarking purposes.</span></span>  
  
 `MapHandleAlgorithm`  
 <span data-ttu-id="7bfbb-218">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxRolapOrConditions`  
 <span data-ttu-id="7bfbb-219">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-219">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseCalculationCacheRegistry`  
 <span data-ttu-id="7bfbb-220">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheFreeLastPageMemory`  
 <span data-ttu-id="7bfbb-221">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-221">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheRegistry`  
 <span data-ttu-id="7bfbb-222">Uma propriedade booliana que especifica se o registro em cache de dados deve ser habilitado, onde os resultados da consulta são armazenados em cache (mesmo se os resultados não forem calculados).</span><span class="sxs-lookup"><span data-stu-id="7bfbb-222">A Boolean property that specifies whether to enable the data cache registry, where query results are cached (though not calculated results).</span></span>  
  
 `UseDataCacheRegistryHashTable`  
 <span data-ttu-id="7bfbb-223">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-223">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataCacheRegistryMultiplyKey`  
 <span data-ttu-id="7bfbb-224">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseDataSlice`  
 <span data-ttu-id="7bfbb-225">Uma propriedade booliana, que define se frações de dados de partição devem ser usadas em runtime para a otimização da consulta.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-225">A Boolean property that defines whether to use partition data slices at runtime for query optimization.</span></span> <span data-ttu-id="7bfbb-226">Essa propriedade é para fins de avaliação de desempenho e de informação.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-226">This property is for benchmarking and informational purposes.</span></span>  
  
 `UseMaterializedIterators`  
 <span data-ttu-id="7bfbb-227">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-227">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseSinglePassForDimSecurityAutoExist`  
 <span data-ttu-id="7bfbb-228">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `UseVBANet`  
 <span data-ttu-id="7bfbb-229">Uma propriedade booliana que define se deve ser usada a assembly VBA .net para funções definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-229">A Boolean property that defines whether to use the VBA .net assembly for user-defined functions.</span></span>  
  
 `CalculationPrefetchLocality\ ApplyIntersect`  
 <span data-ttu-id="7bfbb-230">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationPrefetchLocality\ ApplySubtract`  
 <span data-ttu-id="7bfbb-231">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-231">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `CalculationPrefetchLocality\ PrefetchLowerGranularities`  
 <span data-ttu-id="7bfbb-232">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-232">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ Income`  
 <span data-ttu-id="7bfbb-233">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-233">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ InitialBonus`  
 <span data-ttu-id="7bfbb-234">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-234">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ MaximumBalance`  
 <span data-ttu-id="7bfbb-235">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-235">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ MinimumBalance`  
 <span data-ttu-id="7bfbb-236">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-236">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\  CachedPageAlloc\ Tax`  
 <span data-ttu-id="7bfbb-237">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-237">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ Income`  
 <span data-ttu-id="7bfbb-238">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-238">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ InitialBonus`  
 <span data-ttu-id="7bfbb-239">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-239">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ MaximumBalance`  
 <span data-ttu-id="7bfbb-240">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-240">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ MinimumBalance`  
 <span data-ttu-id="7bfbb-241">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-241">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\CellStore\ Tax`  
 <span data-ttu-id="7bfbb-242">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-242">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ Income`  
 <span data-ttu-id="7bfbb-243">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-243">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ InitialBonus`  
 <span data-ttu-id="7bfbb-244">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-244">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ MaximumBalance`  
 <span data-ttu-id="7bfbb-245">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-245">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel \ MinimumBalance`  
 <span data-ttu-id="7bfbb-246">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-246">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataCache\ MemoryModel\ Tax`  
 <span data-ttu-id="7bfbb-247">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-247">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="jobs"></a><span data-ttu-id="7bfbb-248">Trabalhos</span><span class="sxs-lookup"><span data-stu-id="7bfbb-248">Jobs</span></span>  
 `ProcessAggregation\ MemoryModel\ Income`  
 <span data-ttu-id="7bfbb-249">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-249">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ InitialBonus`  
 <span data-ttu-id="7bfbb-250">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-250">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ MaximumBalance`  
 <span data-ttu-id="7bfbb-251">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-251">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ MinimumBalance`  
 <span data-ttu-id="7bfbb-252">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-252">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ MemoryModel\ Tax`  
 <span data-ttu-id="7bfbb-253">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-253">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition\ Income`  
 <span data-ttu-id="7bfbb-254">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-254">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ InitialBonus`  
 <span data-ttu-id="7bfbb-255">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-255">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ MaximumBalance`  
 <span data-ttu-id="7bfbb-256">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-256">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ MinimumBalance`  
 <span data-ttu-id="7bfbb-257">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-257">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessPartition \ Tax`  
 <span data-ttu-id="7bfbb-258">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-258">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ Income`  
 <span data-ttu-id="7bfbb-259">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-259">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ InitialBonus`  
 <span data-ttu-id="7bfbb-260">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-260">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ MaximumBalance`  
 <span data-ttu-id="7bfbb-261">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-261">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ MinimumBalance`  
 <span data-ttu-id="7bfbb-262">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-262">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ProcessAggregation\ ProcessProperty\ Tax`  
 <span data-ttu-id="7bfbb-263">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bfbb-263">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bfbb-264">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7bfbb-264">See Also</span></span>  
 <span data-ttu-id="7bfbb-265">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="7bfbb-265">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="7bfbb-266">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="7bfbb-266">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
