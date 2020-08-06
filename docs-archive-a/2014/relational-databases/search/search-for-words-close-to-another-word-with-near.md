---
title: Pesquisar palavras perto de outra palavra com NEAR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- word searches [full-text search]
- NEAR option [full-text search]
- phrase searches [full-text search]
- proximity searches [full-text search]
- full-text search [SQL Server], proximity searches
- full-text queries [SQL Server], proximity
- queries [full-text search], proximity
ms.assetid: 87520646-4865-49ae-8790-f766b80a41f3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c2d187ea3ed951ac6f17eb4babc5f4f77451d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682210"
---
# <a name="search-for-words-close-to-another-word-with-near"></a><span data-ttu-id="d4bc0-102">Procurar palavras perto de outra palavra com NEAR</span><span class="sxs-lookup"><span data-stu-id="d4bc0-102">Search for Words Close to Another Word with NEAR</span></span>
  <span data-ttu-id="d4bc0-103">Você pode usar uma condição de proximidade (NEAR) em um predicado [CONTAINS](/sql/t-sql/queries/contains-transact-sql) ou uma função [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) para procurar palavras ou frases próximas umas das outras.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-103">You can use a proximity term (NEAR) in a [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate or [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) function to search for words or phrases near one another.</span></span> <span data-ttu-id="d4bc0-104">Você também pode especificar o número máximo de condições não relacionadas à pesquisa que separam a primeira e a última condição da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-104">You can also specify the maximum number of non-search terms that separate the first and last search terms.</span></span> <span data-ttu-id="d4bc0-105">Além disso, você pode pesquisar palavras ou frases em qualquer ordem, ou pode pesquisar palavras ou frases na ordem em que especificá-las.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-105">In addition, you can search for words or phrases in any order, or you can search for words and phrases in the order in which you specify them.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="d4bc0-106">dá suporte à [condição de proximidade genérica](#Generic_NEAR)anterior, que agora é preterida e a [condição de proximidade personalizada](#Custom_NEAR), que é nova no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4bc0-106">supports both the earlier [generic proximity term](#Generic_NEAR), which is now deprecated, and the [custom proximity term](#Custom_NEAR), which is new in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
##  <a name="the-custom-proximity-term"></a><a name="Custom_NEAR"></a><span data-ttu-id="d4bc0-107">A condição de proximidade personalizada</span><span class="sxs-lookup"><span data-stu-id="d4bc0-107">The Custom Proximity Term</span></span>  
 <span data-ttu-id="d4bc0-108">A condição de proximidade personalizada introduz os novos recursos a seguir:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-108">The custom proximity term introduces the following new capabilities:</span></span>  
  
-   <span data-ttu-id="d4bc0-109">Você pode especificar o número máximo de condições não relacionadas à pesquisa ou *distância máxima*que separa a primeira e o último critério de pesquisa para constituir uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-109">You can specify the maximum number of non-search terms, or *maximum distance*, that separates the first and last search terms in order to constitute a match.</span></span>  
  
-   <span data-ttu-id="d4bc0-110">Se você especificar o número máximo de condições, também poderá especificar as correspondências que contêm condições de pesquisa na ordem especificada.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-110">If you specify the maximum number of terms, you can also specify that matches must contain the search terms in the specified order.</span></span>  
  
 <span data-ttu-id="d4bc0-111">Para se qualificar como uma correspondência, uma cadeia de caracteres de texto deve:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-111">To qualify as a match, a string of text must:</span></span>  
  
-   <span data-ttu-id="d4bc0-112">Iniciar com uma das condições de pesquisa especificadas e terminar com uma das outras condições de pesquisa especificadas.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-112">Start with one of the specified search terms and end with the one of the other specified search terms.</span></span>  
  
-   <span data-ttu-id="d4bc0-113">Conter todas as condições de pesquisa especificadas.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-113">Contain all of the specified search terms.</span></span>  
  
-   <span data-ttu-id="d4bc0-114">O número de condições não relacionadas à pesquisa, incluindo palavras irrelevantes, que ocorre entre a primeira e a última condição de pesquisa deve ser menor ou igual à distância máxima, se especificado.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-114">The number of non-search terms, including stopwords, that occur between the first and last search terms must be less than or equal to the maximum distance, if specified.</span></span>  
  
 <span data-ttu-id="d4bc0-115">A sintaxe básica é:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-115">The basic syntax is:</span></span>  
  
 <span data-ttu-id="d4bc0-116">NEAR (</span><span class="sxs-lookup"><span data-stu-id="d4bc0-116">NEAR (</span></span>  
  
 <span data-ttu-id="d4bc0-117">{</span><span class="sxs-lookup"><span data-stu-id="d4bc0-117">{</span></span>  
  
 <span data-ttu-id="d4bc0-118">*search_term* [,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="d4bc0-118">*search_term* [ ,...*n* ]</span></span>  
  
 |  
  
 <span data-ttu-id="d4bc0-119">(*search_term* [,... *n* ]) [, <maximum_distance> [, <match_order>]]</span><span class="sxs-lookup"><span data-stu-id="d4bc0-119">(*search_term* [ ,...*n* ] ) [, <maximum_distance> [, <match_order> ] ]</span></span>  
  
 <span data-ttu-id="d4bc0-120">}</span><span class="sxs-lookup"><span data-stu-id="d4bc0-120">}</span></span>  
  
 <span data-ttu-id="d4bc0-121">)</span><span class="sxs-lookup"><span data-stu-id="d4bc0-121">)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4bc0-122">Para obter mais informações sobre a sintaxe <custom_proximity_term>, veja [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d4bc0-122">For more information about the <custom_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="d4bc0-123">Por exemplo, você pode procurar 'John' dentro de duas condições de 'Smith', da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-123">For example, you could search for 'John' within two terms of 'Smith', as follows:</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((John, Smith), 2)')  
```  
  
 <span data-ttu-id="d4bc0-124">Alguns exemplos de cadeias de caracteres que correspondem são "`John Jacob Smith`" e "`Smith, John`".</span><span class="sxs-lookup"><span data-stu-id="d4bc0-124">Some examples of strings that match are "`John Jacob Smith`" and "`Smith, John`".</span></span> <span data-ttu-id="d4bc0-125">A cadeia de caracteres "`John Jones knows Fred Smith`" contém três condições de intervenção não relacionadas à pesquisa, portanto, não é uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-125">The string "`John Jones knows Fred Smith`" contains three intervening non-search terms, so it is not a match.</span></span>  
  
 <span data-ttu-id="d4bc0-126">Para exigir que as condições sejam localizadas na ordem especificada, você deve alterar a condição de proximidade do exemplo para `NEAR((John, Smith),2, TRUE).` Dessa maneira, é possível procurar "`John`" dentro de duas condições de "`Smith`", mas somente quando "`John`" precede "`Smith`".</span><span class="sxs-lookup"><span data-stu-id="d4bc0-126">To require that the terms be found in the specified order, you would change the example proximity term to `NEAR((John, Smith),2, TRUE).` This searches for "`John`" within two terms of "`Smith`" but only when "`John`" precedes "`Smith`".</span></span> <span data-ttu-id="d4bc0-127">Em um idioma lido da esquerda para a direita, como o inglês, um exemplo de uma cadeia de caracteres correspondente é "`John Jacob Smith`".</span><span class="sxs-lookup"><span data-stu-id="d4bc0-127">In a language that reads from left to right, such as English, an example of a string that matches is "`John Jacob Smith`".</span></span>  
  
 <span data-ttu-id="d4bc0-128">Observe que, para um idioma que lê da direita para a esquerda, como árabe ou hebraico, o Mecanismo de texto completo aplica as condições especificadas em ordem invertida.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-128">Note that for a language that reads from right to left, such as Arabic or Hebrew, the Full-Text Engine applies the specified terms in reverse order.</span></span> <span data-ttu-id="d4bc0-129">Além disso, o Pesquisador de Objetos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] inverte automaticamente a ordem de exibição de palavras especificada em idiomas da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-129">Also, Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] automatically reverses the display order of words specified in right-to-left languages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4bc0-130">Para obter mais informações, consulte "[Considerações adicionais sobre pesquisas de proximidade](#Additional_Considerations)", posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-130">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="how-maximum-distance-is-measured"></a><span data-ttu-id="d4bc0-131">Como a distância máxima é medida</span><span class="sxs-lookup"><span data-stu-id="d4bc0-131">How Maximum Distance Is Measured</span></span>  
 <span data-ttu-id="d4bc0-132">Uma distância máxima específica, como 10 ou 25, determina quantas condições não relacionadas à pesquisa, inclusive palavras irrelevantes, podem ocorrer entre a primeira e a última condição de pesquisa em uma determinada cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-132">A specific maximum distance, such as 10 or 25, determines how many non-search terms, including stopwords, can occur between the first and last search terms in a given string.</span></span> <span data-ttu-id="d4bc0-133">Por exemplo, `NEAR((dogs, cats, "hunting mice"), 3)` retorna a linha a seguir na qual o número total de condições não relacionadas à pesquisa é três ("`enjoy`", "`but`" e "`avoid`"):</span><span class="sxs-lookup"><span data-stu-id="d4bc0-133">For example, `NEAR((dogs, cats, "hunting mice"), 3)` would return the following row, in which the total number of non-search terms is three ("`enjoy`", "`but`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="d4bc0-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="d4bc0-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span></span>  
  
 <span data-ttu-id="d4bc0-135">A mesma condição de proximidade não retorna a linha a seguir, porque a distância máxima é excedida pelas quatro condições não relacionadas à pesquisa ("`enjoy`", "`but`", "`usually`" e "`avoid`"):</span><span class="sxs-lookup"><span data-stu-id="d4bc0-135">The same proximity term would not return the following row, because the maximum distance is exceeded by the four non-search terms ("`enjoy`", "`but`", "`usually`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="d4bc0-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="d4bc0-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span></span>  
  
### <a name="combining-a-custom-proximity-term-with-other-terms"></a><span data-ttu-id="d4bc0-137">Combinando uma condição de proximidade personalizada com outras condições</span><span class="sxs-lookup"><span data-stu-id="d4bc0-137">Combining a Custom Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="d4bc0-138">Você pode combinar uma condição de proximidade personalizada com outras condições.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-138">You can combine a custom proximity term with some other terms.</span></span> <span data-ttu-id="d4bc0-139">Você pode usar AND (&), OR (|) ou AND NOT (&!) para combinar uma condição de proximidade personalizada com outra, uma condição simples ou uma condição de prefixo.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-139">You can use AND (&), OR (|), or AND NOT (&!) to combine a custom proximity term with another custom proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="d4bc0-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-140">For example:</span></span>  
  
-   <span data-ttu-id="d4bc0-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span><span class="sxs-lookup"><span data-stu-id="d4bc0-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span></span>  
  
-   <span data-ttu-id="d4bc0-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span><span class="sxs-lookup"><span data-stu-id="d4bc0-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span></span>  
  
-   <span data-ttu-id="d4bc0-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span><span class="sxs-lookup"><span data-stu-id="d4bc0-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span></span>  
  
-   <span data-ttu-id="d4bc0-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span><span class="sxs-lookup"><span data-stu-id="d4bc0-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span></span>  
  
-   <span data-ttu-id="d4bc0-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span><span class="sxs-lookup"><span data-stu-id="d4bc0-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span></span>  
  
 <span data-ttu-id="d4bc0-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-146">For example,</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((term1, term2), 5, TRUE) AND term3')  
```  
  
 <span data-ttu-id="d4bc0-147">Não é possível combinar uma condição de proximidade personalizada com uma condição de proximidade genérica (*Term1* perto de *Term2*), um termo de geração (ISABOUT...) ou um termo ponderado (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="d4bc0-147">You cannot combine a custom proximity term with a generic proximity term (*term1* NEAR *term2*), a generation term (ISABOUT ...), or a weighted term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-custom-proximity-term"></a><span data-ttu-id="d4bc0-148">Exemplo: usando a condição de proximidade personalizada</span><span class="sxs-lookup"><span data-stu-id="d4bc0-148">Example: Using the Custom Proximity Term</span></span>  
 <span data-ttu-id="d4bc0-149">O exemplo a seguir pesquisa a tabela `Production.Document` do banco de dados de exemplo `AdventureWorks2012` para todos os resumos de documento que contêm o palavra "reflector" no mesmo documento que a palavra "bracket".</span><span class="sxs-lookup"><span data-stu-id="d4bc0-149">The following example searches the `Production.Document` table of the `AdventureWorks2012` sample database for all document summaries that contain the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable   
INNER JOIN CONTAINSTABLE(Production.Document, Document,  
  'NEAR(bracket, reflector)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
WHERE KEY_TBL.RANK > 50  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  

  
##  <a name="additional-considerations-for-proximity-searches"></a><a name="Additional_Considerations"></a><span data-ttu-id="d4bc0-150">Considerações adicionais para pesquisas de proximidade</span><span class="sxs-lookup"><span data-stu-id="d4bc0-150">Additional Considerations for Proximity Searches</span></span>  
 <span data-ttu-id="d4bc0-151">Esta seção discute considerações que afetam pesquisas de proximidade genéricas e personalizadas:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-151">This section discusses consideration that affect both generic and custom proximity searches:</span></span>  
  
-   <span data-ttu-id="d4bc0-152">Sobrepondo ocorrências de condições de pesquisa</span><span class="sxs-lookup"><span data-stu-id="d4bc0-152">Overlapping occurrences of search terms</span></span>  
  
     <span data-ttu-id="d4bc0-153">Todas as pesquisas de proximidade sempre procuram somente ocorrências sem sobreposição.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-153">All proximity searches always look for only non-overlapping occurrences.</span></span> <span data-ttu-id="d4bc0-154">Sobrepor ocorrências de condições de pesquisa nunca se qualifica como correspondências.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-154">Overlapping occurrences of search terms never qualify as matches.</span></span> <span data-ttu-id="d4bc0-155">Por exemplo, considere a condição de proximidade a seguir, que pesquisa "`A`" e "`AA`" nesta ordem com uma distância máxima de dois termos:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-155">For example, consider the following proximity term, which searches "`A`" and "`AA`" in this order with a maximum distance of two terms:</span></span>  
  
    ```  
    CONTAINS(column_name, 'NEAR((A,AA),2, TRUE')  
    ```  
  
     <span data-ttu-id="d4bc0-156">As correspondências possíveis são "`AAA`", "`A.AA`" e "`A..AA`".</span><span class="sxs-lookup"><span data-stu-id="d4bc0-156">The possible matches are as "`AAA`", "`A.AA`", and "`A..AA`".</span></span> <span data-ttu-id="d4bc0-157">Linhas que contêm apenas "`AA`" não corresponderiam.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-157">Rows containing just "`AA`" would not match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d4bc0-158">Você pode especificar condições que sobrepõem, por exemplo, `NEAR("mountain bike", "bike trails")` ou `(NEAR(comfort*, comfortable), 5)`.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-158">You can specify terms that overlap, for example, `NEAR("mountain bike", "bike trails")` or `(NEAR(comfort*, comfortable), 5)`.</span></span> <span data-ttu-id="d4bc0-159">Especificar condições de sobreposição aumenta a complexidade da consulta aumentando as possíveis permutações de correspondência.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-159">Specifying a overlapping terms increases the complexity of the query by increasing the possible match permutations.</span></span> <span data-ttu-id="d4bc0-160">Se você especificar um número grande deste tipo de condições sobrepostas, a consulta poderá ficar sem recursos e falhar.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-160">If you specify a large number of such overlapping terms, the query can run out of resources and fail.</span></span> <span data-ttu-id="d4bc0-161">Se isto ocorrer, simplifique a consulta e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-161">If this occurs, simplify the query and try again.</span></span>  
  
-   <span data-ttu-id="d4bc0-162">O NEAR genérico e o NEAR personalizado (independentemente de uma distância máxima ter sido especificada) indicam a distância lógica entre condições, em vez de a distância absoluta entre elas.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-162">Both generic NEAR and custom NEAR (regardless of whether a maximum distance is specified) indicate the logical distance between terms, rather than the absolute distance between them.</span></span> <span data-ttu-id="d4bc0-163">Por exemplo, termos dentro de frases diferentes ou orações dentro de um parágrafo são tratadas de forma muito diferente dos termos na mesma frase ou oração, independentemente da proximidade real, supondo que eles estejam menos relacionados.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-163">For example, terms within different phrases or sentences within a paragraph are treated as farther apart than terms in the same phrase or sentence, regardless of their actual proximity, on the assumption that they are less related.</span></span> <span data-ttu-id="d4bc0-164">Da mesma forma, termos em parágrafos diferentes são tratados de forma muito mais diferente.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-164">Likewise, terms in different paragraphs are treated as being even farther apart.</span></span> <span data-ttu-id="d4bc0-165">Se uma correspondência ultrapassar o final de uma frase, parágrafo ou capítulo, o intervalo usado para classificar um documento será aumentado em 8, 128 ou 1024, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-165">If a match spans the end of a sentence, paragraph, or chapter, the gap used for ranking a document is increased by 8, 128, or 1024, respectively.</span></span>  
  
-   <span data-ttu-id="d4bc0-166">Impacto de condições de proximidade sobre a classificação pela função CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="d4bc0-166">Impact of proximity terms on ranking by the CONTAINSTABLE function</span></span>  
  
     <span data-ttu-id="d4bc0-167">Quando NEAR é usado na função CONTAINSTABLE, o número de ocorrências em um documento relativo a seu comprimento, assim como a distância entre a primeira e a última condição de pesquisa em cada uma das ocorrências afeta a posição de cada documento.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-167">When NEAR is used in the CONTAINSTABLE function, the number of hits in a document relative to its length as well as the distance between the first and last search terms in each of the hits affects the ranking of each document.</span></span> <span data-ttu-id="d4bc0-168">Para uma condição de proximidade genérica, se os termos de pesquisa correspondidos estiverem separados em >50 termos lógicos, a classificação retornada em um documento será 0.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-168">For a generic proximity term, if the matched search terms are >50 logical terms apart, the rank returned on a document is 0.</span></span> <span data-ttu-id="d4bc0-169">Para uma condição de proximidade personalizada que não especifica um valor inteiro como a distância máxima, um documento que só contém ocorrências cujo intervalo seja >100 termos lógicos receberá uma classificação de 0.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-169">For a custom proximity term that does not specify an integer as the maximum distance, a document that contains only hits whose gap is >100 logical terms will receive a ranking of 0.</span></span> <span data-ttu-id="d4bc0-170">Para obter mais informações sobre como classificar pesquisas de proximidade personalizada, veja [Limitar resultados da pesquisa com RANK](limit-search-results-with-rank.md).</span><span class="sxs-lookup"><span data-stu-id="d4bc0-170">For more information about ranking of custom proximity searches, see [Limit Search Results with RANK](limit-search-results-with-rank.md).</span></span>  
  
-   <span data-ttu-id="d4bc0-171">A opção **transformar palavras de ruído** do servidor</span><span class="sxs-lookup"><span data-stu-id="d4bc0-171">The **transform noise words** server option</span></span>  
  
     <span data-ttu-id="d4bc0-172">O valor de **transformar palavras de ruído** afetará como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trata palavras irrelevantes se elas forem especificadas em pesquisas de proximidade.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-172">The value of **transform noise words** impacts how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] treats stopwords if they are specified in proximity searches.</span></span> <span data-ttu-id="d4bc0-173">Para saber mais, veja [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="d4bc0-173">For more information, see [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span></span>  
  

  
##  <a name="the-deprecated-generic-proximity-term"></a><a name="Generic_NEAR"></a><span data-ttu-id="d4bc0-174">O termo de proximidade genérico preterido</span><span class="sxs-lookup"><span data-stu-id="d4bc0-174">The Deprecated Generic Proximity Term</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]<span data-ttu-id="d4bc0-175">Recomendamos que você use a [condição de proximidade personalizada](#Custom_NEAR).</span><span class="sxs-lookup"><span data-stu-id="d4bc0-175">We recommend that you use the [custom proximity term](#Custom_NEAR).</span></span>  
  
 <span data-ttu-id="d4bc0-176">Um termo de proximidade genérico indica que todos os termos de pesquisa especificados devem ocorrer em um documento para que uma correspondência seja retornada, independentemente do número de termos não relacionados à pesquisa (a *distância*) entre os termos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-176">A generic proximity term indicates that the specified search terms must all occur in a document for a match to be returned, regardless of the number of non-search terms (the *distance*) between the search terms.</span></span> <span data-ttu-id="d4bc0-177">A sintaxe básica é:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-177">The basic syntax is:</span></span>  
  
 <span data-ttu-id="d4bc0-178">{ *search_term* {Near | ~} *search_term* } [ ,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="d4bc0-178">{ *search_term* { NEAR | ~ } *search_term* } [ ,...*n* ]</span></span>  
  
 <span data-ttu-id="d4bc0-179">Por exemplo, nos exemplos a seguir, as palavras 'fox' e 'chicken' ambos devem aparecer, em qualquer ordem, para gerar uma correspondência:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-179">For example, in the following examples, the words 'fox' and 'chicken' must both appear, in either order, to produce a match:</span></span>  
  
-   `CONTAINS(column_name, 'fox NEAR chicken')`  
  
-   `CONTAINSTABLE(table_name, column_name, 'fox ~ chicken')`  
  
> [!NOTE]  
>  <span data-ttu-id="d4bc0-180">Para obter informações sobre a sintaxe <generic_proximity_term>, veja [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d4bc0-180">For information about the <generic_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="d4bc0-181">Para obter mais informações, consulte "[Considerações adicionais sobre pesquisas de proximidade](#Additional_Considerations)", posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-181">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="combining-a-generic-proximity-term-with-other-terms"></a><span data-ttu-id="d4bc0-182">Combinando uma condição de proximidade genérica com outras condições</span><span class="sxs-lookup"><span data-stu-id="d4bc0-182">Combining a Generic Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="d4bc0-183">Você pode usar AND (&), OR (|) ou AND NOT (&!) para combinar uma condição de proximidade genérica com outra, uma condição simples ou uma condição de prefixo.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-183">You can use AND (&), OR (|), or AND NOT (&!) to combine a generic proximity term with another generic proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="d4bc0-184">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-184">For example:</span></span>  
  
```  
CONTAINSTABLE (Production.ProductDescription,  
   Description,   
   '(light NEAR aluminum) OR  
   (lightweight NEAR aluminum)'  
)  
```  
  
 <span data-ttu-id="d4bc0-185">Não é possível combinar uma condição de proximidade genérica com uma condição de proximidade personalizada, como `NEAR((term1,term2),5)` , um termo ponderado (ISABOUT...) ou um termo de geração (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="d4bc0-185">You cannot combine a generic proximity term with a custom proximity term, such as `NEAR((term1,term2),5)`, a weighted term (ISABOUT ...), or a generational term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-generic-proximity-term"></a><span data-ttu-id="d4bc0-186">Exemplo: usando a condição de proximidade genérica</span><span class="sxs-lookup"><span data-stu-id="d4bc0-186">Example: Using the Generic Proximity Term</span></span>  
 <span data-ttu-id="d4bc0-187">O exemplo a seguir usa a condição de proximidade genérica para procurar o palavra "reflector" no mesmo documento que a palavra "bracket".</span><span class="sxs-lookup"><span data-stu-id="d4bc0-187">The following example uses the generic proximity term to search for the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable INNER JOIN  
  CONTAINSTABLE(Production.Document, Document,  
  '(reflector NEAR bracket)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  
 <span data-ttu-id="d4bc0-188">Observe que você também pode inverter as condições em CONTAINSTABLE e obterá o mesmo resultado:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-188">Notice that you can also reverse the terms in CONTAINSTABLE to get the same result:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(bracket NEAR reflector)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="d4bc0-189">É possível utilizar o caractere til (~) no lugar da palavra-chave NEAR na consulta anterior e obter os mesmos resultados:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-189">You can use the tilde character (~) in place of the NEAR keyword in the earlier query, and get the same results:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="d4bc0-190">É possível especificar mais de duas palavras ou frases nos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d4bc0-190">More than two words or phrases can be specified in the search conditions.</span></span> <span data-ttu-id="d4bc0-191">Por exemplo, é possível escrever:</span><span class="sxs-lookup"><span data-stu-id="d4bc0-191">For example, it is possible to write:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket ~ installation)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="d4bc0-192">Isso significa que "reflector" deve estar no mesmo documento que "bracket", e "bracket" deve estar no mesmo documento que "installation".</span><span class="sxs-lookup"><span data-stu-id="d4bc0-192">This means that "reflector" must be in the same document as "bracket", and "bracket" must be in the same document as "installation".</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="d4bc0-193">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4bc0-193">See Also</span></span>  
 <span data-ttu-id="d4bc0-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d4bc0-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="d4bc0-195">[Consulta com pesquisa de texto completo](query-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="d4bc0-195">[Query with Full-Text Search](query-with-full-text-search.md) </span></span>  
 [<span data-ttu-id="d4bc0-196">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d4bc0-196">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
