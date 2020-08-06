---
title: Recuperar-se de uma falha na instância do cluster de failover | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], recovery from failure
- failover clustering [SQL Server], recovery from failure
- hardware failures [SQL Server]
- recovering failover cluster failures [SQL Server]
ms.assetid: 3d151d0c-e841-4325-8606-c094de37d7d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60db4c2e480b094c18d0a8071e947a38cdc779d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685022"
---
# <a name="recover-from-failover-cluster-instance-failure"></a><span data-ttu-id="5d112-102">Recuperar-se de uma falha na instância do cluster de failover</span><span class="sxs-lookup"><span data-stu-id="5d112-102">Recover from Failover Cluster Instance Failure</span></span>
  <span data-ttu-id="5d112-103">Este tópico descreve como se recuperar de falhas de cluster usando o snap-in Gerenciador de Cluster de Failover após a ocorrência de um failover no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d112-103">This topic describes how to recover from cluster failures by using the Failover Cluster Manager snap-in after a failover occurs in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5d112-104">O snap-in Gerenciador de Cluster de Failover é o aplicativo de gerenciamento de cluster do serviço WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="5d112-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Serer Failover Clustering (WSFC) service.</span></span>  
  
-   [<span data-ttu-id="5d112-105">Recuperar de uma falha irreparável</span><span class="sxs-lookup"><span data-stu-id="5d112-105">Recover from an irreparable failure</span></span>](#Scenario1)  
  
-   [<span data-ttu-id="5d112-106">Recuperar de uma falha de software</span><span class="sxs-lookup"><span data-stu-id="5d112-106">Recover from a software failure</span></span>](#Scenario2)  
  
##  <a name="recover-from-an-irreparable-failure"></a><a name="Scenario1"></a> <span data-ttu-id="5d112-107">Recuperar de uma falha irreparável</span><span class="sxs-lookup"><span data-stu-id="5d112-107">Recover from an irreparable failure</span></span>  
 <span data-ttu-id="5d112-108">Use as seguintes etapas para recuperar-se de uma falha irreparável.</span><span class="sxs-lookup"><span data-stu-id="5d112-108">Use the following steps to recover from an irreparable failure.</span></span> <span data-ttu-id="5d112-109">A falha pode ser causada, por exemplo, por uma falha em um controlador de disco ou no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="5d112-109">The failure could be caused, for example, by the failure of a disk controller or the operating system.</span></span> <span data-ttu-id="5d112-110">Nesse caso, a falha é gerada por um problema de hardware no Nó 1 de um cluster de dois nós.</span><span class="sxs-lookup"><span data-stu-id="5d112-110">In this case, failure is caused by hardware failure in Node 1 of a two-node cluster.</span></span>  
  
1.  <span data-ttu-id="5d112-111">Após a falha no Nó 1, a FCI do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] executa failover no Nó 2.</span><span class="sxs-lookup"><span data-stu-id="5d112-111">After Node 1 fails, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="5d112-112">Remova o Nó 1 da FCI.</span><span class="sxs-lookup"><span data-stu-id="5d112-112">Evict Node 1 from the FCI.</span></span> <span data-ttu-id="5d112-113">Para fazer isso, do Nó 2, abra o snap-in Gerenciador de Cluster de Failover, clique com o botão direito do mouse no Nó 1, clique em **Mover Ações**e em **Remover Nó**.</span><span class="sxs-lookup"><span data-stu-id="5d112-113">To do this, from Node 2, open the Failover Cluster Manager snap-in, right-click Node1, click **Move Actions**, and then click **Evict Node**.</span></span>  
  
3.  <span data-ttu-id="5d112-114">Verifique se o Nó 1 foi removido da definição de cluster.</span><span class="sxs-lookup"><span data-stu-id="5d112-114">Verify that Node 1 has been evicted from the cluster definition.</span></span>  
  
4.  <span data-ttu-id="5d112-115">Instale o novo hardware que substituirá o hardware com falha no Nó 1.</span><span class="sxs-lookup"><span data-stu-id="5d112-115">Install new hardware to replace the failed hardware in Node 1.</span></span>  
  
5.  <span data-ttu-id="5d112-116">Usando o snap-in Gerenciador de Cluster de Failover, adicione o Nó 1 ao cluster existente.</span><span class="sxs-lookup"><span data-stu-id="5d112-116">Using the Failover Cluster Manager snap-in, add Node 1 to the existing cluster.</span></span> <span data-ttu-id="5d112-117">Para obter mais informações sobre como configurar o MS DTC, consulte [Antes de instalar o clustering de failover](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="5d112-117">For more information, see [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
6.  <span data-ttu-id="5d112-118">Verifique se as contas de administradoras são as mesmas em todos os nós do cluster.</span><span class="sxs-lookup"><span data-stu-id="5d112-118">Ensure that the administrator accounts are the same on all cluster nodes.</span></span>  
  
7.  <span data-ttu-id="5d112-119">Execute a Instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para adicionar o Nó 1 à FCI.</span><span class="sxs-lookup"><span data-stu-id="5d112-119">Run [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to add Node 1 to the FCI.</span></span> <span data-ttu-id="5d112-120">Para obter mais informações, consulte [Adicionar ou remover nós em um cluster de Failover SQL Server &#40;instalação&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="5d112-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
##  <a name="recover-from-a-reparable-failure"></a><a name="Scenario2"></a> <span data-ttu-id="5d112-121">Recuperar-se de uma falha reparável</span><span class="sxs-lookup"><span data-stu-id="5d112-121">Recover from a reparable failure</span></span>  
 <span data-ttu-id="5d112-122">Execute as seguintes etapas ara recuperar-se de uma falha reparável.</span><span class="sxs-lookup"><span data-stu-id="5d112-122">Us the following steps to recover from a reparable failure.</span></span> <span data-ttu-id="5d112-123">Nesse caso, a falha é causada porque o Nó 1 está desativado ou offline, mas não irreparavelmente danificado.</span><span class="sxs-lookup"><span data-stu-id="5d112-123">In this case, failure is caused by Node 1 being down or offline but not irretrievably broken.</span></span> <span data-ttu-id="5d112-124">Ela pode ser causada por uma falha do sistema operacional, falha de hardware ou falha na própria instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d112-124">This could be caused by an operating system failure, hardware failure, or failure in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance itself.</span></span>  
  
1.  <span data-ttu-id="5d112-125">Após a falha no Nó 1, a FCI executa failover no Nó 2.</span><span class="sxs-lookup"><span data-stu-id="5d112-125">After Node 1 fails, the FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="5d112-126">Resolva o problema no Nó 1.</span><span class="sxs-lookup"><span data-stu-id="5d112-126">Resolve the problem with Node 1.</span></span>  
  
3.  <span data-ttu-id="5d112-127">Verifique se todos os nós estão online e se o serviço WSFC está funcionando.</span><span class="sxs-lookup"><span data-stu-id="5d112-127">Ensure that all nodes are online and the WSFC service is working.</span></span>  
  
4.  <span data-ttu-id="5d112-128">Execute failover no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no nó recuperado.</span><span class="sxs-lookup"><span data-stu-id="5d112-128">Fail over [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the recovered node.</span></span>  
  
  
