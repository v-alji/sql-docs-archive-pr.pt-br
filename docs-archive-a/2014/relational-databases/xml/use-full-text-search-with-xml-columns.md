---
title: Usar a pesquisa de texto completo com colunas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml columns [full-text search]
- indexes [full-text search]
ms.assetid: 8096cfc6-1836-4ed5-a769-a5d63b137171
author: rothja
ms.author: jroth
ms.openlocfilehash: 2b6b23933fde6a09d043c7055b0daa7c07035cdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679729"
---
# <a name="use-full-text-search-with-xml-columns"></a><span data-ttu-id="1dd62-102">Usar a pesquisa de texto completo com colunas XML</span><span class="sxs-lookup"><span data-stu-id="1dd62-102">Use Full-Text Search with XML Columns</span></span>
  <span data-ttu-id="1dd62-103">É possível criar um índice de texto completo em colunas de XML que indexa o conteúdo dos valores de XML, mas ignora a marcação XML.</span><span class="sxs-lookup"><span data-stu-id="1dd62-103">You can create a full-text index on XML columns that indexes the content of the XML values, but ignores the XML markup.</span></span> <span data-ttu-id="1dd62-104">Marcas de elemento são usadas como limites do token.</span><span class="sxs-lookup"><span data-stu-id="1dd62-104">Element tags are used as token boundaries.</span></span> <span data-ttu-id="1dd62-105">Os seguintes itens são indexados:</span><span class="sxs-lookup"><span data-stu-id="1dd62-105">The following items are indexed:</span></span>  
  
-   <span data-ttu-id="1dd62-106">O conteúdo dos elementos XML.</span><span class="sxs-lookup"><span data-stu-id="1dd62-106">The content of XML elements.</span></span>  
  
-   <span data-ttu-id="1dd62-107">O conteúdo de atributos XML apenas do elemento de nível superior, a menos que esses valores sejam valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="1dd62-107">The content of XML attributes of the top-level element only, unless those values are numeric values.</span></span>  
  
 <span data-ttu-id="1dd62-108">Quando possível, você pode combinar pesquisa de texto completo com índice XML da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1dd62-108">When possible, you can combine full-text search with XML index in the following way:</span></span>  
  
1.  <span data-ttu-id="1dd62-109">Primeiro, filtre os valores de XML de interesse usando a pesquisa de texto completo do SQL.</span><span class="sxs-lookup"><span data-stu-id="1dd62-109">First, filter the XML values of interest by using SQL full-text search.</span></span>  
  
2.  <span data-ttu-id="1dd62-110">Em seguida, consulte esses valores de XML que usam o índice XML na coluna XML.</span><span class="sxs-lookup"><span data-stu-id="1dd62-110">Next, query those XML values that use XML index on the XML column.</span></span>  
  
## <a name="example-combining-full-text-search-with-xml-querying"></a><span data-ttu-id="1dd62-111">Exemplo: Combinando a pesquisa de texto completo com a Consulta XML</span><span class="sxs-lookup"><span data-stu-id="1dd62-111">Example: Combining Full-text Search with XML Querying</span></span>  
 <span data-ttu-id="1dd62-112">Após o índice de texto completo ter sido criado na coluna XML, a seguinte consulta verifica se um valor XML contém as palavras "custom" no título de um manual:</span><span class="sxs-lookup"><span data-stu-id="1dd62-112">After the full-text index has been created on the XML column, the following query checks that an XML value contains the word "custom" in the title of a book:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'custom')   
AND    xCol.exist('/book/title/text()[contains(.,"custom")]') =1  
```  
  
 <span data-ttu-id="1dd62-113">O método **contains()** usa o índice de texto completo para subdividir os valores de XML que contêm a palavra “custom” em qualquer lugar do documento.</span><span class="sxs-lookup"><span data-stu-id="1dd62-113">The **contains()** method uses the full-text index to subset the XML values that contain the word "custom" anywhere in the document.</span></span> <span data-ttu-id="1dd62-114">A cláusula **exist()** garante que a palavra “custom” ocorre no título de um manual.</span><span class="sxs-lookup"><span data-stu-id="1dd62-114">The **exist()** clause ensures that the word "custom" occurs in the title of a book.</span></span>  
  
 <span data-ttu-id="1dd62-115">Uma pesquisa de texto completo que usa **contains()** e **contains()** do XQuery tem semânticas diferentes.</span><span class="sxs-lookup"><span data-stu-id="1dd62-115">A full-text search that uses **contains()** and XQuery **contains()** has different semantics.</span></span> <span data-ttu-id="1dd62-116">O último é uma correspondência de subcadeia de caracteres e o anterior é uma correspondência de tokens que usa lematização.</span><span class="sxs-lookup"><span data-stu-id="1dd62-116">The latter is a substring match and the former is a token match that uses stemming.</span></span> <span data-ttu-id="1dd62-117">Portanto, se a pesquisa se destinar à cadeia de caracteres que contém “run” no título, as correspondências incluirão “run”, “runs” e “running”, porque tanto **contains()** quanto **contains()** do XQuery são atendidos.</span><span class="sxs-lookup"><span data-stu-id="1dd62-117">Therefore, if the search is for the string that has "run" in the title, the matches will include "run", "runs", and "running", because both the full-text **contains()** and the Xquery **contains()** are satisfied.</span></span> <span data-ttu-id="1dd62-118">No entanto, a consulta não corresponde à palavra “customizable” no título em que **contains()** de texto completo falha, mas **contains()** do XQuery é atendido.</span><span class="sxs-lookup"><span data-stu-id="1dd62-118">However, the query does not match the word "customizable" in the title in that the full-text **contains()** fails, but the Xquery **contains()** is satisfied.</span></span> <span data-ttu-id="1dd62-119">Geralmente, para a correspondência pura de subcadeia de caracteres, a cláusula **contains()** de texto completo deve ser removida.</span><span class="sxs-lookup"><span data-stu-id="1dd62-119">Generally, for pure substring match, the full-text **contains()** clause should be removed.</span></span>  
  
 <span data-ttu-id="1dd62-120">Além disso, a pesquisa de texto completo usa a lematização de palavras, mas **contains()** do XQuery é uma correspondência literal.</span><span class="sxs-lookup"><span data-stu-id="1dd62-120">Additionally, full-text search uses word stemming, but XQuery **contains()** is a literal match.</span></span> <span data-ttu-id="1dd62-121">Essa diferença é ilustrada no próximo exemplo.</span><span class="sxs-lookup"><span data-stu-id="1dd62-121">This difference is illustrated in the next example.</span></span>  
  
## <a name="example-full-text-search-on-xml-values-using-stemming"></a><span data-ttu-id="1dd62-122">Exemplo: Pesquisa de texto completo em valores de XML usando lematização</span><span class="sxs-lookup"><span data-stu-id="1dd62-122">Example: Full-text Search on XML Values Using Stemming</span></span>  
 <span data-ttu-id="1dd62-123">A verificação de **contains()** do XQuery executada no exemplo anterior, geralmente, não pode ser eliminada.</span><span class="sxs-lookup"><span data-stu-id="1dd62-123">The XQuery **contains()** check that was performed in the previous example generally cannot be eliminated.</span></span> <span data-ttu-id="1dd62-124">Considere esta consulta:</span><span class="sxs-lookup"><span data-stu-id="1dd62-124">Consider this query:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'run')   
```  
  
 <span data-ttu-id="1dd62-125">A palavra "ran" no documento corresponde à critério de pesquisa por causa da lematização.</span><span class="sxs-lookup"><span data-stu-id="1dd62-125">The word "ran" in the document matches the search condition because of stemming.</span></span> <span data-ttu-id="1dd62-126">Além disso, o contexto da pesquisa não é verificado usando XQuery.</span><span class="sxs-lookup"><span data-stu-id="1dd62-126">Additionally, the search context is not checked by using XQuery.</span></span>  
  
 <span data-ttu-id="1dd62-127">Quando o XML é decomposto em colunas relacionais usando AXSD que são indexadas por texto completo, as consultas XPath que ocorrem sobre a exibição em XML não executam pesquisa de texto completo nas tabelas subjacentes.</span><span class="sxs-lookup"><span data-stu-id="1dd62-127">When XML is decomposed into relational columns by using AXSD that are full-text indexed, XPath queries that occur over the XML view do not perform full-text search on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd62-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1dd62-128">See Also</span></span>  
 [<span data-ttu-id="1dd62-129">Índices XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1dd62-129">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
