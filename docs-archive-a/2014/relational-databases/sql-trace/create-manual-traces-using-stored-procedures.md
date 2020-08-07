---
title: Criar rastreamentos manuais usando procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: f6f47fa2-7c17-41d4-9f69-9be144d56832
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e2840dced22ccdba8fe71cc87c05d7fd6fb4be58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575052"
---
# <a name="create-manual-traces-using-stored-procedures"></a><span data-ttu-id="8480e-102">Criar rastreamentos manuais usando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="8480e-102">Create Manual Traces using Stored Procedures</span></span>
  <span data-ttu-id="8480e-103">O Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece procedimentos armazenados do sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] para criar rastreamentos em uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8480e-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create traces on an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="8480e-104">Esses procedimentos armazenados do sistema podem ser usados nos seus próprios aplicativos para criar rastreamentos manualmente em vez de usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8480e-104">These system stored procedures can be used from within your own applications to create traces manually, instead of using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="8480e-105">Isso lhe permite escrever aplicativos personalizados específicos às necessidades de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="8480e-105">This allows you to write custom applications specific to the needs of your enterprise.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8480e-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8480e-106">In This Section</span></span>  
 <span data-ttu-id="8480e-107">A tabela a seguir lista os procedimentos armazenados do sistema para rastreamento de uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8480e-107">The following table lists the system stored procedures for tracing an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
|<span data-ttu-id="8480e-108">Procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="8480e-108">Stored procedure</span></span>|<span data-ttu-id="8480e-109">Tarefa executada</span><span class="sxs-lookup"><span data-stu-id="8480e-109">Task performed</span></span>|  
|----------------------|--------------------|  
|[<span data-ttu-id="8480e-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8480e-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-geteventinfo-transact-sql)|<span data-ttu-id="8480e-111">Retorna informações sobre eventos incluídos em um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8480e-111">Returns information about events included in a trace.</span></span>|  
|[<span data-ttu-id="8480e-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8480e-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql)|<span data-ttu-id="8480e-113">Retorna informações sobre um rastreamento especificado ou todos os rastreamentos existentes.</span><span class="sxs-lookup"><span data-stu-id="8480e-113">Returns information about a specified trace or all existing traces.</span></span>|  
|[<span data-ttu-id="8480e-114">sp_trace_create &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8480e-114">sp_trace_create &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql)|<span data-ttu-id="8480e-115">Cria uma definição de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8480e-115">Creates a trace definition.</span></span> <span data-ttu-id="8480e-116">O rastreamento novo estará em um estado interrompido.</span><span class="sxs-lookup"><span data-stu-id="8480e-116">The new trace will be in a stopped state.</span></span>|  
|[<span data-ttu-id="8480e-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8480e-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)|<span data-ttu-id="8480e-118">Cria um evento definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="8480e-118">Creates a user-defined event.</span></span>|  
|[<span data-ttu-id="8480e-119">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8480e-119">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)|<span data-ttu-id="8480e-120">Adiciona ou remove uma classe de evento ou coluna de dados de um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8480e-120">Adds an event class or data column to a trace, or removes one from it.</span></span>|  
|[<span data-ttu-id="8480e-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8480e-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)|<span data-ttu-id="8480e-122">Inicia, interrompe ou encerra um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8480e-122">Starts, stops, or closes a trace.</span></span>|  
|[<span data-ttu-id="8480e-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8480e-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql)|<span data-ttu-id="8480e-124">Retorna informações sobre filtros aplicados a um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8480e-124">Returns information about filters applied to a trace.</span></span>|  
|[<span data-ttu-id="8480e-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8480e-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)|<span data-ttu-id="8480e-126">Aplica um filtro novo ou modificado a um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8480e-126">Applies a new or modified filter to a trace.</span></span>|  
  
 <span data-ttu-id="8480e-127">**Para definir seu próprio rastreamento usando procedimentos armazenados**</span><span class="sxs-lookup"><span data-stu-id="8480e-127">**To define your own trace using stored procedures**</span></span>  
  
1.  <span data-ttu-id="8480e-128">Especifique os eventos a serem capturados usando **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="8480e-128">Specify the events to capture using **sp_trace_setevent**.</span></span>  
  
2.  <span data-ttu-id="8480e-129">Especifique qualquer filtro de evento.</span><span class="sxs-lookup"><span data-stu-id="8480e-129">Specify any event filters.</span></span> <span data-ttu-id="8480e-130">Para obter mais informações, veja [Definir um filtro de rastreamento #40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="8480e-130">For more information, see [Set a Trace Filter &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span></span>  
  
3.  <span data-ttu-id="8480e-131">Especifique o destino para os dados do evento capturado usando **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="8480e-131">Specify the destination for the captured event data using **sp_trace_create**.</span></span>  
  
 <span data-ttu-id="8480e-132">Para obter um exemplo de como usar procedimentos armazenados de rastreamento, veja [Criar um rastreamento &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8480e-132">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span></span>  
  
 <span data-ttu-id="8480e-133">**Para definir padrões de definição de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8480e-133">**To set trace definition defaults**</span></span>  
  
 [<span data-ttu-id="8480e-134">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8480e-134">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
 <span data-ttu-id="8480e-135">**Para definir padrões de exibição de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8480e-135">**To set trace display defaults**</span></span>  
  
 [<span data-ttu-id="8480e-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8480e-136">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="8480e-137">**Para criar um rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8480e-137">**To create a trace**</span></span>  
  
 [<span data-ttu-id="8480e-138">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8480e-138">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
 [<span data-ttu-id="8480e-139">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8480e-139">Transact-SQL</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
 <span data-ttu-id="8480e-140">**Para adicionar ou remover eventos de um modelo de rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8480e-140">**To add or remove events from a trace template**</span></span>  
  
 [<span data-ttu-id="8480e-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8480e-141">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="8480e-142">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8480e-142">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
