---
title: Solucionar problemas de indexação de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- indexes [full-text search]
- troubleshooting [SQL Server], full-text search
- troubleshooting [full-text search]
ms.assetid: 964c43a8-5019-4179-82aa-63cd0ef592ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eaca5fcf2dfbac57fc6d3ba6178251927d15aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583461"
---
# <a name="troubleshoot-full-text-indexing"></a><span data-ttu-id="8ccb3-102">Solucionar problemas na indexação de texto completo</span><span class="sxs-lookup"><span data-stu-id="8ccb3-102">Troubleshoot Full-Text Indexing</span></span>
     
##  <a name="troubleshoot-full-text-indexing-failures"></a><a name="failure"></a> <span data-ttu-id="8ccb3-103">Solucionar problemas de falhas na indexação de texto completo</span><span class="sxs-lookup"><span data-stu-id="8ccb3-103">Troubleshoot Full-Text Indexing Failures</span></span>  
 <span data-ttu-id="8ccb3-104">Ao popular ou manter um índice de texto completo, o indexador de texto completo, pelas razões descritas a seguir, talvez falhe ao indexar uma ou mais linhas.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-104">While populating or maintaining a full-text index, the full-text indexer, for reasons described below, might fail to index one or more rows.</span></span> <span data-ttu-id="8ccb3-105">Esses erros em nível de linha não impedem a conclusão da população.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-105">These row-level errors do not prevent the population from completing.</span></span> <span data-ttu-id="8ccb3-106">O indexador ignora essas linhas, o que significa que não é possível consultar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-106">The indexer skips these rows, which means that you are not able to query for content contained in these rows.</span></span>  
  
 <span data-ttu-id="8ccb3-107">As falhas de indexação podem ocorrer quando:</span><span class="sxs-lookup"><span data-stu-id="8ccb3-107">Indexing failures can occur when:</span></span>  
  
-   <span data-ttu-id="8ccb3-108">O indexador não consegue localizar ou carregar um filtro ou componente do separador de palavra.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-108">The indexer cannot find or load a filter or word breaker component.</span></span> <span data-ttu-id="8ccb3-109">Essa falha pode ocorrer se a linha da tabela tiver um formato de documento ou conteúdo em idioma não registrado com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ccb3-109">This failure can occur if the table row contains a document format or content in a language that has not been registered with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8ccb3-110">Essa falha também pode ocorrer se o componente do filtro ou o separador de palavra registrado não estava assinado ou se houve falha na verificação de assinatura ao carregar.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-110">This failure can also happen if the registered word breaker or filter component was not signed or failed signature verification when it was being loaded.</span></span>  
  
-   <span data-ttu-id="8ccb3-111">Um componente, como um separador de palavra ou filtro, falha e retorna um erro para o indexador,</span><span class="sxs-lookup"><span data-stu-id="8ccb3-111">A component, such as a word breaker or filter, fails and returns an error to the indexer.</span></span> <span data-ttu-id="8ccb3-112">o que pode ocorrer se o documento a indexar estiver corrompido e o filtro não conseguir extrair seu texto.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-112">This can happen if the document being indexed is corrupt and the filter is unable to extract text from the document.</span></span> <span data-ttu-id="8ccb3-113">Isso também pode ocorrer quando um componente não puder tratar o conteúdo de uma única linha acima de um determinado tamanho, devido a limites de memória no host do daemon do filtro (fdhost.exe).</span><span class="sxs-lookup"><span data-stu-id="8ccb3-113">This can also occur when a component is unable to handle the content of a single row above a certain size, due to memory limits on the full-text filter daemon host (fdhost.exe).</span></span>  
  
 <span data-ttu-id="8ccb3-114">Para cada falha do nível de linha, o log de rastreamento contém detalhes da razão da falha.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-114">For each row-level failure, the crawl log contains details on the reason for the failure.</span></span> <span data-ttu-id="8ccb3-115">As contas de erro são resumidas no término de uma população completa ou com incremento.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-115">The error counts are summarized at the end of a full or incremental population.</span></span>  
  
 <span data-ttu-id="8ccb3-116">Há outras falhas que podem impactar o próprio processo de indexação e impedir a conclusão da população:</span><span class="sxs-lookup"><span data-stu-id="8ccb3-116">There are other failures that can impact the indexing process itself and prevent the population from completing:</span></span>  
  
-   <span data-ttu-id="8ccb3-117">O índice de texto completo excede o limite para o número de linhas que podem ser contidas em um catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-117">The full-text index exceeds the limit for the number of rows that can be contained in a full-text catalog.</span></span>  
  
-   <span data-ttu-id="8ccb3-118">Um índice clusterizado ou um índice de chave de texto completo da tabela em indexação são alterados, descartados ou recriados.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-118">A clustered index or full-text key index on the table being indexed gets altered, dropped, or rebuilt.</span></span>  
  
-   <span data-ttu-id="8ccb3-119">Uma falha no hardware ou disco corrompido resulta em corrupção do catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-119">A hardware failure or disk corruption results in the corruption of the full-text catalog.</span></span>  
  
-   <span data-ttu-id="8ccb3-120">Um grupo de arquivo que contém a tabela cujo texto completo passa por indexação fica offline ou é do tipo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-120">A file group that contains the table being full-text indexed goes offline, or is made read-only.</span></span>  
  
 <span data-ttu-id="8ccb3-121">Você deve exibir o registro de rastreamento no final de qualquer operação significativa de indexação de texto completo ou ao descobrir que a população não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-121">You should view the crawl log at the end of any significant full-text index population operation, or when you find that a population did not complete.</span></span>  
  
### <a name="unsigned-components"></a><span data-ttu-id="8ccb3-122">Componentes não assinados</span><span class="sxs-lookup"><span data-stu-id="8ccb3-122">Unsigned Components</span></span>  
 <span data-ttu-id="8ccb3-123">Por padrão, o indexador de texto completo requer os filtros e separadores de palavras que carrega ao assinar.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-123">By default, the full-text indexer requires the filters and word breakers that it loads to be signed.</span></span> <span data-ttu-id="8ccb3-124">Se não estiverem assinados, o que algumas vezes é o caso quando os componentes personalizados são instalados, é necessário configurar o indexador de texto completo para ignorar a verificação de assinatura.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-124">If they are not signed, which is the case sometimes when custom components are installed, you must configure the full-text indexer to ignore signature verification.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8ccb3-125">Ignorar a verificação de assinatura torna menos segura a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ccb3-125">Ignoring signature verification makes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] less secure.</span></span> <span data-ttu-id="8ccb3-126">Recomendamos assinar quaisquer componentes implementados ou garantir que os componentes que você adquirir estão assinados.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-126">We recommend that you sign any components that you implement or ensure that any components that you acquire are signed.</span></span> <span data-ttu-id="8ccb3-127">Para obter informações sobre componentes de assinatura, veja [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ccb3-127">For information about signing components, see [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  

  
##  <a name="full-text-index-in-inconsistent-state-after-transaction-log-restored"></a><a name="state"></a> <span data-ttu-id="8ccb3-128">Índice de texto completo em estado inconsistente após o log de transações ser restaurado</span><span class="sxs-lookup"><span data-stu-id="8ccb3-128">Full-Text Index in Inconsistent State after Transaction Log Restored</span></span>  
 <span data-ttu-id="8ccb3-129">Ao restaurar o log de transações de um banco de dados, é possível que apareça um aviso indicando que o índice de texto completo não está em um estado consistente.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-129">When restoring the transaction log of a database, you might see a warning indicating that the full-text index is not in a consistent state.</span></span> <span data-ttu-id="8ccb3-130">O motivo pelo qual isso ocorre é que o índice de texto completo de uma tabela foi modificado após ter sido feito o backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-130">The reason for this is that the full-text index on a table was modified after the database was backed up.</span></span> <span data-ttu-id="8ccb3-131">Para trazer o índice de texto completo a um estado consistente, você deve executar uma população completa (rastreamento) na tabela.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-131">To bring the full-text index to a consistent state, you must run a full population (crawl) on the table.</span></span> <span data-ttu-id="8ccb3-132">Para obter mais informações, veja [Popular índices de texto completo](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="8ccb3-132">For more information, see [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="8ccb3-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ccb3-133">See Also</span></span>  
 <span data-ttu-id="8ccb3-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8ccb3-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="8ccb3-135">Popular índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="8ccb3-135">Populate Full-Text Indexes</span></span>](../indexes/indexes.md)  
  
  
