---
title: Configuração de modos de quorum WSFC e votação (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
- failover clustering [SQL Server], AlwaysOn Availability Groups
ms.assetid: ca0d59ef-25f0-4047-9130-e2282d058283
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b1d5ad992c59f252f485f2d65451a72f150bef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573554"
---
# <a name="wsfc-quorum-modes-and-voting-configuration-sql-server"></a><span data-ttu-id="9e54d-102">Configuração de modos de quorum WSFC e votação (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9e54d-102">WSFC Quorum Modes and Voting Configuration (SQL Server)</span></span>
  <span data-ttu-id="9e54d-103">Tanto [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] quanto as instâncias de cluster de failover (FCI) AlwaysOn utilizam o Windows Server Failover Clustering (WSFC) como tecnologia de plataforma.</span><span class="sxs-lookup"><span data-stu-id="9e54d-103">Both [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and AlwaysOn Failover Cluster Instances (FCI) take advantage of Windows Server Failover Clustering (WSFC) as a platform technology.</span></span>  <span data-ttu-id="9e54d-104">O WSFC usa uma abordagem baseada em quorum para monitorar integridade de cluster geral e maximizar a tolerância a falhas no nível do nó.</span><span class="sxs-lookup"><span data-stu-id="9e54d-104">WSFC uses a quorum-based approach to monitoring overall cluster health and maximize node-level fault tolerance.</span></span> <span data-ttu-id="9e54d-105">Um entendimento fundamental dos modos de quorum do WSFC e a configuração de votação de nó são muito importantes para o design, a operação e a resolução de problemas da sua solução de alta disponibilidade e recuperação de desastre AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="9e54d-105">A fundamental understanding of WSFC quorum modes and node voting configuration is very important to designing, operating, and troubleshooting your AlwaysOn high availability and disaster recovery solution.</span></span>  
  
 <span data-ttu-id="9e54d-106">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="9e54d-106">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="9e54d-107">Detecção de integridade de cluster por quorum</span><span class="sxs-lookup"><span data-stu-id="9e54d-107">Cluster Health Detection by Quorum</span></span>](#ClusterHealthDetectionbyQuorum)  
  
-   [<span data-ttu-id="9e54d-108">Modos de quorum</span><span class="sxs-lookup"><span data-stu-id="9e54d-108">Quorum Modes</span></span>](#QuorumModes)  
  
-   [<span data-ttu-id="9e54d-109">Nós de votação e não votação</span><span class="sxs-lookup"><span data-stu-id="9e54d-109">Voting and Non-Voting Nodes</span></span>](#VotingandNonVotingNodes)  
  
-   [<span data-ttu-id="9e54d-110">Ajustes indicados para votação de quorum</span><span class="sxs-lookup"><span data-stu-id="9e54d-110">Recommended Adjustments to Quorum Voting</span></span>](#RecommendedAdjustmentstoQuorumVoting)  
  
-   [<span data-ttu-id="9e54d-111">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9e54d-111">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="9e54d-112">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="9e54d-112">Related Content</span></span>](#RelatedContent)  
  
##  <a name="cluster-health-detection-by-quorum"></a><a name="ClusterHealthDetectionbyQuorum"></a><span data-ttu-id="9e54d-113">Detecção de integridade de cluster por quorum</span><span class="sxs-lookup"><span data-stu-id="9e54d-113">Cluster Health Detection by Quorum</span></span>  
 <span data-ttu-id="9e54d-114">Cada nó em um cluster do WSFC participa da comunicação de pulsação periódica para compartilhar o status de integridade do nó com os outros nós.</span><span class="sxs-lookup"><span data-stu-id="9e54d-114">Each node in a WSFC cluster participates in periodic heartbeat communication to share the node's health status with the other nodes.</span></span> <span data-ttu-id="9e54d-115">Nós sem resposta são considerados como em estado com falha.</span><span class="sxs-lookup"><span data-stu-id="9e54d-115">Unresponsive nodes are considered to be in a failed state.</span></span>  
  
 <span data-ttu-id="9e54d-116">Um conjunto de nós de *quorum* é uma maioria dos nós de votação e testemunhas no cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="9e54d-116">A *quorum* node set is a majority of the voting nodes and witnesses in the WSFC cluster.</span></span> <span data-ttu-id="9e54d-117">A integridade geral e o status de um cluster WSFC são determinados por um *voto de quorum*periódico.</span><span class="sxs-lookup"><span data-stu-id="9e54d-117">The overall health and status of a WSFC cluster is determined by a periodic *quorum vote*.</span></span>  <span data-ttu-id="9e54d-118">A presença de um quorum significa que o cluster está íntegro e é capaz de fornecer tolerância a falhas no nível de nó.</span><span class="sxs-lookup"><span data-stu-id="9e54d-118">The presence of a quorum means that the cluster is healthy and able to provide node-level fault tolerance.</span></span>  
  
 <span data-ttu-id="9e54d-119">A ausência de um quorum indica que o cluster não está íntegro.</span><span class="sxs-lookup"><span data-stu-id="9e54d-119">The absence of a quorum indicates that the cluster is not healthy.</span></span>  <span data-ttu-id="9e54d-120">A integridade do cluster WSFC geral deve ser mantida para assegurar que os nós secundários de integridade estejam disponíveis para nós primários para failover.</span><span class="sxs-lookup"><span data-stu-id="9e54d-120">Overall WSFC cluster health must be maintained in order to ensure that healthy secondary nodes are available for primary nodes to fail over to.</span></span>  <span data-ttu-id="9e54d-121">Se o voto de quorum falhar, o cluster WSFC será definido offline por precaução.</span><span class="sxs-lookup"><span data-stu-id="9e54d-121">If the quorum vote fails, the WSFC cluster will be set offline as a precautionary measure.</span></span>  <span data-ttu-id="9e54d-122">Isso também fará com que todas as instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] registradas com o cluster sejam interrompidas.</span><span class="sxs-lookup"><span data-stu-id="9e54d-122">This will also cause all [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instances registered with the cluster to be stopped.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9e54d-123">Se um cluster WSFC for definido offline devido a uma falha de quorum, a intervenção manual será necessária para colocá-lo online novamente.</span><span class="sxs-lookup"><span data-stu-id="9e54d-123">If a WSFC cluster is set offline because of quorum failure, manual intervention is required to bring it back online.</span></span>  
>   
>  <span data-ttu-id="9e54d-124">Para obter mais informações, veja: [Recuperação de desastres do WSFC por meio de quorum forçado &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md)periódico.</span><span class="sxs-lookup"><span data-stu-id="9e54d-124">For more information, see: [WSFC Disaster Recovery through Forced Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md).</span></span>  
  
##  <a name="quorum-modes"></a><a name="QuorumModes"></a><span data-ttu-id="9e54d-125">Modos de quorum</span><span class="sxs-lookup"><span data-stu-id="9e54d-125">Quorum Modes</span></span>  
 <span data-ttu-id="9e54d-126">Um *modo de quorum* é configurado no nível do cluster WSFC que dita a metodologia usada para votação de quorum.</span><span class="sxs-lookup"><span data-stu-id="9e54d-126">A *quorum mode* is configured at the WSFC cluster level that dictates the methodology used for quorum voting.</span></span>  <span data-ttu-id="9e54d-127">O utilitário Gerenciador de Cluster de Failover recomendará um modo de quorum com base no número de nós no cluster.</span><span class="sxs-lookup"><span data-stu-id="9e54d-127">The Failover Cluster Manager utility will recommend a quorum mode based on the number of nodes in the cluster.</span></span>  
  
 <span data-ttu-id="9e54d-128">Os seguintes modos de quorum podem ser usados para determinar o que constitui um quorum de votos:</span><span class="sxs-lookup"><span data-stu-id="9e54d-128">The following quorum modes can be used to determine what constitutes a quorum of votes:</span></span>  
  
-   <span data-ttu-id="9e54d-129">**Maioria de nós.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-129">**Node Majority.**</span></span> <span data-ttu-id="9e54d-130">Mais da metade dos nós de votação no cluster precisam votar afirmativamente para o cluster ser íntegro.</span><span class="sxs-lookup"><span data-stu-id="9e54d-130">More than one-half of the voting nodes in the cluster must vote affirmatively for the cluster to be healthy.</span></span>  
  
-   <span data-ttu-id="9e54d-131">**Maioria dos nós e compartilhamento de arquivos.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-131">**Node and File Share Majority.**</span></span> <span data-ttu-id="9e54d-132">Semelhante ao modo de quorum Maioria de Nó, exceto pelo fato de um compartilhamento de arquivo remoto também ser configurado como uma testemunha de votação e a conectividade de qualquer nó com esse compartilhamento também ser contada como um voto afirmativo.</span><span class="sxs-lookup"><span data-stu-id="9e54d-132">Similar to Node Majority quorum mode, except that a remote file share is also configured as a voting witness, and connectivity from any node to that share is also counted as an affirmative vote.</span></span>  <span data-ttu-id="9e54d-133">Mais da metade dos votos possíveis deve ser afirmativa para que o cluster seja íntegro.</span><span class="sxs-lookup"><span data-stu-id="9e54d-133">More than one-half of the possible votes must be affirmative for the cluster to be healthy.</span></span>  
  
     <span data-ttu-id="9e54d-134">Como uma prática recomendada, o compartilhamento de arquivo de testemunha não deve residir em nenhum nó no cluster e deve estar visível para todos os nós no cluster.</span><span class="sxs-lookup"><span data-stu-id="9e54d-134">As a best practice, the witness file share should not reside on any node in the cluster, and it should be visible to all nodes in the cluster.</span></span>  
  
-   <span data-ttu-id="9e54d-135">**Maioria de nós e discos.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-135">**Node and Disk Majority.**</span></span> <span data-ttu-id="9e54d-136">Semelhante ao modo de quorum Maioria de Nó, exceto pelo fato de um recurso de cluster de disco compartilhamento também ser designado como uma testemunha de votação e a conectividade de qualquer nó com esse disco compartilhado também ser contada como um voto afirmativo.</span><span class="sxs-lookup"><span data-stu-id="9e54d-136">Similar to Node Majority quorum mode, except that a shared disk cluster resource is also designated as a voting witness, and connectivity from any node to that shared disk is also counted as an affirmative vote.</span></span>  <span data-ttu-id="9e54d-137">Mais da metade dos votos possíveis deve ser afirmativa para que o cluster seja íntegro.</span><span class="sxs-lookup"><span data-stu-id="9e54d-137">More than one-half of the possible votes must be affirmative for the cluster to be healthy.</span></span>  
  
-   <span data-ttu-id="9e54d-138">**Somente Disco.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-138">**Disk Only.**</span></span> <span data-ttu-id="9e54d-139">Um recurso de cluster de disco compartilhamento é designado como uma testemunha e a conectividade por qualquer nó com esse disco compartilhado é contada como um voto afirmativo.</span><span class="sxs-lookup"><span data-stu-id="9e54d-139">A shared disk cluster resource is designated as a witness, and connectivity by any node to that shared disk is counted as an affirmative vote.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="9e54d-140">Ao usar uma configuração de armazenamento assimétrico para o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], em geral, você deve usar o modo de quorum Maioria de Nós quando há um número ímpar de nós de votação ou o modo de quorum Maioria de Compartilhamentos de Nós e Arquivos quando há um número par de nós de votação.</span><span class="sxs-lookup"><span data-stu-id="9e54d-140">When using an asymmetric storage configuration for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], you should generally use the Node Majority quorum mode when you have an odd number of voting nodes, or the Node and File Share Majority quorum mode when you have an even number of voting nodes.</span></span>  
  
##  <a name="voting-and-non-voting-nodes"></a><a name="VotingandNonVotingNodes"></a><span data-ttu-id="9e54d-141">Nós de votação e não votantes</span><span class="sxs-lookup"><span data-stu-id="9e54d-141">Voting and Non-Voting Nodes</span></span>  
 <span data-ttu-id="9e54d-142">Por padrão, cada nó no cluster WSFC é incluso como membro do quorum de cluster; cada nó tem um único voto na determinação da integridade de cluster geral e cada nó tentará continuamente estabelecer um quorum.</span><span class="sxs-lookup"><span data-stu-id="9e54d-142">By default, each node in the WSFC cluster is included as a member of the cluster quorum; each node has a single vote in determining the overall cluster health, and each node will continuously attempt to establish a quorum.</span></span>  <span data-ttu-id="9e54d-143">A discussão de quorum até esse ponto qualificou cuidadosamente o conjunto de nós do cluster WSFC que votam na integridade do cluster como *nós de votação*.</span><span class="sxs-lookup"><span data-stu-id="9e54d-143">The quorum discussion to this point has carefully qualified the set of WSFC cluster nodes that vote on cluster health as *voting nodes*.</span></span>  
  
 <span data-ttu-id="9e54d-144">Nenhum nó individual em um cluster WSFC pode determinar definitivamente se o cluster como um todo é íntegro ou não íntegro.</span><span class="sxs-lookup"><span data-stu-id="9e54d-144">No individual node in a WSFC cluster can definitively determine that the cluster as a whole is healthy or unhealthy.</span></span>  <span data-ttu-id="9e54d-145">A qualquer momento, da perspectiva de cada nó, alguns dos outros nós podem aparecer offline ou talvez pareça que estão em processo de failover ou não respondentes devido a uma falha de comunicação de rede.</span><span class="sxs-lookup"><span data-stu-id="9e54d-145">At any given moment, from the perspective of each node, some of the other nodes may appear to be offline, or appear to be in the process of failover, or appear unresponsive due to a network communication failure.</span></span>  <span data-ttu-id="9e54d-146">Uma função chave do voto de quorum é determinar se o estado aparente de cada nó no cluster WSFC é de fato o estado real desses nós.</span><span class="sxs-lookup"><span data-stu-id="9e54d-146">A key function of the quorum vote is to determine whether the apparent state of each of node in the WSFC cluster is indeed that actual state of those nodes.</span></span>  
  
 <span data-ttu-id="9e54d-147">Para todos os modelos de quorum, exceto 'Somente Disco', a efetividade de um voto de quorum depende das comunicações confiáveis entre todos os nós de votação no cluster.</span><span class="sxs-lookup"><span data-stu-id="9e54d-147">For all of the quorum models except 'Disk Only', the effectiveness of a quorum vote depends on reliable communications between all of the voting nodes in the cluster.</span></span> <span data-ttu-id="9e54d-148">As comunicações de rede entre os nós na mesma sub-rede física devem ser consideradas confiáveis; o voto de quorum deve ser confiável.</span><span class="sxs-lookup"><span data-stu-id="9e54d-148">Network communications between nodes on the same physical subnet should be considered reliable; the quorum vote should be trusted.</span></span>  
  
 <span data-ttu-id="9e54d-149">No entanto, se um nó em outra sub-rede for visto como não respondente em um voto de quorum, mas na verdade estiver online e, de outra forma, íntegro, isso ocorre muito provavelmente devido a uma falha de comunicação de rede entre sub-redes.</span><span class="sxs-lookup"><span data-stu-id="9e54d-149">However, if a node on another subnet is seen as non-responsive in a quorum vote, but it is actually online and otherwise healthy, that is most likely due to a network communications failure between subnets.</span></span>  <span data-ttu-id="9e54d-150">Dependendo da topologia de cluster, do modo de quorum e da configuração da política de failover, essa falha de comunicação de rede pode criar efetivamente mais de um conjunto (ou subconjunto) de nós de votação.</span><span class="sxs-lookup"><span data-stu-id="9e54d-150">Depending upon the cluster topology, quorum mode, and failover policy configuration, that network communications failure may effectively create more than one set (or subset) of voting nodes.</span></span>  
  
 <span data-ttu-id="9e54d-151">Quando mais de um subconjunto de nós de votação consegue estabelecer um quorum próprio, ele é conhecido como *cenário de separação*.</span><span class="sxs-lookup"><span data-stu-id="9e54d-151">When more than one subset of voting nodes is able to establish a quorum on its own, that is known as a *split-brain scenario*.</span></span>  <span data-ttu-id="9e54d-152">Nesse cenário, os nós nos quorums separados podem se comportar de modo diferente e conflitante.</span><span class="sxs-lookup"><span data-stu-id="9e54d-152">In such a scenario, the nodes in the separate quorums may behave differently, and in conflict with one another.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e54d-153">O cenário de separação somente é possível quando um administrador de sistema executa manualmente uma operação de quorum forçado ou em circunstâncias muito raras, um failover forçado; subdividindo explicitamente o conjunto de nós de quorum.</span><span class="sxs-lookup"><span data-stu-id="9e54d-153">The split-brain scenario is only possible when a system administrator manually performs a forced quorum operation, or in very rare circumstances, a forced failover; explicitly subdividing the quorum node set.</span></span>  
  
 <span data-ttu-id="9e54d-154">Para simplificar sua configuração de quorum e aumentar o tempo de inativo, convém ajustar a configuração de *NodeWeight* de cada nó para que o voto do nó não seja contado para o quorum.</span><span class="sxs-lookup"><span data-stu-id="9e54d-154">In order to simplify your quorum configuration and increase up-time, you may want to adjust each node's *NodeWeight* setting so that the node's vote is not counted towards the quorum.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9e54d-155">Para usar configurações de NodeWeight, é necessário aplicar o seguinte hotfix para todos os servidores no cluster WSFC:</span><span class="sxs-lookup"><span data-stu-id="9e54d-155">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="9e54d-156">[KB2494036](https://support.microsoft.com/kb/2494036): há um hotfix disponível para permitir que você configure um nó de cluster que não tenha votos de quorum em [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] e em [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e54d-156">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
##  <a name="recommended-adjustments-to-quorum-voting"></a><a name="RecommendedAdjustmentstoQuorumVoting"></a><span data-ttu-id="9e54d-157">Ajustes recomendados para votação de quorum</span><span class="sxs-lookup"><span data-stu-id="9e54d-157">Recommended Adjustments to Quorum Voting</span></span>  
 <span data-ttu-id="9e54d-158">Ao habilitar ou desabilitar o voto de um nó WSFC específico, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="9e54d-158">When enabling or disabling a given WSFC node's vote, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="9e54d-159">**Nenhum voto, por padrão.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-159">**No vote by default.**</span></span> <span data-ttu-id="9e54d-160">Assuma que cada nó não deve votar sem justificativa explícita.</span><span class="sxs-lookup"><span data-stu-id="9e54d-160">Assume that each node should not vote without explicit justification.</span></span>  
  
-   <span data-ttu-id="9e54d-161">**Inclua todas as réplicas primárias.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-161">**Include all primary replicas.**</span></span> <span data-ttu-id="9e54d-162">Cada nó WSFC que hospeda uma réplica primária do grupo de disponibilidade ou é o proprietário preferencial de uma FCI deve ter um voto.</span><span class="sxs-lookup"><span data-stu-id="9e54d-162">Each WSFC node that hosts an availability group primary replica or is the preferred owner of an FCI should have a vote.</span></span>  
  
-   <span data-ttu-id="9e54d-163">**Inclua possíveis proprietários de failover automático.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-163">**Include possible automatic failover owners.**</span></span> <span data-ttu-id="9e54d-164">Cada nó que pode hospedar uma réplica primária, como resultado de um failover de grupo de disponibilidade automático ou failover de FCI, deve ter um voto.</span><span class="sxs-lookup"><span data-stu-id="9e54d-164">Each node that could host a primary replica, as the result of an automatic availability group failover or FCI failover, should have a vote.</span></span> <span data-ttu-id="9e54d-165">Se houver apenas um grupo de disponibilidade no cluster WSFC e as réplicas de disponibilidade forem hospedadas apenas por instâncias autônomas, essa regra incluirá somente a réplica secundária que é o destino do failover automático.</span><span class="sxs-lookup"><span data-stu-id="9e54d-165">If there is only one availability group in the WSFC cluster and availability replicas are hosted only by standalone instances, this rule includes only the secondary replica that is the automatic failover target.</span></span>  
  
-   <span data-ttu-id="9e54d-166">**Exclua nós de site secundários.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-166">**Exclude secondary site nodes.**</span></span> <span data-ttu-id="9e54d-167">Em geral, não dê votos para nós WSFC que residem em um site de recuperação de desastre secundário.</span><span class="sxs-lookup"><span data-stu-id="9e54d-167">In general, do not give votes to WSFC nodes that reside at a secondary disaster recovery site.</span></span>  <span data-ttu-id="9e54d-168">Você não deseja que os nós no site secundário colaborem para uma decisão de colocar o cluster offline quando não houver nada errado com o site primário.</span><span class="sxs-lookup"><span data-stu-id="9e54d-168">You do not want nodes in the secondary site to contribute to a decision to take the cluster offline when there is nothing wrong with the primary site.</span></span>  
  
-   <span data-ttu-id="9e54d-169">**Números de votos ímpares.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-169">**Odd number of votes.**</span></span> <span data-ttu-id="9e54d-170">Se necessário, adicione um compartilhamento de arquivo testemunha, um nó testemunha ou um disco testemunha ao cluster e ajuste o modo de quorum para prevenir possíveis empates no voto de quorum.</span><span class="sxs-lookup"><span data-stu-id="9e54d-170">If necessary, add a witness file share, a witness node, or a witness disk to the cluster and adjust the quorum mode to prevent possible ties in the quorum vote.</span></span>  
  
-   <span data-ttu-id="9e54d-171">**Reavalie as atribuições de voto após o failover.**</span><span class="sxs-lookup"><span data-stu-id="9e54d-171">**Re-assess vote assignments post-failover.**</span></span> <span data-ttu-id="9e54d-172">Você não deseja o failover em uma configuração de cluster sem suporte para um quorum íntegro.</span><span class="sxs-lookup"><span data-stu-id="9e54d-172">You do not want to fail over into a cluster configuration that does not support a healthy quorum.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e54d-173">Quando a configuração de voto de quorum do WSFC for validada, o Assistente para Grupo de Disponibilidade AlwaysOn exibirá um aviso se um das condições a seguir for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="9e54d-173">When validating WSFC quorum vote configuration, the AlwaysOn Availability Group Wizard shows a warning if any of the following conditions are true:</span></span>  
> 
>  -   <span data-ttu-id="9e54d-174">O nó do cluster que hospeda a réplica primária não tem um voto</span><span class="sxs-lookup"><span data-stu-id="9e54d-174">The cluster node that hosts the primary replica does not have a vote</span></span>  
> -   <span data-ttu-id="9e54d-175">Uma réplica secundária é configurada para failover automático e seu nó de cluster não tem um voto.</span><span class="sxs-lookup"><span data-stu-id="9e54d-175">A secondary replica is configured for automatic failover and its cluster node does not have a vote.</span></span>  
> -   <span data-ttu-id="9e54d-176">O[KB2494036](https://support.microsoft.com/kb/2494036) não está instalado em todos os nós de cluster que hospedam réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="9e54d-176">[KB2494036](https://support.microsoft.com/kb/2494036) is not installed on all cluster nodes that host availability replicas.</span></span> <span data-ttu-id="9e54d-177">Esse patch é necessário para adicionar ou remover votos para nós de cluster em implantações multissite.</span><span class="sxs-lookup"><span data-stu-id="9e54d-177">This patch is required to add or remove votes for cluster nodes in multi-site deployments.</span></span> <span data-ttu-id="9e54d-178">No entanto, em implantações de site único, ele geralmente não é necessário, e você pode ignorar o aviso sem nenhum problema.</span><span class="sxs-lookup"><span data-stu-id="9e54d-178">However, in single-site deployments, it is usually not required and you may safely ignore the warning.</span></span>  
> 
> [!TIP]
>  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9e54d-179">expõe várias DMVs (exibições de gerenciamento dinâmico) do sistema que podem ajudá-lo a gerenciar configurações relacionadas à configuração do cluster WSFC e à votação de quorum do nó.</span><span class="sxs-lookup"><span data-stu-id="9e54d-179">exposes several system dynamic management views (DMVs) that can help you manage settings related WSFC cluster configuration and node quorum voting.</span></span>  
> 
>  <span data-ttu-id="9e54d-180">Para obter mais informações, veja:  [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql), [sys.dm_hadr_cluster_members](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql), [sys.dm_os_cluster_nodes](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-nodes-transact-sql), [sys.dm_hadr_cluster_networks](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-networks-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="9e54d-180">For more information, see:  [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql), [sys.dm_hadr_cluster_members](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql), [sys.dm_os_cluster_nodes](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-nodes-transact-sql), [sys.dm_hadr_cluster_networks](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-networks-transact-sql)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9e54d-181">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9e54d-181">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9e54d-182">Exibir configurações de NodeWeight de quorum do cluster</span><span class="sxs-lookup"><span data-stu-id="9e54d-182">View Cluster Quorum NodeWeight Settings</span></span>](view-cluster-quorum-nodeweight-settings.md)  
  
-   [<span data-ttu-id="9e54d-183">Definir configurações de NodeWeight de quorum do cluster</span><span class="sxs-lookup"><span data-stu-id="9e54d-183">Configure Cluster Quorum NodeWeight Settings</span></span>](configure-cluster-quorum-nodeweight-settings.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="9e54d-184">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="9e54d-184">Related Content</span></span>  
  
-   [<span data-ttu-id="9e54d-185">Guia de soluções AlwaysOn do Microsoft SQL Server para alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="9e54d-185">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
-   [<span data-ttu-id="9e54d-186">Verificação da configuração do voto de quorum nos assistentes de Grupo de Disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="9e54d-186">Quorum vote configuration check in AlwaysOn Availability Group Wizards</span></span>](https://blogs.msdn.com/b/sqlalwayson/archive/2012/03/13/quorum-vote-configuration-check-in-alwayson-availability-group-wizards-andy-jing.aspx)  
  
-   <span data-ttu-id="9e54d-187">[Tecnologias do Windows Server: clusters de failover](https://technet.microsoft.com/library/cc732488\(v=WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e54d-187">[Windows Server Technologies:  Failover Clusters](https://technet.microsoft.com/library/cc732488\(v=WS.10\).aspx)</span></span>  
  
-   <span data-ttu-id="9e54d-188">[Guia passo a passo do cluster de failover: configurando o quorum em um cluster de failover](https://technet.microsoft.com/library/cc770620\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e54d-188">[Failover Cluster Step-by-Step Guide: Configuring the Quorum in a Failover Cluster](https://technet.microsoft.com/library/cc770620\(WS.10\).aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e54d-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9e54d-189">See Also</span></span>  
 <span data-ttu-id="9e54d-190">[Recuperação de desastre do WSFC por meio de quorum forçado &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9e54d-190">[WSFC Disaster Recovery through Forced Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span></span>  
 [<span data-ttu-id="9e54d-191">WSFC &#40;Windows Server Failover Clustering&#41; com o SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e54d-191">Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server</span></span>](windows-server-failover-clustering-wsfc-with-sql-server.md)  
  
  