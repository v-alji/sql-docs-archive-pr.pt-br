---
title: MSSQLSERVER_10533 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10533 (Database Engine error)
ms.assetid: cc2fbdab-7b90-415f-a1f9-066824344283
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccef25bc8f594cb6ea0b60aefab838ef27cda6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574061"
---
# <a name="mssqlserver_10533"></a><span data-ttu-id="5004a-102">MSSQLSERVER_10533</span><span class="sxs-lookup"><span data-stu-id="5004a-102">MSSQLSERVER_10533</span></span>
    
## <a name="details"></a><span data-ttu-id="5004a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5004a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5004a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="5004a-104">Product Name</span></span>|<span data-ttu-id="5004a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5004a-105">SQL Server</span></span>|  
|<span data-ttu-id="5004a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="5004a-106">Event ID</span></span>|<span data-ttu-id="5004a-107">10533</span><span class="sxs-lookup"><span data-stu-id="5004a-107">10533</span></span>|  
|<span data-ttu-id="5004a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="5004a-108">Event Source</span></span>|<span data-ttu-id="5004a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5004a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5004a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5004a-110">Component</span></span>|<span data-ttu-id="5004a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5004a-111">SQLEngine</span></span>|  
|<span data-ttu-id="5004a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="5004a-112">Symbolic Name</span></span>|<span data-ttu-id="5004a-113">PG_NAME_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="5004a-113">PG_NAME_TOO_BIG</span></span>|  
|<span data-ttu-id="5004a-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="5004a-114">Message Text</span></span>|<span data-ttu-id="5004a-115">Não é possível criar o guia de plano '%.\*ls' porque seu nome tem mais de 124 caracteres, o número máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="5004a-115">Cannot create plan guide '%.\*ls' because the plan guide name exceeds 124 characters, the maximum number allowed.</span></span> <span data-ttu-id="5004a-116">Especifique um nome com menos de 125 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5004a-116">Specify a name that contains fewer than 125 characters.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5004a-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="5004a-117">Explanation</span></span>  
 <span data-ttu-id="5004a-118">O nome do guia de plano tem mais de 124 caracteres, que é o número máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="5004a-118">The plan guide name exceeds 124 characters, the maximum number allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5004a-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5004a-119">User Action</span></span>  
 <span data-ttu-id="5004a-120">Especifique um nome com menos de 125 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5004a-120">Specify a name that contains fewer than 125 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5004a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5004a-121">See Also</span></span>  
 <span data-ttu-id="5004a-122">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="5004a-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="5004a-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5004a-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="5004a-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5004a-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
