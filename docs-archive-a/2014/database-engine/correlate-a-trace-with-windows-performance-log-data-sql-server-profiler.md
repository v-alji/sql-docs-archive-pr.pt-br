---
title: Correlacionar um rastreamento com os dados de log de desempenho do Windows (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], logs
ms.assetid: e1b3072c-8daf-49a7-9895-c8cccd2adb95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 34575cf4270d817ecfbb5b2d1824831cc99454fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574266"
---
# <a name="correlate-a-trace-with-windows-performance-log-data-sql-server-profiler"></a><span data-ttu-id="bc364-102">Correlacionar um rastreamento com dados do log de desempenho do Windows (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="bc364-102">Correlate a Trace with Windows Performance Log Data (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]<span data-ttu-id="bc364-103">pode correlacionar contadores do monitor do sistema do Microsoft Windows a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] eventos ou.</span><span class="sxs-lookup"><span data-stu-id="bc364-103">can correlate Microsoft Windows System Monitor counters with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] events.</span></span> <span data-ttu-id="bc364-104">O Monitor do Sistema do Windows registra a atividade do sistema em logs de desempenho para os contadores especificados.</span><span class="sxs-lookup"><span data-stu-id="bc364-104">Windows System Monitor logs system activity for specified counters in performance logs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc364-105">Para obter informações sobre como compartilhar logs entre versões diferentes do Windows, consulte o procedimento ao final desse tópico.</span><span class="sxs-lookup"><span data-stu-id="bc364-105">For information about sharing logs among different versions of Windows, see the procedure at the end of this topic.</span></span>  
  
### <a name="to-correlate-a-trace-with-performance-log-data"></a><span data-ttu-id="bc364-106">Para correlacionar um rastreamento com dados do log de desempenho</span><span class="sxs-lookup"><span data-stu-id="bc364-106">To correlate a trace with performance log data</span></span>  
  
1.  <span data-ttu-id="bc364-107">No [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], abra uma tabela ou arquivo de rastreamento salvo.</span><span class="sxs-lookup"><span data-stu-id="bc364-107">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], open a saved trace file or trace table.</span></span> <span data-ttu-id="bc364-108">Não é possível correlacionar um rastreamento em execução que ainda está coletando dados de evento.</span><span class="sxs-lookup"><span data-stu-id="bc364-108">You cannot correlate a running trace that is still collecting event data.</span></span> <span data-ttu-id="bc364-109">Para correlação precisa com os dados do Monitor do Sistema, o rastreamento deve conter as colunas de dados **StartTime** e **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="bc364-109">For accurate correlation with System Monitor data, the trace must contain both **StartTime** and **EndTime** data columns.</span></span>  
  
2.  <span data-ttu-id="bc364-110">No menu  **Arquivo** do [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], clique em **Importar Dados de Desempenho**.</span><span class="sxs-lookup"><span data-stu-id="bc364-110">On the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **File** menu, click **Import Performance Data**.</span></span>  
  
3.  <span data-ttu-id="bc364-111">Na caixa de diálogo **Abrir** , selecione um arquivo que contenha um log de desempenho.</span><span class="sxs-lookup"><span data-stu-id="bc364-111">In the **Open** dialog box, select a file that contains a performance log.</span></span> <span data-ttu-id="bc364-112">Os dados do log de desempenho devem ter sido capturados durante o mesmo período de tempo que os dados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="bc364-112">The performance log data must have been captured during the same time period in which the trace data is captured.</span></span>  
  
4.  <span data-ttu-id="bc364-113">Na caixa de diálogo **Limite de Contadores de Desempenho** , marque as caixas de seleção que correspondem aos objetos e contadores do Monitor do Sistema que você deseja exibir junto com o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="bc364-113">In the **Performance Counters Limit** dialog box, select the check boxes that correspond to the System Monitor objects and counters that you want to display alongside the trace.</span></span> <span data-ttu-id="bc364-114">Clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="bc364-114">Click **OK.**</span></span>  
  
5.  <span data-ttu-id="bc364-115">Na janela de eventos de rastreamento, selecione um evento ou navegue pelas linhas adjacentes usando as teclas de direção.</span><span class="sxs-lookup"><span data-stu-id="bc364-115">Select an event in the trace events window, or navigate through several adjacent rows in the trace events window by using the arrow keys.</span></span> <span data-ttu-id="bc364-116">A barra vertical vermelha na janela **Dados do Monitor do Sistema** indica os dados do log de desempenho correlacionados com o evento de rastreamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="bc364-116">The vertical red bar in the **System Monitor data** window indicates the performance log data that is correlated with the selected trace event.</span></span>  
  
6.  <span data-ttu-id="bc364-117">Clique em um ponto de interesse no gráfico do Monitor do Sistema.</span><span class="sxs-lookup"><span data-stu-id="bc364-117">Click a point of interest in the System Monitor graph.</span></span> <span data-ttu-id="bc364-118">É selecionada a linha de rastreamento correspondente ao horário mais próximo.</span><span class="sxs-lookup"><span data-stu-id="bc364-118">The corresponding trace row that is nearest in time is selected.</span></span> <span data-ttu-id="bc364-119">Para aumentar o zoom sobre um intervalo de tempo, pressione e arraste o ponteiro do mouse no gráfico do Monitor do Sistema.</span><span class="sxs-lookup"><span data-stu-id="bc364-119">To zoom in on a time range, press and drag the mouse pointer in the System Monitor graph.</span></span>  
  
### <a name="to-create-performance-logs-that-can-be-shared-among-different-versions-of-windows"></a><span data-ttu-id="bc364-120">Para criar logs de desempenho que possam ser compartilhados entre versões diferentes do Windows</span><span class="sxs-lookup"><span data-stu-id="bc364-120">To create performance logs that can be shared among different versions of Windows</span></span>  
  
1.  <span data-ttu-id="bc364-121">No Painel de Controle, abra **Ferramentas Administrativas**e clique duas vezes em **Desempenho**.</span><span class="sxs-lookup"><span data-stu-id="bc364-121">In Control Panel, open **Administrative Tools**, and then double click **Performance**.</span></span>  
  
2.  <span data-ttu-id="bc364-122">Na caixa de diálogo **Desempenho** , expanda **Logs e Alertas de Desempenho**, clique com o botão direito do mouse em **Logs do Contador**e clique em **Novas Configurações de Log**.</span><span class="sxs-lookup"><span data-stu-id="bc364-122">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span>  
  
3.  <span data-ttu-id="bc364-123">Digite um nome para o log do contador e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc364-123">Type a name for the counter log, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="bc364-124">Na guia **Geral** , clique em **Adicionar Contadores**.</span><span class="sxs-lookup"><span data-stu-id="bc364-124">On the **General** tab, click **Add Counters**.</span></span>  
  
5.  <span data-ttu-id="bc364-125">Na lista **Objeto de Desempenho** , selecione o objeto de desempenho a monitorar.</span><span class="sxs-lookup"><span data-stu-id="bc364-125">In the **Performance object** list, select a performance object you want to monitor.</span></span> <span data-ttu-id="bc364-126">Os nomes dos objetos de desempenho do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para instâncias padrão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] começam com [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e as instâncias nomeadas começam com MSSQL$*instanceName*.</span><span class="sxs-lookup"><span data-stu-id="bc364-126">The names of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] performance objects for default instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] start with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and named instances start with MSSQL$*instanceName*.</span></span>  
  
6.  <span data-ttu-id="bc364-127">Adicione quantos contadores forem necessários para a sua instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e outros valores importantes, como tempo de processador e tempo de disco.</span><span class="sxs-lookup"><span data-stu-id="bc364-127">Add as many counters as necessary for your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and other important values, such as processor time and disk time.</span></span>  
  
7.  <span data-ttu-id="bc364-128">Quando terminar de adicionar contadores, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="bc364-128">When you have finished adding counters, click **Close**.</span></span>  
  
8.  <span data-ttu-id="bc364-129">Defina valores para o intervalo **Amostrar dados a cada** .</span><span class="sxs-lookup"><span data-stu-id="bc364-129">Set values for the **Sample data every** interval.</span></span> <span data-ttu-id="bc364-130">Comece com um intervalo de amostragem modesto, como 5 minutos e depois ajuste o intervalo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="bc364-130">Start with a modest sampling interval, such as 5 minutes, and then adjust the interval if necessary.</span></span>  
  
9. <span data-ttu-id="bc364-131">Na guia **Arquivos de Log** , escolha **Arquivo de Texto (delimitado por vírgula)** na lista **Tipo de arquivo de log** .</span><span class="sxs-lookup"><span data-stu-id="bc364-131">On the **Log Files** tab, choose **TextFile (Comma delimited)** from the **Log file type** list.</span></span> <span data-ttu-id="bc364-132">Os arquivos de log de texto delimitados por vírgula podem ser compartilhados entre versões diferentes do Windows, bem como ser visualizados mais tarde, em ferramentas de relatório como o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="bc364-132">Comma-delimited text log files can be shared among different versions of Windows and can be viewed later in reporting tools such as Microsoft Excel.</span></span>  
  
10. <span data-ttu-id="bc364-133">Na guia **Agenda** , especifique uma agenda de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="bc364-133">On the **Schedule** tab, specify a monitoring schedule.</span></span>  
  
11. <span data-ttu-id="bc364-134">Clique em **OK** para criar o log de desempenho.</span><span class="sxs-lookup"><span data-stu-id="bc364-134">Click **OK** to create the performance log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc364-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc364-135">See Also</span></span>  
 <span data-ttu-id="bc364-136">[Modelos e permissões do SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="bc364-136">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="bc364-137">Iniciar o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="bc364-137">Start SQL Server Profiler</span></span>](../tools/sql-server-profiler/start-sql-server-profiler.md)  
  
  
