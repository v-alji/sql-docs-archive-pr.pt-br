---
title: Pesquisa semântica (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server]
- semantic search [SQL Server], overview
- statistical semantic search [SQL Server]
- statistical semantic search [SQL Server], overview
ms.assetid: cd8faa9d-07db-420d-93f4-a2ea7c974b97
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 91062864b77ba3c62a87d66b8ff93068f9c10c8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682206"
---
# <a name="semantic-search-sql-server"></a><span data-ttu-id="2c5a6-102">Pesquisa semântica (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2c5a6-102">Semantic Search (SQL Server)</span></span>
  <span data-ttu-id="2c5a6-103">A Pesquisa Semântica Estatística fornece uma profunda compreensão de documentos não estruturados armazenados em bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extraindo e indexando *frases-chave*estatisticamente relevantes.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-103">Statistical Semantic Search provides deep insight into unstructured documents stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases by extracting and indexing statistically relevant *key phrases*.</span></span> <span data-ttu-id="2c5a6-104">Portanto, essas frases-chave também são usadas para identificar e indexar *documentos semelhantes ou relacionados*.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-104">Then it also uses these key phrases to identify and index *documents that are similar or related*.</span></span>  
  
 <span data-ttu-id="2c5a6-105">Você consulta esses índices semânticos usando três funções de conjunto de linhas do Transact-SQL para recuperar os resultados como dados estruturados.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-105">You query these semantic indexes by using three Transact-SQL rowset functions to retrieve the results as structured data.</span></span>  
  
##  <a name="what-can-i-do-with-semantic-search"></a><a name="whatcanido"></a><span data-ttu-id="2c5a6-106">O que posso fazer com a pesquisa semântica?</span><span class="sxs-lookup"><span data-stu-id="2c5a6-106">What Can I Do with Semantic Search?</span></span>  
 <span data-ttu-id="2c5a6-107">A pesquisa semântica tem como base o recurso de pesquisa de texto completo existente no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas habilita novos cenários que ampliam as pesquisas de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-107">Semantic search builds upon the existing full-text search feature in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but enables new scenarios that extend beyond keyword searches.</span></span> <span data-ttu-id="2c5a6-108">Enquanto a pesquisa de texto completo permite que você consulte as *palavras* em um documento, a pesquisa semântica permite a consulta do *significado* do documento.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-108">While full-text search lets you query the *words* in a document, semantic search lets you query the *meaning* of the document.</span></span> <span data-ttu-id="2c5a6-109">Agora, as soluções possíveis incluem a extração automática de marcas, a descoberta de conteúdo relacionado e a navegação hierárquica por conteúdo semelhante.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-109">Solutions that are now possible include automatic tag extraction, related content discovery, and hierarchical navigation across similar content.</span></span> <span data-ttu-id="2c5a6-110">Por exemplo, você pode consultar o índice de frases-chave para criar a taxonomia para uma organização ou para um corpo de documentos.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-110">For example, you can query the index of key phrases to build the taxonomy for an organization, or for a corpus of documents.</span></span> <span data-ttu-id="2c5a6-111">Ou, você pode consultar o índice de similaridade do documento para identificar os currículos que correspondem a uma descrição do trabalho.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-111">Or, you can query the document similarity index to identify resumes that match a job description.</span></span>  
  
 <span data-ttu-id="2c5a6-112">Os exemplos a seguir demonstram os recursos da Pesquisa Semântica.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-112">The following examples demonstrate the capabilities of Semantic Search.</span></span>  
  
###  <a name="find-the-key-phrases-in-a-document"></a><a name="find1"></a><span data-ttu-id="2c5a6-113">Localizar as frases-chave em um documento</span><span class="sxs-lookup"><span data-stu-id="2c5a6-113">Find the Key Phrases in a Document</span></span>  
 <span data-ttu-id="2c5a6-114">A consulta a seguir obtém as frases-chave que foram identificadas no documento de exemplo.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-114">The following query gets the key phrases that were identified in the sample document.</span></span> <span data-ttu-id="2c5a6-115">Apresenta os resultados em ordem decrescente pela contagem que classifica a significância estatística de cada frase-chave.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-115">It presents the results in descending order by the score that ranks the statistical significance of each key phrase.</span></span> <span data-ttu-id="2c5a6-116">Essa consulta chama a função [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c5a6-116">This query calls the [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql) function.</span></span>  
  
```sql  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS Title, keyphrase, score  
    FROM SEMANTICKEYPHRASETABLE(Documents, *, @DocID)  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-similar-or-related-documents"></a><a name="find2"></a><span data-ttu-id="2c5a6-117">Localizar documentos semelhantes ou relacionados</span><span class="sxs-lookup"><span data-stu-id="2c5a6-117">Find Similar or Related Documents</span></span>  
 <span data-ttu-id="2c5a6-118">A consulta a seguir obtém os documentos que foram identificados como semelhantes ou relacionados ao documento de exemplo.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-118">The following query gets the documents that were identified as similar or related to the sample document.</span></span> <span data-ttu-id="2c5a6-119">Apresenta os resultados em ordem decrescente pela contagem que classifica a semelhança dos 2 documentos.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-119">It presents the results in descending order by the score that ranks the similarity of the 2 documents.</span></span> <span data-ttu-id="2c5a6-120">Essa consulta chama a função [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c5a6-120">This query calls the [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql) function.</span></span>  
  
```vb  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS SourceTitle, DocumentTitle AS MatchedTitle,  
        DocumentID, score  
    FROM SEMANTICSIMILARITYTABLE(Documents, *, @DocID)  
    INNER JOIN Documents ON DocumentID = matched_document_key  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-the-key-phrases-that-make-documents-similar-or-related"></a><a name="find3"></a><span data-ttu-id="2c5a6-121">Localizar as frases-chave que tornam os documentos semelhantes ou relacionados</span><span class="sxs-lookup"><span data-stu-id="2c5a6-121">Find the Key Phrases That Make Documents Similar or Related</span></span>  
 <span data-ttu-id="2c5a6-122">A consulta a seguir obtém as frases-chave que tornam os 2 documentos de exemplo semelhantes ou relacionados a outro documento.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-122">The following query gets the key phrases that make the 2 sample documents similar or related to one another.</span></span> <span data-ttu-id="2c5a6-123">Apresenta os resultados em ordem decrescente pela contagem que classifica o peso de cada frase-chave.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-123">It presents the results in descending order by the score that ranks the weight of each key phrase.</span></span> <span data-ttu-id="2c5a6-124">Essa consulta chama a função [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c5a6-124">This query calls the [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql) function.</span></span>  
  
```sql  
SET @SourceTitle = 'first.docx'  
SET @MatchedTitle = 'second.docx'  
  
SELECT @SourceDocID = DocumentID FROM Documents WHERE DocumentTitle = @SourceTitle  
SELECT @MatchedDocID = DocumentID FROM Documents WHERE DocumentTitle = @MatchedTitle  
  
SELECT @SourceTitle AS SourceTitle, @MatchedTitle AS MatchedTitle, keyphrase, score  
    FROM semanticsimilaritydetailstable(Documents, DocumentContent,  
        @SourceDocID, DocumentContent, @MatchedDocID)  
    ORDER BY score DESC  
  
```  
  
  
  
##  <a name="storing-documents-in-sql-server"></a><a name="store"></a><span data-ttu-id="2c5a6-125">Armazenando documentos no SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c5a6-125">Storing Documents in SQL Server</span></span>  
 <span data-ttu-id="2c5a6-126">Antes de você poder indexar documentos com Pesquisa Semântica, é preciso armazenar os documentos em um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c5a6-126">Before you can index documents with Semantic Search, you have to store the documents in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="2c5a6-127">O recurso FileTable no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] torna arquivos e documentos não estruturados objetos de primeira classe do banco de dados relacional.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-127">The FileTable feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] makes unstructured files and documents first-class citizens of the relational database.</span></span> <span data-ttu-id="2c5a6-128">Como resultado, os desenvolvedores de banco de dados podem manipular documentos junto com dados estruturados em operações baseadas em conjuntos Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-128">As a result, database developers can manipulate documents together with structured data in Transact-SQL set-based operations.</span></span>  
  
 <span data-ttu-id="2c5a6-129">Para obter mais informações sobre o recurso FileTable, veja [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2c5a6-129">For more information about the FileTable feature, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span> <span data-ttu-id="2c5a6-130">Para obter informações sobre o recurso FILESTREAM, que é outra opção para armazenar documentos no banco de dados, veja [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2c5a6-130">For information about the FILESTREAM feature, which is another option for storing documents in the database, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="2c5a6-131">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2c5a6-131">Related Tasks</span></span>  
 [<span data-ttu-id="2c5a6-132">Instalar e configurar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="2c5a6-132">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)  
 <span data-ttu-id="2c5a6-133">Descreve os pré-requisitos para a pesquisa semântica estatística e como instalá-los ou verificá-los.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-133">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
 [<span data-ttu-id="2c5a6-134">Habilitar a pesquisa semântica em tabelas e colunas</span><span class="sxs-lookup"><span data-stu-id="2c5a6-134">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)  
 <span data-ttu-id="2c5a6-135">Descreve como habilitar ou desabilitar a indexação semântica estatística em colunas selecionadas que contêm documentos ou texto.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-135">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 [<span data-ttu-id="2c5a6-136">Localizar frases chave em documentos com a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="2c5a6-136">Find Key Phrases in Documents with Semantic Search</span></span>](find-key-phrases-in-documents-with-semantic-search.md)  
 <span data-ttu-id="2c5a6-137">Descreve como localizar as frases chave em documentos ou colunas de texto configuradas para indexação semântica estatística.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-137">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="2c5a6-138">Localizar documentos semelhantes e relacionados com a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="2c5a6-138">Find Similar and Related Documents with Semantic Search</span></span>](find-similar-and-related-documents-with-semantic-search.md)  
 <span data-ttu-id="2c5a6-139">Descreve como localizar documentos ou valores de texto semelhantes ou relacionados, e informações sobre como eles são semelhantes ou relacionados, em colunas configuradas para indexação semântica estatística.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-139">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="2c5a6-140">Gerenciar e monitorar a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="2c5a6-140">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)  
 <span data-ttu-id="2c5a6-141">Descreve o processo de indexação semântica e as tarefas relacionadas a monitoramento e gerenciamento dos índices.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-141">Describes the process of semantic indexing and the tasks related to monitoring and managing the indexes.</span></span>  
  
##  <a name="related-content"></a><a name="relcontent"></a> <span data-ttu-id="2c5a6-142">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="2c5a6-142">Related Content</span></span>  
 [<span data-ttu-id="2c5a6-143">DDL, funções, procedimentos armazenados e exibições de pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="2c5a6-143">Semantic Search DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
 <span data-ttu-id="2c5a6-144">Lista as instruções Transact-SQL e os objetos de banco de dados do SQL Server adicionados ou alterados para oferecer suporte à pesquisa semântica estatística.</span><span class="sxs-lookup"><span data-stu-id="2c5a6-144">Lists the Transact-SQL statements and the SQL Server database objects added or changed to support statistical semantic search.</span></span>  
  
  
