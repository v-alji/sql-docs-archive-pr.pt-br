---
title: MSSQLSERVER_10535 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10535 (Database Engine error)
ms.assetid: 478fd978-11d9-4155-8329-f599fdbec14b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 439d282f18490a4353d6528276eaf7e4231c503b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680463"
---
# <a name="mssqlserver_10535"></a><span data-ttu-id="32769-102">MSSQLSERVER_10535</span><span class="sxs-lookup"><span data-stu-id="32769-102">MSSQLSERVER_10535</span></span>
    
## <a name="details"></a><span data-ttu-id="32769-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="32769-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32769-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="32769-104">Product Name</span></span>|<span data-ttu-id="32769-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="32769-105">SQL Server</span></span>|  
|<span data-ttu-id="32769-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="32769-106">Event ID</span></span>|<span data-ttu-id="32769-107">10535</span><span class="sxs-lookup"><span data-stu-id="32769-107">10535</span></span>|  
|<span data-ttu-id="32769-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="32769-108">Event Source</span></span>|<span data-ttu-id="32769-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="32769-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="32769-110">Componente</span><span class="sxs-lookup"><span data-stu-id="32769-110">Component</span></span>|<span data-ttu-id="32769-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="32769-111">SQLEngine</span></span>|  
|<span data-ttu-id="32769-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="32769-112">Symbolic Name</span></span>|<span data-ttu-id="32769-113">PG_NO_PLAN</span><span class="sxs-lookup"><span data-stu-id="32769-113">PG_NO_PLAN</span></span>|  
|<span data-ttu-id="32769-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="32769-114">Message Text</span></span>|<span data-ttu-id="32769-115">Não é possível criar o guia de plano '%.\*ls' porque não foi encontrado no cache de planos um plano que corresponda ao identificador de plano especificado.</span><span class="sxs-lookup"><span data-stu-id="32769-115">Cannot create plan guide '%.\*ls' because a plan was not found in the plan cache that corresponds to the specified plan handle.</span></span> <span data-ttu-id="32769-116">Especifique um identificador de plano em cache.</span><span class="sxs-lookup"><span data-stu-id="32769-116">Specify a cached plan handle.</span></span> <span data-ttu-id="32769-117">Para obter uma lista de identificadores de plano em cache, consulte a exibição de gerenciamento dinâmico sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="32769-117">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="32769-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="32769-118">Explanation</span></span>  
 <span data-ttu-id="32769-119">Não foi localizado no cache de planos um plano que corresponda ao identificador de plano especificado.</span><span class="sxs-lookup"><span data-stu-id="32769-119">A plan was not found in the plan cache that corresponds to the specified plan handle.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32769-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="32769-120">User Action</span></span>  
 <span data-ttu-id="32769-121">Especifique um identificador de plano em cache.</span><span class="sxs-lookup"><span data-stu-id="32769-121">Specify a cached plan handle.</span></span> <span data-ttu-id="32769-122">Para obter uma lista de identificadores de plano em cache, consulte a exibição de gerenciamento dinâmico sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="32769-122">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32769-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32769-123">See Also</span></span>  
 <span data-ttu-id="32769-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="32769-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span></span>  
 [<span data-ttu-id="32769-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="32769-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql)  
  
  
