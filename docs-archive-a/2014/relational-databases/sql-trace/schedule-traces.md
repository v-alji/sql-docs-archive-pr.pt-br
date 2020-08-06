---
title: Agendar rastreamentos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], events
- traces [SQL Server]
- traces [SQL Server], stopping
- events [SQL Server], filters
- scheduling traces [SQL Server]
- traces [SQL Server], scheduling
- stopping traces
ms.assetid: 620b79db-924b-4502-8af3-39efcfca245d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a698d88db35c84f7611293cf45807203c883865a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575763"
---
# <a name="schedule-traces"></a><span data-ttu-id="5d3e4-102">Agendar rastreamentos</span><span class="sxs-lookup"><span data-stu-id="5d3e4-102">Schedule Traces</span></span>
  <span data-ttu-id="5d3e4-103">Há dois modos de agendar rastreamentos no Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d3e4-103">There are two ways to schedule tracing in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5d3e4-104">Você pode:</span><span class="sxs-lookup"><span data-stu-id="5d3e4-104">You can:</span></span>  
  
-   <span data-ttu-id="5d3e4-105">Habilitar uma hora de parada do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="5d3e4-105">Enable a trace stop time.</span></span>  
  
-   <span data-ttu-id="5d3e4-106">Usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para agendar um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="5d3e4-106">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to schedule a trace.</span></span>  
  
## <a name="specifying-a-stop-time"></a><span data-ttu-id="5d3e4-107">Especificando uma hora de parada</span><span class="sxs-lookup"><span data-stu-id="5d3e4-107">Specifying a Stop Time</span></span>  
 <span data-ttu-id="5d3e4-108">Você poderá especificar uma hora de parada do rastreamento se usar procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)] ou o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d3e4-108">You can specify a trace stop time if you use [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures or if you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="5d3e4-109">A hora de parada deve ser definida quando o rastreamento é originalmente configurado.</span><span class="sxs-lookup"><span data-stu-id="5d3e4-109">The stop time must be set when the trace is originally configured.</span></span>  
  
## <a name="scheduling-traces-by-using-sql-server-agent"></a><span data-ttu-id="5d3e4-110">Agendando rastreamentos usando o SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="5d3e4-110">Scheduling Traces by Using SQL Server Agent</span></span>  
 <span data-ttu-id="5d3e4-111">A melhor maneira de agendar rastreamentos é usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para iniciar o rastreamento e especificar uma hora de parada, por meio do procedimento armazenado [!INCLUDE[tsql](../../includes/tsql-md.md)]**sp_trace_setstatus**ou do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d3e4-111">The best way to schedule traces is to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to start the trace and then specify a trace stop time by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure **sp_trace_setstatus**, or [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="5d3e4-112">**Para definir um filtro de hora de término para um rastreamento**</span><span class="sxs-lookup"><span data-stu-id="5d3e4-112">**To set an end time filter for a trace**</span></span>  
  
 [<span data-ttu-id="5d3e4-113">Filtrar eventos com base na hora de término do evento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="5d3e4-113">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
 [<span data-ttu-id="5d3e4-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5d3e4-114">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="5d3e4-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5d3e4-115">See Also</span></span>  
 [<span data-ttu-id="5d3e4-116">Tarefas de administração automatizadas &#40;SQL Server Agent&#41;</span><span class="sxs-lookup"><span data-stu-id="5d3e4-116">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../../ssms/agent/sql-server-agent.md)  
  
  
