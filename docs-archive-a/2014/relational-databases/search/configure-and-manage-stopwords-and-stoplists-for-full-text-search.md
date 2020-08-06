---
title: Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes para pesquisa de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- stoplists [full-text search]
- full-text search [SQL Server], stoplists
- full-text search [SQL Server], noise words
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 43b5ce7b-9f09-4443-8a5b-c3da6eb28bcc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 103b5024368c5ca239856580e9b45473aabf6a92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685520"
---
# <a name="configure-and-manage-stopwords-and-stoplists-for-full-text-search"></a><span data-ttu-id="d8757-102">Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes (stoplists) para pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="d8757-102">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>
  <span data-ttu-id="d8757-103">Para evitar que os índices de texto completo fiquem lotados, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dispõe de um mecanismo que descarta cadeias de caracteres que ocorrem com frequência e que não auxiliam nas pesquisas.</span><span class="sxs-lookup"><span data-stu-id="d8757-103">To prevent a full-text index from becoming bloated, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has a mechanism that discards commonly occurring strings that do not help the search.</span></span> <span data-ttu-id="d8757-104">Essas cadeias de caracteres descartadas são chamadas de *palavras irrelevantes*(stopwords).</span><span class="sxs-lookup"><span data-stu-id="d8757-104">These discarded strings are called *stopwords*.</span></span> <span data-ttu-id="d8757-105">Durante a criação do índice, o Mecanismo de Texto Completo omite as palavras irrelevantes do índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d8757-105">During index creation, the Full-Text Engine omits stopwords from the full-text index.</span></span> <span data-ttu-id="d8757-106">Em outras palavras, as consultas de texto completo não pesquisarão palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="d8757-106">This means that full-text queries will not search on stopwords.</span></span>  
  
##  <a name="understanding-stopwords-and-stoplists"></a><a name="understand"></a><span data-ttu-id="d8757-107">Entendendo palavras irrelevantes e palavras irrelevantes</span><span class="sxs-lookup"><span data-stu-id="d8757-107">Understanding Stopwords and Stoplists</span></span>  
 <span data-ttu-id="d8757-108">Uma palavra irrelevante pode ser uma palavra com significado em um determinado idioma ou um *token* sem significado linguístico.</span><span class="sxs-lookup"><span data-stu-id="d8757-108">A stopword can be a word with meaning in a specific language, or it can be a *token* that does not have linguistic meaning.</span></span> <span data-ttu-id="d8757-109">Por exemplo, em inglês, palavras como "a", "and", "is" e "the" não são incluídas no índice de texto completo porque são consideradas inúteis em uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d8757-109">For example, in the English language, words such as "a," "and," "is," and "the" are left out of the full-text index since they are known to be useless to a search.</span></span>  
  
 <span data-ttu-id="d8757-110">Embora as palavras irrelevantes sejam ignoradas, o índice de texto completo leva em conta sua posição.</span><span class="sxs-lookup"><span data-stu-id="d8757-110">Although it ignores the inclusion of stopwords, the full-text index does take into account their position.</span></span> <span data-ttu-id="d8757-111">Por exemplo, considere a frase "Instructions are applicable to these Adventure Works Cycles models".</span><span class="sxs-lookup"><span data-stu-id="d8757-111">For example, consider the phrase, "Instructions are applicable to these Adventure Works Cycles models".</span></span> <span data-ttu-id="d8757-112">A tabela a seguir descreve a posição das palavras na frase:</span><span class="sxs-lookup"><span data-stu-id="d8757-112">The following table depicts the position of the words in the phrase:</span></span>  
  
|<span data-ttu-id="d8757-113">Word</span><span class="sxs-lookup"><span data-stu-id="d8757-113">Word</span></span>|<span data-ttu-id="d8757-114">Posição</span><span class="sxs-lookup"><span data-stu-id="d8757-114">Position</span></span>|  
|----------|--------------|  
|<span data-ttu-id="d8757-115">Instruções</span><span class="sxs-lookup"><span data-stu-id="d8757-115">Instructions</span></span>|<span data-ttu-id="d8757-116">1</span><span class="sxs-lookup"><span data-stu-id="d8757-116">1</span></span>|  
|<span data-ttu-id="d8757-117">are</span><span class="sxs-lookup"><span data-stu-id="d8757-117">are</span></span>|<span data-ttu-id="d8757-118">2</span><span class="sxs-lookup"><span data-stu-id="d8757-118">2</span></span>|  
|<span data-ttu-id="d8757-119">applicable</span><span class="sxs-lookup"><span data-stu-id="d8757-119">applicable</span></span>|<span data-ttu-id="d8757-120">3</span><span class="sxs-lookup"><span data-stu-id="d8757-120">3</span></span>|  
|<span data-ttu-id="d8757-121">para</span><span class="sxs-lookup"><span data-stu-id="d8757-121">to</span></span>|<span data-ttu-id="d8757-122">4</span><span class="sxs-lookup"><span data-stu-id="d8757-122">4</span></span>|  
|<span data-ttu-id="d8757-123">these</span><span class="sxs-lookup"><span data-stu-id="d8757-123">these</span></span>|<span data-ttu-id="d8757-124">5</span><span class="sxs-lookup"><span data-stu-id="d8757-124">5</span></span>|  
|<span data-ttu-id="d8757-125">Adventure</span><span class="sxs-lookup"><span data-stu-id="d8757-125">Adventure</span></span>|<span data-ttu-id="d8757-126">6</span><span class="sxs-lookup"><span data-stu-id="d8757-126">6</span></span>|  
|<span data-ttu-id="d8757-127">Works</span><span class="sxs-lookup"><span data-stu-id="d8757-127">Works</span></span>|<span data-ttu-id="d8757-128">7</span><span class="sxs-lookup"><span data-stu-id="d8757-128">7</span></span>|  
|<span data-ttu-id="d8757-129">Cycles</span><span class="sxs-lookup"><span data-stu-id="d8757-129">Cycles</span></span>|<span data-ttu-id="d8757-130">8</span><span class="sxs-lookup"><span data-stu-id="d8757-130">8</span></span>|  
|<span data-ttu-id="d8757-131">modelos</span><span class="sxs-lookup"><span data-stu-id="d8757-131">models</span></span>|<span data-ttu-id="d8757-132">9</span><span class="sxs-lookup"><span data-stu-id="d8757-132">9</span></span>|  
  
 <span data-ttu-id="d8757-133">As palavras irrelevantes "are", "to" e "these", que estão nas posições 2, 4 e 5, são excluídas do índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d8757-133">The stopwords "are", "to", and "these" that are in positions 2, 4, and 5 are left out of the full-text index.</span></span> <span data-ttu-id="d8757-134">Contudo, sua informação posicional é mantida, sem afetar a posição das outras palavras da frase.</span><span class="sxs-lookup"><span data-stu-id="d8757-134">However, their positional information is maintained, thereby leaving the position of the other words in the phrase unaffected.</span></span>  
  
 <span data-ttu-id="d8757-135">As palavras irrelevantes são gerenciadas nos bancos de dados por meio de objetos denominados listas de palavras irrelevantes (stoplists).</span><span class="sxs-lookup"><span data-stu-id="d8757-135">Stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="d8757-136">Uma *lista de palavras irrelevantes (stoplist)* é uma lista que, quando associada a um índice de texto completo, é aplicada às consultas de texto completo desse índice.</span><span class="sxs-lookup"><span data-stu-id="d8757-136">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span>  
  
  
##  <a name="creating-a-stoplist"></a><a name="creating"></a><span data-ttu-id="d8757-137">Criando uma STOPLIST</span><span class="sxs-lookup"><span data-stu-id="d8757-137">Creating a Stoplist</span></span>  
 <span data-ttu-id="d8757-138">Você pode criar uma lista de palavras irrelevantes (stoplist) de qualquer uma destas formas:</span><span class="sxs-lookup"><span data-stu-id="d8757-138">You can create a stoplist in any of the following ways:</span></span>  
  
-   <span data-ttu-id="d8757-139">Usando a lista de palavras irrelevantes (stoplist) fornecida pelo sistema no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8757-139">Using the system-supplied stoplist in the database.</span></span> <span data-ttu-id="d8757-140">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é fornecido com uma lista de palavras irrelevantes do sistema que contém as palavras irrelevantes mais usadas em cada idioma com suporte, ou seja, em cada idioma associado a determinados separadores de palavra por padrão.</span><span class="sxs-lookup"><span data-stu-id="d8757-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ships with a system stoplist that contains the most commonly used stopwords for each supported language, that is for every language that is associated with given word breakers by default.</span></span> <span data-ttu-id="d8757-141">A lista de palavras irrelevantes do sistema contém palavras irrelevantes comuns para todos os idiomas com suporte.</span><span class="sxs-lookup"><span data-stu-id="d8757-141">The system stoplist contains common stopwords for all supported languages.</span></span>  <span data-ttu-id="d8757-142">Você pode copiar essa lista e personalizar sua cópia adicionando e removendo palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="d8757-142">You can copy the system stoplist, and customize your copy by adding and removing stopwords.</span></span>  
  
     <span data-ttu-id="d8757-143">A lista de palavras irrelevantes do sistema é instalada no banco de dados [Resource](../databases/resource-database.md) .</span><span class="sxs-lookup"><span data-stu-id="d8757-143">The system stoplist is installed in the [Resource](../databases/resource-database.md) database.</span></span>  
  
-   <span data-ttu-id="d8757-144">Criando sua própria lista de palavras irrelevantes e depois adicionando palavras irrelevantes a ela para qualquer idioma especificado.</span><span class="sxs-lookup"><span data-stu-id="d8757-144">Creating your own stoplist, and then adding stopwords to it for any language that you specify.</span></span> <span data-ttu-id="d8757-145">Você também pode descartar palavras irrelevantes da lista sempre que necessário.</span><span class="sxs-lookup"><span data-stu-id="d8757-145">You can also drop stopwords from your stoplist when necessary.</span></span>  
  
-   <span data-ttu-id="d8757-146">Usando uma lista de palavras irrelevantes personalizada existente de outro banco de dados na instância de servidor atual e, em seguida, adicionando ou descartando palavras irrelevantes conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d8757-146">Using an existing custom stoplist from any other database in the current server instance and then adding and dropping stopwords as necessary.</span></span>  
  
 <span data-ttu-id="d8757-147">**Par criar uma lista de palavras irrelevantes (stoplist)**</span><span class="sxs-lookup"><span data-stu-id="d8757-147">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="d8757-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
#### <a name="to-create-a-full-text-stoplist-in-management-studio"></a><span data-ttu-id="d8757-149">Para criar uma lista de palavras irrelevantes (stoplist) de texto completo no Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8757-149">To create a full-text stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="d8757-150">No Pesquisador de Objetos, expanda o servidor.</span><span class="sxs-lookup"><span data-stu-id="d8757-150">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="d8757-151">Expanda **Bancos de Dados**e o banco de dados no qual você deseja criar a lista de palavras irrelevantes (stoplist) de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d8757-151">Expand **Databases**, and then expand the database in which you want to create the full-text stoplist.</span></span>  
  
3.  <span data-ttu-id="d8757-152">Expanda **Armazenamento**e clique com o botão direito do mouse em **Lista de Palavras Irrelevantes de Texto Completo**.</span><span class="sxs-lookup"><span data-stu-id="d8757-152">Expand **Storage**, and then right-click **Full-Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="d8757-153">Selecione **Nova lista de palavras irrelevantes de texto completo**.</span><span class="sxs-lookup"><span data-stu-id="d8757-153">Select **New Full-Text Stoplist**.</span></span>  
  
5.  <span data-ttu-id="d8757-154">Especifique o nome da lista de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="d8757-154">Specify the stoplist name.</span></span>  
  
6.  <span data-ttu-id="d8757-155">Opcionalmente, especifique outra pessoa como o proprietário da lista de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="d8757-155">Optionally, specify someone else as the stoplist owner.</span></span>  
  
7.  <span data-ttu-id="d8757-156">Selecione uma das seguintes opções de criação de lista de palavras irrelevantes:</span><span class="sxs-lookup"><span data-stu-id="d8757-156">Select one of the following create stoplist options:</span></span>  
  
    -   <span data-ttu-id="d8757-157">**Criar uma lista de palavras irrelevantes vazia**</span><span class="sxs-lookup"><span data-stu-id="d8757-157">**Create an empty stoplist**</span></span>  
  
    -   <span data-ttu-id="d8757-158">**Criar com base na lista de palavras irrelevantes do sistema**</span><span class="sxs-lookup"><span data-stu-id="d8757-158">**Create from the system stoplist**</span></span>  
  
    -   <span data-ttu-id="d8757-159">**Criar com base em uma lista de palavras irrelevantes existente**</span><span class="sxs-lookup"><span data-stu-id="d8757-159">**Create from an existing full-text stoplist**</span></span>  
  
     <span data-ttu-id="d8757-160">Para obter mais informações, veja [Nova lista de palavras irrelevantes de texto completo &#40;Página Geral&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="d8757-160">For more information, see [New Full-Text Stoplist &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="d8757-161">**Para remover uma lista de palavras irrelevantes (stoplist)**</span><span class="sxs-lookup"><span data-stu-id="d8757-161">**To drop a stoplist**</span></span>  
  
-   [<span data-ttu-id="d8757-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
##  <a name="using-a-stoplist-in-full-text-queries"></a><a name="queries"></a><span data-ttu-id="d8757-163">Usando uma STOPLIST em consultas de texto completo</span><span class="sxs-lookup"><span data-stu-id="d8757-163">Using a Stoplist in Full-Text Queries</span></span>  
 <span data-ttu-id="d8757-164">Para usar uma lista de palavras irrelevantes (stoplist) em consultas, é preciso associá-la a um índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d8757-164">To make use of a stoplist in queries, you must associate it with a full-text index.</span></span> <span data-ttu-id="d8757-165">Você pode anexar uma lista de palavras irrelevantes a um índice de texto completo ao criá-lo ou pode alterá-lo posteriormente para adicionar uma lista de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="d8757-165">You can attach a stoplist to a full-text index when you create the index, or you can alter the index later to add a stoplist.</span></span>  
  
 <span data-ttu-id="d8757-166">**Para criar um índice de texto completo e associar uma lista de palavras irrelevantes a ele**</span><span class="sxs-lookup"><span data-stu-id="d8757-166">**To create a full-text index and associate a stoplist with it**</span></span>  
  
-   [<span data-ttu-id="d8757-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
 <span data-ttu-id="d8757-168">**Para associar uma lista de palavras irrelevantes a um índice de texto completo ou desassociá-la dele**</span><span class="sxs-lookup"><span data-stu-id="d8757-168">**To associate or disassociate a stoplist with an existing full-text index**</span></span>  
  
-   [<span data-ttu-id="d8757-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
 <span data-ttu-id="d8757-170">**Para suprimir uma mensagem de erro se palavras irrelevantes causarem falha em uma operação booliana em uma consulta de texto completo**</span><span class="sxs-lookup"><span data-stu-id="d8757-170">**To suppress an error message if stopwords cause a Boolean operation on a full-text query to fail**</span></span>  
  
-   [<span data-ttu-id="d8757-171">Opção de configuração de servidor para transformar palavras de ruído</span><span class="sxs-lookup"><span data-stu-id="d8757-171">transform noise words Server Configuration Option</span></span>](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md)  
  
  
##  <a name="viewing-stoplists-and-stoplist-metadata"></a><a name="viewing"></a><span data-ttu-id="d8757-172">Exibindo os metadados palavras irrelevantes e STOPLIST</span><span class="sxs-lookup"><span data-stu-id="d8757-172">Viewing Stoplists and Stoplist Metadata</span></span>  
 <span data-ttu-id="d8757-173">**Para exibir todas as palavras irrelevantes de uma lista de palavras irrelevantes (stoplist)**</span><span class="sxs-lookup"><span data-stu-id="d8757-173">**To view all the stopwords of a stoplist**</span></span>  
  
-   [<span data-ttu-id="d8757-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="d8757-175">**Para obter informações sobre todas as listas de palavras irrelevantes do banco de dados atual**</span><span class="sxs-lookup"><span data-stu-id="d8757-175">**To get information about all the stoplists in the current database**</span></span>  
  
-   [<span data-ttu-id="d8757-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="d8757-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="d8757-178">**Para exibir o resultado da geração de tokens de um separador de palavras, dicionário de sinônimos e combinação de lista de palavras irrelevantes (stoplist)**</span><span class="sxs-lookup"><span data-stu-id="d8757-178">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="d8757-179">sys. dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-179">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="changing-the-stopwords-in-a-stoplist"></a><a name="change"></a><span data-ttu-id="d8757-180">Alterando o palavras irrelevantes em umalist de parada</span><span class="sxs-lookup"><span data-stu-id="d8757-180">Changing the Stopwords in a Stoplist</span></span>  
 <span data-ttu-id="d8757-181">**Para adicionar ou remover palavras irrelevantes em uma lista de palavras irrelevantes (stoplist)**</span><span class="sxs-lookup"><span data-stu-id="d8757-181">**To add or drop stopwords from a stoplist**</span></span>  
  
-   [<span data-ttu-id="d8757-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8757-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
#### <a name="to-change-the-stopwords-in-a-stoplist-in-management-studio"></a><span data-ttu-id="d8757-183">Para alterar as palavras irrelevantes em uma lista de palavras irrelevantes (stoplist) no Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8757-183">To change the stopwords in a stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="d8757-184">No Pesquisador de Objetos, expanda o servidor.</span><span class="sxs-lookup"><span data-stu-id="d8757-184">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="d8757-185">Expanda **Bancos de Dados**e, em seguida, expanda o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d8757-185">Expand **Databases**, and then expand the database.</span></span>  
  
3.  <span data-ttu-id="d8757-186">Expanda **Armazenamento**e, depois, selecione **Listas de Palavras Irrelevantes de Texto Completo**.</span><span class="sxs-lookup"><span data-stu-id="d8757-186">Expand **Storage**, and then select **Full Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="d8757-187">Clique com o botão direito do mouse na lista de palavras irrelevantes cujas propriedades você deseja alterar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d8757-187">Right-click the stoplist whose properties you want to change, and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="d8757-188">Na caixa de diálogo [Propriedades da lista de palavras irrelevantes de texto completo](../../database-engine/full-text-stoplist-properties.md) :</span><span class="sxs-lookup"><span data-stu-id="d8757-188">In the [Full-Text Stoplist Properties](../../database-engine/full-text-stoplist-properties.md) dialog box:</span></span>  
  
    1.  <span data-ttu-id="d8757-189">Na caixa de listagem **Ação** , selecione uma das seguintes ações: **Adicionar palavra irrelevante**, **Excluir palavra irrelevante**, **Excluir todas as palavras irrelevantes**ou **Limpar lista de palavras irrelevantes**.</span><span class="sxs-lookup"><span data-stu-id="d8757-189">In the **Action** list box, select one of the following actions: **Add stopword**, **Delete stopword**, **Delete all stopwords**, or **Clear stoplist**.</span></span>  
  
    2.  <span data-ttu-id="d8757-190">Se a caixa de texto **Palavra irrelevante** estiver habilitada para a ação selecionada, insira uma única palavra irrelevante.</span><span class="sxs-lookup"><span data-stu-id="d8757-190">If the **Stopword** text box is enabled for the selected action, enter a single stopword.</span></span> <span data-ttu-id="d8757-191">Essa palavra irrelevante deve ser exclusiva; ou seja, ainda não deve estar na lista de palavras irrelevantes para o idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="d8757-191">This stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
    3.  <span data-ttu-id="d8757-192">Se a caixa de listagem **Idioma de texto completo** estiver habilitada para a ação selecionada, selecione um idioma.</span><span class="sxs-lookup"><span data-stu-id="d8757-192">If the **Full-text language** list box is enabled for the selected action, select a language.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
##  <a name="upgrading-noise-words-from-sql-server-2005"></a><a name="upgrade"></a><span data-ttu-id="d8757-193">Atualizando palavras de ruído do SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="d8757-193">Upgrading Noise Words from SQL Server 2005</span></span>  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] <span data-ttu-id="d8757-194">foram substituídas por palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="d8757-194">noise words have been replaced by stopwords.</span></span> <span data-ttu-id="d8757-195">Quando um banco de dados é atualizado no [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], os arquivos de palavras de ruído não são mais usados.</span><span class="sxs-lookup"><span data-stu-id="d8757-195">When a database is upgraded from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the noise-word files are no longer used.</span></span> <span data-ttu-id="d8757-196">No entanto, os arquivos de palavras de ruído são armazenados na pasta FTDATA\ FTNoiseThesaurusBak e você pode usá-los ao atualizar ou compilar as listas de palavras irrelevantes (stoplists) correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d8757-196">However, the noise-word files are stored in the FTDATA\ FTNoiseThesaurusBak folder, and you can use them later when updating or building the corresponding stoplists.</span></span> <span data-ttu-id="d8757-197">Para obter informações sobre como atualizar arquivos de palavras de ruído para listas de palavras irrelevantes, consulte [Atualizar pesquisa de texto completo](upgrade-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="d8757-197">For information about upgrading noise-word files to stoplists, see [Upgrade Full-Text Search](upgrade-full-text-search.md).</span></span>  
  
  
  
