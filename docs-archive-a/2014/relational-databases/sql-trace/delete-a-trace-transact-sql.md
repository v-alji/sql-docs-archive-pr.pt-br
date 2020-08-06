---
title: Excluir um rastreamento (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], deleting
- removing traces
- deleting traces
ms.assetid: a5502814-b281-42dd-b885-5c9368025ae6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b3551cff36ef6e2c2e9cc6a4d9b7056ae44cb950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574609"
---
# <a name="delete-a-trace-transact-sql"></a><span data-ttu-id="06980-102">Excluir um rastreamento (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06980-102">Delete a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="06980-103">Este tópico descreve como usar procedimentos armazenados para excluir um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="06980-103">This topic describes how to use stored procedures to delete a trace.</span></span>  
  
 <span data-ttu-id="06980-104">Para obter um exemplo de como usar procedimentos armazenados de rastreamento, veja [Criar um rastreamento &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="06980-104">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span></span>  
  
### <a name="to-delete-a-trace"></a><span data-ttu-id="06980-105">Para excluir um rastreamento</span><span class="sxs-lookup"><span data-stu-id="06980-105">To delete a trace</span></span>  
  
1.  <span data-ttu-id="06980-106">Execute **sp_trace_setstatus** especificando **@status = 0** para interromper o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="06980-106">Execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="06980-107">Execute **sp_trace_setstatus** especificando **@status = 2** para encerrar o rastreamento e excluir suas informações do servidor.</span><span class="sxs-lookup"><span data-stu-id="06980-107">Execute **sp_trace_setstatus** by specifying **@status = 2** to close the trace and delete its information from the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="06980-108">Um rastreamento deve ser interrompido primeiro antes de ser encerrado.</span><span class="sxs-lookup"><span data-stu-id="06980-108">A trace must be stopped first before it can be closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06980-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="06980-109">See Also</span></span>  
 <span data-ttu-id="06980-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06980-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="06980-111">[Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06980-111">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="06980-112">Procedimentos armazenados do SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06980-112">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
