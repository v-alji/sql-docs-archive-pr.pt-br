---
title: Localizar documentos semelhantes e relacionados com a pesquisa semântica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], document similarity queries
ms.assetid: 9f527883-031b-442f-8e95-24bc0151ecbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b11493b5b04fa9308e3afbe56176251225248338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583462"
---
# <a name="find-similar-and-related-documents-with-semantic-search"></a><span data-ttu-id="54bbd-102">Localizar documentos semelhantes e relacionados com a pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="54bbd-102">Find Similar and Related Documents with Semantic Search</span></span>
  <span data-ttu-id="54bbd-103">Descreve como localizar documentos ou valores de texto semelhantes ou relacionados, e informações sobre como eles são semelhantes ou relacionados, em colunas configuradas para indexação semântica estatística.</span><span class="sxs-lookup"><span data-stu-id="54bbd-103">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-similar-or-related-documents"></a><a name="BasicsQuerySimilar"></a><span data-ttu-id="54bbd-104">Localizando documentos semelhantes ou relacionados</span><span class="sxs-lookup"><span data-stu-id="54bbd-104">Finding Similar or Related Documents</span></span>  
  
###  <a name="how-to-find-similar-or-related-documents-with-semanticsimilaritytable"></a><a name="HowToQuerySimilar"></a><span data-ttu-id="54bbd-105">Como localizar documentos semelhantes ou relacionados com o SEMANTICSIMILARITYTABLE</span><span class="sxs-lookup"><span data-stu-id="54bbd-105">How To: Find Similar or Related Documents with SEMANTICSIMILARITYTABLE</span></span>  
 <span data-ttu-id="54bbd-106">Para identificar documentos semelhantes ou relacionados em uma coluna específica, consulte a função [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54bbd-106">To identify similar or related documents in a specific column, query the function [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
 <span data-ttu-id="54bbd-107">**SEMANTICSIMILARITYTABLE** retorna uma tabela de zero, uma ou mais linhas cujo conteúdo na coluna especificada é semanticamente semelhante ao documento especificado.</span><span class="sxs-lookup"><span data-stu-id="54bbd-107">**SEMANTICSIMILARITYTABLE** returns a table of zero, one, or more rows whose content in the specified column is semantically similar to the specified document.</span></span> <span data-ttu-id="54bbd-108">Essa função de conjunto de linhas pode ser referenciada na cláusula FROM de uma instrução SELECT como um nome de tabela normal.</span><span class="sxs-lookup"><span data-stu-id="54bbd-108">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="54bbd-109">Não é possível consultar documentos similares em colunas.</span><span class="sxs-lookup"><span data-stu-id="54bbd-109">You cannot query across columns for similar documents.</span></span> <span data-ttu-id="54bbd-110">A função **SEMANTICSIMILARITYTABLE** apenas recupera resultados da mesma coluna que a coluna de origem, identificada pelo argumento **source_key** .</span><span class="sxs-lookup"><span data-stu-id="54bbd-110">The **SEMANTICSIMILARITYTABLE** function only retrieves results from the same column as the source column, which is identified by the **source_key** argument.</span></span>  
  
 <span data-ttu-id="54bbd-111">Para obter informações detalhadas sobre os parâmetros exigidos pela função **SEMANTICSIMILARITYTABLE**, e sobre a tabela de resultados que ela retorna, veja [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54bbd-111">For detailed information about the parameters required by the **SEMANTICSIMILARITYTABLE** function, and about the table of results that it returns, see [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="54bbd-112">As colunas de destino devem ter a indexação de texto completo e semântica habilitada.</span><span class="sxs-lookup"><span data-stu-id="54bbd-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-documents-that-are-similar-to-another-document"></a><a name="HowToIdentifySimilar"></a><span data-ttu-id="54bbd-113">Exemplo: localizar os principais documentos semelhantes a outro documento</span><span class="sxs-lookup"><span data-stu-id="54bbd-113">Example: Find the Top Documents That Are Similar to Another Document</span></span>  
 <span data-ttu-id="54bbd-114">O exemplo a seguir recupera os 10 principais candidatos que são semelhantes ao candidato especificado pelo *@CandidateID* da tabela HumanResources. JobCandidate no banco de dados de exemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="54bbd-114">The following example retrieves the top 10 candidates who are similar to the candidate specified by *@CandidateID* from the HumanResources.JobCandidate table in the AdventureWorks2012 sample database.</span></span>  
  
```scr  
SELECT TOP(10) KEY_TBL.matched_document_key AS Candidate_ID  
FROM SEMANTICSIMILARITYTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume,  
    @CandidateID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
##  <a name="finding-information-about-how-documents-are-similar-or-related"></a><a name="BasicsQuerySimilarity"></a><span data-ttu-id="54bbd-115">Localizando informações sobre como os documentos são semelhantes ou relacionados</span><span class="sxs-lookup"><span data-stu-id="54bbd-115">Finding Information about How Documents Are Similar or Related</span></span>  
  
###  <a name="how-to-find-information-about-how-documents-are-similar-or-related-with-semanticsimilaritydetailstable"></a><a name="HowToQuerySimilarity"></a><span data-ttu-id="54bbd-116">Como encontrar informações sobre como os documentos são semelhantes ou relacionados ao SEMANTICSIMILARITYDETAILSTABLE</span><span class="sxs-lookup"><span data-stu-id="54bbd-116">How To: Find Information about How Documents Are Similar or Related with SEMANTICSIMILARITYDETAILSTABLE</span></span>  
 <span data-ttu-id="54bbd-117">Para obter informações sobre as frases-chave que tornam documentos semelhantes ou relacionados, consulte a função [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54bbd-117">To get information about the key phrases that make documents similar or related, you can query the function [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
 <span data-ttu-id="54bbd-118">**SEMANTICSIMILARITYDETAILSTABLE** retorna uma tabela de zero, uma ou mais linhas de frases-chave comuns entre dois documentos (um documento de origem e um documento correspondente) cujo conteúdo é semanticamente semelhante.</span><span class="sxs-lookup"><span data-stu-id="54bbd-118">**SEMANTICSIMILARITYDETAILSTABLE** returns a table of zero, one, or more rows of key phrases common across two documents (a source document and a matched document) whose content is semantically similar.</span></span> <span data-ttu-id="54bbd-119">Essa função de conjunto de linhas pode ser referenciada na cláusula FROM de uma instrução SELECT como um nome de tabela normal.</span><span class="sxs-lookup"><span data-stu-id="54bbd-119">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="54bbd-120">Para obter informações detalhadas sobre os parâmetros exigidos pela função **SEMANTICSIMILARITYDETAILSTABLE** e sobre a tabela de resultados que ela retorna, veja [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54bbd-120">For detailed information about the parameters required by the **SEMANTICSIMILARITYDETAILSTABLE** function, and about the table of results that it returns, see [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="54bbd-121">As colunas de destino devem ter a indexação de texto completo e semântica habilitada.</span><span class="sxs-lookup"><span data-stu-id="54bbd-121">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-key-phrases-that-are-similar-between-documents"></a><a name="HowToSimilarPhrases"></a><span data-ttu-id="54bbd-122">Exemplo: localizar as principais frases-chave que são semelhantes entre os documentos</span><span class="sxs-lookup"><span data-stu-id="54bbd-122">Example: Find the Top Key Phrases That Are Similar between Documents</span></span>  
 <span data-ttu-id="54bbd-123">O exemplo a seguir recupera as cinco frases-chave com a pontuação de similaridade mais alta entre os candidatos especificados na tabela **HumanResources.JobCandidate** do banco de dados de exemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="54bbd-123">The following example retrieves the 5 key phrases that have the highest similarity score between the specified candidates in **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span>  
  
```sql  
SELECT TOP(5) KEY_TBL.keyphrase, KEY_TBL.score  
FROM SEMANTICSIMILARITYDETAILSTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume, @CandidateID,  
    Resume, @MatchedID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
  
