---
title: Estimar requisitos de memória para tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5c5cc1fc-1fdf-4562-9443-272ad9ab5ba8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5c5218a96d3650cbae22501ab2794b1b553996b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684218"
---
# <a name="estimate-memory-requirements-for-memory-optimized-tables"></a><span data-ttu-id="4e408-102">Estimar requisitos de memória para tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="4e408-102">Estimate Memory Requirements for Memory-Optimized Tables</span></span>
  <span data-ttu-id="4e408-103">Se você estiver criando uma nova [!INCLUDE[hek_2](../../includes/hek-2-md.md)] tabela com otimização de memória ou migrando uma tabela baseada em disco existente para uma tabela com otimização de memória, é importante ter uma estimativa razoável das necessidades de memória de cada tabela para que você possa provisionar o servidor com memória suficiente.</span><span class="sxs-lookup"><span data-stu-id="4e408-103">Whether you are creating a new [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized table or migrating an existing disk-based table to a memory-optimized table, it is important to have a reasonable estimate of each table's memory needs so you can provision the server with sufficient memory.</span></span> <span data-ttu-id="4e408-104">Esta seção descreve como estimar a quantidade de memória necessária para manter dados para uma tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="4e408-104">This section describes how to estimate the amount of memory that you need to hold data for a memory-optimized table.</span></span>  
  
 <span data-ttu-id="4e408-105">Se você pretende migrar de tabelas baseadas em disco para tabelas com otimização de memória, antes de continuar neste tópico, veja o tópico [Determinando se uma tabela ou procedimento armazenado deve ser movido para OLTP in-memory](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) para obter diretrizes sobre as melhores tabelas para migração.</span><span class="sxs-lookup"><span data-stu-id="4e408-105">If you are contemplating migrating from disk-based tables to memory-optimized tables, before you proceed in this topic, see the topic [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) for guidance on which tables are best to migrate.</span></span> <span data-ttu-id="4e408-106">Todos os tópicos em [Migrando para OLTP in-memory](migrating-to-in-memory-oltp.md) fornecem diretrizes sobre como migrar de tabelas baseadas em disco para tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="4e408-106">All the topics under [Migrating to In-Memory OLTP](migrating-to-in-memory-oltp.md) provide guidance on migrating from disk-based to memory-optimized tables.</span></span>  
  
## <a name="sections-in-this-topic"></a><span data-ttu-id="4e408-107">Seções neste tópico</span><span class="sxs-lookup"><span data-stu-id="4e408-107">Sections in this topic</span></span>  
  
-   [<span data-ttu-id="4e408-108">Exemplo de tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="4e408-108">Example memory-optimized table</span></span>](#bkmk_ExampleTable)  
  
-   [<span data-ttu-id="4e408-109">Memória da tabela</span><span class="sxs-lookup"><span data-stu-id="4e408-109">Memory for the table</span></span>](#bkmk_MemoryForTable)  
  
-   [<span data-ttu-id="4e408-110">Memória para índices</span><span class="sxs-lookup"><span data-stu-id="4e408-110">Memory for indexes</span></span>](#bkmk_IndexMeemory)  
  
-   [<span data-ttu-id="4e408-111">Memória para o controle de versão de linha</span><span class="sxs-lookup"><span data-stu-id="4e408-111">Memory for row versioning</span></span>](#bkmk_MemoryForRowVersions)  
  
-   [<span data-ttu-id="4e408-112">Memória para variáveis de tabela</span><span class="sxs-lookup"><span data-stu-id="4e408-112">Memory for table variables</span></span>](#bkmk_TableVariables)  
  
-   [<span data-ttu-id="4e408-113">Memória para o crescimento</span><span class="sxs-lookup"><span data-stu-id="4e408-113">Memory for growth</span></span>](#bkmk_MemoryForGrowth)  
  
##  <a name="example-memory-optimized-table"></a><a name="bkmk_ExampleTable"></a> <span data-ttu-id="4e408-114">Exemplo de tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="4e408-114">Example memory-optimized table</span></span>  
 <span data-ttu-id="4e408-115">Considere o esquema de tabela com otimização de memória a seguir:</span><span class="sxs-lookup"><span data-stu-id="4e408-115">Consider the following memory-optimized table schema:</span></span>  
  
```sql  
  
CREATE TABLE t_hk (  
col1 int NOT NULL PRIMARY KEY NONCLUSTERED,  
col2 int NOT NULL INDEX t1c2_index   
     HASH WITH (bucket_count = 5000000),  
col3 int NOT NULL INDEX t1c3_index   
     HASH WITH (bucket_count = 5000000),  
col4 int NOT NULL INDEX t1c4_index   
     HASH WITH (bucket_count = 5000000),  
col5 int NOT NULL INDEX t1c5_index NONCLUSTERED,  
col6 char (50) NOT NULL,  
col7 char (50) NOT NULL,   
col8 char (30) NOT NULL,   
col9 char (50) NOT NULL  
     WITH (memory_optimized = on)  
GO  
  
```  
  
 <span data-ttu-id="4e408-116">Usando esse esquema, determinaremos a memória mínima necessária para essa tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="4e408-116">Using this schema we will determine the minimum memory needed for this memory-optimized table.</span></span>  
  
##  <a name="memory-for-the-table"></a><a name="bkmk_MemoryForTable"></a> <span data-ttu-id="4e408-117">Memória da tabela</span><span class="sxs-lookup"><span data-stu-id="4e408-117">Memory for the table</span></span>  
 <span data-ttu-id="4e408-118">Uma linha de tabela com otimização de memória é composta de três partes:</span><span class="sxs-lookup"><span data-stu-id="4e408-118">A memory-optimized table row is comprised of three parts:</span></span>  
  
-   <span data-ttu-id="4e408-119">**Carimbos de data/hora** </span><span class="sxs-lookup"><span data-stu-id="4e408-119">**Timestamps** </span></span>  
    <span data-ttu-id="4e408-120">Cabeçalho de linha/carimbos de data/hora = 24 bytes.</span><span class="sxs-lookup"><span data-stu-id="4e408-120">Row header/timestamps = 24 bytes.</span></span>  
  
-   <span data-ttu-id="4e408-121">**Ponteiros de índice** </span><span class="sxs-lookup"><span data-stu-id="4e408-121">**Index pointers** </span></span>  
    <span data-ttu-id="4e408-122">Para cada índice de hash na tabela, cada linha tem um ponteiro de endereço de 8 bytes para a próxima linha no índice.</span><span class="sxs-lookup"><span data-stu-id="4e408-122">For each hash index in the table, each row has an 8-byte address pointer to the next row in the index.</span></span>  <span data-ttu-id="4e408-123">Uma vez que há 4 índices, cada linha alocará 32 bytes para ponteiros de índice (um ponteiro de 8 bytes para cada índice).</span><span class="sxs-lookup"><span data-stu-id="4e408-123">Since there are 4 indexes, each row will allocate 32 bytes for index pointers (an 8 byte pointer for each index).</span></span>  
  
-   <span data-ttu-id="4e408-124">**Dados** </span><span class="sxs-lookup"><span data-stu-id="4e408-124">**Data** </span></span>  
    <span data-ttu-id="4e408-125">O tamanho da parte dos dados da linha é determinado pela adição do tamanho de tipo para cada coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="4e408-125">The size of the data portion of the row is determined by summing the type size for each data column.</span></span>  <span data-ttu-id="4e408-126">Em nossa tabela temos cinco números inteiros de 4 bytes, três colunas de caracteres de 50 bytes e uma coluna de caracteres de 30 bytes.</span><span class="sxs-lookup"><span data-stu-id="4e408-126">In our table we have five 4-byte integers, three 50-byte character columns, and one 30-byte character column.</span></span>  <span data-ttu-id="4e408-127">Como consequência, a parte de dados de cada linha tem 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 ou 200 bytes.</span><span class="sxs-lookup"><span data-stu-id="4e408-127">Therefore the data portion of each row is 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 or 200 bytes.</span></span>  
  
 <span data-ttu-id="4e408-128">Veja a seguir uma computação de tamanho para 5.000.000 (5 milhões) de linhas em uma tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="4e408-128">The following is a size computation for 5,000,000 (5 million) rows in a memory-optimized table.</span></span> <span data-ttu-id="4e408-129">A memória total usada pelas linhas de dados é estimada como se segue:</span><span class="sxs-lookup"><span data-stu-id="4e408-129">The total memory used by data rows is estimated as follows:</span></span>  
  
 <span data-ttu-id="4e408-130">**Memória para linhas da tabela**</span><span class="sxs-lookup"><span data-stu-id="4e408-130">**Memory for the table's rows**</span></span>  
  
 <span data-ttu-id="4e408-131">Pelos cálculos acima, o tamanho de cada linha na tabela com otimização de memória é 24 + 32 + 200 ou 256 bytes.</span><span class="sxs-lookup"><span data-stu-id="4e408-131">From the above calculations, the size of each row in the memory-optimized table is 24 + 32 + 200, or 256 bytes.</span></span>  <span data-ttu-id="4e408-132">Como temos 5 milhões de linhas, a tabela consumirá 5.000.000 \* 256 bytes ou 1.280.000.000 bytes – aproximadamente 1,28 GB.</span><span class="sxs-lookup"><span data-stu-id="4e408-132">Since we have 5 million rows, the table will consume 5,000,000 \* 256 bytes, or 1,280,000,000 bytes - approximately 1.28 GB.</span></span>  
  
##  <a name="memory-for-indexes"></a><a name="bkmk_IndexMeemory"></a> <span data-ttu-id="4e408-133">Memória para índices</span><span class="sxs-lookup"><span data-stu-id="4e408-133">Memory for indexes</span></span>  
 <span data-ttu-id="4e408-134">**Memória para cada índice de hash**</span><span class="sxs-lookup"><span data-stu-id="4e408-134">**Memory for each hash index**</span></span>  
  
 <span data-ttu-id="4e408-135">Cada índice de hash é uma matriz de hash de ponteiros de endereço de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="4e408-135">Each hash index is a hash array of 8-byte address pointers.</span></span>  <span data-ttu-id="4e408-136">O tamanho da matriz é melhor determinado pelo número de valores de índice exclusivos para esse índice – por exemplo, o número de valores exclusivos Col2 é um bom ponto de partida para o tamanho da matriz para o t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="4e408-136">The size of the array is best determined by the number of unique index values for that index - e.g., the number of unique Col2 values is a good starting point for the array size for the t1c2_index.</span></span> <span data-ttu-id="4e408-137">Uma matriz de hash que é muito grande desperdiça memória.</span><span class="sxs-lookup"><span data-stu-id="4e408-137">A hash array that is too big wastes memory.</span></span>  <span data-ttu-id="4e408-138">Uma matriz de hash que é muito pequena reduz o desempenho já que haverá muitas colisões pelos valores de índice que usam o hash para o mesmo índice.</span><span class="sxs-lookup"><span data-stu-id="4e408-138">A hash array that is too small slows performance since there will be too many collisions by index values that hash to the same index.</span></span>  
  
 <span data-ttu-id="4e408-139">Os índices de hash atingem muito rápido pesquisas de igualdade como:</span><span class="sxs-lookup"><span data-stu-id="4e408-139">Hash indexes achieve very fast equality lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 = 3  
  
```  
  
 <span data-ttu-id="4e408-140">Os índices não clusterizados são mais rápidos para pesquisas de intervalo como:</span><span class="sxs-lookup"><span data-stu-id="4e408-140">Nonclustered indexes are faster for range lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 >= 3  
  
```  
  
 <span data-ttu-id="4e408-141">Se você estiver migrando uma tabela com base em disco, poderá usar o seguinte para determinar o número de valores exclusivos para o índice t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="4e408-141">If you are migrating a disk-based table you can use the following to determine the number of unique values for the index t1c2_index.</span></span>  
  
```sql  
  
SELECT COUNT(DISTINCT [Col2])  
  FROM t_hk  
  
```  
  
 <span data-ttu-id="4e408-142">Se você estiver criando uma nova tabela, precisará estimar o tamanho da matriz ou a coleta de dados dos testes antes da implantação.</span><span class="sxs-lookup"><span data-stu-id="4e408-142">If you are creating a new table, you'll need to estimate the array size or gather data from your testing prior to deployment.</span></span>  
  
 <span data-ttu-id="4e408-143">Para obter informações sobre como os índices de hash funcionam em tabelas com otimização de memória [!INCLUDE[hek_2](../../includes/hek-2-md.md)] , veja [Índices de hash](../../database-engine/hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4e408-143">For information on how hash indexes work in [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized tables, see [Hash Indexes](../../database-engine/hash-indexes.md).</span></span>  
  
 <span data-ttu-id="4e408-144">**Observação:** Você não pode alterar o tamanho da matriz de índice de hash em tempo real.</span><span class="sxs-lookup"><span data-stu-id="4e408-144">**Note:** You cannot change the hash index array size on the fly.</span></span> <span data-ttu-id="4e408-145">Para alterar o tamanho da matriz de índice de hash é necessário remover a tabela, alterar o valor de bucket_count e recriar a tabela.</span><span class="sxs-lookup"><span data-stu-id="4e408-145">To change the hash index array size you must drop the table, change the bucket_count value and recreate the table.</span></span>  
  
 <span data-ttu-id="4e408-146">**Definindo o tamanho da matriz de índice de hash**</span><span class="sxs-lookup"><span data-stu-id="4e408-146">**Setting the hash index array size**</span></span>  
  
 <span data-ttu-id="4e408-147">O tamanho da matriz de hash é definido por `(bucket_count= <value>)` , em que \<value> é um valor inteiro maior que zero.</span><span class="sxs-lookup"><span data-stu-id="4e408-147">The hash array size is set by `(bucket_count= <value>)` where \<value> is an integer value greater than zero.</span></span> <span data-ttu-id="4e408-148">Se \<value> não for uma potência de 2, o bucket_count real será arredondado até a potência seguinte mais próxima de 2.</span><span class="sxs-lookup"><span data-stu-id="4e408-148">If \<value> is not a power of 2, the actual bucket_count is rounded up to the next closest power of 2.</span></span>  <span data-ttu-id="4e408-149">Em nossa tabela de exemplo, (bucket_count = 5 milhões), como 5 milhões não é uma potência de 2, a contagem de buckets real é arredondada para 8.388.608 (2<sup>23</sup>).</span><span class="sxs-lookup"><span data-stu-id="4e408-149">In our example table, (bucket_count = 5000000), since 5,000,000 is not a power of 2, the actual bucket count rounds up to 8,388,608 (2<sup>23</sup>).</span></span>  <span data-ttu-id="4e408-150">Você deve usar esse número, e não 5.000.000 quando calcular a memória necessária à matriz de hash.</span><span class="sxs-lookup"><span data-stu-id="4e408-150">You must use this number, not 5,000,000 when calculating memory needed by the hash array.</span></span>  
  
 <span data-ttu-id="4e408-151">Assim, em nosso exemplo, a memória necessária para cada matriz de hash é:</span><span class="sxs-lookup"><span data-stu-id="4e408-151">Thus, in our example, the memory needed for each hash array is:</span></span>  
  
 <span data-ttu-id="4e408-152">8.388.608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67.108.864 ou aproximadamente 64 MB.</span><span class="sxs-lookup"><span data-stu-id="4e408-152">8,388,608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67,108,864 or approximately 64 MB.</span></span>  
  
 <span data-ttu-id="4e408-153">Como temos três índices de hash, a memória necessária para os índices de hash é 3 \* 64MB = 192MB.</span><span class="sxs-lookup"><span data-stu-id="4e408-153">Since we have three hash indexes, the memory needed for the hash indexes is 3 \* 64MB = 192MB.</span></span>  
  
 <span data-ttu-id="4e408-154">**Memória para índices não clusterizados**</span><span class="sxs-lookup"><span data-stu-id="4e408-154">**Memory for nonclustered indexes**</span></span>  
  
 <span data-ttu-id="4e408-155">Os índices não clusterizados são implementados como árvores B com os nós internos que contêm o valor e ponteiros de índice aos nós subsequentes.</span><span class="sxs-lookup"><span data-stu-id="4e408-155">Nonclustered indexes are implemented as BTrees with the inner nodes containing the index value and pointers to subsequent nodes.</span></span>  <span data-ttu-id="4e408-156">Os nós folha contêm o valor de índice e um ponteiro para a linha da tabela na memória.</span><span class="sxs-lookup"><span data-stu-id="4e408-156">Leaf nodes contain the index value and a pointer to the table row in memory.</span></span>  
  
 <span data-ttu-id="4e408-157">Diferentemente dos índices de hash, os índices não clusterizados não têm um tamanho fixo do bucket.</span><span class="sxs-lookup"><span data-stu-id="4e408-157">Unlike hash indexes, nonclustered indexes do not have a fixed bucket size.</span></span> <span data-ttu-id="4e408-158">O índice aumenta e diminui dinamicamente com os dados.</span><span class="sxs-lookup"><span data-stu-id="4e408-158">The index grows and shrinks dynamically with the data.</span></span>  
  
 <span data-ttu-id="4e408-159">A memória necessária pelos índices não clusterizados pode ser computada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4e408-159">Memory needed by nonclustered indexes can be computed as follows:</span></span>  
  
-   <span data-ttu-id="4e408-160">**Memória alocada a nós que não são nós folha** </span><span class="sxs-lookup"><span data-stu-id="4e408-160">**Memory allocated to non-leaf nodes** </span></span>  
    <span data-ttu-id="4e408-161">Para uma configuração comum, a memória alocada para nós não folha é uma porcentagem muito pequena da memória total usada pelo índice.</span><span class="sxs-lookup"><span data-stu-id="4e408-161">For a typical configuration, the memory allocated to non-leaf nodes is a small percentage of the overall memory taken by the index.</span></span> <span data-ttu-id="4e408-162">Ela é tão pequena que pode seguramente ser ignorada.</span><span class="sxs-lookup"><span data-stu-id="4e408-162">This is so small it can safely be ignored.</span></span>  
  
-   <span data-ttu-id="4e408-163">**Memória para nós folha** </span><span class="sxs-lookup"><span data-stu-id="4e408-163">**Memory for leaf nodes** </span></span>  
    <span data-ttu-id="4e408-164">Os nós folha têm uma linha para cada chave exclusiva na tabela que aponta para as linhas de dados com essa chave exclusiva.</span><span class="sxs-lookup"><span data-stu-id="4e408-164">The leaf nodes have one row for each unique key in the table that points to the data rows with that unique key.</span></span>  <span data-ttu-id="4e408-165">Se você tiver várias linhas com a mesma chave (isto é, tiver um índice não clusterizado não exclusivo), haverá apenas uma linha no nó folha de índice que apontará para uma das linhas com as outras linhas vinculadas entre si.</span><span class="sxs-lookup"><span data-stu-id="4e408-165">If you have multiple rows with the same key (i.e., you have a non-unique nonclustered index), there is only one row in the index leaf node that points to one of the rows with the other rows linked to each other.</span></span>  <span data-ttu-id="4e408-166">Assim, a memória total necessária pode ser aproximado por:</span><span class="sxs-lookup"><span data-stu-id="4e408-166">Thus, the total memory required can be approximated by:</span></span>   
    <span data-ttu-id="4e408-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span><span class="sxs-lookup"><span data-stu-id="4e408-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span></span>  
  
 <span data-ttu-id="4e408-168">Os índices não clusterizados são os melhores quando usado para pesquisas de intervalo, como exemplificadas pela seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="4e408-168">Nonclustered indexes are best when used for range lookups, as exemplified by the following query:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE c2 > 5  
```  
  
##  <a name="memory-for-row-versioning"></a><a name="bkmk_MemoryForRowVersions"></a> <span data-ttu-id="4e408-169">Memória para o controle de versão de linha</span><span class="sxs-lookup"><span data-stu-id="4e408-169">Memory for row versioning</span></span>  
 <span data-ttu-id="4e408-170">Para evitar bloqueios, OLTP de memória usa a simultaneidade otimista ao atualizar ou excluir linhas.</span><span class="sxs-lookup"><span data-stu-id="4e408-170">To avoid locks, In-Memory OLTP uses optimistic concurrency when updating or deleting rows.</span></span> <span data-ttu-id="4e408-171">Isso significa que quando uma linha é atualizada, uma versão de linha adicional será criada.</span><span class="sxs-lookup"><span data-stu-id="4e408-171">This means that when a row is updated, an additional version of the row is created.</span></span> <span data-ttu-id="4e408-172">O sistema mantém as versões anteriores disponíveis até que todas as transações que poderiam possivelmente usar a versão concluiu a execução.</span><span class="sxs-lookup"><span data-stu-id="4e408-172">The system keeps the previous versions available until all transactions that could possibly use the version have finished execution.</span></span> <span data-ttu-id="4e408-173">Quando uma linha for excluída, o sistema atua de uma maneira semelhante a uma atualização, mantendo a versão disponível até que não estão mais necessário.</span><span class="sxs-lookup"><span data-stu-id="4e408-173">When a row is deleted, the system acts in a similar way to an update, keeping the version available until it is no longer necessary.</span></span> <span data-ttu-id="4e408-174">Leitura e inserções não criam versões adicionais de linha.</span><span class="sxs-lookup"><span data-stu-id="4e408-174">Reads and inserts do not create additional row versions.</span></span>  
  
 <span data-ttu-id="4e408-175">Como pode haver um número de linhas adicionais na memória a qualquer momento aguardando o ciclo de coleta de lixo para liberar a memória, você deve ter memória suficiente para acomodar estas linhas adicionais.</span><span class="sxs-lookup"><span data-stu-id="4e408-175">Because there may be a number of additional rows in memory at any time waiting for the garbage collection cycle to release their memory, you must have sufficient memory to accommodate these additional rows.</span></span>  
  
 <span data-ttu-id="4e408-176">O número de linhas adicionais podem ser estimado calculando o número máximo de linhas por segundo de atualizações e exclusões de linha, então multiplicando que o número de segundos a transação mais longa demora (um mínimo de 1).</span><span class="sxs-lookup"><span data-stu-id="4e408-176">The number of additional rows can be estimated by computing the peak number of row updates and deletions per second, then multiplying that by the number of seconds the longest transaction takes (minimum of 1).</span></span>  
  
 <span data-ttu-id="4e408-177">Esse valor é então multiplicado pelo tamanho da linha para obter o número de bytes necessários para o controle de versão de linha.</span><span class="sxs-lookup"><span data-stu-id="4e408-177">That value is then multiplied by the row size to get the number of bytes you need for row versioning.</span></span>  
  
 `rowVersions = durationOfLongestTransactionInSeconds * peakNumberOfRowUpdatesOrDeletesPerSecond`  
  
 <span data-ttu-id="4e408-178">As necessidades de memória para linhas obsoletas são então estimadas multiplicando o número de linhas obsoletas pelo tamanho de uma linha de tabela com otimização de memória (consulte [a memória da tabela](#bkmk_MemoryForTable) acima).</span><span class="sxs-lookup"><span data-stu-id="4e408-178">Memory needs for stale rows is then estimated by multiplying the number of stale rows by the size of a memory-optimized table row (see [Memory for the table](#bkmk_MemoryForTable) above).</span></span>  
  
 `memoryForRowVersions = rowVersions * rowSize`  
  
##  <a name="memory-for-table-variables"></a><a name="bkmk_TableVariables"></a> <span data-ttu-id="4e408-179">Memória para variáveis de tabela</span><span class="sxs-lookup"><span data-stu-id="4e408-179">Memory for table variables</span></span>  
 <span data-ttu-id="4e408-180">A memória usada para uma variável de tabela é liberada apenas quando a variável de tabela sai do escopo.</span><span class="sxs-lookup"><span data-stu-id="4e408-180">Memory used for a table variable is released only when the table variable goes out of scope.</span></span> <span data-ttu-id="4e408-181">As linhas excluídas, inclusive as linhas excluídas como parte de uma atualização, de uma variável de tabela, não estão sujeitas à coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="4e408-181">Deleted rows, including rows deleted as part of an update, from a table variable are not subject to garbage collection.</span></span> <span data-ttu-id="4e408-182">Nenhuma memória é liberada até a variável de tabela sair do escopo.</span><span class="sxs-lookup"><span data-stu-id="4e408-182">No memory is released until the table variable exits scope.</span></span>  
  
 <span data-ttu-id="4e408-183">As variáveis de tabela definidas em um lote SQL grande, e não em um escopo do procedimento, que são usadas em muitas transações podem consumir bastante memória.</span><span class="sxs-lookup"><span data-stu-id="4e408-183">Table variables defined in a large SQL batch, as opposed to a procedure scope, which are used in many transactions, can consume a lot of memory.</span></span> <span data-ttu-id="4e408-184">Como elas não têm coleta de lixo, as linhas excluídas em uma variável de tabela podem consumir muita memória e diminuir o desempenho, pois as operações de leitura precisam verificar as linhas excluídas.</span><span class="sxs-lookup"><span data-stu-id="4e408-184">Because they are not garbage collected, deleted rows in a table variable can consume a lot memory and degrade performance since read operations need to scan past the deleted rows.</span></span>  
  
##  <a name="memory-for-growth"></a><a name="bkmk_MemoryForGrowth"></a> <span data-ttu-id="4e408-185">Memória para o crescimento</span><span class="sxs-lookup"><span data-stu-id="4e408-185">Memory for growth</span></span>  
 <span data-ttu-id="4e408-186">Os cálculos acima estima suas necessidades de memória para a tabela como existe atualmente.</span><span class="sxs-lookup"><span data-stu-id="4e408-186">The above calculations estimate your memory needs for the table as it currently exists.</span></span> <span data-ttu-id="4e408-187">Além dessa memória, você precisa estimar o aumento da tabela e fornecimento de memória suficiente para acomodar esse crescimento.</span><span class="sxs-lookup"><span data-stu-id="4e408-187">In addition to this memory, you need to estimate the growth of the table and provide sufficient memory to accommodate that growth.</span></span>  <span data-ttu-id="4e408-188">Por exemplo, se você antecipar o crescimento de 10% no múltiplo da necessidade dos resultados acima por 1,1 para obter a memória total necessária para a tabela.</span><span class="sxs-lookup"><span data-stu-id="4e408-188">For example, if you anticipate 10% growth then you need to multiple the results from above by 1.1 to get the total memory needed for your table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e408-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e408-189">See Also</span></span>  
 [<span data-ttu-id="4e408-190">Migrando para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="4e408-190">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
