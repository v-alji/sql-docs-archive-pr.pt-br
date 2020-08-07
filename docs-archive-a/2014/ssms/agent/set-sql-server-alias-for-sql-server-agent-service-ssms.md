---
title: Definir um filtro de rastreamento (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
ms.assetid: 7b976a84-7381-43a6-a828-ba83ada71cbe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47d797c84a05f50da026280f6e197f965d804426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575539"
---
# <a name="set-a-trace-filter-transact-sql"></a><span data-ttu-id="6cb5a-102">Definir um filtro de rastreamento (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6cb5a-102">Set a Trace Filter (Transact-SQL)</span></span>
  <span data-ttu-id="6cb5a-103">Este tópico descreve como usar procedimentos armazenados para criar um filtro que recupera apenas as informações que você necessita em um evento que está sendo rastreado.</span><span class="sxs-lookup"><span data-stu-id="6cb5a-103">This topic describes how to use stored procedures to create a filter that retrieves only the information you need on an event being traced.</span></span>  
  
### <a name="to-set-a-trace-filter"></a><span data-ttu-id="6cb5a-104">Definir um filtro de rastreamento</span><span class="sxs-lookup"><span data-stu-id="6cb5a-104">To set a trace filter</span></span>  
  
1.  <span data-ttu-id="6cb5a-105">Se o rastreamento já estiver em execução, execute **sp_trace_setstatus** especificando **@status = 0** para parar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="6cb5a-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="6cb5a-106">Execute **sp_trace_setfilter** para configurar o tipo de informações para recuperar para o evento que está sendo rastreado.</span><span class="sxs-lookup"><span data-stu-id="6cb5a-106">Execute **sp_trace_setfilter** to configure the type of information to retrieve for the event being traced.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6cb5a-107">Ao contrário dos procedimentos armazenados comuns, os parâmetros de todos os procedimentos armazenados do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>) são estritamente tipados e não são compatíveis com a conversão automática de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="6cb5a-107">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="6cb5a-108">Se esses parâmetros não forem chamados com os tipos de dados com parâmetro de entrada corretos, como especificado na descrição do argumento, o procedimento armazenado retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="6cb5a-108">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure will return an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb5a-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6cb5a-109">See Also</span></span>  
 <span data-ttu-id="6cb5a-110">[Filtrar um rastreamento](../../relational-databases/sql-trace/filter-a-trace.md) </span><span class="sxs-lookup"><span data-stu-id="6cb5a-110">[Filter a Trace](../../relational-databases/sql-trace/filter-a-trace.md) </span></span>  
 <span data-ttu-id="6cb5a-111">[&#41;&#40;Transact-SQL de sp_trace_setfilter](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cb5a-111">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 <span data-ttu-id="6cb5a-112">[&#41;&#40;Transact-SQL de sp_trace_setstatus](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cb5a-112">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="6cb5a-113">[Procedimentos armazenados do sistema &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cb5a-113">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="6cb5a-114">Procedimentos armazenados do SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6cb5a-114">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
