---
title: Reproduzir um arquivo de rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 9e361275-c8fd-4499-8389-242cf8e27415
author: stevestein
ms.author: sstein
ms.openlocfilehash: d3a9f007b9b6d2b46be43abdb10db286a75c33fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683835"
---
# <a name="replay-a-trace-file-sql-server-profiler"></a><span data-ttu-id="d0088-102">Repetir um arquivo de rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="d0088-102">Replay a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="d0088-103">Repetição é a capacidade de abrir um rastreamento salvo e repeti-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="d0088-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="d0088-104">apresenta um mecanismo de repetição multi-threaded que consegue simular as conexões de usuário e a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0088-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="d0088-105">A repetição é útil para solucionar problemas de aplicativos ou processos.</span><span class="sxs-lookup"><span data-stu-id="d0088-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="d0088-106">Ao identificar o problema e implementar correções, execute o rastreamento que encontrou o problema potencial no aplicativo ou processo corrigido.</span><span class="sxs-lookup"><span data-stu-id="d0088-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="d0088-107">Em seguida, repita o rastreamento original e compare os resultados.</span><span class="sxs-lookup"><span data-stu-id="d0088-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="d0088-108">Além de quaisquer outras classes de evento que desejar monitorar, devem ser capturadas classes de evento específicas para habilitar a repetição.</span><span class="sxs-lookup"><span data-stu-id="d0088-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="d0088-109">Esses eventos serão capturados por padrão se você usar o modelo de rastreamento **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="d0088-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="d0088-110">Para obter mais informações, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0088-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-file"></a><span data-ttu-id="d0088-111">Para repetir um arquivo de rastreamento</span><span class="sxs-lookup"><span data-stu-id="d0088-111">To replay a trace file</span></span>  
  
1.  <span data-ttu-id="d0088-112">No menu **Arquivo** , aponte para **Abrir**e clique em **Arquivo de Rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="d0088-112">On the **File** menu, point to **Open**, and then click **Trace File**.</span></span> <span data-ttu-id="d0088-113">Selecione um arquivo de rastreamento que contenha as classes de evento necessárias para a repetição.</span><span class="sxs-lookup"><span data-stu-id="d0088-113">Select a trace file that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="d0088-114">No menu **Repetir** , clique em **Iniciar**e conecte à instância de servidor em que deseja repetir o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="d0088-114">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="d0088-115">Na caixa de diálogo **Configuração de Reprodução** , na guia **Opções de Reprodução Básicas** , especifique o **Servidor de reprodução**.</span><span class="sxs-lookup"><span data-stu-id="d0088-115">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify the **Replay server**.</span></span> <span data-ttu-id="d0088-116">Clique em **Alterar** para alterar o servidor exibido na caixa **Servidor de reprodução** .</span><span class="sxs-lookup"><span data-stu-id="d0088-116">Click **Change** to change the server displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="d0088-117">Opcionalmente, selecione um dos seguintes destinos nos quais salvar a repetição:</span><span class="sxs-lookup"><span data-stu-id="d0088-117">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="d0088-118">**Salvar em arquivo**, que especifica um arquivo no qual a reprodução será salva.</span><span class="sxs-lookup"><span data-stu-id="d0088-118">**Save to file**, which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="d0088-119">**Salvar em tabela**, que especifica uma tabela de banco de dados na qual salvar a repetição.</span><span class="sxs-lookup"><span data-stu-id="d0088-119">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="d0088-120">Escolha **Reproduzir eventos na oudem em que fouam rastreados**ou **Reproduzir eventos usando vários threads**.</span><span class="sxs-lookup"><span data-stu-id="d0088-120">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="d0088-121">A tabela a seguir explica a diferença entre essas configurações.</span><span class="sxs-lookup"><span data-stu-id="d0088-121">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="d0088-122">Opção</span><span class="sxs-lookup"><span data-stu-id="d0088-122">Option</span></span>|<span data-ttu-id="d0088-123">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d0088-123">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="d0088-124">**Repetir eventos na ordem em que foram rastreados**</span><span class="sxs-lookup"><span data-stu-id="d0088-124">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="d0088-125">Repete os eventos na ordem em que foram registrados.</span><span class="sxs-lookup"><span data-stu-id="d0088-125">Replays events in the order they were recorded.</span></span> <span data-ttu-id="d0088-126">Essa opção habilita a depuração.</span><span class="sxs-lookup"><span data-stu-id="d0088-126">This option enables debugging.</span></span>|  
    |<span data-ttu-id="d0088-127">**Reproduzir eventos usando vários threads**</span><span class="sxs-lookup"><span data-stu-id="d0088-127">**Replay events using multiple threads**</span></span>|<span data-ttu-id="d0088-128">Essa opção usa vários threads para repetir cada evento, não importando a sequência.</span><span class="sxs-lookup"><span data-stu-id="d0088-128">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="d0088-129">Essa opção otimiza o desempenho.</span><span class="sxs-lookup"><span data-stu-id="d0088-129">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="d0088-130">Selecione **Exibir resultados da repetição** para visualizar a repetição enquanto ela ocorre.</span><span class="sxs-lookup"><span data-stu-id="d0088-130">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="d0088-131">Como alternativa, clique na guia **Opções de Reprodução Avançadas**para configurar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d0088-131">Optionally click the **Advanced Replay Options**tab to configure the following options:</span></span>  
  
    -   <span data-ttu-id="d0088-132">Para reproduzir todas as SPIDs (IDs de processo do servidor), selecione **Reproduzir SPIDs do sistema**.</span><span class="sxs-lookup"><span data-stu-id="d0088-132">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="d0088-133">Para limitar a repetição aos processos pertencentes a um SPID específico, selecione **Repetir somente um SPID**.</span><span class="sxs-lookup"><span data-stu-id="d0088-133">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="d0088-134">Na caixa **SPID a serem reproduzidas** , digite a SPID.</span><span class="sxs-lookup"><span data-stu-id="d0088-134">In the **SPID to replay** box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="d0088-135">Para reproduzir eventos ocorridos durante um intervalo de tempo específico, selecione **Limitar reprodução por data e hora**.</span><span class="sxs-lookup"><span data-stu-id="d0088-135">To replay events that occurred during a specific time period, select **Limit the replay by date and time**.</span></span> <span data-ttu-id="d0088-136">Selecione uma data e hora para **Hora de início**e **Hora de término**para especificar o intervalo de tempo a incluir na reprodução.</span><span class="sxs-lookup"><span data-stu-id="d0088-136">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="d0088-137">Para controlar o modo como o SQL Server gerencia os processos durante a reprodução, configure as **Opções do Health Monitor**.</span><span class="sxs-lookup"><span data-stu-id="d0088-137">To control how SQL Server manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0088-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0088-138">See Also</span></span>  
 <span data-ttu-id="d0088-139">[Permissões necessárias para executar o SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d0088-139">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="d0088-140">[Repetir rastreamentos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="d0088-140">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="d0088-141">[Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="d0088-141">[Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="d0088-142">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="d0088-142">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
