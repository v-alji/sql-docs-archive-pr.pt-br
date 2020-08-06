---
title: Solucionando problemas comuns de desempenho com índices de hash com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 1954a997-7585-4713-81fd-76d429b8d095
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cef98571edd7736bc45ba8caf17451007a74cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678951"
---
# <a name="troubleshooting-common-performance-problems-with-memory-optimized-hash-indexes"></a><span data-ttu-id="91787-102">Solucionando problemas comuns de desempenho com índices de hash com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="91787-102">Troubleshooting Common Performance Problems with Memory-Optimized Hash Indexes</span></span>
  <span data-ttu-id="91787-103">Este tópico abordará a solução de problemas e como contornar problemas comuns com índices de hash.</span><span class="sxs-lookup"><span data-stu-id="91787-103">This topic will focus on troubleshooting and working around common issues with hash indexes.</span></span>  
  
## <a name="search-requires-a-subset-of-hash-index-key-columns"></a><span data-ttu-id="91787-104">A busca requer um subconjunto de colunas de chave de índice de hash</span><span class="sxs-lookup"><span data-stu-id="91787-104">Search Requires a Subset of Hash Index Key Columns</span></span>  
 <span data-ttu-id="91787-105">**Problema:** Os índices de hash exigem valores para todas as colunas de chave de índice para computar o valor de hash e localizar as linhas correspondentes na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="91787-105">**Issue:** Hash indexes require values for all index key columns in order to compute the hash value, and locate the corresponding rows in the hash table.</span></span> <span data-ttu-id="91787-106">Em virtude disso, se uma consulta inclui predicados de igualdade para apenas um subconjunto das chaves do índice na cláusula WHERE, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não pode usar uma busca de índice para localizar as linhas que correspondem aos predicados na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="91787-106">Therefore, if a query includes equality predicates for only a subset of the index keys in the WHERE clause, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot use an index seek to locate the rows corresponding to the predicates in the WHERE clause.</span></span>  
  
 <span data-ttu-id="91787-107">Em contraste, índices ordenados, como os índices não clusterizados baseados em disco e os índices não clusterizados com otimização de memória, dão suporte à busca de índice em um subconjunto das colunas de chave de índice, desde que elas sejam as colunas principais do índice.</span><span class="sxs-lookup"><span data-stu-id="91787-107">In contrast, ordered indexes like the disk-based nonclustered indexes and the memory-optimized nonclustered indexes support index seek on a subset of the index key columns, as long as they are the leading columns in the index.</span></span>  
  
 <span data-ttu-id="91787-108">**Sintoma:** Isso resulta em uma degradação do desempenho, pois [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] precisa executar verificações de tabela completas em vez de uma busca de índice, que normalmente é uma operação mais rápida.</span><span class="sxs-lookup"><span data-stu-id="91787-108">**Symptom:** This results in a performance degradation, as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] needs to execute full table scans rather than an index seek, which is typically a faster operation.</span></span>  
  
 <span data-ttu-id="91787-109">**Como solucionar problemas:** Além da degradação do desempenho, a inspeção dos planos de consulta mostrará uma verificação em vez de uma busca de índice.</span><span class="sxs-lookup"><span data-stu-id="91787-109">**How to troubleshoot:** Besides the performance degradation, inspection of the query plans will show a scan instead of an index seek.</span></span> <span data-ttu-id="91787-110">Se a consulta for bem simples, a inspeção do texto da consulta e da definição de índice também mostrará se a busca requer um subconjunto das colunas de chave de índice.</span><span class="sxs-lookup"><span data-stu-id="91787-110">If the query is fairly simple, inspection of the query text and index definition will also show whether the search requires a subset of the index key columns.</span></span>  
  
 <span data-ttu-id="91787-111">Considere a seguinte tabela e consulta:</span><span class="sxs-lookup"><span data-stu-id="91787-111">Consider the following table and query:</span></span>  
  
```sql  
CREATE TABLE [dbo].[od]  
(  
     o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
     CONSTRAINT PK_od PRIMARY KEY NONCLUSTERED HASH (o_id, od_id) WITH (BUCKET_COUNT = 10000)  
)  
WITH (MEMORY_OPTIMIZED = ON)  
  
 SELECT p_id  
 FROM dbo.od  
 WHERE o_id=1  
```  
  
 <span data-ttu-id="91787-112">A tabela tem um índice de hash nas duas colunas (o_id, od_id), enquanto a consulta tem um predicado de igualdade (o_id).</span><span class="sxs-lookup"><span data-stu-id="91787-112">The table has a hash index on the two columns (o_id, od_id), while the query has an equality predicate on (o_id).</span></span> <span data-ttu-id="91787-113">Como a consulta tem predicados de igualdade em apenas um subconjunto das colunas de chave de índice, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não pode executar uma operação de busca de índice usando PK_od; em vez disso, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] precisa reverter para uma verificação de índice completo.</span><span class="sxs-lookup"><span data-stu-id="91787-113">As the query has equality predicates on only a subset of the index key columns, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot perform an index seek operation using PK_od; instead, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has to revert to a full index scan.</span></span>  
  
 <span data-ttu-id="91787-114">**Soluções alternativas:** Há uma série de possíveis soluções alternativas.</span><span class="sxs-lookup"><span data-stu-id="91787-114">**Workarounds:** There are a number of possible workarounds.</span></span> <span data-ttu-id="91787-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="91787-115">For example:</span></span>  
  
-   <span data-ttu-id="91787-116">Recrie o índice como o tipo não clusterizado em vez do hash não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="91787-116">Recreate the index as type nonclustered instead of nonclustered hash.</span></span> <span data-ttu-id="91787-117">O índice não clusterizado com otimização de memória é ordenado e, portanto, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pode executar uma busca de índice nas colunas principais de chave de índice.</span><span class="sxs-lookup"><span data-stu-id="91787-117">The memory-optimized nonclustered index is ordered, and thus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can perform an index seek on the leading index key columns.</span></span> <span data-ttu-id="91787-118">A definição de chave primária resultante para o exemplo seria `constraint PK_od primary key nonclustered`.</span><span class="sxs-lookup"><span data-stu-id="91787-118">The resulting primary key definition for the example would be `constraint PK_od primary key nonclustered`.</span></span>  
  
-   <span data-ttu-id="91787-119">Alterar a chave de índice atual para corresponder às colunas na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="91787-119">Change the current index key to match the columns in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="91787-120">Adicionar um novo índice de hash que corresponde às colunas na cláusula WHERE da consulta.</span><span class="sxs-lookup"><span data-stu-id="91787-120">Add a new hash index that matches with the columns in the WHERE clause of the query.</span></span> <span data-ttu-id="91787-121">No exemplo, a definição da tabela resultante teria esta aparência:</span><span class="sxs-lookup"><span data-stu-id="91787-121">In the example, the resulting table definition would look at follows:</span></span>  
  
    ```sql  
    CREATE TABLE dbo.od  
     ( o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
  
     CONSTRAINT PK_od PRIMARY KEY   
     NONCLUSTERED HASH (o_id,od_id) WITH (BUCKET_COUNT=10000),  
  
     INDEX ix_o_id NONCLUSTERED HASH (o_id) WITH (BUCKET_COUNT=10000)  
  
     ) WITH (MEMORY_OPTIMIZED=ON)  
    ```  
  
 <span data-ttu-id="91787-122">Observe que um índice de hash com otimização de memória não apresenta o desempenho ideal quando há muitas linhas duplicadas para um valor de chave de índice específico: no exemplo, se o número de valores exclusivos para a coluna o_id fosse bem menor do que o número de linhas na tabela, o ideal não seria adicionar um índice (o_id); a melhor solução seria alterar o tipo de índice PK_od de hash para não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="91787-122">Note that a memory-optimized hash index does not perform optimally if there are a lot of duplicate rows for a given index key value: in the example, if the number of unique values for the column o_id is much smaller than the number of rows in the table, it would not be optimal to add an index on (o_id); instead, changing the type of the index PK_od from hash to nonclustered would be the better solution.</span></span> <span data-ttu-id="91787-123">Para obter mais informações, consulte [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="91787-123">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91787-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91787-124">See Also</span></span>  
 [<span data-ttu-id="91787-125">Índices em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="91787-125">Indexes on Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
