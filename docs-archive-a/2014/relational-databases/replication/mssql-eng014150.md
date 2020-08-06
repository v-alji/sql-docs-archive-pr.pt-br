---
title: MSSQL_ENG014150 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014150 error
ms.assetid: c3dd3109-abf3-4b38-a4e9-ef48d0235656
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c926d05be9613ff559f119484fa5e238d71d861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569366"
---
# <a name="mssql_eng014150"></a><span data-ttu-id="c7857-102">MSSQL_ENG014150</span><span class="sxs-lookup"><span data-stu-id="c7857-102">MSSQL_ENG014150</span></span>
    
## <a name="message-details"></a><span data-ttu-id="c7857-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="c7857-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7857-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c7857-104">Product Name</span></span>|<span data-ttu-id="c7857-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7857-105">SQL Server</span></span>|  
|<span data-ttu-id="c7857-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c7857-106">Event ID</span></span>|<span data-ttu-id="c7857-107">14150</span><span class="sxs-lookup"><span data-stu-id="c7857-107">14150</span></span>|  
|<span data-ttu-id="c7857-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c7857-108">Event Source</span></span>|<span data-ttu-id="c7857-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c7857-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c7857-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c7857-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="c7857-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c7857-111">Symbolic Name</span></span>||  
|<span data-ttu-id="c7857-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c7857-112">Message Text</span></span>|<span data-ttu-id="c7857-113">Replicação-%s: agente %s bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c7857-113">Replication-%s: agent %s succeeded.</span></span> <span data-ttu-id="c7857-114">%s</span><span class="sxs-lookup"><span data-stu-id="c7857-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c7857-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="c7857-115">Explanation</span></span>  
 <span data-ttu-id="c7857-116">Essa mensagem indica que um agente de replicação concluiu a execução com êxito.</span><span class="sxs-lookup"><span data-stu-id="c7857-116">This message indicates that a replication agent has successfully finished running.</span></span> <span data-ttu-id="c7857-117">A replicação usa os seguintes agentes:</span><span class="sxs-lookup"><span data-stu-id="c7857-117">Replication uses the following agents:</span></span>  
  
-   <span data-ttu-id="c7857-118">O Snapshot Agent.</span><span class="sxs-lookup"><span data-stu-id="c7857-118">The Snapshot Agent.</span></span> <span data-ttu-id="c7857-119">Esse agente é usado por todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="c7857-119">This agent is used by all publications.</span></span>  
  
-   <span data-ttu-id="c7857-120">O Log Reader Agent.</span><span class="sxs-lookup"><span data-stu-id="c7857-120">The Log Reader Agent.</span></span> <span data-ttu-id="c7857-121">Esse agente é usado por todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="c7857-121">This agent is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="c7857-122">O Queue Reader Agent.</span><span class="sxs-lookup"><span data-stu-id="c7857-122">The Queue Reader Agent.</span></span> <span data-ttu-id="c7857-123">Esse agente é usado pelas publicações transacionais habilitadas para atualização de assinaturas em fila.</span><span class="sxs-lookup"><span data-stu-id="c7857-123">This agent is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="c7857-124">O Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="c7857-124">The Distribution Agent.</span></span> <span data-ttu-id="c7857-125">Esse agente sincroniza as assinaturas para publicações transacionais e de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="c7857-125">This agent synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="c7857-126">O Merge Agent.</span><span class="sxs-lookup"><span data-stu-id="c7857-126">The Merge Agent.</span></span> <span data-ttu-id="c7857-127">Esse agente sincroniza as assinaturas para publicações de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="c7857-127">This agent synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="c7857-128">Trabalhos de manutenção de replicação.</span><span class="sxs-lookup"><span data-stu-id="c7857-128">Replication maintenance jobs.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c7857-129">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c7857-129">User Action</span></span>  
 <span data-ttu-id="c7857-130">O Log Reader Agent, o Queue Reader Agent e o Distribution Agent são, em geral, executados continuamente, diferente de outros agentes, que são, em geral, executados sob demanda ou de forma programada.</span><span class="sxs-lookup"><span data-stu-id="c7857-130">The Log Reader Agent, Queue Reader Agent, and Distribution Agent typically run continuously, whereas the other agents typically run on demand or on a schedule.</span></span> <span data-ttu-id="c7857-131">Se você não esperar que um agente tenha concluído a sua execução, verifique o estado do agente.</span><span class="sxs-lookup"><span data-stu-id="c7857-131">If you do not expect an agent to have completed a run, check the status of the agent.</span></span> <span data-ttu-id="c7857-132">Para obter mais informações, consulte [Monitor Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7857-132">For more information, see [Monitor Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7857-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7857-133">See Also</span></span>  
 <span data-ttu-id="c7857-134">[Administração do agente de replicação](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="c7857-134">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="c7857-135">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="c7857-135">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="c7857-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="c7857-136">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="c7857-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="c7857-137">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="c7857-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="c7857-138">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="c7857-139">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="c7857-139">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="c7857-140">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="c7857-140">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
