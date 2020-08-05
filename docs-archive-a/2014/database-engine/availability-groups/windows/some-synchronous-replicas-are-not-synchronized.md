---
title: Algumas réplicas síncronas não são sincronizadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp5synchronized.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: e58ed56e-4c30-42e6-a9fc-a8c401620e02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecef2d16e80e128834a71e1f1f112096f8ccc9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574281"
---
# <a name="some-synchronous-replicas-are-not-synchronized"></a><span data-ttu-id="12177-102">Algumas réplicas síncronas não são sincronizadas</span><span class="sxs-lookup"><span data-stu-id="12177-102">Some synchronous replicas are not synchronized</span></span>
    
## <a name="introduction"></a><span data-ttu-id="12177-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="12177-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12177-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="12177-104">**Policy Name**</span></span>|<span data-ttu-id="12177-105">Estado de sincronização de dados de réplicas síncronas</span><span class="sxs-lookup"><span data-stu-id="12177-105">Synchronous Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="12177-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="12177-106">**Issue**</span></span>|<span data-ttu-id="12177-107">Algumas réplicas síncronas não são sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="12177-107">Some synchronous replicas are not synchronized.</span></span>|  
|<span data-ttu-id="12177-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="12177-108">**Category**</span></span>|<span data-ttu-id="12177-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="12177-109">**Warning**</span></span>|  
|<span data-ttu-id="12177-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="12177-110">**Facet**</span></span>|<span data-ttu-id="12177-111">grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="12177-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="12177-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="12177-112">Description</span></span>  
 <span data-ttu-id="12177-113">Essa política acumula o estado de sincronização de dados de todas as réplicas de disponibilidade e verifica se há réplicas de disponibilidade que não estão no estado de sincronização esperado.</span><span class="sxs-lookup"><span data-stu-id="12177-113">This policy rolls up the data synchronization state of all availability replicas and checks for any availability replicas that are not in the expected synchronization state.</span></span> <span data-ttu-id="12177-114">A política está em um estado não íntegro quando o estado de qualquer réplica assíncrona não é SYNCHRONIZING e o estado de qualquer réplica síncrona não é SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="12177-114">The policy is in an unhealthy state when any asynchronous replica is not in a SYNCHRONIZING state and any synchronous replica is not in a SYNCHRONIZED state.</span></span> <span data-ttu-id="12177-115">Caso contrário, o estado da política é íntegro.</span><span class="sxs-lookup"><span data-stu-id="12177-115">The policy state is otherwise healthy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12177-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre as possíveis causas e soluções estão localizadas em [Algumas réplicas síncronas não estão sincronizadas](https://go.microsoft.com/fwlink/p/?LinkId=220853) no Wiki do TechNet.</span><span class="sxs-lookup"><span data-stu-id="12177-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some synchronous replicas are not synchronized](https://go.microsoft.com/fwlink/p/?LinkId=220853) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="12177-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="12177-117">Possible Causes</span></span>  
 <span data-ttu-id="12177-118">Neste grupo de disponibilidade, pelo menos uma réplica síncrona não está sincronizada no momento.</span><span class="sxs-lookup"><span data-stu-id="12177-118">In this availability group, at least one synchronous replica is not currently synchronized.</span></span> <span data-ttu-id="12177-119">O estado de sincronização de réplica pode ser SYNCHONIZING ou NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="12177-119">The replica synchronization state could be either SYNCHONIZING or NOT SYNCHRONIZING.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="12177-120">Solução possível</span><span class="sxs-lookup"><span data-stu-id="12177-120">Possible Solution</span></span>  
 <span data-ttu-id="12177-121">Use o estado da política de réplica de disponibilidade para localizar a réplica de disponibilidade com o estado de sincronização incorreto e, depois, resolva o problema na réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="12177-121">Use the availability replica policy state to find the availability replica with the incorrect synchronization state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12177-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12177-122">See Also</span></span>  
 <span data-ttu-id="12177-123">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="12177-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="12177-124">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="12177-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
