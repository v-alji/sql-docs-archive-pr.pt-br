---
title: Categoria de eventos de erros e de avisos (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Errors and Warnings event category [SQL Server]
- SQL Server event classes, Errors and Warnings event category
- event classes [SQL Server], Errors and Warnings event category
ms.assetid: 249c19b5-af68-4433-80f6-337395176641
author: stevestein
ms.author: sstein
ms.openlocfilehash: d55f37f5401f60ddfeec340af1ae6d532eb6ad01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682232"
---
# <a name="errors-and-warnings-event-category-database-engine"></a><span data-ttu-id="c5366-102">Categoria de eventos de erros e de avisos (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="c5366-102">Errors and Warnings Event Category (Database Engine)</span></span>
  <span data-ttu-id="c5366-103">A categoria de evento **Errors and Warnings** contém eventos de erros gerais e advertências.</span><span class="sxs-lookup"><span data-stu-id="c5366-103">The **Errors and Warnings** event category contains general error and warning events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5366-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c5366-104">In This Section</span></span>  
  
|<span data-ttu-id="c5366-105">Tópico</span><span class="sxs-lookup"><span data-stu-id="c5366-105">Topic</span></span>|<span data-ttu-id="c5366-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c5366-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c5366-107">Classe de evento Attention</span><span class="sxs-lookup"><span data-stu-id="c5366-107">Attention Event Class</span></span>](attention-event-class.md)|<span data-ttu-id="c5366-108">Indica que ocorreu um evento **Atenção** .</span><span class="sxs-lookup"><span data-stu-id="c5366-108">Indicates that an **Attention** event has occurred.</span></span>|  
|[<span data-ttu-id="c5366-109">Classe de evento Background Job Error</span><span class="sxs-lookup"><span data-stu-id="c5366-109">Background Job Error Event Class</span></span>](background-job-error-event-class.md)|<span data-ttu-id="c5366-110">Indica que uma tarefa em segundo plano terminou de forma anormal.</span><span class="sxs-lookup"><span data-stu-id="c5366-110">Indicates that a background job has terminated abnormally.</span></span>|  
|[<span data-ttu-id="c5366-111">Classe de evento Bitmap Warning</span><span class="sxs-lookup"><span data-stu-id="c5366-111">Bitmap Warning Event Class</span></span>](bitmap-warning-event-class.md)|<span data-ttu-id="c5366-112">Indica que a filtragem de bitmap foi desabilitada em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="c5366-112">Indicates that bitmap filtering has been disabled in a query.</span></span>|  
|[<span data-ttu-id="c5366-113">Classe de evento Blocked Process Report</span><span class="sxs-lookup"><span data-stu-id="c5366-113">Blocked Process Report Event Class</span></span>](blocked-process-report-event-class.md)|<span data-ttu-id="c5366-114">Indica que uma tarefa foi bloqueada para mais do que um período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="c5366-114">Indicates that a task has been blocked for more than a specified amount of time.</span></span>|  
|[<span data-ttu-id="c5366-115">Classe de evento CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="c5366-115">CPU Threshold Exceeded Event Class</span></span>](cpu-threshold-exceeded-event-class.md)|<span data-ttu-id="c5366-116">Indica que o gerenciador de recursos detecta uma consulta que excede o limite de CPU especificado.</span><span class="sxs-lookup"><span data-stu-id="c5366-116">Indicates that the Resource Governor detects a query that exceeds the specified CPU threshold.</span></span>|  
|[<span data-ttu-id="c5366-117">Classe de evento ErrorLog</span><span class="sxs-lookup"><span data-stu-id="c5366-117">ErrorLog Event Class</span></span>](errorlog-event-class.md)|<span data-ttu-id="c5366-118">Indica que eventos de erro foram registrados no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5366-118">Indicates that error events have been logged in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>|  
|[<span data-ttu-id="c5366-119">Classe de evento EventLog</span><span class="sxs-lookup"><span data-stu-id="c5366-119">EventLog Event Class</span></span>](eventlog-event-class.md)|<span data-ttu-id="c5366-120">Indica que eventos foram registrados no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="c5366-120">Indicates that events have been logged in the Windows event log.</span></span>|  
|[<span data-ttu-id="c5366-121">Classe de evento Exception</span><span class="sxs-lookup"><span data-stu-id="c5366-121">Exception Event Class</span></span>](exception-event-class.md)|<span data-ttu-id="c5366-122">Indica que uma exceção ocorreu no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5366-122">Indicates that an exception has occurred in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c5366-123">Classe de evento Exchange Spill</span><span class="sxs-lookup"><span data-stu-id="c5366-123">Exchange Spill Event Class</span></span>](exchange-spill-event-class.md)|<span data-ttu-id="c5366-124">Indica que os buffers de comunicação em um plano de consulta paralelo foram gravados no banco de dados tempdb.</span><span class="sxs-lookup"><span data-stu-id="c5366-124">Indicates that communication buffers in a parallel query plan have been written to the tempdb database.</span></span>|  
|[<span data-ttu-id="c5366-125">Classe de evento Execution Warnings</span><span class="sxs-lookup"><span data-stu-id="c5366-125">Execution Warnings Event Class</span></span>](execution-warnings-event-class.md)|<span data-ttu-id="c5366-126">Indica que ocorreram advertências de concessão de memória durante a execução de uma instrução ou um procedimento armazenado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5366-126">Indicates that memory grant warnings occurred during the execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statement or stored procedure.</span></span>|  
|[<span data-ttu-id="c5366-127">Classe de evento Hash Warning</span><span class="sxs-lookup"><span data-stu-id="c5366-127">Hash Warning Event Class</span></span>](hash-warning-event-class.md)|<span data-ttu-id="c5366-128">Indica que ocorreu uma recursão de hash ou abandono de hash durante uma operação de hash.</span><span class="sxs-lookup"><span data-stu-id="c5366-128">Indicates that a hash recursion or hash bailout has occurred during a hashing operation.</span></span>|  
|[<span data-ttu-id="c5366-129">Classe de evento Missing Column Statistics</span><span class="sxs-lookup"><span data-stu-id="c5366-129">Missing Column Statistics Event Class</span></span>](missing-column-statistics-event-class.md)|<span data-ttu-id="c5366-130">Indica que estatísticas de coluna que podem ter sido úteis para o otimizador não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c5366-130">Indicates that column statistics that could have been useful for the optimizer are not available.</span></span>|  
|[<span data-ttu-id="c5366-131">Classe de evento Missing Join Predicate</span><span class="sxs-lookup"><span data-stu-id="c5366-131">Missing Join Predicate Event Class</span></span>](missing-join-predicate-event-class.md)|<span data-ttu-id="c5366-132">Indica que uma consulta que está sendo executada não tem nenhum predicado de junção.</span><span class="sxs-lookup"><span data-stu-id="c5366-132">Indicates that a query is being executed that has no join predicate.</span></span>|  
|[<span data-ttu-id="c5366-133">Classe de evento Sort Warnings</span><span class="sxs-lookup"><span data-stu-id="c5366-133">Sort Warnings Event Class</span></span>](sort-warnings-event-class.md)|<span data-ttu-id="c5366-134">Indica que operações de classificação não cabem na memória.</span><span class="sxs-lookup"><span data-stu-id="c5366-134">Indicates that sort operations do not fit into memory.</span></span>|  
|[<span data-ttu-id="c5366-135">Classe de evento User Error Message</span><span class="sxs-lookup"><span data-stu-id="c5366-135">User Error Message Event Class</span></span>](user-error-message-event-class.md)|<span data-ttu-id="c5366-136">Exibe mensagens de erro que são vistas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="c5366-136">Displays error messages that are seen by the user.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5366-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5366-137">See Also</span></span>  
 [<span data-ttu-id="c5366-138">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5366-138">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
