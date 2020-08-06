---
title: Limitar os resultados da pesquisa com RANK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- row ranking [full-text search]
- relevance ranking values [full-text search]
- full-text search [SQL Server], rankings
- index rankings [full-text search]
- ranked results [full-text search]
- rankings [full-text search]
- per-row rank values [full-text search]
ms.assetid: 06a776e6-296c-4ec7-9fa5-0794709ccb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab1b930b3238cb541965e1984d1561f1a1c22d87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681504"
---
# <a name="limit-search-results-with-rank"></a><span data-ttu-id="bd91d-102">Limite resultados de pesquisa com RANK</span><span class="sxs-lookup"><span data-stu-id="bd91d-102">Limit Search Results with RANK</span></span>
  <span data-ttu-id="bd91d-103">As funções [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) e [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) retornam uma coluna denominada RANK que contém valores ordinais de 0 a 1000 (valores de classificação).</span><span class="sxs-lookup"><span data-stu-id="bd91d-103">The [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) and [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) functions return a column named RANK that contains ordinal values from 0 through 1000 (rank values).</span></span> <span data-ttu-id="bd91d-104">Esses valores são usados para classificar as linhas retornadas de acordo com o grau de correspondência com os critérios de seleção.</span><span class="sxs-lookup"><span data-stu-id="bd91d-104">These values are used to rank the rows returned according to how well they match the selection criteria.</span></span> <span data-ttu-id="bd91d-105">Os valores de classificação indicam apenas uma ordem relativa de relevância das linhas no conjunto de resultados, sendo que um valor inferior indica menor relevância.</span><span class="sxs-lookup"><span data-stu-id="bd91d-105">The rank values indicate only a relative order of relevance of the rows in the result set, with a lower value indicating lower relevance.</span></span> <span data-ttu-id="bd91d-106">Os valores reais não são importantes e geralmente são diferentes em cada execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="bd91d-106">The actual values are unimportant and typically differ each time the query is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd91d-107">Os predicados CONTAINS e FREETEXT não retornam valores de classificação.</span><span class="sxs-lookup"><span data-stu-id="bd91d-107">The CONTAINS and FREETEXT predicates do not return any rank values.</span></span>  
  
 <span data-ttu-id="bd91d-108">O número de itens que correspondem a uma condição de pesquisa geralmente é muito grande.</span><span class="sxs-lookup"><span data-stu-id="bd91d-108">The number of items matching a search condition is often very large.</span></span> <span data-ttu-id="bd91d-109">Para impedir que as consultas CONTAINSTABLE ou FREETEXTTABLE retornem muitas correspondências, use o parâmetro *top_n_by_rank* opcional, que retorna apenas um subconjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-109">To prevent CONTAINSTABLE or FREETEXTTABLE queries from returning too many matches, use the optional *top_n_by_rank* parameter, which returns only a subset of rows.</span></span> <span data-ttu-id="bd91d-110">*top_n_by_rank* é um valor inteiro, *n*, que especifica que somente as *n* correspondências com classificação mais alta sejam retornadas, em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="bd91d-110">*top_n_by_rank* is an integer value, *n*, that specifies that only the *n* highest ranked matches are to be returned, in descending order.</span></span> <span data-ttu-id="bd91d-111">Se *top_n_by_rank* for combinado com outros parâmetros, a consulta retornará menos linhas do que o número de linhas que corresponde de fato a todos os predicados.</span><span class="sxs-lookup"><span data-stu-id="bd91d-111">If *top_n_by_rank* is combined with other parameters, the query could return fewer rows than the number of rows that actually match all the predicates.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="bd91d-112">ordena as correspondências por classificação e retorna somente o número especificado de linhas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-112">orders the matches by rank and returns only up to the specified number of rows.</span></span> <span data-ttu-id="bd91d-113">Essa opção pode resultar em um aumento significativo no desempenho.</span><span class="sxs-lookup"><span data-stu-id="bd91d-113">This choice can result in a dramatic increase in performance.</span></span> <span data-ttu-id="bd91d-114">Por exemplo, uma consulta que normalmente retornaria 100.000 linhas de uma tabela de um milhão de linhas será processada com muito mais rapidez se apenas as 100 primeiras linhas forem solicitadas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-114">For example, a query that would normally return 100,000 rows from a table of one million rows are processed more quickly if only the top 100 rows are requested.</span></span>  
  
##  <a name="examples-of-using-rank-to-limit-search-results"></a><a name="examples"></a> <span data-ttu-id="bd91d-115">Exemplos do uso de RANK para limitar os resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="bd91d-115">Examples of Using RANK to Limit Search Results</span></span>  
  
### <a name="example-a-searching-for-only-the-top-three-matches"></a><span data-ttu-id="bd91d-116">Exemplo A: Pesquisando apenas as três primeiras correspondências</span><span class="sxs-lookup"><span data-stu-id="bd91d-116">Example A: Searching for only the top three matches</span></span>  
 <span data-ttu-id="bd91d-117">O exemplo a seguir usa CONTAINSTABLE para retornar apenas as três primeiras correspondências.</span><span class="sxs-lookup"><span data-stu-id="bd91d-117">The following example uses CONTAINSTABLE to return only the top three matches.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT K.RANK, AddressLine1, City  
FROM Person.Address AS A  
  INNER JOIN  
  CONTAINSTABLE(Person.Address, AddressLine1, 'ISABOUT ("des*",  
    Rue WEIGHT(0.5),  
    Bouchers WEIGHT(0.9))',  
    3) AS K  
  ON A.AddressID = K.[KEY]  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
RANK        Address                          City  
----------- -------------------------------- ------------------------------  
172         9005, rue des Bouchers           Paris  
172         5, rue des Bouchers              Orleans  
172         5, rue des Bouchers              Metz  
  
(3 row(s) affected)  
```  
  
  
### <a name="example-b-searching-for-the-top-ten-matches"></a><span data-ttu-id="bd91d-118">Exemplo B: Pesquisando apenas as dez primeiras correspondências</span><span class="sxs-lookup"><span data-stu-id="bd91d-118">Example B: Searching for the top ten matches</span></span>  
 <span data-ttu-id="bd91d-119">O exemplo a seguir usa CONTAINSTABLE para retornar a descrição dos 5 produtos principais onde a coluna `Description` contém a palavra "aluminum" próxima à palavra "light" ou "lightweight".</span><span class="sxs-lookup"><span data-stu-id="bd91d-119">The following example uses CONTAINSTABLE to return the description of the top 5 products where the `Description` column contains the word "aluminum" near either the word "light" or the word "lightweight".</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT FT_TBL.ProductDescriptionID,  
   FT_TBL.Description,   
   KEY_TBL.RANK  
FROM Production.ProductDescription AS FT_TBL INNER JOIN  
   CONTAINSTABLE (Production.ProductDescription,  
      Description,   
      '(light NEAR aluminum) OR  
      (lightweight NEAR aluminum)',  
      5  
   ) AS KEY_TBL  
   ON FT_TBL.ProductDescriptionID = KEY_TBL.[KEY]  
GO  
```  
  
  
##  <a name="how-search-query-results-are-ranked"></a><a name="how"></a> <span data-ttu-id="bd91d-120">Como os resultados de consultas de pesquisa são classificados</span><span class="sxs-lookup"><span data-stu-id="bd91d-120">How Search Query Results Are Ranked</span></span>  
 <span data-ttu-id="bd91d-121">A pesquisa de texto completo no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pode gerar uma pontuação (ou valor de classificação) opcional que indica a relevância dos dados retornados por uma consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="bd91d-121">Full-text search in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can generate an optional score (or rank value) that indicates the relevance of the data returned by a full-text query.</span></span> <span data-ttu-id="bd91d-122">Este valor de classificação é calculado para cada linha e pode ser usado como critério de ordenação para classificar o conjunto de resultados de uma determinada consulta por relevância.</span><span class="sxs-lookup"><span data-stu-id="bd91d-122">This rank value is calculated on every row and can be used as an ordering criteria to sort the result set of a given query by relevance.</span></span> <span data-ttu-id="bd91d-123">Os valores de classificação indicam apenas uma ordem relativa de relevância das linhas do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="bd91d-123">The rank values indicate only a relative order of relevance of the rows in the result set.</span></span> <span data-ttu-id="bd91d-124">Os valores reais não são importantes e geralmente são diferentes em cada execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="bd91d-124">The actual values are unimportant and typically differ each time the query is run.</span></span> <span data-ttu-id="bd91d-125">O valor de classificação não guarda nenhuma importância entre as consultas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-125">The rank value does not hold any significance across queries.</span></span>  
  
### <a name="statistics-for-ranking"></a><span data-ttu-id="bd91d-126">Estatísticas para a classificação</span><span class="sxs-lookup"><span data-stu-id="bd91d-126">Statistics for Ranking</span></span>  
 <span data-ttu-id="bd91d-127">Quando um índice é criado, as estatísticas são coletadas para serem usadas na classificação.</span><span class="sxs-lookup"><span data-stu-id="bd91d-127">When an index is built, statistics are collected for use in ranking.</span></span> <span data-ttu-id="bd91d-128">O processo de construir um catálogo de texto completo não resulta diretamente em uma única estrutura de índice.</span><span class="sxs-lookup"><span data-stu-id="bd91d-128">The process of building a full-text catalog does not directly result in a single index structure.</span></span> <span data-ttu-id="bd91d-129">Em vez disso, o Mecanismo de Texto Completo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cria índices intermediários conforme os dados são indexados.</span><span class="sxs-lookup"><span data-stu-id="bd91d-129">Instead, the Full-Text Engine for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] creates intermediate indexes as data is indexed.</span></span> <span data-ttu-id="bd91d-130">O Mecanismo de Texto Completo então mescla esses índices em um índice maior, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="bd91d-130">The Full-Text Engine then merges these indexes into a larger index as needed.</span></span> <span data-ttu-id="bd91d-131">Este processo pode ser repetido muitas vezes.</span><span class="sxs-lookup"><span data-stu-id="bd91d-131">This process can be repeated many times.</span></span> <span data-ttu-id="bd91d-132">Em seguida, o Mecanismo de Texto Completo conduz uma "mesclagem mestra" que combina todos os índices intermediários em um grande índice mestre.</span><span class="sxs-lookup"><span data-stu-id="bd91d-132">The Full-Text Engine then conducts a "master merge" that combines all of the intermediate indexes into one large master index.</span></span>  
  
 <span data-ttu-id="bd91d-133">As estatísticas são coletadas a cada nível de índice intermediário.</span><span class="sxs-lookup"><span data-stu-id="bd91d-133">Statistics are collected at each intermediate index level.</span></span> <span data-ttu-id="bd91d-134">As estatísticas são mescladas quando os índices são mesclados.</span><span class="sxs-lookup"><span data-stu-id="bd91d-134">The statistics are merged when the indexes are merged.</span></span> <span data-ttu-id="bd91d-135">Alguns valores estatísticos só podem ser gerados durante o processo de mesclagem mestra.</span><span class="sxs-lookup"><span data-stu-id="bd91d-135">Some statistical values can only be generated during the master merging process.</span></span>  
  
 <span data-ttu-id="bd91d-136">Ao classificar um conjunto de resultados da consulta, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usa estatísticas do índice intermediário maior.</span><span class="sxs-lookup"><span data-stu-id="bd91d-136">While ranking a query result set, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses statistics from the largest intermediate index.</span></span> <span data-ttu-id="bd91d-137">Isto depende se os índices intermediários foram mesclados ou não.</span><span class="sxs-lookup"><span data-stu-id="bd91d-137">This depends on whether intermediate indexes have been merged or not.</span></span> <span data-ttu-id="bd91d-138">Como resultado, as estatísticas de classificação poderão variar em precisão se os índices intermediários tiverem sido mesclados.</span><span class="sxs-lookup"><span data-stu-id="bd91d-138">As a result, ranking statistics can vary in accuracy if the intermediate indexes have not been merged.</span></span> <span data-ttu-id="bd91d-139">Isto explica porque a mesma consulta pode retornar diferentes resultados de classificação no decorrer do tempo conforme os dados indexados do texto completo são adicionados, modificados e excluídos; e conforme os índices menores são mesclados.</span><span class="sxs-lookup"><span data-stu-id="bd91d-139">This explains why the same query can return different rank results over time as full-text indexed data is added, modified, and deleted, and as the smaller indexes are merged.</span></span>  
  
 <span data-ttu-id="bd91d-140">Para minimizar o tamanho do índice e a complexidade computacional, as estatísticas são sempre arredondadas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-140">To minimize the size of the index and computational complexity, statistics are often rounded.</span></span>  
  
 <span data-ttu-id="bd91d-141">A lista a seguir inclui alguns termos usados comumente e os valores estatísticos que são importantes para a classificação.</span><span class="sxs-lookup"><span data-stu-id="bd91d-141">The list below includes some commonly used terms and statistical values that are important in calculating rank.</span></span>  
  
 <span data-ttu-id="bd91d-142">Propriedade</span><span class="sxs-lookup"><span data-stu-id="bd91d-142">Property</span></span>  
 <span data-ttu-id="bd91d-143">Uma coluna indexada de texto completo da linha.</span><span class="sxs-lookup"><span data-stu-id="bd91d-143">A full-text indexed column of the row.</span></span>  
  
 <span data-ttu-id="bd91d-144">Document</span><span class="sxs-lookup"><span data-stu-id="bd91d-144">Document</span></span>  
 <span data-ttu-id="bd91d-145">A entidade retornada em consultas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-145">The entity that is returned in queries.</span></span> <span data-ttu-id="bd91d-146">Em [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] isso corresponde a uma linha.</span><span class="sxs-lookup"><span data-stu-id="bd91d-146">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] this corresponds to a row.</span></span> <span data-ttu-id="bd91d-147">Um documento pode ter diversas propriedades, assim como uma linha pode ter diversas colunas indexadas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="bd91d-147">A document can have multiple properties, just as a row can have multiple full-text indexed columns.</span></span>  
  
 <span data-ttu-id="bd91d-148">Índice</span><span class="sxs-lookup"><span data-stu-id="bd91d-148">Index</span></span>  
 <span data-ttu-id="bd91d-149">Um único índice invertido de um ou mais documentos.</span><span class="sxs-lookup"><span data-stu-id="bd91d-149">A single inverted index of one or more documents.</span></span> <span data-ttu-id="bd91d-150">Isto pode estar por inteiro na memória ou no disco.</span><span class="sxs-lookup"><span data-stu-id="bd91d-150">This may be entirely in memory or on disk.</span></span> <span data-ttu-id="bd91d-151">Muitas estatísticas de consulta são relativas ao índice individual onde a correspondência ocorreu.</span><span class="sxs-lookup"><span data-stu-id="bd91d-151">Many query statistics are relative to the individual index where the match occurred.</span></span>  
  
 <span data-ttu-id="bd91d-152">Catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="bd91d-152">Full-Text Catalog</span></span>  
 <span data-ttu-id="bd91d-153">Uma coleção de índices intermediários tratada como uma entidade para consultas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-153">A collection of intermediate indexes treated as one entity for queries.</span></span> <span data-ttu-id="bd91d-154">Catálogos são a unidade de organização visível para o administrador [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd91d-154">Catalogs are the unit of organization visible to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="bd91d-155">Palavra, token ou item</span><span class="sxs-lookup"><span data-stu-id="bd91d-155">Word, token or item</span></span>  
 <span data-ttu-id="bd91d-156">A unidade de correspondência no mecanismo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="bd91d-156">The unit of matching in the full-text engine.</span></span> <span data-ttu-id="bd91d-157">Fluxos de texto de documentos são convertidos em palavras ou tokens por separadores de palavras de um determinado idioma.</span><span class="sxs-lookup"><span data-stu-id="bd91d-157">Streams of text from documents are tokenized into words, or tokens by language-specific word breakers.</span></span>  
  
 <span data-ttu-id="bd91d-158">Ocorrência</span><span class="sxs-lookup"><span data-stu-id="bd91d-158">Occurrence</span></span>  
 <span data-ttu-id="bd91d-159">O deslocamento da palavra em uma propriedade de documento como determinado pelo separador de palavras.</span><span class="sxs-lookup"><span data-stu-id="bd91d-159">The word offset in a document property as determined by the word breaker.</span></span> <span data-ttu-id="bd91d-160">A primeira palavra está na ocorrência 1, a próxima na 2, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="bd91d-160">The first word is at occurrence 1, the next at 2, and so on.</span></span> <span data-ttu-id="bd91d-161">A fim de evitar falsos positivos em frase e consultas por proximidade, o término da oração e término do parágrafo introduz intervalos maiores de ocorrência.</span><span class="sxs-lookup"><span data-stu-id="bd91d-161">In order to avoid false positives in phrase and proximity queries, end-of-sentence and end-of-paragraph introduce larger occurrence gaps.</span></span>  
  
 <span data-ttu-id="bd91d-162">TermFrequency</span><span class="sxs-lookup"><span data-stu-id="bd91d-162">TermFrequency</span></span>  
 <span data-ttu-id="bd91d-163">O número de vezes que o valor da chave ocorre em uma linha.</span><span class="sxs-lookup"><span data-stu-id="bd91d-163">The number times the key value occurs in a row.</span></span>  
  
 <span data-ttu-id="bd91d-164">IndexedRowCount</span><span class="sxs-lookup"><span data-stu-id="bd91d-164">IndexedRowCount</span></span>  
 <span data-ttu-id="bd91d-165">Número total de linhas indexadas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-165">Total number of rows indexed.</span></span> <span data-ttu-id="bd91d-166">Isto é computado com base nas contagens mantidas nos índices intermediários.</span><span class="sxs-lookup"><span data-stu-id="bd91d-166">This is computed, based on counts maintained in the intermediate indexes.</span></span> <span data-ttu-id="bd91d-167">Este número pode variar em precisão.</span><span class="sxs-lookup"><span data-stu-id="bd91d-167">This number can vary in accuracy.</span></span>  
  
 <span data-ttu-id="bd91d-168">KeyRowCount</span><span class="sxs-lookup"><span data-stu-id="bd91d-168">KeyRowCount</span></span>  
 <span data-ttu-id="bd91d-169">Total de linhas no catálogo de texto completo que contém uma dada chave.</span><span class="sxs-lookup"><span data-stu-id="bd91d-169">Total number of rows in the full-text catalog that contain a given key.</span></span>  
  
 <span data-ttu-id="bd91d-170">MaxOccurrence</span><span class="sxs-lookup"><span data-stu-id="bd91d-170">MaxOccurrence</span></span>  
 <span data-ttu-id="bd91d-171">A maior ocorrência armazenada em um catálogo de texto completo a uma determinada propriedade em uma linha.</span><span class="sxs-lookup"><span data-stu-id="bd91d-171">The largest occurrence stored in a full-text catalog for a given property in a row.</span></span>  
  
 <span data-ttu-id="bd91d-172">MaxQueryRank</span><span class="sxs-lookup"><span data-stu-id="bd91d-172">MaxQueryRank</span></span>  
 <span data-ttu-id="bd91d-173">A classificação máxima, 1000, retornada pelo Mecanismo de Texto Completo.</span><span class="sxs-lookup"><span data-stu-id="bd91d-173">The maximum rank, 1000, returned by the Full-Text Engine.</span></span>  
  
  
### <a name="rank-computation-issues"></a><span data-ttu-id="bd91d-174">Problemas na computação da classificação</span><span class="sxs-lookup"><span data-stu-id="bd91d-174">Rank Computation Issues</span></span>  
 <span data-ttu-id="bd91d-175">O processo de computação da classificação depende de vários fatores.</span><span class="sxs-lookup"><span data-stu-id="bd91d-175">The process of computing rank, depends on a number of factors.</span></span>  <span data-ttu-id="bd91d-176">Separadores de palavra de idiomas diferentes convertem o texto em token de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="bd91d-176">Different language word breakers tokenize text differently.</span></span> <span data-ttu-id="bd91d-177">Por exemplo, a cadeia de caracteres “casa de cachorro” pode ser quebrada em “casa” “cachorro” por um separador de palavra e em “casa de cachorro” por outro separador de palavra.</span><span class="sxs-lookup"><span data-stu-id="bd91d-177">For example, the string "dog-house" could be broken into "dog" "house" by one word breaker and into "dog-house" by another.</span></span> <span data-ttu-id="bd91d-178">Isto significa que a correspondência e a classificação podem variar com base em um idioma específico, porque não só as palavras são diferentes como também o tamanho do documento.</span><span class="sxs-lookup"><span data-stu-id="bd91d-178">This means that matching and ranking will vary based on the language specified, because not only are the words different, but so is the document length.</span></span> <span data-ttu-id="bd91d-179">A diferença de tamanho do documento pode afetar a classificação para todas as consultas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-179">The document length difference can affect ranking for all queries.</span></span>  
  
 <span data-ttu-id="bd91d-180">Estatísticas como `IndexRowCount` podem variar muito.</span><span class="sxs-lookup"><span data-stu-id="bd91d-180">Statistics such as `IndexRowCount` can vary widely.</span></span> <span data-ttu-id="bd91d-181">Por exemplo, se um catálogo tem 2 bilhões de linhas no índice mestre, um novo documento será indexado no índice intermediário da memória, e a classificação daquele documento será com base no número de documentos no índice da memória que poderão ser inclinados quando comparados às classificações dos documentos do índice mestre.</span><span class="sxs-lookup"><span data-stu-id="bd91d-181">For example, if a catalog has 2 billion rows in the master index, then one new document is indexed into an in-memory intermediate index, and ranks for that document based on the number of documents in the in-memory index could be skewed compared with ranks for documents from the master index.</span></span> <span data-ttu-id="bd91d-182">Por esta razão, recomenda-se que, após qualquer população que resulte em um grande número de linhas, os índices indexados ou reindexados sejam mesclados em um índice mestre usando a função ALTER FULLTEXT CATALOG... Instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="bd91d-182">For this reason, it is recommended that after any population that results in large number of rows being indexed or re-indexed the indexes be merged into a master index using the ALTER FULLTEXT CATALOG ... REORGANIZE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="bd91d-183">O Mecanismo de Texto Completo também mesclará automaticamente os índices com base em parâmetros como o número e o tamanho dos índices intermediários.</span><span class="sxs-lookup"><span data-stu-id="bd91d-183">The Full-Text Engine will also automatically merge the indexes based on parameters such as the number and size of intermediate indexes.</span></span>  
  
 <span data-ttu-id="bd91d-184">Os valores `MaxOccurrence` são normalizados em 1 de 32 intervalos.</span><span class="sxs-lookup"><span data-stu-id="bd91d-184">`MaxOccurrence` values are normalized into 1 of 32 ranges.</span></span> <span data-ttu-id="bd91d-185">Isto significa, por exemplo, que um documento de 50 palavras é tratado da mesma forma que um documento de 100 palavras.</span><span class="sxs-lookup"><span data-stu-id="bd91d-185">This means, for example, that a document 50 words long is treated the same as a document 100 words long.</span></span> <span data-ttu-id="bd91d-186">Abaixo está a tabela usada para normalização.</span><span class="sxs-lookup"><span data-stu-id="bd91d-186">Below is the table used for normalization.</span></span> <span data-ttu-id="bd91d-187">Como os comprimentos do documento estão no intervalo entre os valores de tabela adjacentes 32 e 128, eles são efetivamente tratados como tendo o mesmo comprimento, 128 (32 < `docLength` <= 128).</span><span class="sxs-lookup"><span data-stu-id="bd91d-187">Because the document lengths are in the range between adjacent table values 32 and 128, they are effectively treated as having the same length, 128 (32 < `docLength` <= 128).</span></span>  
  
```  
{ 16, 32, 128, 256, 512, 725, 1024, 1450, 2048, 2896, 4096, 5792, 8192, 11585,   
16384, 23170, 28000, 32768, 39554, 46340, 55938, 65536, 92681, 131072, 185363,   
262144, 370727, 524288, 741455, 1048576, 2097152, 4194304 };  
  
```  
  
  
### <a name="ranking-of-containstable"></a><span data-ttu-id="bd91d-188">Classificação do CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="bd91d-188">Ranking of CONTAINSTABLE</span></span>  
 <span data-ttu-id="bd91d-189">A classificação[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) usa o seguinte algoritmo:</span><span class="sxs-lookup"><span data-stu-id="bd91d-189">[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) ranking uses the following algorithm:</span></span>  
  
```  
StatisticalWeight = Log2( ( 2 + IndexedRowCount ) / KeyRowCount )  
Rank = min( MaxQueryRank, HitCount * 16 * StatisticalWeight / MaxOccurrence )  
```  
  
 <span data-ttu-id="bd91d-190">As correspondências de frase são classificadas exatamente como as chaves individuais, com exceção da `KeyRowCount` (o número de linhas contendo a frase) que é estimada e pode não ser precisa e ser maior do que o número real.</span><span class="sxs-lookup"><span data-stu-id="bd91d-190">Phrase matches are ranked just like individual keys except that `KeyRowCount` (the number of rows containing the phrase) is estimated and can be inaccurate and higher than the actual number.</span></span>  
  
 <span data-ttu-id="bd91d-191">**Classificação de NEAR**</span><span class="sxs-lookup"><span data-stu-id="bd91d-191">**Ranking of NEAR**</span></span>  
  
 <span data-ttu-id="bd91d-192">CONTAINSTABLE oferece suporte a consultas de dois ou mais termos de pesquisa próximos entre si usando a opção NEAR.</span><span class="sxs-lookup"><span data-stu-id="bd91d-192">CONTAINSTABLE supports querying for two or more search terms in proximity to each other by using the NEAR option.</span></span> <span data-ttu-id="bd91d-193">O valor de classificação de cada linha retornada baseia-se em vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="bd91d-193">The rank value of each returned row is based on several parameters.</span></span> <span data-ttu-id="bd91d-194">Um fator de classificação principal é o número total de correspondências (ou *ocorrências*) relativo ao tamanho do documento.</span><span class="sxs-lookup"><span data-stu-id="bd91d-194">One major ranking factor is the total number of matches (or *hits*) relative to the length of the document.</span></span> <span data-ttu-id="bd91d-195">Dessa forma, se, por exemplo, um documento de 100 palavras e um documento de 900 palavras contiverem correspondências idênticas, o documento de 100 palavras terá uma classificação mais alta.</span><span class="sxs-lookup"><span data-stu-id="bd91d-195">Thus, for example, if a 100-word document and a 900-word document contain identical matches, the 100-word document is ranked higher.</span></span>  
  
 <span data-ttu-id="bd91d-196">O comprimento total de cada ocorrência em uma linha também contribuirá para a classificação dessa linha com base na distância entre o primeiro e o último termos de pesquisa daquela ocorrência.</span><span class="sxs-lookup"><span data-stu-id="bd91d-196">The total length of each hit in a row will also contribute to the ranking of that row based on the distance between the first and last search terms of that hit.</span></span> <span data-ttu-id="bd91d-197">Quanto menor a distância, mais a ocorrência contribuirá para o valor de classificação da linha.</span><span class="sxs-lookup"><span data-stu-id="bd91d-197">The smaller the distance, the more the hit contributes to the rank value of the row.</span></span> <span data-ttu-id="bd91d-198">Se uma consulta de texto completo não especificar um valor inteiro como a distância máxima, um documento que só contém ocorrências cujas distâncias são separadamente maiores que 100 condições lógicas, terá uma classificação de 0.</span><span class="sxs-lookup"><span data-stu-id="bd91d-198">If a full-text query does not specify an integer as the maximum distance, a document that contains only hits whose distances are greater than 100 logical terms apart, will have a ranking of 0.</span></span>  
  
 <span data-ttu-id="bd91d-199">**Classificação de ISABOUT**</span><span class="sxs-lookup"><span data-stu-id="bd91d-199">**Ranking of ISABOUT**</span></span>  
  
 <span data-ttu-id="bd91d-200">CONTAINSTABLE oferece suporte a consultas de termos ponderados usando a opção ISABOUT.</span><span class="sxs-lookup"><span data-stu-id="bd91d-200">CONTAINSTABLE supports querying for weighted terms by using the ISABOUT option.</span></span> <span data-ttu-id="bd91d-201">ISABOUT é uma consulta do espaço de vetor na terminologia de recuperação de informações tradicionais.</span><span class="sxs-lookup"><span data-stu-id="bd91d-201">ISABOUT is a vector-space query in traditional information retrieval terminology.</span></span> <span data-ttu-id="bd91d-202">O algoritmo padrão de classificação usado é Jaccard, uma fórmula muito conhecida.</span><span class="sxs-lookup"><span data-stu-id="bd91d-202">The default ranking algorithm used is Jaccard, a widely known formula.</span></span> <span data-ttu-id="bd91d-203">A classificação é computada para cada termo da consulta e combinada conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="bd91d-203">The ranking is computed for each term in the query and then combined as described below.</span></span>  
  
```  
ContainsRank = same formula used for CONTAINSTABLE ranking of a single term (above).  
Weight = the weight specified in the query for each term. Default weight is 1.  
WeightedSum = ??[key=1 to n] ContainsRankKey * WeightKey  
Rank =  ( MaxQueryRank * WeightedSum ) / ( ( ??[key=1 to n] ContainsRankKey^2 )   
      + ( ??[key=1 to n] WeightKey^2 ) - ( WeightedSum ) )  
  
```  
  
  
### <a name="ranking-of-freetexttable"></a><span data-ttu-id="bd91d-204">Classificação de FREETEXTTABLE</span><span class="sxs-lookup"><span data-stu-id="bd91d-204">Ranking of FREETEXTTABLE</span></span>  
 <span data-ttu-id="bd91d-205">A classificação de[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) tem como base a fórmula de classificação OKAPI BM25.</span><span class="sxs-lookup"><span data-stu-id="bd91d-205">[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) ranking is based on the OKAPI BM25 ranking formula.</span></span> <span data-ttu-id="bd91d-206">Consultas FREETEXTTABLE adicionarão palavras à consulta via geração por flexão (formas flexionadas das palavras originais da consulta); essas palavras são tratadas como palavras separadas, sem nenhuma relação especial com as palavras das quais foram geradas.</span><span class="sxs-lookup"><span data-stu-id="bd91d-206">FREETEXTTABLE queries will add words to the query via inflectional generation (inflected forms of the original query words); these words are treated as separate words with no special relationship to the words from which they were generated.</span></span> <span data-ttu-id="bd91d-207">Sinônimos gerados do recurso Thesaurus serão tratados como palavras separadas, em condições de igual equilíbrio.</span><span class="sxs-lookup"><span data-stu-id="bd91d-207">Synonyms generated from the Thesaurus feature are treated as separate, equally weighted terms.</span></span> <span data-ttu-id="bd91d-208">Cada palavra na consulta contribui para a classificação.</span><span class="sxs-lookup"><span data-stu-id="bd91d-208">Each word in the query contributes to the rank.</span></span>  
  
```  
Rank = ??[Terms in Query] w ( ( ( k1 + 1 ) tf ) / ( K + tf ) ) * ( ( k3 + 1 ) qtf / ( k3 + qtf ) ) )  
Where:   
w is the Robertson-Sparck Jones weight.   
In simplified form, w is defined as:   
w = log10 ( ( ( r + 0.5 ) * ( N - R + r + 0.5 ) ) / ( ( R - r + 0.5 ) * ( n - r + 0.5 ) )  
N is the number of indexed rows for the property being queried.   
n is the number of rows containing the word.   
K is ( k1 * ( ( 1 - b ) + ( b * dl / avdl ) ) ).   
dl is the property length, in word occurrences.   
avdl is the average length of the property being queried, in word occurrences.   
k1, b, and k3 are the constants 1.2, 0.75, and 8.0, respectively.   
tf is the frequency of the word in the queried property in a specific row.   
qtf is the frequency of the term in the query.   
```  
  
  
## <a name="see-also"></a><span data-ttu-id="bd91d-209">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bd91d-209">See Also</span></span>  
 [<span data-ttu-id="bd91d-210">Consulta com pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="bd91d-210">Query with Full-Text Search</span></span>](query-with-full-text-search.md)  
  
  
