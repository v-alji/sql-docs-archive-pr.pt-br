---
title: Propriedades do índice de texto completo (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.general.f1
ms.assetid: f4dff61c-8c2f-4ff9-abe4-70a34421448f
author: rothja
ms.author: jroth
ms.openlocfilehash: 61b9f2948df138c39230cf6f5787c395a364c695
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583787"
---
# <a name="full-text-index-properties-general-page"></a><span data-ttu-id="ec062-102">Propriedades do Índice de Texto Completo (página Geral)</span><span class="sxs-lookup"><span data-stu-id="ec062-102">Full-Text Index Properties (General Page)</span></span>
  <span data-ttu-id="ec062-103">**Para exibir ou alterar as propriedades modificáveis de um índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="ec062-103">**To view or change the modifiable properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="ec062-104">Gerenciar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="ec062-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="ec062-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="ec062-105">UI element list</span></span>  
 <span data-ttu-id="ec062-106">**Catálogo de texto completo**</span><span class="sxs-lookup"><span data-stu-id="ec062-106">**Full-Text Catalog**</span></span>  
 <span data-ttu-id="ec062-107">Exibe o nome do catálogo de texto completo ao qual o índice de texto completo está associado.</span><span class="sxs-lookup"><span data-stu-id="ec062-107">Displays the name of the full-text catalog with which the full-text index is associated.</span></span>  
  
 <span data-ttu-id="ec062-108">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="ec062-108">**Database**</span></span>  
 <span data-ttu-id="ec062-109">Exibe o nome do banco de dados no qual o índice de texto completo reside.</span><span class="sxs-lookup"><span data-stu-id="ec062-109">Displays the name of the database in which the full-text index resides.</span></span>  
  
 <span data-ttu-id="ec062-110">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="ec062-110">**Table**</span></span>  
 <span data-ttu-id="ec062-111">Exibe o nome da tabela na qual o índice de texto completo está definido.</span><span class="sxs-lookup"><span data-stu-id="ec062-111">Displays the name of the table on which the full-text index is defined.</span></span>  
  
 <span data-ttu-id="ec062-112">**Chave de Índice de Texto Completo**</span><span class="sxs-lookup"><span data-stu-id="ec062-112">**Full-Text Index Key**</span></span>  
 <span data-ttu-id="ec062-113">Exibe o nome da chave de índice de texto completo, que é um índice exclusivo em uma única coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="ec062-113">Displays the name of the full-text index key, which is a unique index on a single column of the table.</span></span>  
  
 <span data-ttu-id="ec062-114">**Status da População de Texto Completo da Tabela**</span><span class="sxs-lookup"><span data-stu-id="ec062-114">**Table Full-Text Populate Status**</span></span>  
 <span data-ttu-id="ec062-115">Exibe o status da população da tabela indexada de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ec062-115">Displays the population status of the full-text indexed table.</span></span>  
  
 <span data-ttu-id="ec062-116">Os valores possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="ec062-116">The possible values are as follows:</span></span>  
  
 <span data-ttu-id="ec062-117">0 = Ocioso</span><span class="sxs-lookup"><span data-stu-id="ec062-117">0 = Idle.</span></span>  
  
 <span data-ttu-id="ec062-118">1 = População completa em andamento.</span><span class="sxs-lookup"><span data-stu-id="ec062-118">1 = Full population is in progress.</span></span>  
  
 <span data-ttu-id="ec062-119">2 = População incremental em andamento.</span><span class="sxs-lookup"><span data-stu-id="ec062-119">2 = Incremental population is in progress.</span></span>  
  
 <span data-ttu-id="ec062-120">3 = Propagação de alterações controladas em andamento.</span><span class="sxs-lookup"><span data-stu-id="ec062-120">3 = Propagation of tracked changes is in progress.</span></span>  
  
 <span data-ttu-id="ec062-121">4 = Índice de atualização em segundo plano em andamento, como o controle de alteração automática.</span><span class="sxs-lookup"><span data-stu-id="ec062-121">4 = Background update index is in progress, such as automatic change tracking.</span></span>  
  
 <span data-ttu-id="ec062-122">5 = Indexação de texto completo acelerado ou pausado.</span><span class="sxs-lookup"><span data-stu-id="ec062-122">5 = Full-text indexing is throttled or paused.</span></span>  
  
 <span data-ttu-id="ec062-123">**Índice de Texto Completo Ativo**</span><span class="sxs-lookup"><span data-stu-id="ec062-123">**Active Full-Text Index**</span></span>  
 <span data-ttu-id="ec062-124">Indica se a tabela tem um índice de texto completo ativo.</span><span class="sxs-lookup"><span data-stu-id="ec062-124">Indicates whether the table has an active full-text index.</span></span>  
  
 <span data-ttu-id="ec062-125">1 = True</span><span class="sxs-lookup"><span data-stu-id="ec062-125">1 = True</span></span>  
  
 <span data-ttu-id="ec062-126">0 = False</span><span class="sxs-lookup"><span data-stu-id="ec062-126">0 = False</span></span>  
  
 <span data-ttu-id="ec062-127">**Grupo de arquivos do índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="ec062-127">**Full-Text Index Filegroup**</span></span>  
 <span data-ttu-id="ec062-128">O grupo de arquivos ao qual o índice de texto completo pertence.</span><span class="sxs-lookup"><span data-stu-id="ec062-128">The filegroup to which the full-text index belongs.</span></span>  
  
 <span data-ttu-id="ec062-129">**Lista de palavras irrelevantes de índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="ec062-129">**Full-Text Index Stoplist**</span></span>  
 <span data-ttu-id="ec062-130">A lista de palavras irrelevantes associada ao índice de texto completo no momento.</span><span class="sxs-lookup"><span data-stu-id="ec062-130">The stoplist that is currently associated with the full-text index.</span></span> <span data-ttu-id="ec062-131">Uma lista de palavras irrelevantes contém [palavras irrelevantes](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="ec062-131">A stoplist is a list of [stopwords](../relational-databases/search/full-text-search.md).</span></span> <span data-ttu-id="ec062-132">A lista de palavras irrelevantes associada a um índice de texto completo, se houver, é aplicada a consultas de texto completo nesse índice.</span><span class="sxs-lookup"><span data-stu-id="ec062-132">The stoplist associated with a full-text index, if any, is applied to full-text queries on that index.</span></span> <span data-ttu-id="ec062-133">Você pode remover a lista de palavras irrelevantes do índice selecionando-a **\<OFF>** de uma das listas, ou pode selecionar um diferentelist **\<SYSTEM>** . indica a lista de palavras irrelevantes do sistema.</span><span class="sxs-lookup"><span data-stu-id="ec062-133">You can remove the stoplist from the index by selecting **\<OFF>** from the list, or you can select a different stoplist; **\<SYSTEM>** indicates the system stoplist.</span></span>  
  
 <span data-ttu-id="ec062-134">**Par criar uma lista de palavras irrelevantes (stoplist)**</span><span class="sxs-lookup"><span data-stu-id="ec062-134">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="ec062-135">Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes (stoplists) para pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="ec062-135">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
 <span data-ttu-id="ec062-136">**Lista de propriedades de pesquisa**</span><span class="sxs-lookup"><span data-stu-id="ec062-136">**Search Property List**</span></span>  
 <span data-ttu-id="ec062-137">A lista de propriedades de pesquisa associada atualmente o índice de texto completo, se houver algum.</span><span class="sxs-lookup"><span data-stu-id="ec062-137">The search property list that is currently associated with the full-text index, if any.</span></span> <span data-ttu-id="ec062-138">Uma lista de propriedades de pesquisa especifica um conjunto de propriedades de documento que são incluídos no índice de texto completo quando ele é preenchido.</span><span class="sxs-lookup"><span data-stu-id="ec062-138">A search property list specifies a set of document properties that are included in the associated full-text index when it is populated.</span></span> <span data-ttu-id="ec062-139">Para obter mais informações, veja [Pesquisar propriedades de documento com listas de propriedades de pesquisa](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="ec062-139">For more information, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
 <span data-ttu-id="ec062-140">**\<Off>** indica que atualmente não há lista de propriedades de pesquisa associada ao índice.</span><span class="sxs-lookup"><span data-stu-id="ec062-140">**\<Off>** indicates that there is currently no search property list associated with the index.</span></span> <span data-ttu-id="ec062-141">Você pode remover a lista de propriedades de pesquisa atual do índice selecionando **\<Off>** na lista ou pode selecionar uma lista de propriedades de pesquisa diferente na lista.</span><span class="sxs-lookup"><span data-stu-id="ec062-141">You can remove the current search property list from the index by selecting **\<Off>** from the list, or you can select a different search property list from the list.</span></span> <span data-ttu-id="ec062-142">Somente as listas de propriedades de pesquisa do banco de dados atual são relacionadas aqui.</span><span class="sxs-lookup"><span data-stu-id="ec062-142">Only search property lists in the current database are listed here.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec062-143">Você pode associar uma determinada lista de propriedades de pesquisa a mais de um índice de texto completo no mesmo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec062-143">You can associate a given search property list with more than one full-text index in the same database.</span></span>  
  
 <span data-ttu-id="ec062-144">**Para criar uma lista de propriedades de pesquisa**</span><span class="sxs-lookup"><span data-stu-id="ec062-144">**To create a search property list**</span></span>  
  
-   [<span data-ttu-id="ec062-145">Pesquisar propriedades de documento com listas de propriedades de pesquisa</span><span class="sxs-lookup"><span data-stu-id="ec062-145">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
 <span data-ttu-id="ec062-146">**Contagem de Itens de Texto Completo da Tabela**</span><span class="sxs-lookup"><span data-stu-id="ec062-146">**Table Full-Text Item Count**</span></span>  
 <span data-ttu-id="ec062-147">Indica o número de linhas com indexação de texto completo bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="ec062-147">Indicates the number of rows that were full-text indexed successfully.</span></span>  
  
 <span data-ttu-id="ec062-148">Essa propriedade corresponde à propriedade `TableFulltextItemCount` retornada pela função [!INCLUDE[tsql](../includes/tsql-md.md)] OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="ec062-148">This property corresponds to the `TableFulltextItemCount` property returned by the OBJECTPROPERTYEX [!INCLUDE[tsql](../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="ec062-149">**Documentos de Texto Completo da Tabela Processados**</span><span class="sxs-lookup"><span data-stu-id="ec062-149">**Table Full-Text Docs Processed**</span></span>  
 <span data-ttu-id="ec062-150">Exibe o número de linhas processadas desde o início da indexação de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ec062-150">Displays the number of rows that have been processed since the start of full-text indexing.</span></span> <span data-ttu-id="ec062-151">Em uma tabela que está sendo indexada para pesquisa de texto completo, todas as colunas de uma linha são consideradas parte de um documento a ser indexado.</span><span class="sxs-lookup"><span data-stu-id="ec062-151">In a table that is being indexed for full-text search, all the columns of one row are considered as part of one document to be indexed.</span></span> <span data-ttu-id="ec062-152">Linhas excluídas não são contadas.</span><span class="sxs-lookup"><span data-stu-id="ec062-152">Deleted rows are not counted.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec062-153">0</span><span class="sxs-lookup"><span data-stu-id="ec062-153">0</span></span>|<span data-ttu-id="ec062-154">Indica que a indexação de texto completo está concluída e que não há população ativa.</span><span class="sxs-lookup"><span data-stu-id="ec062-154">Indicates that full-text indexing is completed and there is no active population.</span></span>|  
|<span data-ttu-id="ec062-155">> 0</span><span class="sxs-lookup"><span data-stu-id="ec062-155">> 0</span></span>|<span data-ttu-id="ec062-156">Para uma população ativa, indica o número de documentos processados pelas operações de inserção ou de atualização desde qualquer uma das seguintes opções: uma população, a habilitação do controle de alterações com população de índice de atualização em segundo plano (como controle de alterações automáticas), a alteração do esquema de índice de texto completo, a reconstrução do catálogo de texto completo, o reinício da instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], etc.</span><span class="sxs-lookup"><span data-stu-id="ec062-156">For an active population, indicates the number of documents processed by insert or update operations since any of the following: a population, enabling of change tracking with background update index population (such as auto change tracking), changing the full-text index schema, rebuilding the full-text catalog, restarting the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and so forth.</span></span>|  
  
 <span data-ttu-id="ec062-157">**Alterações de Texto Completo Pendentes da Tabela**</span><span class="sxs-lookup"><span data-stu-id="ec062-157">**Table Full-Text Pending Changes**</span></span>  
 <span data-ttu-id="ec062-158">Número de entradas de controle de alterações pendentes a serem processadas.</span><span class="sxs-lookup"><span data-stu-id="ec062-158">Number of pending change tracking entries to process.</span></span>  
  
 <span data-ttu-id="ec062-159">0 = o controle de alterações não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ec062-159">0 = change tracking is not enabled.</span></span>  
  
 <span data-ttu-id="ec062-160">NULL = A tabela não tem um índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ec062-160">NULL = Table does not have a full-text index.</span></span>  
  
 <span data-ttu-id="ec062-161">**Contagem de Falhas de Texto Completo da Tabela**</span><span class="sxs-lookup"><span data-stu-id="ec062-161">**Table Full-Text Fail Count**</span></span>  
 <span data-ttu-id="ec062-162">O número de linhas que a pesquisa de texto completo não indexou.</span><span class="sxs-lookup"><span data-stu-id="ec062-162">The number of rows that full-text search did not index.</span></span>  
  
 <span data-ttu-id="ec062-163">0 = A população foi concluída.</span><span class="sxs-lookup"><span data-stu-id="ec062-163">0 = The population has completed.</span></span>  
  
 <span data-ttu-id="ec062-164">\>0 = um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="ec062-164">\>0 = One of the following:</span></span>  
  
-   <span data-ttu-id="ec062-165">O número de documentos que não foram indexados desde o início da população do controle de alterações completa, incremental ou manual.</span><span class="sxs-lookup"><span data-stu-id="ec062-165">The number of documents that were not indexed since the start of full, incremental, or manual change tracking population.</span></span>  
  
-   <span data-ttu-id="ec062-166">Para o controle de alterações com índice de atualização em segundo plano, o número de linhas que não foram indexadas desde o início ou reinício da população.</span><span class="sxs-lookup"><span data-stu-id="ec062-166">For change tracking with background update index, the number of rows that were not indexed since the start of the population, or the restart of the population.</span></span> <span data-ttu-id="ec062-167">A causa disso pode ter sido uma alteração de esquema, a reconstrução do catálogo, a reinicialização do servidor e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="ec062-167">This could be caused by a schema change, rebuild of the catalog, server restart, and so on</span></span>  
  
 <span data-ttu-id="ec062-168">**Indexação de texto completo habilitada**</span><span class="sxs-lookup"><span data-stu-id="ec062-168">**Full-Text Indexing Enabled**</span></span>  
 <span data-ttu-id="ec062-169">Especifica se a indexação de texto completo está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ec062-169">Specifies whether full-text indexing is enabled.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec062-170">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="ec062-170">**True**</span></span>|<span data-ttu-id="ec062-171">Habilitada</span><span class="sxs-lookup"><span data-stu-id="ec062-171">Enabled</span></span>|  
|<span data-ttu-id="ec062-172">**Falso**</span><span class="sxs-lookup"><span data-stu-id="ec062-172">**False**</span></span>|<span data-ttu-id="ec062-173">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="ec062-173">Disabled</span></span>|  
  
 <span data-ttu-id="ec062-174">**Controle de alterações**</span><span class="sxs-lookup"><span data-stu-id="ec062-174">**Change Tracking**</span></span>  
 <span data-ttu-id="ec062-175">Especifica se a tabela tem o controle de alterações de texto completo habilitado, e nesse caso, de que tipo.</span><span class="sxs-lookup"><span data-stu-id="ec062-175">Specifies whether the table has full-text change-tracking enabled, and if so, what kind.</span></span> <span data-ttu-id="ec062-176">O controle de alterações de texto completo mantém um registro das linhas que foram modificadas em uma tabela ou a exibição indexada que foi configurada para indexação de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ec062-176">Full-text change tracking maintains a record of the rows that have been modified in a table or indexed view that has been set up for full-text indexing.</span></span> <span data-ttu-id="ec062-177">Essas alterações podem ser propagadas para o índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ec062-177">These changes can be propagated to the full-text index.</span></span>  
  
 <span data-ttu-id="ec062-178">Os valores do **Controle de Alterações** são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="ec062-178">The **Change Tracking** values are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec062-179">**Desativado**</span><span class="sxs-lookup"><span data-stu-id="ec062-179">**Off**</span></span>|<span data-ttu-id="ec062-180">O índice de texto completo não é atualizado com alterações nos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="ec062-180">The full-text index is not updated with changes to the underlying data.</span></span>|  
|<span data-ttu-id="ec062-181">**Manual**</span><span class="sxs-lookup"><span data-stu-id="ec062-181">**Manual**</span></span>|<span data-ttu-id="ec062-182">O índice de texto completo não é atualizado automaticamente conforme as alterações ocorrem nos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="ec062-182">The full-text index is not updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="ec062-183">Porém, as alterações aos dados subjacentes são mantidas e você pode propagá-los para o</span><span class="sxs-lookup"><span data-stu-id="ec062-183">However, changes to the underlying data are maintained, and you can propagate them to the .</span></span> <span data-ttu-id="ec062-184">índice de texto completo ou em uma agenda que usa o SQL Server Agent ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="ec062-184">full-text index either on a schedule using SQL Server Agent or manually.</span></span>|  
|<span data-ttu-id="ec062-185">**Automática**</span><span class="sxs-lookup"><span data-stu-id="ec062-185">**Automatic**</span></span>|<span data-ttu-id="ec062-186">O índice de texto completo é atualizado automaticamente conforme as alterações ocorrem nos dados subjacentes na tabela base.</span><span class="sxs-lookup"><span data-stu-id="ec062-186">The full-text index is updated automatically as changes occur to the underlying data in the base table.</span></span>|  
  
 <span data-ttu-id="ec062-187">**Repopular o índice**</span><span class="sxs-lookup"><span data-stu-id="ec062-187">**Repopulate index**</span></span>  
 <span data-ttu-id="ec062-188">Clique para iniciar uma população no índice de texto completo ao sair da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ec062-188">Click to start a population on the full-text index on exiting the dialog box.</span></span> <span data-ttu-id="ec062-189">Selecione um dos seguintes tipos de população:</span><span class="sxs-lookup"><span data-stu-id="ec062-189">Select one of the following types of population:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec062-190">**Full**</span><span class="sxs-lookup"><span data-stu-id="ec062-190">**Full**</span></span>|<span data-ttu-id="ec062-191">Durante uma população completa de uma tabela, as entradas de índice são criadas para todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="ec062-191">During a full population of a table, index entries are built for all the rows.</span></span>|  
|<span data-ttu-id="ec062-192">**Lucrativ**</span><span class="sxs-lookup"><span data-stu-id="ec062-192">**Incremental**</span></span>|<span data-ttu-id="ec062-193">A população incremental atualiza o índice de texto completo para linhas adicionadas, excluídas ou modificadas após a última população ou enquanto a última população estava em andamento.</span><span class="sxs-lookup"><span data-stu-id="ec062-193">Incremental population updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="ec062-194">A execução de uma população incremental requer que a tabela base contenha uma coluna do tipo de dados `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="ec062-194">Performing an incremental population requires that the base table contain a column of the `timestamp` data type.</span></span>|  
|<span data-ttu-id="ec062-195">**Atualização**</span><span class="sxs-lookup"><span data-stu-id="ec062-195">**Update**</span></span>|<span data-ttu-id="ec062-196">O índice de texto completo é atualizado sempre que os dados da tabela base são modificados.</span><span class="sxs-lookup"><span data-stu-id="ec062-196">The full-text index is updated whenever the data in the base table is modified.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec062-197">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec062-197">See Also</span></span>  
 [<span data-ttu-id="ec062-198">Iniciar a pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="ec062-198">Get Started with Full-Text Search</span></span>](../relational-databases/search/get-started-with-full-text-search.md)  
  
  
