---
title: Excluir uma assinatura push | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing subscriptions
- push subscriptions [SQL Server replication], deleting
- deleting subscriptions
- subscriptions [SQL Server replication], push
ms.assetid: 3c4847e2-aed9-4488-b45d-8164422bdb10
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 912958e00d117f51c5dc95c0dc1247d278acb0ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569934"
---
# <a name="delete-a-push-subscription"></a><span data-ttu-id="fdae2-102">Excluir uma assinatura push</span><span class="sxs-lookup"><span data-stu-id="fdae2-102">Delete a Push Subscription</span></span>
  <span data-ttu-id="fdae2-103">Este tópico descreve como excluir uma assinatura push no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]ou RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="fdae2-103">This topic describes how to delete a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="fdae2-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="fdae2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fdae2-105">**Para excluir uma assinatura push, usando:**</span><span class="sxs-lookup"><span data-stu-id="fdae2-105">**To delete a push subscription, using:**</span></span>  
  
     [<span data-ttu-id="fdae2-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fdae2-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fdae2-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fdae2-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="fdae2-108">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="fdae2-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fdae2-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fdae2-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="fdae2-110">Exclua uma assinatura push no Publicador (da pasta **Publicações Locais** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) ou no Assinante (da pasta **Assinaturas Locais** ).</span><span class="sxs-lookup"><span data-stu-id="fdae2-110">Delete a push subscription at the Publisher (from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) or the Subscriber (from the **Local Subscriptions** folder).</span></span> <span data-ttu-id="fdae2-111">A exclusão de uma assinatura não remove objetos ou dados da assinatura; eles devem ser removidos manualmente.</span><span class="sxs-lookup"><span data-stu-id="fdae2-111">Deleting a subscription does not remove objects or data from the subscription; they must be removed manually.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-publisher"></a><span data-ttu-id="fdae2-112">Para excluir uma assinatura push no Publicador</span><span class="sxs-lookup"><span data-stu-id="fdae2-112">To delete a push subscription at the Publisher</span></span>  
  
1.  <span data-ttu-id="fdae2-113">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="fdae2-113">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="fdae2-114">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="fdae2-114">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="fdae2-115">Expanda a publicação associada à assinatura que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="fdae2-115">Expand the publication associated with the subscription you want to delete.</span></span>  
  
4.  <span data-ttu-id="fdae2-116">Clique como botão direito do mouse na assinatura e, então, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="fdae2-116">Right-click the subscription, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="fdae2-117">Na caixa de diálogo de confirmação, selecione onde conectar-se ao Assinante para excluir as informações de assinatura.</span><span class="sxs-lookup"><span data-stu-id="fdae2-117">In the confirmation dialog box, select whether to connect to the Subscriber to delete subscription information.</span></span> <span data-ttu-id="fdae2-118">Se você desmarcar a caixa de seleção **Conectar-se ao Assinante** , será necessário conectar-se ao Assinante, posteriormente, para excluir as informações.</span><span class="sxs-lookup"><span data-stu-id="fdae2-118">If you clear the **Connect to Subscriber** checkbox, you should connect to the Subscriber later to delete the information.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-subscriber"></a><span data-ttu-id="fdae2-119">Para excluir uma assinatura push no Assinante</span><span class="sxs-lookup"><span data-stu-id="fdae2-119">To delete a push subscription at the Subscriber</span></span>  
  
1.  <span data-ttu-id="fdae2-120">Conecte-se ao Assinante no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="fdae2-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="fdae2-121">Expanda a pasta **Replicação** e, então, expanda a pasta **Assinaturas Locais** .</span><span class="sxs-lookup"><span data-stu-id="fdae2-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="fdae2-122">Clique com o botão direito na assinatura a ser excluída e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="fdae2-122">Right-click the subscription you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="fdae2-123">Na caixa de diálogo de confirmação, selecione se deseja se conectar ao Publicador para excluir as informações de assinatura.</span><span class="sxs-lookup"><span data-stu-id="fdae2-123">In the confirmation dialog box, select whether to connect to the Publisher to delete subscription information.</span></span> <span data-ttu-id="fdae2-124">Se você desmarcar a caixa de seleção **Conectar-se ao Publicador** , será necessário se conectar ao Publicador posteriormente para excluir as informações.</span><span class="sxs-lookup"><span data-stu-id="fdae2-124">If you clear the **Connect to Publisher** check box, you should connect to the Publisher later to delete the information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fdae2-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fdae2-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="fdae2-126">As assinaturas push podem ser excluídas programaticamente, usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="fdae2-126">Push subscriptions can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="fdae2-127">Os procedimentos armazenados usados dependem do tipo de publicação ao qual a assinatura pertence.</span><span class="sxs-lookup"><span data-stu-id="fdae2-127">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="fdae2-128">Para excluir uma assinatura push de um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="fdae2-128">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="fdae2-129">No Publicador do banco de dados de publicação, execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fdae2-129">At the Publisher on the publication database, execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span> <span data-ttu-id="fdae2-130">Especifique **@publication** e **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="fdae2-130">Specify **@publication** and **@subscriber**.</span></span> <span data-ttu-id="fdae2-131">Especifique um valor de **all** para **@article**.</span><span class="sxs-lookup"><span data-stu-id="fdae2-131">Specify a value of **all** for **@article**.</span></span> <span data-ttu-id="fdae2-132">(Opcional) Se o Distribuidor não puder ser acessado, especifique um valor de **1** para **@ignore_distributor** para excluir a assinatura sem remover objetos relacionados no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="fdae2-132">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="fdae2-133">No Assinante no banco de dados de assinatura, execute [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) para remover metadados de replicação no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="fdae2-133">At the Subscriber on the subscription database, execute [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="fdae2-134">Para excluir uma assinatura push para uma publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="fdae2-134">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="fdae2-135">No Publicador, execute [sp_dropmergesubscription &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), especificando **@publication** **@subscriber** e **@subscriber_db** .</span><span class="sxs-lookup"><span data-stu-id="fdae2-135">At the Publisher, execute [sp_dropmergesubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), specifying **@publication**, **@subscriber** and **@subscriber_db**.</span></span> <span data-ttu-id="fdae2-136">(Opcional) Se o Distribuidor não puder ser acessado, especifique um valor de **1** para **@ignore_distributor** para excluir a assinatura sem remover objetos relacionados no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="fdae2-136">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="fdae2-137">No Assinante no banco de dados de assinatura, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fdae2-137">At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span></span> <span data-ttu-id="fdae2-138">Especifique **@publisher** , **@publisher_db** , e **@publication** .</span><span class="sxs-lookup"><span data-stu-id="fdae2-138">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="fdae2-139">Isso remove metadados de mesclagem do banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="fdae2-139">This removes merge metadata from the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="fdae2-140">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fdae2-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="fdae2-141">Esse exemplo exclui uma assinatura push para uma publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="fdae2-141">This example deletes a push subscription to a transactional publication.</span></span>  
  
 [!code-sql[HowTo#sp_droptransubscription](../../snippets/tsql/SQL15/replication/howto/tsql/droptranpullsub.sql#sp_droptransubscription)]  
  
 <span data-ttu-id="fdae2-142">Esse exemplo exclui uma assinatura push para uma publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="fdae2-142">This example deletes a push subscription to a merge publication.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergesubscription](../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepullsub.sql#sp_dropmergesubscription)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="fdae2-143">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="fdae2-143">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="fdae2-144">As classes RMO a serem usadas para excluir uma assinatura push dependem do tipo de publicação em que a assinatura push está inscrita.</span><span class="sxs-lookup"><span data-stu-id="fdae2-144">The RMO classes that you use to delete a push subscription depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="fdae2-145">Para excluir uma assinatura push de um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="fdae2-145">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="fdae2-146">Crie uma conexão com o Assinante usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="fdae2-146">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="fdae2-147">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="fdae2-147">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="fdae2-148">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>e <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="fdae2-148">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="fdae2-149">Defina a propriedade <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1 para o <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="fdae2-149">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="fdae2-150">Verifique a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para verificar se a assinatura existe.</span><span class="sxs-lookup"><span data-stu-id="fdae2-150">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="fdae2-151">Se o valor dessa propriedade for `false`, as propriedades de assinatura na etapa 2 foram definidas incorretamente ou a assinatura não existe.</span><span class="sxs-lookup"><span data-stu-id="fdae2-151">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="fdae2-152">Chame o método <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="fdae2-152">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="fdae2-153">Para excluir uma assinatura push para uma publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="fdae2-153">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="fdae2-154">Crie uma conexão com o Assinante usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="fdae2-154">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="fdae2-155">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="fdae2-155">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="fdae2-156">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>e <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="fdae2-156">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="fdae2-157">Defina a propriedade <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1 para o <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="fdae2-157">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="fdae2-158">Verifique a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para verificar se a assinatura existe.</span><span class="sxs-lookup"><span data-stu-id="fdae2-158">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="fdae2-159">Se o valor dessa propriedade for `false`, as propriedades de assinatura na etapa 2 foram definidas incorretamente ou a assinatura não existe.</span><span class="sxs-lookup"><span data-stu-id="fdae2-159">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="fdae2-160">Chame o método <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="fdae2-160">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="fdae2-161">Exemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="fdae2-161">Examples (RMO)</span></span>  
 <span data-ttu-id="fdae2-162">Você pode excluir assinaturas push programaticamente, usando o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="fdae2-162">You can delete push subscriptions programmatically by using Replication Management Objects (RMO).</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="fdae2-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fdae2-163">See Also</span></span>  
 <span data-ttu-id="fdae2-164">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="fdae2-164">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="fdae2-165">Replication Security Best Practices</span><span class="sxs-lookup"><span data-stu-id="fdae2-165">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
