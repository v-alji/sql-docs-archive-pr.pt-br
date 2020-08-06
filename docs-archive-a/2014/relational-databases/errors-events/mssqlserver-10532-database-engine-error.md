---
title: MSSQLSERVER_10532 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10532 (Database Engine error)
ms.assetid: 01da29ee-bf67-433f-8148-587a7e8d1d76
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26ab34c319eff62737eae337828247fdfd7e901b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684757"
---
# <a name="mssqlserver_10532"></a><span data-ttu-id="5d434-102">MSSQLSERVER_10532</span><span class="sxs-lookup"><span data-stu-id="5d434-102">MSSQLSERVER_10532</span></span>
    
## <a name="details"></a><span data-ttu-id="5d434-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5d434-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d434-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="5d434-104">Product Name</span></span>|<span data-ttu-id="5d434-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d434-105">SQL Server</span></span>|  
|<span data-ttu-id="5d434-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="5d434-106">Event ID</span></span>|<span data-ttu-id="5d434-107">10532</span><span class="sxs-lookup"><span data-stu-id="5d434-107">10532</span></span>|  
|<span data-ttu-id="5d434-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="5d434-108">Event Source</span></span>|<span data-ttu-id="5d434-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5d434-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5d434-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5d434-110">Component</span></span>|<span data-ttu-id="5d434-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5d434-111">SQLEngine</span></span>|  
|<span data-ttu-id="5d434-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="5d434-112">Symbolic Name</span></span>|<span data-ttu-id="5d434-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="5d434-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="5d434-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="5d434-114">Message Text</span></span>|<span data-ttu-id="5d434-115">Não é possível criar o guia de plano '%.\*ls' porque o lote ou o módulo especificado por `@plan_handle` não contém uma instrução qualificada para um guia de plano.</span><span class="sxs-lookup"><span data-stu-id="5d434-115">Cannot create plan guide '%.\*ls' because the batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span> <span data-ttu-id="5d434-116">Especifique outro valor para `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="5d434-116">Specify a different value for `@plan_handle`.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5d434-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="5d434-117">Explanation</span></span>  
 <span data-ttu-id="5d434-118">O lote ou o módulo especificado por `@plan_handle` não contém uma instrução qualificada para um guia de plano.</span><span class="sxs-lookup"><span data-stu-id="5d434-118">The batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d434-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5d434-119">User Action</span></span>  
 <span data-ttu-id="5d434-120">Especifique outro valor para `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="5d434-120">Specify a different value for `@plan_handle`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d434-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5d434-121">See Also</span></span>  
 <span data-ttu-id="5d434-122">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="5d434-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="5d434-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d434-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="5d434-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5d434-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
