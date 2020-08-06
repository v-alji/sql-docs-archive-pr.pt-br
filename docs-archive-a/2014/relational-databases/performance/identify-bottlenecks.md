---
title: Identificar afunilamentos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource bottlenecks [SQL Server]
- database monitoring [SQL Server], bottlenecks
- performance [SQL Server], bottlenecks
- tuning databases [SQL Server], bottlenecks
- monitoring server performance [SQL Server], bottlenecks
- monitoring performance [SQL Server], bottlenecks
- database performance [SQL Server], bottlenecks
- server performance [SQL Server], bottlenecks
- bottlenecks [SQL Server]
- identifying bottlenecks [SQL Server]
ms.assetid: db079e65-ee80-4105-aec9-f8230d0d6635
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e941b3f4a1185177cef007eb6a02a71ae1adece7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679307"
---
# <a name="identify-bottlenecks"></a><span data-ttu-id="bba2a-102">Identificar afunilamentos</span><span class="sxs-lookup"><span data-stu-id="bba2a-102">Identify Bottlenecks</span></span>
  <span data-ttu-id="bba2a-103">O acesso simultâneo a recursos compartilhados provoca gargalos.</span><span class="sxs-lookup"><span data-stu-id="bba2a-103">Simultaneous access to shared resources causes bottlenecks.</span></span> <span data-ttu-id="bba2a-104">Em geral, os gargalos estão presentes em todo sistema de software e são inevitáveis.</span><span class="sxs-lookup"><span data-stu-id="bba2a-104">In general, bottlenecks are present in every software system and are inevitable.</span></span> <span data-ttu-id="bba2a-105">Porém, demandas excessivas em recursos compartilhados causam um tempo de resposta ruim e devem ser identificadas e ajustadas.</span><span class="sxs-lookup"><span data-stu-id="bba2a-105">However, excessive demands on shared resources cause poor response time and must be identified and tuned.</span></span>  
  
 <span data-ttu-id="bba2a-106">São causas de gargalos:</span><span class="sxs-lookup"><span data-stu-id="bba2a-106">Causes of bottlenecks include:</span></span>  
  
-   <span data-ttu-id="bba2a-107">Recursos insuficientes, exigindo componentes adicionais ou atualizados.</span><span class="sxs-lookup"><span data-stu-id="bba2a-107">Insufficient resources, requiring additional or upgraded components.</span></span>  
  
-   <span data-ttu-id="bba2a-108">Recursos de mesmo tipo entre os quais as cargas de trabalho não são distribuídas de maneira uniforme; por exemplo, um disco sendo monopolizado.</span><span class="sxs-lookup"><span data-stu-id="bba2a-108">Resources of the same type among which workloads are not distributed evenly; for example, one disk is being monopolized.</span></span>  
  
-   <span data-ttu-id="bba2a-109">Mau funcionamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="bba2a-109">Malfunctioning resources.</span></span>  
  
-   <span data-ttu-id="bba2a-110">Recursos incorretamente configurados.</span><span class="sxs-lookup"><span data-stu-id="bba2a-110">Incorrectly configured resources.</span></span>  
  
## <a name="analyzing-bottlenecks"></a><span data-ttu-id="bba2a-111">Analisando afunilamentos</span><span class="sxs-lookup"><span data-stu-id="bba2a-111">Analyzing Bottlenecks</span></span>  
 <span data-ttu-id="bba2a-112">Durações excessivas de diversos eventos são indicadores de gargalos que podem ser ajustados.</span><span class="sxs-lookup"><span data-stu-id="bba2a-112">Excessive durations for various events are indicators of bottlenecks that can be tuned.</span></span>  
  
 <span data-ttu-id="bba2a-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bba2a-113">For example:</span></span>  
  
-   <span data-ttu-id="bba2a-114">Algum outro componente pode impedir a carga de alcançar esse componente e aumentar, assim, o tempo para a conclusão da carga.</span><span class="sxs-lookup"><span data-stu-id="bba2a-114">Some other component may prevent the load from reaching this component thereby increasing the time to complete the load.</span></span>  
  
-   <span data-ttu-id="bba2a-115">Solicitações de clientes podem levar mais tempo devido a congestionamento da rede.</span><span class="sxs-lookup"><span data-stu-id="bba2a-115">Client requests may take longer due to network congestion.</span></span>  
  
 <span data-ttu-id="bba2a-116">A seguir, encontram-se cinco grandes áreas a monitorar, ao rastrear o desempenho do servidor, para identificar gargalos.</span><span class="sxs-lookup"><span data-stu-id="bba2a-116">Following are five key areas to monitor when tracking server performance to identify bottlenecks.</span></span>  
  
|<span data-ttu-id="bba2a-117">Possível área de gargalo</span><span class="sxs-lookup"><span data-stu-id="bba2a-117">Possible bottleneck area</span></span>|<span data-ttu-id="bba2a-118">Efeitos no servidor</span><span class="sxs-lookup"><span data-stu-id="bba2a-118">Effects on the server</span></span>|  
|------------------------------|---------------------------|  
|<span data-ttu-id="bba2a-119">Uso de memória</span><span class="sxs-lookup"><span data-stu-id="bba2a-119">Memory usage</span></span>|<span data-ttu-id="bba2a-120">Memória insuficiente alocado ou disponível para o Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degrada o desempenho.</span><span class="sxs-lookup"><span data-stu-id="bba2a-120">Insufficient memory allocated or available to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] degrades performance.</span></span> <span data-ttu-id="bba2a-121">Os dados têm que ser lidos do disco, em vez de diretamente do cache de dados.</span><span class="sxs-lookup"><span data-stu-id="bba2a-121">Data must be read from the disk rather than directly from the data cache.</span></span> <span data-ttu-id="bba2a-122">Sistemas operacionais Microsoft Windows executam paginação excessiva, permutando dados de e para o disco, segundo a necessidade de páginas.</span><span class="sxs-lookup"><span data-stu-id="bba2a-122">Microsoft Windows operating systems perform excessive paging by swapping data to and from the disk as the pages are needed.</span></span>|  
|<span data-ttu-id="bba2a-123">Utilização da CPU</span><span class="sxs-lookup"><span data-stu-id="bba2a-123">CPU utilization</span></span>|<span data-ttu-id="bba2a-124">Uma taxa de utilização de CPU cronicamente alta pode indicar que as consultas do [!INCLUDE[tsql](../../includes/tsql-md.md)] precisam ser ajustadas ou que é necessário atualizar a CPU.</span><span class="sxs-lookup"><span data-stu-id="bba2a-124">A chronically high CPU utilization rate may indicate that [!INCLUDE[tsql](../../includes/tsql-md.md)] queries need to be tuned or that a CPU upgrade is needed.</span></span>|  
|<span data-ttu-id="bba2a-125">Entrada/saída (E/S) de disco</span><span class="sxs-lookup"><span data-stu-id="bba2a-125">Disk input/output (I/O)</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="bba2a-126">consultas podem ser ajustadas de modo a reduzir E/S desnecessária; por exemplo, empregando índices.</span><span class="sxs-lookup"><span data-stu-id="bba2a-126">queries can be tuned to reduce unnecessary I/O; for example, by employing indexes.</span></span>|  
|<span data-ttu-id="bba2a-127">Conexões de usuário</span><span class="sxs-lookup"><span data-stu-id="bba2a-127">User connections</span></span>|<span data-ttu-id="bba2a-128">Muitos usuários podem estar acessando o servidor simultaneamente, provocando degradação do desempenho.</span><span class="sxs-lookup"><span data-stu-id="bba2a-128">Too many users may be accessing the server simultaneously causing performance degradation.</span></span>|  
|<span data-ttu-id="bba2a-129">Bloqueios</span><span class="sxs-lookup"><span data-stu-id="bba2a-129">Blocking locks</span></span>|<span data-ttu-id="bba2a-130">Aplicativos incorretamente projetados podem causar bloqueios e obstruir a simultaneidade, causando tempos de resposta mais longos e taxas de transferência de transações mais baixas.</span><span class="sxs-lookup"><span data-stu-id="bba2a-130">Incorrectly designed applications can cause locks and hamper concurrency, thus causing longer response times and lower transaction throughput rates.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bba2a-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bba2a-131">See Also</span></span>  
 <span data-ttu-id="bba2a-132">[Monitorar o uso da CPU](../performance-monitor/monitor-cpu-usage.md) </span><span class="sxs-lookup"><span data-stu-id="bba2a-132">[Monitor CPU Usage](../performance-monitor/monitor-cpu-usage.md) </span></span>  
 <span data-ttu-id="bba2a-133">[Monitorar o uso do disco](../performance-monitor/monitor-disk-usage.md) </span><span class="sxs-lookup"><span data-stu-id="bba2a-133">[Monitor Disk Usage](../performance-monitor/monitor-disk-usage.md) </span></span>  
 <span data-ttu-id="bba2a-134">[Monitorar o uso da memória](../performance-monitor/monitor-memory-usage.md) </span><span class="sxs-lookup"><span data-stu-id="bba2a-134">[Monitor Memory Usage](../performance-monitor/monitor-memory-usage.md) </span></span>  
 <span data-ttu-id="bba2a-135">[SQL Server, objeto General Statistics](../performance-monitor/sql-server-general-statistics-object.md) </span><span class="sxs-lookup"><span data-stu-id="bba2a-135">[SQL Server, General Statistics Object](../performance-monitor/sql-server-general-statistics-object.md) </span></span>  
 [<span data-ttu-id="bba2a-136">SQL Server, objeto Locks</span><span class="sxs-lookup"><span data-stu-id="bba2a-136">SQL Server, Locks Object</span></span>](../performance-monitor/sql-server-locks-object.md)  
  
  
