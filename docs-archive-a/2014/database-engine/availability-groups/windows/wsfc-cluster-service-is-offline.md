---
title: O serviço de cluster WSFC está offline | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp1WSFCquorum.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: d502548d-ece6-4a42-9ded-2157d33e3d21
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6e7b48f96eb09638291b1d0655d385d606b1666
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681188"
---
# <a name="wsfc-cluster-service-is-offline"></a><span data-ttu-id="417bf-102">O serviço de cluster WSFC está offline</span><span class="sxs-lookup"><span data-stu-id="417bf-102">WSFC cluster service is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="417bf-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="417bf-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="417bf-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="417bf-104">**Policy Name**</span></span>|<span data-ttu-id="417bf-105">Estado do cluster WSFC</span><span class="sxs-lookup"><span data-stu-id="417bf-105">WSFC Cluster State</span></span>|  
|<span data-ttu-id="417bf-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="417bf-106">**Issue**</span></span>|<span data-ttu-id="417bf-107">O serviço de cluster WSFC está offline.</span><span class="sxs-lookup"><span data-stu-id="417bf-107">WSFC cluster service is offline.</span></span>|  
|<span data-ttu-id="417bf-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="417bf-108">**Category**</span></span>|<span data-ttu-id="417bf-109">**Crítico**</span><span class="sxs-lookup"><span data-stu-id="417bf-109">**Critical**</span></span>|  
|<span data-ttu-id="417bf-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="417bf-110">**Facet**</span></span>|<span data-ttu-id="417bf-111">Instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="417bf-111">Instance of SQL Server</span></span>|  
  
## <a name="description"></a><span data-ttu-id="417bf-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="417bf-112">Description</span></span>  
 <span data-ttu-id="417bf-113">Esta política verifica o estado do WSFC (Cluster de failover de Windows Server).</span><span class="sxs-lookup"><span data-stu-id="417bf-113">This policy checks the state of the Windows Server Failover Cluster (WSFC).</span></span> <span data-ttu-id="417bf-114">O estado da política é não íntegro e um alerta é gerado quando o cluster WSFC está offline ou no estado de quorum forçado.</span><span class="sxs-lookup"><span data-stu-id="417bf-114">The policy is in an unhealthy state and an alert is raised when the WSFC cluster is offline or in the forced quorum state.</span></span> <span data-ttu-id="417bf-115">Todos os grupos de disponibilidade dentro deste cluster estão offline ou uma ação de recuperação de desastres é necessária.</span><span class="sxs-lookup"><span data-stu-id="417bf-115">All availability groups hosted within this cluster are offline or a disaster recovery action is required.</span></span>  
  
 <span data-ttu-id="417bf-116">O estado da política é íntegro quando o estado do cluster está no quorum normal.</span><span class="sxs-lookup"><span data-stu-id="417bf-116">The policy state is healthy when the cluster state is in the normal quorum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="417bf-117">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre as possíveis causas e soluções estão localizadas em [O serviço de cluster WSFC está offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) no Wiki do TechNet.</span><span class="sxs-lookup"><span data-stu-id="417bf-117">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [WSFC cluster service is offline](https://go.microsoft.com/fwlink/p/?LinkId=220849) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="417bf-118">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="417bf-118">Possible Causes</span></span>  
 <span data-ttu-id="417bf-119">A causa desse problema pode ser um problema de serviço de cluster ou a perda do quorum no cluster.</span><span class="sxs-lookup"><span data-stu-id="417bf-119">This issue can be caused by a cluster service issue or by the loss of the quorum in the cluster.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="417bf-120">Solução possível</span><span class="sxs-lookup"><span data-stu-id="417bf-120">Possible Solution</span></span>  
 <span data-ttu-id="417bf-121">Use a ferramenta de Administrador de Cluster para executar o quorum forçado ou o fluxo de trabalho de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="417bf-121">Use the Cluster Administrator tool to perform the forced quorum or disaster recovery workflow.</span></span> <span data-ttu-id="417bf-122">Se você não conseguir resolver o problema executando o quorum forçado ou a recuperação de desastres, contate o administrador de cluster para ajudar a resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="417bf-122">If you cannot resolve the issue by performing the forced quorum or disaster recovery, contact your cluster administrator to help resolve this issue.</span></span> <span data-ttu-id="417bf-123">Para obter mais informações, veja [Forçar um cluster WSFC a iniciar sem um quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="417bf-123">For more information, see [Force a WSFC Cluster to Start Without a Quorum](../../../sql-server/failover-clusters/windows/force-a-wsfc-cluster-to-start-without-a-quorum.md) in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="417bf-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="417bf-124">See Also</span></span>  
 <span data-ttu-id="417bf-125">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="417bf-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="417bf-126">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="417bf-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
