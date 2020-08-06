---
title: MSSQLSERVER_10538 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: edc6abf192a3341f9b84c99e99071343cc882c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680460"
---
# <a name="mssqlserver_10538"></a><span data-ttu-id="ac2a3-102">MSSQLSERVER_10538</span><span class="sxs-lookup"><span data-stu-id="ac2a3-102">MSSQLSERVER_10538</span></span>
    
## <a name="details"></a><span data-ttu-id="ac2a3-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ac2a3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ac2a3-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ac2a3-104">Product Name</span></span>|<span data-ttu-id="ac2a3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac2a3-105">SQL Server</span></span>|  
|<span data-ttu-id="ac2a3-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ac2a3-106">Event ID</span></span>|<span data-ttu-id="ac2a3-107">10538</span><span class="sxs-lookup"><span data-stu-id="ac2a3-107">10538</span></span>|  
|<span data-ttu-id="ac2a3-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ac2a3-108">Event Source</span></span>|<span data-ttu-id="ac2a3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ac2a3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ac2a3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ac2a3-110">Component</span></span>|<span data-ttu-id="ac2a3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ac2a3-111">SQLEngine</span></span>|  
|<span data-ttu-id="ac2a3-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ac2a3-112">Symbolic Name</span></span>|<span data-ttu-id="ac2a3-113">PG_INVALID_PLANGUIDE_HANDLE</span><span class="sxs-lookup"><span data-stu-id="ac2a3-113">PG_INVALID_PLANGUIDE_HANDLE</span></span>|  
|<span data-ttu-id="ac2a3-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ac2a3-114">Message Text</span></span>|<span data-ttu-id="ac2a3-115">Não foi possível encontrar o guia de plano porque a ID do guia de plano especificada é NULL ou inválida ou você não tem permissão no objeto referenciado pelo guia de plano.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-115">Cannot find the plan guide either because the specified plan guide ID is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span> <span data-ttu-id="ac2a3-116">Verifique se a ID do guia de plano é válida, se a sessão atual está definida com o contexto de banco de dados correto e se você tem a permissão ALTER DATABASE ou ALTER no objeto referenciado pelo guia de plano.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-116">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have either ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ac2a3-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="ac2a3-117">Explanation</span></span>  
 <span data-ttu-id="ac2a3-118">A ID do plano de guia especificado é NULL ou inválida ou você não tem permissão no objeto referenciado pelo guia de plano.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-118">The ID of the specified plan guide is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ac2a3-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ac2a3-119">User Action</span></span>  
 <span data-ttu-id="ac2a3-120">Verifique se a ID do guia de plano é válida, se a sessão atual está definida com o contexto de banco de dados correto e se você tem a permissão ALTER DATABASE ou ALTER no objeto referenciado pelo guia de plano.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-120">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2a3-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ac2a3-121">See Also</span></span>  
 <span data-ttu-id="ac2a3-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ac2a3-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="ac2a3-123">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="ac2a3-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="ac2a3-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ac2a3-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
