---
title: Algumas réplicas de disponibilidade não estão sincronizando dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp4synchronizing.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 3db6a569-e942-4321-a0dd-c4ab002087c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 762b7da1f7b8a07257c2a900307eb1bb10408653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574287"
---
# <a name="some-availability-replicas-are-not-synchronizing-data"></a><span data-ttu-id="94ea1-102">Algumas réplicas de disponibilidade não estão sincronizando dados</span><span class="sxs-lookup"><span data-stu-id="94ea1-102">Some availability replicas are not synchronizing data</span></span>
    
## <a name="introduction"></a><span data-ttu-id="94ea1-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="94ea1-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="94ea1-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="94ea1-104">**Policy Name**</span></span>|<span data-ttu-id="94ea1-105">Estado de Sincronização de Dados de Réplicas de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="94ea1-105">Availability Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="94ea1-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="94ea1-106">**Issue**</span></span>|<span data-ttu-id="94ea1-107">Algumas réplicas de disponibilidade não estão sincronizando dados.</span><span class="sxs-lookup"><span data-stu-id="94ea1-107">Some availability replicas are not synchronizing data.</span></span>|  
|<span data-ttu-id="94ea1-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="94ea1-108">**Category**</span></span>|<span data-ttu-id="94ea1-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="94ea1-109">**Warning**</span></span>|  
|<span data-ttu-id="94ea1-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="94ea1-110">**Facet**</span></span>|<span data-ttu-id="94ea1-111">grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="94ea1-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="94ea1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="94ea1-112">Description</span></span>  
 <span data-ttu-id="94ea1-113">Essa política acumula o estado de sincronização de dados de todas as réplicas de disponibilidade no grupo de disponibilidade e verifica se a sincronização de alguma réplica de disponibilidade não está funcionando.</span><span class="sxs-lookup"><span data-stu-id="94ea1-113">This policy rolls up the data synchronization state of all availability replicas in the availability group and checks if the synchronization of any availability replica is not operational.</span></span> <span data-ttu-id="94ea1-114">A política ficará em estado não íntegro se algum estado de sincronização de dados da réplica de disponibilidade for NOT SYNCRONIZING.</span><span class="sxs-lookup"><span data-stu-id="94ea1-114">The policy is in an unhealthy state if any of the data synchronization states of the availability replica is NOT SYNCRONIZING.</span></span>  
  
 <span data-ttu-id="94ea1-115">Essa política ficará em estado íntegro se nenhum estado de sincronização de dados da réplica de disponibilidade for NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="94ea1-115">This policy is in a healthy state if none of the data synchronization states of the availability replica is NOT SYNCHRONIZING.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94ea1-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre possíveis causas e soluções estão localizadas em [Algumas réplicas de disponibilidade não estão sincronizando os dados](https://go.microsoft.com/fwlink/p/?LinkId=220852) no TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="94ea1-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are not synchronizing data](https://go.microsoft.com/fwlink/p/?LinkId=220852) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="94ea1-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="94ea1-117">Possible Causes</span></span>  
 <span data-ttu-id="94ea1-118">Nesse grupo de disponibilidade, pelo menos uma réplica secundária tem um estado de sincronização NOT SYNCHRONIZING e não está recebendo dados da réplica primária.</span><span class="sxs-lookup"><span data-stu-id="94ea1-118">In this availability group, at least one secondary replica has a NOT SYNCHRONIZING synchronization state and is not receiving data from the primary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="94ea1-119">Solução possível</span><span class="sxs-lookup"><span data-stu-id="94ea1-119">Possible Solution</span></span>  
 <span data-ttu-id="94ea1-120">Use o estado da política de réplica de disponibilidade para localizar a réplica de disponibilidade em estado NOT SYNCHROINIZING e depois resolva o problema na réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94ea1-120">Use the availability replica policy state to find the availability replica with a NOT SYNCHROINIZING state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ea1-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94ea1-121">See Also</span></span>  
 <span data-ttu-id="94ea1-122">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="94ea1-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="94ea1-123">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="94ea1-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
