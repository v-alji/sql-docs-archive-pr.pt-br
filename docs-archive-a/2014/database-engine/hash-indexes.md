---
title: Índices de hash | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f4bdc9c1-7922-4fac-8183-d11ec58fec4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8d1e3a5d92078cc2ec3fe7cd5b6d3fb5b47c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685260"
---
# <a name="hash-indexes"></a><span data-ttu-id="7ffe7-102">Índices de hash</span><span class="sxs-lookup"><span data-stu-id="7ffe7-102">Hash Indexes</span></span>
  <span data-ttu-id="7ffe7-103">Os índices são usados como pontos de entrada para tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-103">Indexes are used as entry points for memory-optimized tables.</span></span> <span data-ttu-id="7ffe7-104">A leitura das linhas de uma tabela requer um índice para localizar os dados na memória.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-104">Reading rows from a table requires an index to locate the data in memory.</span></span>  
  
 <span data-ttu-id="7ffe7-105">Um índice de hash consiste em uma coleção de buckets organizados em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-105">A hash index consists of a collection of buckets organized in an array.</span></span> <span data-ttu-id="7ffe7-106">Uma função de hash mapeia chaves de índice para buckets correspondentes no índice de hash.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-106">A hash function maps index keys to corresponding buckets in the hash index.</span></span> <span data-ttu-id="7ffe7-107">A figura a seguir mostra três chaves de índice mapeadas para três buckets diferentes no índice de hash.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-107">The following figure shows three index keys that are mapped to three different buckets in the hash index.</span></span> <span data-ttu-id="7ffe7-108">Para fins ilustrativos, o nome da função de hash é f(x).</span><span class="sxs-lookup"><span data-stu-id="7ffe7-108">For illustration purposes the hash function name is f(x).</span></span>  
  
 <span data-ttu-id="7ffe7-109">![Chaves de índice mapeadas para buckets diferentes.](../../2014/database-engine/media/hekaton-tables-2.gif "Chaves de índice mapeadas para buckets diferentes.")</span><span class="sxs-lookup"><span data-stu-id="7ffe7-109">![Index keys mapped to different buckets.](../../2014/database-engine/media/hekaton-tables-2.gif "Index keys mapped to different buckets.")</span></span>  
  
 <span data-ttu-id="7ffe7-110">A função de hash usada para índices de hash tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="7ffe7-110">The hashing function used for hash indexes has the following characteristics:</span></span>  
  
-   <span data-ttu-id="7ffe7-111">O [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tem uma função de hash que é usada para todos os índices de hash.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-111">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has one hash function that is used for all hash indexes.</span></span>  
  
-   <span data-ttu-id="7ffe7-112">A função de hash é determinística.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-112">The hash function is deterministic.</span></span> <span data-ttu-id="7ffe7-113">A mesma chave de índice sempre é mapeada para o mesmo bucket no índice de hash.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-113">The same index key is always mapped to the same bucket in the hash index.</span></span>  
  
-   <span data-ttu-id="7ffe7-114">Várias chaves de índice podem ser mapeadas para o mesmo bucket de hash.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-114">Multiple index keys may be mapped to the same hash bucket.</span></span>  
  
-   <span data-ttu-id="7ffe7-115">A função de hash é equilibrada, o que significa que a distribuição de valores de chave do índice sobre buckets de hash geralmente segue uma distribuição de Poisson.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-115">The hash function is balanced, meaning that the distribution of index key values over hash buckets typically follows a Poisson distribution.</span></span>  
  
     <span data-ttu-id="7ffe7-116">A distribuição de Poisson não é uma distribuição uniforme.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-116">Poisson distribution is not an even distribution.</span></span> <span data-ttu-id="7ffe7-117">Os valores de chave de índice não são distribuídos uniformemente nos buckets de hash.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-117">Index key values are not evenly distributed in the hash buckets.</span></span> <span data-ttu-id="7ffe7-118">Por exemplo, uma distribuição de Poisson de chaves de índice distintas *n* nos buckets de hash *n* resulta em aproximadamente um terço de buckets vazios, um terço de buckets que contêm uma chave de índice e o outro terço contendo duas chaves de índice.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-118">For example, a Poisson distribution of *n* distinct index keys over *n* hash buckets results in approximately one third empty buckets, one third of the buckets containing one index key, and the other third containing two index keys.</span></span> <span data-ttu-id="7ffe7-119">Um número pequeno de buckets conterá mais de duas chaves.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-119">A small number of buckets will contain more than two keys.</span></span>  
  
 <span data-ttu-id="7ffe7-120">Se duas chaves de índice forem mapeadas para o mesmo bucket de hash, haverá uma colisão de hash.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-120">If two index keys are mapped to the same hash bucket, there is a hash collision.</span></span> <span data-ttu-id="7ffe7-121">Um número grande de colisões de hash pode afetar o desempenho das operações de leitura.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-121">A large number of hash collisions can have a performance impact on read operations.</span></span>  
  
 <span data-ttu-id="7ffe7-122">A estrutura de índice de hash na memória consiste em uma matriz de ponteiros de memória.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-122">The in-memory hash index structure consists of an array of memory pointers.</span></span> <span data-ttu-id="7ffe7-123">Cada bucket é mapeado para um deslocamento nesta matriz.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-123">Each bucket maps to an offset in this array.</span></span> <span data-ttu-id="7ffe7-124">Cada bucket na matriz aponta para a primeira linha desse bucket de hash.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-124">Each bucket in the array points to the first row in that hash bucket.</span></span> <span data-ttu-id="7ffe7-125">Cada linha no bucket aponta para a próxima linha, resultando em uma cadeia de linhas para cada bucket de hash, conforme ilustrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-125">Each row in the bucket points to the next row, thus resulting in a chain of rows for each hash bucket, as illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="7ffe7-126">![A estrutura de índice de hash em memória.](../../2014/database-engine/media/hekaton-tables-3.gif "A estrutura de índice de hash em memória.")</span><span class="sxs-lookup"><span data-stu-id="7ffe7-126">![The in-memory hash index structure.](../../2014/database-engine/media/hekaton-tables-3.gif "The in-memory hash index structure.")</span></span>  
  
 <span data-ttu-id="7ffe7-127">A figura tem três buckets com linhas.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-127">The figure has three buckets with rows.</span></span> <span data-ttu-id="7ffe7-128">O segundo bucket na parte superior contém as três linhas vermelhas.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-128">The second bucket from the top contains the three red rows.</span></span> <span data-ttu-id="7ffe7-129">O quarto bucket contém uma única linha azul.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-129">The fourth bucket contains the single blue row.</span></span> <span data-ttu-id="7ffe7-130">O bucket inferior contém as duas linhas verdes.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-130">The bottom bucket contains the two green rows.</span></span> <span data-ttu-id="7ffe7-131">Essas versões podem ser diferentes e estarem na mesma linha.</span><span class="sxs-lookup"><span data-stu-id="7ffe7-131">These could be different versions of the same row.</span></span>  
  
 <span data-ttu-id="7ffe7-132">Para obter mais informações sobre índices para tabelas com otimização de memória, consulte [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7ffe7-132">For more information about indexes for memory-optimized tables, see [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ffe7-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ffe7-133">See Also</span></span>  
 [<span data-ttu-id="7ffe7-134">Índices em tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="7ffe7-134">Indexes on Memory-Optimized Tables</span></span>](../../2014/database-engine/indexes-on-memory-optimized-tables.md)  
  
  
