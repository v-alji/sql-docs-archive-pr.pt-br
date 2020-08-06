---
title: MSSQLSERVER_10519 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10519 (Database Engine error)
ms.assetid: 3be393a1-b186-41ae-afb9-a3d07ff354bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0ec584649842f787b1de9d2ea6d161aea6970250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683542"
---
# <a name="mssqlserver_10519"></a><span data-ttu-id="2da3f-102">MSSQLSERVER_10519</span><span class="sxs-lookup"><span data-stu-id="2da3f-102">MSSQLSERVER_10519</span></span>
    
## <a name="details"></a><span data-ttu-id="2da3f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2da3f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2da3f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2da3f-104">Product Name</span></span>|<span data-ttu-id="2da3f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2da3f-105">SQL Server</span></span>|  
|<span data-ttu-id="2da3f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2da3f-106">Event ID</span></span>|<span data-ttu-id="2da3f-107">10519</span><span class="sxs-lookup"><span data-stu-id="2da3f-107">10519</span></span>|  
|<span data-ttu-id="2da3f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2da3f-108">Event Source</span></span>|<span data-ttu-id="2da3f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2da3f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2da3f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2da3f-110">Component</span></span>|<span data-ttu-id="2da3f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2da3f-111">SQLEngine</span></span>|  
|<span data-ttu-id="2da3f-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2da3f-112">Symbolic Name</span></span>|<span data-ttu-id="2da3f-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span><span class="sxs-lookup"><span data-stu-id="2da3f-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span></span>|  
|<span data-ttu-id="2da3f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2da3f-114">Message Text</span></span>|<span data-ttu-id="2da3f-115">Não é possível criar o guia de plano '%.\*ls' porque as dicas especificadas em `@hints` não podem ser aplicadas à instrução especificada por `@stmt` ou `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="2da3f-115">Cannot create plan guide '%.\*ls' because the hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span> <span data-ttu-id="2da3f-116">Verifique se as dicas podem ser aplicadas à instrução.</span><span class="sxs-lookup"><span data-stu-id="2da3f-116">Verify that the hints can be applied to the statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2da3f-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="2da3f-117">Explanation</span></span>  
 <span data-ttu-id="2da3f-118">Não é possível aplicar as dicas especificadas em `@hints` à instrução especificada por `@stmt` ou `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="2da3f-118">The hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2da3f-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2da3f-119">User Action</span></span>  
 <span data-ttu-id="2da3f-120">Especifique dicas que possam ser aplicadas à instrução.</span><span class="sxs-lookup"><span data-stu-id="2da3f-120">Specify hints that can be applied to the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da3f-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2da3f-121">See Also</span></span>  
 <span data-ttu-id="2da3f-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2da3f-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="2da3f-123">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="2da3f-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="2da3f-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2da3f-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
