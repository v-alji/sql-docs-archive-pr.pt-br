---
title: A réplica de disponibilidade não está ingressada | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp4joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 9c0d10b1-9e12-430c-83b9-ca2bd0a3afc4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7c4f76e98d373e50124f5ca2b135a9fad8f34226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681192"
---
# <a name="availability-replica-is-not-joined"></a><span data-ttu-id="07835-102">A réplica de disponibilidade não está unida</span><span class="sxs-lookup"><span data-stu-id="07835-102">Availability replica is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="07835-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="07835-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07835-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="07835-104">**Policy Name**</span></span>|<span data-ttu-id="07835-105">Estado da junção da réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="07835-105">Availability Replica Join State</span></span>|  
|<span data-ttu-id="07835-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="07835-106">**Issue**</span></span>|<span data-ttu-id="07835-107">A réplica de disponibilidade não está unida.</span><span class="sxs-lookup"><span data-stu-id="07835-107">Availability Replica is not joined.</span></span>|  
|<span data-ttu-id="07835-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="07835-108">**Category**</span></span>|<span data-ttu-id="07835-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="07835-109">**Warning**</span></span>|  
|<span data-ttu-id="07835-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="07835-110">**Facet**</span></span>|<span data-ttu-id="07835-111">Réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="07835-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07835-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="07835-112">Description</span></span>  
 <span data-ttu-id="07835-113">Esta política verifica o estado da junção da réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="07835-113">This policy checks the join state of the availability replica.</span></span> <span data-ttu-id="07835-114">A política estará em um estado não íntegro quando a réplica de disponibilidade for adicionada ao grupo de disponibilidade, mas não for unida corretamente.</span><span class="sxs-lookup"><span data-stu-id="07835-114">The policy is in an unhealthy state when the availability replica is added to the availability group, but is not joined properly.</span></span> <span data-ttu-id="07835-115">Caso contrário, a política estará em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="07835-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07835-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre as possíveis causas e soluções estão localizadas em [A réplica de disponibilidade não está unida](https://go.microsoft.com/fwlink/p/?LinkId=220859) no Wiki do TechNet.</span><span class="sxs-lookup"><span data-stu-id="07835-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220859) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="07835-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="07835-117">Possible Causes</span></span>  
 <span data-ttu-id="07835-118">A réplica secundária não está unida ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="07835-118">The secondary replica is not joined to the availability group.</span></span> <span data-ttu-id="07835-119">Para que uma réplica de disponibilidade seja unida com êxito ao grupo de disponibilidade, o estado da junção deve ser Instância Autônoma Unida (1) ou Cluster de Failover Unido (2).</span><span class="sxs-lookup"><span data-stu-id="07835-119">For an availability replica to be successfully joined to the availability group, the join state must be Joined Standalone Instance (1) or Joined Failover Cluster (2).</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="07835-120">Solução possível</span><span class="sxs-lookup"><span data-stu-id="07835-120">Possible Solution</span></span>  
 <span data-ttu-id="07835-121">Use o Transact-SQL, o PowerShell ou o SQL Server Management Studio para unir a réplica secundária ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="07835-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="07835-122">Para obter mais informações sobre como unir réplicas secundárias a grupos de disponibilidade, consulte [Unir uma réplica secundária a um grupo de disponibilidade (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="07835-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07835-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="07835-123">See Also</span></span>  
 <span data-ttu-id="07835-124">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="07835-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="07835-125">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="07835-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
