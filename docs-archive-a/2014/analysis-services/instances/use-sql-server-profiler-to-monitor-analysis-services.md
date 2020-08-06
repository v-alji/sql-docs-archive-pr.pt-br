---
title: Usar SQL Server Profiler para monitorar Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- performance [Analysis Services], SQL Server Profiler
- Profiler [SQL Server Profiler], Analysis Services
ms.assetid: 8b77dafc-4584-4e93-8ad7-299304391bfd
author: minewiskan
ms.author: owend
ms.openlocfilehash: e144c1d858670f8a46b164ffc9885e6e082c4b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570965"
---
# <a name="use-sql-server-profiler-to-monitor-analysis-services"></a><span data-ttu-id="4d307-102">Use SQL Server Profiler to Monitor Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d307-102">Use SQL Server Profiler to Monitor Analysis Services</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="4d307-103">controla eventos do processo de mecanismo, como início de um lote ou de uma transação, e captura dados sobre esses eventos, permitindo que você monitore o servidor e a atividade do banco de dados (por exemplo, consultas do usuário ou atividade de logon).</span><span class="sxs-lookup"><span data-stu-id="4d307-103">tracks engine process events, such as the start of a batch or a transaction, and it captures data about those events, thus enabling you to monitor server and database activity (for example, user queries or login activity).</span></span> <span data-ttu-id="4d307-104">Você pode capturar dados do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou de um arquivo para análise posterior e também pode reproduzir os eventos capturados na mesma ou em outra instância [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para ver o que aconteceu exatamente.</span><span class="sxs-lookup"><span data-stu-id="4d307-104">You can capture [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] data to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or a file for later analysis, and you can also replay the events captured on the same or another [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to see exactly what happened.</span></span> <span data-ttu-id="4d307-105">Você pode reproduzir os eventos em tempo real ou passo a passo.</span><span class="sxs-lookup"><span data-stu-id="4d307-105">You can replay events in real time or on a step-by-step basis.</span></span> <span data-ttu-id="4d307-106">Também é muito útil para executar os eventos de rastreamento junto com os contadores de Desempenho na mesma máquina.</span><span class="sxs-lookup"><span data-stu-id="4d307-106">It is also very useful to run the trace events along with the Performance counters on the same machine.</span></span> <span data-ttu-id="4d307-107">O profiler pode correlacionar esses dois eventos com base na hora e exibi-los ao longo de uma única linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="4d307-107">The profiler can correlate these two based on time and display them together along a single timeline.</span></span> <span data-ttu-id="4d307-108">Eventos de rastreamento darão a você mais detalhes enquanto os contadores de Desempenho proporcionam uma exibição de agregação.</span><span class="sxs-lookup"><span data-stu-id="4d307-108">Trace events will give you more details while Performance counters give you an aggregate view.</span></span> <span data-ttu-id="4d307-109">Para obter informações sobre como criar e executar rastreamentos, consulte [Criar rastreamentos do Profiler para reprodução &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="4d307-109">For information about how to create and run traces, see [Create Profiler Traces for Replay &#40;Analysis Services&#41;](create-profiler-traces-for-replay-analysis-services.md).</span></span>  
  
 <span data-ttu-id="4d307-110">A tabela a seguir descreve os tópicos dessa seção.</span><span class="sxs-lookup"><span data-stu-id="4d307-110">The following table describes the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d307-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4d307-111">In This Section</span></span>  
  
|<span data-ttu-id="4d307-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="4d307-112">Topic</span></span>|<span data-ttu-id="4d307-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d307-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4d307-114">Introdução ao monitoramento do Analysis Services com o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4d307-114">Introduction to Monitoring Analysis Services with SQL Server Profiler</span></span>](introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)|<span data-ttu-id="4d307-115">Descreve como usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para monitorar uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d307-115">Describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to monitor an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>|  
|[<span data-ttu-id="4d307-116">Criar rastreamentos do Profiler para reprodução &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4d307-116">Create Profiler Traces for Replay &#40;Analysis Services&#41;</span></span>](create-profiler-traces-for-replay-analysis-services.md)|<span data-ttu-id="4d307-117">Descreve os requisitos para criar um rastreamento para repetição usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d307-117">Describes the requirements for creating a trace for replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="4d307-118">Eventos de rastreamento do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d307-118">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)|<span data-ttu-id="4d307-119">Descreve as classes de evento do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d307-119">Describes [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] event classes.</span></span> <span data-ttu-id="4d307-120">Essas classes de evento mapeiam as ações geradas pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e são usadas para repetição de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="4d307-120">These event classes map to actions generated by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and are used for trace replays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d307-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d307-121">See Also</span></span>  
 [<span data-ttu-id="4d307-122">Monitorar uma instância do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d307-122">Monitor an Analysis Services Instance</span></span>](monitor-an-analysis-services-instance.md)  
  
  
