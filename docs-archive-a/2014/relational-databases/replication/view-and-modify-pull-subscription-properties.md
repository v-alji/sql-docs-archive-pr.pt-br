---
title: Exibir e modificar propriedades de assinatura pull | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- modifying subscriptions
- viewing replication properties
- modifying replication properties, pull subscriptions
- pull subscriptions [SQL Server replication], modifying
- subscriptions [SQL Server replication], pull
- pull subscriptions [SQL Server replication], properties
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 1601e54f-86f0-49e8-b023-87a5d1def033
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b847a22d31bbf3ea7540c55339fe27531134125
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569308"
---
# <a name="view-and-modify-pull-subscription-properties"></a><span data-ttu-id="82e6e-102">Exibir e modificar propriedades de assinatura pull</span><span class="sxs-lookup"><span data-stu-id="82e6e-102">View and Modify Pull Subscription Properties</span></span>
  <span data-ttu-id="82e6e-103">Este tópico descreve como exibir e modificar propriedades de assinatura pull no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], ou RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="82e6e-103">This topic describes how to view and modify pull subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="82e6e-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="82e6e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="82e6e-105">**Para exibir e modificar propriedades de assinatura pull, usando:**</span><span class="sxs-lookup"><span data-stu-id="82e6e-105">**To view and modify pull subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="82e6e-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82e6e-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="82e6e-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="82e6e-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="82e6e-108">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="82e6e-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="82e6e-109">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82e6e-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="82e6e-110">Veja as propriedades da assinatura pull no Distribuidor ou Assinante, na caixa de diálogo **Propriedades de Assinatura – \<Publisher>: \<PublicationDatabase>** , disponível no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82e6e-110">View pull subscription properties from the Publisher or the Subscriber in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="82e6e-111">Há mais propriedades visíveis no Assinante, e as propriedades podem ser modificadas no Assinante.</span><span class="sxs-lookup"><span data-stu-id="82e6e-111">More properties are visible from the Subscriber, and properties can be modified at the Subscriber.</span></span> <span data-ttu-id="82e6e-112">É igualmente possível exibir propriedades no Publicador, na guia **Todas as Assinaturas** , disponível no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="82e6e-112">You can also view properties from the Publisher on the **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="82e6e-113">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="82e6e-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-management-studio"></a><span data-ttu-id="82e6e-114">Para exibir propriedades de assinatura pull no Publicador do Management Studio</span><span class="sxs-lookup"><span data-stu-id="82e6e-114">To view pull subscription properties from the Publisher in Management Studio</span></span>  
  
1.  <span data-ttu-id="82e6e-115">Conecte-se ao Publicador no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="82e6e-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="82e6e-116">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="82e6e-117">Expanda a publicação apropriada, clique com o botão direito do mouse em uma assinatura e, então, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="82e6e-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="82e6e-118">Exiba as propriedades. Em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="82e6e-118">View properties, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-pull-subscription-properties-from-the-subscriber-in-management-studio"></a><span data-ttu-id="82e6e-119">Para exibir e modificar as propriedades de assinatura pull no Assinante do Management Studio</span><span class="sxs-lookup"><span data-stu-id="82e6e-119">To view and modify pull subscription properties from the Subscriber in Management Studio</span></span>  
  
1.  <span data-ttu-id="82e6e-120">Conecte-se ao Assinante no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="82e6e-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="82e6e-121">Expanda a pasta **Replicação** e, então, expanda a pasta **Assinaturas Locais** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="82e6e-122">Clique com o botão direito do mouse em uma assinatura e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="82e6e-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="82e6e-123">Modifique propriedades, se necessário, depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="82e6e-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-replication-monitor"></a><span data-ttu-id="82e6e-124">Para exibir propriedades de assinatura pull no Publicador do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="82e6e-124">To view pull subscription properties from the Publisher in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="82e6e-125">Expanda um Grupo do publicador no painel esquerdo do Replication Monitor, expanda um Publicador e, em seguida, clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="82e6e-125">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="82e6e-126">Clique na guia **Todas as Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-126">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="82e6e-127">Clique com o botão direito do mouse em uma assinatura e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="82e6e-127">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="82e6e-128">Exiba as propriedades. Em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="82e6e-128">View properties, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="82e6e-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="82e6e-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="82e6e-130">As assinaturas pull podem ser modificadas e suas propriedades acessadas programaticamente usando procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="82e6e-130">Pull subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="82e6e-131">Os procedimentos armazenados usados dependem do tipo de publicação ao qual a assinatura pertence.</span><span class="sxs-lookup"><span data-stu-id="82e6e-131">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="82e6e-132">Para visualizar as propriedades de uma assinatura pull para um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="82e6e-132">To view the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="82e6e-133">No Assinante, execute [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82e6e-133">At the Subscriber, execute [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span></span> <span data-ttu-id="82e6e-134">Especifique **@publisher** , **@publisher_db** , e **@publication** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-134">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="82e6e-135">Isso retorna informações sobre a assinatura que é armazenada em tabelas do sistema no Assinante.</span><span class="sxs-lookup"><span data-stu-id="82e6e-135">This returns information about the subscription that is stored in system tables at the Subscriber.</span></span>  
  
2.  <span data-ttu-id="82e6e-136">No Assinante, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82e6e-136">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="82e6e-137">Especifique **@publisher** , **@publisher_db** , **@publication** e um dos seguintes valores para **@publication_type** :</span><span class="sxs-lookup"><span data-stu-id="82e6e-137">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@publication_type**:</span></span>  
  
    -   <span data-ttu-id="82e6e-138">**0** - Assinatura pertence à uma publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="82e6e-138">**0** - Subscription belongs to a transactional publication.</span></span>  
  
    -   <span data-ttu-id="82e6e-139">**1** - Assinatura pertence à uma publicação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="82e6e-139">**1** - Subscription belongs to a snapshot publication.</span></span>  
  
3.  <span data-ttu-id="82e6e-140">No Publicador, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82e6e-140">At the Publisher, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="82e6e-141">Especifique **@publication** e **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-141">Specify **@publication** and **@subscriber**.</span></span>  
  
4.  <span data-ttu-id="82e6e-142">No Publicador, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), especificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-142">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="82e6e-143">Isso exibe informações sobre o Assinante.</span><span class="sxs-lookup"><span data-stu-id="82e6e-143">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="82e6e-144">Para alterar as propriedades de uma assinatura pull para um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="82e6e-144">To change the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="82e6e-145">No Assinante, execute [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), especificando **@publisher** , **@publisher_db** , **@publication** , um valor de **0** (transacional) ou **1** (instantâneo) para **@publication_type** , a propriedade de assinatura sendo alterada como **@property** e o novo valor como **@value** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-145">At the Subscriber, execute [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), specifying **@publisher**, **@publisher_db**, **@publication**, a value of either **0** (transactional) or **1** (snapshot) for **@publication_type**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
2.  <span data-ttu-id="82e6e-146">(Opcional) No Assinante, no banco de dados da assinatura, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82e6e-146">(Optional) At the Subscriber on the subscription database, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span></span> <span data-ttu-id="82e6e-147">Especifique a ID do trabalho de Agente de Distribuição para **@jobid** e as seguintes propriedades do pacote DTS (Data Transformation Services):</span><span class="sxs-lookup"><span data-stu-id="82e6e-147">Specify the ID of the Distribution Agent job for **@jobid**, and the following Data Transformation Services (DTS) package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="82e6e-148">Isso altera as propriedades de pacote DTS de uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="82e6e-148">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82e6e-149">O ID de trabalho pode ser obtido executando [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82e6e-149">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="82e6e-150">Para exibir as propriedades de uma assinatura pull para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="82e6e-150">To view the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="82e6e-151">No Assinante, execute [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82e6e-151">At the Subscriber, execute [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span></span> <span data-ttu-id="82e6e-152">Especifique **@publisher** , **@publisher_db** , e **@publication** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-152">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span>  
  
2.  <span data-ttu-id="82e6e-153">No Assinante, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82e6e-153">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="82e6e-154">Especifique **@publisher** , **@publisher_db** , e **@publication** um valor de 2 para **@publication_type** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-154">Specify **@publisher**, **@publisher_db**, **@publication**, and a value of 2 for **@publication_type**.</span></span>  
  
3.  <span data-ttu-id="82e6e-155">No Publicador, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) para exibir informações de assinatura.</span><span class="sxs-lookup"><span data-stu-id="82e6e-155">At the Publisher, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) to display subscription information.</span></span> <span data-ttu-id="82e6e-156">Para retornar informações sobre uma assinatura específica, você deve especificar **@publication** , **@subscriber** e um valor de **pull** para **@subscription_type** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-156">To return information on a specific subscription, you must specify **@publication**, **@subscriber**, and a value of **pull** for **@subscription_type**.</span></span>  
  
4.  <span data-ttu-id="82e6e-157">No Publicador, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), especificando **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-157">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="82e6e-158">Isso exibe informações sobre o Assinante.</span><span class="sxs-lookup"><span data-stu-id="82e6e-158">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="82e6e-159">Para alterar as propriedades de uma assinatura pull para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="82e6e-159">To change the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="82e6e-160">No Assinante, execute [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82e6e-160">At the Subscriber, execute [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span></span> <span data-ttu-id="82e6e-161">Especifique **@publication** , **@publisher** , **@publisher_db** , a propriedade de assinatura sendo alterada como **@property** e o novo valor como **@value** .</span><span class="sxs-lookup"><span data-stu-id="82e6e-161">Specify **@publication**, **@publisher**, **@publisher_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="82e6e-162">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="82e6e-162">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="82e6e-163">As classes RMO usadas para exibir ou modificar as propriedades da assinatura pull dependem do tipo de publicação em que a assinatura pull está inscrita.</span><span class="sxs-lookup"><span data-stu-id="82e6e-163">The RMO classes you use to view or modify pull subscription properties depend on the type of publication to which the pull subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="82e6e-164">Para exibir ou modificar as propriedades de uma assinatura pull para um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="82e6e-164">To view or modify properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="82e6e-165">Crie uma conexão com o Assinante usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="82e6e-165">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="82e6e-166">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.TransPullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="82e6e-166">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="82e6e-167">Defina as propriedades <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>e <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="82e6e-167">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="82e6e-168">Defina a conexão da etapa 1 para a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="82e6e-168">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="82e6e-169">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="82e6e-169">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="82e6e-170">Se esse método retornar `false`, as propriedades de assinatura na etapa 3 foram definidas incorretamente ou a assinatura não existe no servidor.</span><span class="sxs-lookup"><span data-stu-id="82e6e-170">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="82e6e-171">(Opcional) Para alterar as propriedades, defina um novo valor para um das propriedades de <xref:Microsoft.SqlServer.Replication.TransPullSubscription> que podem ser definidas e depois chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="82e6e-171">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="82e6e-172">(Opcional) Para exibir as novas configurações, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recarregar as propriedades para o artigo.</span><span class="sxs-lookup"><span data-stu-id="82e6e-172">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="82e6e-173">Feche todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="82e6e-173">Close all connections.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="82e6e-174">Para exibir ou modificar as propriedades de uma assinatura pull de uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="82e6e-174">To view or modify properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="82e6e-175">Crie uma conexão com o Assinante usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="82e6e-175">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="82e6e-176">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.MergePullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="82e6e-176">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="82e6e-177">Defina as propriedades <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>e <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="82e6e-177">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="82e6e-178">Defina a conexão da etapa 1 para a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="82e6e-178">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="82e6e-179">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="82e6e-179">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="82e6e-180">Se esse método retornar `false`, as propriedades de assinatura na etapa 3 foram definidas incorretamente ou a assinatura não existe no servidor.</span><span class="sxs-lookup"><span data-stu-id="82e6e-180">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="82e6e-181">(Opcional) Para alterar as propriedades, defina um novo valor para um das propriedades de <xref:Microsoft.SqlServer.Replication.MergePullSubscription> que podem ser definidas e depois chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="82e6e-181">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="82e6e-182">(Opcional) Para exibir as novas configurações, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recarregar as propriedades para o artigo.</span><span class="sxs-lookup"><span data-stu-id="82e6e-182">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="82e6e-183">Feche todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="82e6e-183">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e6e-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82e6e-184">See Also</span></span>  
 <span data-ttu-id="82e6e-185">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="82e6e-185">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="82e6e-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="82e6e-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="82e6e-187">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="82e6e-187">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
