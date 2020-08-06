---
title: O estado de sincronização de dados de um banco de dados de disponibilidade não está íntegro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 89f95d15-33c6-4768-bccd-9dbf8c4f49a9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 221f25a1ee7e4a8719acc133372c742ca4a79303
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686364"
---
# <a name="data-synchronization-state-of-some-availability-database-is-not-healthy"></a><span data-ttu-id="257db-102">O estado de sincronização de dados de algum banco de dados de disponibilidade não é íntegro</span><span class="sxs-lookup"><span data-stu-id="257db-102">Data synchronization state of some availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="257db-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="257db-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="257db-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="257db-104">**Policy Name**</span></span>|<span data-ttu-id="257db-105">Estado de Sincronização de Dados de Réplicas de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="257db-105">Availability Replica Data Synchronization State</span></span>|  
|<span data-ttu-id="257db-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="257db-106">**Issue**</span></span>|<span data-ttu-id="257db-107">O estado de sincronização de dados de algum banco de dados de disponibilidade não é íntegro.</span><span class="sxs-lookup"><span data-stu-id="257db-107">Data synchronization state of some availability database is not healthy.</span></span>|  
|<span data-ttu-id="257db-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="257db-108">**Category**</span></span>|<span data-ttu-id="257db-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="257db-109">**Warning**</span></span>|  
|<span data-ttu-id="257db-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="257db-110">**Facet**</span></span>|<span data-ttu-id="257db-111">Réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="257db-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="257db-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="257db-112">Description</span></span>  
 <span data-ttu-id="257db-113">Esta política verifica o estado de sincronização de dados do banco de dados de disponibilidade (também conhecido como "réplica de banco de dados").</span><span class="sxs-lookup"><span data-stu-id="257db-113">This policy checks the data synchronization state of the availability database (also known as a "database replica").</span></span> <span data-ttu-id="257db-114">A política está em um estado não íntegro quando o estado de sincronização dos dados é NOT SYNCHRONIZING ou o estado da réplica de banco de dados de confirmação síncrona não é SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="257db-114">The policy is in an unhealthy state when the data synchronization state is NOT SYNCHRONIZING or the state is not SYNCHRONIZED for the synchronous-commit database replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="257db-115">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre as possíveis causas e soluções estão localizadas em [O estado de sincronização de dados do banco de dados de disponibilidade não é íntegro](https://go.microsoft.com/fwlink/p/?LinkId=220863) no Wiki do TechNet.</span><span class="sxs-lookup"><span data-stu-id="257db-115">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220863) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="257db-116">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="257db-116">Possible Causes</span></span>  
 <span data-ttu-id="257db-117">Pelo menos um banco de dados de disponibilidade na réplica está em estado de sincronização de dados não íntegro.</span><span class="sxs-lookup"><span data-stu-id="257db-117">At least one availability database on the replica has an unhealthy data synchronization state.</span></span> <span data-ttu-id="257db-118">Se essa for uma réplica de disponibilidade de confirmação de sincronização, todos os bancos de dados de disponibilidade devem estar no estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="257db-118">If this is an asynchronous-commit availability replica, all availability databases should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="257db-119">Se for uma réplica de disponibilidade da confirmação síncrona, todos os bancos de dados de disponibilidade deverão estar no estado SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="257db-119">If this is a synchronous-commit availability replica, all availability databases should be in the SYNCHRONIZED state.</span></span> <span data-ttu-id="257db-120">Esse problema pode ter sido causado pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="257db-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="257db-121">A réplica de disponibilidade pode estar desconectada.</span><span class="sxs-lookup"><span data-stu-id="257db-121">The availability replica might be disconnected.</span></span>  
  
-   <span data-ttu-id="257db-122">A movimentação de dados pode estar suspensa.</span><span class="sxs-lookup"><span data-stu-id="257db-122">The data movement might be suspended.</span></span>  
  
-   <span data-ttu-id="257db-123">O banco de dados pode não estar acessível.</span><span class="sxs-lookup"><span data-stu-id="257db-123">The database might not be accessible.</span></span>  
  
-   <span data-ttu-id="257db-124">Pode haver um problema de atraso temporário devido à latência de rede ou à carga na réplica primária ou secundária.</span><span class="sxs-lookup"><span data-stu-id="257db-124">There might be a temporary delay issue due to network latency or the load on the primary or secondary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="257db-125">Solução possível</span><span class="sxs-lookup"><span data-stu-id="257db-125">Possible Solution</span></span>  
 <span data-ttu-id="257db-126">Resolva os problemas de suspensão de conexão ou movimentação de dados.</span><span class="sxs-lookup"><span data-stu-id="257db-126">Resolve any connection or data movement suspend issues.</span></span> <span data-ttu-id="257db-127">Verifique os eventos desse problema usando o SQL Server Management Studio e localize o erro do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="257db-127">Check the events for this issue using SQL Server Management Studio, and find the database error.</span></span> <span data-ttu-id="257db-128">Siga as etapas de solução de problemas do erro específico.</span><span class="sxs-lookup"><span data-stu-id="257db-128">Follow the troubleshooting steps for the specific error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257db-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="257db-129">See Also</span></span>  
 <span data-ttu-id="257db-130">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="257db-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="257db-131">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="257db-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
