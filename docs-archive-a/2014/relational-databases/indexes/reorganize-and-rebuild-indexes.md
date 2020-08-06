---
title: Reorganizar e recompilar índices | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.fragmentation.f1
- sql12.swb.index.reorg.f1
- sql12.swb.index.rebuild.f1
helpviewer_keywords:
- large object defragmenting
- indexes [SQL Server], reorganizing
- index reorganization [SQL Server]
- reorganizing indexes
- defragmenting large object data types
- index fragmentation [SQL Server]
- index rebuilding [SQL Server]
- rebuilding indexes
- indexes [SQL Server], rebuilding
- defragmenting indexes
- nonclustered indexes [SQL Server], defragmenting
- fragmentation [SQL Server]
- index defragmenting [SQL Server]
- LOB data [SQL Server], defragmenting
- clustered indexes, defragmenting
ms.assetid: a28c684a-c4e9-4b24-a7ae-e248808b31e9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c00f2128bb4c54064511ffff9e8929c9faf4d59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684742"
---
# <a name="reorganize-and-rebuild-indexes"></a><span data-ttu-id="06b31-102">Reorganizar e recriar índices</span><span class="sxs-lookup"><span data-stu-id="06b31-102">Reorganize and Rebuild Indexes</span></span>
  <span data-ttu-id="06b31-103">Este tópico descreve como reorganizar ou recompilar índice fragmentado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06b31-103">This topic describes how to reorganize or rebuild a fragmented index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="06b31-104">O [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] mantém os índices automaticamente sempre que são realizadas operações de entrada, atualização ou exclusão nos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="06b31-104">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically maintains indexes whenever insert, update, or delete operations are made to the underlying data.</span></span> <span data-ttu-id="06b31-105">No decorrer do tempo, essas modificações podem fazer com que as informações do índice sejam dispersadas pelo banco de dados (fragmentadas).</span><span class="sxs-lookup"><span data-stu-id="06b31-105">Over time these modifications can cause the information in the index to become scattered in the database (fragmented).</span></span> <span data-ttu-id="06b31-106">A fragmentação ocorre quando os índices têm páginas nas quais a ordem lógica, com base no valor de chave, não corresponde à ordem física do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="06b31-106">Fragmentation exists when indexes have pages in which the logical ordering, based on the key value, does not match the physical ordering inside the data file.</span></span> <span data-ttu-id="06b31-107">Índices com fragmentação pesada podem degradar o desempenho da consulta e causar lentidão de resposta do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="06b31-107">Heavily fragmented indexes can degrade query performance and cause your application to respond slowly.</span></span>  
  
 <span data-ttu-id="06b31-108">Você pode solucionar a fragmentação de índice reorganizando ou recriando um índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-108">You can remedy index fragmentation by reorganizing or rebuilding an index.</span></span> <span data-ttu-id="06b31-109">Para índices particionados criados em um esquema de partição, é possível usar qualquer um desses métodos em um índice completo ou em uma única partição de índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-109">For partitioned indexes built on a partition scheme, you can use either of these methods on a complete index or a single partition of an index.</span></span> <span data-ttu-id="06b31-110">A recriação de um índice descarta e recria o índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-110">Rebuilding an index drops and re-creates the index.</span></span> <span data-ttu-id="06b31-111">Isso remove a fragmentação, recupera espaço em disco ao compactar as páginas com base na configuração do fator de preenchimento especificada ou existente, e reclassifica as linhas do índice em páginas contíguas.</span><span class="sxs-lookup"><span data-stu-id="06b31-111">This removes fragmentation, reclaims disk space by compacting the pages based on the specified or existing fill factor setting, and reorders the index rows in contiguous pages.</span></span> <span data-ttu-id="06b31-112">Quando ALL é especificado, todos os índices da tabela são descartados e recriados em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="06b31-112">When ALL is specified, all indexes on the table are dropped and rebuilt in a single transaction.</span></span> <span data-ttu-id="06b31-113">A reorganização de um índice utiliza recursos mínimos do sistema.</span><span class="sxs-lookup"><span data-stu-id="06b31-113">Reorganizing an index uses minimal system resources.</span></span> <span data-ttu-id="06b31-114">Ela desfragmenta o nível folha de índices clusterizados e não clusterizados em tabelas e exibições, reordenando fisicamente as páginas de nível folha para que correspondam à ordem lógica, da esquerda para a direita, dos nós folha.</span><span class="sxs-lookup"><span data-stu-id="06b31-114">It defragments the leaf level of clustered and nonclustered indexes on tables and views by physically reordering the leaf-level pages to match the logical, left to right, order of the leaf nodes.</span></span> <span data-ttu-id="06b31-115">A reorganização também compacta as páginas de índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-115">Reorganizing also compacts the index pages.</span></span> <span data-ttu-id="06b31-116">A compactação baseia-se no valor do fator de preenchimento existente.</span><span class="sxs-lookup"><span data-stu-id="06b31-116">Compaction is based on the existing fill factor value.</span></span>  
  
 <span data-ttu-id="06b31-117">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="06b31-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="06b31-118">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="06b31-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="06b31-119">Detectando a fragmentação</span><span class="sxs-lookup"><span data-stu-id="06b31-119">Detecting Fragmentation</span></span>](#Fragmentation)  
  
     [<span data-ttu-id="06b31-120">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="06b31-120">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="06b31-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="06b31-121">Security</span></span>](#Security)  
  
-   <span data-ttu-id="06b31-122">**Para verificar a fragmentação de um índice usando:**</span><span class="sxs-lookup"><span data-stu-id="06b31-122">**To check the fragmentation of an index, using:**</span></span>  
  
     [<span data-ttu-id="06b31-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06b31-123">SQL Server Management Studio</span></span>](#SSMSProcedureFrag)  
  
     [<span data-ttu-id="06b31-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06b31-124">Transact-SQL</span></span>](#TsqlProcedureFrag)  
  
-   <span data-ttu-id="06b31-125">**Para reorganizar ou recompilar um índice usando:**</span><span class="sxs-lookup"><span data-stu-id="06b31-125">**To reorganize or rebuild an index, using:**</span></span>  
  
     [<span data-ttu-id="06b31-126">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06b31-126">SQL Server Management Studio</span></span>](#SSMSProcedureReorg)  
  
     [<span data-ttu-id="06b31-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06b31-127">Transact-SQL</span></span>](#TsqlProcedureReorg)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="06b31-128">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="06b31-128">Before You Begin</span></span>  
  
###  <a name="detecting-fragmentation"></a><a name="Fragmentation"></a><span data-ttu-id="06b31-129">Detectando a fragmentação</span><span class="sxs-lookup"><span data-stu-id="06b31-129">Detecting Fragmentation</span></span>  
 <span data-ttu-id="06b31-130">A primeira etapa para optar pelo método de fragmentação a ser usado é analisar o índice para determinar o grau de fragmentação.</span><span class="sxs-lookup"><span data-stu-id="06b31-130">The first step in deciding which defragmentation method to use is to analyze the index to determine the degree of fragmentation.</span></span> <span data-ttu-id="06b31-131">Usando a função de sistema [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql), você pode detectar a fragmentação em um índice específico, em todos os índices de uma tabela ou exibição indexada, em todos os índices de um banco de dados ou em todos os índices de todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="06b31-131">By using the system function [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql), you can detect fragmentation in a specific index, all indexes on a table or indexed view, all indexes in a database, or all indexes in all databases.</span></span> <span data-ttu-id="06b31-132">Para índices particionados, **sys.dm_db_index_physical_stats** também fornece informações de fragmentação por partição.</span><span class="sxs-lookup"><span data-stu-id="06b31-132">For partitioned indexes, **sys.dm_db_index_physical_stats** also provides fragmentation information for each partition.</span></span>  
  
 <span data-ttu-id="06b31-133">O conjunto de resultados retornado pela função **sys.dm_db_index_physical_stats** inclui as colunas a seguir.</span><span class="sxs-lookup"><span data-stu-id="06b31-133">The result set returned by the **sys.dm_db_index_physical_stats** function includes the following columns.</span></span>  
  
|<span data-ttu-id="06b31-134">Column</span><span class="sxs-lookup"><span data-stu-id="06b31-134">Column</span></span>|<span data-ttu-id="06b31-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="06b31-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="06b31-136">**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="06b31-136">**avg_fragmentation_in_percent**</span></span>|<span data-ttu-id="06b31-137">Porcentagem de fragmentação lógica (páginas fora de ordem no índice).</span><span class="sxs-lookup"><span data-stu-id="06b31-137">The percent of logical fragmentation (out-of-order pages in the index).</span></span>|  
|<span data-ttu-id="06b31-138">**fragment_count**</span><span class="sxs-lookup"><span data-stu-id="06b31-138">**fragment_count**</span></span>|<span data-ttu-id="06b31-139">Número de fragmentos (páginas folha fisicamente consecutivas) do índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-139">The number of fragments (physically consecutive leaf pages) in the index.</span></span>|  
|<span data-ttu-id="06b31-140">**avg_fragment_size_in_pages**</span><span class="sxs-lookup"><span data-stu-id="06b31-140">**avg_fragment_size_in_pages**</span></span>|<span data-ttu-id="06b31-141">Número médio de páginas em um fragmento de índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-141">Average number of pages in one fragment in an index.</span></span>|  
  
 <span data-ttu-id="06b31-142">Depois que o grau de fragmentação for conhecido, use a tabela a seguir para determinar o melhor método para corrigir a fragmentação.</span><span class="sxs-lookup"><span data-stu-id="06b31-142">After the degree of fragmentation is known, use the following table to determine the best method to correct the fragmentation.</span></span>  
  
|<span data-ttu-id="06b31-143">Valor**avg_fragmentation_in_percent**</span><span class="sxs-lookup"><span data-stu-id="06b31-143">**avg_fragmentation_in_percent** value</span></span>|<span data-ttu-id="06b31-144">Instrução corretiva</span><span class="sxs-lookup"><span data-stu-id="06b31-144">Corrective statement</span></span>|  
|-----------------------------------------------|--------------------------|  
|<span data-ttu-id="06b31-145">> 5% e \< = 30%</span><span class="sxs-lookup"><span data-stu-id="06b31-145">> 5% and \< = 30%</span></span>|<span data-ttu-id="06b31-146">ALTER INDEX REORGANIZE</span><span class="sxs-lookup"><span data-stu-id="06b31-146">ALTER INDEX REORGANIZE</span></span>|  
|<span data-ttu-id="06b31-147">> 30%</span><span class="sxs-lookup"><span data-stu-id="06b31-147">> 30%</span></span>|<span data-ttu-id="06b31-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="06b31-148">ALTER INDEX REBUILD WITH (ONLINE = ON) <sup>1</sup></span></span>|

<span data-ttu-id="06b31-149"><sup>1</sup> A recompilação de um índice pode ser executada online ou offline.</span><span class="sxs-lookup"><span data-stu-id="06b31-149"><sup>1</sup> Rebuilding an index can be executed online or offline.</span></span> <span data-ttu-id="06b31-150">A reorganização de um índice sempre é executada online.</span><span class="sxs-lookup"><span data-stu-id="06b31-150">Reorganizing an index is always executed online.</span></span> <span data-ttu-id="06b31-151">Para atingir disponibilidade semelhante à opção de reorganização, recrie índices online.</span><span class="sxs-lookup"><span data-stu-id="06b31-151">To achieve availability similar to the reorganize option, you should rebuild indexes online.</span></span>  
  
> [!TIP]
> <span data-ttu-id="06b31-152">Esses valores fornecem uma orientação aproximada para determinar o ponto em que você deve mudar entre `ALTER INDEX REORGANIZE` e `ALTER INDEX REBUILD`.</span><span class="sxs-lookup"><span data-stu-id="06b31-152">These values provide a rough guideline for determining the point at which you should switch between `ALTER INDEX REORGANIZE` and `ALTER INDEX REBUILD`.</span></span> <span data-ttu-id="06b31-153">Contudo, os valores reais podem variar de acordo com o caso.</span><span class="sxs-lookup"><span data-stu-id="06b31-153">However, the actual values may vary from case to case.</span></span> <span data-ttu-id="06b31-154">É importante que você experimente para poder determinar o melhor limite para um ambiente.</span><span class="sxs-lookup"><span data-stu-id="06b31-154">It is important that you experiment to determine the best threshold for your environment.</span></span> <span data-ttu-id="06b31-155">Por exemplo, se um determinado índice for usado principalmente para operações de verificação, o desempenho delas poderá ser aprimorado pela remoção da fragmentação.</span><span class="sxs-lookup"><span data-stu-id="06b31-155">For example, if a given index is used mainly for scan operations, removing fragmentation can improve performance of these operations.</span></span> <span data-ttu-id="06b31-156">O benefício de desempenho é menos perceptível para índices que são usados principalmente para operações de busca.</span><span class="sxs-lookup"><span data-stu-id="06b31-156">The performance benefit is less noticeable for indexes that are used primarily for seek operations.</span></span> <span data-ttu-id="06b31-157">Da mesma forma, remover a fragmentação em um heap (uma tabela sem índice clusterizado) é especialmente útil para operações de verificação de índice não clusterizado, mas tem pouco efeito em operações de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="06b31-157">Similarly, removing fragmentation in a heap (a table with no clustered index) is especially useful for nonclustered index scan operations, but has little effect in lookup operations.</span></span>

<span data-ttu-id="06b31-158">Em geral, níveis muito baixos de fragmentação (menos de 5 por cento) não devem ser resolvidos por nenhum desses comandos, pois o benefício da remoção de uma pequena quantidade de fragmentação é quase sempre amplamente excedido pelo custo da reorganização ou da recriação do índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-158">Very low levels of fragmentation (less than 5 percent) should typically not be addressed by either of these commands, because the benefit from removing such a small amount of fragmentation is almost always vastly outweighed by the cost of reorganizing or rebuilding the index.</span></span> 

> [!NOTE]
> <span data-ttu-id="06b31-159">A recriação ou reorganização de índices pequenos geralmente não reduz a fragmentação.</span><span class="sxs-lookup"><span data-stu-id="06b31-159">Rebuilding or reorganizing small indexes often does not reduce fragmentation.</span></span> <span data-ttu-id="06b31-160">As páginas de índices pequenos às vezes são armazenadas em extensões mistas.</span><span class="sxs-lookup"><span data-stu-id="06b31-160">The pages of small indexes are sometimes stored on mixed extents.</span></span> <span data-ttu-id="06b31-161">Extensões mistas são compartilhadas por até oito objetos, portanto, a fragmentação em um índice pequeno pode não ser reduzida após a reorganização ou recriação.</span><span class="sxs-lookup"><span data-stu-id="06b31-161">Mixed extents are shared by up to eight objects, so the fragmentation in a small index might not be reduced after reorganizing or rebuilding it.</span></span>

### <a name="index-defragmentation-considerations"></a><span data-ttu-id="06b31-162">Considerações sobre fragmentação de índice</span><span class="sxs-lookup"><span data-stu-id="06b31-162">Index defragmentation considerations</span></span>
<span data-ttu-id="06b31-163">Em determinadas condições, recompilar um índice clusterizado recompilará automaticamente todo índice não clusterizado que faça referência à chave de clustering, se os identificadores físicos ou lógicos contidos nos registros de índice não clusterizados precisarem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="06b31-163">Under certain conditions, rebuilding a clustered index will automatically rebuild any nonclustered index that reference the clustering key, if the physical or logical identifiers contained in the nonclustered index records needs to change.</span></span>

<span data-ttu-id="06b31-164">Cenários que requerem que todos os índices não clusterizados sejam automaticamente recompilados em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="06b31-164">Scenarios that force all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="06b31-165">Criar um índice clusterizado em uma tabela</span><span class="sxs-lookup"><span data-stu-id="06b31-165">Creating a clustered index on a table</span></span>
-  <span data-ttu-id="06b31-166">Remover um índice clusterizado, fazendo com que a tabela seja armazenada como um heap</span><span class="sxs-lookup"><span data-stu-id="06b31-166">Removing a clustered index, causing the table to be stored as a heap</span></span>
-  <span data-ttu-id="06b31-167">Alterar a chave de clustering para incluir ou excluir colunas</span><span class="sxs-lookup"><span data-stu-id="06b31-167">Changing the clustering key to include or exclude columns</span></span>

<span data-ttu-id="06b31-168">Cenários que não requerem que todos os índices não clusterizados sejam automaticamente recompilados em uma tabela:</span><span class="sxs-lookup"><span data-stu-id="06b31-168">Scenarios that do not require all nonclustered indexes to be automatically rebuilt on a table:</span></span>

-  <span data-ttu-id="06b31-169">Recompilar um índice clusterizado exclusivo</span><span class="sxs-lookup"><span data-stu-id="06b31-169">Rebuilding a unique clustered index</span></span>
-  <span data-ttu-id="06b31-170">Recompilar um índice clusterizado não exclusivo</span><span class="sxs-lookup"><span data-stu-id="06b31-170">Rebuilding a non-unique clustered index</span></span>
-  <span data-ttu-id="06b31-171">Alterar o esquema de índice (assim como ao aplicar um esquema de particionamento a um índice clusterizado) ou mover o índice clusterizado para um grupo de arquivos diferente</span><span class="sxs-lookup"><span data-stu-id="06b31-171">Changing the index schema, such as applying a partitioning scheme to a clustered index or moving the clustered index to a different filegroup</span></span>
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="06b31-172">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="06b31-172">Limitations and Restrictions</span></span>  
  
<span data-ttu-id="06b31-173">Índices com mais de 128 extensões são recriados em duas fases separadas: lógica e física.</span><span class="sxs-lookup"><span data-stu-id="06b31-173">Indexes with more than 128 extents are rebuilt in two separate phases: logical and physical.</span></span> <span data-ttu-id="06b31-174">Na fase lógica, as unidades de alocação existentes usadas pelo índice são marcadas para desalocação, as linhas de dados são copiadas, ordenadas e, depois, movidas para novas unidades de alocação criadas para armazenar o índice recriado.</span><span class="sxs-lookup"><span data-stu-id="06b31-174">In the logical phase, the existing allocation units used by the index are marked for deallocation, the data rows are copied and sorted, then moved to new allocation units created to store the rebuilt index.</span></span> <span data-ttu-id="06b31-175">Na fase física, as unidades de alocação previamente marcadas para desalocação são fisicamente canceladas em transações curtas que ocorrem em segundo plano e que não exigem muitos bloqueios.</span><span class="sxs-lookup"><span data-stu-id="06b31-175">In the physical phase, the allocation units previously marked for deallocation are physically dropped in short transactions that happen in the background, and do not require many locks.</span></span> <span data-ttu-id="06b31-176">Para obter mais informações sobre as extensões, consulte o [Guia de arquitetura de páginas e extensões](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span><span class="sxs-lookup"><span data-stu-id="06b31-176">For more information about extents, refer to the [Pages and Extents Architecture Guide](https://docs.microsoft.com/sql/relational-databases/pages-and-extents-architecture-guide).</span></span>

<span data-ttu-id="06b31-177">A instrução `ALTER INDEX REORGANIZE` exige que o arquivo de dados que contém o índice tenha espaço disponível, pois a operação só pode alocar páginas de trabalho temporárias no mesmo arquivo, não em outro arquivo no grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="06b31-177">The `ALTER INDEX REORGANIZE` statement requires the data file containing the index to have space available, because the operation can only allocate temporary work pages on the same file, not another file within the filegroup.</span></span> <span data-ttu-id="06b31-178">Portanto, embora o grupo de arquivos possa ter páginas livres disponíveis, o usuário ainda poderá se deparar com o erro 1105:`Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span><span class="sxs-lookup"><span data-stu-id="06b31-178">So although the filegroup might have free pages available, the user can still encounter error 1105: `Could not allocate space for object '###' in database '###' because the '###' filegroup is full. Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.`</span></span>

<span data-ttu-id="06b31-179">É possível criar e recompilar índices não alinhados em uma tabela com mais de 1.000 partições, mas isso não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="06b31-179">Creating and rebuilding non-aligned indexes on a table with more than 1,000 partitions is possible, but is not recommended.</span></span> <span data-ttu-id="06b31-180">Fazer isso pode provocar degradação do desempenho ou consumo excessivo de memória durante essas operações.</span><span class="sxs-lookup"><span data-stu-id="06b31-180">Doing so may cause degraded performance or excessive memory consumption during these operations.</span></span>

<span data-ttu-id="06b31-181">Um índice não poderá ser reorganizado ou recriado se o grupo de arquivos no qual ele está localizado estiver offline ou definido como somente leitura.</span><span class="sxs-lookup"><span data-stu-id="06b31-181">An index cannot be reorganized or rebuilt if the filegroup in which it is located is offline or set to read-only.</span></span> <span data-ttu-id="06b31-182">Quando a palavra-chave `ALL` for especificada e um ou mais índices estiver em um grupo de arquivos offline ou somente leitura, a instrução falhará.</span><span class="sxs-lookup"><span data-stu-id="06b31-182">When the keyword `ALL` is specified and one or more indexes are in an offline or read-only filegroup, the statement fails.</span></span>
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="06b31-183">Segurança</span><span class="sxs-lookup"><span data-stu-id="06b31-183">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="06b31-184">Permissões</span><span class="sxs-lookup"><span data-stu-id="06b31-184">Permissions</span></span>  
 <span data-ttu-id="06b31-185">Requer a permissão `ALTER` na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="06b31-185">Requires `ALTER` permission on the table or view.</span></span> <span data-ttu-id="06b31-186">O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="06b31-186">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureFrag"></a> <span data-ttu-id="06b31-187">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06b31-187">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="06b31-188">Para verificar a fragmentação de um índice</span><span class="sxs-lookup"><span data-stu-id="06b31-188">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="06b31-189">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja verificar a fragmentação de um índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-189">In Object Explorer, Expand the database that contains the table on which you want to check an index's fragmentation.</span></span>  
  
2.  <span data-ttu-id="06b31-190">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="06b31-190">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="06b31-191">Expanda a tabela na qual você deseja verificar a fragmentação de um índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-191">Expand the table on which you want to check an index's fragmentation.</span></span>  
  
4.  <span data-ttu-id="06b31-192">Expanda a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="06b31-192">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="06b31-193">Clique com o botão direito do mouse no índice cuja fragmentação você deseja verificar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="06b31-193">Right-click the index of which you want to check the fragmentation and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="06b31-194">Em **Selecione uma página**, selecione **Fragmentação**.</span><span class="sxs-lookup"><span data-stu-id="06b31-194">Under **Select a page**, select **Fragmentation**.</span></span>  
  
     <span data-ttu-id="06b31-195">As informações a seguir estão disponíveis na página **Fragmentação** :</span><span class="sxs-lookup"><span data-stu-id="06b31-195">The following information is available on the **Fragmentation** page:</span></span>  
  
     <span data-ttu-id="06b31-196">**Preenchimento da página**</span><span class="sxs-lookup"><span data-stu-id="06b31-196">**Page fullness**</span></span>  
     <span data-ttu-id="06b31-197">Indica o preenchimento médio das páginas do índice, como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="06b31-197">Indicates average fullness of the index pages, as a percentage.</span></span> <span data-ttu-id="06b31-198">100% significa que as páginas de índice estão completamente preenchidas.</span><span class="sxs-lookup"><span data-stu-id="06b31-198">100% means the index pages are completely full.</span></span> <span data-ttu-id="06b31-199">50% significa que, em média, cada página do índice está preenchida pela metade.</span><span class="sxs-lookup"><span data-stu-id="06b31-199">50% means that, on average, each index page is half full.</span></span>  
  
     <span data-ttu-id="06b31-200">**Fragmentação total**</span><span class="sxs-lookup"><span data-stu-id="06b31-200">**Total fragmentation**</span></span>  
     <span data-ttu-id="06b31-201">A porcentagem de fragmentação lógica.</span><span class="sxs-lookup"><span data-stu-id="06b31-201">The logical fragmentation percentage.</span></span> <span data-ttu-id="06b31-202">Isso indica o número de páginas em um índice que não estão armazenadas em ordem.</span><span class="sxs-lookup"><span data-stu-id="06b31-202">This indicates the number of pages in an index that are not stored in order.</span></span>  
  
     <span data-ttu-id="06b31-203">**Tamanho médio da linha**</span><span class="sxs-lookup"><span data-stu-id="06b31-203">**Average row size**</span></span>  
     <span data-ttu-id="06b31-204">O tamanho médio de uma linha de nível folha.</span><span class="sxs-lookup"><span data-stu-id="06b31-204">The average size of a leaf level row.</span></span>  
  
     <span data-ttu-id="06b31-205">**Depth**</span><span class="sxs-lookup"><span data-stu-id="06b31-205">**Depth**</span></span>  
     <span data-ttu-id="06b31-206">O número de níveis no índice, inclusive o nível folha.</span><span class="sxs-lookup"><span data-stu-id="06b31-206">The number of levels in the index, including the leaf level.</span></span>  
  
     <span data-ttu-id="06b31-207">**Registros encaminhados**</span><span class="sxs-lookup"><span data-stu-id="06b31-207">**Forwarded records**</span></span>  
     <span data-ttu-id="06b31-208">O número de registros em um heap com ponteiros encaminhados a outro local de dados</span><span class="sxs-lookup"><span data-stu-id="06b31-208">The number of records in a heap that have forward pointers to another data location.</span></span> <span data-ttu-id="06b31-209">(Esse estado ocorre durante uma atualização, quando não há espaço suficiente para armazenar a nova linha no local original.)</span><span class="sxs-lookup"><span data-stu-id="06b31-209">(This state occurs during an update, when there is not enough room to store the new row in the original location.)</span></span>  
  
     <span data-ttu-id="06b31-210">**Linhas fantasmas**</span><span class="sxs-lookup"><span data-stu-id="06b31-210">**Ghost rows**</span></span>  
     <span data-ttu-id="06b31-211">O número de linhas que estão marcadas como excluídas, mas ainda não foram removidas.</span><span class="sxs-lookup"><span data-stu-id="06b31-211">The number of rows that are marked as deleted but not yet removed.</span></span> <span data-ttu-id="06b31-212">Essas linhas serão removidas por um thread de limpeza, quando o servidor não estiver ocupado.</span><span class="sxs-lookup"><span data-stu-id="06b31-212">These rows will be removed by a clean-up thread, when the server is not busy.</span></span> <span data-ttu-id="06b31-213">Esse valor não inclui linhas que estejam sendo retidas devido a uma transação de isolamento de instantâneo pendente.</span><span class="sxs-lookup"><span data-stu-id="06b31-213">This value does not include rows that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
     <span data-ttu-id="06b31-214">**Tipo de índice**</span><span class="sxs-lookup"><span data-stu-id="06b31-214">**Index type**</span></span>  
     <span data-ttu-id="06b31-215">O tipo do índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-215">The type of index.</span></span> <span data-ttu-id="06b31-216">Os valores possíveis são **Índice cluster**, **Índice não cluster**e **XML Primário**.</span><span class="sxs-lookup"><span data-stu-id="06b31-216">Possible values are **Clustered index**, **Nonclustered index**, and **Primary XML**.</span></span> <span data-ttu-id="06b31-217">As tabelas também podem ser armazenadas como um heap (sem-índices), mas nesse caso a página Propriedades do Índice não pode ser aberta.</span><span class="sxs-lookup"><span data-stu-id="06b31-217">Tables can also be stored as a heap (without indexes), but then this Index Properties page cannot be opened.</span></span>  
  
     <span data-ttu-id="06b31-218">**Linhas em nível folha**</span><span class="sxs-lookup"><span data-stu-id="06b31-218">**Leaf-level rows**</span></span>  
     <span data-ttu-id="06b31-219">O número de linhas em nível folha.</span><span class="sxs-lookup"><span data-stu-id="06b31-219">The number of leaf level rows.</span></span>  
  
     <span data-ttu-id="06b31-220">**Tamanho máximo da linha**</span><span class="sxs-lookup"><span data-stu-id="06b31-220">**Maximum row size**</span></span>  
     <span data-ttu-id="06b31-221">O tamanho máximo da linha em nível folha.</span><span class="sxs-lookup"><span data-stu-id="06b31-221">The maximum leaf-level row size.</span></span>  
  
     <span data-ttu-id="06b31-222">**Tamanho mínimo da linha**</span><span class="sxs-lookup"><span data-stu-id="06b31-222">**Minimum row size**</span></span>  
     <span data-ttu-id="06b31-223">O tamanho mínimo da linha em nível folha.</span><span class="sxs-lookup"><span data-stu-id="06b31-223">The minimum leaf-level row size.</span></span>  
  
     <span data-ttu-id="06b31-224">**Páginas**</span><span class="sxs-lookup"><span data-stu-id="06b31-224">**Pages**</span></span>  
     <span data-ttu-id="06b31-225">O número total de páginas de dados.</span><span class="sxs-lookup"><span data-stu-id="06b31-225">The total number of data pages.</span></span>  
  
     <span data-ttu-id="06b31-226">**Identificação da Partição**</span><span class="sxs-lookup"><span data-stu-id="06b31-226">**Partition ID**</span></span>  
     <span data-ttu-id="06b31-227">A ID da partição da árvore b que contém o índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-227">The partition ID of the b-tree containing the index.</span></span>  
  
     <span data-ttu-id="06b31-228">**Linhas fantasmas de versão**</span><span class="sxs-lookup"><span data-stu-id="06b31-228">**Version ghost rows**</span></span>  
     <span data-ttu-id="06b31-229">O número de registros fantasmas que estão sendo retidos devido a uma transação de isolamento de instantâneo pendente.</span><span class="sxs-lookup"><span data-stu-id="06b31-229">The number of ghost records that are being retained due to an outstanding snapshot isolation transaction.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureFrag"></a> <span data-ttu-id="06b31-230">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06b31-230">Using Transact-SQL</span></span>  
  
#### <a name="to-check-the-fragmentation-of-an-index"></a><span data-ttu-id="06b31-231">Para verificar a fragmentação de um índice</span><span class="sxs-lookup"><span data-stu-id="06b31-231">To check the fragmentation of an index</span></span>  
  
1.  <span data-ttu-id="06b31-232">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06b31-232">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06b31-233">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="06b31-233">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06b31-234">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="06b31-234">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find the average fragmentation percentage of all indexes  
    -- in the HumanResources.Employee table.   
    SELECT a.index_id, name, avg_fragmentation_in_percent  
    FROM sys.dm_db_index_physical_stats (DB_ID(N'AdventureWorks2012'), OBJECT_ID(N'HumanResources.Employee'), NULL, NULL, NULL) AS a  
        JOIN sys.indexes AS b ON a.object_id = b.object_id AND a.index_id = b.index_id;   
    GO  
    ```  
  
     <span data-ttu-id="06b31-235">A instrução acima poderia retornar um conjunto de resultados semelhante ao que segue.</span><span class="sxs-lookup"><span data-stu-id="06b31-235">The statement above might return a result set similar to the following.</span></span>  
  
    ```  
    index_id    name                                                  avg_fragmentation_in_percent  
    ----------- ----------------------------------------------------- ----------------------------  
    1           PK_Employee_BusinessEntityID                          0  
    2           IX_Employee_OrganizationalNode                        0  
    3           IX_Employee_OrganizationalLevel_OrganizationalNode    0  
    5           AK_Employee_LoginID                                   66.6666666666667  
    6           AK_Employee_NationalIDNumber                          50  
    7           AK_Employee_rowguid                                   0  
  
    (6 row(s) affected)  
    ```  
  
 <span data-ttu-id="06b31-236">Para obter mais informações, consulte [Sys. dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06b31-236">For more information, see  [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedureReorg"></a> <span data-ttu-id="06b31-237">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="06b31-237">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-reorganize-or-rebuild-an-index"></a><span data-ttu-id="06b31-238">Para reorganizar ou recriar um índice</span><span class="sxs-lookup"><span data-stu-id="06b31-238">To reorganize or rebuild an index</span></span>  
  
1.  <span data-ttu-id="06b31-239">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja reorganizar um índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-239">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="06b31-240">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="06b31-240">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="06b31-241">Expanda a tabela na qual você deseja reorganizar um índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-241">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="06b31-242">Expanda a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="06b31-242">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="06b31-243">Clique com o botão direito do mouse no índice a ser reorganizado e selecione **Reorganizar**.</span><span class="sxs-lookup"><span data-stu-id="06b31-243">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="06b31-244">Na caixa de diálogo **Reorganizar Índices** , verifique se o índice correto está na grade **Índices a serem reorganizados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="06b31-244">In the **Reorganize Indexes** dialog box, verify that the correct index is in the **Indexes to be reorganized** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="06b31-245">Marque a caixa de seleção **Compactar dados de coluna de objeto grande** para especificar que todas as páginas que contêm dados de objeto grande (LOB) também sejam compactadas.</span><span class="sxs-lookup"><span data-stu-id="06b31-245">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="06b31-246">Clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="06b31-246">Click **OK.**</span></span>  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="06b31-247">Para reorganizar todos os índices de uma tabela</span><span class="sxs-lookup"><span data-stu-id="06b31-247">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="06b31-248">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja reorganizar os índices.</span><span class="sxs-lookup"><span data-stu-id="06b31-248">In Object Explorer, Expand the database that contains the table on which you want to reorganize the indexes.</span></span>  
  
2.  <span data-ttu-id="06b31-249">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="06b31-249">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="06b31-250">Expanda a tabela na qual você deseja reorganizar os índices.</span><span class="sxs-lookup"><span data-stu-id="06b31-250">Expand the table on which you want to reorganize the indexes.</span></span>  
  
4.  <span data-ttu-id="06b31-251">Clique com o botão direito do mouse na pasta **Índices** e selecione **Reorganizar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="06b31-251">Right-click the **Indexes** folder and select **Reorganize All**.</span></span>  
  
5.  <span data-ttu-id="06b31-252">Na caixa de diálogo **Reorganizar Índices** , verifique se os índices corretos estão na grade **Índices a serem reorganizados**e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="06b31-252">In the **Reorganize Indexes** dialog box, verify that the correct indexes are in the **Indexes to be reorganized**.</span></span> <span data-ttu-id="06b31-253">Para remover um índice da grade **Índices a serem reorganizados** , selecione o índice e pressione a tecla Delete.</span><span class="sxs-lookup"><span data-stu-id="06b31-253">To remove an index from the **Indexes to be reorganized** grid, select the index and then press the Delete key.</span></span>  
  
6.  <span data-ttu-id="06b31-254">Marque a caixa de seleção **Compactar dados de coluna de objeto grande** para especificar que todas as páginas que contêm dados de objeto grande (LOB) também sejam compactadas.</span><span class="sxs-lookup"><span data-stu-id="06b31-254">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
7.  <span data-ttu-id="06b31-255">Clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="06b31-255">Click **OK.**</span></span>  
  
#### <a name="to-rebuild-an-index"></a><span data-ttu-id="06b31-256">Para recriar um índice</span><span class="sxs-lookup"><span data-stu-id="06b31-256">To rebuild an index</span></span>  
  
1.  <span data-ttu-id="06b31-257">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja reorganizar um índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-257">In Object Explorer, Expand the database that contains the table on which you want to reorganize an index.</span></span>  
  
2.  <span data-ttu-id="06b31-258">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="06b31-258">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="06b31-259">Expanda a tabela na qual você deseja reorganizar um índice.</span><span class="sxs-lookup"><span data-stu-id="06b31-259">Expand the table on which you want to reorganize an index.</span></span>  
  
4.  <span data-ttu-id="06b31-260">Expanda a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="06b31-260">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="06b31-261">Clique com o botão direito do mouse no índice a ser reorganizado e selecione **Reorganizar**.</span><span class="sxs-lookup"><span data-stu-id="06b31-261">Right-click the index you want to reorganize and select **Reorganize**.</span></span>  
  
6.  <span data-ttu-id="06b31-262">Na caixa de diálogo **Recriar Índices** , verifique se o índice correto está na grade **Índices a serem recriados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="06b31-262">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to be rebuilt** grid and click **OK**.</span></span>  
  
7.  <span data-ttu-id="06b31-263">Marque a caixa de seleção **Compactar dados de coluna de objeto grande** para especificar que todas as páginas que contêm dados de objeto grande (LOB) também sejam compactadas.</span><span class="sxs-lookup"><span data-stu-id="06b31-263">Select the **Compact large object column data** check box to specify that all pages that contain large object (LOB) data are also compacted.</span></span>  
  
8.  <span data-ttu-id="06b31-264">Clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="06b31-264">Click **OK.**</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedureReorg"></a> <span data-ttu-id="06b31-265">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06b31-265">Using Transact-SQL</span></span>  
  
#### <a name="to-reorganize-a-defragmented-index"></a><span data-ttu-id="06b31-266">Para reorganizar um índice desfragmentado</span><span class="sxs-lookup"><span data-stu-id="06b31-266">To reorganize a defragmented index</span></span>  
  
1.  <span data-ttu-id="06b31-267">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06b31-267">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06b31-268">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="06b31-268">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06b31-269">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="06b31-269">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize the IX_Employee_OrganizationalLevel_OrganizationalNode index on the HumanResources.Employee table.   
  
    ALTER INDEX IX_Employee_OrganizationalLevel_OrganizationalNode ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-reorganize-all-indexes-in-a-table"></a><span data-ttu-id="06b31-270">Para reorganizar todos os índices de uma tabela</span><span class="sxs-lookup"><span data-stu-id="06b31-270">To reorganize all indexes in a table</span></span>  
  
1.  <span data-ttu-id="06b31-271">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06b31-271">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06b31-272">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="06b31-272">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06b31-273">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="06b31-273">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Reorganize all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    REORGANIZE ;   
    GO  
    ```  
  
#### <a name="to-rebuild-a-defragmented-index"></a><span data-ttu-id="06b31-274">Para recriar um índice desfragmentado</span><span class="sxs-lookup"><span data-stu-id="06b31-274">To rebuild a defragmented index</span></span>  
  
1.  <span data-ttu-id="06b31-275">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06b31-275">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06b31-276">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="06b31-276">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06b31-277">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="06b31-277">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="06b31-278">O exemplo recria um único índice na tabela `Employee` .</span><span class="sxs-lookup"><span data-stu-id="06b31-278">The example rebuilds a single index on the `Employee` table.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex1](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex1)]  
  
#### <a name="to-rebuild-all-indexes-in-a-table"></a><span data-ttu-id="06b31-279">Para recriar todos os índices de uma tabela</span><span class="sxs-lookup"><span data-stu-id="06b31-279">To rebuild all indexes in a table</span></span>  
  
1.  <span data-ttu-id="06b31-280">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06b31-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="06b31-281">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="06b31-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="06b31-282">Copie e cole o exemplo a seguir na consulta. O exemplo especifica a palavra-chave `ALL`.</span><span class="sxs-lookup"><span data-stu-id="06b31-282">Copy and paste the following example into the query The example specifies the keyword `ALL`.</span></span> <span data-ttu-id="06b31-283">Isso recria todos os índices associados à tabela.</span><span class="sxs-lookup"><span data-stu-id="06b31-283">This rebuilds all indexes associated with the table.</span></span> <span data-ttu-id="06b31-284">Três opções são especificadas.</span><span class="sxs-lookup"><span data-stu-id="06b31-284">Three options are specified.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="06b31-285">Para obter mais informações, consulte [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06b31-285">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b31-286">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="06b31-286">See Also</span></span>  
 [<span data-ttu-id="06b31-287">Práticas recomendadas de desfragmentação de índice do Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="06b31-287">Microsoft SQL Server 2000 Index Defragmentation Best Practices</span></span>](https://technet.microsoft.com/library/cc966523.aspx)  
  
  
