---
title: SQL Server, HTTP_STORAGE_OBJECT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: ae849f79-c581-42a5-a5cc-0a9ebea171b9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62cd5b8422213624cfd8609027c477760f682239
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570638"
---
# <a name="sql-server-http_storage_object"></a><span data-ttu-id="46ad9-102">SQL Server, HTTP_STORAGE_OBJECT</span><span class="sxs-lookup"><span data-stu-id="46ad9-102">SQL Server, HTTP_STORAGE_OBJECT</span></span>
  <span data-ttu-id="46ad9-103">O objeto de desempenho **SqlServer: HTTP_STORAGE_OBJECT** consiste em contadores de desempenho que monitoram a conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="46ad9-103">The **SQLServer:HTTP_STORAGE_OBJECT** performance object consists of performance counters that monitor Azure Storage account.</span></span> <span data-ttu-id="46ad9-104">Usando [SQL Server arquivos de dados no recurso do Azure](../databases/sql-server-data-files-in-microsoft-azure.md) , você pode armazenar arquivos de banco de dado em blobs de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="46ad9-104">Using [SQL Server Data Files in Azure](../databases/sql-server-data-files-in-microsoft-azure.md) feature, you can store database files in Azure Storage Blobs.</span></span> <span data-ttu-id="46ad9-105">Esse objeto de desempenho trata cada conta de Armazenamento do Microsoft Azure como uma unidade diferente.</span><span class="sxs-lookup"><span data-stu-id="46ad9-105">This performance object treats each Azure Storage account as a different drive.</span></span>  
  
|<span data-ttu-id="46ad9-106">Nome do contador</span><span class="sxs-lookup"><span data-stu-id="46ad9-106">Counter Name</span></span>|<span data-ttu-id="46ad9-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="46ad9-107">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="46ad9-108">**Leitura de bytes/s**</span><span class="sxs-lookup"><span data-stu-id="46ad9-108">**Read Bytes/sec**</span></span>|<span data-ttu-id="46ad9-109">Quantidade de dados que estão sendo transferidos do armazenamento HTTP por segundo durante operações de leitura.</span><span class="sxs-lookup"><span data-stu-id="46ad9-109">Amount of data being transferred from the HTTP storage per second during read operations.</span></span>|  
|<span data-ttu-id="46ad9-110">**Gravação de bytes/s**</span><span class="sxs-lookup"><span data-stu-id="46ad9-110">**Write Bytes/sec**</span></span>|<span data-ttu-id="46ad9-111">Quantidade de dados que estão sendo transferidos do armazenamento HTTP por segundo durante operações de gravação.</span><span class="sxs-lookup"><span data-stu-id="46ad9-111">Amount of data being transferred from the HTTP storage per second during write operations.</span></span>|  
|<span data-ttu-id="46ad9-112">**Total de bytes/s**</span><span class="sxs-lookup"><span data-stu-id="46ad9-112">**Total Bytes/sec**</span></span>|<span data-ttu-id="46ad9-113">Quantidade de dados que estão sendo transferidos do armazenamento HTTP por segundo durante operações de leitura ou gravação.</span><span class="sxs-lookup"><span data-stu-id="46ad9-113">Amount of data being transferred from the HTTP storage per second during read or write operations.</span></span>|  
|<span data-ttu-id="46ad9-114">**Leituras/s**</span><span class="sxs-lookup"><span data-stu-id="46ad9-114">**Reads/sec**</span></span>|<span data-ttu-id="46ad9-115">Número de leituras por segundo no armazenamento HTTP.</span><span class="sxs-lookup"><span data-stu-id="46ad9-115">Number of reads per second on the HTTP storage.</span></span>|  
|<span data-ttu-id="46ad9-116">**Gravações/s**</span><span class="sxs-lookup"><span data-stu-id="46ad9-116">**Writes/sec**</span></span>|<span data-ttu-id="46ad9-117">Número de gravações por segundo no armazenamento HTTP.</span><span class="sxs-lookup"><span data-stu-id="46ad9-117">Number of writer per second on the HTTP storage.</span></span>|  
|<span data-ttu-id="46ad9-118">**Transferências/s**</span><span class="sxs-lookup"><span data-stu-id="46ad9-118">**Transfers/sec**</span></span>|<span data-ttu-id="46ad9-119">Número de operações de leitura e gravação por segundo no armazenamento HTTP.</span><span class="sxs-lookup"><span data-stu-id="46ad9-119">Number of read and write operations per second on the HTTP storage.</span></span>|  
|<span data-ttu-id="46ad9-120">**Méd. de Bytes/leitura**</span><span class="sxs-lookup"><span data-stu-id="46ad9-120">**Avg. Bytes/Read**</span></span>|<span data-ttu-id="46ad9-121">Número médio de bytes transferidos do armazenamento HTTP por leitura.</span><span class="sxs-lookup"><span data-stu-id="46ad9-121">Average number of bytes transferred from the HTTP storage per read.</span></span>|  
|<span data-ttu-id="46ad9-122">**Méd. de Bytes/gravação**</span><span class="sxs-lookup"><span data-stu-id="46ad9-122">**Avg. Bytes/Write**</span></span>|<span data-ttu-id="46ad9-123">Número médio de bytes transferidos do armazenamento HTTP por gravação.</span><span class="sxs-lookup"><span data-stu-id="46ad9-123">Average number of bytes transferred from the HTTP storage per write.</span></span>|  
|<span data-ttu-id="46ad9-124">**Méd. de Bytes/transferência**</span><span class="sxs-lookup"><span data-stu-id="46ad9-124">**Avg. Bytes/Transfer**</span></span>|<span data-ttu-id="46ad9-125">Número médio de bytes transferidos do armazenamento HTTP durante operações de leitura ou gravação.</span><span class="sxs-lookup"><span data-stu-id="46ad9-125">Average number of bytes transferred from the HTTP storage during read or write operations.</span></span>|  
|<span data-ttu-id="46ad9-126">**Média de microssegundos/leitura**</span><span class="sxs-lookup"><span data-stu-id="46ad9-126">**Avg. microsec/Read**</span></span>|<span data-ttu-id="46ad9-127">O número médio de microssegundos que leva para realizar cada leitura do armazenamento HTTP.</span><span class="sxs-lookup"><span data-stu-id="46ad9-127">The average number of microseconds it takes to do each read from the HTTP storage.</span></span>|  
|<span data-ttu-id="46ad9-128">**Média de microssegundos/gravação**</span><span class="sxs-lookup"><span data-stu-id="46ad9-128">**Avg. microsec/Write**</span></span>|<span data-ttu-id="46ad9-129">O número médio de microssegundos que leva para realizar cada gravação no armazenamento HTTP.</span><span class="sxs-lookup"><span data-stu-id="46ad9-129">The average number of microseconds it takes to do each write to the HTTP storage.</span></span>|  
|<span data-ttu-id="46ad9-130">**Média de microssegundos/transferência**</span><span class="sxs-lookup"><span data-stu-id="46ad9-130">**Avg. microsec/Transfer**</span></span>|<span data-ttu-id="46ad9-131">O número médio de microssegundos que leva para realizar cada transferência para o armazenamento HTTP.</span><span class="sxs-lookup"><span data-stu-id="46ad9-131">The average number of microseconds it takes to do each transfer to the HTTP storage.</span></span>|  
|<span data-ttu-id="46ad9-132">**E/S de armazenamento HTTP pendente**</span><span class="sxs-lookup"><span data-stu-id="46ad9-132">**Outstanding HTTP Storage I/O**</span></span>|<span data-ttu-id="46ad9-133">O número total de E/S pendente para um armazenamento HTTP.</span><span class="sxs-lookup"><span data-stu-id="46ad9-133">The total number of outstanding I/Os towards a HTTP storage.</span></span>|  
|<span data-ttu-id="46ad9-134">**Repetição de e/s de Armazenamento HTTP/s**</span><span class="sxs-lookup"><span data-stu-id="46ad9-134">**HTTP Storage I/O Retry/sec**</span></span>|<span data-ttu-id="46ad9-135">Número de solicitações de tentativa enviadas para o armazenamento HTTP por segundo.</span><span class="sxs-lookup"><span data-stu-id="46ad9-135">Number of retry requests sent to the HTTP storage per second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46ad9-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46ad9-136">See Also</span></span>  
 [<span data-ttu-id="46ad9-137">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="46ad9-137">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  