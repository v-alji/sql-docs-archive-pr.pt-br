---
title: Opção de configuração de servidor transform noise words | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- full-text queries [SQL Server], performance
- transform noise words option
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 69bd388e-a86c-4de4-b5d5-d093424d9c57
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 49de4a381de3e998073a73c284e3e3e5960f4921
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684318"
---
# <a name="transform-noise-words-server-configuration-option"></a><span data-ttu-id="b72c2-102">Opção de configuração de servidor para transformar palavras de ruído</span><span class="sxs-lookup"><span data-stu-id="b72c2-102">transform noise words Server Configuration Option</span></span>
  <span data-ttu-id="b72c2-103">Use a `transform noise words` opção de configuração de servidor para suprimir uma mensagem de erro se palavras de ruído, ou seja, [palavras irrelevantes](../../relational-databases/search/full-text-search.md), fizer com que uma operação booliana em uma consulta de texto completo retorne zero linhas.</span><span class="sxs-lookup"><span data-stu-id="b72c2-103">Use the `transform noise words` server configuration option to suppress an error message if noise words, that is [stopwords](../../relational-databases/search/full-text-search.md), cause a Boolean operation on a full-text query to return zero rows.</span></span> <span data-ttu-id="b72c2-104">Essa opção é útil para consultas de texto completo que usam o predicado CONTAINS em que as operações boolianas ou operações NEAR incluem palavras de ruído.</span><span class="sxs-lookup"><span data-stu-id="b72c2-104">This option is useful for full-text queries that use the CONTAINS predicate in which Boolean operations or NEAR operations include noise words.</span></span> <span data-ttu-id="b72c2-105">Os valores possíveis são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b72c2-105">The possible values are described in the following table.</span></span>  
  
|<span data-ttu-id="b72c2-106">Valor</span><span class="sxs-lookup"><span data-stu-id="b72c2-106">Value</span></span>|<span data-ttu-id="b72c2-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b72c2-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b72c2-108">0</span><span class="sxs-lookup"><span data-stu-id="b72c2-108">0</span></span>|<span data-ttu-id="b72c2-109">As palavras de ruído (ou palavras irrelevantes) não são transformadas.</span><span class="sxs-lookup"><span data-stu-id="b72c2-109">Noise words (or stopwords) are not transformed.</span></span> <span data-ttu-id="b72c2-110">Quando uma consulta de texto completo contiver palavras de ruído, a consulta não retornará nenhuma linha e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gerará um aviso.</span><span class="sxs-lookup"><span data-stu-id="b72c2-110">When a full-text query contains noise words, the query returns zero rows, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] raises a warning.</span></span> <span data-ttu-id="b72c2-111">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="b72c2-111">This is the default behavior.</span></span><br /><br /> <span data-ttu-id="b72c2-112">Observe que o aviso é um aviso de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b72c2-112">Note that the warning is a run-time warning.</span></span> <span data-ttu-id="b72c2-113">Portanto, se a cláusula de texto completo na consulta não for executada, o aviso não será gerado.</span><span class="sxs-lookup"><span data-stu-id="b72c2-113">Therefore, if the full-text clause in the query is not executed, the warning is not raised.</span></span> <span data-ttu-id="b72c2-114">Para uma consulta local, apenas um aviso é gerado, mesmo quando há várias cláusulas de consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="b72c2-114">For a local query, only one warning is raised, even when there are multiple full-text query clauses.</span></span> <span data-ttu-id="b72c2-115">Para uma consulta remota, o servidor vinculado pode não retransmitir o erro; portanto, o aviso pode não ser gerado.</span><span class="sxs-lookup"><span data-stu-id="b72c2-115">For a remote query, the linked server might not relay the error; therefore, the warning might not be raised.</span></span>|  
|<span data-ttu-id="b72c2-116">1</span><span class="sxs-lookup"><span data-stu-id="b72c2-116">1</span></span>|<span data-ttu-id="b72c2-117">As palavras de ruído (ou palavras irrelevantes) são transformadas.</span><span class="sxs-lookup"><span data-stu-id="b72c2-117">Noise words (or stopwords) are transformed.</span></span> <span data-ttu-id="b72c2-118">Elas são ignoradas e o resto da consulta é avaliado.</span><span class="sxs-lookup"><span data-stu-id="b72c2-118">They are ignored, and the rest of the query is evaluated.</span></span><br /><br /> <span data-ttu-id="b72c2-119">Se forem especificadas palavras de ruído em uma condição de proximidade, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as removerá.</span><span class="sxs-lookup"><span data-stu-id="b72c2-119">If noise words are specified in a proximity term, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] removes them.</span></span> <span data-ttu-id="b72c2-120">Por exemplo, a palavra de ruído `is` é removida de `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transformando a consulta de pesquisa em `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span><span class="sxs-lookup"><span data-stu-id="b72c2-120">For example, the noise word `is` is removed from `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transforming the search query into `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span></span> <span data-ttu-id="b72c2-121">Observe que `CONTAINS(<column_name>, 'NEAR(hello,is)')` seria transformada simplesmente em `CONTAINS(<column_name>, hello)` porque há apenas um termo de pesquisa válido.</span><span class="sxs-lookup"><span data-stu-id="b72c2-121">Notice that `CONTAINS(<column_name>, 'NEAR(hello,is)')` would be transformed into simply `CONTAINS(<column_name>, hello)` because there is only one valid search term.</span></span>|  
  
## <a name="effects-of-the-transform-noise-words-setting"></a><span data-ttu-id="b72c2-122">Efeitos da Configuração transformar palavras de ruído</span><span class="sxs-lookup"><span data-stu-id="b72c2-122">Effects of the transform noise words Setting</span></span>  
 <span data-ttu-id="b72c2-123">Esta seção ilustra o comportamento de consultas que contêm uma palavra de ruído", `the`", nas configurações alternativas de `transform noise words`.</span><span class="sxs-lookup"><span data-stu-id="b72c2-123">This section illustrates the behavior of queries containing a noise word, "`the`", under the alternate settings of `transform noise words`.</span></span>  <span data-ttu-id="b72c2-124">Parte-se do pressuposto de que as cadeias de consulta de texto completo de exemplo são executadas em uma linha de tabela que contém os seguintes dados: `[1, "The black cat"]`.</span><span class="sxs-lookup"><span data-stu-id="b72c2-124">The sample full-text query strings are assumed to be run against a table row containing the following data: `[1, "The black cat"]`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b72c2-125">Todos esses cenários podem gerar um aviso de palavra de ruído.</span><span class="sxs-lookup"><span data-stu-id="b72c2-125">All such scenarios can generate a noise word warning.</span></span>  
  
-   <span data-ttu-id="b72c2-126">Com transformar palavras de ruído definido como 0:</span><span class="sxs-lookup"><span data-stu-id="b72c2-126">With transform noise words set to 0:</span></span>  
  
    |<span data-ttu-id="b72c2-127">Cadeia de consulta</span><span class="sxs-lookup"><span data-stu-id="b72c2-127">Query string</span></span>|<span data-ttu-id="b72c2-128">Result</span><span class="sxs-lookup"><span data-stu-id="b72c2-128">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="b72c2-129">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="b72c2-129">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="b72c2-130">Nenhum resultado (O comportamento é o mesmo para "`the`" AND "`cat`".)</span><span class="sxs-lookup"><span data-stu-id="b72c2-130">No results (The behavior is the same for "`the`" AND "`cat`".)</span></span>|  
    |<span data-ttu-id="b72c2-131">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="b72c2-131">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="b72c2-132">Nenhum resultado (O comportamento é o mesmo para "`the`" NEAR "`cat`".)</span><span class="sxs-lookup"><span data-stu-id="b72c2-132">No results (The behavior is the same for "`the`" NEAR "`cat`".)</span></span>|  
    |<span data-ttu-id="b72c2-133">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="b72c2-133">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="b72c2-134">Nenhum resultado</span><span class="sxs-lookup"><span data-stu-id="b72c2-134">No results</span></span>|  
    |<span data-ttu-id="b72c2-135">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="b72c2-135">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="b72c2-136">Nenhum resultado</span><span class="sxs-lookup"><span data-stu-id="b72c2-136">No results</span></span>|  
  
-   <span data-ttu-id="b72c2-137">Com transformar palavras de ruído definido como 1:</span><span class="sxs-lookup"><span data-stu-id="b72c2-137">With transform noise words set to 1:</span></span>  
  
    |<span data-ttu-id="b72c2-138">Cadeia de consulta</span><span class="sxs-lookup"><span data-stu-id="b72c2-138">Query string</span></span>|<span data-ttu-id="b72c2-139">Result</span><span class="sxs-lookup"><span data-stu-id="b72c2-139">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="b72c2-140">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="b72c2-140">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="b72c2-141">Ocorrência da linha com ID 1</span><span class="sxs-lookup"><span data-stu-id="b72c2-141">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="b72c2-142">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="b72c2-142">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="b72c2-143">Ocorrência da linha com ID 1</span><span class="sxs-lookup"><span data-stu-id="b72c2-143">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="b72c2-144">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="b72c2-144">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="b72c2-145">Nenhum resultado</span><span class="sxs-lookup"><span data-stu-id="b72c2-145">No results</span></span>|  
    |<span data-ttu-id="b72c2-146">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="b72c2-146">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="b72c2-147">Ocorrência da linha com ID 1</span><span class="sxs-lookup"><span data-stu-id="b72c2-147">Hit for row with ID 1</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b72c2-148">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b72c2-148">Example</span></span>  
 <span data-ttu-id="b72c2-149">O exemplo a seguir define `transform noise words` como `1`.</span><span class="sxs-lookup"><span data-stu-id="b72c2-149">The following example sets `transform noise words` to `1`.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
GO  
sp_configure 'transform noise words', 1;  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b72c2-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b72c2-150">See Also</span></span>  
 <span data-ttu-id="b72c2-151">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b72c2-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="b72c2-152">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b72c2-152">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
