---
title: Excluir uma publicação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing publications
- publications [SQL Server replication], deleting
- articles [SQL Server replication], deleting
- deleting publications
ms.assetid: 408a1360-12ee-4896-ac94-482ae839593b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d2b39a326d59333868b4f8015eb9a2e59d59e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685536"
---
# <a name="delete-a-publication"></a><span data-ttu-id="a884b-102">Excluir uma publicação</span><span class="sxs-lookup"><span data-stu-id="a884b-102">Delete a Publication</span></span>
  <span data-ttu-id="a884b-103">Este tópico descreve como excluir uma publicação no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="a884b-103">This topic describes how to delete a publication in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="a884b-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a884b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a884b-105">**Para excluir uma publicação, usando:**</span><span class="sxs-lookup"><span data-stu-id="a884b-105">**To delete a publication, using:**</span></span>  
  
     [<span data-ttu-id="a884b-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a884b-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a884b-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a884b-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a884b-108">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="a884b-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a884b-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a884b-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a884b-110">Exclua publicações da pasta **Publicações Locais** no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a884b-110">Delete publications from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-a-publication"></a><span data-ttu-id="a884b-111">Para excluir uma publicação</span><span class="sxs-lookup"><span data-stu-id="a884b-111">To delete a publication</span></span>  
  
1.  <span data-ttu-id="a884b-112">Conecte-se ao Publicador no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="a884b-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="a884b-113">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="a884b-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="a884b-114">Clique com o botão direito na publicação que você deseja excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="a884b-114">Right-click the publication you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a884b-115">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a884b-115">Using Transact-SQL</span></span>  
 <span data-ttu-id="a884b-116">As publicações podem ser excluídas programaticamente usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="a884b-116">Publications can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="a884b-117">Os procedimentos armazenados que você usar dependerão do tipo de publicação a ser excluída.</span><span class="sxs-lookup"><span data-stu-id="a884b-117">The stored procedures that you use depend on the type of publication being deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a884b-118">Excluir uma publicação não remove objetos publicados do banco de dados de publicação ou objetos correspondentes do banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="a884b-118">Deleting a publication does not remove published objects from the publication database or the corresponding objects from the subscription database.</span></span> <span data-ttu-id="a884b-119">Use o comando `DROP <object>` para remover esses objetos manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a884b-119">Use the `DROP <object>` command to manually remove these objects if necessary.</span></span>  
  
#### <a name="to-delete-a-snapshot-or-transactional-publication"></a><span data-ttu-id="a884b-120">Para excluir uma publicação de instantâneo ou transacional</span><span class="sxs-lookup"><span data-stu-id="a884b-120">To delete a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="a884b-121">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="a884b-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="a884b-122">Para excluir uma única publicação, execute [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) no Publicador do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="a884b-122">To delete a single publication, execute [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="a884b-123">Para excluir todas as publicações e remover todos os objetos de replicação de um banco de dados publicado, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) no Publicador.</span><span class="sxs-lookup"><span data-stu-id="a884b-123">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="a884b-124">Especifique um valor de `tran` para o \*\* \@ tipo\*\*.</span><span class="sxs-lookup"><span data-stu-id="a884b-124">Specify a value of `tran` for **\@type**.</span></span> <span data-ttu-id="a884b-125">(Opcional) Se o Distribuidor não puder ser acessado ou se o status do banco de dados for suspeito ou estiver offline, especifique um valor igual a **1** em **\@force**.</span><span class="sxs-lookup"><span data-stu-id="a884b-125">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="a884b-126">(Opcional) Especifique o nome do banco de dados em **\@dbname** se [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) não for executado no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="a884b-126">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a884b-127">A especificação de um valor igual a **1** em **\@force** pode manter objetos de publicação relacionados à replicação no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a884b-127">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="a884b-128">(Opcional) Se esse banco de dados não tiver outras publicações, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) para desabilitar a publicação do banco de dados atual usando replicação de instantâneo ou transacional.</span><span class="sxs-lookup"><span data-stu-id="a884b-128">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using snapshot or transactional replication.</span></span>  
  
3.  <span data-ttu-id="a884b-129">(Opcional) No Assinante no banco de dados de assinatura, execute [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) para remover quaisquer metadados de replicação remanescentes no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="a884b-129">(Optional) At the Subscriber on the subscription database, execute [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-merge-publication"></a><span data-ttu-id="a884b-130">Para excluir uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="a884b-130">To delete a merge publication</span></span>  
  
1.  <span data-ttu-id="a884b-131">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="a884b-131">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="a884b-132">Para excluir uma única publicação, execute [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) no Publicador do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="a884b-132">To delete a single publication, execute [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="a884b-133">Para excluir todas as publicações e remover todos os objetos de replicação de um banco de dados publicado, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) no Publicador.</span><span class="sxs-lookup"><span data-stu-id="a884b-133">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="a884b-134">Especifique um valor de `merge` para o \*\* \@ tipo\*\*.</span><span class="sxs-lookup"><span data-stu-id="a884b-134">Specify a value of `merge` for **\@type**.</span></span> <span data-ttu-id="a884b-135">(Opcional) Se o Distribuidor não puder ser acessado ou se o status do banco de dados for suspeito ou estiver offline, especifique um valor igual a **1** em **\@force**.</span><span class="sxs-lookup"><span data-stu-id="a884b-135">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="a884b-136">(Opcional) Especifique o nome do banco de dados em **\@dbname** se [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) não for executado no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="a884b-136">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a884b-137">A especificação de um valor igual a **1** em **\@force** pode manter objetos de publicação relacionados à replicação no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a884b-137">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="a884b-138">(Opcional) Se esse banco de dados não tiver outras publicações, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) para desabilitar a publicação do banco de dados atual usando replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="a884b-138">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using merge replication.</span></span>  
  
3.  <span data-ttu-id="a884b-139">(Opcional) No Assinante no banco de dados de assinatura, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) para remover quaisquer metadados de replicação remanescentes no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="a884b-139">(Optional) At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="a884b-140">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a884b-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="a884b-141">Este exemplo mostra como remover uma publicação transacional e desabilitar publicação transacional para um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a884b-141">This example shows how to remove a transactional publication and disable transactional publishing for a database.</span></span> <span data-ttu-id="a884b-142">Este exemplo pressupõe que todas as assinaturas foram previamente removidas.</span><span class="sxs-lookup"><span data-stu-id="a884b-142">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="a884b-143">Para obter mais informações, consulte [Delete a Pull Subscription](../delete-a-pull-subscription.md) ou [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a884b-143">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_droppublication](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droppublication)]  
  
 <span data-ttu-id="a884b-144">Este exemplo mostra como remover uma publicação de mesclagem e desabilitar publicação de mesclagem para um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a884b-144">This example shows how to remove a merge publication and disable merge publishing for a database.</span></span> <span data-ttu-id="a884b-145">Este exemplo pressupõe que todas as assinaturas foram previamente removidas.</span><span class="sxs-lookup"><span data-stu-id="a884b-145">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="a884b-146">Para obter mais informações, consulte [Delete a Pull Subscription](../delete-a-pull-subscription.md) ou [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a884b-146">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_dropmergepublication](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergepublication)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="a884b-147">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="a884b-147">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="a884b-148">É possível excluir publicações de forma programada usando o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="a884b-148">You can delete publications programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="a884b-149">As classes de RMO usadas para remover uma publicação dependem do tipo de publicação a ser removida.</span><span class="sxs-lookup"><span data-stu-id="a884b-149">The RMO classes that you use to remove a publication depend on the type of publication you remove.</span></span>  
  
#### <a name="to-remove-a-snapshot-or-transactional-publication"></a><span data-ttu-id="a884b-150">Para remover uma publicação transacional ou instantâneo</span><span class="sxs-lookup"><span data-stu-id="a884b-150">To remove a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="a884b-151">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="a884b-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="a884b-152">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.TransPublication>.</span><span class="sxs-lookup"><span data-stu-id="a884b-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPublication> class.</span></span>  
  
3.  <span data-ttu-id="a884b-153">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> e <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> para a publicação, e a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para a conexão criada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a884b-153">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="a884b-154">Verifique a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para saber se a publicação existe.</span><span class="sxs-lookup"><span data-stu-id="a884b-154">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="a884b-155">Se o valor dessa propriedade for `false`, as propriedades de publicação na etapa 3 foram definidas incorretamente ou a publicação não existe.</span><span class="sxs-lookup"><span data-stu-id="a884b-155">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="a884b-156">Chame o método <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="a884b-156">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="a884b-157">(Opcional) Se nenhuma outra publicação transacional existir para esse banco de dados, ele pode ser desabilitado para a publicação transacional, como se segue:</span><span class="sxs-lookup"><span data-stu-id="a884b-157">(Optional) If no other transactional publications exist for this database, the database can be disabled for transactional publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="a884b-158">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="a884b-158">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="a884b-159">Defina a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para a instância de <xref:Microsoft.SqlServer.Management.Common.ServerConnection> na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a884b-159">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1.</span></span>  
  
    2.  <span data-ttu-id="a884b-160">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="a884b-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="a884b-161">Se esse método retorna `false`, confirme que o banco de dados existe.</span><span class="sxs-lookup"><span data-stu-id="a884b-161">If this method returns `false`, confirm that the database exists.</span></span>  
  
    3.  <span data-ttu-id="a884b-162">Defina a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> como `false`.</span><span class="sxs-lookup"><span data-stu-id="a884b-162">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="a884b-163">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="a884b-163">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="a884b-164">Feche as conexões.</span><span class="sxs-lookup"><span data-stu-id="a884b-164">Close the connections.</span></span>  
  
#### <a name="to-remove-a-merge-publication"></a><span data-ttu-id="a884b-165">Para remover uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="a884b-165">To remove a merge publication</span></span>  
  
1.  <span data-ttu-id="a884b-166">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="a884b-166">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="a884b-167">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.MergePublication>.</span><span class="sxs-lookup"><span data-stu-id="a884b-167">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePublication> class.</span></span>  
  
3.  <span data-ttu-id="a884b-168">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> e <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> para a publicação, e a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para a conexão criada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a884b-168">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="a884b-169">Verifique a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para saber se a publicação existe.</span><span class="sxs-lookup"><span data-stu-id="a884b-169">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="a884b-170">Se o valor dessa propriedade for `false`, as propriedades de publicação na etapa 3 foram definidas incorretamente ou a publicação não existe.</span><span class="sxs-lookup"><span data-stu-id="a884b-170">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="a884b-171">Chame o método <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="a884b-171">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="a884b-172">(Opcional) Se nenhuma outra publicação de mesclagem existir para esse banco de dados, ele pode ser desabilitado para a publicação de mesclagem, como se segue:</span><span class="sxs-lookup"><span data-stu-id="a884b-172">(Optional) If no other merge publications exist for this database, the database can be disabled for merge publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="a884b-173">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="a884b-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="a884b-174">Defina a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para a instância de <xref:Microsoft.SqlServer.Management.Common.ServerConnection> na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a884b-174">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from Step 1.</span></span>  
  
    2.  <span data-ttu-id="a884b-175">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="a884b-175">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="a884b-176">Se esse método retornar `false`, verifique se o banco de dados existe.</span><span class="sxs-lookup"><span data-stu-id="a884b-176">If this method returns `false`, verify that the database exists.</span></span>  
  
    3.  <span data-ttu-id="a884b-177">Defina a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> como `false`.</span><span class="sxs-lookup"><span data-stu-id="a884b-177">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="a884b-178">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="a884b-178">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="a884b-179">Feche as conexões.</span><span class="sxs-lookup"><span data-stu-id="a884b-179">Close the connections.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="a884b-180">Exemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="a884b-180">Examples (RMO)</span></span>  
 <span data-ttu-id="a884b-181">O exemplo a seguir exclui uma publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="a884b-181">The following example deletes a transactional publication.</span></span> <span data-ttu-id="a884b-182">Se nenhuma outra publicação transacional existir para esse banco de dados, a publicação transacional será também desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a884b-182">If no other transactional publications exist for this database, transactional publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpub)]  
  
 <span data-ttu-id="a884b-183">O exemplo a seguir exclui uma publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="a884b-183">The following example deletes a merge publication.</span></span> <span data-ttu-id="a884b-184">Se nenhuma outra publicação de mesclagem existir para esse banco de dados, a publicação de mesclagem será também desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a884b-184">If no other merge publications exist for this database, merge publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropMergePub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropmergepub)]  
  
 [!code-vb[HowTo#rmo_vb_DropMergePub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropmergepub)]  
  
## <a name="see-also"></a><span data-ttu-id="a884b-185">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a884b-185">See Also</span></span>  
 <span data-ttu-id="a884b-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="a884b-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="a884b-187">Publicar dados e objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="a884b-187">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
