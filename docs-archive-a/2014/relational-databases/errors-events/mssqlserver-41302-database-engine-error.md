---
title: MSSQLSERVER_41302 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41302 (Database Engine error)
ms.assetid: 01e75618-afec-4232-ba68-93ab7bc31003
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 751dac91378c002a7e6c6c619ddaf12be8173400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572578"
---
# <a name="mssqlserver_41302"></a><span data-ttu-id="127e2-102">MSSQLSERVER_41302</span><span class="sxs-lookup"><span data-stu-id="127e2-102">MSSQLSERVER_41302</span></span>
    
## <a name="details"></a><span data-ttu-id="127e2-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="127e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="127e2-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="127e2-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="127e2-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="127e2-105">Event ID</span></span>|<span data-ttu-id="127e2-106">41302</span><span class="sxs-lookup"><span data-stu-id="127e2-106">41302</span></span>|  
|<span data-ttu-id="127e2-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="127e2-107">Event Source</span></span>|<span data-ttu-id="127e2-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="127e2-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="127e2-109">Componente</span><span class="sxs-lookup"><span data-stu-id="127e2-109">Component</span></span>|<span data-ttu-id="127e2-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="127e2-110">SQLEngine</span></span>|  
|<span data-ttu-id="127e2-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="127e2-111">Symbolic Name</span></span>|<span data-ttu-id="127e2-112">WRITE_WRITE_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="127e2-112">WRITE_WRITE_CONFLICT</span></span>|  
|<span data-ttu-id="127e2-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="127e2-113">Message Text</span></span>|<span data-ttu-id="127e2-114">A transação atual tentou atualizar um registro que foi atualizado desde que esta transação foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="127e2-114">The current transaction attempted to update a record that has been updated since this transaction started.</span></span> <span data-ttu-id="127e2-115">A transação foi anulada.</span><span class="sxs-lookup"><span data-stu-id="127e2-115">The transaction was aborted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="127e2-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="127e2-116">Explanation</span></span>  
 <span data-ttu-id="127e2-117">A transação encontrou um conflito de gravação/gravação e a instrução foi encerrada.</span><span class="sxs-lookup"><span data-stu-id="127e2-117">The transaction encountered a write/write conflict and the statement terminated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="127e2-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="127e2-118">User Action</span></span>  
 <span data-ttu-id="127e2-119">Repita a operação posteriormente em outra transação.</span><span class="sxs-lookup"><span data-stu-id="127e2-119">Retry the operation later in a different transaction.</span></span> <span data-ttu-id="127e2-120">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="127e2-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="127e2-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="127e2-121">See Also</span></span>  
 [<span data-ttu-id="127e2-122">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="127e2-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
