---
title: Iniciar e interromper um agente de replicação (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], stopping
- agents [SQL Server replication], starting
ms.assetid: 97977c4a-8c7c-4a22-9480-69aa812bd1e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40e329e0f04e8a54a2d5a40c30aff418da2cd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569952"
---
# <a name="start-and-stop-a-replication-agent-sql-server-management-studio"></a><span data-ttu-id="f2a44-102">Iniciar e interromper um Agente de Replicação (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f2a44-102">Start and Stop a Replication Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f2a44-103">Inicie e pare os agentes nas pastas **Trabalhos** e **Replicação** do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e do Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="f2a44-103">Start and stop agents from the **Jobs** folder and the **Replication** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from Replication Monitor.</span></span> <span data-ttu-id="f2a44-104">Inicie e pare os seguintes agentes e trabalhos:</span><span class="sxs-lookup"><span data-stu-id="f2a44-104">Start and stop the following agents and jobs:</span></span>  
  
-   <span data-ttu-id="f2a44-105">O Agente de Instantâneo, que é usado por todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="f2a44-105">The Snapshot Agent, which is used by all publications.</span></span>  
  
-   <span data-ttu-id="f2a44-106">O Agente de Leitor de Log, que é usado por todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="f2a44-106">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="f2a44-107">O Agente de Leitor de Fila, que é usado pelas publicações transacionais habilitadas para atualização de assinaturas em fila.</span><span class="sxs-lookup"><span data-stu-id="f2a44-107">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="f2a44-108">O Agente de Distribuição que sincroniza as assinaturas para publicações transacionais e de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="f2a44-108">The Distribution Agent, which synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="f2a44-109">O Agente de Mesclagem que sincroniza as assinaturas para publicações de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="f2a44-109">The Merge Agent, which synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="f2a44-110">Trabalhos de manutenção de replicação.</span><span class="sxs-lookup"><span data-stu-id="f2a44-110">Replication maintenance jobs.</span></span>  
  
 <span data-ttu-id="f2a44-111">Para obter mais informações sobre como iniciar o Agente de Mesclagem e o Agente de Distribuição, consulte [Sincronizar uma assinatura push](../synchronize-a-push-subscription.md) e [Sincronizar uma assinatura pull](../synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="f2a44-111">For more information about starting the Merge Agent and the Distribution Agent, see [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) and [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span></span> <span data-ttu-id="f2a44-112">Para mais informações sobre trabalhos de manutenção, consulte [Executar trabalhos de manutenção de replicação &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="f2a44-112">For more information about maintenance jobs, see [Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span></span>  
  
 <span data-ttu-id="f2a44-113">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](../monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="f2a44-113">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-or-log-reader-agent-from-management-studio"></a><span data-ttu-id="f2a44-114">Para iniciar e parar um Agente de Instantâneo ou Agente de Leitor de Log a partir do Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2a44-114">To start and stop a Snapshot Agent or Log Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="f2a44-115">Conecte-se ao Publicador no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e, em seguida, expanda o nó do servidor e a pasta **Replicação** .</span><span class="sxs-lookup"><span data-stu-id="f2a44-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node and the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="f2a44-116">Expanda a pasta **Publicações Locais** e clique com o botão direito do mouse em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="f2a44-116">Expand the **Local Publications** folder, and then right-click a publication.</span></span>  
  
3.  <span data-ttu-id="f2a44-117">Clique em **Exibir Status do Agente de Instantâneo** ou **Exibir Status do Agente de Leitor de Log**.</span><span class="sxs-lookup"><span data-stu-id="f2a44-117">Click **View Snapshot Agent Status** or **View Log Reader Agent Status**.</span></span>  
  
4.  <span data-ttu-id="f2a44-118">Clique em **Iniciar** ou em **Parar**.</span><span class="sxs-lookup"><span data-stu-id="f2a44-118">Click **Start** or **Stop**.</span></span>  
  
### <a name="to-start-and-stop-a-queue-reader-agent-from-management-studio"></a><span data-ttu-id="f2a44-119">Para iniciar e parar um Agente de Leitor de Fila a partir do Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2a44-119">To start and stop a Queue Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="f2a44-120">Conecte-se ao Distribuidor no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e, em seguida, expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="f2a44-120">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="f2a44-121">Expanda a pasta **SQL Server Agent** e, em seguida, a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="f2a44-121">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="f2a44-122">Clique com o botão direito no trabalho para o agente e, então, clique em **Iniciar Trabalho** ou **Parar Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f2a44-122">Right-click the job for the agent, and then click **Start Job** or **Stop Job**.</span></span> <span data-ttu-id="f2a44-123">O nome do trabalho para o Queue Reader Agent está no formato **[\<Distributor>].\<integer>** .</span><span class="sxs-lookup"><span data-stu-id="f2a44-123">The name of the job for the Queue Reader Agent is in the form **[\<Distributor>].\<integer>**.</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-log-reader-agent-or-queue-reader-agent-from-replication-monitor"></a><span data-ttu-id="f2a44-124">Para iniciar e parar um Agente de Instantâneo, Agente de Leitor de Log ou Agente de Leitor de Fila a partir do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="f2a44-124">To start and stop a Snapshot Agent, Log Reader Agent, or Queue Reader Agent from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="f2a44-125">Expanda um Grupo do publicador no painel esquerdo, expanda um Publicador e clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="f2a44-125">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="f2a44-126">Clique na guia **Agentes** .</span><span class="sxs-lookup"><span data-stu-id="f2a44-126">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="f2a44-127">Clique com o botão direito em um agente e, então, clique em **Iniciar Agente** ou **Parar Agente**.</span><span class="sxs-lookup"><span data-stu-id="f2a44-127">Right-click an agent, and then click **Start Agent** or **Stop Agent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a44-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f2a44-128">See Also</span></span>  
 <span data-ttu-id="f2a44-129">[Monitorando a Replicação](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="f2a44-129">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 <span data-ttu-id="f2a44-130">[Conceitos dos executáveis do Agente de Replicação](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="f2a44-130">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="f2a44-131">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="f2a44-131">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
