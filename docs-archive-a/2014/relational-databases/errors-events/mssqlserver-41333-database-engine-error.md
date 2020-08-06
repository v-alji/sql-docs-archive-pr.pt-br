---
title: MSSQLSERVER_41333 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41333 (Database Engine error)
ms.assetid: c3c3ae9a-1e4c-4de6-ba72-2f393375b053
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ba3cfc9627b4b44c3c9eccc620fb16bb94b861b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680963"
---
# <a name="mssqlserver_41333"></a><span data-ttu-id="8f0f5-102">MSSQLSERVER_41333</span><span class="sxs-lookup"><span data-stu-id="8f0f5-102">MSSQLSERVER_41333</span></span>
    
## <a name="details"></a><span data-ttu-id="8f0f5-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8f0f5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f0f5-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8f0f5-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8f0f5-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8f0f5-105">Event ID</span></span>|<span data-ttu-id="8f0f5-106">41333</span><span class="sxs-lookup"><span data-stu-id="8f0f5-106">41333</span></span>|  
|<span data-ttu-id="8f0f5-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8f0f5-107">Event Source</span></span>|<span data-ttu-id="8f0f5-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8f0f5-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8f0f5-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8f0f5-109">Component</span></span>|<span data-ttu-id="8f0f5-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8f0f5-110">SQLEngine</span></span>|  
|<span data-ttu-id="8f0f5-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8f0f5-111">Symbolic Name</span></span>|<span data-ttu-id="8f0f5-112">CROSS_CONTAINER_ISOLATION_FAILURE</span><span class="sxs-lookup"><span data-stu-id="8f0f5-112">CROSS_CONTAINER_ISOLATION_FAILURE</span></span>|  
|<span data-ttu-id="8f0f5-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8f0f5-113">Message Text</span></span>|<span data-ttu-id="8f0f5-114">As transações a seguir devem acessar tabelas com otimização de memória e procedimentos armazenados em compilados nativamente em isolamento de instantâneo: Transações RepeatableRead, transações Serializable e transações que acessam tabelas não otimizadas para memória em isolamento RepeatableRead ou Serializable.</span><span class="sxs-lookup"><span data-stu-id="8f0f5-114">The following transactions must access memory optimized tables and natively compiled stored procedures under snapshot isolation: RepeatableRead transactions, Serializable transactions, and transactions that access tables that are not memory optimized in RepeatableRead or Serializable isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8f0f5-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="8f0f5-115">Explanation</span></span>  
 <span data-ttu-id="8f0f5-116">Há restrições relacionadas ao usuário dos níveis de isolamento mais altos entre transações baseadas em disco e transações XTP.</span><span class="sxs-lookup"><span data-stu-id="8f0f5-116">There are restrictions against the user of the higher isolation levels between disk based transactions and XTP transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f0f5-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8f0f5-117">User Action</span></span>  
 <span data-ttu-id="8f0f5-118">Não tente operações de alto nível de isolamento em tabelas com otimização de memória (e em procedimentos originalmente compilados) e tabelas baseadas em disco.</span><span class="sxs-lookup"><span data-stu-id="8f0f5-118">Don't attempt high level isolation operations on memory-optimized tables (and natively compiled procedures) and disk based tables.</span></span>  
  
 <span data-ttu-id="8f0f5-119">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="8f0f5-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f0f5-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f0f5-120">See Also</span></span>  
 [<span data-ttu-id="8f0f5-121">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="8f0f5-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
