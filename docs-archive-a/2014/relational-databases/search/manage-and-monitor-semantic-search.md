---
title: Gerenciar e monitorar a pesquisa semântica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], managing
- semantic search [SQL Server], monitoring
ms.assetid: eb5c3b29-da70-42aa-aa97-7d35a3f1eb98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16e3af1d37f177dfe6d4e0cb090e7b8b0a4988d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681497"
---
# <a name="manage-and-monitor-semantic-search"></a><span data-ttu-id="50da4-102">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="50da4-102">Manage and Monitor Semantic Search</span></span>
  <span data-ttu-id="50da4-103">Descreve o processo de indexação semântica e as tarefas relacionadas ao gerenciamento e monitoramento dos índices.</span><span class="sxs-lookup"><span data-stu-id="50da4-103">Describes the process of semantic indexing and the tasks related to managing and monitoring the indexes.</span></span>  
  
##  <a name="how-to-check-the-status-of-semantic-indexing"></a><a name="HowToMonitorStatus"></a><span data-ttu-id="50da4-104">Como verificar o status da indexação semântica</span><span class="sxs-lookup"><span data-stu-id="50da4-104">How To: Check the Status of Semantic Indexing</span></span>  
 <span data-ttu-id="50da4-105">**A primeira fase da indexação semântica está concluída?**</span><span class="sxs-lookup"><span data-stu-id="50da4-105">**Is the first phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="50da4-106">Consulte a exibição de gerenciamento dinâmico [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) e verifique as colunas **status** e **status_description**.</span><span class="sxs-lookup"><span data-stu-id="50da4-106">Query the dynamic management view, [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql), and check the **status** and **status_description** columns.</span></span>  
  
 <span data-ttu-id="50da4-107">A primeira fase da indexação inclui a população do índice de palavras-chave de texto completo e o índice de frases-chave semântico, além da extração de dados de similaridade de documentos.</span><span class="sxs-lookup"><span data-stu-id="50da4-107">The first phase of indexing includes the population of the full-text keyword index and the semantic key phrase index, as well as the extraction of document similarity data.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_index_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="50da4-108">**A segunda fase da indexação semântica está concluída?**</span><span class="sxs-lookup"><span data-stu-id="50da4-108">**Is the second phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="50da4-109">Consulte a exibição de gerenciamento dinâmico [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql) e verifique as colunas **status** e **status_description**.</span><span class="sxs-lookup"><span data-stu-id="50da4-109">Query the dynamic management view, [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql), and check the **status** and **status_description** columns..</span></span>  
  
 <span data-ttu-id="50da4-110">A segunda fase da indexação inclui a população do índice semântico de similaridade de documentos.</span><span class="sxs-lookup"><span data-stu-id="50da4-110">The second phase of indexing includes the population of the semantic document similarity index.</span></span>  
  
```wql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_semantic_similarity_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
##  <a name="how-to-check-the-size-of-the-semantic-indexes"></a><a name="HowToCheckSize"></a><span data-ttu-id="50da4-111">Como verificar o tamanho dos índices semânticos</span><span class="sxs-lookup"><span data-stu-id="50da4-111">How To: Check the Size of the Semantic Indexes</span></span>  
 <span data-ttu-id="50da4-112">**Qual é o tamanho lógico de um índice semântico de frases-chave ou um índice semântico de similaridade de documentos?**</span><span class="sxs-lookup"><span data-stu-id="50da4-112">**What is the logical size of a semantic key phrase index or a semantic document similarity index?**</span></span>  
 <span data-ttu-id="50da4-113">Consulte a exibição de gerenciamento dinâmico [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50da4-113">Query the dynamic management view, [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="50da4-114">O tamanho lógico é exibido em número de páginas de índice.</span><span class="sxs-lookup"><span data-stu-id="50da4-114">The logical size is displayed in number of index pages.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_db_fts_index_physical_stats WHERE object_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="50da4-115">**Qual é o tamanho total dos índices de texto completo e semântico para um catálogo de texto completo?**</span><span class="sxs-lookup"><span data-stu-id="50da4-115">**What is the total size of the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="50da4-116">Consulta a propriedade **IndexSize** da função de metadados [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50da4-116">Query the **IndexSize** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'IndexSize')  
GO  
```  
  
 <span data-ttu-id="50da4-117">**Quantos itens são indexados nos índices de texto completo e semântico para um catálogo de texto completo?**</span><span class="sxs-lookup"><span data-stu-id="50da4-117">**How many items are indexed in the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="50da4-118">Consulta a propriedade **ItemCount** da função de metadados [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50da4-118">Query the **ItemCount** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'ItemCount')  
GO  
```  
  
##  <a name="how-to-force-the-population-of-the-semantic-indexes"></a><a name="HowToForcePopulation"></a><span data-ttu-id="50da4-119">Como forçar a população dos índices semânticos</span><span class="sxs-lookup"><span data-stu-id="50da4-119">How To: Force the Population of the Semantic Indexes</span></span>  
 <span data-ttu-id="50da4-120">Você pode forçar a população de índices de texto completo e semânticos usando a cláusula START/STOP/PAUSE ou RESUME POPULATION com a mesma sintaxe e o comportamento descrito para índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="50da4-120">You can force the population of full-text and semantic indexes by using the START/STOP/PAUSE or RESUME POPULATION clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="50da4-121">Para obter mais informações, veja [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) e [Popular índices de texto completo](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="50da4-121">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) and [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="50da4-122">Como a indexação semântica é dependente da indexação de texto completo, os índices semânticos são populados apenas quando os índices de texto completo associados são populados.</span><span class="sxs-lookup"><span data-stu-id="50da4-122">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="50da4-123">**Exemplo: iniciar uma população completa de índices de texto completo e semânticos**</span><span class="sxs-lookup"><span data-stu-id="50da4-123">**Example: Start a full population of full-text and semantic indexes**</span></span>  
  
 <span data-ttu-id="50da4-124">O exemplo a seguir inicia a população completa de índices de texto completo e semânticos alterando um índice de texto completo existente na tabela **Production.Document** no banco de dados de exemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="50da4-124">The following example starts full population of both full-text and semantic indexes by altering an existing full-text index on the **Production.Document** table in the AdventureWorks2012 sample database.</span></span>  
  
```vb  
USE AdventureWorks2012  
GO  
  
ALTER FULLTEXT INDEX ON Production.Document  
    START FULL POPULATION  
GO  
```  
  
##  <a name="how-to-disable-or-re-enable-semantic-indexing"></a><a name="HowToDisableIndexing"></a><span data-ttu-id="50da4-125">Como desabilitar ou reabilitar a indexação semântica</span><span class="sxs-lookup"><span data-stu-id="50da4-125">How To: Disable or Re-enable Semantic Indexing</span></span>  
 <span data-ttu-id="50da4-126">Você pode habilitar ou desabilitar a indexação de texto completo ou semântica usando a cláusula ENABLE/DISABLE com a mesma sintaxe e o comportamento descrito para índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="50da4-126">You can enable or disable full-text or semantic indexing by using the ENABLE/DISABLE clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="50da4-127">Para obter mais informações, consulte [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="50da4-127">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="50da4-128">Quando a indexação semântica é desabilitada e suspensa, as consultas em dados semânticos continuam a funcionar com êxito e retornar dados previamente indexados.</span><span class="sxs-lookup"><span data-stu-id="50da4-128">When semantic indexing is disabled and suspended, queries over semantic data continue to work successfully and to return previously indexed data.</span></span> <span data-ttu-id="50da4-129">Esse comportamento não é consistente com o comportamento da Pesquisa de Texto Completo.</span><span class="sxs-lookup"><span data-stu-id="50da4-129">This behavior is not consistent with the behavior of Full-Text Search.</span></span>  
  
```sql  
-- To disable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name DISABLE  
GO  
  
-- To re-enable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name ENABLE  
GO  
```  
  
##  <a name="phases-of-semantic-indexing"></a><a name="SemanticIndexing"></a><span data-ttu-id="50da4-130">Fases de Indexação semântica</span><span class="sxs-lookup"><span data-stu-id="50da4-130">Phases of Semantic Indexing</span></span>  
 <span data-ttu-id="50da4-131">A Pesquisa Semântica indexa dois tipos de dados para cada coluna na qual está habilitada:</span><span class="sxs-lookup"><span data-stu-id="50da4-131">Semantic Search indexes two kinds of data for each column on which it is enabled:</span></span>  
  
1.  <span data-ttu-id="50da4-132">**Frases-chave**</span><span class="sxs-lookup"><span data-stu-id="50da4-132">**Key phrases**</span></span>  
  
2.  <span data-ttu-id="50da4-133">**Similaridade de documentos**</span><span class="sxs-lookup"><span data-stu-id="50da4-133">**Document similarity**</span></span>  
  
 <span data-ttu-id="50da4-134">A indexação semântica ocorre em duas fases, junto com a indexação de texto completo:</span><span class="sxs-lookup"><span data-stu-id="50da4-134">Semantic indexing occurs in two phases, in conjunction with full-text indexing:</span></span>  
  
1.  <span data-ttu-id="50da4-135">**Fase 1**.</span><span class="sxs-lookup"><span data-stu-id="50da4-135">**Phase 1**.</span></span> <span data-ttu-id="50da4-136">O índice de palavras-chave de texto completo e o índice de frases-chave semântico são populados ao mesmo tempo em paralelo.</span><span class="sxs-lookup"><span data-stu-id="50da4-136">The full-text keyword index and the semantic key phrase index are populated in parallel at the same time.</span></span> <span data-ttu-id="50da4-137">Os dados necessários para indexar a similaridade de documentos também são extraídos neste momento.</span><span class="sxs-lookup"><span data-stu-id="50da4-137">The data required to index document similarity is also extracted at this time.</span></span>  
  
2.  <span data-ttu-id="50da4-138">**Fase 2**.</span><span class="sxs-lookup"><span data-stu-id="50da4-138">**Phase 2**.</span></span> <span data-ttu-id="50da4-139">O índice semântico de similaridade de documentos é então populado.</span><span class="sxs-lookup"><span data-stu-id="50da4-139">The semantic document similarity index is then populated.</span></span> <span data-ttu-id="50da4-140">Esse índice depende de ambos os índices que foram populados na fase anterior.</span><span class="sxs-lookup"><span data-stu-id="50da4-140">This index depends on both indexes that were populated in the preceding phase.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-semantic-indexes-are-not-populated"></a><a name="ProblemNotPopulated"></a><span data-ttu-id="50da4-141">Problema: os índices semânticos não são populados</span><span class="sxs-lookup"><span data-stu-id="50da4-141">Problem: Semantic Indexes Are Not Populated</span></span>  
 <span data-ttu-id="50da4-142">**Os índices de texto completo associados estão populados?**</span><span class="sxs-lookup"><span data-stu-id="50da4-142">**Are the associated full-text indexes populated?**</span></span>  
 <span data-ttu-id="50da4-143">Como a indexação semântica é dependente da indexação de texto completo, os índices semânticos são populados apenas quando os índices de texto completo associados são populados.</span><span class="sxs-lookup"><span data-stu-id="50da4-143">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="50da4-144">**As pesquisas de texto completo e semântica estão instaladas e configuradas corretamente?**</span><span class="sxs-lookup"><span data-stu-id="50da4-144">**Are full-text search and semantic search properly installed and configured?**</span></span>  
 <span data-ttu-id="50da4-145">Para obter mais informações, veja [Instalar e configurar a pesquisa semântica](install-and-configure-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="50da4-145">For more information, see [Install and Configure Semantic Search](install-and-configure-semantic-search.md).</span></span>  
  
 <span data-ttu-id="50da4-146">**O serviço FDHOST não está disponível ou há outra condição que cause a falha da indexação de texto completo?**</span><span class="sxs-lookup"><span data-stu-id="50da4-146">**Is the FDHOST service not available, or is there another condition that would cause full-text indexing to fail?**</span></span>  
 <span data-ttu-id="50da4-147">Para obter mais informações, veja [Solucionar problemas na indexação de texto completo](troubleshoot-full-text-indexing.md).</span><span class="sxs-lookup"><span data-stu-id="50da4-147">For more information, see [Troubleshoot Full-Text Indexing](troubleshoot-full-text-indexing.md).</span></span>  
  
  
