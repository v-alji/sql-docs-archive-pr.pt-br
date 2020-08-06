---
title: O grupo de disponibilidade não está pronto para o failover automático | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp3autofailover.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 28261014-342c-442a-bd89-6d04b8d4e8b7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2995ddec51cd70d8a3f209229d0ecb9b0132c79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569677"
---
# <a name="availability-group-is-not-ready-for-automatic-failover"></a><span data-ttu-id="e1b26-102">O grupo de disponibilidade não está pronto para o failover automático</span><span class="sxs-lookup"><span data-stu-id="e1b26-102">Availability group is not ready for automatic failover</span></span>
    
## <a name="introduction"></a><span data-ttu-id="e1b26-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="e1b26-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1b26-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="e1b26-104">**Policy Name**</span></span>|<span data-ttu-id="e1b26-105">Prontidão para Failover Automático do Grupo de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="e1b26-105">Availability Group Automatic Failover Readiness</span></span>|  
|<span data-ttu-id="e1b26-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="e1b26-106">**Issue**</span></span>|<span data-ttu-id="e1b26-107">O grupo de disponibilidade não está pronto para o failover automático.</span><span class="sxs-lookup"><span data-stu-id="e1b26-107">Availability group is not ready for automatic failover.</span></span>|  
|<span data-ttu-id="e1b26-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="e1b26-108">**Category**</span></span>|<span data-ttu-id="e1b26-109">**Crítico**</span><span class="sxs-lookup"><span data-stu-id="e1b26-109">**Critical**</span></span>|  
|<span data-ttu-id="e1b26-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="e1b26-110">**Facet**</span></span>|<span data-ttu-id="e1b26-111">grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="e1b26-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1b26-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e1b26-112">Description</span></span>  
 <span data-ttu-id="e1b26-113">Esta política verifica se o grupo de disponibilidade tem ao menos uma réplica secundária pronta para failover.</span><span class="sxs-lookup"><span data-stu-id="e1b26-113">This policy checks to verify that the availability group has at least one secondary replica that is failover ready.</span></span> <span data-ttu-id="e1b26-114">A política estará em estado não íntegro e um alerta será emitido quando o modo de failover da réplica primária for automático, mas nenhuma das réplicas secundárias do grupo de disponibilidade está pronta para failover.</span><span class="sxs-lookup"><span data-stu-id="e1b26-114">The policy is in an unhealthy state and an alert is raised when the failover mode of the primary replica is automatic, however none of the secondary replicas in the availability group are failover ready.</span></span>  
  
 <span data-ttu-id="e1b26-115">A política estará em estado íntegro quando pelo menos uma réplica secundária estiver pronta para failover automático.</span><span class="sxs-lookup"><span data-stu-id="e1b26-115">The policy is in a healthy state when at least one secondary replica is automatic failover ready.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1b26-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre as possíveis causas e soluções estão localizadas em [O grupo de disponibilidade não está pronto para failover automático](https://go.microsoft.com/fwlink/p/?LinkId=220851) no Wiki do TechNet.</span><span class="sxs-lookup"><span data-stu-id="e1b26-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is not ready for automatic failover](https://go.microsoft.com/fwlink/p/?LinkId=220851) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="e1b26-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="e1b26-117">Possible Causes</span></span>  
 <span data-ttu-id="e1b26-118">O grupo de disponibilidade não está pronto para o failover automático.</span><span class="sxs-lookup"><span data-stu-id="e1b26-118">The availability group is not ready for automatic failover.</span></span> <span data-ttu-id="e1b26-119">A réplica primária está configurada para failover automático; porém, a réplica secundária não está pronta para failover automático.</span><span class="sxs-lookup"><span data-stu-id="e1b26-119">The primary replica is configured for automatic failover; however, the secondary replica is not ready for automatic failover.</span></span> <span data-ttu-id="e1b26-120">A réplica secundária que está configurada para failover automático pode estar indisponível ou seu estado de sincronização de dados não é atualmente SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="e1b26-120">The secondary replica that is configured for automatic failover might be unavailable or its data synchronization state is currently not SYNCHRONIZED.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="e1b26-121">Soluções possíveis</span><span class="sxs-lookup"><span data-stu-id="e1b26-121">Possible Solutions</span></span>  
 <span data-ttu-id="e1b26-122">Estas são as possíveis soluções para este problema:</span><span class="sxs-lookup"><span data-stu-id="e1b26-122">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="e1b26-123">Verifique se pelo menos uma réplica secundária está configurada como failover automático.</span><span class="sxs-lookup"><span data-stu-id="e1b26-123">Verify that at least one secondary replica is configured as automatic failover.</span></span> <span data-ttu-id="e1b26-124">Se não houver uma réplica secundária configurada como failover automático, atualize a configuração de uma réplica secundária para ser o destino de failover automático com confirmação síncrona.</span><span class="sxs-lookup"><span data-stu-id="e1b26-124">If there is not a secondary replica configured as automatic failover, update the configuration of a secondary replica to be the automatic failover target with synchronous commit.</span></span>  
  
-   <span data-ttu-id="e1b26-125">Use a política para verificar se os dados estão em estado de sincronização e se o destino de failover automático é SYNCHRONIZED, e depois resolva o problema na réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e1b26-125">Use the policy to verify that the data is in a synchronization state and the automatic failover target is SYNCHRONIZED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b26-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1b26-126">See Also</span></span>  
 <span data-ttu-id="e1b26-127">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e1b26-127">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="e1b26-128">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e1b26-128">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
