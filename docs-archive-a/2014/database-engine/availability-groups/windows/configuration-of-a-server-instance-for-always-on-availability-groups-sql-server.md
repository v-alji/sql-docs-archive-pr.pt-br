---
title: Configuração de uma instância de servidor para Always On grupos de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], about
ms.assetid: fad8db32-593e-49d5-989c-39eb8399c416
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3392e6189b687516e627d847acceedb165141117
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685303"
---
# <a name="configuration-of-a-server-instance-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="b1f79-102">Configuração de uma instância de servidor para grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b1f79-102">Configuration of a Server Instance for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="b1f79-103">Este tópico contém informações sobre os requisitos de configuração de uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para dar suporte ao [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1f79-103">This topic contains information about the requirements for configuring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b1f79-104">Para obter informações básicas sobre os pré-requisitos e restrições do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] em nós do WSFC (Cluster de Failover do Windows Server) e em instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], consulte [Pré-requisitos, restrições e recomendações para grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="b1f79-104">For essential information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites and restrictions for Windows Server Failover Clustering (WSFC) nodes and for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
 
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="b1f79-105">Termos e definições</span><span class="sxs-lookup"><span data-stu-id="b1f79-105">Terms and Definitions</span></span>  
  
 <span data-ttu-id="b1f79-106">Uma solução de alta disponibilidade e de recuperação de desastres que fornece uma substituição em nível corporativo para o espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b1f79-106">A high-availability and disaster-recovery solution that provides an enterprise-level replacement for database mirroring.</span></span> <span data-ttu-id="b1f79-107">Um *grupo de disponibilidade* dá suporte a um ambiente de failover para um conjunto discreto de bancos de dados de usuário, conhecidos como *bancos de dados de disponibilidade*, que fazem failover juntos.</span><span class="sxs-lookup"><span data-stu-id="b1f79-107">An *availability group* supports a failover environment for a discrete set of user databases, known as *availability databases*, that fail over together.</span></span>  
  
 <span data-ttu-id="b1f79-108">réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b1f79-108">availability replica</span></span>  
 <span data-ttu-id="b1f79-109">Uma instanciação de um grupo de disponibilidade que é hospedado por uma instância específica do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e que mantém uma cópia local de cada banco de dados de disponibilidade pertencente ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b1f79-109">An instantiation of an availability group that is hosted by a specific instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and that maintains a local copy of each availability database that belongs to the availability group.</span></span> <span data-ttu-id="b1f79-110">Existem dois tipos de réplica de disponibilidade: uma única *réplica primária* e uma a quatro *réplicas secundárias*.</span><span class="sxs-lookup"><span data-stu-id="b1f79-110">Two types of availability replicas exist: a single *primary replica* and one to four *secondary replicas*.</span></span> <span data-ttu-id="b1f79-111">As instâncias do servidor que hospedam as réplicas de disponibilidade de um determinado grupo de disponibilidade residem em nós diferentes de um único cluster do WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="b1f79-111">The server instances that host the availability replicas for a given availability group must reside on different nodes of a single Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 [<span data-ttu-id="b1f79-112">ponto de extremidade espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b1f79-112">database mirroring endpoint</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
 <span data-ttu-id="b1f79-113">Um ponto de extremidade é um objeto do SQL Server que permite que o SQL Server se comunique pela rede.</span><span class="sxs-lookup"><span data-stu-id="b1f79-113">An endpoint is a SQL Server object that enables SQL Server to communicate over the network.</span></span> <span data-ttu-id="b1f79-114">Para participar do espelhamento de banco de dados e/ou do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , uma instância de servidor requer um ponto de extremidade especial dedicado.</span><span class="sxs-lookup"><span data-stu-id="b1f79-114">To participate in database mirroring and/or [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] a server instance requires a special, dedicated endpoint.</span></span> <span data-ttu-id="b1f79-115">Todas as conexões de espelhamento e de grupo de disponibilidade em uma instância de servidor usam o mesmo ponto de extremidade de espelhamento do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b1f79-115">All mirroring and availability group connections on a server instance use the same database mirroring endpoint.</span></span> <span data-ttu-id="b1f79-116">Esse ponto de extremidade é um ponto de extremidade com finalidade especial usado exclusivamente para essas conexões de outras instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="b1f79-116">This endpoint is a special-purpose endpoint used exclusively to receive these connections from other server instances.</span></span>  
  
##  <a name="to-configure-a-server-instance-to-support-alwayson-availability-groups"></a><a name="ConfigSI"></a><span data-ttu-id="b1f79-117">Para configurar uma instância de servidor para dar suporte a Grupos de Disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="b1f79-117">To Configure a Server Instance to Support AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="b1f79-118">Para oferecer suporte ao [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], uma instância de servidor deve residir em um nó no cluster de failover do WSFC que hospeda o grupo de disponibilidade, estar habilitada pelo [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] e possuir um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b1f79-118">To support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], a server instance must reside on a node in the WSFC failover cluster that hosts the availability group, be [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] enabled, and possess a database mirroring endpoint.</span></span>  
  
1.  <span data-ttu-id="b1f79-119">Habilite o recurso Grupos de Disponibilidade AlwaysOn em cada instância de servidor que deve participar de um ou mais grupos de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b1f79-119">Enable the AlwaysOn Availability Groups feature on every server instance that is to participate in one or more availability groups.</span></span> <span data-ttu-id="b1f79-120">Uma determinada instância de servidor pode hospedar uma única réplica de disponibilidade para um determinado grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b1f79-120">A given server instance can host only a single availability replica for a given availability group.</span></span>  
  
2.  <span data-ttu-id="b1f79-121">Verifique se a instância de servidor tem um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b1f79-121">Ensure that the server instance possesses a database mirroring endpoint.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b1f79-122">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b1f79-122">Related Tasks</span></span>  
 <span data-ttu-id="b1f79-123">**Para habilitar Grupos de Disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="b1f79-123">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="b1f79-124">Habilitar e desabilitar grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b1f79-124">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="b1f79-125">**Para determinar se um ponto de extremidade de espelhamento de banco de dados existe**</span><span class="sxs-lookup"><span data-stu-id="b1f79-125">**To determine whether a database mirroring endpoint exists**</span></span>  
  
-   [<span data-ttu-id="b1f79-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1f79-126">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
 <span data-ttu-id="b1f79-127">**Para criar um ponto de extremidade de espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="b1f79-127">**To create a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="b1f79-128">Criar um ponto de extremidade de espelhamento de banco de dados para Grupos de Disponibilidade AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="b1f79-128">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="b1f79-129">Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b1f79-129">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="b1f79-130">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1f79-130">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="b1f79-131">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="b1f79-131">Related Content</span></span>  
  
-   <span data-ttu-id="b1f79-132">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="b1f79-132">**Blogs:**</span></span>  
  
     [<span data-ttu-id="b1f79-133">Série de aprendizado do AlwaysON - HADRON: uso de trabalho do pool para bancos de dados habilitados do HADRON</span><span class="sxs-lookup"><span data-stu-id="b1f79-133">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="b1f79-134">Blogs da equipe do SQL Server AlwaysOn: o blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="b1f79-134">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="b1f79-135">Blogs dos engenheiros do CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1f79-135">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="b1f79-136">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="b1f79-136">**Videos:**</span></span>  
  
     [<span data-ttu-id="b1f79-137">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 1: Introduzindo a próxima geração de solução de alta disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b1f79-137">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="b1f79-138">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 2: Criando uma solução de disponibilidade de missão crítica usando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="b1f79-138">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="b1f79-139">**Whitepapers:**</span><span class="sxs-lookup"><span data-stu-id="b1f79-139">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="b1f79-140">Guia de soluções AlwaysOn do Microsoft SQL Server para alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="b1f79-140">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="b1f79-141">White papers da Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="b1f79-141">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="b1f79-142">White papers da equipe de consultoria do cliente do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1f79-142">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="b1f79-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b1f79-143">See Also</span></span>  
 <span data-ttu-id="b1f79-144">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b1f79-144">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="b1f79-145">[Pré-requisitos, restrições e recomendações para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="b1f79-145">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="b1f79-146">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b1f79-146">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="b1f79-147">[Grupos de Disponibilidade AlwaysOn: interoperabilidade (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b1f79-147">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="b1f79-148">[Clustering de failover e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b1f79-148">[Failover Clustering and AlwaysOn Availability Groups &#40;SQL Server&#41;](failover-clustering-and-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="b1f79-149">[WSFC &#40;Windows Server Failover Clustering&#41; com o SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b1f79-149">[Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="b1f79-150">Instâncias de cluster de failover do AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="b1f79-150">AlwaysOn Failover Cluster Instances</span></span>](../../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md)  
  
