---
title: Monitorando o desempenho de procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 55548cb2-77a8-4953-8b5a-f2778a4f13cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d14d27cdc20c0f090c7a030efe05cfce4842f437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685680"
---
# <a name="monitoring-performance-of-natively-compiled-stored-procedures"></a><span data-ttu-id="a417d-102">Monitorando o desempenho de procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="a417d-102">Monitoring Performance of Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="a417d-103">Este tópico discute como você pode monitorar o desempenho de procedimentos armazenados compilados de modo nativo</span><span class="sxs-lookup"><span data-stu-id="a417d-103">This topic discusses how you can monitor the performance of natively compiled stored procedures</span></span>  
  
## <a name="using-extended-events"></a><span data-ttu-id="a417d-104">Usando eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="a417d-104">Using Extended Events</span></span>  
 <span data-ttu-id="a417d-105">Use o evento estendido `sp_statement_completed` para rastrear a execução de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="a417d-105">Use the `sp_statement_completed` extended event to trace execution of a query.</span></span> <span data-ttu-id="a417d-106">Crie uma sessão de evento estendido com esse evento, opcionalmente com um filtro no object_id para um procedimento armazenado específico compilado nativamente. O evento estendido é ativado depois da execução de cada consulta.</span><span class="sxs-lookup"><span data-stu-id="a417d-106">Create an extended event session with this event, optionally with a filter on object_id for a particular natively compiled stored procedure, The extended event is raised after the execution of each query.</span></span> <span data-ttu-id="a417d-107">O tempo de CPU e a duração relatados pelo evento estendido indicam a quantidade de CPU usada pela consulta e o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a417d-107">The CPU time and duration reported by the extended event indicate how much CPU the query used and the execution time.</span></span> <span data-ttu-id="a417d-108">Um procedimento armazenado compilado de modo nativo que usa muito tempo da CPU pode ter problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="a417d-108">A natively compiled stored procedure that uses a lot of CPU time may have performance problems.</span></span>  
  
 <span data-ttu-id="a417d-109">`line_number` junto com `object_id` no evento estendido pode ser usado para investigar a consulta.</span><span class="sxs-lookup"><span data-stu-id="a417d-109">`line_number`, along with the `object_id` in the extended event can be used to investigate the query.</span></span> <span data-ttu-id="a417d-110">A consulta a seguir pode ser usada para recuperar a definição de procedimento.</span><span class="sxs-lookup"><span data-stu-id="a417d-110">The following query can be used to retrieve the procedure definition.</span></span> <span data-ttu-id="a417d-111">O número da linha pode ser usado para identificar a consulta na definição:</span><span class="sxs-lookup"><span data-stu-id="a417d-111">The line number can be used to identify the query within the definition:</span></span>  
  
```sql  
select [definition] from sys.sql_modules where object_id=object_id  
```  
  
 <span data-ttu-id="a417d-112">Para obter mais informações sobre o `sp_statement_completed` evento estendido, consulte [como recuperar a instrução que causou um evento](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span><span class="sxs-lookup"><span data-stu-id="a417d-112">For more information about the `sp_statement_completed` extended event, see [How to retrieve the statement that caused an event](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span></span>  
  
## <a name="using-data-management-views"></a><span data-ttu-id="a417d-113">Usando exibições de gerenciamento de dados</span><span class="sxs-lookup"><span data-stu-id="a417d-113">Using Data Management Views</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a417d-114">oferece suporte à coleta de estatísticas de execução para procedimentos armazenados compilados de modo nativo, nos níveis de procedimento e de consulta.</span><span class="sxs-lookup"><span data-stu-id="a417d-114">supports collecting execution statistics for natively compiled stored procedures, both on the procedure level and the query level.</span></span> <span data-ttu-id="a417d-115">Coletar estatísticas de execução não está habilitado por padrão devido ao impacto sobre o desempenho.</span><span class="sxs-lookup"><span data-stu-id="a417d-115">Collecting execution statistics is not enabled by default due to performance impact.</span></span>  
  
 <span data-ttu-id="a417d-116">Você pode habilitar e desabilitar a coleta de estatísticas nos procedimentos armazenados compilados de modo nativo usando [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a417d-116">You can enable and disable statistics collection on natively compiled stored procedures using [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="a417d-117">Quando a coleta de estatísticas está habilitada com [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), você pode usar [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) para monitorar o desempenho de um procedimento armazenado nativamente compilado.</span><span class="sxs-lookup"><span data-stu-id="a417d-117">When statistics collection is enabled with [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), you can use [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="a417d-118">Quando a coleta de estatísticas está habilitada com [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), você pode usar [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) para monitorar o desempenho de um procedimento armazenado nativamente compilado.</span><span class="sxs-lookup"><span data-stu-id="a417d-118">When statistics collection is enabled with [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), you can use [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="a417d-119">No início da coleta, habilite a coleta de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="a417d-119">At the start of collection, enable statistics collection.</span></span> <span data-ttu-id="a417d-120">Depois, execute o procedimento armazenado compilado de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="a417d-120">Then, execute the natively compiled stored procedure.</span></span> <span data-ttu-id="a417d-121">No final da coleta, desabilite a coleta de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="a417d-121">At the end of collection, disable statistics collection.</span></span> <span data-ttu-id="a417d-122">Em seguida, analise as estatísticas de execução retornadas pelos DMVs.</span><span class="sxs-lookup"><span data-stu-id="a417d-122">Then, analyze the execution statistics returned by the DMVs.</span></span>  
  
 <span data-ttu-id="a417d-123">Depois que você coletar estatísticas, as estatísticas de execução de procedimentos armazenados compilados de modo nativo poderão ser consultadas para um procedimento com [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) e para consultas com [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a417d-123">After you collect statistics, the execution statistics for natively compiled stored procedures can be queried for a procedure with [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql), and for queries with [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a417d-124">Para procedimentos armazenados compilados de modo nativo, quando a coleta de estatísticas estiver habilitada, o tempo de trabalho será coletado em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="a417d-124">For natively compiled stored procedures when statistics collection is enabled, worker time is collected in milliseconds.</span></span> <span data-ttu-id="a417d-125">Se a consulta for executada em menos de um milissegundo, o valor será 0.</span><span class="sxs-lookup"><span data-stu-id="a417d-125">If the query executes in less than a millisecond, the value will be 0.</span></span> <span data-ttu-id="a417d-126">Para procedimentos armazenados compilados de modo nativo, o **total_worker_time** pode não ser preciso se várias execuções levarem menos de 1 milissegundo.</span><span class="sxs-lookup"><span data-stu-id="a417d-126">For natively compiled stored procedures, **total_worker_time** may not be accurate if many executions take less than 1 millisecond.</span></span>  
  
 <span data-ttu-id="a417d-127">A seguinte consulta retorna os nomes de procedimento e as estatísticas de execução para procedimentos armazenados compilados de modo nativo no banco de dados atual, após a coleta de estatísticas:</span><span class="sxs-lookup"><span data-stu-id="a417d-127">The following query returns the procedure names and execution statistics for natively compiled stored procedures in the current database, after statistics collection:</span></span>  
  
```sql  
select object_id,  
       object_name(object_id) as 'object name',  
       cached_time,  
       last_execution_time,  
       execution_count,  
       total_worker_time,  
       last_worker_time,  
       min_worker_time,  
       max_worker_time,  
       total_elapsed_time,  
       last_elapsed_time,  
       min_elapsed_time,  
       max_elapsed_time   
from sys.dm_exec_procedure_stats  
where database_id=db_id() and object_id in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by total_worker_time desc  
```  
  
 <span data-ttu-id="a417d-128">A seguinte consulta retorna o texto da consulta, bem como as estatísticas de execução para todas as consultas em procedimentos armazenados compilados de modo nativo no banco de dados atual, para as quais as estatísticas foram coletadas, ordenadas pelo tempo de trabalho total, em ordem decrescente:</span><span class="sxs-lookup"><span data-stu-id="a417d-128">The following query returns the query text as well as execution statistics for all queries in natively compiled stored procedures in the current database for which statistics have been collected, ordered by total worker time, in descending order:</span></span>  
  
```sql  
select st.objectid,   
       object_name(st.objectid) as 'object name',   
       SUBSTRING(st.text, (qs.statement_start_offset/2) + 1, ((qs.statement_end_offset-qs.statement_start_offset)/2) + 1) as 'query text',   
       qs.creation_time,  
       qs.last_execution_time,  
       qs.execution_count,  
       qs.total_worker_time,  
       qs.last_worker_time,  
       qs.min_worker_time,  
       qs.max_worker_time,  
       qs.total_elapsed_time,  
       qs.last_elapsed_time,  
       qs.min_elapsed_time,  
       qs.max_elapsed_time  
from sys.dm_exec_query_stats qs cross apply sys.dm_exec_sql_text(sql_handle) st  
where  st.dbid=db_id() and st.objectid in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by qs.total_worker_time desc  
```  
  
 <span data-ttu-id="a417d-129">Os procedimentos armazenados compilados de modo nativo dão suporte ao SHOWPLAN_XML (plano de execução estimado).</span><span class="sxs-lookup"><span data-stu-id="a417d-129">Natively compiled stored procedures support SHOWPLAN_XML (estimated execution plan).</span></span> <span data-ttu-id="a417d-130">O plano de execução estimado pode ser usado para inspecionar o plano de consulta, para localizar quaisquer problemas de plano incorreto.</span><span class="sxs-lookup"><span data-stu-id="a417d-130">The estimated execution plan can be used to inspect the query plan, to find any bad plan issues.</span></span> <span data-ttu-id="a417d-131">As razões comuns de planos incorretos são:</span><span class="sxs-lookup"><span data-stu-id="a417d-131">Common reasons for bad plans are:</span></span>  
  
-   <span data-ttu-id="a417d-132">As estatísticas não foram atualizadas antes da criação do procedimento.</span><span class="sxs-lookup"><span data-stu-id="a417d-132">Stats were not updated before the procedure was created.</span></span>  
  
-   <span data-ttu-id="a417d-133">Índices ausentes</span><span class="sxs-lookup"><span data-stu-id="a417d-133">Missing indexes</span></span>  
  
 <span data-ttu-id="a417d-134">O plano de execução XML é obtido executando o seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a417d-134">Showplan XML is obtained by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
SET SHOWPLAN_XML ON  
GO  
EXEC my_proc   
GO  
SET SHOWPLAN_XML OFF  
GO  
```  
  
 <span data-ttu-id="a417d-135">Como alternativa, no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selecione o nome do procedimento e clique em **Exibir Plano de Execução Estimado**.</span><span class="sxs-lookup"><span data-stu-id="a417d-135">Alternatively, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the procedure name and click **Display Estimated Execution Plan**.</span></span>  
  
 <span data-ttu-id="a417d-136">O plano de execução estimado para procedimentos armazenados compilados de modo nativo mostra os operadores e as expressões para as consultas no procedimento.</span><span class="sxs-lookup"><span data-stu-id="a417d-136">The estimated execution plan for natively compiled stored procedures shows the query operators and expressions for the queries in the procedure.</span></span> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="a417d-137">não dá suporte a todos os atributos SHOWPLAN_XML para procedimentos armazenados compilados de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="a417d-137">does not support all SHOWPLAN_XML attributes for natively compiled stored procedures.</span></span> <span data-ttu-id="a417d-138">Por exemplo, os atributos relacionados ao cálculo de custos do otimizador de consulta não fazem parte do SHOWPLAN_XML para o procedimento.</span><span class="sxs-lookup"><span data-stu-id="a417d-138">For example, attributes related to query optimizer costing are not part of the SHOWPLAN_XML for the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a417d-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a417d-139">See Also</span></span>  
 [<span data-ttu-id="a417d-140">Procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="a417d-140">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
