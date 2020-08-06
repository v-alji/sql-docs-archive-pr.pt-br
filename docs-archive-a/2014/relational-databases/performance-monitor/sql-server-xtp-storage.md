---
title: Armazenamento XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 4070580b-880d-4f4c-abcc-626a4fe0c9a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: efd4a9eba36060d3d4bab9b371678ab2b2c409ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574676"
---
# <a name="xtp-storage"></a><span data-ttu-id="aee24-102">Armazenamento de XTP</span><span class="sxs-lookup"><span data-stu-id="aee24-102">XTP Storage</span></span>
  <span data-ttu-id="aee24-103">O objeto de desempenho do Armazenamento de XTP contém os contadores relacionados ao Armazenamento de XTP no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aee24-103">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="aee24-104">Esta tabela descreve os contadores de **Armazenamento de XTP** .</span><span class="sxs-lookup"><span data-stu-id="aee24-104">This table describes the **XTP Storage** counters.</span></span>  
  
|<span data-ttu-id="aee24-105">Contador</span><span class="sxs-lookup"><span data-stu-id="aee24-105">Counter</span></span>|<span data-ttu-id="aee24-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="aee24-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aee24-107">**Pontos de verificação fechados**</span><span class="sxs-lookup"><span data-stu-id="aee24-107">**Checkpoints Closed**</span></span>|<span data-ttu-id="aee24-108">Contagem de pontos de verificação fechados feita pelo agente online.</span><span class="sxs-lookup"><span data-stu-id="aee24-108">Count of checkpoints closed done by online agent.</span></span>|  
|<span data-ttu-id="aee24-109">**Pontos de verificação concluídos**</span><span class="sxs-lookup"><span data-stu-id="aee24-109">**Checkpoints Completed**</span></span>|<span data-ttu-id="aee24-110">Contagem de pontos de verificação processados pelo thread de ponto de verificação offline.</span><span class="sxs-lookup"><span data-stu-id="aee24-110">Count of checkpoints processed by offline checkpoint thread.</span></span>|  
|<span data-ttu-id="aee24-111">**Mesclagens de núcleo concluídas**</span><span class="sxs-lookup"><span data-stu-id="aee24-111">**Core Merges Completed**</span></span>|<span data-ttu-id="aee24-112">O número de mesclagens de núcleo concluídas pelo thread de trabalho de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="aee24-112">The number of core merges completed by the merge worker thread.</span></span> <span data-ttu-id="aee24-113">Essas mesclagens ainda precisam ser instaladas.</span><span class="sxs-lookup"><span data-stu-id="aee24-113">These merges still need to be installed.</span></span>|  
|<span data-ttu-id="aee24-114">**Avaliações de política de mesclagem**</span><span class="sxs-lookup"><span data-stu-id="aee24-114">**Merge Policy Evaluations**</span></span>|<span data-ttu-id="aee24-115">O número de avaliações de política de mesclagem desde que o servidor foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="aee24-115">The number of merge policy evaluations since the server started.</span></span>|  
|<span data-ttu-id="aee24-116">**Solicitações de mesclagem pendentes**</span><span class="sxs-lookup"><span data-stu-id="aee24-116">**Merge Requests Outstanding**</span></span>|<span data-ttu-id="aee24-117">O número de solicitações de mesclagem pendentes desde que o servidor foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="aee24-117">The number of merge requests outstanding since the server started.</span></span>|  
|<span data-ttu-id="aee24-118">**Mesclagens abandonadas**</span><span class="sxs-lookup"><span data-stu-id="aee24-118">**Merges Abandoned**</span></span>|<span data-ttu-id="aee24-119">O número de mesclagens abandonadas devido à falha.</span><span class="sxs-lookup"><span data-stu-id="aee24-119">The number of merges abandoned due to failure.</span></span>|  
|<span data-ttu-id="aee24-120">**Mesclagens instaladas**</span><span class="sxs-lookup"><span data-stu-id="aee24-120">**Merges Installed**</span></span>|<span data-ttu-id="aee24-121">O número de mesclagens instaladas com êxito.</span><span class="sxs-lookup"><span data-stu-id="aee24-121">The number of merges successfully installed.</span></span>|  
|<span data-ttu-id="aee24-122">**Total de arquivos mesclados**</span><span class="sxs-lookup"><span data-stu-id="aee24-122">**Total Files Merged**</span></span>|<span data-ttu-id="aee24-123">O número total de arquivos de origem mesclados.</span><span class="sxs-lookup"><span data-stu-id="aee24-123">The total number of source files merged.</span></span> <span data-ttu-id="aee24-124">Esta contagem pode ser usada para localizar o número médio de arquivos de origem na mesclagem.</span><span class="sxs-lookup"><span data-stu-id="aee24-124">This count can be used to find the average number of source files in the merge.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aee24-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aee24-125">See Also</span></span>  
 [<span data-ttu-id="aee24-126">&#40;de OLTP na memória&#41; contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="aee24-126">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
