---
title: O grupo de disponibilidade está offline | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp2online.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 093c5208-bf7a-49f4-a546-72b48197cadf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b25e5b22a09783c8dfcad862500b5c0dfcb2c319
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569674"
---
# <a name="availability-group-is-offline"></a><span data-ttu-id="39d5d-102">O grupo de disponibilidade está offline</span><span class="sxs-lookup"><span data-stu-id="39d5d-102">Availability group is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="39d5d-103">Introdução</span><span class="sxs-lookup"><span data-stu-id="39d5d-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39d5d-104">**Nome da Política**</span><span class="sxs-lookup"><span data-stu-id="39d5d-104">**Policy Name**</span></span>|<span data-ttu-id="39d5d-105">Estado Online do Grupo de Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="39d5d-105">Availability Group Online State</span></span>|  
|<span data-ttu-id="39d5d-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="39d5d-106">**Issue**</span></span>|<span data-ttu-id="39d5d-107">O grupo de disponibilidade está offline.</span><span class="sxs-lookup"><span data-stu-id="39d5d-107">Availability group is offline.</span></span>|  
|<span data-ttu-id="39d5d-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="39d5d-108">**Category**</span></span>|<span data-ttu-id="39d5d-109">**Crítico**</span><span class="sxs-lookup"><span data-stu-id="39d5d-109">**Critical**</span></span>|  
|<span data-ttu-id="39d5d-110">**Faceta**</span><span class="sxs-lookup"><span data-stu-id="39d5d-110">**Facet**</span></span>|<span data-ttu-id="39d5d-111">grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="39d5d-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="39d5d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="39d5d-112">Description</span></span>  
 <span data-ttu-id="39d5d-113">Esta política verifica o estado online ou offline do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="39d5d-113">This policy checks the online or offline state of the availability group.</span></span> <span data-ttu-id="39d5d-114">A política estará em estado não íntegro e um alerta será emitido quando o recurso de cluster do grupo de disponibilidade estiver offline ou o grupo de disponibilidade não tiver uma réplica primária.</span><span class="sxs-lookup"><span data-stu-id="39d5d-114">The policy is in an unhealthy state and an alert is raised when the cluster resource of the availability group is offline or the availability group does not have a primary replica.</span></span>  
  
 <span data-ttu-id="39d5d-115">O estado da política será íntegro quando o recurso de cluster do grupo de disponibilidade estiver online e o grupo de disponibilidade tiver uma réplica primária.</span><span class="sxs-lookup"><span data-stu-id="39d5d-115">The policy state is healthy when the cluster resource of the availability group is online and the availability group has a primary replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39d5d-116">Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre possíveis causas e soluções estão localizadas em [O grupo de disponibilidade está offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) no TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="39d5d-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="39d5d-117">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="39d5d-117">Possible Causes</span></span>  
 <span data-ttu-id="39d5d-118">Esse problema pode ser causado por uma falha na instância de servidor que hospeda a réplica primária ou pelo recurso de grupo de disponibilidade WSFC (Windows Server Failover Cluster) que entra offline.</span><span class="sxs-lookup"><span data-stu-id="39d5d-118">This issue can be caused by a failure in the server instance that hosts the primary replica or by the Windows Server Failover Cluster (WSFC) availability group resource going offline.</span></span> <span data-ttu-id="39d5d-119">Estas são as possíveis causas do grupo de disponibilidade estar offline:</span><span class="sxs-lookup"><span data-stu-id="39d5d-119">Following are possible causes for the availability group to be offline:</span></span>  
  
-   <span data-ttu-id="39d5d-120">O grupo de disponibilidade não está configurado com o modo de failover automático.</span><span class="sxs-lookup"><span data-stu-id="39d5d-120">The availability group is not configured with automatic failover mode.</span></span> <span data-ttu-id="39d5d-121">A réplica primária torna-se indisponível e a função de todas as réplicas do grupo de disponibilidade torna-se RESOLVING.</span><span class="sxs-lookup"><span data-stu-id="39d5d-121">The primary replica becomes unavailable and the role of all replicas in the availability group become RESOLVING.</span></span>  
  
    -   <span data-ttu-id="39d5d-122">O serviço de instância de réplica primária está inativo ou não respondendo.</span><span class="sxs-lookup"><span data-stu-id="39d5d-122">The primary replica instance service is down or unresponsive.</span></span>  
  
    -   <span data-ttu-id="39d5d-123">O grupo de disponibilidade tem um problema de conectividade com o cluster.</span><span class="sxs-lookup"><span data-stu-id="39d5d-123">The availability group has a connectivity issue with the cluster.</span></span>  
  
-   <span data-ttu-id="39d5d-124">O grupo de disponibilidade está configurado com o modo de failover automático e não é concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="39d5d-124">The availability group is configured with automatic failover mode and does not complete successfully.</span></span>  
  
    -   <span data-ttu-id="39d5d-125">Durante o failover automático, a verificação de prontidão primária na réplica de destino falha e não há réplica disponível para se tornar a nova primária.</span><span class="sxs-lookup"><span data-stu-id="39d5d-125">During the automatic failover, the primary readiness check on the target replica fails, and there is no replica available to become the new primary.</span></span>  
  
-   <span data-ttu-id="39d5d-126">O recurso de grupo de disponibilidade no cluster fica offline.</span><span class="sxs-lookup"><span data-stu-id="39d5d-126">The availability group resource in the cluster becomes offline.</span></span>  
  
    -   <span data-ttu-id="39d5d-127">Qualquer recurso de cluster dependente encontra um problema crítico e se torna offline.</span><span class="sxs-lookup"><span data-stu-id="39d5d-127">Any dependent cluster resource encounters a critical issue and becomes offline.</span></span> <span data-ttu-id="39d5d-128">O recurso de grupo de disponibilidade também permanece offline até que o recurso dependente ficar online.</span><span class="sxs-lookup"><span data-stu-id="39d5d-128">The availability group resource is also offline until the dependent resource becomes online.</span></span>  
  
    -   <span data-ttu-id="39d5d-129">Um problema crítico no cluster desativa o recurso de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="39d5d-129">A critical issue in the cluster turns off the availability group resource.</span></span>  
  
-   <span data-ttu-id="39d5d-130">Há um failover automático, manual ou forçado em andamento para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="39d5d-130">There is an automatic, manual, or forced failover in progress for the availability group.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="39d5d-131">Soluções possíveis</span><span class="sxs-lookup"><span data-stu-id="39d5d-131">Possible Solutions</span></span>  
 <span data-ttu-id="39d5d-132">Estas são as possíveis soluções para este problema:</span><span class="sxs-lookup"><span data-stu-id="39d5d-132">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="39d5d-133">Se a instância do SQL Server da réplica primária estiver inativa, reinicie o servidor e verifique se o grupo de disponibilidade recupera o estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="39d5d-133">If the SQL Server instance of the primary replica is down, restart the server and then verify that the availability group recovers to a healthy state.</span></span>  
  
-   <span data-ttu-id="39d5d-134">Se o failover automático parece ter falhado, verifique se os bancos de dados da réplica estão sincronizados com a réplica primária previamente conhecida, e execute o failover da réplica primária.</span><span class="sxs-lookup"><span data-stu-id="39d5d-134">If the automatic failover appears to have failed, verify that the databases on the replica are synchronized with the previously known primary replica, and then failover to the primary replica.</span></span> <span data-ttu-id="39d5d-135">Se os bancos de dados não estiverem sincronizados, selecione uma réplica com perda mínima de dados e recupere no modo de failover.</span><span class="sxs-lookup"><span data-stu-id="39d5d-135">If the databases are not synchronized, select a replica with a minimum loss of data, and then recover to failover mode.</span></span>  
  
-   <span data-ttu-id="39d5d-136">Se o recurso no cluster estiver offline enquanto as instâncias do SQL Server parecerem íntegras, use o Gerenciador de Cluster de Failover para verificar a integridade do cluster ou outros problemas no cluster do servidor.</span><span class="sxs-lookup"><span data-stu-id="39d5d-136">If the resource in the cluster is offline while the instances of SQL Server appear to be healthy, use Failover Cluster Manager to check the cluster health or other cluster issues on the server.</span></span> <span data-ttu-id="39d5d-137">Você também pode usar o Gerenciador de Cluster de Failover para tentar colocar o recurso de grupo de disponibilidade online.</span><span class="sxs-lookup"><span data-stu-id="39d5d-137">You can also use the Failover Cluster Manager to attempt to turn the availability group resource online.</span></span>  
  
-   <span data-ttu-id="39d5d-138">Se houver um failover em andamento, aguarde a conclusão do failover.</span><span class="sxs-lookup"><span data-stu-id="39d5d-138">If there is a failover in progress, wait for the failover to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d5d-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39d5d-139">See Also</span></span>  
 <span data-ttu-id="39d5d-140">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="39d5d-140">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="39d5d-141">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="39d5d-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
