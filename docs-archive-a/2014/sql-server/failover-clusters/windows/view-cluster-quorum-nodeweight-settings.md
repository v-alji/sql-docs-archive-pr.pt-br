---
title: Exibir configurações de NodeWeight de quorum de cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: b845e73a-bb01-4de2-aac2-8ac12abebc95
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef2176d4916e8affbb9ef89c9b26499289c520ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573560"
---
# <a name="view-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="8e413-102">Exibir configurações de NodeWeight de quorum de cluster</span><span class="sxs-lookup"><span data-stu-id="8e413-102">View Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="8e413-103">Este tópico descreve como exibir configurações de NodeWeight para cada nó de membro em um cluster WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="8e413-103">This topic describes how to view NodeWeight settings for each member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="8e413-104">As configurações de NodeWeight são usadas durante a votação de quorum para dar suporte à recuperação de desastre e a cenários com várias sub-redes para instâncias de cluster de failover do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] e do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e413-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="8e413-105">**Antes de iniciar:**  [Pré-requisitos](#Prerequisites), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="8e413-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="8e413-106">**Para exibir as configurações de NodeWeight de quorum usando:** [Usando o Transact-SQL](#TsqlProcedure), [Usando o PowerShell](#PowerShellProcedure), [Usando Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="8e413-106">**To view quorum NodeWeight settings using:** [Using Transact-SQL](#TsqlProcedure), [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8e413-107">Antes de iniciar</span><span class="sxs-lookup"><span data-stu-id="8e413-107">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8e413-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8e413-108">Prerequisites</span></span>  
 <span data-ttu-id="8e413-109">Esse recurso somente tem suporte no [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] ou em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="8e413-109">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e413-110">Para usar configurações de NodeWeight, é necessário aplicar o seguinte hotfix para todos os servidores no cluster WSFC:</span><span class="sxs-lookup"><span data-stu-id="8e413-110">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="8e413-111">[KB2494036](https://support.microsoft.com/kb/2494036): Há um hotfix disponível para permitir que você configure um nó de cluster que não tenha votos de quorum em [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] e em [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e413-111">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="8e413-112">Se esse hotfix não for instalado, os exemplos neste tópico retornarão valores vazios ou NULL para NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="8e413-112">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8e413-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="8e413-113">Security</span></span>  
 <span data-ttu-id="8e413-114">O usuário deve ser uma conta de domínio que seja membro do grupo Administradores local em cada nó do cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="8e413-114">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8e413-115">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e413-115">Using Transact-SQL</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="8e413-116">Para exibir configurações de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="8e413-116">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="8e413-117">Conecte-se a qualquer instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no cluster.</span><span class="sxs-lookup"><span data-stu-id="8e413-117">Connect to any [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the cluster.</span></span>  
  
2.  <span data-ttu-id="8e413-118">Consulte a exibição [sys].[dm_hadr_cluster_members].</span><span class="sxs-lookup"><span data-stu-id="8e413-118">Query the [sys].[dm_hadr_cluster_members] view.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="8e413-119">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8e413-119">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="8e413-120">O exemplo a seguir consulta um modo de exibição do sistema para retornar valores para todos os nós no cluster dessa instância.</span><span class="sxs-lookup"><span data-stu-id="8e413-120">The following example queries a system view to return values for all of the nodes in that instance's cluster.</span></span>  
  
```sql  
SELECT  member_name, member_state_desc, number_of_quorum_votes  
 FROM   sys.dm_hadr_cluster_members;  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="8e413-121">Usando o Powershell</span><span class="sxs-lookup"><span data-stu-id="8e413-121">Using Powershell</span></span>  
  
### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="8e413-122">Para exibir configurações de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="8e413-122">To view NodeWeight settings</span></span>
  
1.  <span data-ttu-id="8e413-123">Inicie um Windows PowerShell elevado via **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="8e413-123">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="8e413-124">Importe o módulo `FailoverClusters` para habilitar commandlets de cluster.</span><span class="sxs-lookup"><span data-stu-id="8e413-124">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="8e413-125">Use o objeto `Get-ClusterNode` para retornar uma coleção de objetos de nó de cluster.</span><span class="sxs-lookup"><span data-stu-id="8e413-125">Use the `Get-ClusterNode` object to return a collection of cluster node objects.</span></span>  
  
4.  <span data-ttu-id="8e413-126">Gere as propriedades de nó de cluster em um formato legível.</span><span class="sxs-lookup"><span data-stu-id="8e413-126">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="8e413-127">Exemplo (Powershell)</span><span class="sxs-lookup"><span data-stu-id="8e413-127">Example (Powershell)</span></span>  
 <span data-ttu-id="8e413-128">O exemplo a seguir gera algumas das propriedades de nó para o cluster chamado "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="8e413-128">The following example output some of the node properties for the cluster called "Cluster001".</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$cluster = "Cluster001"  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -Property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="8e413-129">Usando Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="8e413-129">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e413-130">O utilitário cluster.exe foi preterido na versão [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e413-130">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="8e413-131">Use o PowerShell com Clustering de Failover para desenvolvimento futuro.</span><span class="sxs-lookup"><span data-stu-id="8e413-131">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="8e413-132">O utilitário cluster.exe será removido na próxima versão do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8e413-132">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="8e413-133">Para obter mais informações, consulte [Mapeando comandos cluster.exe para cmdlets Windows PowerShell para clusters de failover](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="8e413-133">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="8e413-134">Para exibir configurações de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="8e413-134">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="8e413-135">Inicie um Prompt de Comando elevado via **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="8e413-135">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="8e413-136">Usar **cluster.exe** para retornar o status do nó e valores de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="8e413-136">Use **cluster.exe** to return node status and NodeWeight values</span></span>  
  
### <a name="example-clusterexe"></a><span data-ttu-id="8e413-137">Exemplo (Cluster.exe)</span><span class="sxs-lookup"><span data-stu-id="8e413-137">Example (Cluster.exe)</span></span>  
 <span data-ttu-id="8e413-138">O exemplo a seguir gera algumas das propriedades de nó para o cluster chamado "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="8e413-138">The following example outputs some of the node properties for the cluster called "Cluster001".</span></span>  
  
```cmd
cluster.exe Cluster001 node /status /properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e413-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e413-139">See Also</span></span>  
 <span data-ttu-id="8e413-140">[Configuração de modos de quorum WSFC e votação &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8e413-140">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="8e413-141">[Definir configurações de NodeWeight de quorum de cluster](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8e413-141">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="8e413-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8e413-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span></span>  
 <span data-ttu-id="8e413-143">[Cmdlets de cluster de failover no Windows PowerShell listados por foco de tarefa](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8e413-143">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
