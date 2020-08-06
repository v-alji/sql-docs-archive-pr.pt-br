---
title: MSSQLSERVER_10531 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10531 (Database Engine error)
ms.assetid: bb40e994-231c-44ce-933f-8d767fb2f450
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6230c046a9eb7b900377888c59a3a492f2b89f73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680468"
---
# <a name="mssqlserver_10531"></a><span data-ttu-id="8dd26-102">MSSQLSERVER_10531</span><span class="sxs-lookup"><span data-stu-id="8dd26-102">MSSQLSERVER_10531</span></span>
    
## <a name="details"></a><span data-ttu-id="8dd26-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8dd26-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8dd26-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8dd26-104">Product Name</span></span>|<span data-ttu-id="8dd26-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8dd26-105">SQL Server</span></span>|  
|<span data-ttu-id="8dd26-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8dd26-106">Event ID</span></span>|<span data-ttu-id="8dd26-107">10531</span><span class="sxs-lookup"><span data-stu-id="8dd26-107">10531</span></span>|  
|<span data-ttu-id="8dd26-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8dd26-108">Event Source</span></span>|<span data-ttu-id="8dd26-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8dd26-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8dd26-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8dd26-110">Component</span></span>|<span data-ttu-id="8dd26-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8dd26-111">SQLEngine</span></span>|  
|<span data-ttu-id="8dd26-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8dd26-112">Symbolic Name</span></span>|<span data-ttu-id="8dd26-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="8dd26-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="8dd26-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8dd26-114">Message Text</span></span>|<span data-ttu-id="8dd26-115">Não é possível criar o guia de plano '%.\*ls' do cache porque o usuário não tem as permissões adequadas.</span><span class="sxs-lookup"><span data-stu-id="8dd26-115">Cannot create plan guide '%.\*ls' from cache because the user does not have adequate permissions.</span></span> <span data-ttu-id="8dd26-116">Conceda a permissão VIEW SERVER STATE para o usuário que está criando o guia de plano.</span><span class="sxs-lookup"><span data-stu-id="8dd26-116">Grant the VIEW SERVER STATE permission to the user creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8dd26-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="8dd26-117">Explanation</span></span>  
 <span data-ttu-id="8dd26-118">O usuário não tem as permissões adequadas para criar o guia de plano especificado a partir do cache de planos.</span><span class="sxs-lookup"><span data-stu-id="8dd26-118">The user does not have adequate permissions to create the specified plan guide from the plan cache.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8dd26-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8dd26-119">User Action</span></span>  
 <span data-ttu-id="8dd26-120">Conceda a permissão VIEW SERVER STATE ao usuário que está criando o guia de plano.</span><span class="sxs-lookup"><span data-stu-id="8dd26-120">Grant VIEW SERVER STATE permission to the user creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd26-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8dd26-121">See Also</span></span>  
 <span data-ttu-id="8dd26-122">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="8dd26-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="8dd26-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dd26-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="8dd26-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8dd26-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
