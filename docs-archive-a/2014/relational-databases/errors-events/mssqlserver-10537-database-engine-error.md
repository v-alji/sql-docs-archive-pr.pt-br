---
title: MSSQLSERVER_10537 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10537 (Database Engine error)
ms.assetid: 728469a4-6523-4a37-925f-a950d75420fa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b1baccad5236bd8c1a71024b7dd542cc9d11cbd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681680"
---
# <a name="mssqlserver_10537"></a><span data-ttu-id="cfb07-102">MSSQLSERVER_10537</span><span class="sxs-lookup"><span data-stu-id="cfb07-102">MSSQLSERVER_10537</span></span>
    
## <a name="details"></a><span data-ttu-id="cfb07-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cfb07-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfb07-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="cfb07-104">Product Name</span></span>|<span data-ttu-id="cfb07-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfb07-105">SQL Server</span></span>|  
|<span data-ttu-id="cfb07-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="cfb07-106">Event ID</span></span>|<span data-ttu-id="cfb07-107">10537</span><span class="sxs-lookup"><span data-stu-id="cfb07-107">10537</span></span>|  
|<span data-ttu-id="cfb07-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="cfb07-108">Event Source</span></span>|<span data-ttu-id="cfb07-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cfb07-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cfb07-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cfb07-110">Component</span></span>|<span data-ttu-id="cfb07-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cfb07-111">SQLEngine</span></span>|  
|<span data-ttu-id="cfb07-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="cfb07-112">Symbolic Name</span></span>|<span data-ttu-id="cfb07-113">PG_DUP_ENABLED</span><span class="sxs-lookup"><span data-stu-id="cfb07-113">PG_DUP_ENABLED</span></span>|  
|<span data-ttu-id="cfb07-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="cfb07-114">Message Text</span></span>|<span data-ttu-id="cfb07-115">Não é possível habilitar o guia de plano '%.\*ls' porque o guia de plano habilitado '%.\*ls' contém o mesmo escopo e valor de deslocamento inicial da instrução.</span><span class="sxs-lookup"><span data-stu-id="cfb07-115">Cannot enable plan guide '%.\*ls' because the enabled plan guide '%.\*ls' contains the same scope and starting offset value as the statement.</span></span> <span data-ttu-id="cfb07-116">Desabilite o guia de plano existente antes de habilitar o guia de plano especificado.</span><span class="sxs-lookup"><span data-stu-id="cfb07-116">Disable the existing plan guide before enabling the specified plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cfb07-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="cfb07-117">Explanation</span></span>  
 <span data-ttu-id="cfb07-118">Um guia de plano existente contém o mesmo escopo e valor de deslocamento inicial que a instrução no guia de plano especificado.</span><span class="sxs-lookup"><span data-stu-id="cfb07-118">An existing plan guide contains the same scope and starting offset value as the statement in the specified plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cfb07-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="cfb07-119">User Action</span></span>  
 <span data-ttu-id="cfb07-120">Desabilite o guia de plano existente antes de habilitar o guia de plano especificado.</span><span class="sxs-lookup"><span data-stu-id="cfb07-120">Disable the existing plan guide before enabling the specified plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb07-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cfb07-121">See Also</span></span>  
 <span data-ttu-id="cfb07-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfb07-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="cfb07-123">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="cfb07-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="cfb07-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cfb07-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
