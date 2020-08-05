---
title: Algumas réplicas de disponibilidade estão desconectadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp7allconnected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: aea808be-6f0f-40c2-9aa2-a2a435ec6443
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1bb6535b513770b9b4718a0e8372c0a5bc3cba84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574290"
---
# <a name="some-availability-replicas-are-disconnected"></a><span data-ttu-id="9ae89-102">Algumas réplicas de disponibilidade são desconectadas</span><span class="sxs-lookup"><span data-stu-id="9ae89-102">Some availability replicas are disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="9ae89-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="9ae89-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ae89-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="9ae89-104">**Policy Name**</span></span>|<span data-ttu-id="9ae89-105">Estado da conexão em réplicas de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="9ae89-105">Availability Replicas Connection State</span></span>|  
|<span data-ttu-id="9ae89-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="9ae89-106">**Issue**</span></span>|<span data-ttu-id="9ae89-107">Algumas réplicas de disponibilidade estão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="9ae89-107">Some availability replicas are disconnected.</span></span>|  
|<span data-ttu-id="9ae89-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="9ae89-108">**Category**</span></span>|<span data-ttu-id="9ae89-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="9ae89-109">**Warning**</span></span>|  
|<span data-ttu-id="9ae89-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="9ae89-110">**Facet**</span></span>|<span data-ttu-id="9ae89-111">grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="9ae89-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9ae89-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9ae89-112">Description</span></span>  
 <span data-ttu-id="9ae89-113">Essa política acumula o estado de conexão de todas as réplicas de disponibilidade e verifica se há alguma réplica DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="9ae89-113">This policy rolls up the connection state of all availability replicas and checks for any availability replicas that are DISCONENCTED.</span></span> <span data-ttu-id="9ae89-114">O estado da política é não íntegro quando qualquer réplica de disponibilidade é DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="9ae89-114">The policy is in an unhealthy state when any availability replica is DISCONNECTED.</span></span> <span data-ttu-id="9ae89-115">Caso contrário, a política estará em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="9ae89-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ae89-116"> Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre possíveis causas e soluções estão localizadas em [Algumas réplicas de disponibilidade são desconectadas](https://go.microsoft.com/fwlink/p/?LinkId=220855) no TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="9ae89-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220855) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="9ae89-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="9ae89-117">Possible Causes</span></span>  
 <span data-ttu-id="9ae89-118">Nesse grupo de disponibilidade, pelo menos uma réplica secundária não está conectada à réplica primária.</span><span class="sxs-lookup"><span data-stu-id="9ae89-118">In this availability group, at least one secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="9ae89-119">O estado de conexão é DISCONNECTED.</span><span class="sxs-lookup"><span data-stu-id="9ae89-119">The connected state is DISCONNECTED.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="9ae89-120">Solução possível</span><span class="sxs-lookup"><span data-stu-id="9ae89-120">Possible Solution</span></span>  
 <span data-ttu-id="9ae89-121">Use o estado da política de réplica de disponibilidade para localizar a réplica de disponibilidade que é DISCONNECTED; depois, resolva o problema na réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="9ae89-121">Use the availability replica policy state to find the availability replica that is DISCONNECTED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae89-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9ae89-122">See Also</span></span>  
 <span data-ttu-id="9ae89-123">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ae89-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="9ae89-124">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9ae89-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
