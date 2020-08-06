---
title: Opções de reprodução (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
- health monitor [SQL Server]
- Replay Configuration dialog box
ms.assetid: 58761a25-a84f-4a90-9c61-97700bc5ad9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 695a1431145813f0a7829626a380e510d0e602e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683834"
---
# <a name="replay-options-sql-server-profiler"></a><span data-ttu-id="a8daa-102">Opções de repetição (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a8daa-102">Replay Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="a8daa-103">Antes de repetir um rastreamento capturado com [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], especifique as seguintes opções de repetição na caixa de diálogo **Configuração de Repetição** .</span><span class="sxs-lookup"><span data-stu-id="a8daa-103">Before replaying a captured trace with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], specify replay options in the **Replay Configuration** dialog box.</span></span> <span data-ttu-id="a8daa-104">Para inicializar essa caixa de diálogo, abra o arquivo ou tabela de rastreamento a repetir no [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]e, no menu **Repetir** , clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="a8daa-104">To launch this dialog box, open the replay trace file or table in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and on the **Replay** menu, click **Start**.</span></span> <span data-ttu-id="a8daa-105">Para obter informações sobre quais permissões são necessárias para reproduzir um rastreamento, veja [Permissões necessárias para executar o SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="a8daa-105">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="a8daa-106">Este tópico descreve as opções especificadas com a caixa de diálogo **Configuração de Repetição** .</span><span class="sxs-lookup"><span data-stu-id="a8daa-106">This topic describes the options specified with the **Replay Configuration** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8daa-107">É recomendável usar o Distributed Replay Utility para reproduzir um aplicativo OLTP intensivo (com muitas conexões simultâneas ativas ou alta taxa de transferência).</span><span class="sxs-lookup"><span data-stu-id="a8daa-107">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="a8daa-108">O Distributed Replay Utility pode reproduzir dados de rastreamento de vários computadores, com uma simulação melhor de uma carga de trabalho de missão crítica.</span><span class="sxs-lookup"><span data-stu-id="a8daa-108">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="a8daa-109">Para obter mais informações, consulte [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="a8daa-109">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="basic-replay-options"></a><span data-ttu-id="a8daa-110">Opções de repetição básicas</span><span class="sxs-lookup"><span data-stu-id="a8daa-110">Basic Replay Options</span></span>  
 <span data-ttu-id="a8daa-111">**Servidor de repetição**</span><span class="sxs-lookup"><span data-stu-id="a8daa-111">**Replay server**</span></span>  
 <span data-ttu-id="a8daa-112">O servidor é o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em relação ao qual se deseja repetir o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a8daa-112">The server is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] against which you want to replay the trace.</span></span> <span data-ttu-id="a8daa-113">O servidor deve cumprir os requisitos de repetição descritos em [Replay Requirements](replay-requirements.md)".</span><span class="sxs-lookup"><span data-stu-id="a8daa-113">The server must adhere to the replay requirements described in [Replay Requirements](replay-requirements.md)."</span></span>  
  
 <span data-ttu-id="a8daa-114">**Salvar no arquivo**</span><span class="sxs-lookup"><span data-stu-id="a8daa-114">**Save to file**</span></span>  
 <span data-ttu-id="a8daa-115">O arquivo de saída em que é gravado o resultado da repetição do rastreamento para posterior análise.</span><span class="sxs-lookup"><span data-stu-id="a8daa-115">The output file where the result of replaying the trace is written for later viewing.</span></span> <span data-ttu-id="a8daa-116">Por padrão, o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] exibe os resultados da repetição do rastreamento apenas na tela.</span><span class="sxs-lookup"><span data-stu-id="a8daa-116">By default, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] displays only the results of replaying the trace on the screen.</span></span>  
  
 <span data-ttu-id="a8daa-117">**Salvar na tabela**</span><span class="sxs-lookup"><span data-stu-id="a8daa-117">**Save to table**</span></span>  
 <span data-ttu-id="a8daa-118">O tabela de banco de dados em que é gravado o resultado da repetição do rastreamento para posterior análise.</span><span class="sxs-lookup"><span data-stu-id="a8daa-118">The database table where the result of replaying the trace is written for later viewing.</span></span>  
  
 <span data-ttu-id="a8daa-119">**Número de threads de repetição**</span><span class="sxs-lookup"><span data-stu-id="a8daa-119">**Number of replay threads**</span></span>  
 <span data-ttu-id="a8daa-120">Especifica o número de threads de repetição a usar simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="a8daa-120">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="a8daa-121">Um número mais alto consome mais recursos durante a repetição, porém ela é mais rápida.</span><span class="sxs-lookup"><span data-stu-id="a8daa-121">A higher number consumes more resources during replay, but replay is faster.</span></span> <span data-ttu-id="a8daa-122">A ordenação de eventos não é completamente mantida quando são usados vários threads.</span><span class="sxs-lookup"><span data-stu-id="a8daa-122">Event ordering is not fully maintained when multiple threads are used.</span></span>  
  
 <span data-ttu-id="a8daa-123">**Repetir eventos na ordem em que foram rastreados**</span><span class="sxs-lookup"><span data-stu-id="a8daa-123">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="a8daa-124">Permite-lhe usar métodos de depuração, como cada etapa de cada rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a8daa-124">Allows you to use debugging methods such as stepping through each trace.</span></span> <span data-ttu-id="a8daa-125">Se esta opção não estiver selecionada, a repetição não garantirá que os eventos sejam repetidos em uma ordem consistente com a que foram capturados originalmente.</span><span class="sxs-lookup"><span data-stu-id="a8daa-125">If this option is not selected, replay does not guarantee that events are replayed in an order that is consistent with the order in which events were originally captured.</span></span>  
  
 <span data-ttu-id="a8daa-126">**Reproduzir eventos usando vários threads**</span><span class="sxs-lookup"><span data-stu-id="a8daa-126">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="a8daa-127">Otimiza o desempenho e desabilita a depuração.</span><span class="sxs-lookup"><span data-stu-id="a8daa-127">Optimizes performance and disables debugging.</span></span> <span data-ttu-id="a8daa-128">Os eventos são repetidos na ordem em que foram registrados para uma ID de processo do servidor (SPID) específica, mas não se garante a ordem dos SPIDs.</span><span class="sxs-lookup"><span data-stu-id="a8daa-128">Events are replayed in the order they were recorded for a particular server process ID (SPID), but ordering of SPIDs is not guaranteed.</span></span>  
  
 <span data-ttu-id="a8daa-129">**Exibir resultados da repetição**</span><span class="sxs-lookup"><span data-stu-id="a8daa-129">**Display replay results**</span></span>  
 <span data-ttu-id="a8daa-130">Exibe os resultados da repetição.</span><span class="sxs-lookup"><span data-stu-id="a8daa-130">Display the results of the replay.</span></span> <span data-ttu-id="a8daa-131">Essa é a opção padrão.</span><span class="sxs-lookup"><span data-stu-id="a8daa-131">This is the default option.</span></span> <span data-ttu-id="a8daa-132">Se o rastreamento que está sendo repetido for muito grande, pode ser conveniente desabilitar essa opção para economizar espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="a8daa-132">If the trace you are replaying is very large, you may want to disable this to save disk space.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8daa-133">Para um melhor desempenho da repetição, recomendamos selecionar eventos a repetir usando vários threads e não selecionar a exibição dos resultados da repetição.</span><span class="sxs-lookup"><span data-stu-id="a8daa-133">For best replay performance, we recommend that you select to replay events using multiple threads, and do not select to display the replay results.</span></span>  
  
## <a name="advanced-replay-options"></a><span data-ttu-id="a8daa-134">Opções de repetição avançadas</span><span class="sxs-lookup"><span data-stu-id="a8daa-134">Advanced Replay Options</span></span>  
 <span data-ttu-id="a8daa-135">**Repetir SPIDs do sistema**</span><span class="sxs-lookup"><span data-stu-id="a8daa-135">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="a8daa-136">Repetir todos os SPIDs.</span><span class="sxs-lookup"><span data-stu-id="a8daa-136">Replay all SPIDs.</span></span> <span data-ttu-id="a8daa-137">Essa é a opção padrão.</span><span class="sxs-lookup"><span data-stu-id="a8daa-137">This is the default option.</span></span>  
  
 <span data-ttu-id="a8daa-138">**Repetir somente um SPID**</span><span class="sxs-lookup"><span data-stu-id="a8daa-138">**Replay one SPID only**</span></span>  
 <span data-ttu-id="a8daa-139">Repetir o número de SPID selecionado na lista.</span><span class="sxs-lookup"><span data-stu-id="a8daa-139">Replays the SPID number you choose from the list.</span></span>  
  
 <span data-ttu-id="a8daa-140">**Limitar repetição por data e hora**</span><span class="sxs-lookup"><span data-stu-id="a8daa-140">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="a8daa-141">Repete o rastreamento para a **Hora de início** e **Hora de término**especificadas.</span><span class="sxs-lookup"><span data-stu-id="a8daa-141">Replays the trace for the specified **Start time** and **End time**.</span></span>  
  
 <span data-ttu-id="a8daa-142">**Intervalo de espera do Health Monitor**</span><span class="sxs-lookup"><span data-stu-id="a8daa-142">**Health monitor wait interval**</span></span>  
 <span data-ttu-id="a8daa-143">Define o tempo de execução permitido a um processo até que o Health Monitor o encerre.</span><span class="sxs-lookup"><span data-stu-id="a8daa-143">Sets the amount of time a process is allowed to run before the health monitor terminates it.</span></span>  
  
 <span data-ttu-id="a8daa-144">**Intervalo de sondagem do Health Monitor**</span><span class="sxs-lookup"><span data-stu-id="a8daa-144">**Health monitor poll interval**</span></span>  
 <span data-ttu-id="a8daa-145">Define a frequência com que o Health Monitor sonda candidatos a encerramento.</span><span class="sxs-lookup"><span data-stu-id="a8daa-145">Sets how often the health monitor polls candidates for termination.</span></span>  
  
 <span data-ttu-id="a8daa-146">**Habilitar monitor de processos bloqueados do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a8daa-146">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="a8daa-147">Define a frequência com que o monitor de processos bloqueados procura processos bloqueados ou que estejam causando bloqueios.</span><span class="sxs-lookup"><span data-stu-id="a8daa-147">Sets how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="about-the-health-monitor"></a><span data-ttu-id="a8daa-148">Sobre o Health Monitor</span><span class="sxs-lookup"><span data-stu-id="a8daa-148">About the Health Monitor</span></span>  
 <span data-ttu-id="a8daa-149">O Health Monitor é um thread de aplicativo que monitora os processos simulados envolvidos na repetição de um rastreamento e encerra os processos que se encontram bloqueados na repetição.</span><span class="sxs-lookup"><span data-stu-id="a8daa-149">The health monitor is an application thread that monitors the simulated processes involved in replaying a trace, and ends those processes that are blocked within the replay.</span></span> <span data-ttu-id="a8daa-150">Na guia **Opções de Repetição Avançadas** da caixa de diálogo **Configuração de Repetição** , é possível especificar o tempo, em segundos, que o Health Monitor deve esperar antes de encerrar um processo bloqueado (**Intervalo de espera do Health Monitor**).</span><span class="sxs-lookup"><span data-stu-id="a8daa-150">In the **Advanced Replay Options** tab of the **Replay Configuration** dialog box, you can specify how long the health monitor should wait in seconds before ending a blocked process (**Health monitor wait interval**).</span></span> <span data-ttu-id="a8daa-151">Se você definir esse intervalo como 0, o Health Monitor nunca encerrará os processos que causam bloqueios no rastreamento de repetição.</span><span class="sxs-lookup"><span data-stu-id="a8daa-151">If you set this interval to 0, the health monitor never ends simulated blocking processes in the replaying trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8daa-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8daa-152">See Also</span></span>  
 <span data-ttu-id="a8daa-153">[Repetir rastreamentos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="a8daa-153">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="a8daa-154">[Requisitos para reprodução](replay-requirements.md) </span><span class="sxs-lookup"><span data-stu-id="a8daa-154">[Replay Requirements](replay-requirements.md) </span></span>  
 [<span data-ttu-id="a8daa-155">Considerações para reproduzir rastreamentos &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a8daa-155">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)  
  
  
