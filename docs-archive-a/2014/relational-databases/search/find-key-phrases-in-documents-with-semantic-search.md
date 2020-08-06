---
title: Localizar frases chave em documentos com pesquisa semântica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], key phrase queries
ms.assetid: 6ee3676e-ed5d-43ec-aeca-1eed78967111
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8388fb704bf13f44d025e6e32a1450d537f61832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679841"
---
# <a name="find-key-phrases-in-documents-with-semantic-search"></a><span data-ttu-id="d24f5-102">Localizar frases chave em documentos com pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="d24f5-102">Find Key Phrases in Documents with Semantic Search</span></span>
  <span data-ttu-id="d24f5-103">Descreve como localizar as frases chave em documentos ou colunas de texto configuradas para indexação semântica estatística.</span><span class="sxs-lookup"><span data-stu-id="d24f5-103">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-key-phrases-in-documents"></a><a name="BasicsQueryKey"></a><span data-ttu-id="d24f5-104">Localizando frases-chave em documentos</span><span class="sxs-lookup"><span data-stu-id="d24f5-104">Finding Key Phrases in Documents</span></span>  
  
###  <a name="how-to-find-the-key-phrases-in-documents-with-semantickeyphrasetable"></a><a name="howtofind"></a><span data-ttu-id="d24f5-105">Como: localizar as frases-chave em documentos com SEMANTICKEYPHRASETABLE</span><span class="sxs-lookup"><span data-stu-id="d24f5-105">How to: Find the Key Phrases in Documents with SEMANTICKEYPHRASETABLE</span></span>  
 <span data-ttu-id="d24f5-106">Para identificar as frases chave em documentos específicos, ou para identificar documentos que contêm frases chave específicas, veja a função [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d24f5-106">To identify the key phrases in specific documents, or to identify documents that contain specific key phrases, query the function [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
 <span data-ttu-id="d24f5-107">SEMANTICKEYPHRASETABLE retorna uma tabela com zero, uma ou mais linhas para essas frases-chave associadas às colunas da tabela especificada.</span><span class="sxs-lookup"><span data-stu-id="d24f5-107">SEMANTICKEYPHRASETABLE returns a table with zero, one, or more rows for those key phrases associated with columns in the specified table.</span></span> <span data-ttu-id="d24f5-108">Essa função de conjunto de linhas pode ser referenciada na cláusula FROM de uma instrução SELECT como se fosse um nome de tabela comum.</span><span class="sxs-lookup"><span data-stu-id="d24f5-108">This rowset function can be referenced in the FROM clause of a SELECT statement as if it were a regular table name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d24f5-109">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], somente palavras únicas são indexadas para pesquisa semântica; frases com várias palavras (ngrams) não são indexadas.</span><span class="sxs-lookup"><span data-stu-id="d24f5-109">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], only single words are indexed for semantic search; multi-word phrases (ngrams) are not indexed.</span></span> <span data-ttu-id="d24f5-110">Além disso, várias formas da mesma palavra são indexadas separadamente; por exemplo, "computador" e "computadores" são indexadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="d24f5-110">Also, various forms of the same word are indexed separately; for example, "computer" and "computers" are indexed separately.</span></span>  
  
 <span data-ttu-id="d24f5-111">Para obter informações detalhadas sobre os parâmetros exigidos pela função SEMANTICKEYPHRASETABLE, e sobre a tabela de resultados que ela retorna, veja [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d24f5-111">For detailed information about the parameters required by the SEMANTICKEYPHRASETABLE function, and about the table of results that it returns, see [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d24f5-112">As colunas de destino devem ter a indexação de texto completo e semântica habilitada.</span><span class="sxs-lookup"><span data-stu-id="d24f5-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-1-find-the-top-key-phrases-in-a-specific-document"></a><a name="HowToTopPhrases"></a><span data-ttu-id="d24f5-113">Exemplo 1: localizar as principais frases-chave em um documento específico</span><span class="sxs-lookup"><span data-stu-id="d24f5-113">Example 1: Find the Top Key Phrases in a Specific Document</span></span>  
 <span data-ttu-id="d24f5-114">O exemplo a seguir recupera as 10 principais frases-chave do documento especificado pela variável @DocumentId na coluna Document da tabela Production.Document do banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d24f5-114">The following example retrieves the top 10 key phrases from the document specified by the @DocumentId variable in the Document column of the Production.Document table of the AdventureWorks sample database.</span></span> <span data-ttu-id="d24f5-115">A variável @DocumentId representa um valor da coluna de chave do índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d24f5-115">The @DocumentId variable represents a value from the key column of the full-text index.</span></span>  
  
```sql  
SELECT TOP(10) KEYP_TBL.keyphrase  
FROM SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document,  
    @DocumentId  
    ) AS KEYP_TBL  
ORDER BY KEYP_TBL.score DESC;  
GO  
```  
  
 <span data-ttu-id="d24f5-116">A função **SEMANTICKEYPHRASETABLE** recupera esses resultados com eficácia usando uma busca de índice em vez de um exame de tabela.</span><span class="sxs-lookup"><span data-stu-id="d24f5-116">The **SEMANTICKEYPHRASETABLE** function retrieves these results efficiently by using an index seek instead of a table scan.</span></span>  
  
###  <a name="example-2-find-the-top-documents-that-contain-a-specific-key-phrase"></a><a name="HowToTopDocuments"></a><span data-ttu-id="d24f5-117">Exemplo 2: localizar os principais documentos que contêm uma frase-chave específica</span><span class="sxs-lookup"><span data-stu-id="d24f5-117">Example 2: Find the Top Documents that Contain a Specific Key Phrase</span></span>  
 <span data-ttu-id="d24f5-118">O exemplo a seguir recupera os 25 principais documentos que contêm a frase-chave "Bracket" da coluna Document da tabela Production.Document do banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d24f5-118">The following example retrieves the top 25 documents that contain the key phrase "Bracket" from the Document column of the Production.Document table of the AdventureWorks sample database.</span></span>  
  
```sql  
SELECT TOP (25) DOC_TBL.DocumentID, DOC_TBL.DocumentSummary  
FROM Production.Document AS DOC_TBL  
    INNER JOIN SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document  
    ) AS KEYP_TBL  
ON DOC_TBL.DocumentID = KEYP_TBL.document_key  
WHERE KEYP_TBL.keyphrase = 'Bracket'  
ORDER BY KEYP_TBL.Score DESC;  
GO  
```  
  
  
