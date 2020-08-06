---
title: SQL Server Profiler-configuração de reprodução (opções de reprodução avançadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.advanced.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: b4eb34f7-3af6-4a44-ba7e-2b8430ec3cd7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95070d8defb5b7778859ce470aaa8cfc85955ba6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683651"
---
# <a name="sql-server-profiler---replay-configuration-advanced-replay-options"></a><span data-ttu-id="cc4f7-102">SQL Server Profiler - configuração de repetição (Opções de Repetição Avançadas)</span><span class="sxs-lookup"><span data-stu-id="cc4f7-102">SQL Server Profiler - Replay Configuration (Advanced Replay Options)</span></span>
  <span data-ttu-id="cc4f7-103">Na caixa de diálogo **Configuração de Reprodução** , use a guia **Opções de Reprodução Avançadas** para especificar como reproduzir um arquivo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-103">In the **Replay Configuration** dialog box, use the **Advanced Replay Options** tab to specify how to replay a trace file.</span></span>  
  
 <span data-ttu-id="cc4f7-104">Para exibir essa janela, use o [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] para abrir um arquivo ou tabela de rastreamento que contenha os eventos adequados para repetição.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="cc4f7-105">Para obter mais informações, consulte [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc4f7-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="cc4f7-106">Enquanto o arquivo ou tabela de rastreamento está aberto, no menu **Reprodução** , clique em **Iniciar**, conecte-se à instância do SQL Server em que você deseja reproduzir o rastreamento e clique na guia **Opções de Reprodução Avançadas** .</span><span class="sxs-lookup"><span data-stu-id="cc4f7-106">While the trace file or table is open, on the **Replay** menu, click **Start**, connect to the instance of SQL Server where you want to replay the trace, and then click the **Advanced Replay Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc4f7-107">Opções</span><span class="sxs-lookup"><span data-stu-id="cc4f7-107">Options</span></span>  
 <span data-ttu-id="cc4f7-108">**Repetir SPIDs do sistema**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-108">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="cc4f7-109">Especifica se o [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] repete os identificadores de processos do sistema (SPIDs).</span><span class="sxs-lookup"><span data-stu-id="cc4f7-109">Specifies whether [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] replays system process identifiers (SPIDs).</span></span>  
  
 <span data-ttu-id="cc4f7-110">**Repetir somente um SPID**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-110">**Replay one SPID only**</span></span>  
 <span data-ttu-id="cc4f7-111">Repete apenas a atividade no arquivo de rastreamento de origem que está relacionado ao SPID selecionado.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-111">Replays only the activity in the source trace file that is related to the selected SPID.</span></span>  
  
 <span data-ttu-id="cc4f7-112">**SPID para repetir**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-112">**SPID to replay**</span></span>  
 <span data-ttu-id="cc4f7-113">Especifica o SPID para repetir.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-113">Specify which SPID to replay.</span></span>  
  
 <span data-ttu-id="cc4f7-114">**Limitar repetição por data e hora**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-114">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="cc4f7-115">Verifica para repetir apenas uma parte do arquivo de rastreamento de origem.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-115">Check to replay only a portion of the source trace file.</span></span>  
  
 <span data-ttu-id="cc4f7-116">**Hora de início**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-116">**Start time**</span></span>  
 <span data-ttu-id="cc4f7-117">Data e hora no arquivo de rastreamento de origem em que a repetição deve iniciar.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-117">Date and time in the source trace file where the replay should start.</span></span>  
  
 <span data-ttu-id="cc4f7-118">**Hora de término**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-118">**End time**</span></span>  
 <span data-ttu-id="cc4f7-119">Data e hora no arquivo de rastreamento de origem em que a repetição deve ser interrompida.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-119">Date and time in the source trace file where the replay should stop.</span></span>  
  
 <span data-ttu-id="cc4f7-120">**Intervalo de espera do monitor de integridade (s)**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-120">**Health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="cc4f7-121">Especifica o intervalo de espera de repetição, em segundos.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-121">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="cc4f7-122">O padrão é 3600 segundos (1 hora).</span><span class="sxs-lookup"><span data-stu-id="cc4f7-122">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="cc4f7-123">Essa configuração afeta o tempo durante o qual um processo pode ser executado antes de ser concluído pelo monitor de integridade.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-123">This setting affects the amount of time a process is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="cc4f7-124">**Intervalo de sondagem do monitor de integridade (s)**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-124">**Health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="cc4f7-125">Especifica o intervalo de sondagem do monitor de integridade durante a repetição, em segundos.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-125">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="cc4f7-126">O padrão é 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-126">Default is 60 seconds.</span></span> <span data-ttu-id="cc4f7-127">Este valor permite que o usuário configure com que frequência o monitor de integridade sonda candidatos a conclusão.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-127">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
 <span data-ttu-id="cc4f7-128">**Habilitar monitor de processos bloqueados do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-128">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="cc4f7-129">Habilita um processo que procura processos bloqueados ou em bloqueio.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-129">Enables a process that searches for blocked or blocking processes.</span></span>  
  
 <span data-ttu-id="cc4f7-130">**Intervalo de espera do monitor de processos bloqueados (s)**</span><span class="sxs-lookup"><span data-stu-id="cc4f7-130">**Blocked processes monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="cc4f7-131">Configura a frequência com que o monitor de processos bloqueados procura processos bloqueados ou em bloqueio.</span><span class="sxs-lookup"><span data-stu-id="cc4f7-131">Configures how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc4f7-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc4f7-132">See Also</span></span>  
 <span data-ttu-id="cc4f7-133">[Reproduzir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="cc4f7-133">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="cc4f7-134">[Reproduzir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="cc4f7-134">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="cc4f7-135">Reproduzir rastreamentos</span><span class="sxs-lookup"><span data-stu-id="cc4f7-135">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
