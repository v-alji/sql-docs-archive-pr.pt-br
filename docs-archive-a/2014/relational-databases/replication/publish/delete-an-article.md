---
title: Excluir um artigo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- articles [SQL Server replication], dropping
- sp_droparticle
- sp_dropmergearticle
- deleting articles
- removing articles
- dropping articles
ms.assetid: 185b58fc-38c0-4abe-822e-6ec20066c863
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 082f90d33c2b8dedfae34dcada9b3935bed134ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570618"
---
# <a name="delete-an-article"></a><span data-ttu-id="fa870-102">Excluir um artigo</span><span class="sxs-lookup"><span data-stu-id="fa870-102">Delete an Article</span></span>
  <span data-ttu-id="fa870-103">Este tópico descreve como excluir um artigo no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="fa870-103">This topic describes how to delete an article in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] or Replication Management Objects (RMO).</span></span> <span data-ttu-id="fa870-104">Para obter informações sobre as condições nas quais os artigos podem ser removidos e se a remoção de um artigo requer um novo instantâneo ou a reinicialização de assinaturas, consulte [Adicionar e remover artigos de publicações existentes](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="fa870-104">For information about the conditions under which articles can be dropped and whether dropping an article requires a new snapshot or the reinitialization of subscriptions, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fa870-105">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fa870-105">Using Transact-SQL</span></span>  
 <span data-ttu-id="fa870-106">Os artigos podem ser excluídos de forma programática usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="fa870-106">Articles can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="fa870-107">Os procedimentos armazenados usados dependem do tipo de publicação ao qual o artigo pertence.</span><span class="sxs-lookup"><span data-stu-id="fa870-107">The stored procedures that you use depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-from-a-snapshot-or-transactional-publication"></a><span data-ttu-id="fa870-108">Para excluir um artigo de um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="fa870-108">To delete an article from a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="fa870-109">Execute [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) para excluir um artigo, especificado por **\@article**, de uma publicação, especificado por **\@publication**.</span><span class="sxs-lookup"><span data-stu-id="fa870-109">Execute [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="fa870-110">Especifique um valor de **1** para \*\* \@ force_invalidate_snapshot\*\*.</span><span class="sxs-lookup"><span data-stu-id="fa870-110">Specify a value of **1** for **\@force_invalidate_snapshot**.</span></span>  
  
2.  <span data-ttu-id="fa870-111">(Opcional) Para remover inteiramente o objeto publicado de um banco de dados, execute o comando `DROP <objectname>` no Publicador do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="fa870-111">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
#### <a name="to-delete-an-article-from-a-merge-publication"></a><span data-ttu-id="fa870-112">Para excluir um artigo de uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="fa870-112">To delete an article from a merge publication</span></span>  
  
1.  <span data-ttu-id="fa870-113">Execute [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) para excluir um artigo, especificado por **\@article**, de uma publicação, especificado por **\@publication**.</span><span class="sxs-lookup"><span data-stu-id="fa870-113">Execute [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="fa870-114">Se necessário, especifique um valor de **1** para \*\* \@ force_invalidate_snapshot\*\* e um valor de **1** para \*\* \@ force_reinit_subscription\*\*.</span><span class="sxs-lookup"><span data-stu-id="fa870-114">If necessary, specify a value of **1** for **\@force_invalidate_snapshot** and a value of **1** for **\@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="fa870-115">(Opcional) Para remover inteiramente o objeto publicado de um banco de dados, execute o comando `DROP <objectname>` no Publicador do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="fa870-115">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="fa870-116">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fa870-116">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="fa870-117">O exemplo a seguir exclui um artigo da publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="fa870-117">The following example deletes an article from a transactional publication.</span></span> <span data-ttu-id="fa870-118">Como essa alteração invalida o instantâneo existente, um valor de **1** é especificado para o parâmetro \*\* \@ force_invalidate_snapshot\*\* .</span><span class="sxs-lookup"><span data-stu-id="fa870-118">Because this change invalidates the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_droparticle](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droparticle)]  
  
 <span data-ttu-id="fa870-119">O exemplo a seguir exclui dois artigos de uma publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="fa870-119">The following example deletes two articles from a merge publication.</span></span> <span data-ttu-id="fa870-120">Como essas alterações invalidam o instantâneo existente, um valor de **1** é especificado para o parâmetro \*\* \@ force_invalidate_snapshot\*\* .</span><span class="sxs-lookup"><span data-stu-id="fa870-120">Because these changes invalidate the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergearticle)]
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergearticles.sql#sp_dropmergearticle)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="fa870-121">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="fa870-121">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="fa870-122">Você pode excluir artigos programaticamente usando o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="fa870-122">You can delete articles programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="fa870-123">As classes RMO que você usa para excluir um artigo dependem do tipo de publicação a que o artigo pertence.</span><span class="sxs-lookup"><span data-stu-id="fa870-123">The RMO classes you use to delete an article depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="fa870-124">Para excluir um artigo que pertence a uma publicação de instantâneo ou transacional</span><span class="sxs-lookup"><span data-stu-id="fa870-124">To delete an article that belongs to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="fa870-125">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="fa870-125">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="fa870-126">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.TransArticle>.</span><span class="sxs-lookup"><span data-stu-id="fa870-126">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransArticle> class.</span></span>  
  
3.  <span data-ttu-id="fa870-127">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>e <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="fa870-127">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="fa870-128">Defina a conexão da etapa 1 para a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="fa870-128">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="fa870-129">Verifique a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para se certificar de que o artigo existe.</span><span class="sxs-lookup"><span data-stu-id="fa870-129">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="fa870-130">Se o valor desta propriedade for `false`, as propriedades do artigo na etapa 3 foram definidas incorretamente ou o artigo não existe.</span><span class="sxs-lookup"><span data-stu-id="fa870-130">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="fa870-131">Chame o método <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="fa870-131">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="fa870-132">Feche todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="fa870-132">Close all connections.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-merge-publication"></a><span data-ttu-id="fa870-133">Para excluir um artigo que pertence a uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="fa870-133">To delete an article that belongs to a merge publication</span></span>  
  
1.  <span data-ttu-id="fa870-134">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="fa870-134">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="fa870-135">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.MergeArticle>.</span><span class="sxs-lookup"><span data-stu-id="fa870-135">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeArticle> class.</span></span>  
  
3.  <span data-ttu-id="fa870-136">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>e <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="fa870-136">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="fa870-137">Defina a conexão da etapa 1 para a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="fa870-137">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="fa870-138">Verifique a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para se certificar de que o artigo existe.</span><span class="sxs-lookup"><span data-stu-id="fa870-138">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="fa870-139">Se o valor desta propriedade for `false`, as propriedades do artigo na etapa 3 foram definidas incorretamente ou o artigo não existe.</span><span class="sxs-lookup"><span data-stu-id="fa870-139">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="fa870-140">Chame o método <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="fa870-140">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="fa870-141">Feche todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="fa870-141">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa870-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa870-142">See Also</span></span>  
 <span data-ttu-id="fa870-143">[Adicionar e remover artigos de publicações existentes](add-articles-to-and-drop-articles-from-existing-publications.md) </span><span class="sxs-lookup"><span data-stu-id="fa870-143">[Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md) </span></span>  
 [<span data-ttu-id="fa870-144">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="fa870-144">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
