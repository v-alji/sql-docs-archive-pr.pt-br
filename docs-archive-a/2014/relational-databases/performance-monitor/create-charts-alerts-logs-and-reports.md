---
title: Criar gráficos, alertas, logs e relatórios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], charts and reports
- charts [SQL Server]
- reports [SQL Server]
- reports [SQL Server], creating
- Windows System Monitor [SQL Server], charts and reports
- logs [SQL Server], System Monitor
- System Monitor [SQL Server], logs
- Windows System Monitor [SQL Server], logs
ms.assetid: c9162b37-e5dc-43d1-a3aa-1e9ebc69fecc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a0c95c3f483a8af3e3e68d9c5c7d3caf44350d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684671"
---
# <a name="create-charts-alerts-logs-and-reports"></a><span data-ttu-id="343d3-102">Criar gráficos, alertas, logs e relatórios</span><span class="sxs-lookup"><span data-stu-id="343d3-102">Create Charts, Alerts, Logs, and Reports</span></span>
  <span data-ttu-id="343d3-103">O Monitor do Sistema permite criar gráficos, alertas, logs e relatórios para monitorar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="343d3-103">System Monitor lets you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="charts"></a><span data-ttu-id="343d3-104">Gráficos</span><span class="sxs-lookup"><span data-stu-id="343d3-104">Charts</span></span>  
 <span data-ttu-id="343d3-105">Os gráficos podem monitorar o desempenho atual de objetos e contadores selecionados; por exemplo, o uso da CPU ou E/S em disco.</span><span class="sxs-lookup"><span data-stu-id="343d3-105">Charts can monitor the current performance of selected objects and counters; for example, the CPU usage or disk I/O.</span></span> <span data-ttu-id="343d3-106">É possível adicionar diversas combinações de objetos e contadores a um gráfico do Monitor do Sistema.</span><span class="sxs-lookup"><span data-stu-id="343d3-106">You can add to a chart various combinations of System Monitor objects and counters.</span></span> <span data-ttu-id="343d3-107">Também é possível adicionar objetos e contadores do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows a um gráfico.</span><span class="sxs-lookup"><span data-stu-id="343d3-107">You also can add [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows objects and counters to a chart.</span></span>  
  
 <span data-ttu-id="343d3-108">Cada gráfico representa um subconjunto de informações a monitorar.</span><span class="sxs-lookup"><span data-stu-id="343d3-108">Each chart represents a subset of information you want to monitor.</span></span> <span data-ttu-id="343d3-109">Por exemplo, um gráfico pode rastrear estatísticas de uso de memória e um outro gráfico pode rastrear estatísticas de E/S em disco.</span><span class="sxs-lookup"><span data-stu-id="343d3-109">For example, one chart can track memory usage statistics and a second chart can track disk I/O statistics.</span></span>  
  
 <span data-ttu-id="343d3-110">Usar um gráfico pode ser útil para as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="343d3-110">Using a chart can be useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="343d3-111">Investigar por que um computador ou aplicativo está lento ou ineficiente.</span><span class="sxs-lookup"><span data-stu-id="343d3-111">Investigating why a computer or application is slow or inefficient.</span></span>  
  
-   <span data-ttu-id="343d3-112">Monitorar continuamente os sistemas para localizar problemas de desempenho intermitentes.</span><span class="sxs-lookup"><span data-stu-id="343d3-112">Continually monitoring systems to find intermittent performance problems.</span></span>  
  
-   <span data-ttu-id="343d3-113">Descobrir por que a capacidade precisa ser aumentada.</span><span class="sxs-lookup"><span data-stu-id="343d3-113">Discovering why you need to increase capacity.</span></span>  
  
-   <span data-ttu-id="343d3-114">Exibir uma tendência na forma de um gráfico de linhas.</span><span class="sxs-lookup"><span data-stu-id="343d3-114">Displaying a trend as a line chart.</span></span>  
  
-   <span data-ttu-id="343d3-115">Exibir uma comparação na forma de um gráfico de histograma.</span><span class="sxs-lookup"><span data-stu-id="343d3-115">Displaying a comparison as a histogram chart.</span></span>  
  
 <span data-ttu-id="343d3-116">Gráficos são úteis para o monitoramento de curto prazo em tempo real de um computador local ou remoto (por exemplo, quando se deseja monitorar um evento enquanto ele ocorre).</span><span class="sxs-lookup"><span data-stu-id="343d3-116">Charts are useful for short-term, real-time monitoring of a local or remote computer (for example, when you want to monitor an event as it occurs).</span></span>  
  
## <a name="alerts"></a><span data-ttu-id="343d3-117">Alertas</span><span class="sxs-lookup"><span data-stu-id="343d3-117">Alerts</span></span>  
 <span data-ttu-id="343d3-118">Usando alertas, o Monitor do Sistema rastreia eventos específicos e emite notificações a seu respeito conforme solicitado.</span><span class="sxs-lookup"><span data-stu-id="343d3-118">Using alerts, System Monitor tracks specific events and notifies you of these events as requested.</span></span> <span data-ttu-id="343d3-119">Um log de alertas pode monitorar o desempenho atual de contadores e instâncias de objetos selecionados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="343d3-119">An alert log can monitor the current performance of selected counters and instances for objects in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="343d3-120">Quando um contador excede um determinado valor, o log registra a data e a hora do evento.</span><span class="sxs-lookup"><span data-stu-id="343d3-120">When a counter exceeds a given value, the log records the date and time of the event.</span></span> <span data-ttu-id="343d3-121">Um evento também pode gerar um alerta de rede.</span><span class="sxs-lookup"><span data-stu-id="343d3-121">An event can also generate a network alert.</span></span> <span data-ttu-id="343d3-122">Você pode fazer com que um programa especificado seja executado na primeira vez ou em todas as vezes que o evento ocorrer.</span><span class="sxs-lookup"><span data-stu-id="343d3-122">You can have a specified program run the first time or every time an event occurs.</span></span> <span data-ttu-id="343d3-123">Por exemplo, um alerta pode enviar uma mensagem de rede a todos os administradores do sistema avisando que a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está ficando com pouco espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="343d3-123">For example, an alert can send a network message to all system administrators that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is getting low on disk space.</span></span>  
  
## <a name="logs"></a><span data-ttu-id="343d3-124">Logs</span><span class="sxs-lookup"><span data-stu-id="343d3-124">Logs</span></span>  
 <span data-ttu-id="343d3-125">Os logs permitem registrar informações sobre a atividade atual de objetos e computadores selecionados para visualização e análise posteriores.</span><span class="sxs-lookup"><span data-stu-id="343d3-125">Logs allow you to record information on the current activity of selected objects and computers for later viewing and analysis.</span></span> <span data-ttu-id="343d3-126">É possível coletar dados de vários sistemas em um mesmo arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="343d3-126">You can collect data from multiple systems into a single log file.</span></span> <span data-ttu-id="343d3-127">Por exemplo, é possível criar logs diferentes que coletem informações sobre o desempenho de objetos selecionados em diversos computadores para análise futura.</span><span class="sxs-lookup"><span data-stu-id="343d3-127">For example, you can create different logs to accumulate information about the performance of selected objects on various computers for future analysis.</span></span> <span data-ttu-id="343d3-128">Você pode salvar essas seleções sob um nome de arquivo e reutilizá-las quando quiser criar um outro log de informações similares para comparação.</span><span class="sxs-lookup"><span data-stu-id="343d3-128">You can save these selections under a file name and reuse them when you want to create another log of similar information for comparison.</span></span>  
  
 <span data-ttu-id="343d3-129">Arquivos de log fornecem informações preciosas para a solução de problemas ou planejamento.</span><span class="sxs-lookup"><span data-stu-id="343d3-129">Log files provide a wealth of information for troubleshooting or planning.</span></span> <span data-ttu-id="343d3-130">Enquanto que gráficos, alertas e relatórios sobre a atividade atual propiciam um feedback instantâneo, os arquivos de log permitem rastrear os contadores por um longo intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="343d3-130">Whereas charts, alerts, and reports on current activity provide instant feedback, log files enable you to track counters over a long period of time.</span></span> <span data-ttu-id="343d3-131">Assim, você pode examinar as informações mais minuciosamente e documentar o desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="343d3-131">Thus, you can examine information more thoroughly and document system performance.</span></span>  
  
## <a name="reports"></a><span data-ttu-id="343d3-132">Relatórios</span><span class="sxs-lookup"><span data-stu-id="343d3-132">Reports</span></span>  
 <span data-ttu-id="343d3-133">Os relatórios permitem exibir valores de instâncias e contadores de objetos selecionados que mudam constantemente.</span><span class="sxs-lookup"><span data-stu-id="343d3-133">Reports allow you to display constantly changing counter and instance values for selected objects.</span></span> <span data-ttu-id="343d3-134">Os valores aparecem em colunas para cada instância.</span><span class="sxs-lookup"><span data-stu-id="343d3-134">Values appear in columns for each instance.</span></span> <span data-ttu-id="343d3-135">É possível ajustar os intervalos do relatório, imprimir instantâneos e exportar dados.</span><span class="sxs-lookup"><span data-stu-id="343d3-135">You can adjust report intervals, print snapshots, and export data.</span></span> <span data-ttu-id="343d3-136">Use relatórios quando precisar exibir os números brutos.</span><span class="sxs-lookup"><span data-stu-id="343d3-136">Use reports when you need to display the raw numbers.</span></span>  
  
 <span data-ttu-id="343d3-137">Para obter mais informações sobre como criar gráficos, alertas, logs e relatórios ou sobre objetos e contadores do Windows, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="343d3-137">For more information about creating charts, alerts, logs, and reports, or about Windows objects and counters, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="343d3-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="343d3-138">See Also</span></span>  
 [<span data-ttu-id="343d3-139">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="343d3-139">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
