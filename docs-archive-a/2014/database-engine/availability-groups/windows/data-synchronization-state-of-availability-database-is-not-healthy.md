---
title: O estado de sincronização de dados do banco de dados de disponibilidade não está íntegro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 4fd003e7-808e-4b0e-b28a-47d9f2616f06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a179008c20b108a2f6aaefd5dd80b22708e94a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686369"
---
# <a name="data-synchronization-state-of-availability-database-is-not-healthy"></a><span data-ttu-id="38af4-102">O estado de sincronização de dados do banco de dados de disponibilidade não é íntegro</span><span class="sxs-lookup"><span data-stu-id="38af4-102">Data synchronization state of availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="38af4-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="38af4-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38af4-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="38af4-104">**Policy Name**</span></span>|<span data-ttu-id="38af4-105">Estado de Sincronização dos Dados do Banco de Dados de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="38af4-105">Availability Database Data Synchronization State</span></span>|  
|<span data-ttu-id="38af4-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="38af4-106">**Issue**</span></span>|<span data-ttu-id="38af4-107">O estado de sincronização de dados do banco de dados de disponibilidade não é íntegro.</span><span class="sxs-lookup"><span data-stu-id="38af4-107">Data synchronization state of availability database is not healthy.</span></span>|  
|<span data-ttu-id="38af4-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="38af4-108">**Category**</span></span>|<span data-ttu-id="38af4-109">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="38af4-109">**Warning**</span></span>|  
|<span data-ttu-id="38af4-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="38af4-110">**Facet**</span></span>|<span data-ttu-id="38af4-111">Banco de dados de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="38af4-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="38af4-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="38af4-112">Description</span></span>  
 <span data-ttu-id="38af4-113">Esta política acumula o estado de sincronização de dados de todos os bancos de dados de disponibilidade (também chamados de "réplicas de banco de dados") na réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="38af4-113">This policy rolls up the data synchronization state of all availability databases (also known as "database replicas") in the availability replica.</span></span> <span data-ttu-id="38af4-114">A política estará em estado não íntegro quando alguma réplica de banco de dados não estiver no estado de sincronização de dados esperado.</span><span class="sxs-lookup"><span data-stu-id="38af4-114">The policy is in an unhealthy sate when any database replica is not in the expected data synchronization state.</span></span> <span data-ttu-id="38af4-115">Caso contrário, a política estará em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="38af4-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38af4-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre possíveis causas e soluções estão localizadas em [O estado de sincronização de dados de algum banco de dados de disponibilidade não é íntegro](https://go.microsoft.com/fwlink/p/?LinkId=220858) no TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="38af4-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of some availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220858) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="38af4-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="38af4-117">Possible Causes</span></span>  
 <span data-ttu-id="38af4-118">O estado de sincronização de dados deste banco de dados de disponibilidade não é íntegro.</span><span class="sxs-lookup"><span data-stu-id="38af4-118">The data synchronization state of this availability database is unhealthy.</span></span> <span data-ttu-id="38af4-119">Em uma réplica de disponibilidade de confirmação de transação, todos os bancos de dados de disponibilidade devem estar no estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="38af4-119">On an asynchronous-commit availability replica, every availability database should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="38af4-120">Em uma réplica de disponibilidade da confirmação síncrona, todo banco de dados de disponibilidade deve estar no estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="38af4-120">On a synchronous-commit replica, every availability database must be in the SYNCHRONIZED state.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="38af4-121">Solução possível</span><span class="sxs-lookup"><span data-stu-id="38af4-121">Possible Solution</span></span>  
 <span data-ttu-id="38af4-122">Use a política de réplica de banco de dados para localizar a réplica de banco de dados em estado de sincronização de dados não íntegro e depois resolva o problema na réplica de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="38af4-122">Use the database replica policy to find the database replica with an unhealthy data synchronization state, and then resolve the issue at the database replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38af4-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38af4-123">See Also</span></span>  
 <span data-ttu-id="38af4-124">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38af4-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="38af4-125">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="38af4-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
