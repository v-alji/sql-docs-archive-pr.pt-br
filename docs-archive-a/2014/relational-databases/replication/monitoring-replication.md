---
title: Monitorando a replicação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
author: rothja
ms.author: jroth
ms.openlocfilehash: df2760e4ce04c95f38ceb9dfe9fa9f79c4c467f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681605"
---
# <a name="monitoring-replication"></a><span data-ttu-id="599ab-102">Monitorando (Replicação)</span><span class="sxs-lookup"><span data-stu-id="599ab-102">Monitoring (Replication)</span></span>
  <span data-ttu-id="599ab-103">Monitorar uma topologia de replicação é um aspecto importante na implantação da replicação.</span><span class="sxs-lookup"><span data-stu-id="599ab-103">Monitoring a replication topology is an important aspect of deploying replication.</span></span> <span data-ttu-id="599ab-104">Já que a atividade de replicação é distribuída, é essencial controlar sua atividade e o status em todos os computadores envolvidos na replicação.</span><span class="sxs-lookup"><span data-stu-id="599ab-104">Because replication activity is distributed, it is essential to track activity and status across all computers involved in replication.</span></span> <span data-ttu-id="599ab-105">As seguintes ferramentas podem ser usadas para monitorar a replicação:</span><span class="sxs-lookup"><span data-stu-id="599ab-105">The following tools can be used to monitor replication:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)]<span data-ttu-id="599ab-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)]Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="599ab-106">[!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] Replication Monitor</span></span>  
  
     <span data-ttu-id="599ab-107">O Replication Monitor é a ferramenta mais importante para monitorar a replicação, apresentando uma exibição do Publicador dedicada a toda atividade de replicação.</span><span class="sxs-lookup"><span data-stu-id="599ab-107">Replication Monitor is the most important tool for monitoring replication, presenting a Publisher-focused view of all replication activity.</span></span> <span data-ttu-id="599ab-108">Para obter mais informações, consulte [monitorar o desempenho com o Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="599ab-108">For more information, see [Monitor performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)] <span data-ttu-id="599ab-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="599ab-109">[!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]</span></span>  
  
     [!INCLUDE[ssManStudio](../../includes/ssManStudio-md.md)] <span data-ttu-id="599ab-110">fornece o acesso ao Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="599ab-110">provides access to Replication Monitor.</span></span> <span data-ttu-id="599ab-111">Também permite que você exiba o status atual e a última mensagem registrada pelos seguintes agentes e permite que você inicie e interrompa cada agente: Agente de Leitor de Log, Agente de Instantâneo, Agente de Mesclagem e Agente de Distribuição.</span><span class="sxs-lookup"><span data-stu-id="599ab-111">It also allows you to view the current status and last message logged by the following agents and allows you start and stop each agent: Log Reader Agent, Snapshot Agent, Merge Agent, and Distribution Agent.</span></span> <span data-ttu-id="599ab-112">Para obter mais informações, consulte [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span><span class="sxs-lookup"><span data-stu-id="599ab-112">For more information, see [Monitor Replication Agents](monitor/monitor-replication-agents.md).</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="599ab-113">e RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="599ab-113">and Replication Management Objects (RMO)</span></span>  
  
     <span data-ttu-id="599ab-114">Ambas as interfaces permitem monitorar todos os tipos de replicação do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="599ab-114">Both interfaces allow you to monitor all types of replication from the Distributor.</span></span> <span data-ttu-id="599ab-115">A replicação de mesclagem fornece também a capacidade de monitorar a replicação a partir do Assinante.</span><span class="sxs-lookup"><span data-stu-id="599ab-115">Merge replication also provides the ability to monitor replication from the Subscriber.</span></span>  
  
-   <span data-ttu-id="599ab-116">Alertas para eventos do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="599ab-116">Alerts for replication agent events</span></span>  
  
     <span data-ttu-id="599ab-117">A replicação fornece vários alertas predefinidos para os eventos do agente de replicação e você pode criar alertas adicionais, se necessário.</span><span class="sxs-lookup"><span data-stu-id="599ab-117">Replication provides a number of predefined alerts for replication agent events, and you can create additional alerts if necessary.</span></span> <span data-ttu-id="599ab-118">Os alertas podem ser usados para acionar uma resposta automatizada a um evento e/ou notificar um administrador.</span><span class="sxs-lookup"><span data-stu-id="599ab-118">Alerts can be used to trigger an automated response to an event and/or notify an administrator.</span></span> <span data-ttu-id="599ab-119">Para obter mais informações, consulte [Usar alertas para eventos do agente de replicação](agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="599ab-119">For more information, see [Use Alerts for Replication Agent Events](agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
-   <span data-ttu-id="599ab-120">Monitor do Sistema</span><span class="sxs-lookup"><span data-stu-id="599ab-120">System Monitor</span></span>  
  
     <span data-ttu-id="599ab-121">O Monitor do Sistema pode ser útil para monitorar o desempenho, ao fornecer vários contadores para a replicação.</span><span class="sxs-lookup"><span data-stu-id="599ab-121">System Monitor can be useful for monitoring performance, providing a number of counters for replication.</span></span> <span data-ttu-id="599ab-122">Para obter mais informações, consulte [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="599ab-122">For more information, see [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="599ab-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="599ab-123">See Also</span></span>  
 <span data-ttu-id="599ab-124">[Perguntas Frequentes sobre Administração de Replicação](administration/frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="599ab-124">[Replication Administration FAQ](administration/frequently-asked-questions-for-replication-administrators.md) </span></span>  
 [<span data-ttu-id="599ab-125">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="599ab-125">Best Practices for Replication Administration</span></span>](administration/best-practices-for-replication-administration.md)   

  
  
