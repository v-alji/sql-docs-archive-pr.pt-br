---
title: Monitorar os agentes de replicação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], agents
- Log Reader Agent, monitoring
- Replication Monitor, agents
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- agents [SQL Server replication], monitoring
- Distribution Agent, monitoring
ms.assetid: d06ed24f-82d7-4b9e-9e40-cc9780476a71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: baa22ef9e9f7c4621f76838e82c309d17f1e12a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571941"
---
# <a name="monitor-replication-agents"></a><span data-ttu-id="b123c-102">Monitorar agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="b123c-102">Monitor Replication Agents</span></span>
  <span data-ttu-id="b123c-103">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor fornece uma exibição sistemática da atividade de replicação, mas também simplifica a localização de informações em um agente específico.</span><span class="sxs-lookup"><span data-stu-id="b123c-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor provides a systemic view of replication activity, but also makes it straightforward to find information on a specific agent.</span></span> <span data-ttu-id="b123c-104">A lista a seguir inclui cada agente, as guias no Replication Monitor onde pode ser localizado e um link para um tópico que explica como acessar essas guias:</span><span class="sxs-lookup"><span data-stu-id="b123c-104">The following list includes each agent, the tabs in the Replication Monitor on which it can be found, and a link to a topic that explains how to access these tabs:</span></span>  
  
-   <span data-ttu-id="b123c-105">Os agentes a seguir estão associados às publicações no Replication Monitor:</span><span class="sxs-lookup"><span data-stu-id="b123c-105">The following agents are associated with publications in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="b123c-106">Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="b123c-106">Snapshot Agent</span></span>  
  
    -   <span data-ttu-id="b123c-107">Agente de Leitor de Log</span><span class="sxs-lookup"><span data-stu-id="b123c-107">Log Reader Agent</span></span>  
  
    -   <span data-ttu-id="b123c-108">Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="b123c-108">Queue Reader Agent</span></span>  
  
     <span data-ttu-id="b123c-109">Acesse as informações e as tarefas associadas a esses agentes por meio das guias a seguir: **Agentes** (disponível para cada Editor e publicação) e **Avisos** (disponível para cada publicação).</span><span class="sxs-lookup"><span data-stu-id="b123c-109">Access information and tasks associated with these agents through the following tabs: **Agents** (available for each Publisher and publication) and **Warnings** (available for each publication).</span></span> <span data-ttu-id="b123c-110">Para obter mais informações, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b123c-110">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="b123c-111">Os agentes a seguir estão associados às assinaturas no Replication Monitor:</span><span class="sxs-lookup"><span data-stu-id="b123c-111">The following agents are associated with subscriptions in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="b123c-112">Agente de Distribuição</span><span class="sxs-lookup"><span data-stu-id="b123c-112">Distribution Agent</span></span>  
  
    -   <span data-ttu-id="b123c-113">Merge Agent</span><span class="sxs-lookup"><span data-stu-id="b123c-113">Merge Agent</span></span>  
  
     <span data-ttu-id="b123c-114">Acesse as informações e as tarefas associadas a esses agentes por meio das guias a seguir: **Lista de Observação da Assinatura** (disponível para cada Editor) ou **Todas as Assinaturas** (disponível para cada publicação).</span><span class="sxs-lookup"><span data-stu-id="b123c-114">Access information and tasks associated with these agents through the following tabs: **Subscription Watch List** (available for each Publisher) or the **All Subscriptions** tab (available for each publication).</span></span> <span data-ttu-id="b123c-115">Para obter mais informações, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b123c-115">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="using-sql-server-management-studio-to-monitor-replication-agents"></a><span data-ttu-id="b123c-116">Usando o SQL Server Management Studio para monitorar agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="b123c-116">Using SQL Server Management Studio to Monitor Replication Agents</span></span>  
 <span data-ttu-id="b123c-117">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] fornece as seguintes caixas de diálogo para monitorar agentes de replicação:</span><span class="sxs-lookup"><span data-stu-id="b123c-117">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] provides the following dialog boxes for monitoring replication agents:</span></span>  
  
-   <span data-ttu-id="b123c-118">**Exibir Status do Snapshot Agent** (para todas as publicações)</span><span class="sxs-lookup"><span data-stu-id="b123c-118">**View Snapshot Agent Status** (for all publications)</span></span>  
  
-   <span data-ttu-id="b123c-119">**Exibir Status do Log Reader Agent** (para todas as publicações transacionais)</span><span class="sxs-lookup"><span data-stu-id="b123c-119">**View Log Reader Agent Status** (for all transactional publications)</span></span>  
  
-   <span data-ttu-id="b123c-120">**Exibir Status da Sincronização** (para todas as assinaturas; essa caixa de diálogo permite acesso ao Distribution Agent e ao Merge Agent)</span><span class="sxs-lookup"><span data-stu-id="b123c-120">**View Synchronization Status** (for all subscriptions; this dialog box allows access to the Distribution Agent and the Merge Agent)</span></span>  
  
 <span data-ttu-id="b123c-121">O Replication Monitor fornece informações adicionais sobre cada agente e fornece monitoramento para o Queue Reader Agent, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b123c-121">Replication Monitor provides additional information about each agent and provides monitoring for the Queue Reader Agent, if it is used.</span></span> <span data-ttu-id="b123c-122">Para obter mais informações, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b123c-122">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
#### <a name="to-monitor-the-snapshot-agent-and-log-reader-agent"></a><span data-ttu-id="b123c-123">Para monitorar o Snapshot Agent e o Log Reader Agent</span><span class="sxs-lookup"><span data-stu-id="b123c-123">To monitor the Snapshot Agent and Log Reader Agent</span></span>  
  
1.  <span data-ttu-id="b123c-124">Conecte-se ao Publicador no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="b123c-124">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b123c-125">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="b123c-125">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="b123c-126">Clique com o botão direito do mouse em uma publicação e, então, clique em **Exibir Status do Log Reader Agent** ou **Exibir Status do Snapshot Agent**.</span><span class="sxs-lookup"><span data-stu-id="b123c-126">Right-click a publication, and then click **View Log Reader Agent Status** or **View Snapshot Agent Status**.</span></span>  
  
4.  <span data-ttu-id="b123c-127">Na caixa de diálogo do **Exibir Status do Log Reader Agent** ou do **Exibir Status do Snapshot Agent** :</span><span class="sxs-lookup"><span data-stu-id="b123c-127">In the **View Log Reader Agent Status** or **View Snapshot Agent Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="b123c-128">Exiba o status do agente.</span><span class="sxs-lookup"><span data-stu-id="b123c-128">View agent status.</span></span>  
  
    -   <span data-ttu-id="b123c-129">Inicie ou pare o agente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b123c-129">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="b123c-130">Clique em **Monitor** para iniciar o **Replication Monitor**.</span><span class="sxs-lookup"><span data-stu-id="b123c-130">Click **Monitor** to launch **Replication Monitor**.</span></span>  
  
5.  <span data-ttu-id="b123c-131">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="b123c-131">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-publisher"></a><span data-ttu-id="b123c-132">Para monitorar o Distribution Agent e o Merge Agent (no Publicador)</span><span class="sxs-lookup"><span data-stu-id="b123c-132">To monitor the Distribution Agent and Merge Agent (from the Publisher)</span></span>  
  
1.  <span data-ttu-id="b123c-133">Conecte-se ao Publicador no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="b123c-133">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b123c-134">Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .</span><span class="sxs-lookup"><span data-stu-id="b123c-134">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="b123c-135">Expanda a publicação para a assinatura que você quer monitorar.</span><span class="sxs-lookup"><span data-stu-id="b123c-135">Expand the publication for the subscription you want to monitor.</span></span>  
  
4.  <span data-ttu-id="b123c-136">Clique com o botão direito do mouse na assinatura e clique em **Exibir Status da Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="b123c-136">Right-click the subscription, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="b123c-137">Na caixa de diálogo **Exibir Status da Sincronização** :</span><span class="sxs-lookup"><span data-stu-id="b123c-137">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="b123c-138">Exiba o status do agente.</span><span class="sxs-lookup"><span data-stu-id="b123c-138">View agent status.</span></span>  
  
    -   <span data-ttu-id="b123c-139">Inicie ou pare o agente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b123c-139">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="b123c-140">Para assinaturas push, clique em **Monitor** para iniciar o **Replication Monitor**.</span><span class="sxs-lookup"><span data-stu-id="b123c-140">For push subscriptions, click **Monitor** to launch **Replication Monitor**.</span></span>  
  
    -   <span data-ttu-id="b123c-141">Para assinaturas pull, clique em **Exibir Histórico de Trabalhos** para iniciar o **Visualizador do Arquivo de Log**que exibe a saída do log do agente.</span><span class="sxs-lookup"><span data-stu-id="b123c-141">For pull subscriptions, click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
6.  <span data-ttu-id="b123c-142">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="b123c-142">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-subscriber"></a><span data-ttu-id="b123c-143">Para monitorar o Distribution Agent e o Merge Agent (no Assinante)</span><span class="sxs-lookup"><span data-stu-id="b123c-143">To monitor the Distribution Agent and Merge Agent (from the Subscriber)</span></span>  
  
1.  <span data-ttu-id="b123c-144">Conecte-se ao Assinante no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e expanda o nó do servidor.</span><span class="sxs-lookup"><span data-stu-id="b123c-144">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b123c-145">Expanda a pasta **Replicação** e, então, expanda a pasta **Assinaturas Locais** .</span><span class="sxs-lookup"><span data-stu-id="b123c-145">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="b123c-146">Clique com o botão direito do mouse na assinatura que deseja monitorar e clique em **Exibir Status da Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="b123c-146">Right-click the subscription you want to monitor, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="b123c-147">Na caixa de diálogo **Exibir Status da Sincronização** :</span><span class="sxs-lookup"><span data-stu-id="b123c-147">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="b123c-148">Exiba o status do agente.</span><span class="sxs-lookup"><span data-stu-id="b123c-148">View agent status.</span></span>  
  
    -   <span data-ttu-id="b123c-149">Inicie ou pare o agente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b123c-149">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="b123c-150">Clique em **Exibir Histórico do Agente** para iniciar o **Visualizador do Arquivo de Log**que exibe a saída do log do agente.</span><span class="sxs-lookup"><span data-stu-id="b123c-150">Click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
5.  <span data-ttu-id="b123c-151">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="b123c-151">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b123c-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b123c-152">See Also</span></span>  
 <span data-ttu-id="b123c-153">[Monitorando a Replicação](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="b123c-153">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 [<span data-ttu-id="b123c-154">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="b123c-154">Replication Agents Overview</span></span>](../agents/replication-agents-overview.md)  
  
  
