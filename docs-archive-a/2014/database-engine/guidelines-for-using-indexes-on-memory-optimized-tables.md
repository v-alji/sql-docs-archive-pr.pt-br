---
title: Diretrizes para usar índices em tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- hash indexes
ms.assetid: 16ef63a4-367a-46ac-917d-9eebc81ab29b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f00d643088634c918eb626917eae64a001ce3678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681074"
---
# <a name="guidelines-for-using-indexes-on-memory-optimized-tables"></a><span data-ttu-id="54764-102">Diretrizes para usar índices em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="54764-102">Guidelines for Using Indexes on Memory-Optimized Tables</span></span>
  <span data-ttu-id="54764-103">Os índices são usados para acessar dados com eficiência nas tabelas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54764-103">Indexes are used for efficiently accessing data in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="54764-104">Especificar os índices certos pode melhorar significativamente o desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="54764-104">Specifying the right indexes can dramatically improve query performance.</span></span> <span data-ttu-id="54764-105">Considere, por exemplo, a consulta:</span><span class="sxs-lookup"><span data-stu-id="54764-105">Consider, for example, the query:</span></span>  
  
```sql  
SELECT c1, c2 FROM t WHERE c1 = 1;  
```  
  
 <span data-ttu-id="54764-106">Se não houver nenhum índice na coluna c1, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] precisará verificar a tabela t inteira e filtrar por linhas que atendam à condição c1=1.</span><span class="sxs-lookup"><span data-stu-id="54764-106">If there is no index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will need to scan the entire table t, and then filter on the rows that satisfy the condition c1=1.</span></span> <span data-ttu-id="54764-107">No entanto, se t tiver um índice na coluna c1, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] poderá buscar diretamente o valor 1 e recuperar as linhas.</span><span class="sxs-lookup"><span data-stu-id="54764-107">However, if t has an index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can seek directly on the value 1 and retrieve the rows.</span></span>  
  
 <span data-ttu-id="54764-108">Ao procurar por registros com um valor específico, ou intervalo de valores, para uma ou mais colunas na tabela, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pode usar um índice nessas colunas para localizar rapidamente os registros correspondentes.</span><span class="sxs-lookup"><span data-stu-id="54764-108">When searching for records that have a specific value, or range of values, for one or more columns in the table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can use an index on those columns to quickly locate the corresponding records.</span></span> <span data-ttu-id="54764-109">As tabelas com base em disco e com otimização de memória se beneficiam dos índices.</span><span class="sxs-lookup"><span data-stu-id="54764-109">Both disk-based and memory-optimized tables benefit from indexes.</span></span> <span data-ttu-id="54764-110">No entanto, há determinadas diferenças entre as estruturas de índice que precisam ser consideradas durante o uso de tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="54764-110">There are, however, certain differences between index structures that need to be considered when using memory-optimized tables.</span></span> <span data-ttu-id="54764-111">(Os índices em tabelas com otimização de memória são chamados de índices com otimização de memória.) Algumas das principais diferenças são:</span><span class="sxs-lookup"><span data-stu-id="54764-111">(Indexes on memory-optimized tables are referred to as memory-optimized indexes.) Some of the key differences are:</span></span>  
  
-   <span data-ttu-id="54764-112">Os índices com otimização de memória devem ser criados com [CREATE TABLE &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54764-112">Memory-optimized indexes must be created with [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span> <span data-ttu-id="54764-113">Os índices baseados em disco podem ser criados com `CREATE TABLE` e `CREATE INDEX`.</span><span class="sxs-lookup"><span data-stu-id="54764-113">Disk-based indexes can be created with `CREATE TABLE` and `CREATE INDEX`.</span></span>  
  
-   <span data-ttu-id="54764-114">Os índices com otimização de memória existem apenas na memória.</span><span class="sxs-lookup"><span data-stu-id="54764-114">Memory-optimized indexes exist only in memory.</span></span> <span data-ttu-id="54764-115">As estruturas de índice não são persistentes no disco e as operações de índice não são registradas no log de transações.</span><span class="sxs-lookup"><span data-stu-id="54764-115">Index structures are not persisted to disk and index operations are not logged in the transaction log.</span></span> <span data-ttu-id="54764-116">A estrutura de índice é criada quando a tabela com otimização de memória é criada na memória, tanto durante a instrução CREATE TABLE quanto durante a inicialização do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="54764-116">The index structure is created when the memory-optimized table is created in memory, both during CREATE TABLE and during database startup.</span></span>  
  
-   <span data-ttu-id="54764-117">Os índices com otimização de memória são inerentemente cobertos.</span><span class="sxs-lookup"><span data-stu-id="54764-117">Memory-optimized indexes are inherently covering.</span></span> <span data-ttu-id="54764-118">A cobertura significa que, praticamente, todas as colunas são incluídas no índice e que as pesquisas de indicador não são necessárias em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="54764-118">Covering means that all columns are virtually included in the index and bookmark lookups are not needed for memory-optimized tables.</span></span> <span data-ttu-id="54764-119">Em vez de uma referência à chave primária, os índices com otimização de memória simplesmente contêm um ponteiro de memória para a linha real na estrutura de dados da tabela.</span><span class="sxs-lookup"><span data-stu-id="54764-119">Rather than a reference to the primary key, memory-optimized indexes simply contain a memory pointer to the actual row in the table data structure.</span></span>  
  
-   <span data-ttu-id="54764-120">A fragmentação e o fator de preenchimento não se aplicam aos índices com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="54764-120">Fragmentation and fillfactor do not apply to memory-optimized indexes.</span></span> <span data-ttu-id="54764-121">Em índices baseados em disco, a fragmentação se refere a páginas na árvore B sendo gravadas fora de ordem no disco.</span><span class="sxs-lookup"><span data-stu-id="54764-121">In disk-based indexes, fragmentation refers to pages in the B-tree being written to disk out-of-order.</span></span> <span data-ttu-id="54764-122">Os índices com otimização de memória não são gravados nem lidos no disco.</span><span class="sxs-lookup"><span data-stu-id="54764-122">Memory-optimized indexes are not written to or read from disk.</span></span> <span data-ttu-id="54764-123">O fator de preenchimento nos índices da árvore B baseados em disco se refere ao grau em que as estruturas de página física são preenchidas com dados reais.</span><span class="sxs-lookup"><span data-stu-id="54764-123">Fillfactor in disk-based B-tree indexes refers to the degree to which the physical page structures are filled with actual data.</span></span> <span data-ttu-id="54764-124">As estruturas de índice com otimização de memória não têm páginas de tamanho fixo.</span><span class="sxs-lookup"><span data-stu-id="54764-124">The memory-optimized index structures do not have fixed-size pages.</span></span>  
  
 <span data-ttu-id="54764-125">Há dois tipos de índices com otimização de memória:</span><span class="sxs-lookup"><span data-stu-id="54764-125">There are two types of memory-optimized indexes:</span></span>  
  
-   <span data-ttu-id="54764-126">Índices de hash não clusterizados, que são projetados para pesquisas de ponto.</span><span class="sxs-lookup"><span data-stu-id="54764-126">Nonclustered hash indexes, which are made for point lookups.</span></span> <span data-ttu-id="54764-127">Para obter mais informações sobre índices de hash, consulte [hash Indexes](hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="54764-127">For more information about hash indexes, see [Hash Indexes](hash-indexes.md).</span></span>  
  
-   <span data-ttu-id="54764-128">Índices não clusterizados, que são projetados para exames de intervalo e exames ordenados.</span><span class="sxs-lookup"><span data-stu-id="54764-128">Nonclustered indexes, which are made for range scans and ordered scans.</span></span>  
  
 <span data-ttu-id="54764-129">Com um índice de hash, os dados são acessados por meio de uma tabela de hash na memória.</span><span class="sxs-lookup"><span data-stu-id="54764-129">With a hash index, data is accessed through an in-memory hash table.</span></span> <span data-ttu-id="54764-130">Os índices de hash não possuem páginas e sempre são de um tamanho fixo.</span><span class="sxs-lookup"><span data-stu-id="54764-130">Hash indexes do not have pages and are always of a fixed size.</span></span> <span data-ttu-id="54764-131">No entanto, um índice de hash pode ter buckets de hash vazios, o que resulta em espaço desperdiçado limitado.</span><span class="sxs-lookup"><span data-stu-id="54764-131">However, a hash index can have empty hash buckets, which result in limited wasted space.</span></span> <span data-ttu-id="54764-132">Os valores retornados por uma consulta que usa um índice de hash não são classificados.</span><span class="sxs-lookup"><span data-stu-id="54764-132">The values returned from a query using a hash index are not sorted.</span></span> <span data-ttu-id="54764-133">Os índices de hash são otimizados para buscas de índice em predicados de igualdade e oferecem suporte a exames completos de índice.</span><span class="sxs-lookup"><span data-stu-id="54764-133">Hash indexes are optimized for index seeks on equality predicates and also support full index scans.</span></span>  
  
 <span data-ttu-id="54764-134">Os índices não clusterizados (não os índices de hash) oferecem suporte aos mesmos itens que os índices de hash, mais as operações de busca em predicados de desigualdade, como maior que ou menor que e ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="54764-134">Nonclustered indexes (not hash indexes) support everything that hash indexes supports plus seek operations on inequality predicates such as greater than or less than, as well as sort order.</span></span> <span data-ttu-id="54764-135">As linhas podem ser recuperadas de acordo com a ordem especificada com a criação do índice.</span><span class="sxs-lookup"><span data-stu-id="54764-135">Rows can be retrieved according to the order specified with index creation.</span></span> <span data-ttu-id="54764-136">Se a ordem de classificação do índice corresponder à ordem de classificação necessária para uma consulta específica, por exemplo, se a chave de índice corresponder à cláusula ORDER BY, não haverá necessidade de classificar as linhas como parte da execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="54764-136">If the sort order of the index matches the sort order required for a particular query, for example if the index key matches the ORDER BY clause, there is no need to sort the rows as part of query execution.</span></span> <span data-ttu-id="54764-137">Os índices não clusterizados com otimização de memória são unidirecionais; não oferecerão suporte a recuperação de linhas em uma ordem de classificação que for o oposto da ordem de classificação do índice.</span><span class="sxs-lookup"><span data-stu-id="54764-137">Memory-optimized nonclustered indexes are unidirectional; they do not support retrieving rows in a sort order that is the reverse of the sort order of the index.</span></span> <span data-ttu-id="54764-138">Por exemplo, para um índice especificado como (c1 ASC), não é possível digitalizar o índice em ordem inversa, como (c1 DESC).</span><span class="sxs-lookup"><span data-stu-id="54764-138">For example, for an index specified as (c1 ASC), it is not possible to scan the index in reverse order, as (c1 DESC).</span></span>  
  
 <span data-ttu-id="54764-139">Cada índice consome memória.</span><span class="sxs-lookup"><span data-stu-id="54764-139">Each index consumes memory.</span></span> <span data-ttu-id="54764-140">Os índices de hash consomem uma quantidade fixa de memória, que é uma função do número de buckets.</span><span class="sxs-lookup"><span data-stu-id="54764-140">Hash indexes consume a fixed amount of memory, which is a function of the bucket count.</span></span> <span data-ttu-id="54764-141">Para índices não clusterizados com otimização de memória, o consumo de memória é uma função da contagem de linhas e do tamanho das colunas de chave de índice, com alguma sobrecarga adicional, dependendo da carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54764-141">For nonclustered indexes, memory consumption is a function of the row count and the size of the index key columns, with some additional overhead depending on the workload.</span></span> <span data-ttu-id="54764-142">A memória para índices com otimização de memória é separada da memória usada para armazenar linhas em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="54764-142">Memory for memory-optimized indexes is in addition to and separate from the memory used to store rows in memory-optimized tables.</span></span>  
  
 <span data-ttu-id="54764-143">Valores de chave duplicados sempre compartilham o mesmo bucket de hash.</span><span class="sxs-lookup"><span data-stu-id="54764-143">Duplicate key values always share the same hash bucket.</span></span> <span data-ttu-id="54764-144">Se um índice de hash contiver muitos valores de chave duplicados, as longas sequências de hash resultantes prejudicarão o desempenho.</span><span class="sxs-lookup"><span data-stu-id="54764-144">If a hash index contains many duplicate key values, the resulting long hash chains will harm performance.</span></span> <span data-ttu-id="54764-145">Colisões de hash, que ocorrem em qualquer índice de hash, reduzirão ainda mais o desempenho nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="54764-145">Hash collisions, which occur in any hash index, will further reduce performance in this scenario.</span></span> <span data-ttu-id="54764-146">Por esse motivo, se o número de chaves de índice exclusivas for pelo menos 100 vezes menor do que a contagem de linhas, você poderá reduzir o risco de colisões de hash, tornando o número de buckets muito maior (pelo menos oito vezes a quantidade de chaves de índice exclusivas; consulte [determinando a contagem de buckets correta para](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) obter mais informações) ou elimine as colisões de hash por completo usando um índice não</span><span class="sxs-lookup"><span data-stu-id="54764-146">For that reason, if the number of unique index keys is at least 100 times smaller than the row count, you can reduce the risk of hash collisions by making the bucket count much larger (at least eight times the number of unique index keys; see [Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) for more information) or you can eliminate hash collisions entirely by using a nonclustered index.</span></span>  
  
## <a name="determining-which-indexes-to-use-for-a-memory-optimized-table"></a><span data-ttu-id="54764-147">Determinando os índices a serem usados em uma tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="54764-147">Determining Which Indexes to Use for a Memory-Optimized Table</span></span>  
 <span data-ttu-id="54764-148">Cada tabela com otimização de memória deve ter pelo menos um índice.</span><span class="sxs-lookup"><span data-stu-id="54764-148">Each memory-optimized table must have at least one index.</span></span> <span data-ttu-id="54764-149">Observe que cada restrição PRIMARY KEY cria um índice implicitamente.</span><span class="sxs-lookup"><span data-stu-id="54764-149">Note that each PRIMARY KEY constraint implicitly creates an index.</span></span> <span data-ttu-id="54764-150">Desse modo, se uma tabela tiver uma chave primária, ela terá um índice.</span><span class="sxs-lookup"><span data-stu-id="54764-150">Therefore, if a table has a primary key, it has an index.</span></span> <span data-ttu-id="54764-151">Uma chave primária é um requisito para uma tabela com otimização de memória durável.</span><span class="sxs-lookup"><span data-stu-id="54764-151">A primary key is a requirement for a durable memory-optimized table.</span></span>  
  
 <span data-ttu-id="54764-152">Ao consultar uma tabela com otimização de memória, os índices de hash são melhor executados quando a cláusula de predicado contém somente predicados de igualdade.</span><span class="sxs-lookup"><span data-stu-id="54764-152">When querying a memory-optimized table, hash indexes perform better when the predicate clause contains only equality predicates.</span></span> <span data-ttu-id="54764-153">O predicado deve incluir todas as colunas na chave de índice de hash.</span><span class="sxs-lookup"><span data-stu-id="54764-153">The predicate must include all columns in the hash index key.</span></span> <span data-ttu-id="54764-154">Um índice de hash reverterá para um exame de acordo com um predicado de desigualdade.</span><span class="sxs-lookup"><span data-stu-id="54764-154">A hash index will revert to a scan given an inequality predicate.</span></span>  
  
 <span data-ttu-id="54764-155">Uma coluna em uma tabela com otimização de memória pode fazer parte de um índice de hash e de um índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="54764-155">A column in a memory-optimized table can be part of both a hash index and a nonclustered index.</span></span>  
  
 <span data-ttu-id="54764-156">Ao consultar uma tabela com otimização de memória com predicados de desigualdade, os índices não clusterizados serão executados melhor do que os índices de hash não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="54764-156">When querying a memory-optimized table with inequality predicates, nonclustered indexes will perform better than nonclustered hash indexes.</span></span>  
  
 <span data-ttu-id="54764-157">O índice de hash requer uma chave (para submeter a hash) para realizar a busca no índice.</span><span class="sxs-lookup"><span data-stu-id="54764-157">The hash index requires a key (to hash) to seek into the index.</span></span> <span data-ttu-id="54764-158">Se uma chave de índice consiste em duas colunas e você fornece apenas a primeira coluna, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não tem uma chave completo ao hash.</span><span class="sxs-lookup"><span data-stu-id="54764-158">If an index key consists of two columns and you only provide the first column, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a complete key to hash.</span></span> <span data-ttu-id="54764-159">Isso resultará em um plano de consulta de exame de índice.</span><span class="sxs-lookup"><span data-stu-id="54764-159">This will result in an index scan query plan.</span></span> <span data-ttu-id="54764-160">O uso determina quais colunas devem ser indexadas.</span><span class="sxs-lookup"><span data-stu-id="54764-160">Usage determines which columns should be indexed.</span></span>  
  
 <span data-ttu-id="54764-161">Quando uma coluna em um índice não clusterizado tiver o mesmo valor em várias linhas (as colunas de chave de índice terão muitos valores duplicados), o desempenho pode diminuir nas atualizações, inserções e exclusões.</span><span class="sxs-lookup"><span data-stu-id="54764-161">When a column in a nonclustered index has the same value in many rows (index key columns have a lot of duplicate values), performance can degrade for updates, inserts, and deletions.</span></span>  <span data-ttu-id="54764-162">Uma maneira de melhorar o desempenho nessa situação é adicionar outra coluna ao índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="54764-162">One way to improve performance in this situation is to add another column to the nonclustered index.</span></span>  
  
### <a name="operations-on-memory-optimized-and-disk-based-indexes"></a><span data-ttu-id="54764-163">Operações em índices com otimização de memória e baseados no disco.</span><span class="sxs-lookup"><span data-stu-id="54764-163">Operations on memory-optimized and disk-based indexes.</span></span>  
  
|<span data-ttu-id="54764-164">Operação</span><span class="sxs-lookup"><span data-stu-id="54764-164">Operation</span></span>|<span data-ttu-id="54764-165">Índice, hash não clusterizado, com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="54764-165">Memory-optimized, nonclustered hash, index</span></span>|<span data-ttu-id="54764-166">Índice não clusterizado com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="54764-166">Memory-optimized nonclustered index</span></span>|<span data-ttu-id="54764-167">Índice baseado em disco</span><span class="sxs-lookup"><span data-stu-id="54764-167">Disk-based index</span></span>|  
|---------------|-------------------------------------------------|------------------------------------------|-----------------------|  
|<span data-ttu-id="54764-168">Verificação de índice, recuperar todas as linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="54764-168">Index Scan, retrieve all table rows.</span></span>|<span data-ttu-id="54764-169">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-169">Yes</span></span>|<span data-ttu-id="54764-170">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-170">Yes</span></span>|<span data-ttu-id="54764-171">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-171">Yes</span></span>|  
|<span data-ttu-id="54764-172">Busca de índice em predicados de igualdade (=).</span><span class="sxs-lookup"><span data-stu-id="54764-172">Index seek on equality predicate(s) (=).</span></span>|<span data-ttu-id="54764-173">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-173">Yes</span></span><br /><br /> <span data-ttu-id="54764-174">(Chave completa necessária.)</span><span class="sxs-lookup"><span data-stu-id="54764-174">(Full key required.)</span></span>|<span data-ttu-id="54764-175">Sim <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="54764-175">Yes <sup>1</sup></span></span>|<span data-ttu-id="54764-176">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-176">Yes</span></span>|  
|<span data-ttu-id="54764-177">Índice Seek em predicados de desigualdade (>, <, \<=, > =, entre).</span><span class="sxs-lookup"><span data-stu-id="54764-177">Index seek on inequality predicates (>, <, \<=, >=, BETWEEN).</span></span>|<span data-ttu-id="54764-178">Não (resultados em uma verificação de índice)</span><span class="sxs-lookup"><span data-stu-id="54764-178">No (results in an index scan)</span></span>|<span data-ttu-id="54764-179">Sim <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="54764-179">Yes <sup>1</sup></span></span>|<span data-ttu-id="54764-180">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-180">Yes</span></span>|  
|<span data-ttu-id="54764-181">Recuperar linhas em uma ordem de classificação que corresponda à definição do índice.</span><span class="sxs-lookup"><span data-stu-id="54764-181">Retrieve rows in a sort-order matching the index definition.</span></span>|<span data-ttu-id="54764-182">Não</span><span class="sxs-lookup"><span data-stu-id="54764-182">No</span></span>|<span data-ttu-id="54764-183">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-183">Yes</span></span>|<span data-ttu-id="54764-184">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-184">Yes</span></span>|  
|<span data-ttu-id="54764-185">Recuperar linhas em uma ordem de classificação que corresponda à inversão da definição do índice.</span><span class="sxs-lookup"><span data-stu-id="54764-185">Retrieve rows in a sort-order matching the reverse of the index definition.</span></span>|<span data-ttu-id="54764-186">Não</span><span class="sxs-lookup"><span data-stu-id="54764-186">No</span></span>|<span data-ttu-id="54764-187">Não</span><span class="sxs-lookup"><span data-stu-id="54764-187">No</span></span>|<span data-ttu-id="54764-188">Sim</span><span class="sxs-lookup"><span data-stu-id="54764-188">Yes</span></span>|  
  
 <span data-ttu-id="54764-189">Na tabela, Sim significa que o índice pode servir adequadamente o pedido e Não significa que o índice não pode ser usado com êxito para satisfazer o pedido.</span><span class="sxs-lookup"><span data-stu-id="54764-189">In the table, Yes means that the index can adequately service the request and No means that the index cannot be used successfully to satisfy the request.</span></span>  
  
 <span data-ttu-id="54764-190"><sup>1</sup> para um índice com otimização de memória não clusterizado, a chave completa não é necessária para executar uma busca de índice.</span><span class="sxs-lookup"><span data-stu-id="54764-190"><sup>1</sup> For a nonclustered memory-optimized index, the full key is not required to perform an index seek.</span></span> <span data-ttu-id="54764-191">Embora, de acordo com a ordem de colunas da chave de índice, ocorrerá um exame se o valor de uma coluna aparecer após uma coluna ausente.</span><span class="sxs-lookup"><span data-stu-id="54764-191">Although, given the column order of the index key, a scan will occur if a value for a column comes after a missing column.</span></span>  
  
## <a name="index-count"></a><span data-ttu-id="54764-192">Contagem de índice</span><span class="sxs-lookup"><span data-stu-id="54764-192">Index Count</span></span>  
 <span data-ttu-id="54764-193">Uma tabela com otimização de memória pode ter até 8 índices, incluindo o índice criado com a chave primária.</span><span class="sxs-lookup"><span data-stu-id="54764-193">A memory-optimized table can have up to 8 indexes, including the index created with the primary key.</span></span>  
  
 <span data-ttu-id="54764-194">Em relação ao número de índices criados em uma tabela com otimização de memória, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="54764-194">Regarding the number of indexes created on a memory-optimized table, consider the following:</span></span>  
  
-   <span data-ttu-id="54764-195">Especifique os índices que você precisa quando cria a tabela.</span><span class="sxs-lookup"><span data-stu-id="54764-195">Specify the indexes you need when you create the table.</span></span> <span data-ttu-id="54764-196">Não é possível criar um índice para uma tabela com otimização de memória depois que a tabela é criada.</span><span class="sxs-lookup"><span data-stu-id="54764-196">You cannot create an index for a memory-optimized table after the table is created.</span></span> <span data-ttu-id="54764-197">Se você deseja adicionar um índice a uma tabela com otimização de memória, solte e recrie a tabela.</span><span class="sxs-lookup"><span data-stu-id="54764-197">If you want to add an index to a memory-optimized table, drop and recreate that table.</span></span>  
  
-   <span data-ttu-id="54764-198">Não crie um índice que você use raramente:</span><span class="sxs-lookup"><span data-stu-id="54764-198">Do not create an index that you rarely use:</span></span>  
  
     <span data-ttu-id="54764-199">A coleta de lixo funciona melhor se todos os índices na tabela forem usados frequentemente.</span><span class="sxs-lookup"><span data-stu-id="54764-199">Garbage collection works best if all indexes on the table are frequently used.</span></span> <span data-ttu-id="54764-200">Os índices usados raramente podem fazer com que o sistema de coleta de lixo não seja bem executado em versões de linha antigas.</span><span class="sxs-lookup"><span data-stu-id="54764-200">Rarely-used indexes may cause the garbage collection system to not perform optimally for old row versions.</span></span>  
  
## <a name="creating-a-memory-optimized-index-code-samples"></a><span data-ttu-id="54764-201">Criando um índice com otimização de memória: exemplos de código</span><span class="sxs-lookup"><span data-stu-id="54764-201">Creating a Memory-Optimized Index: Code Samples</span></span>  
 <span data-ttu-id="54764-202">Índice de hash em nível de coluna:</span><span class="sxs-lookup"><span data-stu-id="54764-202">Column level hash index:</span></span>  
  
```sql  
CREATE TABLE t1   
   (c1 INT NOT NULL INDEX idx HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="54764-203">Índice de hash em nível de tabela:</span><span class="sxs-lookup"><span data-stu-id="54764-203">Table level hash index:</span></span>  
  
```sql  
CREATE TABLE t1_1   
   (c1 INT NOT NULL,   
   INDEX IDX HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="54764-204">Índice de hash chave primária em nível de coluna:</span><span class="sxs-lookup"><span data-stu-id="54764-204">Column level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="54764-205">Índice de hash de chave primária em nível de tabela:</span><span class="sxs-lookup"><span data-stu-id="54764-205">Table level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2_2   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="54764-206">Índice não clusterizado em nível de coluna:</span><span class="sxs-lookup"><span data-stu-id="54764-206">Column level nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t3   
   (c1 INT NOT NULL INDEX ID)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="54764-207">Índice não clusterizado em nível de tabela:</span><span class="sxs-lookup"><span data-stu-id="54764-207">Table level nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t3_3   
   (c1 INT NOT NULL,   
   INDEX IDX NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="54764-208">Índice não clusterizado de chave primária em nível de coluna:</span><span class="sxs-lookup"><span data-stu-id="54764-208">Column level primary key nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t4   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="54764-209">Índice não clusterizado de chave primária em nível de tabela:</span><span class="sxs-lookup"><span data-stu-id="54764-209">Table level primary key nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t4_4   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="54764-210">Índice de várias colunas definido depois que as colunas são definidas:</span><span class="sxs-lookup"><span data-stu-id="54764-210">Multicolumn index defined after columns are defined:</span></span>  
  
```sql  
create table t (  
       a int not null constraint ta primary key nonclustered,  
       b int not null,  
       c int not null,  
       d int not null,  
       index idx_t_b_c_d nonclustered (b, c asc, d desc)  
) with (memory_optimized = on, durability = SCHEMA_AND_DATA)  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="54764-211">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54764-211">See Also</span></span>  
 <span data-ttu-id="54764-212">[Índices em tabelas com otimização de memória](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="54764-212">[Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="54764-213">[Determinando o número correto de buckets para índices de hash](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="54764-213">[Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span></span>  
 [<span data-ttu-id="54764-214">Índices de hash</span><span class="sxs-lookup"><span data-stu-id="54764-214">Hash Indexes</span></span>](hash-indexes.md)  
  
  
