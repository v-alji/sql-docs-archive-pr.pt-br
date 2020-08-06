---
title: Exibir e modificar propriedades de assinatura push | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- push subscriptions [SQL Server replication], properties
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], modifying
- modifying replication properties, push subscriptions
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 801d2995-7aa5-4626-906e-c8190758ec71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1506d4f83fcfb94d62efd01c4d6447048fecfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684146"
---
# <a name="view-and-modify-push-subscription-properties"></a><span data-ttu-id="d12ea-102">Exibir e modificar propriedades de assinatura push</span><span class="sxs-lookup"><span data-stu-id="d12ea-102">View and Modify Push Subscription Properties</span></span>
  <span data-ttu-id="d12ea-103">Este tópico descreve como exibir e modificar propriedades de assinatura push no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)]ou o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="d12ea-103">This topic describes how to view and modify push subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="d12ea-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="d12ea-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d12ea-105">**Para exibir e modificar propriedades de assinatura push, usando:**</span><span class="sxs-lookup"><span data-stu-id="d12ea-105">**To view and modify push subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="d12ea-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d12ea-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d12ea-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d12ea-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="d12ea-108">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="d12ea-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d12ea-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d12ea-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d12ea-110">Exibir e modificar as propriedades de assinatura push do Publicador em:</span><span class="sxs-lookup"><span data-stu-id="d12ea-110">View and modify push subscription properties from the Publisher in:</span></span>  
  
-   <span data-ttu-id="d12ea-111">A caixa de diálogo **Propriedades da Assinatura – \<Publisher>: \<PublicationDatabase>** que está disponível no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d12ea-111">The **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="d12ea-112">A guia **Todas as Assinaturas** que está disponível no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="d12ea-112">The **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="d12ea-113">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="d12ea-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-management-studio"></a><span data-ttu-id="d12ea-114">Para exibir e modificar propriedades de assinatura push no Management Studio</span><span class="sxs-lookup"><span data-stu-id="d12ea-114">To view and modify push subscription properties in Management Studio</span></span>  
  
1.  <span data-ttu-id="d12ea-115">Conecte-se ao Publicador no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="d12ea-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d12ea-116">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="d12ea-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="d12ea-117">Expanda a publicação apropriada, clique com o botão direito do mouse em uma assinatura e, então, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d12ea-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="d12ea-118">Modifique propriedades, se necessário, depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d12ea-118">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-replication-monitor"></a><span data-ttu-id="d12ea-119">Para exibir e modificar propriedades de assinatura push no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="d12ea-119">To view and modify push subscription properties in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="d12ea-120">Expanda um Grupo do publicador no painel esquerdo do Replication Monitor, expanda um Publicador e, em seguida, clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="d12ea-120">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="d12ea-121">Clique na guia **Todas as Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="d12ea-121">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="d12ea-122">Clique com o botão direito do mouse em uma assinatura e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d12ea-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="d12ea-123">Modifique propriedades, se necessário, depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d12ea-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d12ea-124">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d12ea-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="d12ea-125">As assinaturas push podem ser modificadas e suas propriedades acessadas programaticamente usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="d12ea-125">Push subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="d12ea-126">Os procedimentos armazenados usados dependem do tipo de publicação ao qual a assinatura pertence.</span><span class="sxs-lookup"><span data-stu-id="d12ea-126">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="d12ea-127">Para exibir as propriedades de uma assinatura push de um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="d12ea-127">To view the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="d12ea-128">No Publicador do banco de dados da publicação, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d12ea-128">At the Publisher on the publication database, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="d12ea-129">Especifique **@publication** , **@subscriber** e um valor de **todos** para **@article** .</span><span class="sxs-lookup"><span data-stu-id="d12ea-129">Specify **@publication**, **@subscriber**, and a value of **all** for **@article**.</span></span>  
  
2.  <span data-ttu-id="d12ea-130">No Publicador do banco de dados da publicação, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), especificando **@subscriber**.</span><span class="sxs-lookup"><span data-stu-id="d12ea-130">At the Publisher on the publication database, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="d12ea-131">Para alterar as propriedades de uma assinatura push de um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="d12ea-131">To change the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="d12ea-132">No Publicador do banco de dados da publicação, execute [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), especificando **@subscriber** e quaisquer parâmetros para as propriedades do Assinante que está sendo alterado.</span><span class="sxs-lookup"><span data-stu-id="d12ea-132">At the Publisher on the publication database, execute [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), specifying **@subscriber** and any parameters for the Subscriber properties being changed.</span></span>  
  
2.  <span data-ttu-id="d12ea-133">No Publicador do banco de dados de publicação, execute [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d12ea-133">At the Publisher on the publication database, execute [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span></span> <span data-ttu-id="d12ea-134">Especifique **@publication** , **@subscriber** , **@destination_db** , um valor de **tudo** para **@article** , a propriedade de assinatura sendo alterada como **@property** e o novo valor como **@value** .</span><span class="sxs-lookup"><span data-stu-id="d12ea-134">Specify **@publication**, **@subscriber**, **@destination_db**, a value of **all** for **@article**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span> <span data-ttu-id="d12ea-135">Isto altera as configurações de segurança para a assinatura push.</span><span class="sxs-lookup"><span data-stu-id="d12ea-135">This changes security settings for the push subscription.</span></span>  
  
3.  <span data-ttu-id="d12ea-136">(Opcional) Para alterar as propriedades do pacote DTS (Data Transformation Services) de uma assinatura, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) , do Assinante no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="d12ea-136">(Optional) To change the Data Transformation Services (DTS) package properties of a subscription, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="d12ea-137">Especifique a ID do trabalho de Agente de Distribuição para **@jobid** e as seguintes propriedades de pacote DTS:</span><span class="sxs-lookup"><span data-stu-id="d12ea-137">Specify the ID of the Distribution Agent job for **@jobid** and the following DTS package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="d12ea-138">Isso altera as propriedades de pacote DTS de uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="d12ea-138">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d12ea-139">O ID de trabalho pode ser obtido executando [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d12ea-139">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="d12ea-140">Para exibir as propriedades de uma assinatura push de uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="d12ea-140">To view the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="d12ea-141">No Publicador do banco de dados de publicação, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d12ea-141">At the Publisher on the publication database, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span></span> <span data-ttu-id="d12ea-142">Especifique **@publication** e **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="d12ea-142">Specify **@publication** and **@subscriber**.</span></span>  
  
2.  <span data-ttu-id="d12ea-143">No Publicador, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), especificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="d12ea-143">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="d12ea-144">Para alterar as propriedades de uma assinatura push de uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="d12ea-144">To change the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="d12ea-145">No Publicador do banco de dados de publicação, execute [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d12ea-145">At the Publisher on the publication database, execute [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span></span> <span data-ttu-id="d12ea-146">Especifique **@publication** , **@subscriber** , **@subscriber_db** , a propriedade de assinatura sendo alterada como **@property** e o novo valor como **@value** .</span><span class="sxs-lookup"><span data-stu-id="d12ea-146">Specify **@publication**, **@subscriber**, **@subscriber_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="d12ea-147">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d12ea-147">Example (Transact-SQL)</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="d12ea-148">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="d12ea-148">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="d12ea-149">As classes RMO a serem usadas para exibir ou modificar as propriedades da assinatura push dependem do tipo de publicação em que a assinatura push está inscrita.</span><span class="sxs-lookup"><span data-stu-id="d12ea-149">The RMO classes you use to view or modify push subscription properties depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="d12ea-150">Para exibir ou modificar as propriedades de uma assinatura push para um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="d12ea-150">To view or modify properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="d12ea-151">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="d12ea-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="d12ea-152">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="d12ea-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="d12ea-153">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>e <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="d12ea-153">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="d12ea-154">Defina a configuração da propriedade <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1 para o <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="d12ea-154">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="d12ea-155">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="d12ea-155">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="d12ea-156">Se esse método retornar `false`, as propriedades de assinatura na etapa 3 foram definidas incorretamente ou a assinatura não existe.</span><span class="sxs-lookup"><span data-stu-id="d12ea-156">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="d12ea-157">(Opcional) Para alterar as propriedades, defina um novo valor para um das propriedades de <xref:Microsoft.SqlServer.Replication.TransSubscription> que podem ser definidas e depois chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="d12ea-157">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="d12ea-158">(Opcional) Para exibir as novas configurações, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recarregar as propriedades para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="d12ea-158">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="d12ea-159">Para exibir ou modificar as propriedades de uma assinatura push para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="d12ea-159">To view or modify properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="d12ea-160">Crie uma conexão com o Assinante usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="d12ea-160">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="d12ea-161">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="d12ea-161">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="d12ea-162">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>e <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="d12ea-162">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="d12ea-163">Defina a configuração da propriedade <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1 para o <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="d12ea-163">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="d12ea-164">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="d12ea-164">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="d12ea-165">Se esse método retornar `false`, as propriedades de assinatura na etapa 3 foram definidas incorretamente ou a assinatura não existe.</span><span class="sxs-lookup"><span data-stu-id="d12ea-165">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="d12ea-166">(Opcional) Para alterar as propriedades, defina um novo valor para um das propriedades de <xref:Microsoft.SqlServer.Replication.MergeSubscription> que podem ser definidas e depois chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="d12ea-166">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="d12ea-167">(Opcional) Para exibir as novas configurações, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recarregar as propriedades para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="d12ea-167">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d12ea-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d12ea-168">See Also</span></span>  
 <span data-ttu-id="d12ea-169">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d12ea-169">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="d12ea-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="d12ea-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="d12ea-171">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="d12ea-171">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
