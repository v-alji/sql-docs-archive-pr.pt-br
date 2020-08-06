---
title: Noções básicas sobre transações em tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 06075248-705e-4563-9371-b64cd609793c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0671bba8b7a0bda27ea27cf059cb9e3b1bb87b2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681061"
---
# <a name="understanding-transactions-on-memory-optimized-tables"></a><span data-ttu-id="08a8a-102">Compreendendo transações em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="08a8a-102">Understanding Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="08a8a-103">As transações acessam as tabelas com otimização de memória usando um formulário de controle de simultaneidade otimista e de várias versões.</span><span class="sxs-lookup"><span data-stu-id="08a8a-103">Transactions access memory-optimized tables using a form of optimistic, multi-version concurrency control.</span></span> <span data-ttu-id="08a8a-104">Isso significa que há versões diferentes de dados.</span><span class="sxs-lookup"><span data-stu-id="08a8a-104">This means that there are different versions of the data.</span></span> <span data-ttu-id="08a8a-105">Cada transação opera sua própria versão do banco de dados consistente transacionalmente, independentemente de outras transações simultaneamente em execução.</span><span class="sxs-lookup"><span data-stu-id="08a8a-105">Each transaction operates on its own transactionally consistent version of the database, independent from other concurrently running transactions.</span></span> <span data-ttu-id="08a8a-106">Além disso, as transações operam sob a suposição otimista de que não haverá conflitos com outras transações simultâneas.</span><span class="sxs-lookup"><span data-stu-id="08a8a-106">In addition, transactions operate under the optimistic assumption that there will be no conflicts with other, concurrent, transactions.</span></span> <span data-ttu-id="08a8a-107">Isso evita a necessidade de usar bloqueios, mas exige que o sistema detecte conflitos e encerre uma das transações conflitantes.</span><span class="sxs-lookup"><span data-stu-id="08a8a-107">This avoids the need to use locks, but does require the system to detect conflicts and terminate one of the conflicting transactions.</span></span> <span data-ttu-id="08a8a-108">Conflitos podem ocorrer apenas em transações de gravação/gravação e em transações de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="08a8a-108">Conflicts can occur only for write-write transactions and for read-write transactions.</span></span> <span data-ttu-id="08a8a-109">Se houver um conflito de gravação/gravação, uma transação de gravação será encerrada.</span><span class="sxs-lookup"><span data-stu-id="08a8a-109">If there is a write-write conflict, one write transaction is terminated.</span></span>  
  
 <span data-ttu-id="08a8a-110">Há semelhanças entre o controle de simultaneidade para tabelas com otimização de memória e o controle de simultaneidade para tabelas baseadas em disco, para os níveis de isolamento da transação READ_COMMITTED_SNAPSHOT e SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="08a8a-110">There are similarities between the concurrency control for memory-optimized tables and the concurrency control for disk-based tables for the READ_COMMITTED_SNAPSHOT and SNAPSHOT transaction isolation levels.</span></span> <span data-ttu-id="08a8a-111">(Para obter mais informações sobre tabelas baseadas em disco, consulte [Níveis de isolamento com base em controle de versão de linha no mecanismo de banco de dados](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span><span class="sxs-lookup"><span data-stu-id="08a8a-111">(For more information about disk-based tables, see [Row Versioning-based Isolation Levels in the Database Engine](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span></span>  
  
## <a name="topics-in-this-section"></a><span data-ttu-id="08a8a-112">Tópicos desta seção</span><span class="sxs-lookup"><span data-stu-id="08a8a-112">Topics in This Section</span></span>  
 <span data-ttu-id="08a8a-113">Esta seção sobre transações em tabelas com otimização de memória inclui os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="08a8a-113">This section on transactions in memory-optimized tables includes the following topics:</span></span>  
  
-   [<span data-ttu-id="08a8a-114">Diretrizes para níveis de isolamento da transação com tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="08a8a-114">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
-   [<span data-ttu-id="08a8a-115">Diretrizes para lógica de repetição das transações em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="08a8a-115">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="08a8a-116">Transações em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="08a8a-116">Transactions in Memory-Optimized Tables</span></span>](transactions-in-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="08a8a-117">Níveis de isolamento da transação</span><span class="sxs-lookup"><span data-stu-id="08a8a-117">Transaction Isolation Levels</span></span>](transaction-isolation-levels.md)  
  
-   [<span data-ttu-id="08a8a-118">Transações entre contêineres</span><span class="sxs-lookup"><span data-stu-id="08a8a-118">Cross-Container Transactions</span></span>](cross-container-transactions.md)  
  
 <span data-ttu-id="08a8a-119">Para obter mais informações, veja [Controlar a durabilidade da transação](../relational-databases/logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="08a8a-119">For more information, see [Control Transaction Durability](../relational-databases/logs/control-transaction-durability.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a8a-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08a8a-120">See Also</span></span>  
 [<span data-ttu-id="08a8a-121">Memory-Optimized Tables</span><span class="sxs-lookup"><span data-stu-id="08a8a-121">Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
