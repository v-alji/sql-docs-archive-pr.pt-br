---
title: Monitoramento de desempenho e atividade de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- activity monitoring [SQL Server]
- traces [SQL Server], how-to topics
- monitoring server performance [SQL Server], activity monitoring
- stored procedures [SQL Server], traces
- performance [SQL Server], servers
- servers [SQL Server], performance
- SQL Server Profiler, how-to topics
- SQL Server Management Studio [SQL Server], monitoring system
- Profiler [SQL Server Profiler], how-to topics
ms.assetid: f9abe48d-d6e9-4c38-a355-fc5eb5a95a25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0fa7902d68c587a7733f07ceb8daccd3a6a98fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583553"
---
# <a name="server-performance-and-activity-monitoring"></a><span data-ttu-id="a3ede-102">Monitoramento de desempenho e atividade de servidor</span><span class="sxs-lookup"><span data-stu-id="a3ede-102">Server Performance and Activity Monitoring</span></span>
  <span data-ttu-id="a3ede-103">A meta do monitoramento de bancos de dados é avaliar o desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="a3ede-103">The goal of monitoring databases is to assess how a server is performing.</span></span> <span data-ttu-id="a3ede-104">Um monitoramento eficaz envolve a criação de instantâneos periódicos do desempenho atual para isolar processos que estão ocasionando problemas, e a coleta contínua de dados para o controle das tendências de desempenho.</span><span class="sxs-lookup"><span data-stu-id="a3ede-104">Effective monitoring involves taking periodic snapshots of current performance to isolate processes that are causing problems, and gathering data continuously over time to track performance trends.</span></span> <span data-ttu-id="a3ede-105">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o sistema operacional [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows fornecem utilitários que permitem exibir a condição atual do banco de dados e acompanhar o desempenho à medida que as condições mudam.</span><span class="sxs-lookup"><span data-stu-id="a3ede-105">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows operating system provide utilities that let you view the current condition of the database and to track performance as conditions change.</span></span>  
  
 <span data-ttu-id="a3ede-106">A seção a seguir contém tópicos que descrevem como usar as ferramentas de monitoramento de desempenho e atividade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows.</span><span class="sxs-lookup"><span data-stu-id="a3ede-106">The following section contains topics that describe how to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows performance and activity monitoring tools.</span></span> <span data-ttu-id="a3ede-107">Ela contém os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a3ede-107">It contains the following topics:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3ede-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a3ede-108">In This Section</span></span>  
 <span data-ttu-id="a3ede-109">**Para executar tarefas de monitoramento com ferramentas do Windows**</span><span class="sxs-lookup"><span data-stu-id="a3ede-109">**To perform monitoring tasks with Windows tools**</span></span>  
  
-   [<span data-ttu-id="a3ede-110">Iniciar o Monitor do Sistema &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-110">Start System Monitor &#40;Windows&#41;</span></span>](start-system-monitor-windows.md)  
  
-   [<span data-ttu-id="a3ede-111">Exibir o log de aplicativos do Windows &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-111">View the Windows Application Log &#40;Windows&#41;</span></span>](view-the-windows-application-log-windows-10.md)  
  
 <span data-ttu-id="a3ede-112">**Para criar alertas de banco de dados do SQL Server com ferramentas do Windows**</span><span class="sxs-lookup"><span data-stu-id="a3ede-112">**To create SQL Server database alerts with Windows tools**</span></span>  
  
-   [<span data-ttu-id="a3ede-113">Configurar um alerta de banco de dados do SQL Server &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-113">Set Up a SQL Server Database Alert &#40;Windows&#41;</span></span>](set-up-a-sql-server-database-alert-windows.md)  
  
 <span data-ttu-id="a3ede-114">**Para realizar tarefas de monitoramento com o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a3ede-114">**To perform monitoring tasks with SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="a3ede-115">Exibir o log de erros do SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-115">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="a3ede-116">Abrir o Monitor de Atividade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-116">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)  
  
 <span data-ttu-id="a3ede-117">**Para realizar tarefas de monitoramento com o Rastreamento do SQL, usando procedimentos armazenados Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="a3ede-117">**To perform monitoring tasks with SQL Trace by using Transact-SQL stored procedures**</span></span>  
  
-   [<span data-ttu-id="a3ede-118">Criar um rastreamento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-118">Create a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
-   [<span data-ttu-id="a3ede-119">Definir um filtro de rastreamento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-119">Set a Trace Filter &#40;Transact-SQL&#41;</span></span>](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md)  
  
-   [<span data-ttu-id="a3ede-120">Modificar um rastreamento existente &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-120">Modify an Existing Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/modify-an-existing-trace-transact-sql.md)  
  
-   [<span data-ttu-id="a3ede-121">Exibir um rastreamento salvo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-121">View a Saved Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-a-saved-trace-transact-sql.md)  
  
-   [<span data-ttu-id="a3ede-122">Exibir informações de filtro &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-122">View Filter Information &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-filter-information-transact-sql.md)  
  
-   [<span data-ttu-id="a3ede-123">Excluir um rastreamento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-123">Delete a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/delete-a-trace-transact-sql.md)  
  
 <span data-ttu-id="a3ede-124">**Para criar e modificar rastreamentos usando o SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="a3ede-124">**To create and modify traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="a3ede-125">Criar um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-125">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-126">Definir opções de rastreamento globais &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-126">Set Global Trace Options &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-127">Especificar eventos e colunas de dados para um arquivo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-127">Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-128">Criar um script Transact-SQL para executar um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-128">Create a Transact-SQL Script for Running a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-transact-sql-script-for-running-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-129">Salvar resultados de rastreamento em um arquivo &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-129">Save Trace Results to a File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-130">Definir um tamanho máximo para um arquivo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-130">Set a Maximum File Size for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-file-size-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-131">Salvar resultados de rastreamento em uma tabela &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-131">Save Trace Results to a Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-132">Definir um tamanho máximo para uma tabela de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-132">Set a Maximum Table Size for a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-table-size-for-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-133">Filtrar eventos em um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-133">Filter Events in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-134">Exibir informações de filtro &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-134">View Filter Information &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-135">Modificar um filtro &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-135">Modify a Filter &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-136">Filtrar eventos com base na hora de início do evento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-136">Filter Events Based on the Event Start Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-start-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-137">Filtrar eventos com base na hora de término do evento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-137">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-138">Filtrar SPIDs &#40;IDs de processo de servidor&#41; em um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-138">Filter Server Process IDs &#40;SPIDs&#41; in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-server-process-ids-spids-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-139">Organizar colunas exibidas em um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-139">Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="a3ede-140">**Para iniciar, pausar e parar rastreamentos usando o SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="a3ede-140">**To start, pause, and stop traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="a3ede-141">Iniciar um rastreamento automaticamente após a conexão com um servidor &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-141">Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-142">Pausar um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-142">Pause a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/pause-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-143">Interromper um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-143">Stop a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/stop-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-144">Executar um rastreamento que foi pausado ou interrompido &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-144">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
 <span data-ttu-id="a3ede-145">**Para abrir rastreamentos e configurar a forma como serão exibidos usando o SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="a3ede-145">**To open traces and configure how traces are displayed by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="a3ede-146">Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-146">Open a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-147">Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-147">Open a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-148">Limpar uma janela de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-148">Clear a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/clear-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-149">Fechar uma janela de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-149">Close a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/close-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-150">Definir padrões de definição de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-150">Set Trace Definition Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-definition-defaults-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-151">Definir padrões de exibição de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-151">Set Trace Display Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="a3ede-152">**Para repetir rastreamentos usando o SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="a3ede-152">**To replay traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="a3ede-153">Reproduzir um arquivo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-153">Replay a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-154">Reproduzir uma tabela de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-154">Replay a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-155">Reproduzir um único evento de cada vez &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-155">Replay a Single Event at a Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-single-event-at-a-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-156">Reproduzir em um ponto de interrupção &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-156">Replay to a Breakpoint &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-breakpoint-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-157">Reproduzir para um cursor &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-157">Replay to a Cursor &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-cursor-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-158">Reproduzir um script Transact-SQL &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-158">Replay a Transact-SQL Script &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-transact-sql-script-sql-server-profiler.md)  
  
 <span data-ttu-id="a3ede-159">**Para criar, modificar e usar modelos de rastreamento usando o SQL Server Profiler**</span><span class="sxs-lookup"><span data-stu-id="a3ede-159">**To create, modify, and use trace templates by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="a3ede-160">Criar um modelo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-160">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-161">Modificar um modelo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-161">Modify a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-162">Derivar um modelo de um rastreamento em execução &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-162">Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-163">Derivar um modelo de um arquivo ou uma tabela de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-163">Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-164">Exportar um modelo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-164">Export a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/export-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-165">Importar um modelo de rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-165">Import a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/import-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="a3ede-166">**Para usar rastreamentos do SQL Server Profiler para coletar e monitorar o desempenho do servidor**</span><span class="sxs-lookup"><span data-stu-id="a3ede-166">**To use SQL Server Profiler traces to collect and monitor server performance**</span></span>  
  
-   [<span data-ttu-id="a3ede-167">Localizar um valor ou coluna de dados durante um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-167">Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-168">Salvar gráficos de deadlock &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-168">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-169">Salvar eventos Showplan XMLL separadamente &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-169">Save Showplan XML Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-170">Salvar eventos Showplan XML Statistics Profile separadamente &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-170">Save Showplan XML Statistics Profile Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-statistics-profile-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-171">Extrair um script de um rastreamento &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-171">Extract a Script from a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/extract-a-script-from-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="a3ede-172">Correlacionar um rastreamento com dados do log de desempenho do Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ede-172">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
