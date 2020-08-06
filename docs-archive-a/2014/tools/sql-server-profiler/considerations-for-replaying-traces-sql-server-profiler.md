---
title: Considerações para reproduzir rastreamentos (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 73fa339f-b71a-4be4-97ca-d4ae84c8b90b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c2f030a0191596e40ef1ee9e2b0b2d4da34c773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678417"
---
# <a name="considerations-for-replaying-traces-sql-server-profiler"></a><span data-ttu-id="ae9b2-102">Considerações para reproduzir rastreamentos (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="ae9b2-102">Considerations for Replaying Traces (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="ae9b2-103">não pode reproduzir os seguintes tipos de rastreamento:</span><span class="sxs-lookup"><span data-stu-id="ae9b2-103">cannot replay the following kinds of traces:</span></span>  
  
-   <span data-ttu-id="ae9b2-104">Rastreamentos que contêm replicação transacional e outra atividade de log de transações.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-104">Traces that contain transactional replication and other transaction log activity.</span></span> <span data-ttu-id="ae9b2-105">Esses eventos são ignorados.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-105">These events are skipped.</span></span> <span data-ttu-id="ae9b2-106">Outros tipos de replicação não marcam o log de transações e, logo, não são afetados.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-106">Other types of replication do not mark the transaction log so they are not affected.</span></span>  
  
-   <span data-ttu-id="ae9b2-107">Rastreamentos que contêm operações que envolvem identificadores globalmente exclusivos (GUID).</span><span class="sxs-lookup"><span data-stu-id="ae9b2-107">Traces that contain operations that involve globally unique identifiers (GUID).</span></span> <span data-ttu-id="ae9b2-108">Esses eventos serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-108">These events will be skipped.</span></span>  
  
-   <span data-ttu-id="ae9b2-109">Rastreamentos que contêm operações em colunas **text**, **ntext**e **image** envolvendo o utilitário **bcp** , as instruções BULK INSERT, READTEXT, WRITETEXT e UPDATETEXT e operações de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-109">Traces that contain operations on **text**, **ntext**, and **image** columns involving the **bcp** utility, the BULK INSERT, READTEXT, WRITETEXT, and UPDATETEXT statements, and full-text operations.</span></span> <span data-ttu-id="ae9b2-110">Esses eventos são ignorados.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-110">These events are skipped.</span></span>  
  
-   <span data-ttu-id="ae9b2-111">Rastreamentos que contêm associação de sessões: os procedimentos armazenados do sistema **sp_getbindtoken** e **sp_bindsession** .</span><span class="sxs-lookup"><span data-stu-id="ae9b2-111">Traces that contain session binding: **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span> <span data-ttu-id="ae9b2-112">Esses eventos são ignorados.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-112">These events are skipped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae9b2-113">Se você não usar o modelo de reprodução pré-configurado (**TSQL_Replay**) e não capturar todos os dados necessários, o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] não reproduzirá o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ae9b2-113">If you do not use the preconfigured replay template (**TSQL_Replay**), and do not capture all required data, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] does not replay the trace.</span></span> <span data-ttu-id="ae9b2-114">Para obter mais informações, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae9b2-114">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
 <span data-ttu-id="ae9b2-115">Para obter informações sobre quais permissões são necessárias para reproduzir um rastreamento, veja [Permissões necessárias para executar o SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="ae9b2-115">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9b2-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae9b2-116">See Also</span></span>  
 <span data-ttu-id="ae9b2-117">[Utilitário bcp](../bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ae9b2-117">[bcp Utility](../bcp-utility.md) </span></span>  
 <span data-ttu-id="ae9b2-118">[Referência de classe de evento do SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ae9b2-118">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="ae9b2-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ae9b2-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span></span>  
 <span data-ttu-id="ae9b2-120">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ae9b2-120">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 <span data-ttu-id="ae9b2-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ae9b2-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="ae9b2-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ae9b2-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span></span>  
 <span data-ttu-id="ae9b2-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ae9b2-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span></span>  
 [<span data-ttu-id="ae9b2-124">UPDATETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ae9b2-124">UPDATETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/updatetext-transact-sql)  
  
  
