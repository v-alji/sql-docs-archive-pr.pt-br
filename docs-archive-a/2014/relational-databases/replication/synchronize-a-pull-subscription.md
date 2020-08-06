---
title: Sincronizar uma assinatura pull | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- pull subscriptions [SQL Server replication], synchronizing
- synchronization [SQL Server replication], pull subscriptions
- subscriptions [SQL Server replication], pull
ms.assetid: 3ca24b23-fdc3-408e-8208-a2ace48fc8e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 826622cd17862c0535e60c01baab756af2b2996b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574650"
---
# <a name="synchronize-a-pull-subscription"></a><span data-ttu-id="e05bb-102">Sincronizar uma assinatura pull</span><span class="sxs-lookup"><span data-stu-id="e05bb-102">Synchronize a Pull Subscription</span></span>
  <span data-ttu-id="e05bb-103">Este tópico descreve como sincronizar uma assinatura pull no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [agentes de replicação](agents/replication-agents-overview.md), ou RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="e05bb-103">This topic describes how to synchronize a pull subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e05bb-104">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e05bb-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="e05bb-105">Assinaturas são sincronizadas pelo Agente de Distribuição (para replicação transacional e de instantâneo) ou pelo Agente de Mesclagem (para replicação de mesclagem).</span><span class="sxs-lookup"><span data-stu-id="e05bb-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="e05bb-106">Os agentes podem ser executados continuamente, sob demanda ou em um agendamento.</span><span class="sxs-lookup"><span data-stu-id="e05bb-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="e05bb-107">Para obter mais informações sobre como especificar agendas de sincronização, consulte [Especificar agendas de sincronização](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="e05bb-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="e05bb-108">Sincronize uma assinatura em demanda na pasta **Assinaturas Locais** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e05bb-108">Synchronize a subscription on demand from the **Local Subscriptions** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-on-demand-in-management-studio"></a><span data-ttu-id="e05bb-109">Para sincronizar uma assinatura pull sob demanda no Management Studio</span><span class="sxs-lookup"><span data-stu-id="e05bb-109">To synchronize a pull subscription on demand in Management Studio</span></span>  
  
1.  <span data-ttu-id="e05bb-110">Conecte-se ao Assinante no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="e05bb-110">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="e05bb-111">Expanda a pasta **Replicação** e, então, expanda a pasta **Assinaturas Locais** .</span><span class="sxs-lookup"><span data-stu-id="e05bb-111">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="e05bb-112">Clique com o botão direito do mouse na assinatura a ser sincronizada e clique em **Exibir Status da Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="e05bb-112">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="e05bb-113">Na caixa de diálogo **Exibir Status da Sincronização – \<Subscriber>:\<SubscriptionDatabase>** , clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="e05bb-113">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="e05bb-114">Quando a sincronização estiver concluída, a mensagem **Sincronização concluída** será exibida.</span><span class="sxs-lookup"><span data-stu-id="e05bb-114">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
5.  <span data-ttu-id="e05bb-115">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="e05bb-115">Click **Close**.</span></span>  
  
##  <a name="replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="e05bb-116">Replication Agents</span><span class="sxs-lookup"><span data-stu-id="e05bb-116">Replication Agents</span></span>  
 <span data-ttu-id="e05bb-117">As assinaturas pull podem ser sincronizadas programaticamente e sob demanda chamando o arquivo executável do agente de replicação apropriado do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="e05bb-117">Pull subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="e05bb-118">O arquivo executável do agente de replicação chamado dependerá do tipo de publicação para a qual a assinatura pull pertence.</span><span class="sxs-lookup"><span data-stu-id="e05bb-118">The replication agent executable file that is invoked will depend on the type of publication to which the pull subscription belongs.</span></span> <span data-ttu-id="e05bb-119">Para obter mais informações, consulte [Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e05bb-119">For more information, see [Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e05bb-120">Os agentes de replicação conectam-se ao servidor local usando as credenciais de Autenticação do Windows do usuário que inicializou o agente a partir do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="e05bb-120">Replication agents connect to the local server using the Windows Authentication credentials of the user who started the agent from the command prompt.</span></span> <span data-ttu-id="e05bb-121">Estas credenciais de Windows também são usadas ao conectar a servidores remotos que usam Autenticação Integrada do Windows.</span><span class="sxs-lookup"><span data-stu-id="e05bb-121">These Windows credentials are also used when connecting to remote servers using Windows Integrated Authentication.</span></span>  
  
#### <a name="to-start-the-distribution-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="e05bb-122">Para iniciar o agente de distribuição no prompt de comando ou de um arquivo em lotes</span><span class="sxs-lookup"><span data-stu-id="e05bb-122">To start the distribution agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="e05bb-123">Do prompt de comando ou em um arquivo em lote, inicie o [Replication Distribution Agent](agents/replication-distribution-agent.md) executando **distrib.exe**, especificando os seguintes argumentos de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="e05bb-123">From the command prompt or in a batch file, start the [Replication Distribution Agent](agents/replication-distribution-agent.md) by running **distrib.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="e05bb-124">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="e05bb-124">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="e05bb-125">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="e05bb-125">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="e05bb-126">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="e05bb-126">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="e05bb-127">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="e05bb-127">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="e05bb-128">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="e05bb-128">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="e05bb-129">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="e05bb-129">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="e05bb-130">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="e05bb-130">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="e05bb-131">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="e05bb-131">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="e05bb-132">Se você estiver usando Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , também deverá especificar os seguintes argumentos:</span><span class="sxs-lookup"><span data-stu-id="e05bb-132">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="e05bb-133">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="e05bb-133">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="e05bb-134">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="e05bb-134">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="e05bb-135">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="e05bb-135">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="e05bb-136">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="e05bb-136">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="e05bb-137">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="e05bb-137">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="e05bb-138">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="e05bb-138">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="e05bb-139">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="e05bb-139">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="e05bb-140">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="e05bb-140">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="e05bb-141">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="e05bb-141">**-SubscriberSecurityMode** = **0**</span></span>  
  
#### <a name="to-start-the-merge-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="e05bb-142">Para iniciar o agente de mesclagem no prompt de comando ou de um arquivo em lotes</span><span class="sxs-lookup"><span data-stu-id="e05bb-142">To start the merge agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="e05bb-143">Do prompt de comando ou em um arquivo em lotes, inicie o [Replication Merge Agent](agents/replication-merge-agent.md) executando **replmerg.exe**, especificando os seguintes argumentos de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="e05bb-143">From the command prompt or in a batch file, start the [Replication Merge Agent](agents/replication-merge-agent.md) by running **replmerg.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="e05bb-144">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="e05bb-144">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="e05bb-145">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="e05bb-145">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="e05bb-146">**-PublisherSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="e05bb-146">**-PublisherSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="e05bb-147">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="e05bb-147">**-Publication**</span></span>  
  
    -   <span data-ttu-id="e05bb-148">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="e05bb-148">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="e05bb-149">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="e05bb-149">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="e05bb-150">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="e05bb-150">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="e05bb-151">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="e05bb-151">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="e05bb-152">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="e05bb-152">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="e05bb-153">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="e05bb-153">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="e05bb-154">Se você estiver usando Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , também deverá especificar os seguintes argumentos:</span><span class="sxs-lookup"><span data-stu-id="e05bb-154">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="e05bb-155">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="e05bb-155">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="e05bb-156">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="e05bb-156">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="e05bb-157">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="e05bb-157">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="e05bb-158">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="e05bb-158">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="e05bb-159">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="e05bb-159">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="e05bb-160">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="e05bb-160">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="e05bb-161">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="e05bb-161">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="e05bb-162">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="e05bb-162">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="e05bb-163">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="e05bb-163">**-SubscriberSecurityMode** = **0**</span></span>  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="e05bb-164">Exemplos (agentes de replicação)</span><span class="sxs-lookup"><span data-stu-id="e05bb-164">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="e05bb-165">O exemplo a seguir inicia o Agente de Distribuição para sincronizar uma assinatura pull.</span><span class="sxs-lookup"><span data-stu-id="e05bb-165">The following example starts the Distribution Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="e05bb-166">Todas as conexões são feitas usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="e05bb-166">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_synctranpullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/synctranpullsub_10.bat)]  
  
 <span data-ttu-id="e05bb-167">O exemplo a seguir inicia o Agente de Mesclagem para sincronizar uma assinatura pull.</span><span class="sxs-lookup"><span data-stu-id="e05bb-167">The following example starts the Merge Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="e05bb-168">Todas as conexões são feitas usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="e05bb-168">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_syncmergepullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/syncmergepullsub_10.bat)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="e05bb-169">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="e05bb-169">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="e05bb-170">É possível sincronizar as assinaturas pull programaticamente usando o RMO (Replication Management Objects) e o acesso de código gerenciado para as funcionalidades do agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="e05bb-170">You can synchronize pull subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="e05bb-171">As classes usadas para sincronizar uma assinatura pull dependem do tipo de publicação ao qual a assinatura pertence.</span><span class="sxs-lookup"><span data-stu-id="e05bb-171">The classes you use to synchronize a pull subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e05bb-172">Se quiser iniciar uma sincronização que execute autonomamente sem afetar seu aplicativo, inicie o agente em modo assíncrono.</span><span class="sxs-lookup"><span data-stu-id="e05bb-172">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="e05bb-173">Porém, se quiser monitorar o resultado da sincronização e receber retornos de chamada do agente durante o processo de sincronização (por exemplo, se quiser exibir uma barra de progresso), inicie o agente de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="e05bb-173">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="e05bb-174">Para os Assinantes do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] , você deve iniciar o agente de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="e05bb-174">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="e05bb-175">Para sincronizar uma assinatura pull com um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="e05bb-175">To synchronize a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="e05bb-176">Crie uma conexão com o Assinante usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="e05bb-176">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="e05bb-177">Crie uma instância de classe <xref:Microsoft.SqlServer.Replication.TransPullSubscription> , e defina as propriedades a seguir:</span><span class="sxs-lookup"><span data-stu-id="e05bb-177">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="e05bb-178">O nome do banco de dados da assinatura para <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-178">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="e05bb-179">O nome da publicação à qual a assinatura pertence para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-179">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="e05bb-180">O nome do banco de dados de publicação para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-180">The name of the publication database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="e05bb-181">O nome do Publicador para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-181">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="e05bb-182">A conexão criada na etapa 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-182">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="e05bb-183">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as demais propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="e05bb-183">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="e05bb-184">Se esse método retornar `false`, verifique se a assinatura existe.</span><span class="sxs-lookup"><span data-stu-id="e05bb-184">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="e05bb-185">Inicie o Distribution Agent no Assinante de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="e05bb-185">Start the Distribution Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="e05bb-186">Chame o método <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> na instância de <xref:Microsoft.SqlServer.Replication.TransPullSubscription> da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="e05bb-186">Call the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransPullSubscription> from step 2.</span></span> <span data-ttu-id="e05bb-187">Esse método inicia o Distribution Agent em modo assíncrono e o controle retorna imediatamente para o seu aplicativo enquanto o trabalho do agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="e05bb-187">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="e05bb-188">Você não poderá chamar este método para Assinantes do [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] ou se a assinatura foi criada com um valor de `false` para <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (o padrão).</span><span class="sxs-lookup"><span data-stu-id="e05bb-188">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="e05bb-189">Obtenha uma instância de classe <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> da propriedade <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> , e chame o método <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="e05bb-189">Get an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="e05bb-190">Esse método inicia o agente de forma síncrona e o controle permanece com o trabalho do agente em execução.</span><span class="sxs-lookup"><span data-stu-id="e05bb-190">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="e05bb-191">Durante execução síncrona, você pode manipular o evento <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> enquanto o agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="e05bb-191">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e05bb-192">Se você especificou um valor de `false` para <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (o padrão) quando criou a assinatura pull, também precisará especificar <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A> e, opcionalmente, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> e <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> porque os metadados relacionados ao trabalho do agente para a assinatura não estão disponíveis no [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e05bb-192">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A>, and optionally <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> and <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="e05bb-193">Para sincronizar uma assinatura pull para publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="e05bb-193">To synchronize a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="e05bb-194">Crie uma conexão com o Assinante usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="e05bb-194">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="e05bb-195">Crie uma instância de classe <xref:Microsoft.SqlServer.Replication.MergePullSubscription> , e defina as propriedades a seguir:</span><span class="sxs-lookup"><span data-stu-id="e05bb-195">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="e05bb-196">O nome do banco de dados da assinatura para <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-196">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="e05bb-197">O nome da publicação à qual a assinatura pertence para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-197">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="e05bb-198">Nome do banco de dados publicado para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-198">The name of the published database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="e05bb-199">O nome do Publicador para <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-199">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="e05bb-200">A conexão criada na etapa 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="e05bb-200">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="e05bb-201">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as demais propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="e05bb-201">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="e05bb-202">Se esse método retornar `false`, verifique se a assinatura existe.</span><span class="sxs-lookup"><span data-stu-id="e05bb-202">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="e05bb-203">Inicie o Merge Agent no Assinante de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="e05bb-203">Start the Merge Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="e05bb-204">Chame o método <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> na instância de <xref:Microsoft.SqlServer.Replication.MergePullSubscription> da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="e05bb-204">Call the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergePullSubscription> from step 2.</span></span> <span data-ttu-id="e05bb-205">Esse método inicia o Merge Agent em modo assíncrono e o controle retorna imediatamente para o seu aplicativo enquanto o trabalho do agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="e05bb-205">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="e05bb-206">Você não poderá chamar este método para Assinantes do [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] ou se a assinatura foi criada com um valor de `false` para <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (o padrão).</span><span class="sxs-lookup"><span data-stu-id="e05bb-206">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="e05bb-207">Obtenha uma instância de classe <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> da propriedade <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> , e chame o método <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="e05bb-207">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="e05bb-208">Esse método inicia o Merge Agent de forma síncrona e o controle permanece com o trabalho do agente em execução.</span><span class="sxs-lookup"><span data-stu-id="e05bb-208">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="e05bb-209">Durante execução síncrona, você pode manipular o evento <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> enquanto o agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="e05bb-209">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e05bb-210">Se você especificou um valor de `false` para <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (o padrão) quando criou a assinatura pull, também precisará especificar <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A> ,,, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A> , e, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A> opcionalmente <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A> ,, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A> e <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> porque os metadados relacionados ao trabalho do agente para a assinatura não estão disponíveis no [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e05bb-210">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A>, and optionally <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A>, and <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="e05bb-211">Exemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="e05bb-211">Examples (RMO)</span></span>  
 <span data-ttu-id="e05bb-212">Esse exemplo sincroniza a assinatura pull para uma publicação transacional, onde o agente é iniciado em modo assíncrono usando o trabalho do agente.</span><span class="sxs-lookup"><span data-stu-id="e05bb-212">This example synchronizes a pull subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub_withjob)]  
  
 <span data-ttu-id="e05bb-213">Esse exemplo sincroniza a assinatura pull com uma publicação transacional, em que o agente é iniciado de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="e05bb-213">This example synchronizes a pull subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub)]  
  
 <span data-ttu-id="e05bb-214">Esse exemplo sincroniza a assinatura pull para uma publicação de mesclagem, onde o agente é iniciado em modo assíncrono usando o trabalho do agente.</span><span class="sxs-lookup"><span data-stu-id="e05bb-214">This example synchronizes a pull subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_withjob)]  
  
 <span data-ttu-id="e05bb-215">Esse exemplo sincroniza a assinatura pull com uma publicação de mesclagem, em que o agente é iniciado de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="e05bb-215">This example synchronizes a pull subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub)]  
  
 <span data-ttu-id="e05bb-216">Esse exemplo sincroniza a assinatura pull para uma publicação de mesclagem usando sincronização da Web.</span><span class="sxs-lookup"><span data-stu-id="e05bb-216">This example synchronizes a pull subscription to a merge publication using Web synchronization.</span></span> <span data-ttu-id="e05bb-217">A assinatura foi criada sem o trabalho do agente e metadados relativos à assinatura, assim o agente deve ser iniciado de forma síncrona e as informações de assinatura adicionais serão fornecidas.</span><span class="sxs-lookup"><span data-stu-id="e05bb-217">The subscription was created without the agent job and related subscription metadata, so the agent must be started synchronously and additional subscription information is supplied.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_NoJobWebSync](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_nojobwebsync)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_NoJobWebSync](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_nojobwebsync)]  
  
## <a name="see-also"></a><span data-ttu-id="e05bb-218">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e05bb-218">See Also</span></span>  
 <span data-ttu-id="e05bb-219">[Sincronizar dados](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="e05bb-219">[Synchronize Data](synchronize-data.md) </span></span>  
 <span data-ttu-id="e05bb-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="e05bb-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="e05bb-221">Replication Security Best Practices</span><span class="sxs-lookup"><span data-stu-id="e05bb-221">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
