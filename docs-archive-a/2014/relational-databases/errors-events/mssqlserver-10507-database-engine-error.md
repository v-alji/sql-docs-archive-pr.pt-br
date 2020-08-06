---
title: MSSQLSERVER_10507 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10507 (Database Engine error)
ms.assetid: cd83fa81-ac37-4eda-a3c3-17610b051de2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a80e48948c03b370c07742fabbb3cf8eb3e74315
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684237"
---
# <a name="mssqlserver_10507"></a><span data-ttu-id="aaea2-102">MSSQLSERVER_10507</span><span class="sxs-lookup"><span data-stu-id="aaea2-102">MSSQLSERVER_10507</span></span>
    
## <a name="details"></a><span data-ttu-id="aaea2-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="aaea2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aaea2-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="aaea2-104">Product Name</span></span>|<span data-ttu-id="aaea2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aaea2-105">SQL Server</span></span>|  
|<span data-ttu-id="aaea2-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="aaea2-106">Event ID</span></span>|<span data-ttu-id="aaea2-107">10507</span><span class="sxs-lookup"><span data-stu-id="aaea2-107">10507</span></span>|  
|<span data-ttu-id="aaea2-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="aaea2-108">Event Source</span></span>|<span data-ttu-id="aaea2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aaea2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aaea2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aaea2-110">Component</span></span>|<span data-ttu-id="aaea2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aaea2-111">SQLEngine</span></span>|  
|<span data-ttu-id="aaea2-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="aaea2-112">Symbolic Name</span></span>|<span data-ttu-id="aaea2-113">PG_STMT_DOES_NOT_MATCH</span><span class="sxs-lookup"><span data-stu-id="aaea2-113">PG_STMT_DOES_NOT_MATCH</span></span>|  
|<span data-ttu-id="aaea2-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="aaea2-114">Message Text</span></span>|<span data-ttu-id="aaea2-115">Não é possível criar o guia de plano '%.\*ls' porque a instrução especificada por `@stmt` e `@module_or_batch` ou por `@plan_handle` e `@statement_start_offset`, não corresponde a nenhuma instrução no módulo ou no lote especificado.</span><span class="sxs-lookup"><span data-stu-id="aaea2-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` and `@module_or_batch`, or by `@plan_handle` and `@statement_start_offset`, does not match any statement in the specified module or batch.</span></span> <span data-ttu-id="aaea2-116">Modifique os valores para que correspondam a uma instrução no módulo ou lote.</span><span class="sxs-lookup"><span data-stu-id="aaea2-116">Modify the values to match a statement in the module or batch.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aaea2-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="aaea2-117">Explanation</span></span>  
 <span data-ttu-id="aaea2-118">Uma instrução no módulo ou lote especificado não correspondeu à instrução especificada ou ao valor de deslocamento da instrução.</span><span class="sxs-lookup"><span data-stu-id="aaea2-118">A statement in the specified module or batch could not be matched to the specified statement or statement offset value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aaea2-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="aaea2-119">User Action</span></span>  
 <span data-ttu-id="aaea2-120">Modifique os valores de parâmetro especificados para que correspondam a uma instrução no módulo ou lote.</span><span class="sxs-lookup"><span data-stu-id="aaea2-120">Modify the specified parameter values to match a statement in the module or batch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaea2-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aaea2-121">See Also</span></span>  
 <span data-ttu-id="aaea2-122">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="aaea2-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="aaea2-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aaea2-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="aaea2-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aaea2-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
