---
title: Gerenciando memória para OLTP na memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d82f21fa-6be1-4723-a72e-f2526fafd1b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90f9b638697d59a0a573a9a31c0a5faade23e870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684316"
---
# <a name="managing-memory-for-in-memory-oltp"></a><span data-ttu-id="51a04-102">Gerenciando memória para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="51a04-102">Managing Memory for In-Memory OLTP</span></span>
  <span data-ttu-id="51a04-103">As tabelas com otimização de memória requerem a existência de memória suficiente para manter todas as linhas e índices na memória.</span><span class="sxs-lookup"><span data-stu-id="51a04-103">Memory-optimized tables require that sufficient memory exist to keep all of the rows and indexes in memory.</span></span> <span data-ttu-id="51a04-104">Como a memória é um recurso finito, é importante compreender e gerenciar o uso de memória no sistema.</span><span class="sxs-lookup"><span data-stu-id="51a04-104">Because memory is a finite resource, it is important that you understand and manage memory usage on your system.</span></span> <span data-ttu-id="51a04-105">Os tópicos nessa seção abordam os cenários comuns de uso e gerenciamento de memória.</span><span class="sxs-lookup"><span data-stu-id="51a04-105">The topics in this section cover common memory use and management scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51a04-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="51a04-106">In this section</span></span>  
  
|<span data-ttu-id="51a04-107">Seção</span><span class="sxs-lookup"><span data-stu-id="51a04-107">Section</span></span>|<span data-ttu-id="51a04-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="51a04-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51a04-109">Estimar requisitos de memória para tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="51a04-109">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)|<span data-ttu-id="51a04-110">Estimar as necessidades de memória de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="51a04-110">Estimate a table's memory needs.</span></span>|  
|[<span data-ttu-id="51a04-111">Associar um banco de dados com tabelas com otimização de memória a um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="51a04-111">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)|<span data-ttu-id="51a04-112">Passo a passo para associar um banco de dados a um pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="51a04-112">Step by step walkthrough to bind a database with a resource pool.</span></span>|  
|[<span data-ttu-id="51a04-113">Monitorar e solucionar problemas de uso da memória</span><span class="sxs-lookup"><span data-stu-id="51a04-113">Monitor and Troubleshoot Memory Usage</span></span>](../relational-databases/in-memory-oltp/monitor-and-troubleshoot-memory-usage.md)|<span data-ttu-id="51a04-114">Ferramentas que você pode usar para monitorar o uso da memória.</span><span class="sxs-lookup"><span data-stu-id="51a04-114">Tools you can use to monitor your memory usage.</span></span> <span data-ttu-id="51a04-115">Também abrange a solução de problemas se o uso de memória ficar muito alto.</span><span class="sxs-lookup"><span data-stu-id="51a04-115">Also covers troubleshooting if memory usage gets too high.</span></span>|  
|[<span data-ttu-id="51a04-116">Resolver problemas de memória insuficiente</span><span class="sxs-lookup"><span data-stu-id="51a04-116">Resolve Out Of Memory Issues</span></span>](../relational-databases/in-memory-oltp/resolve-out-of-memory-issues.md)|<span data-ttu-id="51a04-117">Etapas para recuperar-se de uma situação de OOM (memória insuficiente).</span><span class="sxs-lookup"><span data-stu-id="51a04-117">Steps to recover from an OOM (Out of Memory) situation.</span></span>|  
|[<span data-ttu-id="51a04-118">Restaurar um banco de dados e associá-lo a um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="51a04-118">Restore a Database and Bind it to a Resource Pool</span></span>](../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md)|<span data-ttu-id="51a04-119">Etapas para restaurar um banco de dados do [!INCLUDE[hek_2](../includes/hek-2-md.md)] e associá-lo a um pool de recursos nomeado.</span><span class="sxs-lookup"><span data-stu-id="51a04-119">Steps to restore an [!INCLUDE[hek_2](../includes/hek-2-md.md)] database and bind it to a named resource pool.</span></span>|  
|[<span data-ttu-id="51a04-120">Coleta de lixo de OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="51a04-120">In-Memory OLTP Garbage Collection</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-garbage-collection.md)|<span data-ttu-id="51a04-121">Saiba como a coleta de lixo opera em linhas excluídas.</span><span class="sxs-lookup"><span data-stu-id="51a04-121">Understand how garbage collection operates on deleted rows.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51a04-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51a04-122">See Also</span></span>  
 [<span data-ttu-id="51a04-123">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="51a04-123">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
