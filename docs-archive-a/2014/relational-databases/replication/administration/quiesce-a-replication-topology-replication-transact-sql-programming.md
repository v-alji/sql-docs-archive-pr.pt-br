---
title: Fechar uma topologia de replicação para novas sessões (programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- administering replication, quiescing
- quiesce [SQL Server replication]
- transactional replication, backup and restore
ms.assetid: 7626d575-9994-47be-b772-5b6f1b7ef7ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12f0fb8ee3a6118e03799d17836573fb5c733df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683503"
---
# <a name="quiesce-a-replication-topology-replication-transact-sql-programming"></a><span data-ttu-id="0910b-102">Confirmar uma topologia de replicação (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="0910b-102">Quiesce a Replication Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="0910b-103">*Confirmar* um sistema inclui interromper as atividades em tabelas publicadas em todos os nós e assegurar que todos eles tenham recebido todas as alterações de todos os demais nós.</span><span class="sxs-lookup"><span data-stu-id="0910b-103">*Quiescing* a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="0910b-104">Esse tópico explica como confirmar a topologia de replicação, necessária para um número de tarefas administrativas, e como garantir que um nó tenha recebido todas as alterações dos demais nós.</span><span class="sxs-lookup"><span data-stu-id="0910b-104">This topic explains how to quiesce a replication topology, which is required for a number of administrative tasks, and how to ensure that a node has received all changes from other nodes.</span></span>  
  
### <a name="to-quiesce-a-transactional-replication-topology-with-read-only-subscriptions"></a><span data-ttu-id="0910b-105">Para confirmar uma topologia de replicação transacional com assinaturas somente leitura</span><span class="sxs-lookup"><span data-stu-id="0910b-105">To quiesce a transactional replication topology with read-only subscriptions</span></span>  
  
1.  <span data-ttu-id="0910b-106">Interrompa a atividade em todas as tabelas publicadas no Publicador.</span><span class="sxs-lookup"><span data-stu-id="0910b-106">Stop activity on all published tables at the Publisher.</span></span>  
  
2.  <span data-ttu-id="0910b-107">No Publicador do banco de dados de publicação, execute [sp_posttracertoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0910b-107">At the Publisher on the publication database, execute [sp_posttracertoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span></span>  
  
3.  <span data-ttu-id="0910b-108">No Publicador do banco de dados de publicação, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0910b-108">At the Publisher on the publication database, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span></span>  
  
4.  <span data-ttu-id="0910b-109">Certifique-se de que cada Assinante tenha recebido o token de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="0910b-109">Ensure that each Subscriber has received the tracer token.</span></span>  
  
### <a name="to-quiesce-a-transactional-replication-topology-with-updatable-subscriptions"></a><span data-ttu-id="0910b-110">Para confirmar uma topologia de replicação transacional com assinaturas atualizáveis</span><span class="sxs-lookup"><span data-stu-id="0910b-110">To quiesce a transactional replication topology with updatable subscriptions</span></span>  
  
1.  <span data-ttu-id="0910b-111">Interrompa a atividade em todas as tabelas publicadas no Publicador e em todos os Assinantes.</span><span class="sxs-lookup"><span data-stu-id="0910b-111">Stop activity on all published tables at the Publisher and all Subscribers.</span></span>  
  
2.  <span data-ttu-id="0910b-112">Se os Assinantes usarem assinaturas de atualização em fila:</span><span class="sxs-lookup"><span data-stu-id="0910b-112">If any Subscribers use queued updating subscriptions:</span></span>  
  
    1.  <span data-ttu-id="0910b-113">Se o Agente de Leitor de Fila não estiver executando em modo contínuo, execute o agente.</span><span class="sxs-lookup"><span data-stu-id="0910b-113">If the Queue Reader Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="0910b-114">Para obter mais informações sobre os agentes em execução, consulte [Conceitos dos executáveis do agente de replicação](../concepts/replication-agent-executables-concepts.md) ou [Iniciar e parar um agente de replicação &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0910b-114">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
    2.  <span data-ttu-id="0910b-115">Para verificar se a fila está vazia, execute [sp_replqueuemonitor](/sql/relational-databases/system-stored-procedures/sp-replqueuemonitor-transact-sql) em cada Assinante.</span><span class="sxs-lookup"><span data-stu-id="0910b-115">To verify that the queue is empty, execute [sp_replqueuemonitor](/sql/relational-databases/system-stored-procedures/sp-replqueuemonitor-transact-sql) at each Subscriber.</span></span>  
  
3.  <span data-ttu-id="0910b-116">No Publicador do banco de dados de publicação, execute [sp_posttracertoken](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0910b-116">At the Publisher on the publication database, execute [sp_posttracertoken](/sql/relational-databases/system-stored-procedures/sp-posttracertoken-transact-sql).</span></span>  
  
4.  <span data-ttu-id="0910b-117">No Publicador do banco de dados de publicação, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0910b-117">At the Publisher on the publication database, execute [sp_helptracertokenhistory](/sql/relational-databases/system-stored-procedures/sp-helptracertokenhistory-transact-sql).</span></span>  
  
5.  <span data-ttu-id="0910b-118">Certifique-se de que cada Assinante tenha recebido o token de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="0910b-118">Ensure that each Subscriber has received the tracer token.</span></span>  
  
### <a name="to-quiesce-a-peer-to-peer-transactional-replication-topology"></a><span data-ttu-id="0910b-119">Para confirmar uma topologia de replicação transacional ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="0910b-119">To quiesce a peer-to-peer transactional replication topology</span></span>  
  
1.  <span data-ttu-id="0910b-120">Interrompa a atividade em todas as tabelas publicadas em todos os nós.</span><span class="sxs-lookup"><span data-stu-id="0910b-120">Stop activity on all published tables at all nodes.</span></span>  
  
2.  <span data-ttu-id="0910b-121">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) em cada banco de dados de publicação na topologia.</span><span class="sxs-lookup"><span data-stu-id="0910b-121">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) on each publication database in the topology.</span></span>  
  
3.  <span data-ttu-id="0910b-122">Se o Agente de Leitor de Log ou o Agente de Distribuição não estiver executando em modo contínuo, execute o agente.</span><span class="sxs-lookup"><span data-stu-id="0910b-122">If the Log Reader Agent or Distribution Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="0910b-123">O Agente de Leitor de Log deve ser iniciado antes do Agente de Distribuição.</span><span class="sxs-lookup"><span data-stu-id="0910b-123">The Log Reader Agent must be started before the Distribution Agent.</span></span> <span data-ttu-id="0910b-124">Para obter mais informações sobre os agentes em execução, consulte [Conceitos dos executáveis do agente de replicação](../concepts/replication-agent-executables-concepts.md) ou [Iniciar e parar um agente de replicação &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0910b-124">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
4.  <span data-ttu-id="0910b-125">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) em cada banco de dados de publicação na topologia.</span><span class="sxs-lookup"><span data-stu-id="0910b-125">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) on each publication database in the topology.</span></span> <span data-ttu-id="0910b-126">Certifique-se de que o conjunto de resultados contenha as respostas de cada um dos demais nós.</span><span class="sxs-lookup"><span data-stu-id="0910b-126">Ensure that the result set contains responses from each of the other nodes.</span></span>  
  
### <a name="to-ensure-a-peer-to-peer-node-has-received-all-prior-changes"></a><span data-ttu-id="0910b-127">Para ter certeza de que um nó ponto a ponto recebeu todas as alterações anteriores</span><span class="sxs-lookup"><span data-stu-id="0910b-127">To ensure a peer-to-peer node has received all prior changes</span></span>  
  
1.  <span data-ttu-id="0910b-128">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) no banco de dados de publicação, no nó que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="0910b-128">Execute [sp_requestpeerresponse](/sql/relational-databases/system-stored-procedures/sp-requestpeerresponse-transact-sql) on the publication database at the node you are checking.</span></span>  
  
2.  <span data-ttu-id="0910b-129">Se o Agente de Leitor de Log ou o Agente de Distribuição não estiver executando em modo contínuo, execute o agente.</span><span class="sxs-lookup"><span data-stu-id="0910b-129">If the Log Reader Agent or Distribution Agent is not running in continuous mode, run the agent.</span></span> <span data-ttu-id="0910b-130">O Agente de Leitor de Log deve ser iniciado antes do Agente de Distribuição.</span><span class="sxs-lookup"><span data-stu-id="0910b-130">The Log Reader Agent must be started before the Distribution Agent.</span></span> <span data-ttu-id="0910b-131">Para obter mais informações sobre os agentes em execução, consulte [Conceitos dos executáveis do agente de replicação](../concepts/replication-agent-executables-concepts.md) ou [Iniciar e parar um agente de replicação &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0910b-131">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="0910b-132">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) no banco de dados de publicação, no nó que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="0910b-132">Execute [sp_helppeerresponses](/sql/relational-databases/system-stored-procedures/sp-helppeerresponses-transact-sql) on the publication database at the node you are checking.</span></span> <span data-ttu-id="0910b-133">Certifique-se de que o conjunto de resultados contenha as respostas de cada um dos demais nós.</span><span class="sxs-lookup"><span data-stu-id="0910b-133">Ensure that the result set contains responses from each of the other nodes.</span></span>  
  
### <a name="to-quiesce-a-merge-replication-topology"></a><span data-ttu-id="0910b-134">Para confirmar uma topologia de replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="0910b-134">To quiesce a merge replication topology</span></span>  
  
1.  <span data-ttu-id="0910b-135">Interrompa a atividade em todas as tabelas publicadas no Publicador e em todos os Assinantes.</span><span class="sxs-lookup"><span data-stu-id="0910b-135">Stop activity on all published tables at the Publisher and at all Subscribers.</span></span>  
  
2.  <span data-ttu-id="0910b-136">Execute o Agente de Mesclagem para cada assinatura duas vezes: sincronize todas as assinaturas uma vez e, em seguida, sincronize cada assinatura uma segunda vez:</span><span class="sxs-lookup"><span data-stu-id="0910b-136">Run the Merge Agent for each subscription two times: synchronize all subscriptions once and then synchronize each subscription a second time.</span></span> <span data-ttu-id="0910b-137">Isso garantirá que todos as alterações sejam replicadas em todos os nós.</span><span class="sxs-lookup"><span data-stu-id="0910b-137">This ensures that all changes are replicated to all nodes.</span></span> <span data-ttu-id="0910b-138">Para obter mais informações sobre os agentes em execução, consulte [Conceitos dos executáveis do agente de replicação](../concepts/replication-agent-executables-concepts.md) ou [Iniciar e parar um agente de replicação &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0910b-138">For more information about running agents, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0910b-139">Em caso de conflitos durante a sincronização, é possível que as alterações exigidas pela resolução do conflito não sejam propagadas a todos os nós, após a execução do Agente de Mesclagem duas vezes.</span><span class="sxs-lookup"><span data-stu-id="0910b-139">If conflicts occur during synchronization, it is possible that changes required by conflict resolution will not be propagated to all nodes after running the Merge Agent two times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0910b-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0910b-140">See Also</span></span>  
 <span data-ttu-id="0910b-141">[Administrar uma topologia ponto a ponto &#40;programação Transact-SQL de replicação&#41;](administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="0910b-141">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="0910b-142">Medir a latência e validar conexões para replicação transacional</span><span class="sxs-lookup"><span data-stu-id="0910b-142">Measure Latency and Validate Connections for Transactional Replication</span></span>](../monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
