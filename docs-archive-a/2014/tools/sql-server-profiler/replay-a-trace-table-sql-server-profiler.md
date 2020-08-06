---
title: Reproduzir uma tabela de rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 6a0ad817-3d8d-4495-889d-c66a7ef9e8bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: f3c26858fa852686bc3d9ccf4a26d47e04852647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681309"
---
# <a name="replay-a-trace-table-sql-server-profiler"></a><span data-ttu-id="426ff-102">Repetir uma tabela de rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="426ff-102">Replay a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="426ff-103">Repetição é a capacidade de abrir um rastreamento salvo e repeti-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="426ff-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="426ff-104">apresenta um mecanismo de repetição multi-threaded que consegue simular as conexões de usuário e a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="426ff-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="426ff-105">A repetição é útil para solucionar problemas de aplicativos ou processos.</span><span class="sxs-lookup"><span data-stu-id="426ff-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="426ff-106">Ao identificar o problema e implementar correções, execute o rastreamento que encontrou o problema potencial no aplicativo ou processo corrigido.</span><span class="sxs-lookup"><span data-stu-id="426ff-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="426ff-107">Em seguida, repita o rastreamento original e compare os resultados.</span><span class="sxs-lookup"><span data-stu-id="426ff-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="426ff-108">Além de quaisquer outras classes de evento que desejar monitorar, devem ser capturadas classes de evento específicas para habilitar a repetição.</span><span class="sxs-lookup"><span data-stu-id="426ff-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="426ff-109">Esses eventos serão capturados por padrão se você usar o modelo de rastreamento **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="426ff-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="426ff-110">Para obter mais informações, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="426ff-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-table"></a><span data-ttu-id="426ff-111">Para repetir uma tabela de rastreamento</span><span class="sxs-lookup"><span data-stu-id="426ff-111">To replay a trace table</span></span>  
  
1.  <span data-ttu-id="426ff-112">Abra uma tabela de rastreamento que contenha as classes de evento necessárias para a repetição.</span><span class="sxs-lookup"><span data-stu-id="426ff-112">Open a trace table that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="426ff-113">No menu **Repetir** , clique em **Iniciar**e conecte à instância de servidor em que deseja repetir o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="426ff-113">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="426ff-114">Na caixa de diálogo **Configuração de Repetição** , na guia **Opções de Repetição Básicas** , especifique o **Servidor de repetição**.</span><span class="sxs-lookup"><span data-stu-id="426ff-114">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify **Replay server**.</span></span> <span data-ttu-id="426ff-115">Clique em **Alterar** para alterar o servidor exibido na caixa **Servidor de repetição** .</span><span class="sxs-lookup"><span data-stu-id="426ff-115">Click **Change** to change the server that is displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="426ff-116">Opcionalmente, selecione um dos seguintes destinos nos quais salvar a repetição:</span><span class="sxs-lookup"><span data-stu-id="426ff-116">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="426ff-117">**Salvar em arquivo** , que especifica um arquivo no qual salvar a reprodução.</span><span class="sxs-lookup"><span data-stu-id="426ff-117">**Save to file,** which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="426ff-118">**Salvar em tabela**, que especifica uma tabela de banco de dados na qual salvar a repetição.</span><span class="sxs-lookup"><span data-stu-id="426ff-118">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="426ff-119">Escolha **Reproduzir eventos na oudem em que fouam rastreados**ou **Reproduzir eventos usando vários threads**.</span><span class="sxs-lookup"><span data-stu-id="426ff-119">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="426ff-120">A tabela a seguir explica a diferença entre essas configurações.</span><span class="sxs-lookup"><span data-stu-id="426ff-120">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="426ff-121">Opção</span><span class="sxs-lookup"><span data-stu-id="426ff-121">Option</span></span>|<span data-ttu-id="426ff-122">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="426ff-122">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="426ff-123">**Repetir eventos na ordem em que foram rastreados**</span><span class="sxs-lookup"><span data-stu-id="426ff-123">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="426ff-124">Repete os eventos na ordem em que foram registrados.</span><span class="sxs-lookup"><span data-stu-id="426ff-124">Replays events in the order they were recorded.</span></span> <span data-ttu-id="426ff-125">Essa opção habilita a depuração.</span><span class="sxs-lookup"><span data-stu-id="426ff-125">This option enables debugging.</span></span>|  
    |<span data-ttu-id="426ff-126">**Reproduzir eventos usando vários threads**</span><span class="sxs-lookup"><span data-stu-id="426ff-126">**Replay events using multiple threads**</span></span>|<span data-ttu-id="426ff-127">Essa opção usa vários threads para repetir cada evento, não importando a sequência.</span><span class="sxs-lookup"><span data-stu-id="426ff-127">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="426ff-128">Essa opção otimiza o desempenho.</span><span class="sxs-lookup"><span data-stu-id="426ff-128">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="426ff-129">Selecione **Exibir resultados da repetição** para visualizar a repetição enquanto ela ocorre.</span><span class="sxs-lookup"><span data-stu-id="426ff-129">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="426ff-130">Opcionalmente, clique na guia **Opções de Reprodução Avançadas**para especificar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="426ff-130">Optionally, click the **Advanced Replay Options**tab to specify the following options:</span></span>  
  
    -   <span data-ttu-id="426ff-131">Para reproduzir todas as SPIDs (IDs de processo do servidor), selecione **Reproduzir SPIDs do sistema**.</span><span class="sxs-lookup"><span data-stu-id="426ff-131">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="426ff-132">Para limitar a repetição aos processos pertencentes a um SPID específico, selecione **Repetir somente um SPID**.</span><span class="sxs-lookup"><span data-stu-id="426ff-132">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="426ff-133">Na caixa **SPID a serem reproduzidas**, digite a SPID.</span><span class="sxs-lookup"><span data-stu-id="426ff-133">In the **SPID to replay**box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="426ff-134">Para repetir eventos ocorridos durante um intervalo de tempo específico, selecione **Limitar repetição por data e hora**.</span><span class="sxs-lookup"><span data-stu-id="426ff-134">To replay events that occurred during a specific time period, select **Limit replay by date and time**.</span></span> <span data-ttu-id="426ff-135">Selecione uma data e hora para **Hora de início**e **Hora de término**para especificar o intervalo de tempo a incluir na reprodução.</span><span class="sxs-lookup"><span data-stu-id="426ff-135">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="426ff-136">Para controlar como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gerencia os processos durante a repetição, configure as **Opções do Health Monitor**.</span><span class="sxs-lookup"><span data-stu-id="426ff-136">To control how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="426ff-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="426ff-137">See Also</span></span>  
 <span data-ttu-id="426ff-138">[Permissões necessárias para executar o SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="426ff-138">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="426ff-139">[Repetir rastreamentos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="426ff-139">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="426ff-140">[Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="426ff-140">[Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="426ff-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="426ff-141">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
