---
title: Categoria de evento Procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Stored Procedures event category [SQL Server]
- SQL Server event classes, Stored Procedures event category
- event classes [SQL Server], Stored Procedures event category
ms.assetid: 71bebaa3-a05a-4695-b349-078cecd0949a
author: stevestein
ms.author: sstein
ms.openlocfilehash: df2e0d9a4c077ff16eba09bc5ebb6447d5d27595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686289"
---
# <a name="stored-procedures-event-category"></a><span data-ttu-id="155e0-102">Categoria de evento dos procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="155e0-102">Stored Procedures Event Category</span></span>
  <span data-ttu-id="155e0-103">A categoria de evento **Procedimentos armazenados** contém eventos de procedimentos gerais armazenados.</span><span class="sxs-lookup"><span data-stu-id="155e0-103">The **Stored Procedures** event category contains general stored procedure events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="155e0-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="155e0-104">In This Section</span></span>  
  
|<span data-ttu-id="155e0-105">Tópico</span><span class="sxs-lookup"><span data-stu-id="155e0-105">Topic</span></span>|<span data-ttu-id="155e0-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="155e0-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="155e0-107">Classe de evento RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="155e0-107">RPC:Completed Event Class</span></span>](rpc-completed-event-class.md)|<span data-ttu-id="155e0-108">Indica que uma RPC (chamada de procedimento remoto) foi completada.</span><span class="sxs-lookup"><span data-stu-id="155e0-108">Indicates that a remote procedure call (RPC) has been completed.</span></span>|  
|[<span data-ttu-id="155e0-109">Classe de evento PreConnect:Completed</span><span class="sxs-lookup"><span data-stu-id="155e0-109">PreConnect:Completed Event Class</span></span>](preconnect-completed-event-class.md)|<span data-ttu-id="155e0-110">Indica quando a função de classificação Administrador de Recursos conclui a execução.</span><span class="sxs-lookup"><span data-stu-id="155e0-110">Indicates when the Resource Governor classifier function finishes execution.</span></span>|  
|[<span data-ttu-id="155e0-111">Classe de evento PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="155e0-111">PreConnect:Starting Event Class</span></span>](preconnect-starting-event-class.md)|<span data-ttu-id="155e0-112">Indica quando a função de classificação Administrador de Recursos inicia a execução.</span><span class="sxs-lookup"><span data-stu-id="155e0-112">Indicates when the Resource Governor classifier function starts execution.</span></span>|  
|[<span data-ttu-id="155e0-113">Classe de evento RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="155e0-113">RPC Output Parameter Event Class</span></span>](rpc-output-parameter-event-class.md)|<span data-ttu-id="155e0-114">Rastreia os valores do parâmetro de saída das chamadas de procedimento remoto após a execução.</span><span class="sxs-lookup"><span data-stu-id="155e0-114">Traces the output parameter values of remote procedure calls after execution.</span></span>|  
|[<span data-ttu-id="155e0-115">Classe de evento RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="155e0-115">RPC:Starting Event Class</span></span>](rpc-starting-event-class.md)|<span data-ttu-id="155e0-116">Indica que uma chamada de procedimento remoto está iniciando.</span><span class="sxs-lookup"><span data-stu-id="155e0-116">Indicates that a remote procedure call is starting.</span></span>|  
|[<span data-ttu-id="155e0-117">Classe de evento SP:CacheHit</span><span class="sxs-lookup"><span data-stu-id="155e0-117">SP:CacheHit Event Class</span></span>](sp-cachehit-event-class.md)|<span data-ttu-id="155e0-118">Indica que o procedimento armazenado está em cache.</span><span class="sxs-lookup"><span data-stu-id="155e0-118">Indicates that the stored procedure is in the cache.</span></span>|  
|[<span data-ttu-id="155e0-119">Classe de evento SP:CacheInsert</span><span class="sxs-lookup"><span data-stu-id="155e0-119">SP:CacheInsert Event Class</span></span>](sp-cacheinsert-event-class.md)|<span data-ttu-id="155e0-120">Indica que o procedimento armazenado foi colocado no cache.</span><span class="sxs-lookup"><span data-stu-id="155e0-120">Indicates that the stored procedure has been brought into the cache.</span></span>|  
|[<span data-ttu-id="155e0-121">Classe de evento SP:CacheMiss</span><span class="sxs-lookup"><span data-stu-id="155e0-121">SP:CacheMiss Event Class</span></span>](sp-cachemiss-event-class.md)|<span data-ttu-id="155e0-122">Indica que o procedimento armazenado não foi encontrado no cache.</span><span class="sxs-lookup"><span data-stu-id="155e0-122">Indicates that the stored procedure was not found in the cache.</span></span>|  
|[<span data-ttu-id="155e0-123">Classe de evento SP:CacheRemove</span><span class="sxs-lookup"><span data-stu-id="155e0-123">SP:CacheRemove Event Class</span></span>](sp-cacheremove-event-class.md)|<span data-ttu-id="155e0-124">Indica que o procedimento armazenado foi removido do cache.</span><span class="sxs-lookup"><span data-stu-id="155e0-124">Indicates that the stored procedure has been removed from the cache.</span></span>|  
|[<span data-ttu-id="155e0-125">Classe de evento SP:Completed</span><span class="sxs-lookup"><span data-stu-id="155e0-125">SP:Completed Event Class</span></span>](sp-completed-event-class.md)|<span data-ttu-id="155e0-126">Indica que a execução do procedimento armazenado foi concluída.</span><span class="sxs-lookup"><span data-stu-id="155e0-126">Indicates that execution of the stored procedure has completed.</span></span>|  
|[<span data-ttu-id="155e0-127">Classe de evento SP:Recompile</span><span class="sxs-lookup"><span data-stu-id="155e0-127">SP:Recompile Event Class</span></span>](sp-recompile-event-class.md)|<span data-ttu-id="155e0-128">Indica que o procedimento armazenado foi recompilado.</span><span class="sxs-lookup"><span data-stu-id="155e0-128">Indicates that the stored procedure has been recompiled.</span></span>|  
|[<span data-ttu-id="155e0-129">Classe de evento SP:Starting</span><span class="sxs-lookup"><span data-stu-id="155e0-129">SP:Starting Event Class</span></span>](sp-starting-event-class.md)|<span data-ttu-id="155e0-130">Indica que a execução do procedimento armazenado está iniciando.</span><span class="sxs-lookup"><span data-stu-id="155e0-130">Indicates that execution of the stored procedure is starting.</span></span>|  
|[<span data-ttu-id="155e0-131">Classe de evento SP:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="155e0-131">SP:StmtCompleted Event Class</span></span>](sp-stmtcompleted-event-class.md)|<span data-ttu-id="155e0-132">Indica que uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] em um procedimento armazenado foi concluída.</span><span class="sxs-lookup"><span data-stu-id="155e0-132">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has completed.</span></span>|  
|[<span data-ttu-id="155e0-133">Classe de evento SP: StmtStarting</span><span class="sxs-lookup"><span data-stu-id="155e0-133">SP:StmtStarting Event Class</span></span>](sp-stmtstarting-event-class.md)|<span data-ttu-id="155e0-134">Indica que uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] em um procedimento armazenado foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="155e0-134">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has started.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="155e0-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="155e0-135">See Also</span></span>  
 <span data-ttu-id="155e0-136">[Eventos estendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="155e0-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="155e0-137">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="155e0-137">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
