---
title: A réplica de disponibilidade não tem uma função íntegra | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp1rolehealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: ebb2c9f4-2097-4688-b4fb-8f0571047317
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7be26945903a5e3b602ef4a99c269de6a58b04a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681196"
---
# <a name="availability-replica-does-not-have-a-healthy-role"></a><span data-ttu-id="7338a-102">A réplica de disponibilidade não têm uma função íntegra</span><span class="sxs-lookup"><span data-stu-id="7338a-102">Availability replica does not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="7338a-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="7338a-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7338a-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="7338a-104">**Policy Name**</span></span>|<span data-ttu-id="7338a-105">Estado da função da réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="7338a-105">Availability Replica Role State</span></span>|  
|<span data-ttu-id="7338a-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="7338a-106">**Issue**</span></span>|<span data-ttu-id="7338a-107">A réplica de disponibilidade não tem uma função íntegra.</span><span class="sxs-lookup"><span data-stu-id="7338a-107">Availability replica does not have a healthy role.</span></span>|  
|<span data-ttu-id="7338a-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="7338a-108">**Category**</span></span>|<span data-ttu-id="7338a-109">**Crítico**</span><span class="sxs-lookup"><span data-stu-id="7338a-109">**Critical**</span></span>|  
|<span data-ttu-id="7338a-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="7338a-110">**Facet**</span></span>|<span data-ttu-id="7338a-111">Réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="7338a-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7338a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7338a-112">Description</span></span>  
 <span data-ttu-id="7338a-113">Esta política verifica o estado da função da réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7338a-113">This policy checks the state of the role of the availability replica.</span></span> <span data-ttu-id="7338a-114">O estado da política é não íntegro quando a função da réplica de disponibilidade não é primária nem secundária.</span><span class="sxs-lookup"><span data-stu-id="7338a-114">The policy is in an unhealthy state when the role of the availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="7338a-115">Caso contrário, a política estará em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="7338a-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7338a-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre as possíveis causas e soluções estão localizadas em [A réplica de disponibilidade não tem uma função íntegra](https://go.microsoft.com/fwlink/p/?LinkId=220856) no Wiki do TechNet.</span><span class="sxs-lookup"><span data-stu-id="7338a-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica does not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220856) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="7338a-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="7338a-117">Possible Causes</span></span>  
 <span data-ttu-id="7338a-118">A função desta réplica de disponibilidade é não íntegra.</span><span class="sxs-lookup"><span data-stu-id="7338a-118">The role of this availability replica is unhealthy.</span></span> <span data-ttu-id="7338a-119">A réplica não tem a função primária ou secundária.</span><span class="sxs-lookup"><span data-stu-id="7338a-119">The replica does not have either the primary or secondary role.</span></span>  
  
## <a name="possible-solution-information_still_to_come"></a><span data-ttu-id="7338a-120">Solução possível: Information_still_to_come</span><span class="sxs-lookup"><span data-stu-id="7338a-120">Possible Solution: Information_still_to_come</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7338a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7338a-121">See Also</span></span>  
 <span data-ttu-id="7338a-122">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7338a-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="7338a-123">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7338a-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
