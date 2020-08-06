---
title: SQL Server destinos de eventos estendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- extended events [SQL Server], targets
ms.assetid: e281684c-40d1-4cf9-a0d4-7ea1ecffa384
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 010b7cc29543f266b77aaf180c50173ef9f70346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569614"
---
# <a name="sql-server-extended-events-targets"></a><span data-ttu-id="7e528-102">SQL Server Extended Events Targets</span><span class="sxs-lookup"><span data-stu-id="7e528-102">SQL Server Extended Events Targets</span></span>
  <span data-ttu-id="7e528-103">Os destinos de Eventos Estendidos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] são consumidores de evento.</span><span class="sxs-lookup"><span data-stu-id="7e528-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events targets are event consumers.</span></span> <span data-ttu-id="7e528-104">Os destinos podem gravar em um arquivo, armazenar dados de evento em um buffer de memória ou agregar dados de evento.</span><span class="sxs-lookup"><span data-stu-id="7e528-104">Targets can write to a file, store event data in a memory buffer, or aggregate event data.</span></span> <span data-ttu-id="7e528-105">Os destinos podem processar dados de forma síncrona ou assíncrona.</span><span class="sxs-lookup"><span data-stu-id="7e528-105">Targets can process data synchronously or asynchronously.</span></span>  
  
 <span data-ttu-id="7e528-106">O design de Eventos Estendidos assegura que os destinos tenham a garantia de receber eventos somente uma vez por sessão.</span><span class="sxs-lookup"><span data-stu-id="7e528-106">The Extended Events design ensures that targets are guaranteed to receive events once and only once per session.</span></span>  
  
 <span data-ttu-id="7e528-107">Os Eventos Estendidos fornecem os seguintes destinos que você pode usar em uma sessão de Eventos Estendidos:</span><span class="sxs-lookup"><span data-stu-id="7e528-107">Extended Events provide the following targets that you can use for an Extended Events session:</span></span>  
  
-   [<span data-ttu-id="7e528-108">Contador de eventos</span><span class="sxs-lookup"><span data-stu-id="7e528-108">Event counter</span></span>](../../2014/database-engine/event-counter-target.md)  
  
     <span data-ttu-id="7e528-109">Conta todos os eventos especificados que ocorrem durante uma sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="7e528-109">Counts all specified events that occur during an Extended Events session.</span></span> <span data-ttu-id="7e528-110">Use para obter informações sobre as características da carga de trabalho sem adicionar a sobrecarga de uma coleção de eventos completa.</span><span class="sxs-lookup"><span data-stu-id="7e528-110">Use to obtain information about workload characteristics without adding the overhead of full event collection.</span></span> <span data-ttu-id="7e528-111">Este é um destino síncrono.</span><span class="sxs-lookup"><span data-stu-id="7e528-111">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="7e528-112">Arquivo de evento</span><span class="sxs-lookup"><span data-stu-id="7e528-112">Event file</span></span>](../../2014/database-engine/event-file-target.md)  
  
     <span data-ttu-id="7e528-113">Use para gravar a saída da sessão de evento de buffers de memória completos em disco.</span><span class="sxs-lookup"><span data-stu-id="7e528-113">Use to write event session output from complete memory buffers to disk.</span></span> <span data-ttu-id="7e528-114">Este é um destino assíncrono.</span><span class="sxs-lookup"><span data-stu-id="7e528-114">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="7e528-115">Emparelhamento de eventos</span><span class="sxs-lookup"><span data-stu-id="7e528-115">Event pairing</span></span>](../../2014/database-engine/event-pairing-target.md)  
  
     <span data-ttu-id="7e528-116">Muitos tipos de eventos ocorrem em pares, como aquisições e liberações de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="7e528-116">Many kinds of events occur in pairs, such as lock acquires and lock releases.</span></span> <span data-ttu-id="7e528-117">Use para determinar quando um evento emparelhado especificado não ocorre em um conjunto correspondente.</span><span class="sxs-lookup"><span data-stu-id="7e528-117">Use to determine when a specified paired event does not occur in a matched set.</span></span> <span data-ttu-id="7e528-118">Este é um destino assíncrono.</span><span class="sxs-lookup"><span data-stu-id="7e528-118">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="7e528-119">ETW (Rastreamento de Eventos para Windows)</span><span class="sxs-lookup"><span data-stu-id="7e528-119">Event Tracing for Windows (ETW)</span></span>](../relational-databases/extended-events/event-tracing-for-windows-target.md)  
  
     <span data-ttu-id="7e528-120">Use para correlacionar eventos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] com o sistema operacional Windows ou dados de eventos de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7e528-120">Use to correlate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events with Windows operating system or application event data.</span></span> <span data-ttu-id="7e528-121">Este é um destino síncrono.</span><span class="sxs-lookup"><span data-stu-id="7e528-121">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="7e528-122">Histograma</span><span class="sxs-lookup"><span data-stu-id="7e528-122">Histogram</span></span>](../../2014/database-engine/histogram-target.md)  
  
     <span data-ttu-id="7e528-123">Use para contar o número de vezes que um evento especificado ocorre com base em uma coluna de eventos ou uma ação específica.</span><span class="sxs-lookup"><span data-stu-id="7e528-123">Use to count the number of times that a specified event occurs, based on a specified event column or action.</span></span> <span data-ttu-id="7e528-124">Este é um destino assíncrono.</span><span class="sxs-lookup"><span data-stu-id="7e528-124">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="7e528-125">Buffer de anéis</span><span class="sxs-lookup"><span data-stu-id="7e528-125">Ring buffer</span></span>](../../2014/database-engine/ring-buffer-target.md)  
  
     <span data-ttu-id="7e528-126">Use para manter os dados do evento na memória em uma base PEPS (primeiro a entrar, primeiro a sair) ou em uma base PEPS por evento.</span><span class="sxs-lookup"><span data-stu-id="7e528-126">Use to hold the event data in memory on a first-in first-out (FIFO) basis, or on a per-event FIFO basis.</span></span> <span data-ttu-id="7e528-127">Este é um destino assíncrono.</span><span class="sxs-lookup"><span data-stu-id="7e528-127">This is an asynchronous target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e528-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e528-128">See Also</span></span>  
 <span data-ttu-id="7e528-129">[Eventos estendidos](../relational-databases/extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="7e528-129">[Extended Events](../relational-databases/extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="7e528-130">[SQL Server pacotes de eventos estendidos](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span><span class="sxs-lookup"><span data-stu-id="7e528-130">[SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span></span>  
 <span data-ttu-id="7e528-131">[SQL Server sessões de eventos estendidos](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="7e528-131">[SQL Server Extended Events Sessions](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span></span>  
 [<span data-ttu-id="7e528-132">Mecanismo de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e528-132">SQL Server Extended Events Engine</span></span>](../relational-databases/extended-events/sql-server-extended-events-engine.md)  
  
  
