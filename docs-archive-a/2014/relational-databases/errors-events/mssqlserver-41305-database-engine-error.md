---
title: MSSQLSERVER_41305 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41305 (Database Engine error)
ms.assetid: a96e5083-ff97-4003-a900-07942454151d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9c00e20ec220d7fcee0da4e99c2ef35817dae67f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575146"
---
# <a name="mssqlserver_41305"></a><span data-ttu-id="8b720-102">MSSQLSERVER_41305</span><span class="sxs-lookup"><span data-stu-id="8b720-102">MSSQLSERVER_41305</span></span>
    
## <a name="details"></a><span data-ttu-id="8b720-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8b720-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b720-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8b720-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8b720-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8b720-105">Event ID</span></span>|<span data-ttu-id="8b720-106">41305</span><span class="sxs-lookup"><span data-stu-id="8b720-106">41305</span></span>|  
|<span data-ttu-id="8b720-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8b720-107">Event Source</span></span>|<span data-ttu-id="8b720-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8b720-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8b720-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8b720-109">Component</span></span>|<span data-ttu-id="8b720-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8b720-110">SQLEngine</span></span>|  
|<span data-ttu-id="8b720-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8b720-111">Symbolic Name</span></span>|<span data-ttu-id="8b720-112">HK_TX_COMMIT_RR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="8b720-112">HK_TX_COMMIT_RR_VALIDATION</span></span>|  
|<span data-ttu-id="8b720-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8b720-113">Message Text</span></span>|<span data-ttu-id="8b720-114">A transação atual não foi confirmada devido a uma falha de validação de leitura repetida.</span><span class="sxs-lookup"><span data-stu-id="8b720-114">The current transaction failed to commit due to a repeatable read validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8b720-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="8b720-115">Explanation</span></span>  
 <span data-ttu-id="8b720-116">A transação encontrou uma falha de validação e agora está condenada.</span><span class="sxs-lookup"><span data-stu-id="8b720-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
 <span data-ttu-id="8b720-117">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="8b720-117">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8b720-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8b720-118">User Action</span></span>  
 <span data-ttu-id="8b720-119">Repita a transação com falha.</span><span class="sxs-lookup"><span data-stu-id="8b720-119">Retry the failed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b720-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b720-120">See Also</span></span>  
 [<span data-ttu-id="8b720-121">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="8b720-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
