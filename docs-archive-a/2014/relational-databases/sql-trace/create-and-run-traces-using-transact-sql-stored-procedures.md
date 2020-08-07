---
title: Criar e executar rastreamentos usando procedimentos armazenados de Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 80347417-338d-4bea-8885-91fae5181cfe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2905ce2822598502ef6337d1a083fb6fde001c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575054"
---
# <a name="create-and-run-traces-using-transact-sql-stored-procedures"></a><span data-ttu-id="1033f-102">Criar e executar rastreamentos usando procedimentos armazenados de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1033f-102">Create and Run Traces Using Transact-SQL Stored Procedures</span></span>
  <span data-ttu-id="1033f-103">O processo de rastrear com o Rastreamento do SQL varia segundo se está criando e executando o rastreamento através do Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou de procedimentos armazenados de sistema.</span><span class="sxs-lookup"><span data-stu-id="1033f-103">The process of tracing with SQL Trace varies depending on whether you create and run your trace by using Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or by using system stored procedures.</span></span>  
  
 <span data-ttu-id="1033f-104">Como alternativa ao [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], você pode usar procedimentos armazenados de sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] para criar e executar rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="1033f-104">As an alternative to [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create and run traces.</span></span> <span data-ttu-id="1033f-105">O processo de rastrear usando procedimentos armazenados de sistema é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1033f-105">The process of tracing by using system stored procedures is as follows:</span></span>  
  
1.  <span data-ttu-id="1033f-106">Crie um rastreamento usando **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="1033f-106">Create a trace by using **sp_trace_create**.</span></span>  
  
2.  <span data-ttu-id="1033f-107">Adicione eventos com **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="1033f-107">Add events with **sp_trace_setevent**.</span></span>  
  
3.  <span data-ttu-id="1033f-108">(Opcional) Defina um filtro, com **sp_trace_setfilter**.</span><span class="sxs-lookup"><span data-stu-id="1033f-108">(Optional) Set a filter with **sp_trace_setfilter**.</span></span>  
  
4.  <span data-ttu-id="1033f-109">Inicie o rastreamento com **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="1033f-109">Start the trace with **sp_trace_setstatus**.</span></span>  
  
5.  <span data-ttu-id="1033f-110">Pare o rastreamento com **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="1033f-110">Stop the trace with **sp_trace_setstatus**.</span></span>  
  
6.  <span data-ttu-id="1033f-111">Feche o rastreamento com **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="1033f-111">Close the trace with **sp_trace_setstatus**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1033f-112">Usar procedimentos armazenados do sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] cria um rastreamento no servidor, o que garante que nenhum evento se perca enquanto houver espaço no disco e não ocorrerem erros.</span><span class="sxs-lookup"><span data-stu-id="1033f-112">Using [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures creates a server-side trace, which guarantees that no events will be lost as long as there is space on the disk and no write errors occur.</span></span> <span data-ttu-id="1033f-113">Se o disco ficar cheio ou falhar, a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] continuará em execução, mas o rastreamento será interrompido.</span><span class="sxs-lookup"><span data-stu-id="1033f-113">If the disk becomes full or the disk fails, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance continues to run, but tracing stops.</span></span> <span data-ttu-id="1033f-114">Se **c2 audit mode** estiver definido e houver uma falha de gravação, o rastreamento será interrompido e a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será encerrada.</span><span class="sxs-lookup"><span data-stu-id="1033f-114">If the **c2 audit mode** is set, and there is a write failure, tracing stops and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span> <span data-ttu-id="1033f-115">Para obter mais informações sobre a configuração **c2 audit mode** , veja [Opção c2 audit mode de configuração de servidor](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="1033f-115">For more information about the **c2 audit mode** setting, see [c2 audit mode Server Configuration Option](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1033f-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1033f-116">In This Section</span></span>  
  
|<span data-ttu-id="1033f-117">Tópico</span><span class="sxs-lookup"><span data-stu-id="1033f-117">Topic</span></span>|<span data-ttu-id="1033f-118">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1033f-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1033f-119">Otimizar o rastreamento do SQL</span><span class="sxs-lookup"><span data-stu-id="1033f-119">Optimize SQL Trace</span></span>](sql-trace.md)|<span data-ttu-id="1033f-120">Contém informações sobre maneiras de reduzir os efeitos do rastreamento sobre o desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="1033f-120">Contains information about ways you can reduce the effects of tracing on system performance.</span></span>|  
|[<span data-ttu-id="1033f-121">Filtrar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="1033f-121">Filter a Trace</span></span>](filter-a-trace.md)|<span data-ttu-id="1033f-122">Contém informações sobre como usar filtros em rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="1033f-122">Contains information about using filters for tracing.</span></span>|  
|[<span data-ttu-id="1033f-123">Limitar o tamanho de arquivos e tabelas do rastreamento</span><span class="sxs-lookup"><span data-stu-id="1033f-123">Limit Trace File and Table Sizes</span></span>](limit-trace-file-and-table-sizes.md)|<span data-ttu-id="1033f-124">Contém informações sobre como limitar o tamanho dos arquivos e tabelas nos quais são gravados os dados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1033f-124">Contains information about how to limit the size of files and tables where trace data is written.</span></span> <span data-ttu-id="1033f-125">Observe que só o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pode gravar informações de rastreamento em tabelas.</span><span class="sxs-lookup"><span data-stu-id="1033f-125">Note that only [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can write trace information to tables.</span></span>|  
|[<span data-ttu-id="1033f-126">Agendar rastreamentos</span><span class="sxs-lookup"><span data-stu-id="1033f-126">Schedule Traces</span></span>](schedule-traces.md)|<span data-ttu-id="1033f-127">Contém informações sobre como definir a hora de início e a hora de término de um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1033f-127">Contains information about how to set the start time and the end time for tracing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1033f-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1033f-128">See Also</span></span>  
 <span data-ttu-id="1033f-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1033f-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="1033f-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1033f-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="1033f-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1033f-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 [<span data-ttu-id="1033f-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1033f-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
  
