---
title: Suporte ao Transact-SQL para OLTP in-memory | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b1cc7c30-1747-4c21-88ac-e95a5e58baac
author: rothja
ms.author: jroth
ms.openlocfilehash: bf3708a258e3bb97231e45b10bea2c59351a06a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685134"
---
# <a name="transact-sql-support-for-in-memory-oltp"></a><span data-ttu-id="2b603-102">Suporte ao Transact-SQL para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="2b603-102">Transact-SQL Support for In-Memory OLTP</span></span>
  <span data-ttu-id="2b603-103">Você pode acessar tabelas com otimização de memória usando qualquer consulta de Transact-SQL ou operação DML (SELEÇÃO, INSERÇÃO, ATUALIZAÇÃO ou EXCLUSÃO), lotes ad hoc e os módulos SQL, como procedimentos armazenados, funções com valor de tabela, funções escalares, gatilhos e exibições.</span><span class="sxs-lookup"><span data-stu-id="2b603-103">You can access memory-optimized tables using any Transact-SQL query or DML statement (SELECT, INSERT, UPDATE, or DELETE), ad hoc statement, and SQL module such as stored procedures, table-value functions, scalar functions, triggers, and views.</span></span> <span data-ttu-id="2b603-104">Para obter mais informações, consulte [acessando tabelas com otimização de memória usando Transact-SQL interpretado](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2b603-104">For more information see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span>  
  
 <span data-ttu-id="2b603-105">Os procedimentos armazenados que só fazem referência a tabelas com otimização de memória podem ser compilados nativamente em código de computador e fornecem tipicamente melhorias de desempenho sobre procedimentos armazenados interpretados (baseados em disco).</span><span class="sxs-lookup"><span data-stu-id="2b603-105">Stored procedures that only reference memory-optimized tables can be natively compiled into machine code and typically provide significant performance gains over interpreted (disk-based) stored procedures.</span></span> <span data-ttu-id="2b603-106">Para acesso otimizado a tabelas com otimização de memória, use procedimentos armazenados compilados.</span><span class="sxs-lookup"><span data-stu-id="2b603-106">For optimized access to memory-optimized tables use natively compiled stored procedures.</span></span> <span data-ttu-id="2b603-107">Para saber mais, veja [Procedimentos armazenados compilados nativamente](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2b603-107">For more information, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="2b603-108">Ao criar e modificar objetos de banco de dados (instruções DDL), as instruções a seguir são modificadas:</span><span class="sxs-lookup"><span data-stu-id="2b603-108">When creating and modifying database objects (DDL statements), the following statements have been modified:</span></span>  
  
-   <span data-ttu-id="2b603-109">[Opções de arquivo e grupo de arquivos ALTER DATABASE &#40;&#41;Transact-SQL](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (consulte `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="2b603-109">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="2b603-110">[Criar &#40;de banco de dados SQL Server&#41;Transact-SQL](/sql/t-sql/statements/create-database-sql-server-transact-sql) (consulte `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="2b603-110">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="2b603-111">[Criar procedimento &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-procedure-transact-sql) (consulte `NATIVE_COMPILATION` , `SCHEMABINDING` , `EXECUTE AS` e `BEGIN ATOMIC` )</span><span class="sxs-lookup"><span data-stu-id="2b603-111">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) (see `NATIVE_COMPILATION`, `SCHEMABINDING`, `EXECUTE AS`, and `BEGIN ATOMIC`)</span></span>  
  
-   <span data-ttu-id="2b603-112">[CREATE TABLE &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-table-transact-sql) (consulte `MEMORY_OPTIMIZED` ,,, `DURABILITY` `BUCKET_COUNT` `INDEX` e `HASH` )</span><span class="sxs-lookup"><span data-stu-id="2b603-112">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) (see `MEMORY_OPTIMIZED`, `DURABILITY`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="2b603-113">[Criar tipo &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-type-transact-sql) (consulte `MEMORY_OPTIMIZED` , `BUCKET_COUNT` , `INDEX` e `HASH` )</span><span class="sxs-lookup"><span data-stu-id="2b603-113">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) (see `MEMORY_OPTIMIZED`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="2b603-114">[Declarar @local_variable &#40;&#41;TRANSACT-SQL](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (consulte `NULL`  |  `NOT NULL` )</span><span class="sxs-lookup"><span data-stu-id="2b603-114">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (see `NULL` | `NOT NULL`)</span></span>  
  
 <span data-ttu-id="2b603-115">As tabelas com otimização de memória suportam restrições `PRIMARY KEY` e `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="2b603-115">Memory-optimized tables support `PRIMARY KEY` and `NOT NULL` constraints.</span></span> <span data-ttu-id="2b603-116">Para obter informações sobre como implementar restrições sem suporte, consulte [migrando restrições CHECK e Foreign Key](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="2b603-116">For information on implementing unsupported constraints, see [Migrating Check and Foreign Key Constraints](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="2b603-117">Para obter informações sobre os recursos sem suporte, veja [Construções do Transact-SQL sem suporte pelo OLTP in-memory](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="2b603-117">For information on unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b603-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2b603-118">In This Section</span></span>  
  
-   [<span data-ttu-id="2b603-119">Tipos de dados com suporte</span><span class="sxs-lookup"><span data-stu-id="2b603-119">Supported Data Types</span></span>](supported-data-types-for-in-memory-oltp.md)  
  
-   [<span data-ttu-id="2b603-120">Acessando tabelas com otimização de memória usando Transact-SQL interpretado</span><span class="sxs-lookup"><span data-stu-id="2b603-120">Accessing Memory-Optimized Tables Using Interpreted Transact-SQL</span></span>](accessing-memory-optimized-tables-using-interpreted-transact-sql.md)  
  
-   [<span data-ttu-id="2b603-121">Exibições do sistema, procedimentos armazenados, tipos de espera e DMVs para OLTP in-memory</span><span class="sxs-lookup"><span data-stu-id="2b603-121">System Views, Stored Procedures, DMVs and Wait Types for In-Memory OLTP</span></span>](../../database-engine/system-views-stored-procedures-dmvs-and-wait-types-for-in-memory-oltp.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b603-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b603-122">See Also</span></span>  
 <span data-ttu-id="2b603-123">[OLTP in-memory &#40;Otimização na memória&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="2b603-123">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="2b603-124">[Problemas de migração para procedimentos armazenados compilados nativamente](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="2b603-124">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="2b603-125">[Recursos de SQL Server com suporte](unsupported-sql-server-features-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="2b603-125">[Supported SQL Server Features](unsupported-sql-server-features-for-in-memory-oltp.md) </span></span>  
 [<span data-ttu-id="2b603-126">Procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="2b603-126">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
