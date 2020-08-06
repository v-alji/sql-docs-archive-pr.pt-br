---
title: MSSQLSERVER_41325 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41325 (Database Engine error)
ms.assetid: 97c6a8bb-139a-44f3-9ed5-f46d047e8ed3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a512d7db6529876259d889d04aabf3d07747cafe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680962"
---
# <a name="mssqlserver_41325"></a><span data-ttu-id="56fa0-102">MSSQLSERVER_41325</span><span class="sxs-lookup"><span data-stu-id="56fa0-102">MSSQLSERVER_41325</span></span>
    
## <a name="details"></a><span data-ttu-id="56fa0-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="56fa0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56fa0-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="56fa0-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="56fa0-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="56fa0-105">Event ID</span></span>|<span data-ttu-id="56fa0-106">41325</span><span class="sxs-lookup"><span data-stu-id="56fa0-106">41325</span></span>|  
|<span data-ttu-id="56fa0-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="56fa0-107">Event Source</span></span>|<span data-ttu-id="56fa0-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="56fa0-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="56fa0-109">Componente</span><span class="sxs-lookup"><span data-stu-id="56fa0-109">Component</span></span>|<span data-ttu-id="56fa0-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="56fa0-110">SQLEngine</span></span>|  
|<span data-ttu-id="56fa0-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="56fa0-111">Symbolic Name</span></span>|<span data-ttu-id="56fa0-112">HK_TX_COMMIT_SR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="56fa0-112">HK_TX_COMMIT_SR_VALIDATION</span></span>|  
|<span data-ttu-id="56fa0-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="56fa0-113">Message Text</span></span>|<span data-ttu-id="56fa0-114">A transação atual não foi confirmada devido a uma falha de validação serializável.</span><span class="sxs-lookup"><span data-stu-id="56fa0-114">The current transaction failed to commit due to a serializable validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="56fa0-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="56fa0-115">Explanation</span></span>  
 <span data-ttu-id="56fa0-116">A transação encontrou uma falha de validação e agora está condenada.</span><span class="sxs-lookup"><span data-stu-id="56fa0-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56fa0-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="56fa0-117">User Action</span></span>  
 <span data-ttu-id="56fa0-118">Repita a transação com falha.</span><span class="sxs-lookup"><span data-stu-id="56fa0-118">Retry the failed transaction.</span></span> <span data-ttu-id="56fa0-119">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="56fa0-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56fa0-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56fa0-120">See Also</span></span>  
 [<span data-ttu-id="56fa0-121">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="56fa0-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
