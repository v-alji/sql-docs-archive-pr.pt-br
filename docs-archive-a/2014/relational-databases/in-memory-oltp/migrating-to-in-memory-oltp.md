---
title: Migrando para o OLTP in-memory | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 405cdac5-a0d4-47a4-9180-82876b773b82
author: rothja
ms.author: jroth
ms.openlocfilehash: ed764ce52d41d76667213b846cec51b26f634a27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685692"
---
# <a name="migrating-to-in-memory-oltp"></a><span data-ttu-id="21f57-102">Migrando para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="21f57-102">Migrating to In-Memory OLTP</span></span>
  <span data-ttu-id="21f57-103">Esta seção discute como migrar objetos do banco de dados para usar o OLTP na memória.</span><span class="sxs-lookup"><span data-stu-id="21f57-103">This section discusses how to migrate database objects to use In-Memory OLTP.</span></span>  
  
-   [<span data-ttu-id="21f57-104">Determinando se uma tabela ou um procedimento armazenado deve ser movido para OLTP in-memory</span><span class="sxs-lookup"><span data-stu-id="21f57-104">Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP</span></span>](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)  
  
-   [<span data-ttu-id="21f57-105">Orientador de otimização da memória</span><span class="sxs-lookup"><span data-stu-id="21f57-105">Memory Optimization Advisor</span></span>](memory-optimization-advisor.md)  
  
-   [<span data-ttu-id="21f57-106">Orientador de compilação nativa</span><span class="sxs-lookup"><span data-stu-id="21f57-106">Native Compilation Advisor</span></span>](native-compilation-advisor.md)  
  
-   [<span data-ttu-id="21f57-107">Construções do Transact-SQL sem suporte pelo OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="21f57-107">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
-   [<span data-ttu-id="21f57-108">Implementando Colunas LOB em uma tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="21f57-108">Implementing LOB Columns in a Memory-Optimized Table</span></span>](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="21f57-109">Implementando SQL_VARIANT em uma tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="21f57-109">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="21f57-110">Problemas de migração para procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="21f57-110">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="21f57-111">Criando colunas computadas</span><span class="sxs-lookup"><span data-stu-id="21f57-111">Migrating Computed Columns</span></span>](migrating-computed-columns.md)  
  
-   [<span data-ttu-id="21f57-112">Migrando gatilhos</span><span class="sxs-lookup"><span data-stu-id="21f57-112">Migrating Triggers</span></span>](migrating-triggers.md)  
  
-   [<span data-ttu-id="21f57-113">Consultas entre bancos de dados</span><span class="sxs-lookup"><span data-stu-id="21f57-113">Cross-Database Queries</span></span>](cross-database-queries.md)  
  
-   [<span data-ttu-id="21f57-114">Verificação de migração e restrições Chave Estrangeira</span><span class="sxs-lookup"><span data-stu-id="21f57-114">Migrating Check and Foreign Key Constraints</span></span>](../../database-engine/migrating-check-and-foreign-key-constraints.md)  
  
-   [<span data-ttu-id="21f57-115">Implementando IDENTITY em uma tabela otimizada em memória</span><span class="sxs-lookup"><span data-stu-id="21f57-115">Implementing IDENTITY in a Memory-Optimized Table</span></span>](implementing-identity-in-a-memory-optimized-table.md)  
  
 <span data-ttu-id="21f57-116">Para obter informações sobre as metodologias de migração, confira [In-Memory OLTP – Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx)(OLTP in-memory – Padrões comuns de carga de trabalho e considerações de migração).</span><span class="sxs-lookup"><span data-stu-id="21f57-116">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f57-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="21f57-117">See Also</span></span>  
 <span data-ttu-id="21f57-118">[OLTP in-memory &#40;Otimização na memória&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="21f57-118">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 [<span data-ttu-id="21f57-119">Estimar requisitos de memória para tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="21f57-119">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
