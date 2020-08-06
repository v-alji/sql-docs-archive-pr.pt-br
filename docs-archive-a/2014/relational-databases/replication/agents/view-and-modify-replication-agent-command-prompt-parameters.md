---
title: Exibir e modificar parâmetros do prompt de comando do agente de replicação (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], command prompt parameters
ms.assetid: 45f2e781-c21d-4b44-8992-89f60fb3d022
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 752f674c21bb66c7b64e399e30e4917512431195
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569951"
---
# <a name="view-and-modify-replication-agent-command-prompt-parameters-sql-server-management-studio"></a><span data-ttu-id="f98da-102">Exibir e modificar parâmetros do prompt de comando de agentes de replicação (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f98da-102">View and Modify Replication Agent Command Prompt Parameters (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f98da-103">Agentes de replicação são executáveis que aceitam parâmetros de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f98da-103">Replication agents are executables that accept command line parameters.</span></span> <span data-ttu-id="f98da-104">Por padrão, os agentes são executados nas etapas [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de trabalho do Agente, assim sendo, esses parâmetros podem ser exibidos e modificados usando a caixa de diálogo **Propriedades do trabalho – \<Job>** .</span><span class="sxs-lookup"><span data-stu-id="f98da-104">By default, agents run under [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job steps, so these parameters can be viewed and modified using the **Job Properties - \<Job>** dialog box.</span></span> <span data-ttu-id="f98da-105">Essa caixa de diálogo está disponível na pasta **Trabalhos** no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e na guia **Agentes** no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="f98da-105">This dialog box is available from the **Jobs** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="f98da-106">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](../monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="f98da-106">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f98da-107">As alterações do parâmetro de agente entrarão em vigor na próxima vez o agente for iniciado.</span><span class="sxs-lookup"><span data-stu-id="f98da-107">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="f98da-108">Se o agente ficar executando continuamente, será necessário parar e reiniciar o agente.</span><span class="sxs-lookup"><span data-stu-id="f98da-108">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
 <span data-ttu-id="f98da-109">Embora seja possível modificar os parâmetros diretamente, em geral, eles são modificados através de um perfil de agente.</span><span class="sxs-lookup"><span data-stu-id="f98da-109">Although parameters can be modified directly, it is more common to modify them through an agent profile.</span></span> <span data-ttu-id="f98da-110">Para saber mais, confira [Replication Agent Profiles](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f98da-110">For more information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="f98da-111">Ao acessar os trabalhos de agentes na pasta **Trabalhos** use a tabela a seguir, para determinar o nome do trabalho do agente e os parâmetros disponíveis para cada agente.</span><span class="sxs-lookup"><span data-stu-id="f98da-111">If you access agent jobs from the **Jobs** folder, use the following table to determine the agent job name and the parameters available for each agent.</span></span>  
  
|<span data-ttu-id="f98da-112">Agente</span><span class="sxs-lookup"><span data-stu-id="f98da-112">Agent</span></span>|<span data-ttu-id="f98da-113">Nome do trabalho</span><span class="sxs-lookup"><span data-stu-id="f98da-113">Job name</span></span>|<span data-ttu-id="f98da-114">Para uma lista de parâmetros, confira...</span><span class="sxs-lookup"><span data-stu-id="f98da-114">For a list of parameters, see...</span></span>|  
|-----------|--------------|------------------------------------|  
|<span data-ttu-id="f98da-115">Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-115">Snapshot Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<integer>**|[<span data-ttu-id="f98da-116">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-116">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="f98da-117">Snapshot Agent para uma partição de publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="f98da-117">Snapshot Agent for a merge publication partition</span></span>|<span data-ttu-id="f98da-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span><span class="sxs-lookup"><span data-stu-id="f98da-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span></span>|[<span data-ttu-id="f98da-119">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-119">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="f98da-120">Agente de Leitor de Log</span><span class="sxs-lookup"><span data-stu-id="f98da-120">Log Reader Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<integer>**|[<span data-ttu-id="f98da-121">Agente do Leitor de Log de Replicação</span><span class="sxs-lookup"><span data-stu-id="f98da-121">Replication Log Reader Agent</span></span>](replication-log-reader-agent.md)|  
|<span data-ttu-id="f98da-122">Merge Agent para assinaturas pull</span><span class="sxs-lookup"><span data-stu-id="f98da-122">Merge Agent for pull subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<integer>**|[<span data-ttu-id="f98da-123">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-123">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="f98da-124">Merge Agent para assinaturas push</span><span class="sxs-lookup"><span data-stu-id="f98da-124">Merge Agent for push subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="f98da-125">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-125">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="f98da-126">Distribution Agent para assinaturas push</span><span class="sxs-lookup"><span data-stu-id="f98da-126">Distribution Agent for push subscriptions</span></span>|<span data-ttu-id="f98da-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f98da-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span></span>|[<span data-ttu-id="f98da-128">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-128">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="f98da-129">Distribution Agent para assinaturas pull</span><span class="sxs-lookup"><span data-stu-id="f98da-129">Distribution Agent for pull subscriptions</span></span>|<span data-ttu-id="f98da-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f98da-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span></span>|[<span data-ttu-id="f98da-131">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-131">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="f98da-132">Distribution Agent para assinaturas push para Assinantes não SQL Server</span><span class="sxs-lookup"><span data-stu-id="f98da-132">Distribution Agent for push subscriptions to non-SQL Server Subscribers</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="f98da-133">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-133">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="f98da-134">Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="f98da-134">Queue Reader Agent</span></span>|<span data-ttu-id="f98da-135">**[\<Distributor>].\<integer>**</span><span class="sxs-lookup"><span data-stu-id="f98da-135">**[\<Distributor>].\<integer>**</span></span>|[<span data-ttu-id="f98da-136">Agente de Leitor de Fila de Replicação</span><span class="sxs-lookup"><span data-stu-id="f98da-136">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)|  
  
 <span data-ttu-id="f98da-137"><sup>1</sup> Para assinaturas push para publicações Oracle, é \*\*\<Publisher>-\<Publisher**> em vez de **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="f98da-137"><sup>1</sup> For push subscriptions to Oracle publications, it is \*\*\<Publisher>-\<Publisher**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
 <span data-ttu-id="f98da-138"><sup>2</sup> Para assinaturas pull para publicações Oracle, é \*\*\<Publisher>-\<DistributionDatabase**> em vez de **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="f98da-138"><sup>2</sup> For pull subscriptions to Oracle publications, it is \*\*\<Publisher>-\<DistributionDatabase**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
### <a name="to-view-and-modify-replication-agent-command-line-parameters-from-management-studio"></a><span data-ttu-id="f98da-139">Para exibir e modificar os parâmetros da linha de comando dos agentes de replicação do Management Studio</span><span class="sxs-lookup"><span data-stu-id="f98da-139">To view and modify replication agent command line parameters from Management Studio</span></span>  
  
1.  <span data-ttu-id="f98da-140">Conecte-se ao computador adequado em [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], e expanda o servidor.</span><span class="sxs-lookup"><span data-stu-id="f98da-140">Connect to the appropriate computer in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="f98da-141">Para assinatura pull no Agente de Distribuição e no Agente de Mesclagem, conecte-se com o Assinante.</span><span class="sxs-lookup"><span data-stu-id="f98da-141">For the Distribution Agent and Merge Agent for pull subscriptions, connect to the Subscriber.</span></span>  
  
    -   <span data-ttu-id="f98da-142">Para todos os demais agentes, conecte-se com o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="f98da-142">For all other agents, connect to the Distributor.</span></span>  
  
2.  <span data-ttu-id="f98da-143">Expanda a pasta **SQL Server Agent** e, em seguida, a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="f98da-143">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="f98da-144">Clique com o botão direito do mouse em um trabalho e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f98da-144">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f98da-145">Na página **Etapas** da caixa de diálogo **Propriedades do Trabalho – \<Job>** , selecione a etapa **Executar agente** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f98da-145">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="f98da-146">Na caixa de diálogo **Propriedades da Etapa do Trabalho – Executar agente** , edite o campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="f98da-146">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="f98da-147">Clique em **OK** , em ambas as caixas de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f98da-147">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-distribution-agent-and-merge-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="f98da-148">Para exibir e modificar os parâmetros da linha de comando do Agente de Distribuição e do Agente de Mesclagem do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="f98da-148">To view and modify Distribution Agent and Merge Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="f98da-149">Expanda um Grupo do publicador no painel esquerdo do Replication Monitor, expanda um Publicador e, em seguida, clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="f98da-149">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="f98da-150">Clique na guia **Todas as Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="f98da-150">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="f98da-151">Clique com o botão direito do mouse em uma assinatura e clique em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f98da-151">Right-click a subscription, and then click **View Details**.</span></span>  
  
4.  <span data-ttu-id="f98da-152">Na janela **assinatura \< SubscriptionName> \*\* , clique em **ação**e, em seguida, clique em \*\* \<AgentName> Propriedades do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f98da-152">In the **Subscription \< SubscriptionName>** window, click **Action**, and then click **\<AgentName> Job Properties**.</span></span>  
  
5.  <span data-ttu-id="f98da-153">Na página **Etapas** da caixa de diálogo **Propriedades do Trabalho – \<Job>** , selecione a etapa **Executar agente** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f98da-153">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="f98da-154">Na caixa de diálogo **Propriedades da Etapa do Trabalho – Executar agente** , edite o campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="f98da-154">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
7.  <span data-ttu-id="f98da-155">Clique em **OK** , em ambas as caixas de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f98da-155">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-snapshot-agent-log-reader-agent-and-queue-reader-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="f98da-156">Para exibir e modificar parâmetros de linha de comando do Replication Monitor do Agente de Instantâneo, do Agente de Leitor de Log e do Agente de Leitor de Fila.</span><span class="sxs-lookup"><span data-stu-id="f98da-156">To view and modify Snapshot Agent, Log Reader Agent, and Queue Reader Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="f98da-157">Expanda um Grupo do publicador no painel esquerdo do Replication Monitor, expanda um Publicador e, em seguida, clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="f98da-157">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="f98da-158">Clique na guia **Agentes** .</span><span class="sxs-lookup"><span data-stu-id="f98da-158">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="f98da-159">Clique com o botão direito do mouse em um agente na grade e em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f98da-159">Right-click an agent in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f98da-160">Na página **Etapas** da caixa de diálogo **Propriedades do Trabalho – \<Job>** , selecione a etapa **Executar agente** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f98da-160">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="f98da-161">Na caixa de diálogo **Propriedades da Etapa do Trabalho – Executar agente** , edite o campo **Comando** .</span><span class="sxs-lookup"><span data-stu-id="f98da-161">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="f98da-162">Clique em **OK** , em ambas as caixas de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f98da-162">Click **OK** on both dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98da-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f98da-163">See Also</span></span>  
 <span data-ttu-id="f98da-164">[Administração do agente de replicação](replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="f98da-164">[Replication Agent Administration](replication-agent-administration.md) </span></span>  
 <span data-ttu-id="f98da-165">[Conceitos dos executáveis do Agente de Replicação](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="f98da-165">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="f98da-166">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="f98da-166">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
