---
title: Usar o Assistente para Indexação de Texto Completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextindexingwizard.selecttablecolumns.f1
- sql12.swb.fulltextindexingwizard.welcome.f1
- sql12.swb.fulltextindexingwizard.selectacatalog.f1
- sql12.swb.fulltextindexingwizard.progress.f1
- sql12.swb.fulltextindexingwizard.selectorcreatepopschedules.f1
- sql12.swb.fulltextindexingwizard.selectatableorview.f1
- sql12.swb.fulltextindexingwizard.selectchangetracking.f1
- sql12.swb.fulltextindexingwizard.selectanindex.f1
- sql12.swb.fulltextindexingwizard.summary.f1
helpviewer_keywords:
- Full-Text Indexing Wizard
- full-text search [SQL Server], Full-Text Indexing Wizard
ms.assetid: 3e9d9605-6525-4781-9168-fdaa06db3459
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ef8a23c4d85cbe47bf6bdb47eb3f45723f1559d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679826"
---
# <a name="use-the-full-text-indexing-wizard"></a><span data-ttu-id="28d0d-102">Usar o Assistente para Indexação de Texto Completo</span><span class="sxs-lookup"><span data-stu-id="28d0d-102">Use the Full-Text Indexing Wizard</span></span>
  <span data-ttu-id="28d0d-103">O Assistente para Indexação de Texto Completo guia você por uma série de etapas planejadas para ajudá-lo a criar um índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-103">The Full-Text Indexing Wizard walks you through a series of steps designed to help you create a full-text index.</span></span>  
  
#### <a name="to-use-the-full-text-indexing-wizard"></a><span data-ttu-id="28d0d-104">Para usar o Assistente para Indexação de Texto Completo</span><span class="sxs-lookup"><span data-stu-id="28d0d-104">To use the Full-Text Indexing wizard</span></span>  
  
1.  <span data-ttu-id="28d0d-105">No Pesquisador de Objetos, clique com o botão direito do mouse na tabela em que você deseja criar um **Índice de Texto Completo**e clique em **Índice de Texto Completo**.</span><span class="sxs-lookup"><span data-stu-id="28d0d-105">In Object Explorer, right-click the table on which you want to create a full-text index, point to **Full-Text index**, and then click **Define Full-Text Index**.</span></span>  
  
     <span data-ttu-id="28d0d-106">**Índice exclusivo**</span><span class="sxs-lookup"><span data-stu-id="28d0d-106">**Unique Index**</span></span>  
     <span data-ttu-id="28d0d-107">Selecione um índice na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="28d0d-107">Select an index from the drop down list.</span></span> <span data-ttu-id="28d0d-108">O índice deve ser um índice não nulo, exclusivo e de coluna de chave única.</span><span class="sxs-lookup"><span data-stu-id="28d0d-108">The index must be a single-key-column, unique, non-nullable index.</span></span> <span data-ttu-id="28d0d-109">Selecione o menor índice de chave exclusiva para a chave exclusiva de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-109">Select the smallest unique key index for the full-text unique key.</span></span> <span data-ttu-id="28d0d-110">Para obter um melhor desempenho, é recomendável um índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="28d0d-110">For best performance, a clustered index is recommended.</span></span>  
  
     <span data-ttu-id="28d0d-111">**Colunas disponíveis**</span><span class="sxs-lookup"><span data-stu-id="28d0d-111">**Available Columns**</span></span>  
     <span data-ttu-id="28d0d-112">Para incluir uma coluna no índice, marque a caixa de seleção do lado do nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="28d0d-112">To include a column in the index, select the check box next to the column name.</span></span> <span data-ttu-id="28d0d-113">As colunas que não são qualificadas para indexação de texto completo aparecem em cinza com suas caixas de seleção desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="28d0d-113">Columns that are not eligible for full-text indexing appear in grey with their check boxes disabled.</span></span>  
  
     <span data-ttu-id="28d0d-114">**Idioma do separador de palavras**</span><span class="sxs-lookup"><span data-stu-id="28d0d-114">**Language for Word Breaker**</span></span>  
     <span data-ttu-id="28d0d-115">Selecione um idioma da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="28d0d-115">Select a language from the drop-down list.</span></span> <span data-ttu-id="28d0d-116">Essa seleção será usada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para indicar os separadores de palavras corretos para o índice.</span><span class="sxs-lookup"><span data-stu-id="28d0d-116">This choice will be used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to identify the correct word breakers for the index.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="28d0d-117">usa separadores de palavras para identificar limites das palavras nos dados de indexação de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-117">uses word breakers to identify word boundaries in the full-text indexed data.</span></span>  
  
     <span data-ttu-id="28d0d-118">**Coluna de tipo**</span><span class="sxs-lookup"><span data-stu-id="28d0d-118">**Type Column**</span></span>  
     <span data-ttu-id="28d0d-119">Selecione o nome da coluna que possui o tipo de documento de coluna que está sendo indexado com texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-119">Select the name of the column that holds the document type of column being full-text indexed.</span></span>  
  
     <span data-ttu-id="28d0d-120">A **coluna tipo** só é habilitada quando a coluna denominada na coluna **colunas disponíveis** é do tipo `varbinary(max)` ou `image` .</span><span class="sxs-lookup"><span data-stu-id="28d0d-120">The  **Type Column** is only enabled when the column named in the **Available Columns** column is of type `varbinary(max)` or `image`.</span></span>  
  
     <span data-ttu-id="28d0d-121">**Semântica Estatística**</span><span class="sxs-lookup"><span data-stu-id="28d0d-121">**Statistical Semantics**</span></span>  
     <span data-ttu-id="28d0d-122">Especifique se habilitará a indexação semântica da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="28d0d-122">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="28d0d-123">Para obter mais informações, veja [Pesquisa semântica &#40;SQL Server&#41;](semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28d0d-123">For more information, see [Semantic Search &#40;SQL Server&#41;](semantic-search-sql-server.md).</span></span>  
  
     <span data-ttu-id="28d0d-124">Se você selecionar um **Idioma** antes de selecionar **Semântica Estatística**, e o idioma selecionado não tiver um Modelo de Idioma Semântico associado, a caixa de seleção **Semântica Estatística** será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="28d0d-124">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="28d0d-125">Se você selecionar **Semântica Estatística** antes de selecionar um **Idioma**, os idiomas disponíveis na caixa de combinação suspensa serão restringidos a esses para os quais o Modelo de Idioma Semântico dá suporte.</span><span class="sxs-lookup"><span data-stu-id="28d0d-125">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
2.  <span data-ttu-id="28d0d-126">Selecione as opções de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="28d0d-126">Select the change tracking options.</span></span>  
  
     <span data-ttu-id="28d0d-127">**Automaticamente**</span><span class="sxs-lookup"><span data-stu-id="28d0d-127">**Automatically**</span></span>  
     <span data-ttu-id="28d0d-128">Selecione esse botão de opção para que o índice de texto completo seja atualizado automaticamente à medida que ocorrem alterações nos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="28d0d-128">Select this radio button to have the full-text index updated automatically as changes occur to the underlying data.</span></span>  
  
     <span data-ttu-id="28d0d-129">**Manualmente**</span><span class="sxs-lookup"><span data-stu-id="28d0d-129">**Manually**</span></span>  
     <span data-ttu-id="28d0d-130">Selecione esse botão de opção se não deseja que o índice de texto completo seja atualizado automaticamente à medida que ocorrem alterações nos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="28d0d-130">Select this radio button if you do not want the full-text index to be updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="28d0d-131">São mantidas as alterações nos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="28d0d-131">Changes to the underlying data are maintained.</span></span> <span data-ttu-id="28d0d-132">Porém, para aplicar as alterações no índice de texto completo você deve iniciar ou agendar esse processo manualmente.</span><span class="sxs-lookup"><span data-stu-id="28d0d-132">However, to apply the changes to the full-text index you must start or schedule this process manually.</span></span>  
  
     <span data-ttu-id="28d0d-133">**Não rastrear alterações**</span><span class="sxs-lookup"><span data-stu-id="28d0d-133">**Do not track changes**</span></span>  
     <span data-ttu-id="28d0d-134">Selecione esse botão de opção se não deseja que o índice de texto completo seja atualizado com as alterações nos dados subjacentes.</span><span class="sxs-lookup"><span data-stu-id="28d0d-134">Select this radio button if you do not want the full-text index to be updated with changes to the underlying data.</span></span>  
  
     <span data-ttu-id="28d0d-135">**Iniciar população completa quando o índice é criado**</span><span class="sxs-lookup"><span data-stu-id="28d0d-135">**Start full population when index is created**</span></span>  
     <span data-ttu-id="28d0d-136">Selecione esse botão de opção para iniciar uma população completa à conclusão com êxito desse assistente.</span><span class="sxs-lookup"><span data-stu-id="28d0d-136">Select this radio button to kick off a full population at the successful completion of this wizard.</span></span> <span data-ttu-id="28d0d-137">Isso consistirá na criação da estrutura de índice de texto completo no catálogo e em populá-lo com dados indexados de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-137">This will consist of creating the full-text index structure in the catalog and populating it with full-text indexed data.</span></span>  
  
3.  <span data-ttu-id="28d0d-138">Selecione o catálogo, o grupo de arquivos de índice e a lista de palavras irrelevantes (stoplist).</span><span class="sxs-lookup"><span data-stu-id="28d0d-138">Select the catalog, index filegroup and stoplist.</span></span>  
  
     <span data-ttu-id="28d0d-139">**Selecione o catálogo de texto completo**</span><span class="sxs-lookup"><span data-stu-id="28d0d-139">**Select full-text catalog**</span></span>  
     <span data-ttu-id="28d0d-140">Selecione um catálogo de texto completo na lista.</span><span class="sxs-lookup"><span data-stu-id="28d0d-140">Select a full-text catalog from the list.</span></span> <span data-ttu-id="28d0d-141">O catálogo padrão para o banco de dados será o item selecionado por padrão na lista.</span><span class="sxs-lookup"><span data-stu-id="28d0d-141">The default catalog for the database will be the selected item by default in the list.</span></span> <span data-ttu-id="28d0d-142">Se não houver catálogos disponíveis, a lista permanecerá desabilitada e a caixa de seleção **Criar um novo catálogo** estará marcada e desabilitada.</span><span class="sxs-lookup"><span data-stu-id="28d0d-142">If no catalogs are available, the list will be disabled, and the **Create a new catalog** checkbox will be checked and disabled.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="28d0d-143">**Criar um novo catálogo**</span><span class="sxs-lookup"><span data-stu-id="28d0d-143">**Create a new catalog**</span></span>|<span data-ttu-id="28d0d-144">Marque essa caixa de seleção para criar um novo catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-144">Select to create a new full-text catalog.</span></span>|  
  
     <span data-ttu-id="28d0d-145">**Nome**</span><span class="sxs-lookup"><span data-stu-id="28d0d-145">**Name**</span></span>  
     <span data-ttu-id="28d0d-146">Digite um nome para o novo catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-146">Enter a name for the new full-text catalog.</span></span>  
  
     <span data-ttu-id="28d0d-147">**Definir como catálogo padrão**</span><span class="sxs-lookup"><span data-stu-id="28d0d-147">**Set as default catalog**</span></span>  
     <span data-ttu-id="28d0d-148">Marque para tornar este o catálogo padrão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="28d0d-148">Select to make the catalog the default for this database.</span></span>  
  
     <span data-ttu-id="28d0d-149">**Distinção de acentos**</span><span class="sxs-lookup"><span data-stu-id="28d0d-149">**Accent sensitivity**</span></span>  
     <span data-ttu-id="28d0d-150">Especifique se o novo catálogo diferenciará caracteres com e sem acentos.</span><span class="sxs-lookup"><span data-stu-id="28d0d-150">Specify whether the new catalog will be accent-sensitive or accent-insensitive.</span></span> <span data-ttu-id="28d0d-151">Se o banco de dados distinguir acentos, por padrão, **Com Distinção** será selecionado.</span><span class="sxs-lookup"><span data-stu-id="28d0d-151">If the database is accent-sensitive, **Sensitive** will be selected by default.</span></span>  
  
     <span data-ttu-id="28d0d-152">**Selecionar grupo de arquivos de índice**</span><span class="sxs-lookup"><span data-stu-id="28d0d-152">**Select index filegroup**</span></span>  
     <span data-ttu-id="28d0d-153">Especifique o grupo de arquivos no qual criar o índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-153">Specify the filegroup on which to create the full-text index.</span></span>  
  
     <span data-ttu-id="28d0d-154">Selecione um destes valores:</span><span class="sxs-lookup"><span data-stu-id="28d0d-154">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="28d0d-155">Valor</span><span class="sxs-lookup"><span data-stu-id="28d0d-155">Value</span></span>|<span data-ttu-id="28d0d-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="28d0d-156">Description</span></span>|  
    |-----------|-----------------|  
    |**\<default>**|<span data-ttu-id="28d0d-157">Se a tabela ou exibição não for particionada, selecione para usar o mesmo grupo de arquivos da tabela ou exibição subjacente.</span><span class="sxs-lookup"><span data-stu-id="28d0d-157">If the table or view is not partitioned, select to use the same filegroup as the underlying table or view.</span></span> <span data-ttu-id="28d0d-158">Se a tabela ou exibição for particionada, o grupo de arquivos primário será utilizado.</span><span class="sxs-lookup"><span data-stu-id="28d0d-158">If the table or view is partitioned, the primary filegroup is used.</span></span>|  
    |<span data-ttu-id="28d0d-159">**PRIMARY**</span><span class="sxs-lookup"><span data-stu-id="28d0d-159">**PRIMARY**</span></span>|<span data-ttu-id="28d0d-160">Selecione para usar o grupo de arquivos primário para o novo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-160">Select to use the primary filegroup for the new full-text index.</span></span>|  
    |<span data-ttu-id="28d0d-161">*grupo de arquivos padrão especificado pelo usuário*</span><span class="sxs-lookup"><span data-stu-id="28d0d-161">*user-specified default filegroup*</span></span>|<span data-ttu-id="28d0d-162">Se existir uma lista de palavras irrelevantes padrão definida pelo usuário, selecione seu nome na lista para usar esse grupo de arquivos para o novo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-162">If a user-defined default stoplist exists, select its name from the list to use that filegroup for the new full-text index.</span></span>|  
  
     <span data-ttu-id="28d0d-163">**Selecionar lista de palavras irrelevantes de texto completo**</span><span class="sxs-lookup"><span data-stu-id="28d0d-163">**Select full-text stoplist**</span></span>  
     <span data-ttu-id="28d0d-164">Especifique uma lista de palavras irrelevantes para usar no índice de texto completo ou desabilitar seu uso.</span><span class="sxs-lookup"><span data-stu-id="28d0d-164">Specify a stoplist to use for the full-text index, or disable stoplist use.</span></span>  
  
     <span data-ttu-id="28d0d-165">No [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e nas versões posteriores, as palavras irrelevantes (stopwords) são gerenciadas em bancos de dados por meio de objetos chamados listas de palavras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="28d0d-165">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="28d0d-166">Uma *lista de palavras irrelevantes (stoplist)* é uma lista que, quando associada a um índice de texto completo, é aplicada às consultas de texto completo desse índice.</span><span class="sxs-lookup"><span data-stu-id="28d0d-166">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span> <span data-ttu-id="28d0d-167">Para obter mais informações, veja [Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes para pesquisa de texto completo](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="28d0d-167">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span></span>  
  
     <span data-ttu-id="28d0d-168">Selecione um destes valores:</span><span class="sxs-lookup"><span data-stu-id="28d0d-168">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="28d0d-169">Valor</span><span class="sxs-lookup"><span data-stu-id="28d0d-169">Value</span></span>|<span data-ttu-id="28d0d-170">Descrição</span><span class="sxs-lookup"><span data-stu-id="28d0d-170">Description</span></span>|  
    |-----------|-----------------|  
    |**\<system>**|<span data-ttu-id="28d0d-171">Selecione para usar a lista de palavras irrelevantes do sistema no novo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-171">Select to use the system stoplist on the new full-text index.</span></span> <span data-ttu-id="28d0d-172">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="28d0d-172">This is the default</span></span>|  
    |**\<off>**|<span data-ttu-id="28d0d-173">Selecione para desabilitar as listas de palavras irrelevantes para o novo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-173">Select to disable stoplists for the new full-text index.</span></span>|  
    |<span data-ttu-id="28d0d-174">*user-defined-stoplist-name*</span><span class="sxs-lookup"><span data-stu-id="28d0d-174">*user-defined-stoplist-name*</span></span>|<span data-ttu-id="28d0d-175">A lista exibe o nome de cada lista de palavras irrelevantes definida pelo usuário, se houver alguma, que foi criada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="28d0d-175">The list displays the name of each user-defined stoplist, if any, that has been created on the database.</span></span> <span data-ttu-id="28d0d-176">Selecione qualquer lista de palavras irrelevantes definida pelo usuário para usar no novo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-176">Select any user-defined stoplist to use for the new full-text index.</span></span>|  
  
4.  <span data-ttu-id="28d0d-177">Opcionalmente, defina a agenda de população.</span><span class="sxs-lookup"><span data-stu-id="28d0d-177">Optionally, define the population schedule.</span></span> <span data-ttu-id="28d0d-178">As operações de indexação começarão imediatamente, a menos que tenham sido agendadas para execução futura.</span><span class="sxs-lookup"><span data-stu-id="28d0d-178">Indexing operations will begin immediately unless they have been scheduled for future execution.</span></span> <span data-ttu-id="28d0d-179">Serão criadas agendas imediatamente, embora elas sejam executadas somente na hora agendada.</span><span class="sxs-lookup"><span data-stu-id="28d0d-179">Schedules will be created immediately, although they will not run until their scheduled time.</span></span>  
  
     <span data-ttu-id="28d0d-180">**Nova Agenda de Tabela**</span><span class="sxs-lookup"><span data-stu-id="28d0d-180">**New Table Schedule**</span></span>  
     <span data-ttu-id="28d0d-181">Defina uma agenda de população para uma tabela.</span><span class="sxs-lookup"><span data-stu-id="28d0d-181">Define a population schedule for a table.</span></span>  
  
     <span data-ttu-id="28d0d-182">**Nova Agenda do Catálogo**</span><span class="sxs-lookup"><span data-stu-id="28d0d-182">**New Catalog Schedule**</span></span>  
     <span data-ttu-id="28d0d-183">Defina uma agenda de população para um catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-183">Define a population schedule for a full-text catalog.</span></span>  
  
     <span data-ttu-id="28d0d-184">**Editar**</span><span class="sxs-lookup"><span data-stu-id="28d0d-184">**Edit**</span></span>  
     <span data-ttu-id="28d0d-185">Edite uma agenda.</span><span class="sxs-lookup"><span data-stu-id="28d0d-185">Edit a schedule.</span></span>  
  
     <span data-ttu-id="28d0d-186">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="28d0d-186">**Delete**</span></span>  
     <span data-ttu-id="28d0d-187">Exclua uma agenda.</span><span class="sxs-lookup"><span data-stu-id="28d0d-187">Delete a schedule.</span></span>  
  
5.  <span data-ttu-id="28d0d-188">Exiba ou controle o progresso do Assistente de Indexação de Texto Completo.</span><span class="sxs-lookup"><span data-stu-id="28d0d-188">View or control the progress of the Full-Text Indexing Wizard.</span></span>  
  
     <span data-ttu-id="28d0d-189">**Parar**</span><span class="sxs-lookup"><span data-stu-id="28d0d-189">**Stop**</span></span>  
     <span data-ttu-id="28d0d-190">Interrompe a operação atual e impede que sejam executadas operações de texto completo subsequentes pelo assistente durante esta sessão.</span><span class="sxs-lookup"><span data-stu-id="28d0d-190">Interrupts the current operation and prevents subsequent full-text operations from being performed by the wizard during this session.</span></span>  
  
     <span data-ttu-id="28d0d-191">**Report**</span><span class="sxs-lookup"><span data-stu-id="28d0d-191">**Report**</span></span>  
     <span data-ttu-id="28d0d-192">Quando todas as operações terminarem de executar, clique nesse botão para acessar um relatório sobre as operações executadas.</span><span class="sxs-lookup"><span data-stu-id="28d0d-192">When all of the operations have finished executing, click this button to access a report on the operations performed.</span></span> <span data-ttu-id="28d0d-193">Você pode exibir o relatório, imprimi-lo em um arquivo, copiá-lo na área de transferência ou enviá-lo por email.</span><span class="sxs-lookup"><span data-stu-id="28d0d-193">You can view the report, print it to a file, copy it to the clipboard, or e-mail the report.</span></span>  
  
  
