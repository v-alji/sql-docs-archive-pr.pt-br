---
title: Criando e gerenciando armazenamento para objetos com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 622aabe6-95c7-42cc-8768-ac2e679c5089
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 118e5e582a284023dd8e5cc71629d635e79fb989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572569"
---
# <a name="creating-and-managing-storage-for-memory-optimized-objects"></a><span data-ttu-id="6f79e-102">Criando e gerenciando armazenamento para objetos com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6f79e-102">Creating and Managing Storage for Memory-Optimized Objects</span></span>
  <span data-ttu-id="6f79e-103">O mecanismo [!INCLUDE[hek_2](../../includes/hek-2-md.md)] é integrado ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o que permite que você tenha tabelas com otimização de memória e tabelas baseadas em disco (tradicionais) no mesmo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f79e-103">The [!INCLUDE[hek_2](../../includes/hek-2-md.md)] engine is integrated into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which lets you have both memory-optimized tables and (traditional) disk-based tables in the same database.</span></span> <span data-ttu-id="6f79e-104">No entanto, a estrutura de armazenamento para tabelas com otimização de memória é diferente daquela para tabelas baseadas em disco.</span><span class="sxs-lookup"><span data-stu-id="6f79e-104">However, the storage structure for memory-optimized tables is different from disk-based tables.</span></span>  
  
 <span data-ttu-id="6f79e-105">O armazenamento de tabela com base em disco tem os seguintes atributos de chave:</span><span class="sxs-lookup"><span data-stu-id="6f79e-105">Storage for disk-based table has following key attributes:</span></span>  
  
-   <span data-ttu-id="6f79e-106">Mapeado para um grupo de arquivos, e o grupo de arquivos contém um ou mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="6f79e-106">Mapped to a filegroup and the filegroup contains one or more files.</span></span>  
  
-   <span data-ttu-id="6f79e-107">Cada arquivo é dividido em extensões de 8 páginas e cada página tem tamanho de 8 Kb.</span><span class="sxs-lookup"><span data-stu-id="6f79e-107">Each file is divided into extents of 8 pages and each page is of size 8K bytes.</span></span>  
  
-   <span data-ttu-id="6f79e-108">Uma extensão pode ser compartilhada entre várias tabelas, mas há mapeamento de 1 para 1 entre uma página alocada e a tabela ou índice.</span><span class="sxs-lookup"><span data-stu-id="6f79e-108">An extent can be shared across multiple tables, but a there is 1-to-1 mapping between an allocated page and the table or index.</span></span> <span data-ttu-id="6f79e-109">Em outras palavras, uma página não pode ter linhas de duas ou mais tabelas ou índices.</span><span class="sxs-lookup"><span data-stu-id="6f79e-109">In other words, a page can't have rows from two or more tables or index.</span></span>  
  
-   <span data-ttu-id="6f79e-110">Os dados são movidos para a memória (pool de buffers) conforme necessário e as páginas modificadas ou recém-criadas assincronamente são gravadas no disco, gerando principalmente E/S aleatória.</span><span class="sxs-lookup"><span data-stu-id="6f79e-110">The data is moved into memory (the buffer pool) as needed and the modified or newly created pages are asynchronously written to the disk generating mostly random IO.</span></span>  
  
 <span data-ttu-id="6f79e-111">O armazenamento de tabelas com otimização de memória tem os seguintes atributos de chave:</span><span class="sxs-lookup"><span data-stu-id="6f79e-111">Storage for memory-optimized tables has following key attributes:</span></span>  
  
-   <span data-ttu-id="6f79e-112">Todas as tabelas com otimização de memória são mapeadas para um grupo de arquivos com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="6f79e-112">All memory-optimized tables are mapped to a memory-optimized filegroup.</span></span> <span data-ttu-id="6f79e-113">Esse grupo de arquivos é criado usando o grupo de arquivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="6f79e-113">This filegroup is built using the filestream filegroup.</span></span>  
  
-   <span data-ttu-id="6f79e-114">Não existem páginas e os dados são persistentes como uma linha.</span><span class="sxs-lookup"><span data-stu-id="6f79e-114">There are no pages and the data is persisted as a row.</span></span>  
  
-   <span data-ttu-id="6f79e-115">Todas as alterações em tabelas com otimização de memória são armazenadas, sendo anexadas a arquivos ativos.</span><span class="sxs-lookup"><span data-stu-id="6f79e-115">All changes to memory-optimized tables are stored by appending to active files.</span></span> <span data-ttu-id="6f79e-116">A leitura e a gravação de arquivos são sequenciais.</span><span class="sxs-lookup"><span data-stu-id="6f79e-116">Both reading and writing to files is sequential.</span></span>  
  
-   <span data-ttu-id="6f79e-117">Uma atualização é registrada como uma exclusão seguida de uma inserção.</span><span class="sxs-lookup"><span data-stu-id="6f79e-117">An update is implemented as a delete followed by an insert.</span></span> <span data-ttu-id="6f79e-118">As linhas excluídas não são removidas imediatamente do armazenamento.</span><span class="sxs-lookup"><span data-stu-id="6f79e-118">The deleted rows are not immediately removed from the storage.</span></span> <span data-ttu-id="6f79e-119">As linhas excluídas são removidas por um processo em segundo plano chamado MERGE, com base em uma política conforme descrito em [Durabilidade de tabelas com otimização de memória](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6f79e-119">The deleted rows are removed by a background process, called MERGE, based on a policy as described in [Durability for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
-   <span data-ttu-id="6f79e-120">Ao contrário das tabelas baseadas em disco, o armazenamento para tabelas com otimização de memória não é compactado.</span><span class="sxs-lookup"><span data-stu-id="6f79e-120">Unlike disk-based tables, storage for memory-optimized tables is not compressed.</span></span> <span data-ttu-id="6f79e-121">Ao migrar uma tabela baseada em disco compactada (ROW ou PAGE) para tabela com otimização de memória, você precisará levar em conta a alteração no tamanho.</span><span class="sxs-lookup"><span data-stu-id="6f79e-121">When migrating a compressed (ROW or PAGE) disk-based table to memory-optimized table, you will need to account for the change in size.</span></span>  
  
-   <span data-ttu-id="6f79e-122">Uma tabela com otimização de memória pode ser durável ou não durável.</span><span class="sxs-lookup"><span data-stu-id="6f79e-122">A memory-optimized table can be durable or can be non-durable.</span></span> <span data-ttu-id="6f79e-123">Você só precisa configurar o armazenamento para as tabelas duráveis de otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="6f79e-123">You only need to configure storage for durable memory-optimize tables.</span></span>  
  
 <span data-ttu-id="6f79e-124">Esta seção descreve os pares do arquivo do ponto de verificação e outros aspectos do armazenamento de dados em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="6f79e-124">This section describes checkpoint file pairs and other aspects of how data in memory-optimized tables is stored.</span></span>  
  
 <span data-ttu-id="6f79e-125">Tópicos desta seção:</span><span class="sxs-lookup"><span data-stu-id="6f79e-125">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="6f79e-126">Configuração do armazenamento para tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6f79e-126">Configuring Storage for Memory-Optimized Tables</span></span>](configuring-storage-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="6f79e-127">O grupo de arquivos com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6f79e-127">The Memory Optimized Filegroup</span></span>](the-memory-optimized-filegroup.md)  
  
-   [<span data-ttu-id="6f79e-128">Durabilidade de tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6f79e-128">Durability for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
-   [<span data-ttu-id="6f79e-129">Operação de ponto de verificação para tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6f79e-129">Checkpoint Operation for Memory-Optimized Tables</span></span>](checkpoint-operation-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="6f79e-130">Definindo a durabilidade dos objetos com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6f79e-130">Defining Durability for Memory-Optimized Objects</span></span>](defining-durability-for-memory-optimized-objects.md)  
  
-   [<span data-ttu-id="6f79e-131">Comparando o armazenamento de tabela baseado em disco com o armazenamento de tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="6f79e-131">Comparing Disk-Based Table Storage to Memory-Optimized Table Storage</span></span>](comparing-disk-based-table-storage-to-memory-optimized-table-storage.md)  
  
-   [<span data-ttu-id="6f79e-132">Monitorando e solucionando problemas de mesclagem de pares de arquivos delta e de dados</span><span class="sxs-lookup"><span data-stu-id="6f79e-132">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>](../../database-engine/monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f79e-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f79e-133">See Also</span></span>  
 [<span data-ttu-id="6f79e-134">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="6f79e-134">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
