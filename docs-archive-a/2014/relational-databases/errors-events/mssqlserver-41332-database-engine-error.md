---
title: MSSQLSERVER_41332 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41332 (Database Engine error)
ms.assetid: d3403c3e-d178-4006-b6c9-c18609562db5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72a87838673f07f7a40596517ab54533d944e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575879"
---
# <a name="mssqlserver_41332"></a><span data-ttu-id="6c781-102">MSSQLSERVER_41332</span><span class="sxs-lookup"><span data-stu-id="6c781-102">MSSQLSERVER_41332</span></span>
    
## <a name="details"></a><span data-ttu-id="6c781-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="6c781-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c781-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="6c781-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="6c781-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="6c781-105">Event ID</span></span>|<span data-ttu-id="6c781-106">41332</span><span class="sxs-lookup"><span data-stu-id="6c781-106">41332</span></span>|  
|<span data-ttu-id="6c781-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="6c781-107">Event Source</span></span>|<span data-ttu-id="6c781-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6c781-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6c781-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6c781-109">Component</span></span>|<span data-ttu-id="6c781-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6c781-110">SQLEngine</span></span>|  
|<span data-ttu-id="6c781-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="6c781-111">Symbolic Name</span></span>|<span data-ttu-id="6c781-112">SQL_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="6c781-112">SQL_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="6c781-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="6c781-113">Message Text</span></span>|<span data-ttu-id="6c781-114">As tabelas com otimização de memória e os procedimentos armazenados compilados originalmente não poderão ser acessados ou criados quando o TRANSACTION ISOLATION LEVEL de sessão estiver definido como SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="6c781-114">Memory optimized tables and natively compiled stored procedures cannot be accessed or created when the session TRANSACTION ISOLATION LEVEL is set to SNAPSHOT.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6c781-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="6c781-115">Explanation</span></span>  
 <span data-ttu-id="6c781-116">A transação foi iniciada no nível de isolamento do instantâneo e tentou usar um recurso incompatível.</span><span class="sxs-lookup"><span data-stu-id="6c781-116">The transaction was started in snapshot isolation level and then attempted to use an incompatible feature.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6c781-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="6c781-117">User Action</span></span>  
 <span data-ttu-id="6c781-118">Inicie a transação com um nível de isolamento diferente.</span><span class="sxs-lookup"><span data-stu-id="6c781-118">Start the transaction with a different isolation level.</span></span> <span data-ttu-id="6c781-119">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="6c781-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c781-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6c781-120">See Also</span></span>  
 [<span data-ttu-id="6c781-121">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="6c781-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
