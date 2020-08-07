---
title: Pesquisa de semântica de DDL, funções, procedimentos armazenados e exibições | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], database objects
ms.assetid: 182f395f-3168-48a4-b723-ef4403544f9f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ce6c23f9a8ff1d0dac8986bf6b44c7725d4badc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682207"
---
# <a name="semantic-search-ddl-functions-stored-procedures-and-views"></a><span data-ttu-id="8a37d-102">Pesquisa de semântica DDL, funções, procedimentos armazenados e exibições</span><span class="sxs-lookup"><span data-stu-id="8a37d-102">Semantic Search DDL, Functions, Stored Procedures, and Views</span></span>
  <span data-ttu-id="8a37d-103">Lista as instruções Transact-SQL e os objetos de banco de dados que oferecem suporte à pesquisa semântica estatística no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a37d-103">Lists the Transact-SQL statements and the database objects that support statistical semantic search in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8a37d-104">Para obter a lista de instruções e objetos de banco de dados que dão suporte à pesquisa de texto completo, consulte [DDL, funções, procedimentos armazenados e exibições de pesquisa de texto completo](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="8a37d-104">For the list of statements and database objects that support full-text search, see [Full-Text Search DDL, Functions, Stored Procedures, and Views](../views/views.md).</span></span>  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> <span data-ttu-id="8a37d-105">Instruções DDL (linguagem de definição de dados) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8a37d-105">Transact-SQL Data Definition Language (DDL) Statements</span></span>  
  
|<span data-ttu-id="8a37d-106">Objeto</span><span class="sxs-lookup"><span data-stu-id="8a37d-106">Object</span></span>|<span data-ttu-id="8a37d-107">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8a37d-107">More Information</span></span>|  
|------------|----------------------|  
|[<span data-ttu-id="8a37d-108">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-108">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)|[<span data-ttu-id="8a37d-109">Habilitar a pesquisa semântica em tabelas e colunas</span><span class="sxs-lookup"><span data-stu-id="8a37d-109">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)|  
|[<span data-ttu-id="8a37d-110">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-110">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)|[<span data-ttu-id="8a37d-111">Habilitar a pesquisa semântica em tabelas e colunas</span><span class="sxs-lookup"><span data-stu-id="8a37d-111">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)|  
  
##  <a name="system-functions"></a><a name="func"></a> <span data-ttu-id="8a37d-112">Funções de sistema</span><span class="sxs-lookup"><span data-stu-id="8a37d-112">System Functions</span></span>  
  
|<span data-ttu-id="8a37d-113">Objeto</span><span class="sxs-lookup"><span data-stu-id="8a37d-113">Object</span></span>|<span data-ttu-id="8a37d-114">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8a37d-114">More Information</span></span>|  
|------------|----------------------|  
|[<span data-ttu-id="8a37d-115">semantickeyphrasetable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-115">semantickeyphrasetable &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql)|[<span data-ttu-id="8a37d-116">Localizar frases chave em documentos com a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-116">Find Key Phrases in Documents with Semantic Search</span></span>](find-key-phrases-in-documents-with-semantic-search.md)|  
|[<span data-ttu-id="8a37d-117">semanticsimilaritydetailstable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-117">semanticsimilaritydetailstable &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql)|[<span data-ttu-id="8a37d-118">Localizar documentos semelhantes e relacionados com a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-118">Find Similar and Related Documents with Semantic Search</span></span>](find-similar-and-related-documents-with-semantic-search.md)|  
|[<span data-ttu-id="8a37d-119">semanticsimilaritytable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-119">semanticsimilaritytable &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql)|[<span data-ttu-id="8a37d-120">Localizar documentos semelhantes e relacionados com a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-120">Find Similar and Related Documents with Semantic Search</span></span>](find-similar-and-related-documents-with-semantic-search.md)|  
  
##  <a name="system-metadata-functions"></a><a name="meta"></a> <span data-ttu-id="8a37d-121">Funções de metadados do sistema</span><span class="sxs-lookup"><span data-stu-id="8a37d-121">System Metadata Functions</span></span>  
  
|<span data-ttu-id="8a37d-122">Objeto</span><span class="sxs-lookup"><span data-stu-id="8a37d-122">Object</span></span>|<span data-ttu-id="8a37d-123">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8a37d-123">More Information</span></span>|  
|------------|----------------------|  
|[<span data-ttu-id="8a37d-124">COLUMNPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-124">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)|[<span data-ttu-id="8a37d-125">Habilitar a pesquisa semântica em tabelas e colunas</span><span class="sxs-lookup"><span data-stu-id="8a37d-125">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)|  
|[<span data-ttu-id="8a37d-126">DATABASEPROPERTYEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-126">DATABASEPROPERTYEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/databasepropertyex-transact-sql)|[<span data-ttu-id="8a37d-127">Habilitar a pesquisa semântica em tabelas e colunas</span><span class="sxs-lookup"><span data-stu-id="8a37d-127">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)|  
|[<span data-ttu-id="8a37d-128">FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-128">FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)|[<span data-ttu-id="8a37d-129">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-129">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)|  
|[<span data-ttu-id="8a37d-130">INDEXPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-130">INDEXPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/indexproperty-transact-sql)|[<span data-ttu-id="8a37d-131">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-131">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)|  
|[<span data-ttu-id="8a37d-132">OBJECTPROPERTYEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-132">OBJECTPROPERTYEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/objectproperty-transact-sql)|[<span data-ttu-id="8a37d-133">Habilitar a pesquisa semântica em tabelas e colunas</span><span class="sxs-lookup"><span data-stu-id="8a37d-133">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)|  
|[<span data-ttu-id="8a37d-134">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-134">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)|[<span data-ttu-id="8a37d-135">Instalar e configurar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-135">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)|  
  
##  <a name="system-stored-procedures"></a><a name="sproc"></a> <span data-ttu-id="8a37d-136">Procedimentos armazenados do sistema</span><span class="sxs-lookup"><span data-stu-id="8a37d-136">System Stored Procedures</span></span>  
  
|<span data-ttu-id="8a37d-137">Objeto</span><span class="sxs-lookup"><span data-stu-id="8a37d-137">Object</span></span>|<span data-ttu-id="8a37d-138">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8a37d-138">More Information</span></span>|  
|------------|----------------------|  
|[<span data-ttu-id="8a37d-139">sp_fulltext_semantic_register_language_statistics_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-139">sp_fulltext_semantic_register_language_statistics_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-register-language-statistics-db-transact-sql)|[<span data-ttu-id="8a37d-140">Instalar e configurar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-140">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)|  
|[<span data-ttu-id="8a37d-141">sp_fulltext_semantic_unregister_language_statistics_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-141">sp_fulltext_semantic_unregister_language_statistics_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-unregister-language-statistics-db-transact-sql)|[<span data-ttu-id="8a37d-142">Instalar e configurar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-142">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)|  
  
##  <a name="system-views---catalog-views"></a><a name="cv"></a> <span data-ttu-id="8a37d-143">Exibições do sistema – Exibições do catálogo</span><span class="sxs-lookup"><span data-stu-id="8a37d-143">System Views - Catalog Views</span></span>  
  
|<span data-ttu-id="8a37d-144">Objeto</span><span class="sxs-lookup"><span data-stu-id="8a37d-144">Object</span></span>|<span data-ttu-id="8a37d-145">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8a37d-145">More Information</span></span>|  
|------------|----------------------|  
|[<span data-ttu-id="8a37d-146">sys.fulltext_index_columns &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-146">sys.fulltext_index_columns &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql)|[<span data-ttu-id="8a37d-147">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-147">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)|  
|[<span data-ttu-id="8a37d-148">sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-148">sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql)|[<span data-ttu-id="8a37d-149">Instalar e configurar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-149">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)|  
|[<span data-ttu-id="8a37d-150">sys.fulltext_semantic_languages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-150">sys.fulltext_semantic_languages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql)|[<span data-ttu-id="8a37d-151">Instalar e configurar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-151">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)|  
  
##  <a name="system-views---dynamic-management-views"></a><a name="dmv"></a> <span data-ttu-id="8a37d-152">Exibições do sistema – Exibições de gerenciamento dinâmico</span><span class="sxs-lookup"><span data-stu-id="8a37d-152">System Views - Dynamic Management Views</span></span>  
  
|<span data-ttu-id="8a37d-153">Objeto</span><span class="sxs-lookup"><span data-stu-id="8a37d-153">Object</span></span>|<span data-ttu-id="8a37d-154">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8a37d-154">More Information</span></span>|  
|------------|----------------------|  
|[<span data-ttu-id="8a37d-155">sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-155">sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql)|[<span data-ttu-id="8a37d-156">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-156">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)|  
|[<span data-ttu-id="8a37d-157">sys.dm_fts_index_population &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-157">sys.dm_fts_index_population &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql)|[<span data-ttu-id="8a37d-158">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-158">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)|  
|[<span data-ttu-id="8a37d-159">sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a37d-159">sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql)|[<span data-ttu-id="8a37d-160">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-160">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)|  
  
## <a name="see-also"></a><span data-ttu-id="8a37d-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a37d-161">See Also</span></span>  
 [<span data-ttu-id="8a37d-162">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="8a37d-162">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)  
  
  