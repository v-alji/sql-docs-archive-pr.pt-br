---
title: Sincronizar uma assinatura push | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], push subscriptions
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], synchronizing
ms.assetid: 0cfa7ae5-91d3-4a4f-9edf-a852d45783b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fb2f7bd961748272d6cd67e3412b09d9370a6f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680895"
---
# <a name="synchronize-a-push-subscription"></a><span data-ttu-id="34fc9-102">Sincronizar uma assinatura push</span><span class="sxs-lookup"><span data-stu-id="34fc9-102">Synchronize a Push Subscription</span></span>
  <span data-ttu-id="34fc9-103">Este tópico descreve como sincronizar uma assinatura push no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [agentes de replicação](agents/replication-agents-overview.md), ou RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="34fc9-103">This topic describes how to synchronize a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="34fc9-104">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34fc9-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="34fc9-105">Assinaturas são sincronizadas pelo Agente de Distribuição (para replicação transacional e de instantâneo) ou pelo Agente de Mesclagem (para replicação de mesclagem).</span><span class="sxs-lookup"><span data-stu-id="34fc9-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="34fc9-106">Os agentes podem ser executados continuamente, sob demanda ou em um agendamento.</span><span class="sxs-lookup"><span data-stu-id="34fc9-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="34fc9-107">Para obter mais informações sobre como especificar agendas de sincronização, consulte [Especificar agendas de sincronização](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="34fc9-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="34fc9-108">Sincronize uma assinatura sob demanda das pastas **Publicações Locais** e **Assinaturas Locais** no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e na guia **Todas as Assinaturas** no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="34fc9-108">Synchronize a subscription on demand from the **Local Publications** and **Local Subscriptions** folders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and the **All Subscriptions** tab in Replication Monitor.</span></span> <span data-ttu-id="34fc9-109">As assinaturas para as publicações Oracle não podem ser sincronizadas sob demanda no Assinante.</span><span class="sxs-lookup"><span data-stu-id="34fc9-109">Subscriptions to Oracle publications cannot be synchronized on demand from the Subscriber.</span></span> <span data-ttu-id="34fc9-110">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="34fc9-110">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-publisher"></a><span data-ttu-id="34fc9-111">Para sincronizar uma assinatura push sob demanda no Management Studio (no Publicador)</span><span class="sxs-lookup"><span data-stu-id="34fc9-111">To synchronize a push subscription on demand in Management Studio (at the Publisher)</span></span>  
  
1.  <span data-ttu-id="34fc9-112">Conecte-se ao Publicador no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="34fc9-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="34fc9-113">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="34fc9-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="34fc9-114">Expanda a publicação com relação à qual as assinaturas serão sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="34fc9-114">Expand the publication for which you want to synchronize subscriptions.</span></span>  
  
4.  <span data-ttu-id="34fc9-115">Clique com o botão direito do mouse na assinatura a ser sincronizada e clique em **Exibir Status da Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-115">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="34fc9-116">Na caixa de diálogo **Exibir Status da Sincronização – \<Subscriber>:\<SubscriptionDatabase>** , clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-116">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="34fc9-117">Quando a sincronização estiver concluída, a mensagem **Sincronização concluída** será exibida.</span><span class="sxs-lookup"><span data-stu-id="34fc9-117">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="34fc9-118">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="34fc9-118">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-subscriber"></a><span data-ttu-id="34fc9-119">Para sincronizar uma assinatura push sob demanda no Management Studio (no Assinante)</span><span class="sxs-lookup"><span data-stu-id="34fc9-119">To synchronize a push subscription on demand in Management Studio (at the Subscriber)</span></span>  
  
1.  <span data-ttu-id="34fc9-120">Conecte-se ao Assinante no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="34fc9-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="34fc9-121">Expanda a pasta **Replicação** e, então, expanda a pasta **Assinaturas Locais** .</span><span class="sxs-lookup"><span data-stu-id="34fc9-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="34fc9-122">Clique com o botão direito do mouse na assinatura a ser sincronizada e clique em **Exibir Status da Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-122">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="34fc9-123">Uma mensagem é exibida sobre como estabelecer conexão com o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="34fc9-123">A message is displayed about establishing a connection to the Distributor.</span></span> <span data-ttu-id="34fc9-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-124">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="34fc9-125">Na caixa de diálogo **Exibir Status da Sincronização – \<Subscriber>:\<SubscriptionDatabase>** , clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-125">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="34fc9-126">Quando a sincronização estiver concluída, a mensagem **Sincronização concluída** será exibida.</span><span class="sxs-lookup"><span data-stu-id="34fc9-126">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="34fc9-127">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="34fc9-127">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-replication-monitor"></a><span data-ttu-id="34fc9-128">Para sincronizar uma assinatura push sob demanda no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="34fc9-128">To synchronize a push subscription on demand in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="34fc9-129">No Replication Monitor, expanda um Grupo do publicador no painel esquerdo, expanda um Publicador e, depois, clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="34fc9-129">In Replication Monitor, expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="34fc9-130">Clique na guia **Todas as Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="34fc9-130">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="34fc9-131">Clique com o botão direito do mouse na assinatura a ser sincronizada, depois clique em **Iniciar Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-131">Right-click the subscription you want to synchronize, and then click **Start Synchronizing**.</span></span>  
  
4.  <span data-ttu-id="34fc9-132">Para exibir o andamento da sincronização, clique com o botão direito do mouse na assinatura e, depois, clique em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-132">To view synchronization progress, right-click the subscription, and then click **View Details**.</span></span>  
  
##  <a name="using-replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="34fc9-133">Usando agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="34fc9-133">Using Replication Agents</span></span>  
 <span data-ttu-id="34fc9-134">Assinaturas push podem ser sincronizadas por programa e sob demanda chamando o arquivo executável apropriado do agente de replicação do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="34fc9-134">Push subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="34fc9-135">O arquivo executável do agente de replicação chamado dependerá do tipo de publicação para a qual a assinatura push pertence.</span><span class="sxs-lookup"><span data-stu-id="34fc9-135">The replication agent executable file that is invoked will depend on the type of publication to which the push subscription belongs.</span></span>  
  
#### <a name="to-start-the-distribution-agent-to-synchronize-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="34fc9-136">Para iniciar o Distribution Agent para sincronizar uma assinatura push a uma publicação transacional</span><span class="sxs-lookup"><span data-stu-id="34fc9-136">To start the Distribution Agent to synchronize a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="34fc9-137">Do prompt de comando ou do arquivo de lote no Distribuidor, execute **distrib.exe**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-137">From the command prompt or in a batch file at the Distributor, execute **distrib.exe**.</span></span> <span data-ttu-id="34fc9-138">Especifique os seguintes argumentos de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="34fc9-138">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="34fc9-139">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="34fc9-139">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="34fc9-140">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="34fc9-140">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="34fc9-141">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="34fc9-141">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="34fc9-142">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="34fc9-142">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="34fc9-143">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="34fc9-143">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="34fc9-144">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="34fc9-144">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="34fc9-145">Se você estiver usando Autenticação do SQL Server, deve-se também especificar os seguintes argumentos:</span><span class="sxs-lookup"><span data-stu-id="34fc9-145">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="34fc9-146">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="34fc9-146">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="34fc9-147">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="34fc9-147">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="34fc9-148">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="34fc9-148">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="34fc9-149">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="34fc9-149">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="34fc9-150">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="34fc9-150">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="34fc9-151">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="34fc9-151">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="34fc9-152">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="34fc9-152">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="34fc9-153">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="34fc9-153">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="34fc9-154">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="34fc9-154">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
#### <a name="to-start-the-merge-agent-to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="34fc9-155">Para iniciar o Merge Agent para sincronizar uma assinatura push a uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="34fc9-155">To start the Merge Agent to synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="34fc9-156">Do prompt de comando ou do arquivo de lote no Distribuidor, execute **replmerg.exe**.</span><span class="sxs-lookup"><span data-stu-id="34fc9-156">From the command prompt or in a batch file at the Distributor, execute **replmerg.exe**.</span></span> <span data-ttu-id="34fc9-157">Especifique os seguintes argumentos de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="34fc9-157">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="34fc9-158">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="34fc9-158">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="34fc9-159">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="34fc9-159">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="34fc9-160">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="34fc9-160">**-Publication**</span></span>  
  
    -   <span data-ttu-id="34fc9-161">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="34fc9-161">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="34fc9-162">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="34fc9-162">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="34fc9-163">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="34fc9-163">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="34fc9-164">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="34fc9-164">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="34fc9-165">Se você estiver usando Autenticação do SQL Server, deve-se também especificar os seguintes argumentos:</span><span class="sxs-lookup"><span data-stu-id="34fc9-165">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="34fc9-166">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="34fc9-166">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="34fc9-167">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="34fc9-167">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="34fc9-168">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="34fc9-168">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="34fc9-169">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="34fc9-169">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="34fc9-170">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="34fc9-170">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="34fc9-171">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="34fc9-171">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="34fc9-172">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="34fc9-172">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="34fc9-173">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="34fc9-173">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="34fc9-174">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="34fc9-174">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="34fc9-175">Exemplos (agentes de replicação)</span><span class="sxs-lookup"><span data-stu-id="34fc9-175">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="34fc9-176">O exemplo seguinte inicia o Agente de Distribuição para sincronizar uma assinatura push.</span><span class="sxs-lookup"><span data-stu-id="34fc9-176">The following example starts the Distribution Agent to synchronize a push subscription.</span></span>  
  
 
```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksProductsTran  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4
```
  
 <span data-ttu-id="34fc9-177">O exemplo a seguir inicia o Agente de Mesclagem para sincronizar uma assinatura push.</span><span class="sxs-lookup"><span data-stu-id="34fc9-177">The following example starts the Merge Agent to synchronize a push subscription.</span></span>  

```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksSalesOrdersMerge  
  
REM -- Start the Merge Agent.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher %Publisher%   
-Subscriber  %Subscriber%  -Distributor %Publisher% -PublisherDB  %PublicationDB%   
-SubscriberDB %SubscriptionDB% -Publication %Publication% -PublisherSecurityMode 1   
-OutputVerboseLevel 3  -Output -SubscriberSecurityMode 1  -SubscriptionType 0   
-DistributorSecurityMode 1
```
  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="34fc9-178">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="34fc9-178">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="34fc9-179">É possível sincronizar as assinaturas push programaticamente usando o RMO (Replication Management Objects) e o acesso de código gerenciado para as funcionalidades do agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="34fc9-179">You can synchronize push subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="34fc9-180">As classes usadas para sincronizar uma assinatura push dependem do tipo de publicação ao qual a assinatura pertence.</span><span class="sxs-lookup"><span data-stu-id="34fc9-180">The classes that you use to synchronize a push subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34fc9-181">Se quiser iniciar uma sincronização que execute autonomamente sem afetar seu aplicativo, inicie o agente em modo assíncrono.</span><span class="sxs-lookup"><span data-stu-id="34fc9-181">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="34fc9-182">Porém, se quiser monitorar o resultado da sincronização e receber retornos de chamada do agente durante o processo de sincronização (por exemplo, se quiser exibir a barra de andamento), inicie o agente de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="34fc9-182">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, if you want to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="34fc9-183">Para os Assinantes do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] , você deve iniciar o agente de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="34fc9-183">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="34fc9-184">Para sincronizar uma assinatura push a um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="34fc9-184">To synchronize a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="34fc9-185">Crie uma conexão com o Distribuidor usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="34fc9-185">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="34fc9-186">Crie uma instância da classe <xref:Microsoft.SqlServer.Replication.TransSubscription> e defina as propriedades a seguir:</span><span class="sxs-lookup"><span data-stu-id="34fc9-186">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class and set the following properties:</span></span>  
  
    -   <span data-ttu-id="34fc9-187">O nome do banco de dados de publicação para <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-187">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-188">O nome da publicação à qual a assinatura pertence para <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-188">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-189">O nome do banco de dados de assinatura para <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-189">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-190">O nome do Assinante para <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-190">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-191">A conexão criada na etapa 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-191">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="34fc9-192">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as demais propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="34fc9-192">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="34fc9-193">Se esse método retornar `false`, verifique se a assinatura existe.</span><span class="sxs-lookup"><span data-stu-id="34fc9-193">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="34fc9-194">Inicie o Distribution Agent no Distribuidor de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="34fc9-194">Start the Distribution Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="34fc9-195">Chame o método <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> na instância de <xref:Microsoft.SqlServer.Replication.TransSubscription> da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="34fc9-195">Call the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransSubscription> from step 2.</span></span> <span data-ttu-id="34fc9-196">Esse método inicia o Distribution Agent em modo assíncrono e o controle retorna imediatamente para o seu aplicativo enquanto o trabalho do agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="34fc9-196">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="34fc9-197">Você não poderá chamar este método se a assinatura foi criada com um valor de `false` para <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-197">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-198">Obtenha uma instância de classe <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> da propriedade <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> , e chame o método <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="34fc9-198">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="34fc9-199">Esse método inicia o agente de forma síncrona e o controle permanece com o trabalho do agente em execução.</span><span class="sxs-lookup"><span data-stu-id="34fc9-199">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="34fc9-200">Durante a execução síncrona você pode manipular o evento <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> com o agente em execução.</span><span class="sxs-lookup"><span data-stu-id="34fc9-200">During synchronous execution you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="34fc9-201">Para sincronizar uma assinatura push a uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="34fc9-201">To synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="34fc9-202">Crie uma conexão com o Distribuidor usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="34fc9-202">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="34fc9-203">Crie uma instância de classe <xref:Microsoft.SqlServer.Replication.MergeSubscription> , e defina as propriedades a seguir:</span><span class="sxs-lookup"><span data-stu-id="34fc9-203">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="34fc9-204">O nome do banco de dados de publicação para <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-204">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-205">O nome da publicação à qual a assinatura pertence para <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-205">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-206">O nome do banco de dados de assinatura para <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-206">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-207">O nome do Assinante para <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-207">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-208">A conexão criada na etapa 1 para <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-208">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="34fc9-209">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as demais propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="34fc9-209">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="34fc9-210">Se esse método retornar `false`, verifique se a assinatura existe.</span><span class="sxs-lookup"><span data-stu-id="34fc9-210">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="34fc9-211">Inicie o Merge Agent no Distribuidor de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="34fc9-211">Start the Merge Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="34fc9-212">Chame o método <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> na instância de <xref:Microsoft.SqlServer.Replication.MergeSubscription> da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="34fc9-212">Call the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergeSubscription> from step 2.</span></span> <span data-ttu-id="34fc9-213">Esse método inicia o Merge Agent em modo assíncrono e o controle retorna imediatamente para o seu aplicativo enquanto o trabalho do agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="34fc9-213">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="34fc9-214">Você não poderá chamar este método se a assinatura foi criada com um valor de `false` para <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="34fc9-214">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="34fc9-215">Obtenha uma instância de classe <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> da propriedade <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> , e chame o método <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="34fc9-215">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="34fc9-216">Esse método inicia o Merge Agent de forma síncrona e o controle permanece com o trabalho do agente em execução.</span><span class="sxs-lookup"><span data-stu-id="34fc9-216">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="34fc9-217">Durante execução síncrona, você pode manipular o evento <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> enquanto o agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="34fc9-217">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="34fc9-218">Exemplos (RMO)</span><span class="sxs-lookup"><span data-stu-id="34fc9-218">Examples (RMO)</span></span>  
 <span data-ttu-id="34fc9-219">Este exemplo sincroniza a assinatura push a uma publicação transacional, onde o agente é iniciado de forma assíncrona usando o trabalho do agente.</span><span class="sxs-lookup"><span data-stu-id="34fc9-219">This example synchronizes a push subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub_withjob)]  
  
 <span data-ttu-id="34fc9-220">Este exemplo sincroniza a assinatura push a uma publicação transacional, onde o agente é iniciado de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="34fc9-220">This example synchronizes a push subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub)]  
  
 <span data-ttu-id="34fc9-221">Este exemplo sincroniza a assinatura push a uma publicação de mesclagem, onde o agente é iniciado de forma assíncrona usando o trabalho do agente.</span><span class="sxs-lookup"><span data-stu-id="34fc9-221">This example synchronizes a push subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub_withjob)]  
  
 <span data-ttu-id="34fc9-222">Este exemplo sincroniza a assinatura push a uma publicação de mesclagem, onde o agente é iniciado de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="34fc9-222">This example synchronizes a push subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="34fc9-223">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34fc9-223">See Also</span></span>  
 <span data-ttu-id="34fc9-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="34fc9-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="34fc9-225">[Sincronizar dados](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="34fc9-225">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="34fc9-226">Replication Security Best Practices</span><span class="sxs-lookup"><span data-stu-id="34fc9-226">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
