---
title: Requisitos de espaço em disco para operações de índice DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- index disk space [SQL Server]
- space [SQL Server], indexes
- indexes [SQL Server], disk space requirements
- temporary disk space [SQL Server]
ms.assetid: 35930826-c870-44c1-a966-a6a4638f62ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4ac25fc1555d6b6cfd8ee97b50d261cf5788f587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583054"
---
# <a name="disk-space-requirements-for-index-ddl-operations"></a><span data-ttu-id="15eb0-102">Disk Space Requirements for Index DDL Operations</span><span class="sxs-lookup"><span data-stu-id="15eb0-102">Disk Space Requirements for Index DDL Operations</span></span>
  <span data-ttu-id="15eb0-103">O espaço em disco é uma consideração importante ao criar, recriar ou cancelar índices.</span><span class="sxs-lookup"><span data-stu-id="15eb0-103">Disk space is an important consideration when you create, rebuild, or drop indexes.</span></span> <span data-ttu-id="15eb0-104">Um espaço em disco inadequado pode degradar o desempenho ou até mesmo provocar falha na operação de índice.</span><span class="sxs-lookup"><span data-stu-id="15eb0-104">Inadequate disk space can degrade performance or even cause the index operation to fail.</span></span> <span data-ttu-id="15eb0-105">Este tópico fornece informações gerais que poderão lhe ajudar a determinar a quantidade de espaço em disco necessária para operações DDL (Linguagem de Definição de Dados) de índice.</span><span class="sxs-lookup"><span data-stu-id="15eb0-105">This topic provides general information that can help you determine the amount of disk space required for index data definition language (DDL) operations.</span></span>  
  
## <a name="index-operations-that-require-no-additional-disk-space"></a><span data-ttu-id="15eb0-106">Operações de índice que não requerem espaço adicional em disco</span><span class="sxs-lookup"><span data-stu-id="15eb0-106">Index Operations That Require No Additional Disk Space</span></span>  
 <span data-ttu-id="15eb0-107">As operações de índice que não requerem nenhum espaço adicional em disco são:</span><span class="sxs-lookup"><span data-stu-id="15eb0-107">The following index operations require no additional disk space:</span></span>  
  
-   <span data-ttu-id="15eb0-108">ALTER INDEX REORGANIZE; porém, espaço de log é necessário.</span><span class="sxs-lookup"><span data-stu-id="15eb0-108">ALTER INDEX REORGANIZE; however, log space is required.</span></span>  
  
-   <span data-ttu-id="15eb0-109">DROP INDEX, quando se está cancelando um índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="15eb0-109">DROP INDEX when you are dropping a nonclustered index.</span></span>  
  
-   <span data-ttu-id="15eb0-110">DROP INDEX quando se está cancelando um índice clusterizado offline sem especificar a cláusula MOVE TO e quando não houver índices não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="15eb0-110">DROP INDEX when you are dropping a clustered index offline without specifying the MOVE TO clause and nonclustered indexes do not exist.</span></span>  
  
-   <span data-ttu-id="15eb0-111">CREATE TABLE (restrições PRIMARY KEY ou UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="15eb0-111">CREATE TABLE (PRIMARY KEY or UNIQUE constraints)</span></span>  
  
## <a name="index-operations-that-require-additional-disk-space"></a><span data-ttu-id="15eb0-112">Operações de índice que requerem espaço adicional em disco</span><span class="sxs-lookup"><span data-stu-id="15eb0-112">Index Operations That Require Additional Disk Space</span></span>  
 <span data-ttu-id="15eb0-113">Todas as outras operações de índice DDL exigem espaço adicional temporário em disco para serem utilizadas na operação, e espaço permanente em disco para armazenar a nova estrutura ou estruturas de índice.</span><span class="sxs-lookup"><span data-stu-id="15eb0-113">All other index DDL operations require additional temporary disk space to use during the operation, and permanent disk space to store the new index structure or structures.</span></span>  
  
 <span data-ttu-id="15eb0-114">Quando uma nova estrutura de índice é criada, o espaço em disco de ambas as estruturas, a antiga (origem) e a nova (destino), é necessário para os arquivos e grupos de arquivos apropriados.</span><span class="sxs-lookup"><span data-stu-id="15eb0-114">When a new index structure is created, disk space for both the old (source) and new (target) structures is required in their appropriate files and filegroups.</span></span> <span data-ttu-id="15eb0-115">A estrutura antiga não é desalocada até que a transação de criação do índice seja confirmada.</span><span class="sxs-lookup"><span data-stu-id="15eb0-115">The old structure is not deallocated until the index creation transaction commits.</span></span>  
  
 <span data-ttu-id="15eb0-116">As seguintes operações de índice DDL criam novas estruturas de índice e exigem espaço adicional em disco:</span><span class="sxs-lookup"><span data-stu-id="15eb0-116">The following index DDL operations create new index structures and require additional disk space:</span></span>  
  
-   <span data-ttu-id="15eb0-117">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="15eb0-117">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="15eb0-118">CREATE INDEX WITH DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="15eb0-118">CREATE INDEX WITH DROP_EXISTING</span></span>  
  
-   <span data-ttu-id="15eb0-119">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="15eb0-119">ALTER INDEX REBUILD</span></span>  
  
-   <span data-ttu-id="15eb0-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY ou UNIQUE)</span><span class="sxs-lookup"><span data-stu-id="15eb0-120">ALTER TABLE ADD CONSTRAINT (PRIMARY KEY or UNIQUE)</span></span>  
  
-   <span data-ttu-id="15eb0-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY ou UNIQUE) quando a restrição tem base em um índice clusterizado</span><span class="sxs-lookup"><span data-stu-id="15eb0-121">ALTER TABLE DROP CONSTRAINT (PRIMARY KEY or UNIQUE) when the constraint is based on a clustered index</span></span>  
  
-   <span data-ttu-id="15eb0-122">DROP INDEX MOVE TO (Aplica-se somente a índices clusterizados.)</span><span class="sxs-lookup"><span data-stu-id="15eb0-122">DROP INDEX MOVE TO (Applies only to clustered indexes.)</span></span>  
  
## <a name="temporary-disk-space-for-sorting"></a><span data-ttu-id="15eb0-123">Espaço em disco temporário para classificação</span><span class="sxs-lookup"><span data-stu-id="15eb0-123">Temporary Disk Space for Sorting</span></span>  
 <span data-ttu-id="15eb0-124">Além do espaço em disco exigido para as estruturas de origem e destino, o espaço em disco temporário é necessário para classificar, a menos que o otimizador de consulta localize um plano de execução que não exija classificação.</span><span class="sxs-lookup"><span data-stu-id="15eb0-124">Besides the disk space required for the source and target structures, temporary disk space is required for sorting, unless the query optimizer finds an execution plan that does not require sorting.</span></span>  
  
 <span data-ttu-id="15eb0-125">Quando a classificação for necessária, a classificação será de um índice novo por vez.</span><span class="sxs-lookup"><span data-stu-id="15eb0-125">If sorting is required, sorting occurs one new index at a time.</span></span> <span data-ttu-id="15eb0-126">Por exemplo, quando você recria um índice clusterizado e índices não clusterizados associados dentro de uma única instrução, os índices são classificados um após o outro.</span><span class="sxs-lookup"><span data-stu-id="15eb0-126">For example, when you rebuild a clustered index and associated nonclustered indexes within a single statement, the indexes are sorted one after the other.</span></span> <span data-ttu-id="15eb0-127">Portanto, o espaço em disco temporário adicional, exigido apenas para classificar, terá que ser tão grande quanto o maior índice da operação.</span><span class="sxs-lookup"><span data-stu-id="15eb0-127">Therefore, the additional temporary disk space that is required for sorting only has to be as large as the largest index in the operation.</span></span> <span data-ttu-id="15eb0-128">Esse, quase sempre, é o índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="15eb0-128">This is almost always the clustered index.</span></span>  
  
 <span data-ttu-id="15eb0-129">Se a opção SORT_IN_TEMPDB for definida como ON, o maior índice deverá se ajustar à **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="15eb0-129">If the SORT_IN_TEMPDB option is set to ON, the largest index must fit into **tempdb**.</span></span> <span data-ttu-id="15eb0-130">Embora essa opção aumente a quantidade de espaço temporário em disco que é usado para criar um índice, pode reduzir o tempo necessário à criação de um índice quando **tempdb** estiver em um conjunto de discos diverso do banco de dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="15eb0-130">Although this option increases the amount of temporary disk space that is used to create an index, it may reduce the time that is required to create an index when **tempdb** is on a set of disks different from the user database.</span></span>  
  
 <span data-ttu-id="15eb0-131">Se SORT_IN_TEMPDB for definida como OFF (padrão), todos os índices, inclusive os índices particionados, serão classificados em seu espaço de disco de destino. Apenas o espaço em disco das estruturas do novo índice será requerido.</span><span class="sxs-lookup"><span data-stu-id="15eb0-131">If SORT_IN_TEMPDB is set to OFF (the default) each index, including partitioned indexes, is sorted in its destination disk space; and only the disk space for the new index structures is required.</span></span>  
  
 <span data-ttu-id="15eb0-132">Para obter um exemplo de cálculo de espaço em disco, consulte [Index Disk Space Example](index-disk-space-example.md).</span><span class="sxs-lookup"><span data-stu-id="15eb0-132">For an example of calculating disk space, see [Index Disk Space Example](index-disk-space-example.md).</span></span>  
  
## <a name="temporary-disk-space-for-online-index-operations"></a><span data-ttu-id="15eb0-133">Espaço temporário em disco para operações de índice online</span><span class="sxs-lookup"><span data-stu-id="15eb0-133">Temporary Disk Space for Online Index Operations</span></span>  
 <span data-ttu-id="15eb0-134">Quando se executam operações de índice online é necessário espaço temporário adicional em disco.</span><span class="sxs-lookup"><span data-stu-id="15eb0-134">When you perform index operations online, additional temporary disk space is required.</span></span>  
  
 <span data-ttu-id="15eb0-135">Se um índice clusterizado for criado, recriado, ou cancelado online, um índice não clusterizado temporário será criado para mapear indicadores antigos para os indicadores novos.</span><span class="sxs-lookup"><span data-stu-id="15eb0-135">If a clustered index is created, rebuilt, or dropped online, a temporary nonclustered index is created to map old bookmarks to new bookmarks.</span></span> <span data-ttu-id="15eb0-136">Se a opção SORT_IN_TEMPDB for definida como ON, esse índice temporário será criado em **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="15eb0-136">If the SORT_IN_TEMPDB option is set to ON, this temporary index is created in **tempdb**.</span></span> <span data-ttu-id="15eb0-137">Se SORT_IN_TEMPDB for definida como OFF, o mesmo grupo de arquivos ou esquema de partição do índice de destino serão usados.</span><span class="sxs-lookup"><span data-stu-id="15eb0-137">If SORT_IN_TEMPDB is set to OFF, the same filegroup or partition scheme as the target index is used.</span></span> <span data-ttu-id="15eb0-138">O índice temporário de mapeamento contém um registro para cada linha da tabela, e seus conteúdos são a união das colunas de indicadores antigas e novas, incluindo indicadores de exclusividade, mais identificadores de registro e incluindo apenas uma cópia única de todas as colunas usadas em ambos os indicadores.</span><span class="sxs-lookup"><span data-stu-id="15eb0-138">The temporary mapping index contains one record for each row in the table, and its contents is the union of the old and new bookmark columns, including uniqueifiers and record identifiers and including only a single copy of any column used in both bookmarks.</span></span> <span data-ttu-id="15eb0-139">Para obter mais informações sobre operações de índice online, consulte [Executar operações de índice online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="15eb0-139">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15eb0-140">A opção SORT_IN_TEMPDB não pode ser definida para instruções DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="15eb0-140">The SORT_IN_TEMPDB option cannot be set for DROP INDEX statements.</span></span> <span data-ttu-id="15eb0-141">O índice temporário de mapeamento é sempre criado no mesmo grupo de arquivos ou esquema de partição que o índice de destino.</span><span class="sxs-lookup"><span data-stu-id="15eb0-141">The temporary mapping index is always created in the same filegroup or partition scheme as the target index.</span></span>  
  
 <span data-ttu-id="15eb0-142">As operações de índice online utilizam o controle de versão de linha para isolar a operação de índice dos efeitos das modificações feitas por outras transações.</span><span class="sxs-lookup"><span data-stu-id="15eb0-142">Online index operations use row versioning to isolate the index operation from the effects of modifications made by other transactions.</span></span> <span data-ttu-id="15eb0-143">Isso evita a necessidade de solicitar bloqueios de compartilhamento de linhas já lidas.</span><span class="sxs-lookup"><span data-stu-id="15eb0-143">This avoids the need for requesting share locks on rows that have been read.</span></span> <span data-ttu-id="15eb0-144">As operações simultâneas de atualização e exclusão de usuários durante operações de índice online precisam de espaço para os registros de versão no **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="15eb0-144">Concurrent user update and delete operations during online index operations require space for version records in **tempdb**.</span></span> <span data-ttu-id="15eb0-145">Para obter mais informações, consulte [Executar operações de índice online](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="15eb0-145">For more information, see [Perform Index Operations Online](perform-index-operations-online.md) .</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="15eb0-146">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="15eb0-146">Related Tasks</span></span>  
 [<span data-ttu-id="15eb0-147">Exemplo de espaço em disco de índice</span><span class="sxs-lookup"><span data-stu-id="15eb0-147">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
 [<span data-ttu-id="15eb0-148">Espaço em disco de log de transações para operações de índice</span><span class="sxs-lookup"><span data-stu-id="15eb0-148">Transaction Log Disk Space for Index Operations</span></span>](transaction-log-disk-space-for-index-operations.md)  
  
 [<span data-ttu-id="15eb0-149">Estimar o tamanho de uma tabela</span><span class="sxs-lookup"><span data-stu-id="15eb0-149">Estimate the Size of a Table</span></span>](../databases/estimate-the-size-of-a-table.md)  
  
 [<span data-ttu-id="15eb0-150">Estimar o tamanho de um índice clusterizado</span><span class="sxs-lookup"><span data-stu-id="15eb0-150">Estimate the Size of a Clustered Index</span></span>](../databases/estimate-the-size-of-a-clustered-index.md)  
  
 [<span data-ttu-id="15eb0-151">Estimar o tamanho de um índice não clusterizado</span><span class="sxs-lookup"><span data-stu-id="15eb0-151">Estimate the Size of a Nonclustered Index</span></span>](../databases/estimate-the-size-of-a-nonclustered-index.md)  
  
 [<span data-ttu-id="15eb0-152">Estimar o tamanho de um heap</span><span class="sxs-lookup"><span data-stu-id="15eb0-152">Estimate the Size of a Heap</span></span>](../databases/estimate-the-size-of-a-heap.md)  
  
## <a name="related-content"></a><span data-ttu-id="15eb0-153">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="15eb0-153">Related Content</span></span>  
 [<span data-ttu-id="15eb0-154">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15eb0-154">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="15eb0-155">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15eb0-155">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
 [<span data-ttu-id="15eb0-156">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15eb0-156">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="15eb0-157">Especificar o fator de preenchimento para um índice</span><span class="sxs-lookup"><span data-stu-id="15eb0-157">Specify Fill Factor for an Index</span></span>](specify-fill-factor-for-an-index.md)  
  
 [<span data-ttu-id="15eb0-158">Reorganizar e recompilar índices</span><span class="sxs-lookup"><span data-stu-id="15eb0-158">Reorganize and Rebuild Indexes</span></span>](indexes.md)  
  
  
