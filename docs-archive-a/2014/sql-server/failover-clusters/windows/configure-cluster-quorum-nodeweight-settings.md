---
title: Definir configurações de NodeWeight de quórum de cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: cb3fd9a6-39a2-4e9c-9157-619bf3db9951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e469d5fc0fc030304a7cf2f1bdd894eb578aa056
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573575"
---
# <a name="configure-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="00e6c-102">Definir configurações de NodeWeight de quorum de cluster</span><span class="sxs-lookup"><span data-stu-id="00e6c-102">Configure Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="00e6c-103">Este tópico descreve como definir configurações de NodeWeight para um nó de membro em um cluster WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="00e6c-103">This topic describes how to configure NodeWeight settings for a member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="00e6c-104">As configurações de NodeWeight são usadas durante a votação de quorum para dar suporte à recuperação de desastre e a cenários com várias sub-redes para instâncias de cluster de failover do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] e do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00e6c-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="00e6c-105">**Antes de iniciar:**  [Pré-requisitos](#Prerequisites), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="00e6c-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="00e6c-106">**Para exibir as configurações de NodeWeight de quorum usando:** [Usando o PowerShell](#PowerShellProcedure), [Usando Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="00e6c-106">**To view quorum NodeWeight settings using:** [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
-   [<span data-ttu-id="00e6c-107">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="00e6c-107">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="00e6c-108">Antes de iniciar</span><span class="sxs-lookup"><span data-stu-id="00e6c-108">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="00e6c-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="00e6c-109">Prerequisites</span></span>  
 <span data-ttu-id="00e6c-110">Esse recurso somente tem suporte no [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] ou em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="00e6c-110">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="00e6c-111">Para usar configurações de NodeWeight, é necessário aplicar o seguinte hotfix para todos os servidores no cluster WSFC:</span><span class="sxs-lookup"><span data-stu-id="00e6c-111">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="00e6c-112">[KB2494036](https://support.microsoft.com/kb/2494036): Há um hotfix disponível para permitir que você configure um nó de cluster que não tenha votos de quorum em [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] e em [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00e6c-112">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="00e6c-113">Se esse hotfix não for instalado, os exemplos neste tópico retornarão valores vazios ou NULL para NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="00e6c-113">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="00e6c-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="00e6c-114">Security</span></span>  
 <span data-ttu-id="00e6c-115">O usuário deve ser uma conta de domínio que seja membro do grupo Administradores local em cada nó do cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="00e6c-115">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="00e6c-116">Usando o Powershell</span><span class="sxs-lookup"><span data-stu-id="00e6c-116">Using Powershell</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="00e6c-117">Para definir configurações de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="00e6c-117">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="00e6c-118">Inicie um Windows PowerShell elevado via **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="00e6c-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="00e6c-119">Importe o módulo `FailoverClusters` para habilitar commandlets de cluster.</span><span class="sxs-lookup"><span data-stu-id="00e6c-119">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="00e6c-120">Use o objeto `Get-ClusterNode` para definir a propriedade `NodeWeight` para cada nó no cluster.</span><span class="sxs-lookup"><span data-stu-id="00e6c-120">Use the `Get-ClusterNode` object to set the `NodeWeight` property for each node in the cluster.</span></span>  
  
4.  <span data-ttu-id="00e6c-121">Gere as propriedades de nó de cluster em um formato legível.</span><span class="sxs-lookup"><span data-stu-id="00e6c-121">Output the cluster node properties in a readable format.</span></span>  
  
 <span data-ttu-id="00e6c-122">O exemplo a seguir altera a configuração de NodeWeight para remover o voto de quorum do nó "AlwaysOnSrv1" e gera as configurações de todos os nós no cluster.</span><span class="sxs-lookup"><span data-stu-id="00e6c-122">The following example changes the NodeWeight setting to remove the quorum vote for the "AlwaysOnSrv1" node, and then outputs the settings for all nodes in the cluster.</span></span>
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv1"  
(Get-ClusterNode $node).NodeWeight = 0  
  
$cluster = (Get-ClusterNode $node).Cluster  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="00e6c-123">Usando Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="00e6c-123">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00e6c-124">O utilitário cluster.exe foi preterido na versão [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00e6c-124">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="00e6c-125">Use o PowerShell com Clustering de Failover para desenvolvimento futuro.</span><span class="sxs-lookup"><span data-stu-id="00e6c-125">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="00e6c-126">O utilitário cluster.exe será removido na próxima versão do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="00e6c-126">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="00e6c-127">Para obter mais informações, consulte [Mapeando comandos cluster.exe para cmdlets Windows PowerShell para clusters de failover](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="00e6c-127">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="00e6c-128">Para definir configurações de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="00e6c-128">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="00e6c-129">Inicie um Prompt de Comando elevado via **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="00e6c-129">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="00e6c-130">Use **cluster.exe** para definir valores de `NodeWeight` .</span><span class="sxs-lookup"><span data-stu-id="00e6c-130">Use **cluster.exe** to set `NodeWeight` values.</span></span>  

 <span data-ttu-id="00e6c-131">O exemplo a seguir altera o valor de NodeWeight para remover o voto de quorum do nó "AlwaysOnSrv1" no cluster "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="00e6c-131">The following example changes the NodeWeight value to remove the quorum vote of the "AlwaysOnSrv1" node in the "Cluster001" cluster.</span></span>  
  
```cmd
cluster.exe Cluster001 node AlwaysOnSrv1 /prop NodeWeight=0  
```  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="00e6c-132">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="00e6c-132">Related Content</span></span>  
  
-   <span data-ttu-id="00e6c-133">[Exibir eventos e logs de um cluster de failover](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="00e6c-133">[View Events and Logs for a Failover Cluster](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="00e6c-134">Cluster de failover Get-ClusterLog do cmdlet</span><span class="sxs-lookup"><span data-stu-id="00e6c-134">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="00e6c-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="00e6c-135">See Also</span></span>  
 <span data-ttu-id="00e6c-136">[Os modos de quorum WSFC e a configuração de votação &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00e6c-136">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="00e6c-137">[Exibir configurações de NodeWeight de quorum de cluster](view-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="00e6c-137">[View Cluster Quorum NodeWeight Settings](view-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="00e6c-138">[Cmdlets de cluster de failover no Windows PowerShell listados por foco de tarefa](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="00e6c-138">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
