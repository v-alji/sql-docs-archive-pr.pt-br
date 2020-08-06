---
title: Reproduzir para um ponto de interrupção (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- breakpoints [SQL Server]
- traces [SQL Server], replaying
ms.assetid: 3caf751e-df3b-40c7-b5e8-4490ae178e0c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f33b6862847b042a2613d8c2aa035dd5805493ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683832"
---
# <a name="replay-to-a-breakpoint-sql-server-profiler"></a><span data-ttu-id="a02b0-102">Repetir até um ponto de interrupção (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a02b0-102">Replay to a Breakpoint (SQL Server Profiler)</span></span>
  <span data-ttu-id="a02b0-103">Este tópico descreve como definir pontos de interrupção em um arquivo ou tabela de rastreamento que se deseja repetir, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a02b0-103">This topic describes how to set breakpoints in a trace file or table that you want to replay by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="a02b0-104">Definir pontos de interrupção em um arquivo ou tabela de rastreamento antes de dar início à repetição do rastreamento permite que você pause a repetição em eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="a02b0-104">Setting breakpoints in a trace file or table before you start to replay the trace, enables you to pause replay of the trace at specific events.</span></span> <span data-ttu-id="a02b0-105">Usar pontos de interrupção ao repetir um rastreamento dá suporte à depuração, pois é possível dividir a repetição de scripts de rastreamento longos em segmentos curtos que podem ser analisados incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="a02b0-105">Using breakpoints while replaying a trace supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-a-breakpoint"></a><span data-ttu-id="a02b0-106">Para repetir até um ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="a02b0-106">To replay to a breakpoint</span></span>  
  
1.  <span data-ttu-id="a02b0-107">Abra o arquivo ou tabela de rastreamento que deseja repetir.</span><span class="sxs-lookup"><span data-stu-id="a02b0-107">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="a02b0-108">Para obter mais informações, consulte [Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou do [Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="a02b0-108">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="a02b0-109">Certifique-se de que o arquivo ou tabela de rastreamento aberto contém as classes de evento necessárias para a repetição.</span><span class="sxs-lookup"><span data-stu-id="a02b0-109">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="a02b0-110">Para obter mais informações, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a02b0-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="a02b0-111">Na janela de rastreamento, clique em um evento que você deseje usar como ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="a02b0-111">In the trace window, click an event that you want to use as a breakpoint.</span></span> <span data-ttu-id="a02b0-112">Use um destes três métodos para definir um ponto de interrupção:</span><span class="sxs-lookup"><span data-stu-id="a02b0-112">Use one of the following three methods to set a breakpoint:</span></span>  
  
    -   <span data-ttu-id="a02b0-113">Pressione F9.</span><span class="sxs-lookup"><span data-stu-id="a02b0-113">Press F9.</span></span>  
  
    -   <span data-ttu-id="a02b0-114">No menu **Repetir** , clique em **Alternar Ponto de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="a02b0-114">On the **Replay** menu, click **Toggle Breakpoint**.</span></span>  
  
    -   <span data-ttu-id="a02b0-115">Clique com o botão direito do mouse no evento e clique em **Alternar Ponto de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="a02b0-115">Right-click the event, and then click **Toggle Breakpoint**.</span></span>  
  
     <span data-ttu-id="a02b0-116">Um marcador vermelho aparecerá próximo ao evento de rastreamento selecionado, indicando que se trata de um ponto de interrupção do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a02b0-116">A red bullet appears next to the selected trace event, indicating that it is the trace breakpoint.</span></span>  
  
     <span data-ttu-id="a02b0-117">Repita essa etapa para definir vários pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="a02b0-117">Repeat this step to set several breakpoints.</span></span>  
  
3.  <span data-ttu-id="a02b0-118">No menu **Repetir** , clique em **Iniciar**e conecte-se ao servidor em que deseja repetir o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a02b0-118">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="a02b0-119">Na caixa de diálogo **Configuração de Repetição** , verifique as definições e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a02b0-119">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a02b0-120">A repetição tem início, sendo pausada quando o ponto de interrupção é alcançado.</span><span class="sxs-lookup"><span data-stu-id="a02b0-120">The replay starts, pausing when the breakpoint is reached.</span></span>  
  
5.  <span data-ttu-id="a02b0-121">Pressione F5 para retomar a repetição e prosseguir até o próximo ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="a02b0-121">Press F5 to resume the replay and proceed to the next breakpoint.</span></span>  
  
6.  <span data-ttu-id="a02b0-122">Repita a Etapa 5 até o término do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a02b0-122">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a02b0-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a02b0-123">See Also</span></span>  
 <span data-ttu-id="a02b0-124">[Reproduzir para um cursor &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="a02b0-124">[Replay to a Cursor &#40;SQL Server Profiler&#41;](replay-to-a-cursor-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="a02b0-125">[Repetir rastreamentos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="a02b0-125">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="a02b0-126">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a02b0-126">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
