---
title: Algumas réplicas de disponibilidade não têm uma função íntegra | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp6allroleshealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 7ec5b337-7201-4a66-a541-7560f8b18784
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 801fe20edf6f2dbe09bc800722cf4210988ebc69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574286"
---
# <a name="some-availability-replicas-do-not-have-a-healthy-role"></a><span data-ttu-id="61add-102">Algumas réplicas de disponibilidade não têm uma função íntegra</span><span class="sxs-lookup"><span data-stu-id="61add-102">Some availability replicas do not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="61add-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="61add-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="61add-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="61add-104">**Policy Name**</span></span>|<span data-ttu-id="61add-105">Estado da Função das Réplica de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="61add-105">Availability Replicas Role State</span></span>|  
|<span data-ttu-id="61add-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="61add-106">**Issue**</span></span>|<span data-ttu-id="61add-107">Algumas réplicas de disponibilidade não têm uma função íntegra.</span><span class="sxs-lookup"><span data-stu-id="61add-107">Some availability replicas do not have a healthy role.</span></span>|  
|<span data-ttu-id="61add-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="61add-108">**Category**</span></span>|<span data-ttu-id="61add-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="61add-109">**Warning**</span></span>|  
|<span data-ttu-id="61add-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="61add-110">**Facet**</span></span>|<span data-ttu-id="61add-111">grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="61add-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="61add-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="61add-112">Description</span></span>  
 <span data-ttu-id="61add-113">Essa política acumula o estado de conexão de todas as réplicas de disponibilidade no grupo de disponibilidade e verifica se há alguma réplica de disponibilidade que não está em estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="61add-113">This policy rolls up the connection state of all availability replicas and checks if there are any availability replicas that are not in a healthy role.</span></span> <span data-ttu-id="61add-114">A política fica em um estado não íntegro quando alguma réplica de disponibilidade não é primária nem secundária.</span><span class="sxs-lookup"><span data-stu-id="61add-114">The policy is in an unhealthy state when any availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="61add-115">Caso contrário, a política estará em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="61add-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61add-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre as possíveis causas e soluções estão localizadas em [Algumas réplicas de disponibilidade não têm uma função íntegra](https://go.microsoft.com/fwlink/p/?LinkId=220854) no Wiki do TechNet.</span><span class="sxs-lookup"><span data-stu-id="61add-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas do not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220854) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="61add-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="61add-117">Possible Causes</span></span>  
 <span data-ttu-id="61add-118">Nesse grupo de disponibilidade, pelo menos uma réplica de disponibilidade não tem a função primária ou secundária atualmente.</span><span class="sxs-lookup"><span data-stu-id="61add-118">In this availability group, at least one availability replica does not currently have the primary or secondary role.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="61add-119">Solução possível</span><span class="sxs-lookup"><span data-stu-id="61add-119">Possible Solution</span></span>  
 <span data-ttu-id="61add-120">Use o estado da política de réplica de disponibilidade para localizar a réplica de disponibilidade cuja função não é primária ou secundária e depois resolva o problema na réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="61add-120">Use the availability replica policy state to find the availability replica whose role is not primary or secondary, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61add-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61add-121">See Also</span></span>  
 <span data-ttu-id="61add-122">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="61add-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="61add-123">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="61add-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
