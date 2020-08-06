---
title: O banco de dados de disponibilidade está suspenso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp1notsuspended.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6baee70f-848c-4e86-b20d-78875c0f82cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07a547f217367f13df739348325461c862d831f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569681"
---
# <a name="availability-database-is-suspended"></a><span data-ttu-id="fe731-102">O banco de dados de disponibilidade está suspenso</span><span class="sxs-lookup"><span data-stu-id="fe731-102">Availability database is suspended</span></span>
    
## <a name="introduction"></a><span data-ttu-id="fe731-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="fe731-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe731-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="fe731-104">**Policy Name**</span></span>|<span data-ttu-id="fe731-105">Estado de Suspensão do Banco de Dados de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="fe731-105">Availability Database Suspension State</span></span>|  
|<span data-ttu-id="fe731-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="fe731-106">**Issue**</span></span>|<span data-ttu-id="fe731-107">O banco de dados de disponibilidade está suspenso.</span><span class="sxs-lookup"><span data-stu-id="fe731-107">Availability database is suspended.</span></span>|  
|<span data-ttu-id="fe731-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="fe731-108">**Category**</span></span>|<span data-ttu-id="fe731-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="fe731-109">**Warning**</span></span>|  
|<span data-ttu-id="fe731-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="fe731-110">**Facet**</span></span>|<span data-ttu-id="fe731-111">Banco de dados de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="fe731-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe731-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe731-112">Description</span></span>  
 <span data-ttu-id="fe731-113">Esta política verifica o estado de movimento de dados do banco de dados secundário (também conhecido como "réplica de banco de dados secundário").</span><span class="sxs-lookup"><span data-stu-id="fe731-113">This policy checks the state of data movement of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="fe731-114">A política ficará em estado não íntegro quando a movimentação de dados for suspensa.</span><span class="sxs-lookup"><span data-stu-id="fe731-114">The policy is in an unhealthy state when the data movement is suspended.</span></span> <span data-ttu-id="fe731-115">Caso contrário, a política estará em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="fe731-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe731-116"> Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre possíveis causas e soluções estão localizadas em [Banco de dados de disponibilidade é suspenso](https://go.microsoft.com/fwlink/p/?LinkId=220860) no TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="fe731-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability database is suspended](https://go.microsoft.com/fwlink/p/?LinkId=220860) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="fe731-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="fe731-117">Possible Causes</span></span>  
 <span data-ttu-id="fe731-118">A sincronização de dados nesse banco de dados de disponibilidade pode ter sido suspensa pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="fe731-118">Data synchronization on this availability database might have been suspended because of the following:</span></span>  
  
-   <span data-ttu-id="fe731-119">Devido a um erro, o sistema pode ter suspendido a sincronização de dados.</span><span class="sxs-lookup"><span data-stu-id="fe731-119">Due to an error, the system might have suspended data synchronization.</span></span>  
  
-   <span data-ttu-id="fe731-120">O administrador de banco de dados pode ter suspendido a sincronização de dados para fins de manutenção.</span><span class="sxs-lookup"><span data-stu-id="fe731-120">The database administrator might have suspended data synchronization for maintenance purposes.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="fe731-121">Solução possível</span><span class="sxs-lookup"><span data-stu-id="fe731-121">Possible Solution</span></span>  
 <span data-ttu-id="fe731-122">Retome a sincronização de dados.</span><span class="sxs-lookup"><span data-stu-id="fe731-122">Resume data synchronization.</span></span> <span data-ttu-id="fe731-123">Se o problema persistir, verifique o grupo de disponibilidade no log de eventos e diagnostique por que o sistema suspendeu a movimentação de dados.</span><span class="sxs-lookup"><span data-stu-id="fe731-123">If the issue persists, check the availability group in the Event log, and then diagnose why the system suspended data movement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe731-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe731-124">See Also</span></span>  
 <span data-ttu-id="fe731-125">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe731-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="fe731-126">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="fe731-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
