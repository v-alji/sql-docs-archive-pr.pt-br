---
title: MSSQLSERVER_10502 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10502 (Database Engine error)
ms.assetid: 26d9b64d-4299-4b55-92d0-0a32a3688c0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eeec3a3adf318cadc96501938f8a5565f1c07670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569546"
---
# <a name="mssqlserver_10502"></a><span data-ttu-id="2af31-102">MSSQLSERVER_10502</span><span class="sxs-lookup"><span data-stu-id="2af31-102">MSSQLSERVER_10502</span></span>
    
## <a name="details"></a><span data-ttu-id="2af31-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2af31-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2af31-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2af31-104">Product Name</span></span>|<span data-ttu-id="2af31-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2af31-105">SQL Server</span></span>|  
|<span data-ttu-id="2af31-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2af31-106">Event ID</span></span>|<span data-ttu-id="2af31-107">10502</span><span class="sxs-lookup"><span data-stu-id="2af31-107">10502</span></span>|  
|<span data-ttu-id="2af31-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2af31-108">Event Source</span></span>|<span data-ttu-id="2af31-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2af31-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2af31-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2af31-110">Component</span></span>|<span data-ttu-id="2af31-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2af31-111">SQLEngine</span></span>|  
|<span data-ttu-id="2af31-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2af31-112">Symbolic Name</span></span>|<span data-ttu-id="2af31-113">PG_DUP_FOUND</span><span class="sxs-lookup"><span data-stu-id="2af31-113">PG_DUP_FOUND</span></span>|  
|<span data-ttu-id="2af31-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2af31-114">Message Text</span></span>|<span data-ttu-id="2af31-115">Não é possível criar o guia de plano '%.\*ls' porque a instrução especificada por @stmt e @module_or_batch ou por @plan_handle e @statement_start_offset, corresponde ao guia de plano '%.\*ls' existente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2af31-115">Cannot create plan guide '%.\*ls' because the statement specified by @stmt and @module_or_batch, or by @plan_handle and @statement_start_offset, matches the existing plan guide '%.\*ls' in the database.</span></span> <span data-ttu-id="2af31-116">Descarte o guia de plano existente antes de criar o novo.</span><span class="sxs-lookup"><span data-stu-id="2af31-116">Drop the existing plan guide before creating the new plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2af31-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="2af31-117">Explanation</span></span>  
 <span data-ttu-id="2af31-118">Há um guia de plano relativo à instrução especificada.</span><span class="sxs-lookup"><span data-stu-id="2af31-118">A plan guide exists for the specified statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2af31-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2af31-119">User Action</span></span>  
 <span data-ttu-id="2af31-120">Descarte o guia de plano existente antes de criar o novo.</span><span class="sxs-lookup"><span data-stu-id="2af31-120">Drop the existing plan guide before creating the new plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af31-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2af31-121">See Also</span></span>  
 <span data-ttu-id="2af31-122">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="2af31-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="2af31-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2af31-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="2af31-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2af31-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
