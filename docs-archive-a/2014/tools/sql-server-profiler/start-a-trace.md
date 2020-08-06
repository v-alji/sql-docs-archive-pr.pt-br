---
title: Iniciar um rastreamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, stopping traces
- pausing traces
- Profiler [SQL Server Profiler], stopping traces
- Profiler [SQL Server Profiler], starting traces
- traces [SQL Server], starting
- SQL Server Profiler, pausing traces
- traces [SQL Server], stopping
- Profiler [SQL Server Profiler], pausing traces
- traces [SQL Server], pausing
- SQL Server Profiler, starting traces
- stopping traces
- starting traces
ms.assetid: aeeb38eb-229a-4c8b-ad66-57e9ce45fb6a
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2b75519631269a1213077a4e295ac73fca1b950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681991"
---
# <a name="start-a-trace"></a><span data-ttu-id="760fa-102">Iniciar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="760fa-102">Start a Trace</span></span>
  <span data-ttu-id="760fa-103">Após definir um novo rastreamento ou criar um modelo usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], você pode iniciar, pausar ou interromper a captura de dados usando a nova definição ou modelo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="760fa-103">After you have defined a new trace or created a template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can start, pause, or stop capturing data by using the new trace definition or template.</span></span>  
  
## <a name="starting-a-trace"></a><span data-ttu-id="760fa-104">Iniciando um rastreamento</span><span class="sxs-lookup"><span data-stu-id="760fa-104">Starting a Trace</span></span>  
 <span data-ttu-id="760fa-105">Quando se inicia um rastreamento e a origem definida é uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ou do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cria uma fila que fornece um local de guarda temporária para os eventos de servidor capturados.</span><span class="sxs-lookup"><span data-stu-id="760fa-105">When you start a trace and the defined source is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates a queue that provides a temporary holding place for captured server events.</span></span>  
  
 <span data-ttu-id="760fa-106">Quando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] é utilizado para acessar o Rastreamento do SQL, uma nova janela de rastreamento é aberta (se já não houver uma) quando o rastreamento é iniciado e os dados são capturados imediatamente.</span><span class="sxs-lookup"><span data-stu-id="760fa-106">When you use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to access SQL Trace, a new trace window opens (if one is not already open) when a trace is started, and data is immediately captured.</span></span>  
  
 <span data-ttu-id="760fa-107">Quando se usam procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)] do sistema para acessar o Rastreamento do SQL, é necessário iniciar um rastreamento toda vez que uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é iniciada para a captura de dados.</span><span class="sxs-lookup"><span data-stu-id="760fa-107">When you use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to access SQL Trace, you must start a trace every time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts for data to be captured.</span></span> <span data-ttu-id="760fa-108">Depois que um rastreamento é iniciado, só é possível modificar seu nome.</span><span class="sxs-lookup"><span data-stu-id="760fa-108">When a trace has been started, you can modify only the name of the trace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="760fa-109">Ao trabalhar com rastreamentos existentes, você pode exibir as propriedades, mas não pode modificá-las.</span><span class="sxs-lookup"><span data-stu-id="760fa-109">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="760fa-110">Para modificar as propriedades, interrompa ou pause o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="760fa-110">To modify the properties, stop or pause the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760fa-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="760fa-111">See Also</span></span>  
 <span data-ttu-id="760fa-112">[Iniciar um rastreamento automaticamente após a conexão com um servidor &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="760fa-112">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="760fa-113">[Pausar um &#40;de rastreamento SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="760fa-113">[Pause a Trace &#40;SQL Server Profiler&#41;](pause-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="760fa-114">[Interromper um &#40;de rastreamento SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="760fa-114">[Stop a Trace &#40;SQL Server Profiler&#41;](stop-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="760fa-115">[Limpar uma janela de rastreamento &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="760fa-115">[Clear a Trace Window &#40;SQL Server Profiler&#41;](clear-a-trace-window-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="760fa-116">Executar um rastreamento que foi pausado ou interrompido &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="760fa-116">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
  
