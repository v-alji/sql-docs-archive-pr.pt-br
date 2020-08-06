---
title: MSSQLSERVER_10509 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10509 (Database Engine error)
ms.assetid: e9dd5357-ee3d-420a-9a89-d12ab5404e73
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73194c7da553bf27acb78d8c4e7d71bc93f457d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685176"
---
# <a name="mssqlserver_10509"></a><span data-ttu-id="207d6-102">MSSQLSERVER_10509</span><span class="sxs-lookup"><span data-stu-id="207d6-102">MSSQLSERVER_10509</span></span>
    
## <a name="details"></a><span data-ttu-id="207d6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="207d6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="207d6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="207d6-104">Product Name</span></span>|<span data-ttu-id="207d6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="207d6-105">SQL Server</span></span>|  
|<span data-ttu-id="207d6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="207d6-106">Event ID</span></span>|<span data-ttu-id="207d6-107">10509</span><span class="sxs-lookup"><span data-stu-id="207d6-107">10509</span></span>|  
|<span data-ttu-id="207d6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="207d6-108">Event Source</span></span>|<span data-ttu-id="207d6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="207d6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="207d6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="207d6-110">Component</span></span>|<span data-ttu-id="207d6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="207d6-111">SQLEngine</span></span>|  
|<span data-ttu-id="207d6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="207d6-112">Symbolic Name</span></span>|<span data-ttu-id="207d6-113">PG_INVALID_STMT</span><span class="sxs-lookup"><span data-stu-id="207d6-113">PG_INVALID_STMT</span></span>|  
|<span data-ttu-id="207d6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="207d6-114">Message Text</span></span>|<span data-ttu-id="207d6-115">Não é possível criar o guia de plano '%.\*ls' porque a instrução especificada por `@stmt` ou `@statement_start_offset` contém um erro de sintaxe ou não está qualificada para uso em um guia de plano.</span><span class="sxs-lookup"><span data-stu-id="207d6-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span> <span data-ttu-id="207d6-116">Especifique uma única instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] válida ou uma posição inicial válida da instrução no lote.</span><span class="sxs-lookup"><span data-stu-id="207d6-116">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="207d6-117">Para obter uma posição inicial válida, consulte a coluna statement_start_offset na função de gerenciamento dinâmico sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="207d6-117">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="207d6-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="207d6-118">Explanation</span></span>  
 <span data-ttu-id="207d6-119">A instrução especificada por `@stmt` ou `@statement_start_offset` contém um erro de sintaxe ou não está qualificada para uso em um guia de plano.</span><span class="sxs-lookup"><span data-stu-id="207d6-119">The statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="207d6-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="207d6-120">User Action</span></span>  
 <span data-ttu-id="207d6-121">Especifique uma única instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] válida ou uma posição inicial válida da instrução no lote.</span><span class="sxs-lookup"><span data-stu-id="207d6-121">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="207d6-122">Para obter uma posição inicial válida, consulte a coluna statement_start_offset na função de gerenciamento dinâmico sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="207d6-122">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207d6-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="207d6-123">See Also</span></span>  
 <span data-ttu-id="207d6-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="207d6-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="207d6-125">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="207d6-125">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="207d6-126">[sys. dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="207d6-126">[sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span></span>  
 [<span data-ttu-id="207d6-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="207d6-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
