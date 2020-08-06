---
title: Monitorar o uso de recursos (Monitor do Sistema) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], resource usage
- System Monitor [SQL Server], about Windows System Monitor
- resource usage monitoring [SQL Server]
- System Monitor [SQL Server]
- counters [SQL Server], resource usage subjects
- performance counters [SQL Server], resource usage subjects
- Windows System Monitor [SQL Server], about Windows System Monitor
- monitoring [SQL Server], server resource usage
- monitoring resource usage [SQL Server]
- Windows System Monitor [SQL Server]
- database monitoring [SQL Server], resource usage
- database performance [SQL Server], resource usage
- tuning databases [SQL Server], resource usage
- server performance [SQL Server], resource usage
ms.assetid: f2993a28-0b81-46f2-aec0-6877fe990387
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d691091a41e3161c733902824bf439b6788cc4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582990"
---
# <a name="monitor-resource-usage-system-monitor"></a><span data-ttu-id="4f1f7-102">Monitorar o uso de recursos (Monitor do Sistema)</span><span class="sxs-lookup"><span data-stu-id="4f1f7-102">Monitor Resource Usage (System Monitor)</span></span>
  <span data-ttu-id="4f1f7-103">Se estiver executando o sistema operacional Microsoft Windows Server, use a ferramenta gráfica Monitor do Sistema para avaliar o desempenho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f1f7-103">If you are running Microsoft Windows server operating system, use the System Monitor graphical tool to measure the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4f1f7-104">É possível visualizar objetos, contadores de desempenho e o comportamento de outros objetos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , como processadores, memória, cache, threads e processos.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-104">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects, performance counters, and the behavior of other objects, such as processors, memory, cache, threads, and processes.</span></span> <span data-ttu-id="4f1f7-105">Cada um desses objetos possui um conjunto de contadores associado para medir o uso de dispositivos, o comprimento de filas, demoras e outros indicadores da taxa de transferência e do congestionamento interno.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-105">Each of these objects has an associated set of counters that measure device usage, queue lengths, delays, and other indicators of throughput and internal congestion.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f1f7-106">O Monitor do Sistema substituiu o Monitor de Desempenho a partir do Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-106">System Monitor replaced Performance Monitor after Windows NT 4.0.</span></span>  
  
## <a name="benefits-of-system-monitor"></a><span data-ttu-id="4f1f7-107">Benefícios do Monitor do Sistema</span><span class="sxs-lookup"><span data-stu-id="4f1f7-107">Benefits of System Monitor</span></span>  
 <span data-ttu-id="4f1f7-108">O Monitor do Sistema pode ser útil monitorar o sistema operacional Windows e os contadores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao mesmo tempo para determinar a correlação entre o desempenho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o Windows.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-108">System Monitor can be useful to monitor Windows operating system and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] counters at the same time to determine any correlation between the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows.</span></span> <span data-ttu-id="4f1f7-109">Por exemplo, monitorar os contadores de entrada/saída (E/S) em disco do Windows e os contadores do Gerenciador de Buffer do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao mesmo tempo pode revelar o comportamento do sistema inteiro.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-109">For example, monitoring the Windows disk input/output (I/O) counters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Buffer Manager counters at the same time can reveal the behavior of the entire system.</span></span>  
  
 <span data-ttu-id="4f1f7-110">O Monitor do Sistema permite obter estatísticas sobre a atividade e o desempenho atuais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f1f7-110">System Monitor allows you to obtain statistics on current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity and performance.</span></span> <span data-ttu-id="4f1f7-111">Usando o Monitor do Sistema, você pode:</span><span class="sxs-lookup"><span data-stu-id="4f1f7-111">Using System Monitor, you can:</span></span>  
  
-   <span data-ttu-id="4f1f7-112">Exibir dados simultaneamente de qualquer quantidade de computadores.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-112">View data simultaneously from any number of computers.</span></span>  
  
-   <span data-ttu-id="4f1f7-113">Visualizar e alterar gráficos, de modo a refletir a atividade atual, e exibir valores de contadores que são atualizados a uma frequência definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-113">View and change charts to reflect current activity, and show counter values that are updated at a frequency that the user defines.</span></span>  
  
-   <span data-ttu-id="4f1f7-114">Exportar dados de gráficos, logs, logs de alertas e relatórios para aplicativos de planilha ou de banco de dados, para manipulação adicional e impressão.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-114">Export data from charts, logs, alert logs, and reports to spreadsheet or database applications for further manipulation and printing.</span></span>  
  
-   <span data-ttu-id="4f1f7-115">Adicionar alertas do sistema que listam um evento no log de alertas e que podem notificá-lo, emitindo um alerta de rede.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-115">Add system alerts that list an event in the alert log and can notify you by issuing a network alert.</span></span>  
  
-   <span data-ttu-id="4f1f7-116">Executar um aplicativo predefinido na primeira vez ou toda vez que um valor de contador estiver acima ou abaixo de um valor definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-116">Run a predefined application the first time or every time a counter value goes over or under a user-defined value.</span></span>  
  
-   <span data-ttu-id="4f1f7-117">Criar arquivos de log contendo dados sobre diversos objetos de computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-117">Create log files that contain data about various objects from different computers.</span></span>  
  
-   <span data-ttu-id="4f1f7-118">Adicionar a um arquivo seções selecionadas de outros arquivos de log existentes, para formar um arquivo morto de longo prazo.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-118">Append to one file selected sections from other existing log files to form a long-term archive.</span></span>  
  
-   <span data-ttu-id="4f1f7-119">Exibir relatórios sobre a atividade atual ou criar relatórios a partir de arquivos de log existentes.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-119">View current-activity reports, or create reports from existing log files.</span></span>  
  
-   <span data-ttu-id="4f1f7-120">Salvar gráficos, alertas, logs ou configurações de relatórios individuais ou toda a configuração do workspace, para reutilização.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-120">Save individual chart, alert, log, or report settings, or the entire workspace setup for reuse.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f1f7-121">O Monitor do Sistema substituiu o Monitor de Desempenho a partir do Windows NT 4.0.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-121">System Monitor replaced the Performance Monitor after Windows NT 4.0.</span></span> <span data-ttu-id="4f1f7-122">Você pode usar o Monitor do Sistema ou o Monitor de Desempenho para essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-122">You can use either the System Monitor or Performance Monitor to do these tasks.</span></span>  
  
## <a name="system-monitor-performance"></a><span data-ttu-id="4f1f7-123">Desempenho do Monitor do Sistema</span><span class="sxs-lookup"><span data-stu-id="4f1f7-123">System Monitor Performance</span></span>  
 <span data-ttu-id="4f1f7-124">Ao monitorar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o sistema operacional Microsoft Windows para investigar questões relacionadas ao desempenho, concentre seus esforços iniciais em três áreas principais:</span><span class="sxs-lookup"><span data-stu-id="4f1f7-124">When you monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the Microsoft Windows operating system to investigate performance-related issues, concentrate your initial efforts in three main areas:</span></span>  
  
-   <span data-ttu-id="4f1f7-125">Atividade de disco</span><span class="sxs-lookup"><span data-stu-id="4f1f7-125">Disk activity</span></span>  
  
-   <span data-ttu-id="4f1f7-126">Utilização do processador</span><span class="sxs-lookup"><span data-stu-id="4f1f7-126">Processor utilization</span></span>  
  
-   <span data-ttu-id="4f1f7-127">Uso de memória</span><span class="sxs-lookup"><span data-stu-id="4f1f7-127">Memory usage</span></span>  
  
 <span data-ttu-id="4f1f7-128">Monitorar um computador em que o Monitor do Sistema é executado pode influir ligeiramente em seu desempenho.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-128">Monitoring a computer on which System Monitor is running can affect computer performance slightly.</span></span> <span data-ttu-id="4f1f7-129">Portanto, registre os dados do Monitor do Sistema em outro disco (ou computador), de modo a reduzir o efeito no computador que está sendo monitorado, ou execute o Monitor do Sistema a partir de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-129">Therefore, either log the System Monitor data to another disk (or computer) so that it reduces the effect on the computer being monitored, or run System Monitor from a remote computer.</span></span> <span data-ttu-id="4f1f7-130">Monitore apenas os contadores que lhe interessam.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-130">Monitor only the counters in which you are interested.</span></span> <span data-ttu-id="4f1f7-131">Se você monitorar contadores demais, haverá sobrecarga de uso de recursos no processo de monitoramento, o que afetará o desempenho do computador que está sendo monitorado.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-131">If you monitor too many counters, resource usage overhead is added to the monitoring process and affects the performance of the computer that is being monitored.</span></span>  
  
## <a name="system-monitor-tasks"></a><span data-ttu-id="4f1f7-132">Tarefas do Monitor do Sistema</span><span class="sxs-lookup"><span data-stu-id="4f1f7-132">System Monitor Tasks</span></span>  
  
|<span data-ttu-id="4f1f7-133">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="4f1f7-133">Task Description</span></span>|<span data-ttu-id="4f1f7-134">Tópico</span><span class="sxs-lookup"><span data-stu-id="4f1f7-134">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="4f1f7-135">Descreve quando usar o Monitor do Sistema e discute a sobrecarga de desempenho quando você usa o Monitor do Sistema.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-135">Describes when to use System Monitor and discusses performance overhead when you use System Monitor.</span></span>|[<span data-ttu-id="4f1f7-136">Executar o Monitor do Sistema</span><span class="sxs-lookup"><span data-stu-id="4f1f7-136">Run System Monitor</span></span>](run-system-monitor.md)|  
|<span data-ttu-id="4f1f7-137">Descreve como monitorar contadores de disco para determinar a atividade de disco e a quantidade de E/S gerada pelos componentes do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-137">Describes how to monitor disk counters to determine disk activity and the amount of I/O generated by their SQL Server components.</span></span>|[<span data-ttu-id="4f1f7-138">Monitorar o uso do disco</span><span class="sxs-lookup"><span data-stu-id="4f1f7-138">Monitor Disk Usage</span></span>](monitor-disk-usage.md)|  
|<span data-ttu-id="4f1f7-139">Descreve como monitorar uma instância do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para determinar se as taxas de uso de CPU estão dentro dos intervalos normais.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-139">Describes how to monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to determine whether CPU usage rates are within normal ranges.</span></span>|[<span data-ttu-id="4f1f7-140">Monitorar o uso da CPU</span><span class="sxs-lookup"><span data-stu-id="4f1f7-140">Monitor CPU Usage</span></span>](monitor-cpu-usage.md)|  
|<span data-ttu-id="4f1f7-141">Descreve como monitorar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para confirmar que o uso de memória está dentro de intervalos normais.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-141">Describes how to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to confirm that memory usage is within typical ranges.</span></span>|[<span data-ttu-id="4f1f7-142">Monitorar o uso de memória</span><span class="sxs-lookup"><span data-stu-id="4f1f7-142">Monitor Memory Usage</span></span>](monitor-memory-usage.md)|  
|<span data-ttu-id="4f1f7-143">Descreve como criar um alerta a ser emitido quando um valor limite de um contador do Monitor do Sistema for atingido.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-143">Describes how to create an alert that is raised when a threshold value for a System Monitor counter has been reached.</span></span>|[<span data-ttu-id="4f1f7-144">Criar um alerta de Banco de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f1f7-144">Create a SQL Server Database Alert</span></span>](create-a-sql-server-database-alert.md)|  
|<span data-ttu-id="4f1f7-145">Descreve como criar gráficos, alertas, logs e relatórios para monitorar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f1f7-145">Describes how to you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="4f1f7-146">Criar gráficos, alertas, logs e relatórios</span><span class="sxs-lookup"><span data-stu-id="4f1f7-146">Create Charts, Alerts, Logs, and Reports</span></span>](create-charts-alerts-logs-and-reports.md)|  
|<span data-ttu-id="4f1f7-147">Lista os objetos e contadores que o Monitor do Sistema usa para monitorar a atividade em computadores que executem uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f1f7-147">Lists objects and counters that System Monitor uses to monitor activity in computers running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[<span data-ttu-id="4f1f7-148">Usar objetos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f1f7-148">Use SQL Server Objects</span></span>](use-sql-server-objects.md)|  
|<span data-ttu-id="4f1f7-149">Lista os objetos e contadores que o Monitor do Sistema usa para monitorar a atividade de OLTP na memória.</span><span class="sxs-lookup"><span data-stu-id="4f1f7-149">Lists objects and counters that System Monitor uses to monitor In-Memory OLTP activity.</span></span>|[<span data-ttu-id="4f1f7-150">&#40;de OLTP na memória&#41; contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="4f1f7-150">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)|  
  
  
