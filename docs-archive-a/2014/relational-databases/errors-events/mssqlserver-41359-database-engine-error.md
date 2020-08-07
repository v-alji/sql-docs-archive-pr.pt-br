---
title: MSSQLSERVER_41359 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41359 (Database Engine error)
ms.assetid: 02b717c7-9170-4676-b0f6-4dec9eb5b5d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cf45a117dcda0827672c6072c603a1fc0866a33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582454"
---
# <a name="mssqlserver_41359"></a><span data-ttu-id="6abe8-102">MSSQLSERVER_41359</span><span class="sxs-lookup"><span data-stu-id="6abe8-102">MSSQLSERVER_41359</span></span>
    
## <a name="details"></a><span data-ttu-id="6abe8-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="6abe8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6abe8-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="6abe8-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="6abe8-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="6abe8-105">Event ID</span></span>|<span data-ttu-id="6abe8-106">41359</span><span class="sxs-lookup"><span data-stu-id="6abe8-106">41359</span></span>|  
|<span data-ttu-id="6abe8-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="6abe8-107">Event Source</span></span>|<span data-ttu-id="6abe8-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6abe8-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6abe8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="6abe8-109">Component</span></span>|<span data-ttu-id="6abe8-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6abe8-110">SQLEngine</span></span>|  
|<span data-ttu-id="6abe8-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="6abe8-111">Symbolic Name</span></span>|<span data-ttu-id="6abe8-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="6abe8-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="6abe8-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="6abe8-113">Message Text</span></span>|<span data-ttu-id="6abe8-114">Uma consulta que acessa as tabelas com otimização de memória usando o nível de isolamento READ COMMITTED não pode acessar as tabelas baseadas em disco quando a opção READ_COMMITTED_SNAPSHOT do banco de dados é definida como ON.</span><span class="sxs-lookup"><span data-stu-id="6abe8-114">A query that accesses memory optimized tables using the READ COMMITTED isolation level, cannot access disk based tables when the database option READ_COMMITTED_SNAPSHOT is set to ON.</span></span> <span data-ttu-id="6abe8-115">Forneça um nível de isolamento com suporte para a tabela com otimização de memória usando uma dica de tabela, como WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="6abe8-115">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6abe8-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="6abe8-116">Explanation</span></span>  
 <span data-ttu-id="6abe8-117">O banco de dados com READ_COMMITTED_SNAPSHOT=ON não oferece suporte a transações que acessam tabelas com otimização de memória e tabelas baseadas em disco.</span><span class="sxs-lookup"><span data-stu-id="6abe8-117">The database with READ_COMMITTED_SNAPSHOT=ON does not support the transactions that access both memory-optimized tables and disk based tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6abe8-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="6abe8-118">User Action</span></span>  
 <span data-ttu-id="6abe8-119">Defina READ_COMMITTED_SNAPSHOT como OFF ou forneça um nível de isolamento com suporte para a tabela com otimização de memória usando uma dica no nível de tabela, como WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="6abe8-119">Set READ_COMMITTED_SNAPSHOT to OFF or supply a supported isolation level for the memory-optimized table using a table-level hint, such as WITH (SNAPSHOT).</span></span> <span data-ttu-id="6abe8-120">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="6abe8-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6abe8-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6abe8-121">See Also</span></span>  
 [<span data-ttu-id="6abe8-122">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="6abe8-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
