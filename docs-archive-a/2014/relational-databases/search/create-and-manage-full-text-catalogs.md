---
title: Criar e gerenciar catálogos de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs [SQL Server], creating
- full-text search [SQL Server], using SQL Server Management Studio
ms.assetid: 824b7131-44a6-4815-89e6-62b7bab060e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18efd79bc34beee94d4edc61e9165a986edba90b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583463"
---
# <a name="create-and-manage-full-text-catalogs"></a><span data-ttu-id="eaf9e-102">Criar e gerenciar catálogos de texto completo</span><span class="sxs-lookup"><span data-stu-id="eaf9e-102">Create and Manage Full-Text Catalogs</span></span>
  <span data-ttu-id="eaf9e-103">Um catálogo de texto completo é um objeto virtual que não pertence a nenhum grupo de arquivos; trata-se de um conceito lógico que faz referência a um grupo de índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-103">A full-text catalog is a virtual object that does not belong to any filegroup; it is a logical concept that refers to a group of full-text indexes.</span></span>  
  
##  <a name="creating-a-full-text-catalog"></a><a name="creating"></a><span data-ttu-id="eaf9e-104">Criando um catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="eaf9e-104">Creating a Full-Text Catalog</span></span>  
  
#### <a name="to-create-a-full-text-catalog"></a><span data-ttu-id="eaf9e-105">Para criar um catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="eaf9e-105">To create a full-text catalog</span></span>  
  
1.  <span data-ttu-id="eaf9e-106">No Pesquisador de Objetos, expanda o servidor, **Bancos de Dados**e o banco de dados em que deseja criar um catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-106">In Object Explorer, expand the server, expand **Databases**, and expand the database in which you want to create the full-text catalog.</span></span>  
  
2.  <span data-ttu-id="eaf9e-107">Expanda **Armazenamento**e clique com o botão direito do mouse em **Catálogos de Texto Completo**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-107">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="eaf9e-108">Selecione **Novo Catálogo de Texto Completo**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-108">Select **New Full-Text Catalog**.</span></span>  
  
4.  <span data-ttu-id="eaf9e-109">Na caixa de diálogo **Novo Catálogo de Texto Completo** , especifique as informações do catálogo que você está recriando.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-109">In the **New Full-Text Catalog** dialog box, specify the information for the catalog that you are re-creating.</span></span> <span data-ttu-id="eaf9e-110">Para obter mais informações, veja [Catálogo de texto completo novo &#40;Página Geral&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="eaf9e-110">For more information, see [New Full-Text Catalog &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eaf9e-111">Os identificadores de catálogos de texto completo começam em 00005 e são incrementados em um para cada novo catálogo criado.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-111">Full-text catalog IDs begin at 00005 and are incremented by one for each new catalog created.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
  
##  <a name="viewing-the-properties-of-a-full-text-catalog"></a><a name="props"></a><span data-ttu-id="eaf9e-112">Exibindo as propriedades de um catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="eaf9e-112">Viewing the Properties of a Full-Text Catalog</span></span>  
 <span data-ttu-id="eaf9e-113">Funções [!INCLUDE[tsql](../../includes/tsql-md.md)], como FULLTEXTCATALOGPROPERTY, podem ser usadas para obter o valor de diversas propriedades relativas à indexação de texto completo.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-113">[!INCLUDE[tsql](../../includes/tsql-md.md)] functions such as FULLTEXTCATALOGPROPERTY can be used to obtain the value of various properties related to full-text indexing.</span></span> <span data-ttu-id="eaf9e-114">Essas informações são úteis para administrar e solucionar problemas de pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-114">This information is useful for administering and troubleshooting full-text search.</span></span>  
  
 <span data-ttu-id="eaf9e-115">A tabela a seguir lista as propriedades relacionadas a catálogos de texto completo.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-115">The following table lists the properties that are related to full-text catalogs.</span></span>  
  
|<span data-ttu-id="eaf9e-116">Propriedade</span><span class="sxs-lookup"><span data-stu-id="eaf9e-116">Property</span></span>|<span data-ttu-id="eaf9e-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="eaf9e-117">Description</span></span>|<span data-ttu-id="eaf9e-118">Função</span><span class="sxs-lookup"><span data-stu-id="eaf9e-118">Function</span></span>|  
|--------------|-----------------|--------------|  
|`AccentSensitivity`|<span data-ttu-id="eaf9e-119">Configuração da diferenciação de caracteres com/sem acento.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-119">Accent-sensitivity setting.</span></span>|[<span data-ttu-id="eaf9e-120">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="eaf9e-120">FULLTEXTCATALOGPROPERTY</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)|  
|`ImportStatus`|<span data-ttu-id="eaf9e-121">Se o catálogo de texto completo está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-121">Whether the full-text catalog is being imported.</span></span>|<span data-ttu-id="eaf9e-122">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="eaf9e-122">FULLTEXTCATALOGPROPERTY</span></span>|  
|`IndexSize`|<span data-ttu-id="eaf9e-123">Tamanho do catálogo de texto completo em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="eaf9e-123">Size of the full-text catalog in megabytes (MB).</span></span>|<span data-ttu-id="eaf9e-124">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="eaf9e-124">FULLTEXTCATALOGPROPERTY</span></span>|  
|`ItemCount`|<span data-ttu-id="eaf9e-125">Número atual de itens indexados de texto completo no catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-125">Number of full-text indexed items currently in the full-text catalog.</span></span>|<span data-ttu-id="eaf9e-126">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="eaf9e-126">FULLTEXTCATALOGPROPERTY</span></span>|  
|`MergeStatus`|<span data-ttu-id="eaf9e-127">Se uma mesclagem mestra está em andamento.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-127">Whether a master merge is in progress.</span></span>|<span data-ttu-id="eaf9e-128">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="eaf9e-128">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateCompletionAge`|<span data-ttu-id="eaf9e-129">Diferença, em segundos, entre a conclusão da última população do índice de texto completo e 01/01/1990 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-129">Difference in seconds between the completion of the last full-text index population and 01/01/1990 00:00:00.</span></span>|<span data-ttu-id="eaf9e-130">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="eaf9e-130">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateStatus`|<span data-ttu-id="eaf9e-131">Status da população.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-131">Populate status.</span></span><br /><br /> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]|<span data-ttu-id="eaf9e-132">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="eaf9e-132">FULLTEXTCATALOGPROPERTY</span></span>|  
|`UniqueKeyCount`|<span data-ttu-id="eaf9e-133">Número de chaves exclusivas no catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-133">Number of unique keys in the full-text catalog.</span></span>|<span data-ttu-id="eaf9e-134">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="eaf9e-134">FULLTEXTCATALOGPROPERTY</span></span>|  
  
  
  
##  <a name="rebuilding-a-full-text-catalog"></a><a name="rebuildone"></a><span data-ttu-id="eaf9e-135">Recriando um catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="eaf9e-135">Rebuilding a Full-Text Catalog</span></span>  
  
#### <a name="to-rebuild-a-full-text-catalog"></a><span data-ttu-id="eaf9e-136">Para recriar um catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="eaf9e-136">To rebuild a full-text catalog</span></span>  
  
1.  <span data-ttu-id="eaf9e-137">No Pesquisador de Objetos, expanda o servidor, expanda **Bancos de Dados**e o banco de dados que contém o catálogo de texto completo a ser recriado.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-137">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalog that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="eaf9e-138">Expanda **Armazenamento**e, depois, **Catálogos de texto completo**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-138">Expand **Storage**, and then expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="eaf9e-139">Clique com o botão direito do mouse no nome do catálogo de texto completo que deseja recriar e selecione **Recriar**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-139">Right-click the name of the full-text catalog that you want to rebuild, and select **Rebuild**.</span></span>  
  
4.  <span data-ttu-id="eaf9e-140">Para a pergunta **Deseja excluir o catálogo de texto completo e recriá-lo?**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-140">To the question **Do you want to delete the full-text catalog and rebuild it?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="eaf9e-141">Na caixa de diálogo **Recriar Catálogo de Texto Completo** , clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-141">In the **Rebuild Full-Text Catalog** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="rebuilding-all-full-text-catalogs-for-a-database"></a><a name="rebuildall"></a><span data-ttu-id="eaf9e-142">Recompilando todos os catálogos de texto completo de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="eaf9e-142">Rebuilding All Full-Text Catalogs for a Database</span></span>  
  
#### <a name="to-rebuild-the-full-text-catalogs-for-a-database"></a><span data-ttu-id="eaf9e-143">Para recriar os catálogos de texto completo para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="eaf9e-143">To rebuild the full-text catalogs for a database</span></span>  
  
1.  <span data-ttu-id="eaf9e-144">No Pesquisador de Objetos, expanda o servidor, expanda **Bancos de Dados**e o banco de dados contendo os catálogos de texto completo a serem recriados.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-144">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalogs that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="eaf9e-145">Expanda **Armazenamento**e clique com o botão direito do mouse em **Catálogos de Texto Completo**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-145">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="eaf9e-146">Selecione **Recriar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-146">Select **Rebuild All**.</span></span>  
  
4.  <span data-ttu-id="eaf9e-147">Para a pergunta **Deseja excluir todos os catálogos de texto completo e recriá-los?**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-147">To the question, **Do you want to delete all full-text catalogs and rebuild them?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="eaf9e-148">Na caixa de diálogo **Recriar Todos os Catálogos de Texto Completo** , clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-148">In the **Rebuild All Full-Text Catalogs** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="removing-a-full-text-catalog-from-a-database"></a><a name="removing"></a><span data-ttu-id="eaf9e-149">Removendo um catálogo de texto completo de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="eaf9e-149">Removing a Full-Text Catalog from a Database</span></span>  
  
#### <a name="to-remove-a-full-text-catalog-from-a-database"></a><span data-ttu-id="eaf9e-150">Para remover um catálogo de texto completo de um Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="eaf9e-150">To remove a full-text catalog from a database</span></span>  
  
1.  <span data-ttu-id="eaf9e-151">No Pesquisador de Objetos, expanda o servidor, **Bancos de Dados**e o banco de dados que contém o catálogo de texto completo a ser removido.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-151">In Object Explorer, expand the server, expand **Databases**, and expand the database that contains the full-text catalog you want to remove.</span></span>  
  
2.  <span data-ttu-id="eaf9e-152">Expanda **Armazenamento**e **Catálogo de texto completo**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-152">Expand **Storage**, and expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="eaf9e-153">Clique com o botão direito do mouse no catálogo de texto completo que deseja remover e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-153">Right-click the full-text catalog that you want to remove, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="eaf9e-154">Na caixa de diálogo **Excluir Objetos** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaf9e-154">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="eaf9e-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eaf9e-155">See Also</span></span>  
 [<span data-ttu-id="eaf9e-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eaf9e-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-catalog-transact-sql)  
  
  
