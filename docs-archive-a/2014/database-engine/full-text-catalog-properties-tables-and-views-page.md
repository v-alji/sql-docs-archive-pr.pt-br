---
title: Propriedades do catálogo de texto completo (página tabelas e exibições) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.tablesviews.f1
ms.assetid: 2d45fcd2-0f0f-4167-9027-316d6696c106
author: rothja
ms.author: jroth
ms.openlocfilehash: eb4d968af6c550d19fbb8934b5d76a1bd63cb8da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684851"
---
# <a name="full-text-catalog-properties-tables-and-views-page"></a><span data-ttu-id="4bb30-102">Propriedades do catálogo de texto completo (página Tabelas e Exibições)</span><span class="sxs-lookup"><span data-stu-id="4bb30-102">Full-Text Catalog Properties (Tables and Views Page)</span></span>
  <span data-ttu-id="4bb30-103">Usa essa página de caixa de diálogo para exibir ou modificar as tabelas e exibições atribuídas ao catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="4bb30-103">Use this dialog page to view or modify the tables and views that are assigned to the full-text catalog.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="4bb30-104">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="4bb30-104">UI element list</span></span>  
 <span data-ttu-id="4bb30-105">**Todos os objetos de tabela/exibição qualificados neste banco de dados**</span><span class="sxs-lookup"><span data-stu-id="4bb30-105">**All eligible table/view objects in this database**</span></span>  
 <span data-ttu-id="4bb30-106">Lista as tabelas e exibições que possuem um índice exclusivo definido nelas, mas que ainda não fazem parte do catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="4bb30-106">Lists the tables and views that have a unique index defined on them, but are not already a part of the full-text catalog.</span></span> <span data-ttu-id="4bb30-107">Para selecionar uma tabela ou exibição e atribuí-la ao catálogo, selecione os itens na caixa de listagem e pressione o botão "->".</span><span class="sxs-lookup"><span data-stu-id="4bb30-107">To select a table or view and assign it to the catalog, select the items in the list box and press the "->" button.</span></span>  
  
 <span data-ttu-id="4bb30-108">**Objetos de tabela/exibição atribuídos ao catálogo**</span><span class="sxs-lookup"><span data-stu-id="4bb30-108">**Table/view objects assigned to the catalog**</span></span>  
 <span data-ttu-id="4bb30-109">Lista as tabelas e exibições que estão atualmente atribuídas ao catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="4bb30-109">Lists the tables and views that are currently assigned to the full-text catalog</span></span>  
  
## <a name="selected-object-properties"></a><span data-ttu-id="4bb30-110">Propriedades dos objetos selecionados</span><span class="sxs-lookup"><span data-stu-id="4bb30-110">Selected Object Properties</span></span>  
 <span data-ttu-id="4bb30-111">**Propriedades dos objetos selecionados**</span><span class="sxs-lookup"><span data-stu-id="4bb30-111">**Selected object properties**</span></span>  
 <span data-ttu-id="4bb30-112">Exibe as propriedades do objeto selecionado na caixa de listagem de objetos atribuídos ao catálogo.</span><span class="sxs-lookup"><span data-stu-id="4bb30-112">Displays the properties of the selected object in the list box of objects assigned to the catalog.</span></span>  
  
 <span data-ttu-id="4bb30-113">**Índice exclusivo**</span><span class="sxs-lookup"><span data-stu-id="4bb30-113">**Unique Index**</span></span>  
 <span data-ttu-id="4bb30-114">Lista os índices exclusivos disponíveis da tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="4bb30-114">Lists the available unique indexes of the table or view.</span></span>  
  
 <span data-ttu-id="4bb30-115">**Tabela habilitada para texto completo**</span><span class="sxs-lookup"><span data-stu-id="4bb30-115">**Table is full-text enabled**</span></span>  
 <span data-ttu-id="4bb30-116">Marque essa caixa de seleção para habilitar o índice de texto completo na tabela.</span><span class="sxs-lookup"><span data-stu-id="4bb30-116">Select this check box to enable the full-text index on the table.</span></span> <span data-ttu-id="4bb30-117">Desmarque-a para desabilitar o índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="4bb30-117">Clear the check box to disable the full-text index.</span></span>  
  
## <a name="eligible-columns-grid"></a><span data-ttu-id="4bb30-118">Grade de colunas qualificadas</span><span class="sxs-lookup"><span data-stu-id="4bb30-118">Eligible Columns Grid</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bb30-119">**Colunas disponíveis**</span><span class="sxs-lookup"><span data-stu-id="4bb30-119">**Available Columns**</span></span>|<span data-ttu-id="4bb30-120">Exibe todas as colunas que são indexadas com texto completo.</span><span class="sxs-lookup"><span data-stu-id="4bb30-120">Displays all the columns that are full-text indexed.</span></span> <span data-ttu-id="4bb30-121">Marque a caixa de seleção para adicionar a coluna ao índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="4bb30-121">Select a check box to add a column to the full-text index.</span></span>|  
|<span data-ttu-id="4bb30-122">**Idioma do separador de palavras**</span><span class="sxs-lookup"><span data-stu-id="4bb30-122">**Language for Word Breaker**</span></span>|<span data-ttu-id="4bb30-123">Exibe o idioma do separador de palavras.</span><span class="sxs-lookup"><span data-stu-id="4bb30-123">Displays the language of the word breaker.</span></span>|  
|<span data-ttu-id="4bb30-124">**Coluna de Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="4bb30-124">**Data Type Column**</span></span>|<span data-ttu-id="4bb30-125">Lista o nome da coluna na tabela que contém o tipo de documento da coluna listada em **colunas disponíveis** se a coluna for uma `varbinary(max)` coluna ou `image` .</span><span class="sxs-lookup"><span data-stu-id="4bb30-125">Lists the name of the column in the table that holds the document type of the column listed in **Available Columns** if the column is a `varbinary(max)` or `image` column.</span></span>|  
|<span data-ttu-id="4bb30-126">**Semântica Estatística**</span><span class="sxs-lookup"><span data-stu-id="4bb30-126">**Statistical Semantics**</span></span>|<span data-ttu-id="4bb30-127">Especifique se habilitará a indexação semântica da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="4bb30-127">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="4bb30-128">Para obter mais informações, veja [Pesquisa semântica &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4bb30-128">For more information, see [Semantic Search &#40;SQL Server&#41;](../relational-databases/search/semantic-search-sql-server.md).</span></span><br /><br /> <span data-ttu-id="4bb30-129">Se você selecionar um **Idioma** antes de selecionar **Semântica Estatística**, e o idioma selecionado não tiver um Modelo de Idioma Semântico associado, a caixa de seleção **Semântica Estatística** será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="4bb30-129">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="4bb30-130">Se você selecionar **Semântica Estatística** antes de selecionar um **Idioma**, os idiomas disponíveis na caixa de combinação suspensa serão restringidos a esses para os quais o Modelo de Idioma Semântico dá suporte.</span><span class="sxs-lookup"><span data-stu-id="4bb30-130">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>|  
  
## <a name="track-changes"></a><span data-ttu-id="4bb30-131">Controlar Alterações</span><span class="sxs-lookup"><span data-stu-id="4bb30-131">Track Changes</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bb30-132">**Automática**</span><span class="sxs-lookup"><span data-stu-id="4bb30-132">**Automatic**</span></span>|<span data-ttu-id="4bb30-133">O índice de texto completo será atualizado automaticamente quando os dados da tabela subjacente forem alterados, adicionados ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="4bb30-133">The full-text index is automatically updated when the data in the underlying table is modified, added, or deleted.</span></span>|  
|<span data-ttu-id="4bb30-134">**Manual**</span><span class="sxs-lookup"><span data-stu-id="4bb30-134">**Manual**</span></span>|<span data-ttu-id="4bb30-135">Se os dados forem modificados, adicionados ou excluídos dos dados indexados, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] controlará as alterações.</span><span class="sxs-lookup"><span data-stu-id="4bb30-135">When data is modified, added, or deleted in the indexed data, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tracks the changes.</span></span> <span data-ttu-id="4bb30-136">Se o controle de alteração **Manual** estiver em vigor, o índice não será atualizado automaticamente com essas alterações.</span><span class="sxs-lookup"><span data-stu-id="4bb30-136">When **Manual** change tracking is in effect, the index is not automatically updated with these changes.</span></span> <span data-ttu-id="4bb30-137">Em vez disso, um administrador pode aplicar as alterações manualmente usando um [ALTER FULLTEXT index... Instrução START UPDATE Population](/sql/t-sql/statements/alter-fulltext-index-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4bb30-137">Instead, an administrator can apply the changes manually by using an [ALTER FULLTEXT INDEX ... START UPDATE POPULATION](/sql/t-sql/statements/alter-fulltext-index-transact-sql) statement.</span></span>|  
|<span data-ttu-id="4bb30-138">**Não controlar alterações**</span><span class="sxs-lookup"><span data-stu-id="4bb30-138">**Do not track change**</span></span>|<span data-ttu-id="4bb30-139">Com essa opção em vigor, as alterações feitas nos dados indexados do catálogo não são registradas.</span><span class="sxs-lookup"><span data-stu-id="4bb30-139">With this option in effect, changes to the indexed data in the catalog are not recorded.</span></span> <span data-ttu-id="4bb30-140">O administrador deve criar o índice usando ALTER FULLTEXT INDEX com FULL POPULATION ou INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="4bb30-140">An administrator must build the index by using ALTER FULLTEXT INDEX with either FULL POPULATION or INCREMENTAL POPULATION.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bb30-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4bb30-141">See Also</span></span>  
 <span data-ttu-id="4bb30-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4bb30-142">[CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-catalog-transact-sql) </span></span>  
 <span data-ttu-id="4bb30-143">[ALTERAR o catálogo de texto completo &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4bb30-143">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="4bb30-144">Popular índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="4bb30-144">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
