---
title: Partições remotas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- storage [Analysis Services], partitions
- archiving remote partitions [Analysis Services]
- partitions [Analysis Services], remote
- restoring remote partitions [Analysis Services]
- backing up remote partitions [Analysis Services]
- partitions [Analysis Services], storage
- storing data [Analysis Services], partitions
- remote partitions [Analysis Services]
ms.assetid: 63f5d9f5-c6b6-4ceb-94fe-7b6c396d10bb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 32fdf05d061d4e1c1da6ec0ef9179ecd12bda172
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681235"
---
# <a name="remote-partitions"></a><span data-ttu-id="2c009-102">Partições remotas</span><span class="sxs-lookup"><span data-stu-id="2c009-102">Remote Partitions</span></span>
  <span data-ttu-id="2c009-103">Os dados de uma partição remota são armazenados em uma instância diferente da Microsoft do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que a instância do que contém as definições (metadados) da partição e seu cubo pai.</span><span class="sxs-lookup"><span data-stu-id="2c009-103">The data of a remote partition is stored on a different instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] than the instance that contains the definitions (metadata) of the partition and its parent cube.</span></span> <span data-ttu-id="2c009-104">Uma partição remota é gerenciada na mesma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] onde a partição e seu cubo pai são definidos.</span><span class="sxs-lookup"><span data-stu-id="2c009-104">A remote partition is administered on the same instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] where the partition and its parent cube are defined.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c009-105">Para armazenar uma partição remota, o computador deve ter uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instalada e estar executando o mesmo nível de Service Pack que a instância em que a partição foi definida.</span><span class="sxs-lookup"><span data-stu-id="2c009-105">To store a remote partition, the computer must have an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] installed and be running the same service pack level as the instance where the partition was defined.</span></span> <span data-ttu-id="2c009-106">As partições remotas em instâncias de uma versão anterior do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não oferecem suporte.</span><span class="sxs-lookup"><span data-stu-id="2c009-106">Remote partitions on instances of an earlier version of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] are not supported.</span></span>  
  
 <span data-ttu-id="2c009-107">Quando as partições remotas são incluídas em um grupo de medidas, a memória e a utilização da CPU do cubo são distribuídas ao longo das partições nesse grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="2c009-107">When remote partitions are included in a measure group, the memory and CPU utilization of the cube is distributed across all the partitions in the measure group.</span></span> <span data-ttu-id="2c009-108">Por exemplo, quando uma partição remota é processada, sozinha ou como parte do processamento de um cubo pai, a maior parte da utilização da memória e da CPU para a partição ocorre na instância remota do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c009-108">For example, when a remote partition is processed, either alone or as part of parent cube processing, most of the memory and CPU utilization for that partition occurs on the remote instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c009-109">Um cubo que contém partições remotas pode conter dimensões habilitadas para gravação; porém, isso pode afetar o desempenho do cubo.</span><span class="sxs-lookup"><span data-stu-id="2c009-109">A cube that contains remote partitions can contain write-enabled dimensions; however, this may affect performance for the cube.</span></span> <span data-ttu-id="2c009-110">Para obter mais informações sobre dimensões habilitadas para gravação, consulte [dimensões habilitadas para gravação](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="2c009-110">For more information about write-enabled dimensions, see [Write-Enabled Dimensions](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md).</span></span>  
  
## <a name="storage-modes-for-remote-partitions"></a><span data-ttu-id="2c009-111">Modos de armazenamento para partições remotas</span><span class="sxs-lookup"><span data-stu-id="2c009-111">Storage Modes for Remote Partitions</span></span>  
 <span data-ttu-id="2c009-112">As partições remotas podem usar qualquer dos tipos de armazenamento usados por partições locais: OLAP multidimensional (MOLAP), OLAP híbrido (HOLAP) ou OLAP relacional (ROLAP).</span><span class="sxs-lookup"><span data-stu-id="2c009-112">Remote partitions may use any of the storage types used by local partitions: multidimensional OLAP (MOLAP), hybrid OLAP (HOLAP), or relational OLAP (ROLAP).</span></span> <span data-ttu-id="2c009-113">As partições remotas também podem usar cache pró-ativo.</span><span class="sxs-lookup"><span data-stu-id="2c009-113">Remote partitions may also use proactive caching.</span></span> <span data-ttu-id="2c009-114">Dependendo do modo de armazenamento de uma partição remota, os dados a seguir são armazenados na instância remota do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c009-114">Depending on the storage mode of a remote partition, the following data is stored on the remote instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c009-115">Tipo de armazenamento</span><span class="sxs-lookup"><span data-stu-id="2c009-115">Storage Type</span></span>|<span data-ttu-id="2c009-116">Dados</span><span class="sxs-lookup"><span data-stu-id="2c009-116">Data</span></span>|  
|<span data-ttu-id="2c009-117">MOLAP</span><span class="sxs-lookup"><span data-stu-id="2c009-117">MOLAP</span></span>|<span data-ttu-id="2c009-118">As agregações da partição e uma cópia dos dados de origem da partição</span><span class="sxs-lookup"><span data-stu-id="2c009-118">The partition's aggregations and a copy of the partition's source data</span></span>|  
|<span data-ttu-id="2c009-119">HOLAP</span><span class="sxs-lookup"><span data-stu-id="2c009-119">HOLAP</span></span>|<span data-ttu-id="2c009-120">As agregações das partições</span><span class="sxs-lookup"><span data-stu-id="2c009-120">The partitions aggregations</span></span>|  
|<span data-ttu-id="2c009-121">ROLAP</span><span class="sxs-lookup"><span data-stu-id="2c009-121">ROLAP</span></span>|<span data-ttu-id="2c009-122">Nenhum dado da partição</span><span class="sxs-lookup"><span data-stu-id="2c009-122">No partition data</span></span>|  
  
 <span data-ttu-id="2c009-123">Se o grupo de medidas contiver várias partições MOLAP ou HOLAP armazenadas em várias instâncias do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], o cubo distribui os dados nos dados do grupo de medidas entre as instâncias do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c009-123">If a measure group contains multiple MOLAP or HOLAP partitions stored on multiple instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the cube distributes the data in the measure group data among those instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="merging-remote-partitions"></a><span data-ttu-id="2c009-124">Mesclando partições remotas</span><span class="sxs-lookup"><span data-stu-id="2c009-124">Merging Remote Partitions</span></span>  
 <span data-ttu-id="2c009-125">As partições remotas podem ser mescladas somente com outras partições remotas armazenadas na mesma instância remota do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c009-125">Remote partitions can be merged only with other remote partitions that are stored on the same remote instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="2c009-126">Para obter mais informações sobre como mesclar partições, consulte [mesclar partições em Analysis Services &#40;SSAS-&#41;multidimensional ](../multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="2c009-126">For more information about merging partitions, see [Merge Partitions in Analysis Services &#40;SSAS - Multidimensional&#41;](../multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md).</span></span>  
  
## <a name="archiving-and-restoring-remote-partitions"></a><span data-ttu-id="2c009-127">Arquivando e restaurando partições remotas</span><span class="sxs-lookup"><span data-stu-id="2c009-127">Archiving and Restoring Remote Partitions</span></span>  
 <span data-ttu-id="2c009-128">Os dados em partições remotas podem ser arquivados ou restaurados quando o banco de dados que armazena a partição remota for arquivado ou restaurado.</span><span class="sxs-lookup"><span data-stu-id="2c009-128">Data in remote partitions can be archived or restored when the database that stores the remote partition is archived or restored.</span></span> <span data-ttu-id="2c009-129">Se você restaurar um banco de dados sem restaurar uma partição remota, você deve processar a partição remota antes de usar os dados na partição.</span><span class="sxs-lookup"><span data-stu-id="2c009-129">If you restore a database without restoring a remote partition, you must process the remote partition before you can use the data in the partition.</span></span> <span data-ttu-id="2c009-130">Para obter mais informações sobre arquivamento e restauração de bancos de dados, consulte [backup e restauração de bancos de dados Analysis Services](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2c009-130">For more information about archiving and restoring databases, see [Backup and Restore of Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c009-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c009-131">See Also</span></span>  
 <span data-ttu-id="2c009-132">[Criar e gerenciar uma partição remota &#40;Analysis Services&#41;](../multidimensional-models/create-and-manage-a-remote-partition-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="2c009-132">[Create and Manage a Remote Partition &#40;Analysis Services&#41;](../multidimensional-models/create-and-manage-a-remote-partition-analysis-services.md) </span></span>  
 [<span data-ttu-id="2c009-133">Processando objetos do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2c009-133">Processing Analysis Services Objects</span></span>](../multidimensional-models/processing-analysis-services-objects.md)  
  
  
