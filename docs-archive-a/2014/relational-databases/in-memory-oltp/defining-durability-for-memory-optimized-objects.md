---
title: Definindo a durabilidade dos objetos com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0fe85fbf-8e8d-4983-96fd-d04b3c7d6d65
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 325f50a74ea75270dd62fc3564200c59255dc6cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571381"
---
# <a name="defining-durability-for-memory-optimized-objects"></a><span data-ttu-id="dd280-102">Definindo a durabilidade dos objetos com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="dd280-102">Defining Durability for Memory-Optimized Objects</span></span>
  <span data-ttu-id="dd280-103">O OLTP na memória garante as propriedades ACID (total atomicidade, consistência, isolamento e total durabilidade).</span><span class="sxs-lookup"><span data-stu-id="dd280-103">In-Memory OLTP guarantees full atomicity, consistency, isolation, and full durability (ACID) properties.</span></span> <span data-ttu-id="dd280-104">A durabilidade no contexto do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e nas tabelas com otimização de memória oferece as seguintes garantias:</span><span class="sxs-lookup"><span data-stu-id="dd280-104">Durability in the context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and memory-optimized tables provides following guarantees:</span></span>  
  
 <span data-ttu-id="dd280-105">Durabilidade transacional</span><span class="sxs-lookup"><span data-stu-id="dd280-105">Transactional Durability</span></span>  
 <span data-ttu-id="dd280-106">Quando você confirma uma transação completamente durável que fez alterações (DDL ou DML) em uma tabela com otimização de memória, as alterações feitas em uma tabela durável com otimização de memória tornam-se permanentes.</span><span class="sxs-lookup"><span data-stu-id="dd280-106">When you commit a fully durable transaction that made (DDL or DML) changes to a memory-optimized table, the changes made to a durable memory-optimized table are permanent.</span></span>  
  
 <span data-ttu-id="dd280-107">Quando você confirma uma transação durável atrasada em uma tabela com otimização de memória, a transação se torna durável somente depois que o log de transações na memória é salvo em disco.</span><span class="sxs-lookup"><span data-stu-id="dd280-107">When you commit a delayed durable transaction to a memory-optimized table, the transaction becomes durable only after the in-memory transaction log is saved to disk.</span></span>  
  
 <span data-ttu-id="dd280-108">Durabilidade de reinicialização</span><span class="sxs-lookup"><span data-stu-id="dd280-108">Restart Durability</span></span>  
 <span data-ttu-id="dd280-109">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é reiniciado após uma pane ou um desligamento planejado, as tabelas duráveis com otimização de memória são instanciadas novamente para que sejam restauradas para o estado anterior ao desligamento ou à pane.</span><span class="sxs-lookup"><span data-stu-id="dd280-109">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restarts after a crash or planned shutdown, the memory-optimized durable tables are reinstantiated to restore them to the state before the shutdown or crash.</span></span>  
  
 <span data-ttu-id="dd280-110">Durabilidade da falha de mídia</span><span class="sxs-lookup"><span data-stu-id="dd280-110">Media Failure Durability</span></span>  
 <span data-ttu-id="dd280-111">Se um disco com falha ou corrompido contiver uma ou mais cópias persistentes dos objetos duráveis com otimização de memória, o recurso de backup e restauração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restaurará as tabelas com otimização de memória na nova mídia.</span><span class="sxs-lookup"><span data-stu-id="dd280-111">If a failed or corrupt disk contains one or more persisted copies of durable memory-optimized objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore feature restores memory-optimized tables on the new media.</span></span>  
  
 <span data-ttu-id="dd280-112">Há duas opções de durabilidade nas tabelas com otimização de memória:</span><span class="sxs-lookup"><span data-stu-id="dd280-112">There are two durability options for memory-optimized tables:</span></span>  
  
 <span data-ttu-id="dd280-113">SCHEMA_ONLY (tabela não durável)</span><span class="sxs-lookup"><span data-stu-id="dd280-113">SCHEMA_ONLY (non-durable table)</span></span>  
 <span data-ttu-id="dd280-114">Essa opção assegura a durabilidade do esquema da tabela, inclusive os índices.</span><span class="sxs-lookup"><span data-stu-id="dd280-114">This option ensures durability of the table schema, including indexes.</span></span> <span data-ttu-id="dd280-115">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é reiniciado, a tabela não durável é recriada, mas começa sem nenhum dado.</span><span class="sxs-lookup"><span data-stu-id="dd280-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted, the non-durable table is recreated, but starts with no data.</span></span> <span data-ttu-id="dd280-116">(Isso é diferente de uma tabela em tempdb, onde a tabela e seus dados são perdidos na reinicialização.) Um cenário típico para criar uma tabela não durável é armazenar dados transitórios, como uma tabela de preparo para um processo ETL.</span><span class="sxs-lookup"><span data-stu-id="dd280-116">(This is unlike a table in tempdb, where both the table and its data are lost upon restart.) A typical scenario for creating a non-durable table is to store transient data, such as a staging table for an ETL process.</span></span> <span data-ttu-id="dd280-117">Uma durabilidade SCHEMA_ONLY evita o log e o ponto de verificação da transação, o que pode reduzir significativamente as operações de E/S.</span><span class="sxs-lookup"><span data-stu-id="dd280-117">A SCHEMA_ONLY durability avoids both transaction logging and checkpoint, which can significantly reduce I/O operations.</span></span>  
  
 <span data-ttu-id="dd280-118">SCHEMA_AND_DATA (tabela durável)</span><span class="sxs-lookup"><span data-stu-id="dd280-118">SCHEMA_AND_DATA (durable table)</span></span>  
 <span data-ttu-id="dd280-119">Essa opção fornece a durabilidade tanto do esquema quanto dos dados.</span><span class="sxs-lookup"><span data-stu-id="dd280-119">This option provides durability of both schema and data.</span></span> <span data-ttu-id="dd280-120">O nível de durabilidade dos dados depende da transação que você confirmará, se completamente durável ou com durabilidade atrasada.</span><span class="sxs-lookup"><span data-stu-id="dd280-120">The level of data durability depends on whether you commit a transaction as fully durable or with delayed durability.</span></span> <span data-ttu-id="dd280-121">Transações completamente duráveis fornecem a mesma garantia de durabilidade de dados e de esquema, semelhante a uma tabela baseada em disco.</span><span class="sxs-lookup"><span data-stu-id="dd280-121">Fully durable transactions provide the same durability guarantee for data and schema, similar to a disk-based table.</span></span> <span data-ttu-id="dd280-122">A durabilidade atrasada melhorará o desempenho, mas poderá resultar na perda potencial de dados caso haja uma falha no servidor ou um failover.</span><span class="sxs-lookup"><span data-stu-id="dd280-122">Delayed durability will improve performance but can potentially result in data loss in case of a server crash or fail over.</span></span> <span data-ttu-id="dd280-123">(Para obter mais informações sobre a durabilidade atrasada, consulte [Controlar durabilidade atrasada](../logs/control-transaction-durability.md).)</span><span class="sxs-lookup"><span data-stu-id="dd280-123">(For more information about delayed durability, see [Control Transaction Durability](../logs/control-transaction-durability.md).)</span></span>  
  
 <span data-ttu-id="dd280-124">O esquema da tabela com otimização de memória é persistente, semelhante às tabelas baseadas em disco, no grupo de arquivos primário de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dd280-124">The schema of the memory-optimized table is persisted, similar to disk-based tables, in the primary file group of a database.</span></span>  
  
 <span data-ttu-id="dd280-125">Os dados em tabelas duráveis com otimização de memória são salvos em pares de arquivos delta e de dados.</span><span class="sxs-lookup"><span data-stu-id="dd280-125">Data in durable memory-optimized tables is saved in data and delta file pairs.</span></span>  
  
 <span data-ttu-id="dd280-126">Os índices definidos nas tabelas com otimização de memória persistem apenas nos metadados, e não no armazenamento.</span><span class="sxs-lookup"><span data-stu-id="dd280-126">The indexes defined in memory-optimized tables persist only in metadata, not in storage.</span></span> <span data-ttu-id="dd280-127">As estruturas de índice são geradas como parte do carregamento das tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="dd280-127">Index structures are generated as part of loading memory-optimized tables.</span></span>  
  
 <span data-ttu-id="dd280-128">As linhas são excluídas explicitamente por uma instrução DELETE ou indiretamente por uma instrução UPDATE.</span><span class="sxs-lookup"><span data-stu-id="dd280-128">Rows are deleted either explicitly by a DELETE statement or indirectly by an UPDATE statement.</span></span> <span data-ttu-id="dd280-129">Uma operação UPDATE é executada como uma exclusão seguida por uma inserção.</span><span class="sxs-lookup"><span data-stu-id="dd280-129">An UPDATE operation is executed as a delete followed by an insert.</span></span> <span data-ttu-id="dd280-130">Quando uma linha é excluída, nenhuma alteração é feita em um arquivo de dados, mas uma nova linha, identificando a linha excluída, é acrescentada ao arquivo delta correspondente.</span><span class="sxs-lookup"><span data-stu-id="dd280-130">When a row is deleted, no change is made to a data file but a new row, identifying the deleted row, is appended to the corresponding delta file.</span></span>  
  
 <span data-ttu-id="dd280-131">Durante as operações de recuperação ou restauração, o mecanismo OLTP na memória lê os arquivos delta e de dados para carregamento na memória física.</span><span class="sxs-lookup"><span data-stu-id="dd280-131">During recovery or restore operations, the In-Memory OLTP engine reads data and delta files for loading into physical memory.</span></span> <span data-ttu-id="dd280-132">O tempo de carregamento é determinado pelos seguintes fatores:</span><span class="sxs-lookup"><span data-stu-id="dd280-132">The load time is determined by:</span></span>  
  
-   <span data-ttu-id="dd280-133">A quantidade de dados a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="dd280-133">The amount of data to load.</span></span>  
  
-   <span data-ttu-id="dd280-134">Largura de banda de E/S sequencial.</span><span class="sxs-lookup"><span data-stu-id="dd280-134">Sequential I/O bandwidth.</span></span>  
  
-   <span data-ttu-id="dd280-135">Grau de paralelismo, determinado pelo número de contêineres de arquivo e núcleos de processador.</span><span class="sxs-lookup"><span data-stu-id="dd280-135">Degree of parallelism, determined by number of file containers and processor cores.</span></span>  
  
-   <span data-ttu-id="dd280-136">A quantidade de registros de log na parte ativa do log que precisam ser refeitos.</span><span class="sxs-lookup"><span data-stu-id="dd280-136">The amount of log records in the active portion of the log that need to be redone.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd280-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd280-137">See Also</span></span>  
 [<span data-ttu-id="dd280-138">Criando e gerenciando armazenamento para objetos com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="dd280-138">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  
