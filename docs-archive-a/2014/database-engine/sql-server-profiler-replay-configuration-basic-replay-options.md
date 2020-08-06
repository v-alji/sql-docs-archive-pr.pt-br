---
title: SQL Server Profiler-configuração de reprodução (opções de reprodução básicas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: 85a1dec6-9bbc-477a-86c5-b463db9ebb31
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cbf433c3108294909d91f7860136c0755b39b46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683649"
---
# <a name="sql-server-profiler---replay-configuration-basic-replay-options"></a><span data-ttu-id="bed65-102">SQL Server Profiler – Configuração de repetição (Opções de repetição básicas)</span><span class="sxs-lookup"><span data-stu-id="bed65-102">SQL Server Profiler - Replay Configuration (Basic Replay Options)</span></span>
  <span data-ttu-id="bed65-103">Na caixa de diálogo **Configuração de Repetição** , use a página **Opções de Repetição Básicas** para especificar como repetir um arquivo ou tabela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="bed65-103">In the **Replay Configuration** dialog box, use the **Basic Replay Options** page to specify how to replay a trace file or table.</span></span>  
  
 <span data-ttu-id="bed65-104">Para exibir essa janela, use o [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] para abrir um arquivo ou tabela de rastreamento que contenha os eventos adequados para repetição.</span><span class="sxs-lookup"><span data-stu-id="bed65-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="bed65-105">Para obter mais informações, consulte [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bed65-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="bed65-106">Enquanto o arquivo ou tabela de rastreamento está aberto, no menu **Repetição** , clique em **Iniciar**e, então, conecte à instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] onde deseja repetir o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="bed65-106">While the trace file or table is open, on the **Replay** menu, click **Start**, and then connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where you want to replay the trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bed65-107">Opções</span><span class="sxs-lookup"><span data-stu-id="bed65-107">Options</span></span>  
 <span data-ttu-id="bed65-108">**Servidor de repetição**</span><span class="sxs-lookup"><span data-stu-id="bed65-108">**Replay server**</span></span>  
 <span data-ttu-id="bed65-109">Exibe a instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para conectar para a repetição.</span><span class="sxs-lookup"><span data-stu-id="bed65-109">Displays the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to for the replay.</span></span>  
  
 <span data-ttu-id="bed65-110">**Alterar...**</span><span class="sxs-lookup"><span data-stu-id="bed65-110">**Change...**</span></span>  
 <span data-ttu-id="bed65-111">Inicia a caixa de diálogo **Conectar ao Servidor** para conectar a outro servidor.</span><span class="sxs-lookup"><span data-stu-id="bed65-111">Launches the **Connect to Server** dialog box to connect to another server.</span></span>  
  
 <span data-ttu-id="bed65-112">**Salvar no arquivo**</span><span class="sxs-lookup"><span data-stu-id="bed65-112">**Save to file**</span></span>  
 <span data-ttu-id="bed65-113">Salva os resultados da repetição para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="bed65-113">Save the replay results to a file.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="bed65-114">exibe o diálogo de arquivo padrão, permitindo que se especifique o local para salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="bed65-114">displays the standard file dialog, where you can specify the location to save the file.</span></span>  
  
 <span data-ttu-id="bed65-115">**Salvar na tabela**</span><span class="sxs-lookup"><span data-stu-id="bed65-115">**Save to table**</span></span>  
 <span data-ttu-id="bed65-116">Salva os resultados da repetição em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="bed65-116">Save the replay results to a table.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="bed65-117">exibe a caixa de diálogo de seleção da tabela, permitindo que se especifique o local para salvar a tabela.</span><span class="sxs-lookup"><span data-stu-id="bed65-117">displays the table selection dialog, where you can specify the location to save the table.</span></span>  
  
 <span data-ttu-id="bed65-118">**Número de threads de repetição**</span><span class="sxs-lookup"><span data-stu-id="bed65-118">**Number of replay threads**</span></span>  
 <span data-ttu-id="bed65-119">Especifica o número de threads de repetição a usar simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="bed65-119">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="bed65-120">Um número maior consome mais recursos durante a repetição, porém esta será mais rápida e simultânea.</span><span class="sxs-lookup"><span data-stu-id="bed65-120">A higher number consumes more resources during replay, but replay is faster and more concurrent.</span></span>  
  
 <span data-ttu-id="bed65-121">**Repetir eventos na ordem em que foram rastreados**</span><span class="sxs-lookup"><span data-stu-id="bed65-121">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="bed65-122">Repete os eventos sequencialmente.</span><span class="sxs-lookup"><span data-stu-id="bed65-122">Replay events sequentially.</span></span> <span data-ttu-id="bed65-123">Use esta opção se você estiver repetindo um rastreamento para depuração.</span><span class="sxs-lookup"><span data-stu-id="bed65-123">Use this option if you are replaying a trace for debugging.</span></span>  
  
 <span data-ttu-id="bed65-124">**Reproduzir eventos usando vários threads**</span><span class="sxs-lookup"><span data-stu-id="bed65-124">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="bed65-125">Repete os eventos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="bed65-125">Replay events concurrently.</span></span> <span data-ttu-id="bed65-126">Essa opção é mais rápida que repetir eventos sequencialmente, mas desabilita a depuração.</span><span class="sxs-lookup"><span data-stu-id="bed65-126">This option is faster than replaying events sequentially, but disables debugging.</span></span> <span data-ttu-id="bed65-127">Os eventos são ordenados dentro de seus identificadores de processo de sistema (SPID).</span><span class="sxs-lookup"><span data-stu-id="bed65-127">The events are ordered within their system process identifiers (SPID).</span></span>  
  
 <span data-ttu-id="bed65-128">**Exibir resultados da repetição**</span><span class="sxs-lookup"><span data-stu-id="bed65-128">**Display replay results**</span></span>  
 <span data-ttu-id="bed65-129">Exibe os resultados da repetição no [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bed65-129">Display replay results in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed65-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bed65-130">See Also</span></span>  
 <span data-ttu-id="bed65-131">[Reproduzir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="bed65-131">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="bed65-132">[Reproduzir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="bed65-132">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="bed65-133">Reproduzir rastreamentos</span><span class="sxs-lookup"><span data-stu-id="bed65-133">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
