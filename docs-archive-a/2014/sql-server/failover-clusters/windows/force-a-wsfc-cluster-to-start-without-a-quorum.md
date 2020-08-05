---
title: Forçar um cluster WSFC a iniciar sem um quorum | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: 4a121375-7424-4444-b876-baefa8fe9015
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6f2110b706de015d0c7b19475b335908c118267
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573563"
---
# <a name="force-a-wsfc-cluster-to-start-without-a-quorum"></a><span data-ttu-id="dddb9-102">Forçar um cluster WSFC para iniciar sem um quorum</span><span class="sxs-lookup"><span data-stu-id="dddb9-102">Force a WSFC Cluster to Start Without a Quorum</span></span>
  <span data-ttu-id="dddb9-103">Este tópico descreve como forçar um nó de cluster WSFC (Windows Server Failover Clustering) a iniciar sem um quorum.</span><span class="sxs-lookup"><span data-stu-id="dddb9-103">This topic describes how to force a Windows Server Failover Clustering (WSFC) cluster node to start without a quorum.</span></span>  <span data-ttu-id="dddb9-104">Talvez isso seja necessário na recuperação de desastre e em cenários com várias sub-redes para recuperar dados e restabelecer totalmente a alta disponibilidade para o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] e instâncias de cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dddb9-104">This may be required in disaster recovery and multi-subnet scenarios to recover data and fully re-establish high-availability for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="dddb9-105">**Antes de iniciar:**  [Recomendações](#Recommendations), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="dddb9-105">**Before you start:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="dddb9-106">**Para forçar um cluster a iniciar sem um quorum usando:**  [Usando o Gerenciador de Cluster de Failover](#FailoverClusterManagerProcedure), [Usando o Powershell](#PowerShellProcedure), [Usando Net.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="dddb9-106">**To force a cluster to start without a quorum using:**  [Using Failover Cluster Manager](#FailoverClusterManagerProcedure), [Using Powershell](#PowerShellProcedure), [Using Net.exe](#CommandPromptProcedure)</span></span>  
  
-   <span data-ttu-id="dddb9-107">**Acompanhamento:**  [Acompanhamento: depois de forçar o cluster a iniciar sem um quorum](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="dddb9-107">**Follow up:**  [Follow Up: After Forcing Cluster to Start without a Quorum](#FollowUp)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dddb9-108">Antes de iniciar</span><span class="sxs-lookup"><span data-stu-id="dddb9-108">Before You Start</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="dddb9-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="dddb9-109">Recommendations</span></span>  
 <span data-ttu-id="dddb9-110">Exceto nas ocasiões em que houver instruções explícitas, os procedimentos neste tópico deverão funcionar se você executá-los de qualquer nó no cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="dddb9-110">Except where explicitly directed, the procedures in this topic should work if you execute them from any node in the WSFC cluster.</span></span>  <span data-ttu-id="dddb9-111">No entanto, é possível obter resultados melhores e evitar problemas de rede, executando essas etapas a partir do nó que você pretende forçar a iniciar sem um quorum.</span><span class="sxs-lookup"><span data-stu-id="dddb9-111">However, you may obtain better results, and avoid networking issues, by executing these steps from the node that you intend to force to start without a quorum.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dddb9-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="dddb9-112">Security</span></span>  
 <span data-ttu-id="dddb9-113">O usuário deve ser uma conta de domínio que seja membro do grupo Administradores local em cada nó do cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="dddb9-113">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-failover-cluster-manager"></a><a name="FailoverClusterManagerProcedure"></a><span data-ttu-id="dddb9-114">Usando Gerenciador de Cluster de Failover</span><span class="sxs-lookup"><span data-stu-id="dddb9-114">Using Failover Cluster Manager</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="dddb9-115">Para forçar um cluster a iniciar sem um quorum</span><span class="sxs-lookup"><span data-stu-id="dddb9-115">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="dddb9-116">Abra um Gerenciador de Cluster de Failover e conecte-se ao nó de cluster que você deseja forçar online.</span><span class="sxs-lookup"><span data-stu-id="dddb9-116">Open a Failover Cluster Manager and connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="dddb9-117">No painel **ações** , clique em **forçar início do cluster**e em **Sim – forçar o início do cluster**.</span><span class="sxs-lookup"><span data-stu-id="dddb9-117">In the **Actions** pane, click **Force Cluster Start**, and then click **Yes - Force my cluster to start**.</span></span>  
  
3.  <span data-ttu-id="dddb9-118">No painel esquerdo, na árvore **Gerenciador de Cluster de Failover** , clique no nome do cluster.</span><span class="sxs-lookup"><span data-stu-id="dddb9-118">In the left pane, in the **Failover Cluster Manager** tree, click the cluster name.</span></span>  
  
4.  <span data-ttu-id="dddb9-119">No painel de resumo, confirme se o valor atual de **Configuração de Quorum** é:  **Aviso: o cluster está sendo executado no estado ForceQuorum**.</span><span class="sxs-lookup"><span data-stu-id="dddb9-119">In the summary pane, confirm that the current **Quorum Configuration** value is:  **Warning: Cluster is running in ForceQuorum state**.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a><span data-ttu-id="dddb9-120">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="dddb9-120">Using Powershell</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="dddb9-121">Para forçar um cluster a iniciar sem um quorum</span><span class="sxs-lookup"><span data-stu-id="dddb9-121">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="dddb9-122">Inicie um Windows PowerShell elevado via **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="dddb9-122">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="dddb9-123">Importe o módulo `FailoverClusters` para habilitar commandlets de cluster.</span><span class="sxs-lookup"><span data-stu-id="dddb9-123">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="dddb9-124">Use `Stop-ClusterNode` para assegurar que o serviço de cluster seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="dddb9-124">Use `Stop-ClusterNode` to make sure that the cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="dddb9-125">Use `Start-ClusterNode` com `-FixQuorum` para forçar o serviço de cluster a ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="dddb9-125">Use `Start-ClusterNode` with `-FixQuorum` to force the cluster service to start.</span></span>  
  
5.  <span data-ttu-id="dddb9-126">Use `Get-ClusterNode` com `-Propery NodeWieght = 1` para definir o valor que garanta que o nó é um membro votante do quorum.</span><span class="sxs-lookup"><span data-stu-id="dddb9-126">Use `Get-ClusterNode` with `-Propery NodeWieght = 1` to set the value the guarantees that the node is a voting member of the quorum.</span></span>  
  
6.  <span data-ttu-id="dddb9-127">Gere as propriedades de nó de cluster em um formato legível.</span><span class="sxs-lookup"><span data-stu-id="dddb9-127">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="dddb9-128">Exemplo (Powershell)</span><span class="sxs-lookup"><span data-stu-id="dddb9-128">Example (Powershell)</span></span>  
 <span data-ttu-id="dddb9-129">O exemplo a seguir força o serviço de cluster de nó AlwaysOnSrv02 a iniciar sem um quorum, define o `NodeWeight = 1`e enumera o status de nó de cluster a partir do nó recém-forçado.</span><span class="sxs-lookup"><span data-stu-id="dddb9-129">The following example forces the AlwaysOnSrv02 node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv02"  
Stop-ClusterNode -Name $node  
Start-ClusterNode -Name $node -FixQuorum  
  
(Get-ClusterNode $node).NodeWeight = 1  
  
$nodes = Get-ClusterNode -Cluster $node  
$nodes | Format-Table -property NodeName, State, NodeWeight
```  
  
##  <a name="using-netexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="dddb9-130">Usando Net.exe</span><span class="sxs-lookup"><span data-stu-id="dddb9-130">Using Net.exe</span></span>  
  
### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="dddb9-131">Para forçar um cluster a iniciar sem um quorum</span><span class="sxs-lookup"><span data-stu-id="dddb9-131">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="dddb9-132">Use a Área de Trabalho Remota para se conectar ao nó de cluster que você deseja forçar online.</span><span class="sxs-lookup"><span data-stu-id="dddb9-132">Use Remote Desktop to connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="dddb9-133">Inicie um Prompt de Comando elevado via **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="dddb9-133">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
3.  <span data-ttu-id="dddb9-134">Use **net.exe** para assegurar que o serviço de cluster local seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="dddb9-134">Use **net.exe** to make sure that the local cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="dddb9-135">Use **net.exe** com `/forcequorum` para forçar o início do serviço de cluster local.</span><span class="sxs-lookup"><span data-stu-id="dddb9-135">Use **net.exe** with `/forcequorum` to force the local cluster service to start.</span></span>  
  
### <a name="example-netexe"></a><span data-ttu-id="dddb9-136">Exemplo (Net.exe)</span><span class="sxs-lookup"><span data-stu-id="dddb9-136">Example (Net.exe)</span></span>  
 <span data-ttu-id="dddb9-137">O exemplo a seguir força um serviço de cluster de nó a iniciar sem um quorum, define o `NodeWeight = 1`e enumera o status de nó de cluster a partir do nó recém-forçado.</span><span class="sxs-lookup"><span data-stu-id="dddb9-137">The following example forces a node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```cmd
net.exe stop clussvc  
net.exe start clussvc /forcequorum  
```  
  
##  <a name="follow-up-after-forcing-cluster-to-start-without-a-quorum"></a><a name="FollowUp"></a><span data-ttu-id="dddb9-138">Acompanhamento: depois de forçar o cluster a iniciar sem um quorum</span><span class="sxs-lookup"><span data-stu-id="dddb9-138">Follow Up: After Forcing Cluster to Start without a Quorum</span></span>  
  
-   <span data-ttu-id="dddb9-139">Você deve reavaliar e reconfigurar valores de NodeWeight para construir corretamente um novo quorum antes de colocar os outros nós online novamente.</span><span class="sxs-lookup"><span data-stu-id="dddb9-139">You must re-evaluate and reconfigure NodeWeight values to correctly construct a new quorum before bringing other nodes back online.</span></span> <span data-ttu-id="dddb9-140">Caso contrário, o cluster talvez fique offline novamente.</span><span class="sxs-lookup"><span data-stu-id="dddb9-140">Otherwise, the cluster may go back offline again.</span></span>  
  
     <span data-ttu-id="dddb9-141">Para obter mais informações, veja [Configuração de modos de quorum WSFC e votação &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dddb9-141">For more information, see [WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="dddb9-142">Os procedimentos neste tópico constituem apenas uma etapa para a colocação do cluster WSFC online novamente se uma falha de quorum não planejada por ocorrer.</span><span class="sxs-lookup"><span data-stu-id="dddb9-142">The procedures in this topic are only one step in bringing the WSFC cluster back online if an un-planned quorum failure were to occur.</span></span>  <span data-ttu-id="dddb9-143">Talvez você também queira executar etapas adicionais para impedir que outros nós de cluster WSFC interfiram na nova configuração do quorum.</span><span class="sxs-lookup"><span data-stu-id="dddb9-143">You may also want to take additional steps to prevent other WSFC cluster nodes from interfering with the new quorum configuration.</span></span>  
  
-   <span data-ttu-id="dddb9-144">Outros recursos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , como [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], espelhamento de banco de dados e envio de logs, também podem exigir ações subsequentes para recuperar dados e restabelecer totalmente a alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="dddb9-144">Other [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features such as [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], database mirroring, and log shipping may also require subsequent actions to recover data and to fully re-establish high-availability.</span></span>  
  
     <span data-ttu-id="dddb9-145">**Para obter mais informações:**</span><span class="sxs-lookup"><span data-stu-id="dddb9-145">**For more information:**</span></span>  
  
     [<span data-ttu-id="dddb9-146">Executar um failover manual forçado de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dddb9-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](../../../database-engine/availability-groups/windows/perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
     [<span data-ttu-id="dddb9-147">Forçar serviço em uma sessão de espelhamento de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dddb9-147">Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](../../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)  
  
     [<span data-ttu-id="dddb9-148">Executar failover para um secundário de envio de logs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dddb9-148">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](../../../database-engine/log-shipping/fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="dddb9-149">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="dddb9-149">Related Content</span></span>  
  
-   <span data-ttu-id="dddb9-150">[Exibir eventos e logs de um cluster de failover](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="dddb9-150">[View Events and Logs for a Failover Cluster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span></span>  
  
-   [<span data-ttu-id="dddb9-151">Cluster de failover Get-ClusterLog do cmdlet</span><span class="sxs-lookup"><span data-stu-id="dddb9-151">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="dddb9-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dddb9-152">See Also</span></span>  
 <span data-ttu-id="dddb9-153">[Recuperação de desastre do WSFC por meio de quorum forçado &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dddb9-153">[WSFC Disaster Recovery through Forced Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span></span>  
 <span data-ttu-id="dddb9-154">[Definir configurações de NodeWeight de quorum de cluster](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="dddb9-154">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="dddb9-155">[Cmdlets de cluster de failover no Windows PowerShell listados por foco de tarefa](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="dddb9-155">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
