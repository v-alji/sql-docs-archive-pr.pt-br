---
title: Reproduzir para um cursor (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- replaying cursors
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 89eadc41-4424-4a1c-ba61-0b52c851cdb1
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfc5ba06b60100bf8ecc8d04909371021a5b00e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683831"
---
# <a name="replay-to-a-cursor-sql-server-profiler"></a><span data-ttu-id="c8589-102">Repetir até um cursor (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c8589-102">Replay to a Cursor (SQL Server Profiler)</span></span>
  <span data-ttu-id="c8589-103">Este tópico descreve como repetir arquivos ou tabelas de rastreamento e pausar quando um cursor for atingido, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8589-103">This topic describes how to replay trace files or tables that pause when a cursor is reached by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="c8589-104">Pausar rastreamentos mediante cursores dá suporte à depuração, pois é possível dividir a repetição de scripts de rastreamento longos em segmentos curtos que podem ser analisados incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="c8589-104">Pausing traces at cursors supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-the-cursor"></a><span data-ttu-id="c8589-105">Para repetir até o cursor</span><span class="sxs-lookup"><span data-stu-id="c8589-105">To replay to the cursor</span></span>  
  
1.  <span data-ttu-id="c8589-106">Abra o arquivo ou tabela de rastreamento que deseja repetir.</span><span class="sxs-lookup"><span data-stu-id="c8589-106">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="c8589-107">Para obter mais informações, consulte [Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou do [Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="c8589-107">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="c8589-108">Certifique-se de que o arquivo ou tabela de rastreamento aberto contém as classes de evento necessárias para a repetição.</span><span class="sxs-lookup"><span data-stu-id="c8589-108">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="c8589-109">Para obter mais informações, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8589-109">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="c8589-110">Na janela do rastreamento, clique em um evento.</span><span class="sxs-lookup"><span data-stu-id="c8589-110">In the trace window, click an event.</span></span>  
  
3.  <span data-ttu-id="c8589-111">No menu **Reprodução** , clique em **Executar até Cursor**e conecte-se ao servidor em que deseja reproduzir o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c8589-111">On the **Replay** menu, click **Run to Cursor**, and then connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="c8589-112">Na caixa de diálogo **Configuração de Repetição** , verifique as definições e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8589-112">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c8589-113">A repetição é iniciada, sendo pausada quando o primeiro cursor é atingido.</span><span class="sxs-lookup"><span data-stu-id="c8589-113">The replay starts, pausing when the first cursor is reached.</span></span>  
  
5.  <span data-ttu-id="c8589-114">Pressione F5 para retomar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c8589-114">Press F5 to resume the trace.</span></span>  
  
6.  <span data-ttu-id="c8589-115">Repita a Etapa 5 até o término do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c8589-115">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8589-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8589-116">See Also</span></span>  
 <span data-ttu-id="c8589-117">[Reproduzir em um ponto de interrupção &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c8589-117">[Replay to a Breakpoint &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c8589-118">[Repetir rastreamentos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="c8589-118">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="c8589-119">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c8589-119">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
