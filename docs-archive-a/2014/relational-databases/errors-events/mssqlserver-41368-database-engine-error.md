---
title: MSSQLSERVER_41368 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41368 (Database Engine error)
ms.assetid: abc71559-4c4d-4cce-a08f-3299dd167842
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 10e187223a3f35b4b21ede6965e3c9efea2e30c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680430"
---
# <a name="mssqlserver_41368"></a><span data-ttu-id="a4533-102">MSSQLSERVER_41368</span><span class="sxs-lookup"><span data-stu-id="a4533-102">MSSQLSERVER_41368</span></span>
    
## <a name="details"></a><span data-ttu-id="a4533-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a4533-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a4533-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a4533-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a4533-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a4533-105">Event ID</span></span>|<span data-ttu-id="a4533-106">41368</span><span class="sxs-lookup"><span data-stu-id="a4533-106">41368</span></span>|  
|<span data-ttu-id="a4533-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a4533-107">Event Source</span></span>|<span data-ttu-id="a4533-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a4533-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a4533-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a4533-109">Component</span></span>|<span data-ttu-id="a4533-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a4533-110">SQLEngine</span></span>|  
|<span data-ttu-id="a4533-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a4533-111">Symbolic Name</span></span>|<span data-ttu-id="a4533-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="a4533-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="a4533-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a4533-113">Message Text</span></span>|<span data-ttu-id="a4533-114">Há suporte para o acesso às tabelas com otimização de memória usando o nível de isolamento READ COMMITTED somente em transações de confirmação automática.</span><span class="sxs-lookup"><span data-stu-id="a4533-114">Accessing memory optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="a4533-115">Ele não tem suporte para transações implícitas ou explícitas.</span><span class="sxs-lookup"><span data-stu-id="a4533-115">It is not supported for explicit or implicit transactions.</span></span> <span data-ttu-id="a4533-116">Forneça um nível de isolamento com suporte para a tabela com otimização de memória usando uma dica de tabela, como WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="a4533-116">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a4533-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="a4533-117">Explanation</span></span>  
 <span data-ttu-id="a4533-118">O acesso às tabelas com otimização de memória usando o nível de isolamento READ COMMITTED tem suporte somente para transações de confirmação automática.</span><span class="sxs-lookup"><span data-stu-id="a4533-118">Accessing memory-optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="a4533-119">Para obter mais informações, consulte [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a4533-119">For more information, see [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span></span>  
  
 <span data-ttu-id="a4533-120">Ao acessar uma tabela com otimização de memória de uma transação explícita que é iniciada com BEGIN TRANSACTION, ou de uma transação implícita, se IMPLICIT_TRANSACTIONS estiver definido como ON, o nível de isolamento READ COMMITTED não terá suporte.</span><span class="sxs-lookup"><span data-stu-id="a4533-120">When accessing a memory-optimized table from an explicit transaction that was started with BEGIN TRANSACTION, or from an implicit transaction, if IMPLICIT_TRANSACTIONS is set to ON, the READ COMMITTED isolation level is not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a4533-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a4533-121">User Action</span></span>  
 <span data-ttu-id="a4533-122">Ao acessar uma tabela com otimização de memória de uma transação READ COMMITTED explícita ou implícita, use SNAPSHOT para acessar a tabela.</span><span class="sxs-lookup"><span data-stu-id="a4533-122">When accessing a memory-optimized table from an explicit or implicit READ COMMITTED transaction, use SNAPSHOT to access the table.</span></span> <span data-ttu-id="a4533-123">Isso pode ser feito usando a dica de tabela com (instantâneo) (para obter mais informações, consulte [diretrizes para níveis de isolamento de transação com tabelas com otimização de memória](../in-memory-oltp/memory-optimized-tables.md)) ou definindo a opção de banco de dados MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT como on (para obter mais informações, consulte [Opções ALTER database SET &#40;&#41;Transact-SQL ](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span><span class="sxs-lookup"><span data-stu-id="a4533-123">This can be achieved by using the table hint WITH (SNAPSHOT) (for more information, see [Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md)) or by setting the database option MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT to ON (for more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4533-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a4533-124">See Also</span></span>  
 [<span data-ttu-id="a4533-125">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="a4533-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
