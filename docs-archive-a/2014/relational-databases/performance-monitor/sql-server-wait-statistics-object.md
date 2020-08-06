---
title: SQL Server, objeto Estatística de espera | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Wait Statistics object
- SQLServer:Wait Statistics
ms.assetid: cb7f917d-4291-4115-9b78-ee7692ebbb2d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfd2f1309cb118896ff7951b7f82feb38de60e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679310"
---
# <a name="sql-server-wait-statistics-object"></a><span data-ttu-id="92593-102">SQL Server, Objeto Wait Statistics</span><span class="sxs-lookup"><span data-stu-id="92593-102">SQL Server, Wait Statistics Object</span></span>
  <span data-ttu-id="92593-103">O objeto de desempenho **SQLServer:Wait Statistics** contém contadores de desempenho que relatam informações sobre o status de espera.</span><span class="sxs-lookup"><span data-stu-id="92593-103">The **SQLServer:Wait Statistics** performance object contains performance counters that report information about wait status.</span></span>  
  
 <span data-ttu-id="92593-104">A tabela a seguir lista os contadores contidos no objeto Wait Statistics (Estatísticas de Espera).</span><span class="sxs-lookup"><span data-stu-id="92593-104">The table below lists the counters that the Wait Statistics object contains.</span></span>  
  
|<span data-ttu-id="92593-105">Contadores de Estatísticas de Espera do SQL Server</span><span class="sxs-lookup"><span data-stu-id="92593-105">SQL Server Wait Statistics counters</span></span>|<span data-ttu-id="92593-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="92593-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="92593-107">**Esperas de bloqueio**</span><span class="sxs-lookup"><span data-stu-id="92593-107">**Lock waits**</span></span>|<span data-ttu-id="92593-108">Estatísticas dos processos que esperam por um bloqueio.</span><span class="sxs-lookup"><span data-stu-id="92593-108">Statistics for processes waiting on a lock.</span></span>|  
|<span data-ttu-id="92593-109">**Esperas de buffer de log**</span><span class="sxs-lookup"><span data-stu-id="92593-109">**Log buffer waits**</span></span>|<span data-ttu-id="92593-110">Estatísticas dos processos que esperam pela disponibilização de buffer de log.</span><span class="sxs-lookup"><span data-stu-id="92593-110">Statistics for processes waiting for log buffer to be available.</span></span>|  
|<span data-ttu-id="92593-111">**Esperas de gravação de log**</span><span class="sxs-lookup"><span data-stu-id="92593-111">**Log write waits**</span></span>|<span data-ttu-id="92593-112">Estatísticas dos processos que esperam por buffer de log para serem gravados.</span><span class="sxs-lookup"><span data-stu-id="92593-112">Statistics for processes waiting for log buffer to be written.</span></span>|  
|<span data-ttu-id="92593-113">**Tempo de espera em fila para concessão de memória**</span><span class="sxs-lookup"><span data-stu-id="92593-113">**Memory grant queue waits**</span></span>|<span data-ttu-id="92593-114">Estatísticas dos processos que esperam por concessão de memória para ficarem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="92593-114">Statistics for processes waiting for memory grant to become available.</span></span>|  
|<span data-ttu-id="92593-115">**Esperas de E/S de rede**</span><span class="sxs-lookup"><span data-stu-id="92593-115">**Network IO waits**</span></span>|<span data-ttu-id="92593-116">Estatísticas pertinentes às esperas de E/S de rede.</span><span class="sxs-lookup"><span data-stu-id="92593-116">Statistics relevant to wait on network I/O.</span></span>|  
|<span data-ttu-id="92593-117">**Esperas de travas sem-página**</span><span class="sxs-lookup"><span data-stu-id="92593-117">**Non-Page latch waits**</span></span>|<span data-ttu-id="92593-118">Estatísticas pertinentes a travas sem-página.</span><span class="sxs-lookup"><span data-stu-id="92593-118">Statistics relevant to non-page latches.</span></span>|  
|<span data-ttu-id="92593-119">**Esperas de travas de E/S de página**</span><span class="sxs-lookup"><span data-stu-id="92593-119">**Page IO latch waits**</span></span>|<span data-ttu-id="92593-120">Estatísticas pertinentes a travas de E/S de página.</span><span class="sxs-lookup"><span data-stu-id="92593-120">Statistics relevant to page I/O latches.</span></span>|  
|<span data-ttu-id="92593-121">**Esperas de trava de página**</span><span class="sxs-lookup"><span data-stu-id="92593-121">**Page latch waits**</span></span>|<span data-ttu-id="92593-122">Estatísticas pertinentes a travas de página, excluindo-se travas de E/S.</span><span class="sxs-lookup"><span data-stu-id="92593-122">Statistics relevant to page latches, not including I/O latches.</span></span>|  
|<span data-ttu-id="92593-123">**Espera de objetos de memória isenta de threads**</span><span class="sxs-lookup"><span data-stu-id="92593-123">**Thread-safe memory objects waits**</span></span>|<span data-ttu-id="92593-124">Estatísticas dos processos que esperam alocadores de memória isenta de threads.</span><span class="sxs-lookup"><span data-stu-id="92593-124">Statistics for processes waiting on thread-safe memory allocators.</span></span>|  
|<span data-ttu-id="92593-125">**Esperas de propriedade de transação**</span><span class="sxs-lookup"><span data-stu-id="92593-125">**Transaction ownership waits**</span></span>|<span data-ttu-id="92593-126">Estatísticas pertinentes a processos de sincronização de acesso à transação.</span><span class="sxs-lookup"><span data-stu-id="92593-126">Statistics relevant to processes synchronizing access to transaction.</span></span>|  
|<span data-ttu-id="92593-127">**Espera pelo trabalhador**</span><span class="sxs-lookup"><span data-stu-id="92593-127">**Wait for the worker**</span></span>|<span data-ttu-id="92593-128">Estatísticas pertinentes a processos que esperam pela disponibilização do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="92593-128">Statistics relevant to processes waiting for worker to become available.</span></span>|  
|<span data-ttu-id="92593-129">**Esperas da sincronização do workspace**</span><span class="sxs-lookup"><span data-stu-id="92593-129">**Workspace synchronization waits**</span></span>|<span data-ttu-id="92593-130">Estatísticas pertinentes a processos de sincronização de acesso ao workspace.</span><span class="sxs-lookup"><span data-stu-id="92593-130">Statistics relevant to processes synchronizing access to workspace.</span></span>|  
  
 <span data-ttu-id="92593-131">Cada contador no objeto contém as seguintes instâncias:</span><span class="sxs-lookup"><span data-stu-id="92593-131">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="92593-132">Item</span><span class="sxs-lookup"><span data-stu-id="92593-132">Item</span></span>|<span data-ttu-id="92593-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="92593-133">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="92593-134">**Tempo de espera médio (ms)**</span><span class="sxs-lookup"><span data-stu-id="92593-134">**Average wait time (ms)**</span></span>|<span data-ttu-id="92593-135">Tempo médio do tipo de espera selecionado.</span><span class="sxs-lookup"><span data-stu-id="92593-135">Average time for the selected type of wait.</span></span>|  
|<span data-ttu-id="92593-136">**Tempo de espera cumulativo (ms) por segundo**</span><span class="sxs-lookup"><span data-stu-id="92593-136">**Cumulative wait time (ms) per second**</span></span>|<span data-ttu-id="92593-137">Tempo de espera agregado, por segundo, do tipo de espera selecionado.</span><span class="sxs-lookup"><span data-stu-id="92593-137">Aggregated wait time per second, for the selected type of wait.</span></span>|  
|<span data-ttu-id="92593-138">**Esperas em andamento**</span><span class="sxs-lookup"><span data-stu-id="92593-138">**Waits in progress**</span></span>|<span data-ttu-id="92593-139">Número de processos que esperam atualmente pelo tipo seguinte.</span><span class="sxs-lookup"><span data-stu-id="92593-139">Number of processes currently waiting on the following type.</span></span>|  
|<span data-ttu-id="92593-140">**Esperas iniciadas por segundo**</span><span class="sxs-lookup"><span data-stu-id="92593-140">**Waits started per second**</span></span>|<span data-ttu-id="92593-141">Número de esperas iniciadas, por segundo, do tipo de espera selecionado.</span><span class="sxs-lookup"><span data-stu-id="92593-141">Number of waits started per second of the selected type of wait.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92593-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92593-142">See Also</span></span>  
 [<span data-ttu-id="92593-143">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="92593-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
