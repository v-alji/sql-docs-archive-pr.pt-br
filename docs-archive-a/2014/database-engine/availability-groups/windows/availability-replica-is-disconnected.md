---
title: A réplica de disponibilidade está desconectada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp2connected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 1a2162d3-54fb-4356-b349-effbdc15a5a4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1db92b8e73b6daaee7edf5042b1d73cfeb471d1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681193"
---
# <a name="availability-replica-is-disconnected"></a><span data-ttu-id="7031c-102">A réplica de disponibilidade está desconectada</span><span class="sxs-lookup"><span data-stu-id="7031c-102">Availability replica is disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="7031c-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="7031c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7031c-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="7031c-104">**Policy Name**</span></span>|<span data-ttu-id="7031c-105">Estado da Conexão da Réplica de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="7031c-105">Availability Replica Connection State</span></span>|  
|<span data-ttu-id="7031c-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="7031c-106">**Issue**</span></span>|<span data-ttu-id="7031c-107">A réplica de disponibilidade está desconectada.</span><span class="sxs-lookup"><span data-stu-id="7031c-107">Availability replica is disconnected.</span></span>|  
|<span data-ttu-id="7031c-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="7031c-108">**Category**</span></span>|<span data-ttu-id="7031c-109">**Crítico**</span><span class="sxs-lookup"><span data-stu-id="7031c-109">**Critical**</span></span>|  
|<span data-ttu-id="7031c-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="7031c-110">**Facet**</span></span>|<span data-ttu-id="7031c-111">Réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="7031c-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7031c-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7031c-112">Description</span></span>  
 <span data-ttu-id="7031c-113">Esta política verifica o estado da conexão entre as réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7031c-113">This policy checks the connection state between availability replicas.</span></span> <span data-ttu-id="7031c-114">O estado da política é não íntegro quando o estado de conexão da réplica de disponibilidade é DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="7031c-114">The policy is in an unhealthy state when the connection state of the availability replica is DISCONNECTED.</span></span> <span data-ttu-id="7031c-115">Caso contrário, a política estará em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="7031c-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7031c-116"> Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre possíveis causas e soluções estão localizadas em [Availability replica is disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220857) no TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="7031c-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220857) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="7031c-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="7031c-117">Possible Causes</span></span>  
 <span data-ttu-id="7031c-118">A réplica secundária não está conectada à réplica primária.</span><span class="sxs-lookup"><span data-stu-id="7031c-118">The secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="7031c-119">O estado de conexão é DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="7031c-119">The connected state is DISCONNECTED.</span></span> <span data-ttu-id="7031c-120">Esse problema pode ter sido causado pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="7031c-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="7031c-121">A porta de conexão pode estar em conflito com outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7031c-121">The connection port might be in conflict with another application.</span></span>  
  
-   <span data-ttu-id="7031c-122">O tipo de criptografia ou algoritmo é incompatível.</span><span class="sxs-lookup"><span data-stu-id="7031c-122">The encryption type or algorithm is mismatched.</span></span>  
  
-   <span data-ttu-id="7031c-123">O ponto de extremidade de conexão foi excluído ou não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="7031c-123">The connection endpoint has been deleted or has not been started.</span></span>  
  
-   <span data-ttu-id="7031c-124">O transporte está desconectado.</span><span class="sxs-lookup"><span data-stu-id="7031c-124">The transport is disconnected.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="7031c-125">Soluções possíveis</span><span class="sxs-lookup"><span data-stu-id="7031c-125">Possible Solutions</span></span>  
 <span data-ttu-id="7031c-126">Estas são as possíveis soluções para este problema:</span><span class="sxs-lookup"><span data-stu-id="7031c-126">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="7031c-127">Verifique a configuração de ponto de extremidade de espelhamento de banco de dados para as instâncias da réplica primária e secundária e atualize a configuração incompatível.</span><span class="sxs-lookup"><span data-stu-id="7031c-127">Check the database mirroring endpoint configuration for the instances of the primary and secondary replica and update the mismatched configuration.</span></span>  
  
-   <span data-ttu-id="7031c-128">Verifique se a porta está em conflito, e se estiver, altere o número da porta.</span><span class="sxs-lookup"><span data-stu-id="7031c-128">Check if the port is conflicting, and if so, change the port number.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7031c-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7031c-129">See Also</span></span>  
 <span data-ttu-id="7031c-130">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7031c-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="7031c-131">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7031c-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
