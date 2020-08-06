---
title: Reproduzir um único evento de cada vez (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- events [SQL Server], replaying single event at a time
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 220fb192-9636-41a2-b15c-62af6cab8fff
author: stevestein
ms.author: sstein
ms.openlocfilehash: 457bc94d9d8eae470fb60b450d30441c07e676df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683841"
---
# <a name="replay-a-single-event-at-a-time-sql-server-profiler"></a><span data-ttu-id="8fab6-102">Repetir um único evento de cada vez (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="8fab6-102">Replay a Single Event at a Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="8fab6-103">Este tópico descreve como repetir um evento de cada vez em um arquivo ou tabela de rastreamento de repetição usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fab6-103">This topic describes how to replay one event at a time in a replay trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-replay-a-single-event-at-a-time"></a><span data-ttu-id="8fab6-104">Para repetir um único evento de cada vez</span><span class="sxs-lookup"><span data-stu-id="8fab6-104">To replay a single event at a time</span></span>  
  
1.  <span data-ttu-id="8fab6-105">Abra o arquivo ou tabela de rastreamento que deseja repetir.</span><span class="sxs-lookup"><span data-stu-id="8fab6-105">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="8fab6-106">Para obter mais informações, consulte [Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou do [Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="8fab6-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="8fab6-107">Certifique-se de que o arquivo ou tabela de rastreamento aberto contém as classes de evento necessárias para a repetição.</span><span class="sxs-lookup"><span data-stu-id="8fab6-107">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="8fab6-108">Para obter mais informações, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fab6-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="8fab6-109">No menu **Repetir** , clique em **Etapa**e conecte-se à instância de servidor em que deseja repetir o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8fab6-109">On the **Replay** menu, click **Step**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="8fab6-110">Na caixa de diálogo **Configuração de Repetição** , verifique as definições e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fab6-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span> <span data-ttu-id="8fab6-111">Para obter mais informações sobre como especificar configurações na caixa de diálogo **Configuração de Reprodução**, consulte [Repetir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) ou [Repetir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="8fab6-111">For more information about specifying settings on the **Replay Configuration** dialog box, see [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) or [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span></span>  
  
4.  <span data-ttu-id="8fab6-112">Para repetir o primeiro evento, clique em **OK** na caixa de diálogo **Configuração de Repetição** .</span><span class="sxs-lookup"><span data-stu-id="8fab6-112">To replay the first event, click **OK** in the **Replay Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="8fab6-113">Para repetir eventos subsequentes, no menu **Repetir** , clique em **Etapa**ou pressione F10.</span><span class="sxs-lookup"><span data-stu-id="8fab6-113">To replay subsequent events, on the **Replay** menu, click **Step**, or press F10.</span></span> <span data-ttu-id="8fab6-114">Continue clicando em **Etapa** ou pressionando F10 para cada evento.</span><span class="sxs-lookup"><span data-stu-id="8fab6-114">Repeat clicking **Step** or pressing F10 for each event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fab6-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8fab6-115">See Also</span></span>  
 <span data-ttu-id="8fab6-116">[Repetir rastreamentos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="8fab6-116">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="8fab6-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8fab6-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
