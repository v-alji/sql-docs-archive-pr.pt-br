---
title: Reproduzir rastreamentos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, replaying traces
- Run to Cursor option
- Toggle Breakpoint option
- traces [SQL Server], replaying
- replaying traces
- playback engine [SQL Server Profiler]
- events [SQL Server], replaying traces
- Profiler [SQL Server Profiler], replaying traces
ms.assetid: da958d3c-7f3e-44c9-aecc-8a9493bea7c0
author: stevestein
ms.author: sstein
ms.openlocfilehash: c485317d1343958f9c430b73d858130097d44d75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683830"
---
# <a name="replay-traces"></a><span data-ttu-id="57d67-102">Repetir rastreamentos</span><span class="sxs-lookup"><span data-stu-id="57d67-102">Replay Traces</span></span>
  <span data-ttu-id="57d67-103">Reprodução é a capacidade para reproduzir a atividade que foi capturada em um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="57d67-103">Replay is the ability to reproduce activity that has been captured in a trace.</span></span> <span data-ttu-id="57d67-104">Ao criar ou editar um rastreamento, você pode salvá-lo em um arquivo para reproduzi-lo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="57d67-104">When you create or edit a trace, you can save the trace to a file and replay it later.</span></span> <span data-ttu-id="57d67-105">Você pode usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para reproduzir a atividade de rastreamento de um único computador.</span><span class="sxs-lookup"><span data-stu-id="57d67-105">You can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay trace activity from a single computer.</span></span> <span data-ttu-id="57d67-106">Para cargas de trabalho grandes, use o Distributed Replay Utility para reproduzir dados de rastreamento de vários computadores.</span><span class="sxs-lookup"><span data-stu-id="57d67-106">For large workloads, use the Distributed Replay Utility to replay trace data from multiple computers.</span></span>  
  
 <span data-ttu-id="57d67-107">Esta seção descreve como usar os recursos de reprodução do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57d67-107">This section describes how to use the replay features of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="57d67-108">Para obter mais informações sobre o Distributed Replay Utility, consulte [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="57d67-108">For more information about the Distributed Replay Utility, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="57d67-109">apresenta um mecanismo de repetição multi-threaded que consegue simular as conexões de usuário e a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57d67-109">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="57d67-110">A repetição é útil para solucionar problemas de aplicativos ou processos.</span><span class="sxs-lookup"><span data-stu-id="57d67-110">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="57d67-111">Tendo identificado o problema e implementado correções, execute o rastreamento que encontrou o problema potencial contra o aplicativo ou processo corrigido.</span><span class="sxs-lookup"><span data-stu-id="57d67-111">When you have identified the problem and implemented corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="57d67-112">Em seguida, repita o rastreamento original e compare os resultados.</span><span class="sxs-lookup"><span data-stu-id="57d67-112">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="57d67-113">A repetição de rastreamentos é compatível com a depuração por meio das opções **Alternar Ponto de Interrupção** e **Executar até o Cursor** do menu [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Reproduzir** menu.</span><span class="sxs-lookup"><span data-stu-id="57d67-113">Trace replay supports debugging by using the **Toggle Breakpoint** and the **Run to Cursor** options on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Replay** menu.</span></span> <span data-ttu-id="57d67-114">Essas opções melhoram, em especial, a análise de scripts longos, pois elas podem dividir a repetição do rastreamento em segmentos curtos que podem ser analisados incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="57d67-114">These options especially improve the analysis of long scripts because they can break the replay of the trace into short segments so they can be analyzed incrementally.</span></span>  
  
 <span data-ttu-id="57d67-115">Para obter informações sobre as permissões necessárias para reproduzir rastreamentos, consulte [Permissões necessárias para executar o SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="57d67-115">For information about the permissions required to replay traces, see [Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57d67-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="57d67-116">In This Section</span></span>  
  
|<span data-ttu-id="57d67-117">Tópico</span><span class="sxs-lookup"><span data-stu-id="57d67-117">Topic</span></span>|<span data-ttu-id="57d67-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="57d67-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="57d67-119">Requisitos para reprodução</span><span class="sxs-lookup"><span data-stu-id="57d67-119">Replay Requirements</span></span>](replay-requirements.md)|<span data-ttu-id="57d67-120">Descreve os eventos que devem ser incluídos na definição de um rastreamento para que ele possa ser reproduzido com o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57d67-120">Describes the events that must be included in a trace definition so that it can be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="57d67-121">Opções de repetição &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="57d67-121">Replay Options &#40;SQL Server Profiler&#41;</span></span>](replay-options-sql-server-profiler.md)|<span data-ttu-id="57d67-122">Descreve as opções que podem ser definidas na caixa de diálogo **Configuração de Reprodução** do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57d67-122">Describes the options you can set in the **Replay Configuration** dialog box of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>|  
|[<span data-ttu-id="57d67-123">Considerações para reproduzir rastreamentos &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="57d67-123">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)|<span data-ttu-id="57d67-124">Descreve os eventos de rastreamento que não podem ser reproduzidos com o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] e os efeitos da reprodução de rastreamentos no desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="57d67-124">Describes trace events that can not be replayed with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and the effects on server performance of replaying traces.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57d67-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="57d67-125">See Also</span></span>  
 [<span data-ttu-id="57d67-126">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="57d67-126">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
