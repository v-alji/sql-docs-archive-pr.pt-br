---
title: Caixa de diálogo Índice de Texto Completo (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextindex
ms.assetid: ef45b585-2567-4abe-b421-9fd0994e0146
author: stevestein
ms.author: sstein
ms.openlocfilehash: f98d3bf43707caedd8c9d0a01349f36d5a5bfbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685398"
---
# <a name="full-text-index-dialog-box-visual-database-tools"></a><span data-ttu-id="8b14f-102">Caixa de diálogo Índice de Texto Completo (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8b14f-102">Full-Text Index Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="8b14f-103">Essa caixa de diálogo permite que você crie um índice de texto completo, para executar pesquisas de texto completo em colunas baseadas em texto nas suas tabelas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8b14f-103">This dialog box allows you to create a full-text index, for full-text searches on text-based columns in your database tables.</span></span> <span data-ttu-id="8b14f-104">Um índice de texto completo baseia-se em um índice regular, assim você deve criá-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="8b14f-104">A full-text index relies on a regular index, so you must create that first.</span></span> <span data-ttu-id="8b14f-105">O índice regular deve ser criado em uma coluna não nula exclusiva, e é melhor escolher uma coluna com valores baixos em vez de uma coluna com valores altos.</span><span class="sxs-lookup"><span data-stu-id="8b14f-105">The regular index must be created on a single, non-null column; it is best to choose a column with small values rather than a column with large ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b14f-106">Para criar um índice de texto completo, você deve criar primeiro um catálogo de texto completo para o banco de dados usando uma ferramenta externa, como o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="8b14f-106">To create a full-text index, you must first create a full-text catalog for the database using an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b14f-107">Não há uma funcionalidade de índice de texto completo disponível em todas as edições do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b14f-107">Full-text index functionality is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8b14f-108">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="8b14f-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8b14f-109">Opções</span><span class="sxs-lookup"><span data-stu-id="8b14f-109">Options</span></span>  
 <span data-ttu-id="8b14f-110">**Índice de texto completo selecionado**</span><span class="sxs-lookup"><span data-stu-id="8b14f-110">**Selected Full-Text Index**</span></span>  
 <span data-ttu-id="8b14f-111">Exibe índices de texto completo existentes.</span><span class="sxs-lookup"><span data-stu-id="8b14f-111">Lists existing full-text indexes.</span></span> <span data-ttu-id="8b14f-112">Selecione um índice para exibir suas propriedades na grade à direita.</span><span class="sxs-lookup"><span data-stu-id="8b14f-112">Select an index to show its properties in the grid to the right.</span></span> <span data-ttu-id="8b14f-113">Se a lista estiver vazia, nenhuma relação de texto completo foi definida para a tabela.</span><span class="sxs-lookup"><span data-stu-id="8b14f-113">If the list is empty, no full-text relationships have been defined for the table.</span></span>  
  
 <span data-ttu-id="8b14f-114">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="8b14f-114">**Add**</span></span>  
 <span data-ttu-id="8b14f-115">Crie um novo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8b14f-115">Create a new full-text index.</span></span>  
  
 <span data-ttu-id="8b14f-116">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="8b14f-116">**Delete**</span></span>  
 <span data-ttu-id="8b14f-117">Exclua o índice de texto completo selecionado na lista **Índice de texto completo selecionado** .</span><span class="sxs-lookup"><span data-stu-id="8b14f-117">Delete the full-text index selected in the **Selected Full-Text Index** list.</span></span>  
  
 <span data-ttu-id="8b14f-118">**Categoria Geral**</span><span class="sxs-lookup"><span data-stu-id="8b14f-118">**General Category**</span></span>  
 <span data-ttu-id="8b14f-119">Quando expandida, mostra **Colunas** e o **Nome do Catálogo de Texto Completo**.</span><span class="sxs-lookup"><span data-stu-id="8b14f-119">When expanded, shows **Columns** and **Full-text Catalog Name**.</span></span>  
  
 <span data-ttu-id="8b14f-120">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="8b14f-120">**Columns**</span></span>  
 <span data-ttu-id="8b14f-121">Exibe uma lista de nomes de colunas pesquisável de texto completo separados por vírgula.</span><span class="sxs-lookup"><span data-stu-id="8b14f-121">Displays a comma-separated list of the names of full-text-searchable columns.</span></span> <span data-ttu-id="8b14f-122">Para ver a lista completa, clique no botão de reticências ( **...** ) à esquerda do campo de propriedade.</span><span class="sxs-lookup"><span data-stu-id="8b14f-122">To see the complete list, click the ellipsis button (**...**) to the left of the property field.</span></span>  
  
 <span data-ttu-id="8b14f-123">**Full-Text Catalog Name**</span><span class="sxs-lookup"><span data-stu-id="8b14f-123">**Full-Text Catalog Name**</span></span>  
 <span data-ttu-id="8b14f-124">Exibe o nome do catálogo de texto completo no qual este índice de texto completo é armazenado.</span><span class="sxs-lookup"><span data-stu-id="8b14f-124">Displays the name of the full-text catalog on which this full-text index is stored.</span></span> <span data-ttu-id="8b14f-125">Para armazenar o índice em um catálogo diferente, clique no nome do catálogo e escolha outro na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8b14f-125">To store the index on a different catalog, click the catalog name and choose another from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b14f-126">O catálogo deve ser criado primeiro em uma ferramenta externa, como o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="8b14f-126">The catalog must be created first in an outside tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Enterprise Manager.</span></span>  
  
 <span data-ttu-id="8b14f-127">**Categoria de identidade**</span><span class="sxs-lookup"><span data-stu-id="8b14f-127">**Identity Category**</span></span>  
 <span data-ttu-id="8b14f-128">Quando expandida, mostra o campo de nome para este índice.</span><span class="sxs-lookup"><span data-stu-id="8b14f-128">When expanded, shows the name field for this index.</span></span>  
  
 <span data-ttu-id="8b14f-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8b14f-129">**Name**</span></span>  
 <span data-ttu-id="8b14f-130">Exibe o nome especificado pelo sistema para este índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8b14f-130">Displays the system-specified name for this full-text index.</span></span>  
  
 <span data-ttu-id="8b14f-131">**Categoria do Designer de Tabelas**</span><span class="sxs-lookup"><span data-stu-id="8b14f-131">**Table Designer Category**</span></span>  
 <span data-ttu-id="8b14f-132">Quando expandido, mostra as propriedades que ditam como o índice é executado.</span><span class="sxs-lookup"><span data-stu-id="8b14f-132">When expanded, shows properties that dictate how the index performs.</span></span>  
  
 <span data-ttu-id="8b14f-133">**Ativo**</span><span class="sxs-lookup"><span data-stu-id="8b14f-133">**Active**</span></span>  
 <span data-ttu-id="8b14f-134">Indica se você pode executar uma pesquisa de texto completo usando este índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8b14f-134">Indicates whether you can currently perform a full-text search using this full-text index.</span></span>  
  
 <span data-ttu-id="8b14f-135">**Definição de Rastreamento de alterações**</span><span class="sxs-lookup"><span data-stu-id="8b14f-135">**Change Tracking Setting**</span></span>  
 <span data-ttu-id="8b14f-136">Descreve o status do controle de alterações para este índice: Manual, Automático ou Desligado.</span><span class="sxs-lookup"><span data-stu-id="8b14f-136">Describes the status of change tracking for this index: Manual, Auto, or Off.</span></span>  
  
 <span data-ttu-id="8b14f-137">**Rastreamento Concluído**</span><span class="sxs-lookup"><span data-stu-id="8b14f-137">**Crawl Completed**</span></span>  
 <span data-ttu-id="8b14f-138">Mostra se o rastreamento mais recente foi concluído.</span><span class="sxs-lookup"><span data-stu-id="8b14f-138">Shows whether the most recent crawl has been completed.</span></span> <span data-ttu-id="8b14f-139">Se este valor de propriedade for Não, um rastreamento está em progresso no momento.</span><span class="sxs-lookup"><span data-stu-id="8b14f-139">If this property value is No, a crawl is currently in progress.</span></span>  
  
 <span data-ttu-id="8b14f-140">**Data e Hora de Término do Rastreamento Atual ou Último**</span><span class="sxs-lookup"><span data-stu-id="8b14f-140">**End Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="8b14f-141">Exibe a data e a hora de término do rastreamento mais recente.</span><span class="sxs-lookup"><span data-stu-id="8b14f-141">Displays the date and time that the most recent crawl ended.</span></span>  
  
 <span data-ttu-id="8b14f-142">**Erros no Rastreamento Atual ou Último**</span><span class="sxs-lookup"><span data-stu-id="8b14f-142">**Errors In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="8b14f-143">Exibe o número de erros em rastreamentos atuais ou mais recentes.</span><span class="sxs-lookup"><span data-stu-id="8b14f-143">Displays the number of errors in current or most recent crawl.</span></span>  
  
 <span data-ttu-id="8b14f-144">**Versão do Índice**</span><span class="sxs-lookup"><span data-stu-id="8b14f-144">**Index Version**</span></span>  
 <span data-ttu-id="8b14f-145">Exibe a versão do esquema da tabela na hora em que o rastreamento iniciou.</span><span class="sxs-lookup"><span data-stu-id="8b14f-145">Displays the schema version of table at time the crawl started.</span></span>  
  
 <span data-ttu-id="8b14f-146">**Linhas no Rastreamento Atual ou Último**</span><span class="sxs-lookup"><span data-stu-id="8b14f-146">**Rows In Current Or Last Crawl**</span></span>  
 <span data-ttu-id="8b14f-147">Exibe o número de linhas atualizado no rastreamento atual ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="8b14f-147">Displays the number of rows updated in the current or most recent crawl.</span></span>  
  
 <span data-ttu-id="8b14f-148">**Data e Hora de Início do Rastreamento Atual ou Último**</span><span class="sxs-lookup"><span data-stu-id="8b14f-148">**Start Date And Time Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="8b14f-149">Exibe a data e a hora em que o rastreamento atual ou mais recente iniciou.</span><span class="sxs-lookup"><span data-stu-id="8b14f-149">Displays the date and time that the current or most recent crawl started.</span></span>  
  
 <span data-ttu-id="8b14f-150">**Carimbo de Data/Hora do Próximo Rastreamento**</span><span class="sxs-lookup"><span data-stu-id="8b14f-150">**Time Stamp For Next Crawl**</span></span>  
 <span data-ttu-id="8b14f-151">Exibe a data e a hora em que o próximo rastreamento iniciará.</span><span class="sxs-lookup"><span data-stu-id="8b14f-151">Displays the date and time that the next crawl will start.</span></span>  
  
 <span data-ttu-id="8b14f-152">**Tipo do Rastreamento Atual ou Último**</span><span class="sxs-lookup"><span data-stu-id="8b14f-152">**Type Of Current Or Last Crawl**</span></span>  
 <span data-ttu-id="8b14f-153">Exibe o tipo do rastreamento atual ou mais recente: Completo, Incremental, Atualização ou Propagação Automática.</span><span class="sxs-lookup"><span data-stu-id="8b14f-153">Displays the type of the current or most recent crawl: Full, Incremental, Update, or Auto Propagation.</span></span>  
  
 <span data-ttu-id="8b14f-154">**Nome do Índice Exclusivo**</span><span class="sxs-lookup"><span data-stu-id="8b14f-154">**Unique Index Name**</span></span>  
 <span data-ttu-id="8b14f-155">Exibe uma lista de todos os nomes de colunas neste banco de dados que têm índices de uma única coluna exclusivos.</span><span class="sxs-lookup"><span data-stu-id="8b14f-155">Displays a list of all of the names of columns in this database that have unique single-column indexes.</span></span> <span data-ttu-id="8b14f-156">Estas colunas podem ser usadas para criar um índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="8b14f-156">These columns can be used to create a full-text index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b14f-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b14f-157">See Also</span></span>  
 <span data-ttu-id="8b14f-158">[Usar o assistente para indexação de texto completo](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="8b14f-158">[Use the Full-Text Indexing Wizard](../../relational-databases/search/use-the-full-text-indexing-wizard.md) </span></span>  
 [<span data-ttu-id="8b14f-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8b14f-159">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
  
