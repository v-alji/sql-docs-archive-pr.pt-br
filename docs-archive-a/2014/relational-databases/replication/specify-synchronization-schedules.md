---
title: Especificar agendas de sincronização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], synchronizing
- scheduling synchronization [SQL Server replication]
- synchronization [SQL Server replication], schedules
- replication [SQL Server], synchronization
ms.assetid: 97f2535b-ec19-4973-823d-bcf3d5aa0216
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d752817f7d620b2c6e5fdc5eeb2178c50c42040
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684151"
---
# <a name="specify-synchronization-schedules"></a><span data-ttu-id="3e53c-102">Especificar agendas de sincronização</span><span class="sxs-lookup"><span data-stu-id="3e53c-102">Specify Synchronization Schedules</span></span>
  <span data-ttu-id="3e53c-103">Este tópico descreve como especificar agendas de sincronização no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)]ou o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="3e53c-103">This topic describes how to specify synchronization schedules in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="3e53c-104">Quando criar uma assinatura, você pode definir uma agenda de sincronização que controla quando o agente de replicação para a assinatura executará.</span><span class="sxs-lookup"><span data-stu-id="3e53c-104">When you create a subscription, you can define a synchronization schedule that controls when the replication agent for the subscription will run.</span></span> <span data-ttu-id="3e53c-105">Se você não especificar os parâmetros de programação, a assinatura usará a agenda padrão.</span><span class="sxs-lookup"><span data-stu-id="3e53c-105">If you do not specify scheduling parameters, the subscription will use the default schedule.</span></span>  
  
 <span data-ttu-id="3e53c-106">Assinaturas são sincronizadas pelo Agente de Distribuição (para replicação transacional e de instantâneo) ou pelo Agente de Mesclagem (para replicação de mesclagem).</span><span class="sxs-lookup"><span data-stu-id="3e53c-106">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="3e53c-107">Os agentes podem ser executados continuamente, sob demanda ou em um agendamento.</span><span class="sxs-lookup"><span data-stu-id="3e53c-107">Agents can run continuously, run on demand, or run on a schedule.</span></span>  
  
 <span data-ttu-id="3e53c-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3e53c-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3e53c-109">**Para especificar agendas de sincronização, usando:**</span><span class="sxs-lookup"><span data-stu-id="3e53c-109">**To specify synchronization schedules, using:**</span></span>  
  
     [<span data-ttu-id="3e53c-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e53c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3e53c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e53c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="3e53c-112">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="3e53c-112">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3e53c-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e53c-113">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3e53c-114">Especifique agendas de sincronização na página **Agenda de Sincronização** do Assistente para Nova Assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-114">Specify synchronization schedules on the **Synchronization Schedule** page of the New Subscription Wizard.</span></span> <span data-ttu-id="3e53c-115">Para mais informações sobre como acessar esse assistente, consulte [Create a Push Subscription](create-a-push-subscription.md) e [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-115">For more information about accessing this wizard, see [Create a Push Subscription](create-a-push-subscription.md) and [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="3e53c-116">Modifique agendas de sincronização na caixa de diálogo **Propriedades da Agenda de Trabalho** , que se encontra disponível na pasta **Trabalhos** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e nas janelas de detalhes do agente no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-116">Modify synchronization schedules in the **Job Schedule Properties** dialog box, which is available from the **Jobs** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and from the agent details windows in Replication Monitor.</span></span> <span data-ttu-id="3e53c-117">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="3e53c-117">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="3e53c-118">Se você especificar agendas da pasta **Jobs** use a tabela a seguir para determinar o nome do trabalho do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-118">If you specify schedules from the **Jobs** folder, use the following table to determine the agent job name.</span></span>  
  
|<span data-ttu-id="3e53c-119">Agente</span><span class="sxs-lookup"><span data-stu-id="3e53c-119">Agent</span></span>|<span data-ttu-id="3e53c-120">Nome do trabalho</span><span class="sxs-lookup"><span data-stu-id="3e53c-120">Job name</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="3e53c-121">Merge Agent para assinaturas pull</span><span class="sxs-lookup"><span data-stu-id="3e53c-121">Merge Agent for pull subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<integer>**|  
|<span data-ttu-id="3e53c-122">Merge Agent para assinaturas push</span><span class="sxs-lookup"><span data-stu-id="3e53c-122">Merge Agent for push subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|  
|<span data-ttu-id="3e53c-123">Distribution Agent para assinaturas push</span><span class="sxs-lookup"><span data-stu-id="3e53c-123">Distribution Agent for push subscriptions</span></span>|<span data-ttu-id="3e53c-124">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3e53c-124">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span></span>|  
|<span data-ttu-id="3e53c-125">Distribution Agent para assinaturas pull</span><span class="sxs-lookup"><span data-stu-id="3e53c-125">Distribution Agent for pull subscriptions</span></span>|<span data-ttu-id="3e53c-126">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3e53c-126">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span></span>|  
|<span data-ttu-id="3e53c-127">Distribution Agent para assinaturas push para Assinantes não SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e53c-127">Distribution Agent for push subscriptions to non-SQL Server Subscribers</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|  
  
 <span data-ttu-id="3e53c-128"><sup>1</sup> Para assinaturas push para publicações Oracle, é \*\*\<Publisher>-\<Publisher**> em vez de **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="3e53c-128"><sup>1</sup> For push subscriptions to Oracle publications, it is \*\*\<Publisher>-\<Publisher**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
 <span data-ttu-id="3e53c-129"><sup>2</sup> Para assinaturas pull para publicações Oracle, é \*\*\<Publisher>-\<DistributionDatabase**> em vez de **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="3e53c-129"><sup>2</sup> For pull subscriptions to Oracle publications, it is \*\*\<Publisher>-\<DistributionDatabase**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
#### <a name="to-specify-synchronization-schedules"></a><span data-ttu-id="3e53c-130">Para especificar agendas de sincronização</span><span class="sxs-lookup"><span data-stu-id="3e53c-130">To specify synchronization schedules</span></span>  
  
1.  <span data-ttu-id="3e53c-131">Na página **SynchronizationSchedule** do Assistente para Nova Assinatura, selecione um dos seguintes valores da lista suspensa **Agenda do Agente** para cada assinatura que está sendo criada:</span><span class="sxs-lookup"><span data-stu-id="3e53c-131">On the **SynchronizationSchedule** page of the New Subscription Wizard, select one of the following values from the **Agent Schedule** drop-down list for each subscription you are creating:</span></span>  
  
    -   <span data-ttu-id="3e53c-132">**Executar continuamente**</span><span class="sxs-lookup"><span data-stu-id="3e53c-132">**Run continuously**</span></span>  
  
    -   <span data-ttu-id="3e53c-133">**Executar somente sob demanda**</span><span class="sxs-lookup"><span data-stu-id="3e53c-133">**Run on demand only**</span></span>  
  
    -   **\<Define Schedule...>**  
  
2.  <span data-ttu-id="3e53c-134">Se você selecionar **\<Define Schedule...>** , especifique uma agenda na caixa de diálogo **Propriedades da Agenda de Trabalho** e, então, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-134">If you select **\<Define Schedule...>**, specify a schedule in the **Job Schedule Properties** dialog box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3e53c-135">Conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-135">Complete the wizard.</span></span>  
  
#### <a name="to-modify-a-synchronization-schedule-for-a-push-subscription-in-replication-monitor"></a><span data-ttu-id="3e53c-136">Para modificar uma agenda de sincronização para uma assinatura push no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="3e53c-136">To modify a synchronization schedule for a push subscription in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="3e53c-137">Expanda um Grupo do publicador no painel esquerdo do Replication Monitor, expanda um Publicador e, em seguida, clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="3e53c-137">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="3e53c-138">Clique na guia **Todas as Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="3e53c-138">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="3e53c-139">Clique com o botão direito do mouse em uma assinatura e clique em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-139">Right-click a subscription, and then click **View Details**.</span></span>  
  
4.  <span data-ttu-id="3e53c-140">Na janela **assinatura \< SubscriptionName> \*\* , clique em **ação**e, em seguida, clique em \*\* \<AgentName> Propriedades do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-140">In the **Subscription \< SubscriptionName>** window, click **Action**, and then click **\<AgentName> Job Properties**.</span></span>  
  
5.  <span data-ttu-id="3e53c-141">Na página **Agendas** da caixa de diálogo **Propriedades do Trabalho – \<JobName>** , clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="3e53c-141">On the **Schedules** page of the **Job Properties - \<JobName>** dialog box, click **Edit.**</span></span>  
  
6.  <span data-ttu-id="3e53c-142">Na caixa de diálogo **Propriedades da Agenda de Trabalho** , selecione um valor da lista suspensa **Tipo de Agenda** :</span><span class="sxs-lookup"><span data-stu-id="3e53c-142">In the **Job Schedule Properties** dialog box, select a value from the **Schedule Type** drop-down list:</span></span>  
  
    -   <span data-ttu-id="3e53c-143">Para especificar que o agente deve executar continuamente, selecione **Iniciar automaticamente quando o SQL Server Agent for iniciado**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-143">To specify that the agent should run continuously, select **Start automatically when SQL Server Agent starts**.</span></span>  
  
    -   <span data-ttu-id="3e53c-144">Para especificar que o agente deve ser executado em uma agenda, selecione **Recorrente**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-144">To specify that the agent should run on a schedule, select **Recurring**.</span></span>  
  
    -   <span data-ttu-id="3e53c-145">Para especificar que o agente deve ser executado sob demanda, selecione **Uma vez**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-145">To specify that the agent should run on demand, select **One time**.</span></span>  
  
7.  <span data-ttu-id="3e53c-146">Se você selecionar **Recorrente**, especifique uma agenda para o agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-146">If you select **Recurring**, specify a schedule for the agent.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
#### <a name="to-modify-a-synchronization-schedule-for-a-push-subscription-in-management-studio"></a><span data-ttu-id="3e53c-147">Para modificar uma agenda de sincronização para uma assinatura push no Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e53c-147">To modify a synchronization schedule for a push subscription in Management Studio</span></span>  
  
1.  <span data-ttu-id="3e53c-148">Conecte-se ao Distribuidor no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e, em seguida, expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-148">Connect to the Distributor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="3e53c-149">Expanda a pasta **SQL Server Agent** e, em seguida, a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="3e53c-149">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="3e53c-150">Clique com o botão direito do mouse no trabalho para o Distribution Agent ou Merge Agent associado à assinatura e, então, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-150">Right-click the job for the Distribution Agent or Merge Agent associated with the subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3e53c-151">Na página **Agendas** da caixa de diálogo **Propriedades do Trabalho – \<JobName>** , clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="3e53c-151">On the **Schedules** page of the **Job Properties - \<JobName>** dialog box, click **Edit.**</span></span>  
  
5.  <span data-ttu-id="3e53c-152">Na caixa de diálogo **Propriedades da Agenda de Trabalho** , selecione um valor da lista suspensa **Tipo de Agenda** :</span><span class="sxs-lookup"><span data-stu-id="3e53c-152">In the **Job Schedule Properties** dialog box, select a value from the **Schedule Type** drop-down list:</span></span>  
  
    -   <span data-ttu-id="3e53c-153">Para especificar que o agente deve executar continuamente, selecione **Iniciar automaticamente quando o SQL Server Agent for iniciado**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-153">To specify that the agent should run continuously, select **Start automatically when SQL Server Agent starts**.</span></span>  
  
    -   <span data-ttu-id="3e53c-154">Para especificar que o agente deve ser executado em uma agenda, selecione **Recorrente**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-154">To specify that the agent should run on a schedule, select **Recurring**.</span></span>  
  
    -   <span data-ttu-id="3e53c-155">Para especificar que o agente deve ser executado sob demanda, selecione **Uma vez**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-155">To specify that the agent should run on demand, select **One time**.</span></span>  
  
6.  <span data-ttu-id="3e53c-156">Se você selecionar **Recorrente**, especifique uma agenda para o agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-156">If you select **Recurring**, specify a schedule for the agent.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
#### <a name="to-modify-a-synchronization-schedule-for-a-pull-subscription-in-management-studio"></a><span data-ttu-id="3e53c-157">Para modificar uma agenda de sincronização para uma assinatura pull no Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e53c-157">To modify a synchronization schedule for a pull subscription in Management Studio</span></span>  
  
1.  <span data-ttu-id="3e53c-158">Conecte-se ao Assinante no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-158">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="3e53c-159">Expanda a pasta **SQL Server Agent** e, em seguida, a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="3e53c-159">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="3e53c-160">Clique com o botão direito do mouse no trabalho para o Distribution Agent ou Merge Agent associado à assinatura e, então, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-160">Right-click the job for the Distribution Agent or Merge Agent associated with the subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3e53c-161">Na página **Agendas** da caixa de diálogo **Propriedades do Trabalho – \<JobName>** , clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="3e53c-161">On the **Schedules** page of the **Job Properties - \<JobName>** dialog box, click **Edit.**</span></span>  
  
5.  <span data-ttu-id="3e53c-162">Na caixa de diálogo **Propriedades da Agenda de Trabalho** , selecione um valor da lista suspensa **Tipo de Agenda** :</span><span class="sxs-lookup"><span data-stu-id="3e53c-162">In the **Job Schedule Properties** dialog box, select a value from the **Schedule Type** drop-down list:</span></span>  
  
    -   <span data-ttu-id="3e53c-163">Para especificar que o agente deve executar continuamente, selecione **Iniciar automaticamente quando o SQL Server Agent for iniciado**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-163">To specify that the agent should run continuously, select **Start automatically when SQL Server Agent starts**.</span></span>  
  
    -   <span data-ttu-id="3e53c-164">Para especificar que o agente deve ser executado em uma agenda, selecione **Recorrente**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-164">To specify that the agent should run on a schedule, select **Recurring**.</span></span>  
  
    -   <span data-ttu-id="3e53c-165">Para especificar que o agente deve ser executado sob demanda, selecione **Uma vez**.</span><span class="sxs-lookup"><span data-stu-id="3e53c-165">To specify that the agent should run on demand, select **One time**.</span></span>  
  
6.  <span data-ttu-id="3e53c-166">Se você selecionar **Recorrente**, especifique uma agenda para o agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-166">If you select **Recurring**, specify a schedule for the agent.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3e53c-167">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e53c-167">Using Transact-SQL</span></span>  
 <span data-ttu-id="3e53c-168">Você pode definir agendas de sincronização de forma programada, usando os procedimentos de replicação armazenados.</span><span class="sxs-lookup"><span data-stu-id="3e53c-168">You can define synchronization schedules programmatically using replication stored procedures.</span></span> <span data-ttu-id="3e53c-169">Os procedimentos armazenados que você usar dependem do tipo de replicação e do tipo de assinatura (de recepção ou push).</span><span class="sxs-lookup"><span data-stu-id="3e53c-169">The stored procedures that you use depend on the type of replication and the type of subscription (pull or push).</span></span>  
  
 <span data-ttu-id="3e53c-170">Uma agenda é definida pelos seguintes parâmetros de programação, os comportamentos dos quais são herdados de [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql):</span><span class="sxs-lookup"><span data-stu-id="3e53c-170">A schedule is defined by the following scheduling parameters, the behaviors of which are inherited from [sp_add_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql):</span></span>  
  
-   <span data-ttu-id="3e53c-171">**@frequency_type**-o tipo de frequência usado ao agendar o agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-171">**@frequency_type** - the type of frequency used when scheduling the agent.</span></span>  
  
-   <span data-ttu-id="3e53c-172">**@frequency_interval**-o dia da semana em que um agente é executado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-172">**@frequency_interval** - the day of the week when an agent runs.</span></span>  
  
-   <span data-ttu-id="3e53c-173">**@frequency_relative_interval**-a semana de um determinado mês em que o agente está agendado para ser executado mensalmente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-173">**@frequency_relative_interval** - the week of a given month when the agent is scheduled to run monthly.</span></span>  
  
-   <span data-ttu-id="3e53c-174">**@frequency_recurrence_factor**-o número de unidades de tipo de frequência que ocorrem entre sincronizações.</span><span class="sxs-lookup"><span data-stu-id="3e53c-174">**@frequency_recurrence_factor** - the number of frequency-type units that occur between synchronizations.</span></span>  
  
-   <span data-ttu-id="3e53c-175">**@frequency_subday**-a unidade de frequência quando o agente é executado com mais frequência do que uma vez por dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-175">**@frequency_subday** - the frequency unit when the agent runs more often than once a day.</span></span>  
  
-   <span data-ttu-id="3e53c-176">**@frequency_subday_interval**-o número de unidades de frequência entre as execuções quando o agente é executado com frequência maior do que uma vez por dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-176">**@frequency_subday_interval** - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
-   <span data-ttu-id="3e53c-177">**@active_start_time_of_day**-a hora mais antiga em um determinado dia em que uma execução de agente será iniciada.</span><span class="sxs-lookup"><span data-stu-id="3e53c-177">**@active_start_time_of_day** - the earliest time in a given day when an agent run will start.</span></span>  
  
-   <span data-ttu-id="3e53c-178">**@active_end_time_of_day**-o horário mais recente em um determinado dia em que uma execução de agente será iniciada.</span><span class="sxs-lookup"><span data-stu-id="3e53c-178">**@active_end_time_of_day** - the latest time in a given day when an agent run will start.</span></span>  
  
-   <span data-ttu-id="3e53c-179">**@active_start_date**-o primeiro dia em que a agenda do agente estará em vigor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-179">**@active_start_date** - the first day that the agent schedule will be in effect.</span></span>  
  
-   <span data-ttu-id="3e53c-180">**@active_end_date**-o último dia em que a agenda do agente estará em vigor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-180">**@active_end_date** - the last day that the agent schedule will be in effect.</span></span>  
  
#### <a name="to-define-the-synchronization-schedule-for-a-pull-subscription-to-a-transactional-publication"></a><span data-ttu-id="3e53c-181">Para definir a agenda de sincronização para uma assinatura pull em uma publicação transacional</span><span class="sxs-lookup"><span data-stu-id="3e53c-181">To define the synchronization schedule for a pull subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="3e53c-182">Crie uma assinatura pull nova para uma publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="3e53c-182">Create a new pull subscription to a transactional publication.</span></span> <span data-ttu-id="3e53c-183">Para obter mais informações, consulte [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-183">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
2.  <span data-ttu-id="3e53c-184">No Assinante, execute [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e53c-184">At the Subscriber, execute [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql).</span></span> <span data-ttu-id="3e53c-185">Especifique **@publisher** , **@publisher_db** , e **@publication** as [!INCLUDE[msCoName](../../includes/msconame-md.md)] credenciais do Windows sob as quais o agente de distribuição no assinante é executado para **@job_name** e **@password** .</span><span class="sxs-lookup"><span data-stu-id="3e53c-185">Specify **@publisher**, **@publisher_db**, **@publication**, and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows credentials under which the Distribution Agent at the Subscriber runs for **@job_name** and **@password**.</span></span> <span data-ttu-id="3e53c-186">Especifique os parâmetros de sincronização, detalhados acima, que definem a agenda para o trabalho do Distribution Agent que sincroniza a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-186">Specify the synchronization parameters, detailed above, that define the schedule for the Distribution Agent job that synchronizes the subscription.</span></span>  
  
#### <a name="to-define-the-synchronization-schedule-for-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="3e53c-187">Para definir a agenda de sincronização para uma assinatura push em uma publicação transacional</span><span class="sxs-lookup"><span data-stu-id="3e53c-187">To define the synchronization schedule for a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="3e53c-188">Crie uma assinatura push nova para uma publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="3e53c-188">Create a new push subscription to a transactional publication.</span></span> <span data-ttu-id="3e53c-189">Para obter mais informações, consulte [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-189">For more information, see [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="3e53c-190">No Assinante, execute [sp_addpushsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e53c-190">At the Subscriber, execute [sp_addpushsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql).</span></span> <span data-ttu-id="3e53c-191">Especifique **@subscriber** , **@subscriber_db** , e **@publication** as credenciais do Windows sob as quais o agente de distribuição no assinante é executado para **@job_name** e **@password** .</span><span class="sxs-lookup"><span data-stu-id="3e53c-191">Specify **@subscriber**, **@subscriber_db**, **@publication**, and the Windows credentials under which the Distribution Agent at the Subscriber runs for **@job_name** and **@password**.</span></span> <span data-ttu-id="3e53c-192">Especifique os parâmetros de sincronização, detalhados acima, que definem a agenda para o trabalho do Distribution Agent que sincroniza a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-192">Specify the synchronization parameters, detailed above, that define the schedule for the Distribution Agent job that synchronizes the subscription.</span></span>  
  
#### <a name="to-define-the-synchronization-schedule-for-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="3e53c-193">Para definir a agenda de sincronização para uma assinatura pull em uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="3e53c-193">To define the synchronization schedule for a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="3e53c-194">Crie uma assinatura pull nova para uma publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="3e53c-194">Create a new pull subscription to a merge publication.</span></span> <span data-ttu-id="3e53c-195">Para obter mais informações, consulte [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-195">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
2.  <span data-ttu-id="3e53c-196">No Assinante, execute o [sp_addmergepullsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e53c-196">At the Subscriber, execute [sp_addmergepullsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql).</span></span> <span data-ttu-id="3e53c-197">Especifique **@publisher** , **@publisher_db** , e **@publication** as credenciais do Windows sob as quais o agente de mesclagem no assinante é executado para **@job_name** e **@password** .</span><span class="sxs-lookup"><span data-stu-id="3e53c-197">Specify **@publisher**, **@publisher_db**, **@publication**, and the Windows credentials under which the Merge Agent at the Subscriber runs for **@job_name** and **@password**.</span></span> <span data-ttu-id="3e53c-198">Especifique os parâmetros de sincronização, detalhados acima, que definem a agenda para o trabalho do Agente de Mesclagem que sincroniza a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-198">Specify the synchronization parameters, detailed above, that define the schedule for the Merge Agent job that synchronizes the subscription.</span></span>  
  
#### <a name="to-define-the-synchronization-schedule-for-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="3e53c-199">Para definir a agenda de sincronização para uma assinatura push em uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="3e53c-199">To define the synchronization schedule for a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="3e53c-200">Crie uma assinatura push nova para uma publicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="3e53c-200">Create a new push subscription to a merge publication.</span></span> <span data-ttu-id="3e53c-201">Para obter mais informações, consulte [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-201">For more information, see [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="3e53c-202">No Assinante, execute o [sp_addmergepushsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e53c-202">At the Subscriber, execute [sp_addmergepushsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql).</span></span> <span data-ttu-id="3e53c-203">Especifique **@subscriber** , **@subscriber_db** , e **@publication** as credenciais do Windows sob as quais o agente de mesclagem no assinante é executado para **@job_name** e **@password** .</span><span class="sxs-lookup"><span data-stu-id="3e53c-203">Specify **@subscriber**, **@subscriber_db**, **@publication**, and the Windows credentials under which the Merge Agent at the Subscriber runs for **@job_name** and **@password**.</span></span> <span data-ttu-id="3e53c-204">Especifique os parâmetros de sincronização, detalhados acima, que definem a agenda para o trabalho do Agente de Mesclagem que sincroniza a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-204">Specify the synchronization parameters, detailed above, that define the schedule for the Merge Agent job that synchronizes the subscription.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="3e53c-205">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="3e53c-205">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="3e53c-206">A replicação usa o SQL Server Agent para agendar trabalhos para atividades que ocorrem periodicamente, como geração de instantâneo e sincronização de assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-206">Replication uses the SQL Server Agent to schedule jobs for activities that occur periodically, such as snapshot generation and subscription synchronization.</span></span> <span data-ttu-id="3e53c-207">Use programaticamente os RMO (Replication Management Objects) para especificar agendamentos de trabalhos de agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="3e53c-207">You can use Replication Management Objects (RMO) programmatically to specify schedules for replication agent jobs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e53c-208">Quando uma subscrição é criada e um valor `false` é especificado para `CreateSyncAgentByDefault` (comportamento padrão para inscrições pull), o trabalho do agente não é criado e as propriedades agendadas são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="3e53c-208">When you create a subscription and specify a value `false` for `CreateSyncAgentByDefault` (the default behavior for pull subscriptions) the agent job is not created and scheduling properties are ignored.</span></span> <span data-ttu-id="3e53c-209">Nesse caso, o agendamento de sincronização precisará ser determinado pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3e53c-209">In this case, the synchronization schedule must be determined by the application.</span></span> <span data-ttu-id="3e53c-210">Para obter mais informações, consulte [Create a Pull Subscription](create-a-pull-subscription.md) e [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-210">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md) and [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
#### <a name="to-define-a-replication-agent-schedule-when-you-create-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="3e53c-211">Para definir um agendamento de agente de replicação quando é criada uma assinatura push para uma publicação transacional</span><span class="sxs-lookup"><span data-stu-id="3e53c-211">To define a replication agent schedule when you create a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="3e53c-212">Crie uma instância da classe <xref:Microsoft.SqlServer.Replication.TransSubscription> para a assinatura que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="3e53c-212">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class for the subscription you are creating.</span></span> <span data-ttu-id="3e53c-213">Para obter mais informações, consulte [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-213">For more information, see [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="3e53c-214">Antes de chamar <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A>, defina um ou mais dos campos seguintes da propriedade <xref:Microsoft.SqlServer.Replication.Subscription.AgentSchedule%2A> :</span><span class="sxs-lookup"><span data-stu-id="3e53c-214">Before you call <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A>, set one or more of the following fields of the <xref:Microsoft.SqlServer.Replication.Subscription.AgentSchedule%2A> property:</span></span>  
  
    -   <span data-ttu-id="3e53c-215"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - o tipo de frequência (como diária ou semanalmente) usado para agendar o agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-215"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - the type of frequency (such as daily or weekly) you use when you schedule the agent.</span></span>  
  
    -   <span data-ttu-id="3e53c-216"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - dia da semana em que o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-216"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - the day of the week that an agent runs.</span></span>  
  
    -   <span data-ttu-id="3e53c-217"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - semana de um determinado mês em que o agente é agendado para ser executado mensalmente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-217"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - the week of a given month when the agent is scheduled to run monthly.</span></span>  
  
    -   <span data-ttu-id="3e53c-218"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - número de unidades do tipo-frequência que ocorrem entre sincronizações.</span><span class="sxs-lookup"><span data-stu-id="3e53c-218"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - the number of frequency-type units that occur between synchronizations.</span></span>  
  
    -   <span data-ttu-id="3e53c-219"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - unidade de frequência em que o agente é executado com frequência maior que uma vez ao dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-219"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - the frequency unit when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="3e53c-220"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - número de unidades de frequência entre execuções quando o agente é executado com frequência maior que uma vez ao dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-220"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="3e53c-221"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - hora anterior em determinado dia em que tem início a execução do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-221"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - earliest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="3e53c-222"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - hora posterior em um determinado dia em que tem início a execução do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-222"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - latest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="3e53c-223"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - primeiro dia em que o agendamento do agente entra em vigor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-223"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - first day that the agent schedule is in effect.</span></span>  
  
    -   <span data-ttu-id="3e53c-224"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - último dia de vigência do agendamento.</span><span class="sxs-lookup"><span data-stu-id="3e53c-224"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - last day that the agent schedule is in effect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e53c-225">Se uma dessas propriedades não for especificada, um valor padrão será determinado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-225">If you do not specify one of these properties, a default value is set.</span></span>  
  
3.  <span data-ttu-id="3e53c-226">Chame o método <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A> para criar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-226">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A> method to create the subscription.</span></span>  
  
#### <a name="to-define-a-replication-agent-schedule-when-you-create-a-pull-subscription-to-a-transactional-publication"></a><span data-ttu-id="3e53c-227">Para definir um agendamento de agente de replicação quando é criada uma assinatura pull para uma publicação transacional</span><span class="sxs-lookup"><span data-stu-id="3e53c-227">To define a replication agent schedule when you create a pull subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="3e53c-228">Crie uma instância da classe <xref:Microsoft.SqlServer.Replication.TransPullSubscription> para a assinatura que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="3e53c-228">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class for the subscription you are creating.</span></span> <span data-ttu-id="3e53c-229">Para obter mais informações, consulte [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-229">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
2.  <span data-ttu-id="3e53c-230">Antes de chamar <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A>, defina um ou mais dos campos seguintes da propriedade <xref:Microsoft.SqlServer.Replication.PullSubscription.AgentSchedule%2A> :</span><span class="sxs-lookup"><span data-stu-id="3e53c-230">Before you call <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A>, set one or more of the following fields of the <xref:Microsoft.SqlServer.Replication.PullSubscription.AgentSchedule%2A> property:</span></span>  
  
    -   <span data-ttu-id="3e53c-231"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - tipo de frequência (por exemplo, diária ou semanal) usada durante o agendamento do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-231"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - the type of frequency (such as daily or weekly) that you use when you schedule the agent.</span></span>  
  
    -   <span data-ttu-id="3e53c-232"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - dia da semana em que o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-232"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - the day of the week that an agent runs.</span></span>  
  
    -   <span data-ttu-id="3e53c-233"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - semana de um determinado mês em que o agente é agendado para ser executado mensalmente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-233"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - the week of a given month that the agent is scheduled to run monthly.</span></span>  
  
    -   <span data-ttu-id="3e53c-234"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - número de unidades do tipo-frequência que ocorrem entre sincronizações.</span><span class="sxs-lookup"><span data-stu-id="3e53c-234"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - the number of frequency-type units that occur between synchronizations.</span></span>  
  
    -   <span data-ttu-id="3e53c-235"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - unidade de frequência em que o agente é executado com frequência maior que uma vez ao dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-235"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - the frequency unit when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="3e53c-236"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - número de unidades de frequência entre execuções quando o agente é executado com frequência maior que uma vez ao dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-236"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="3e53c-237"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - hora anterior em determinado dia em que tem início a execução do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-237"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - earliest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="3e53c-238"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - hora posterior em um determinado dia em que tem início a execução do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-238"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - latest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="3e53c-239"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - primeiro dia em que o agendamento do agente entra em vigor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-239"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - first day that the agent schedule is in effect.</span></span>  
  
    -   <span data-ttu-id="3e53c-240"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - último dia de vigência do agendamento.</span><span class="sxs-lookup"><span data-stu-id="3e53c-240"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - last day that the agent schedule is in effect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e53c-241">Se uma dessas propriedades não for especificada, um valor padrão será determinado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-241">If you do not specify one of these properties, a default value is set.</span></span>  
  
3.  <span data-ttu-id="3e53c-242">Chame o método <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A> para criar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-242">Call the <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A> method to create the subscription.</span></span>  
  
#### <a name="to-define-a-replication-agent-schedule-when-you-create-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="3e53c-243">Para definir um agendamento de agente de replicação quando uma assinatura pull é criada para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="3e53c-243">To define a replication agent schedule when you create a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="3e53c-244">Crie uma instância da classe <xref:Microsoft.SqlServer.Replication.MergePullSubscription> para a assinatura que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="3e53c-244">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class for the subscription you are creating.</span></span> <span data-ttu-id="3e53c-245">Para obter mais informações, consulte [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-245">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
2.  <span data-ttu-id="3e53c-246">Antes de chamar <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A>, defina um ou mais dos campos seguintes da propriedade <xref:Microsoft.SqlServer.Replication.PullSubscription.AgentSchedule%2A> :</span><span class="sxs-lookup"><span data-stu-id="3e53c-246">Before you call <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A>, set one or more of the following fields of the <xref:Microsoft.SqlServer.Replication.PullSubscription.AgentSchedule%2A> property:</span></span>  
  
    -   <span data-ttu-id="3e53c-247"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - tipo de frequência (por exemplo, diária ou semanal) usada durante o agendamento do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-247"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - the type of frequency (such as daily or weekly) that you use when you schedule the agent.</span></span>  
  
    -   <span data-ttu-id="3e53c-248"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - dia da semana em que o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-248"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - the day of the week that an agent runs.</span></span>  
  
    -   <span data-ttu-id="3e53c-249"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - semana de um determinado mês em que o agente é agendado para ser executado mensalmente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-249"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - the week of a given month that the agent is scheduled to run monthly.</span></span>  
  
    -   <span data-ttu-id="3e53c-250"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - número de unidades do tipo-frequência que ocorrem entre sincronizações.</span><span class="sxs-lookup"><span data-stu-id="3e53c-250"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - the number of frequency-type units that occur between synchronizations.</span></span>  
  
    -   <span data-ttu-id="3e53c-251"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - unidade de frequência em que o agente é executado com frequência maior que uma vez ao dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-251"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - the frequency unit when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="3e53c-252"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - número de unidades de frequência entre execuções quando o agente é executado com frequência maior que uma vez ao dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-252"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="3e53c-253"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - hora anterior em determinado dia em que tem início a execução do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-253"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - earliest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="3e53c-254"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - hora posterior em um determinado dia em que tem início a execução do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-254"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - latest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="3e53c-255"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - primeiro dia em que o agendamento do agente entra em vigor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-255"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - first day that the agent schedule is in effect.</span></span>  
  
    -   <span data-ttu-id="3e53c-256"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - último dia de vigência do agendamento.</span><span class="sxs-lookup"><span data-stu-id="3e53c-256"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - last day that the agent schedule is in effect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e53c-257">Se uma dessas propriedades não for especificada, um valor padrão será determinado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-257">If you do not specify one of these properties, a default value is set.</span></span>  
  
3.  <span data-ttu-id="3e53c-258">Chame o método <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A> para criar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-258">Call the <xref:Microsoft.SqlServer.Replication.PullSubscription.Create%2A> method to create the subscription.</span></span>  
  
#### <a name="to-define-a-replication-agent-schedule-when-you-create-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="3e53c-259">Para definir um agendamento de agente de replicação quando uma assinatura push é criada para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="3e53c-259">To define a replication agent schedule when you create a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="3e53c-260">Crie uma instância da classe <xref:Microsoft.SqlServer.Replication.MergeSubscription> para a assinatura que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="3e53c-260">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class for the subscription you are creating.</span></span> <span data-ttu-id="3e53c-261">Para obter mais informações, consulte [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3e53c-261">For more information, see [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="3e53c-262">Antes de chamar <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A>, defina um ou mais dos campos seguintes da propriedade <xref:Microsoft.SqlServer.Replication.Subscription.AgentSchedule%2A> :</span><span class="sxs-lookup"><span data-stu-id="3e53c-262">Before you call <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A>, set one or more of the following fields of the <xref:Microsoft.SqlServer.Replication.Subscription.AgentSchedule%2A> property:</span></span>  
  
    -   <span data-ttu-id="3e53c-263"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - tipo de frequência (por exemplo, diária ou semanal) usada durante o agendamento do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-263"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyType%2A> - the type of frequency (such as daily or weekly) that you use when you schedule the agent.</span></span>  
  
    -   <span data-ttu-id="3e53c-264"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - dia da semana em que o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-264"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyInterval%2A> - the day of the week that an agent runs.</span></span>  
  
    -   <span data-ttu-id="3e53c-265"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - semana de um determinado mês em que o agente é agendado para ser executado mensalmente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-265"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRelativeInterval%2A> - the week of a given month that the agent is scheduled to run monthly.</span></span>  
  
    -   <span data-ttu-id="3e53c-266"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - número de unidades do tipo-frequência que ocorrem entre sincronizações.</span><span class="sxs-lookup"><span data-stu-id="3e53c-266"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencyRecurrenceFactor%2A> - the number of frequency-type units that occur between synchronizations.</span></span>  
  
    -   <span data-ttu-id="3e53c-267"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - unidade de frequência em que o agente é executado com frequência maior que uma vez ao dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-267"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDay%2A> - the frequency unit when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="3e53c-268"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - número de unidades de frequência entre execuções quando o agente é executado com frequência maior que uma vez ao dia.</span><span class="sxs-lookup"><span data-stu-id="3e53c-268"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.FrequencySubDayInterval%2A> - the number of frequency units between runs when the agent runs more often than once a day.</span></span>  
  
    -   <span data-ttu-id="3e53c-269"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - hora anterior em determinado dia em que tem início a execução do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-269"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartTime%2A> - earliest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="3e53c-270"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - hora posterior em um determinado dia em que tem início a execução do agente.</span><span class="sxs-lookup"><span data-stu-id="3e53c-270"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndTime%2A> - latest time on a given day that an agent run starts.</span></span>  
  
    -   <span data-ttu-id="3e53c-271"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - primeiro dia em que o agendamento do agente entra em vigor.</span><span class="sxs-lookup"><span data-stu-id="3e53c-271"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveStartDate%2A> - first day that the agent schedule is in effect.</span></span>  
  
    -   <span data-ttu-id="3e53c-272"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - último dia de vigência do agendamento.</span><span class="sxs-lookup"><span data-stu-id="3e53c-272"><xref:Microsoft.SqlServer.Replication.ReplicationAgentSchedule.ActiveEndDate%2A> - last day that the agent schedule is in effect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e53c-273">Se uma dessas propriedades não for especificada, um valor padrão será determinado.</span><span class="sxs-lookup"><span data-stu-id="3e53c-273">If you do not specify one of these properties, a default value is set.</span></span>  
  
3.  <span data-ttu-id="3e53c-274">Chame o método <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A> para criar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3e53c-274">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Create%2A> method to create the subscription.</span></span>  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="3e53c-275">Exemplo (RMO)</span><span class="sxs-lookup"><span data-stu-id="3e53c-275">Example (RMO)</span></span>  
 <span data-ttu-id="3e53c-276">Esse exemplo cria uma assinatura push para uma publicação de mesclagem e especifica o agendamento em que a assinatura é sincronizada.</span><span class="sxs-lookup"><span data-stu-id="3e53c-276">This example creates a push subscription to a merge publication and specifies the schedule on which the subscription is synchronized.</span></span>  
  
 [!code-csharp[HowTo#rmo_CreateMergePushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_createmergepushsub)]  
  
 [!code-vb[HowTo#rmo_vb_CreateMergePushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_createmergepushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="3e53c-277">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3e53c-277">See Also</span></span>  
 <span data-ttu-id="3e53c-278">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="3e53c-278">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 <span data-ttu-id="3e53c-279">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="3e53c-279">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="3e53c-280">[Sincronizar uma assinatura push](synchronize-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="3e53c-280">[Synchronize a Push Subscription](synchronize-a-push-subscription.md) </span></span>  
 <span data-ttu-id="3e53c-281">[Sincronizar uma assinatura pull](synchronize-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="3e53c-281">[Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="3e53c-282">Sincronizar dados</span><span class="sxs-lookup"><span data-stu-id="3e53c-282">Synchronize Data</span></span>](synchronize-data.md)  
  
  
