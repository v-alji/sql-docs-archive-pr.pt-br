---
title: Tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 14dddf81-b502-49dc-a6b6-d18b1ae32d2b
author: rothja
ms.author: jroth
ms.openlocfilehash: 73430505e55230daf31c492d882eadeb6d35d29f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685145"
---
# <a name="memory-optimized-tables"></a><span data-ttu-id="66a96-102">Tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="66a96-102">Memory-Optimized Tables</span></span>
  <span data-ttu-id="66a96-103">O OLTP na memória do[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ajuda a aumentar o desempenho de aplicativos OLTP por meio de acesso a dados com otimização de memória eficiente, compilação nativa de lógica de negócios e algoritmos livres de bloqueio e trava.</span><span class="sxs-lookup"><span data-stu-id="66a96-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] In-Memory OLTP helps improve performance of OLTP applications through efficient, memory-optimized data access, native compilation of business logic, and lock- and latch free algorithms.</span></span> <span data-ttu-id="66a96-104">O recurso OLTP na memória inclui tipos de tabela e tabelas com otimização de memória, bem como compilação nativa de procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)] para acesso eficiente a essas tabelas.</span><span class="sxs-lookup"><span data-stu-id="66a96-104">The In-Memory OLTP feature includes memory-optimized tables and table types, as well as native compilation of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures for efficient access to these tables.</span></span>  
  
 <span data-ttu-id="66a96-105">Para obter mais informações sobre tabelas com otimização de memória, consulte:</span><span class="sxs-lookup"><span data-stu-id="66a96-105">For more information about memory-optimized tables, see:</span></span>  
  
-   [<span data-ttu-id="66a96-106">Introdução às tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="66a96-106">Introduction to Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
     <span data-ttu-id="66a96-107">Detalha o que são tabelas com otimização de memória e fornece informações sobre durabilidade de dados, acesso a dados em tabelas com otimização de memória e desempenho e escalabilidade.</span><span class="sxs-lookup"><span data-stu-id="66a96-107">Details what memory-optimized tables are and provides information about data durability, accessing data in memory-optimized tables, and performance and scalability.</span></span>  
  
-   [<span data-ttu-id="66a96-108">Compilação nativa de tabelas e procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="66a96-108">Native Compilation of Tables and Stored Procedures</span></span>](../in-memory-oltp/natively-compiled-stored-procedures.md)  
  
     <span data-ttu-id="66a96-109">Detalha como tabelas com otimização de memória e procedimentos armazenados compilados nativamente são compilados para DLLs, além de fornecer considerações relacionadas sobre segurança.</span><span class="sxs-lookup"><span data-stu-id="66a96-109">Details how memory-optimized tables and natively compiled stored procedures are compiled into DLLs, and provides related security considerations.</span></span>  
  
-   [<span data-ttu-id="66a96-110">Alterando tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="66a96-110">Altering Memory-Optimized Tables</span></span>](altering-memory-optimized-tables.md)  
  
     <span data-ttu-id="66a96-111">Diretrizes para atualizar tabelas com otimização de memória (incluindo alterar colunas de tabela, índices e bucket_count).</span><span class="sxs-lookup"><span data-stu-id="66a96-111">Guidelines for updating memory-optimized tables (including changing table columns, indexes, and bucket_count).</span></span>  
  
-   [<span data-ttu-id="66a96-112">Compreendendo transações em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="66a96-112">Understanding Transactions on Memory-Optimized Tables</span></span>](../../database-engine/understanding-transactions-on-memory-optimized-tables.md)  
  
     <span data-ttu-id="66a96-113">Esta seção fornece vários tópicos relacionados a realizar transações em tabelas com otimização de memória, incluindo níveis de isolamento de transação e transações intercontêineres.</span><span class="sxs-lookup"><span data-stu-id="66a96-113">This section provides several topics related to performing transactions on memory-optimized tables including transaction isolation levels, and cross-container transactions.</span></span>  
  
-   [<span data-ttu-id="66a96-114">Padrão de aplicativo para particionamento de tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="66a96-114">Application Pattern for Partitioning Memory-Optimized Tables</span></span>](application-pattern-for-partitioning-memory-optimized-tables.md)  
  
     <span data-ttu-id="66a96-115">Amostra de código detalhada que mostra como emular tabelas particionadas ao usar tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="66a96-115">Detailed code sample that shows how to emulate partitioned tables when using memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="66a96-116">Estatísticas para tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="66a96-116">Statistics for Memory-Optimized Tables</span></span>](statistics-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="66a96-117">Detalha como as estatísticas são compiladas para tabelas com otimização de memória e como manter e atualizar estatísticas para tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="66a96-117">Details how statistics are compiled for memory-optimized tables and how to maintain and manually update statistics for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="66a96-118">Páginas de código de ordenações</span><span class="sxs-lookup"><span data-stu-id="66a96-118">Collations and Code Pages</span></span>](../../database-engine/collations-and-code-pages.md)  
  
     <span data-ttu-id="66a96-119">Detalha as restrições sobre ordenações com suporte e páginas de código para tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="66a96-119">Details the restrictions on supported collations and code pages for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="66a96-120">Tamanho da tabela e da linha em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="66a96-120">Table and Row Size in Memory-Optimized Tables</span></span>](table-and-row-size-in-memory-optimized-tables.md)  
  
     <span data-ttu-id="66a96-121">Detalha o limite de 8060 bytes em linhas de tabela com otimização de memória e fornece um exemplo para calcular tamanhos de tabela e linha.</span><span class="sxs-lookup"><span data-stu-id="66a96-121">Details the 8060 byte limit on memory-optimized table rows, and provides an example for calculating table and row sizes.</span></span>  
  
-   [<span data-ttu-id="66a96-122">Um guia para processamento de consulta de tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="66a96-122">A Guide to Query Processing for Memory-Optimized Tables</span></span>](a-guide-to-query-processing-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="66a96-123">Fornece uma visão geral do processamento de consulta para tabelas com otimização de memória e procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="66a96-123">Provides an overview of query processing for both memory-optimized tables, and natively compiled stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a96-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66a96-124">See Also</span></span>  
 [<span data-ttu-id="66a96-125">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="66a96-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
