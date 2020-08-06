---
title: Modificar um rastreamento existente (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], modifying
- modifying traces
ms.assetid: 8792b43f-2510-44e3-9239-e73ad8227b89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 55b8172ef8e6188059c484ab41f1a719e0e9f8c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569845"
---
# <a name="modify-an-existing-trace-transact-sql"></a><span data-ttu-id="fb782-102">Modificar um rastreamento existente (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb782-102">Modify an Existing Trace (Transact-SQL)</span></span>
  <span data-ttu-id="fb782-103">Este tópico descreve como usar procedimentos armazenados para modificar um rastreamento existente.</span><span class="sxs-lookup"><span data-stu-id="fb782-103">This topic describes how to use stored procedures to modify an existing trace.</span></span>  
  
### <a name="to-modify-an-existing-trace"></a><span data-ttu-id="fb782-104">Modificar um rastreamento existente</span><span class="sxs-lookup"><span data-stu-id="fb782-104">To modify an existing trace</span></span>  
  
1.  <span data-ttu-id="fb782-105">Se o rastreamento já estiver em execução, execute **sp_trace_setstatus** especificando **@status = 0** para parar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="fb782-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="fb782-106">Para modificar eventos de rastreamento, execute **sp_trace_setevent** especificando as alterações pelos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fb782-106">To modify trace events, execute **sp_trace_setevent** by specifying the changes through the parameters.</span></span> <span data-ttu-id="fb782-107">Listado em ordem, os parâmetros são:</span><span class="sxs-lookup"><span data-stu-id="fb782-107">Listed in order, the parameters are:</span></span>  
  
    -   <span data-ttu-id="fb782-108">**@traceid**(ID do rastreamento)</span><span class="sxs-lookup"><span data-stu-id="fb782-108">**@traceid** (Trace ID)</span></span>  
  
    -   <span data-ttu-id="fb782-109">**@eventid**(ID do evento)</span><span class="sxs-lookup"><span data-stu-id="fb782-109">**@eventid** (Event ID)</span></span>  
  
    -   <span data-ttu-id="fb782-110">**@columnid**(ID da coluna)</span><span class="sxs-lookup"><span data-stu-id="fb782-110">**@columnid** (Column ID)</span></span>  
  
    -   <span data-ttu-id="fb782-111">**@on**NO</span><span class="sxs-lookup"><span data-stu-id="fb782-111">**@on** (ON)</span></span>  
  
     <span data-ttu-id="fb782-112">Ao modificar o **@on** parâmetro, tenha em mente sua interação com o **@columnid** parâmetro:</span><span class="sxs-lookup"><span data-stu-id="fb782-112">When you modify the **@on** parameter, keep in mind its interaction with the **@columnid** parameter:</span></span>  
  
    |<span data-ttu-id="fb782-113">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="fb782-113">ON</span></span>|<span data-ttu-id="fb782-114">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="fb782-114">Column ID</span></span>|<span data-ttu-id="fb782-115">Result</span><span class="sxs-lookup"><span data-stu-id="fb782-115">Result</span></span>|  
    |--------|---------------|------------|  
    |<span data-ttu-id="fb782-116">ON (**1**)</span><span class="sxs-lookup"><span data-stu-id="fb782-116">ON (**1**)</span></span>|<span data-ttu-id="fb782-117">NULO</span><span class="sxs-lookup"><span data-stu-id="fb782-117">NULL</span></span>|<span data-ttu-id="fb782-118">O evento é ativado.</span><span class="sxs-lookup"><span data-stu-id="fb782-118">Event is turned on.</span></span> <span data-ttu-id="fb782-119">Todas as colunas são limpas.</span><span class="sxs-lookup"><span data-stu-id="fb782-119">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="fb782-120">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fb782-120">NOT NULL</span></span>|<span data-ttu-id="fb782-121">A coluna é ativada para o evento especificado.</span><span class="sxs-lookup"><span data-stu-id="fb782-121">Column is turned on for the specified event.</span></span>|  
    |<span data-ttu-id="fb782-122">OFF (**0**)</span><span class="sxs-lookup"><span data-stu-id="fb782-122">OFF (**0**)</span></span>|<span data-ttu-id="fb782-123">NULO</span><span class="sxs-lookup"><span data-stu-id="fb782-123">NULL</span></span>|<span data-ttu-id="fb782-124">Evento é desativado.</span><span class="sxs-lookup"><span data-stu-id="fb782-124">Event is turned off.</span></span> <span data-ttu-id="fb782-125">Todas as colunas são limpas.</span><span class="sxs-lookup"><span data-stu-id="fb782-125">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="fb782-126">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fb782-126">NOT NULL</span></span>|<span data-ttu-id="fb782-127">A coluna é desativada para o evento especificado.</span><span class="sxs-lookup"><span data-stu-id="fb782-127">Column is turned off for the specified event.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="fb782-128">Ao contrário dos procedimentos armazenados comuns, os parâmetros de todos os procedimentos armazenados do [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>) são estritamente tipados e não são compatíveis com a conversão automática de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="fb782-128">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="fb782-129">Se esses parâmetros não forem chamados pelos tipos de dados com parâmetros de entrada corretos, como especificado na descrição do argumento, o procedimento armazenado retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="fb782-129">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fb782-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb782-130">See Also</span></span>  
 <span data-ttu-id="fb782-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb782-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="fb782-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb782-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="fb782-133">[Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb782-133">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="fb782-134">Procedimentos armazenados do SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb782-134">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
