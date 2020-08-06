---
title: O banco de dados secundário não está ingressado | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp2joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 10817e5e-75fa-42dd-baa2-359bea3ad051
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81275e85fd865924778f6d6f985e170a5bda9f9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684911"
---
# <a name="secondary-database-is-not-joined"></a><span data-ttu-id="e0165-102">O banco de dados secundário não está unido</span><span class="sxs-lookup"><span data-stu-id="e0165-102">Secondary database is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="e0165-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="e0165-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0165-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="e0165-104">**Policy Name**</span></span>|<span data-ttu-id="e0165-105">Estado de junção do banco de dados de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="e0165-105">Availability Database Join State</span></span>|  
|<span data-ttu-id="e0165-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="e0165-106">**Issue**</span></span>|<span data-ttu-id="e0165-107">O banco de dados secundário não está unido.</span><span class="sxs-lookup"><span data-stu-id="e0165-107">Secondary database is not joined.</span></span>|  
|<span data-ttu-id="e0165-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="e0165-108">**Category**</span></span>|<span data-ttu-id="e0165-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="e0165-109">**Warning**</span></span>|  
|<span data-ttu-id="e0165-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="e0165-110">**Facet**</span></span>|<span data-ttu-id="e0165-111">Banco de dados de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="e0165-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0165-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0165-112">Description</span></span>  
 <span data-ttu-id="e0165-113">Esta política verifica o estado de junção do banco de dados secundário (também conhecido como "réplica de banco de dados secundário").</span><span class="sxs-lookup"><span data-stu-id="e0165-113">This policy checks the join state of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="e0165-114">A política ficará em estado não íntegro quando a réplica do conjunto de dados não estiver unida.</span><span class="sxs-lookup"><span data-stu-id="e0165-114">The policy is in an unhealthy state when the dataset replica is not joined.</span></span> <span data-ttu-id="e0165-115">Caso contrário, a política estará em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="e0165-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0165-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre possíveis causas e soluções estão localizadas em [Secondary database is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220862) (O banco de dados secundário não está unido) no TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="e0165-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Secondary database is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220862) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="e0165-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="e0165-117">Possible Causes</span></span>  
 <span data-ttu-id="e0165-118">Este banco de dados secundário não está unido ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e0165-118">This secondary database is not joined to the availability group.</span></span> <span data-ttu-id="e0165-119">A configuração deste banco de dados secundário está incompleta.</span><span class="sxs-lookup"><span data-stu-id="e0165-119">The configuration of this secondary database is incomplete.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="e0165-120">Solução possível</span><span class="sxs-lookup"><span data-stu-id="e0165-120">Possible Solution</span></span>  
 <span data-ttu-id="e0165-121">Use o Transact-SQL, o PowerShell ou o SQL Server Management Studio para unir a réplica secundária ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e0165-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="e0165-122">Para obter mais informações sobre como unir réplicas secundárias a grupos de disponibilidade, consulte [Unir uma réplica secundária a um grupo de disponibilidade (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="e0165-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0165-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e0165-123">See Also</span></span>  
 <span data-ttu-id="e0165-124">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e0165-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="e0165-125">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e0165-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
