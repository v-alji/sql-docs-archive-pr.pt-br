---
title: Administração de um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], managing
ms.assetid: 0b7542fa-235e-413d-81bf-3eff9ee07480
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2cac9a34fe71c11f71ec47bbb6d690199869fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570259"
---
# <a name="administration-of-an-availability-group-sql-server"></a><span data-ttu-id="94777-102">Administração de um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="94777-102">Administration of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="94777-103">O gerenciamento de um grupo de disponibilidade AlwaysOn existente no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] envolve uma ou mais das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="94777-103">Managing an existing AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] involves one or more of the following tasks:</span></span>  
  
-   <span data-ttu-id="94777-104">Alterar as propriedades de uma réplica de disponibilidade existente, por exemplo, para alterar acesso de conexão de cliente (para configurar réplicas secundárias legíveis), alterar seu modo de failover, modo de disponibilidade ou configuração de tempo limite de sessão.</span><span class="sxs-lookup"><span data-stu-id="94777-104">Altering the properties of an existing availability replica, for example to change client connection access (for configuring readable secondary replicas), changing its failover mode, availability mode, or session timeout setting.</span></span>  
  
-   <span data-ttu-id="94777-105">Adicionar ou remover réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="94777-105">Adding or removing secondary replicas.</span></span>  
  
-   <span data-ttu-id="94777-106">Adicionar ou remover um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="94777-106">Adding or removing a database.</span></span>  
  
-   <span data-ttu-id="94777-107">Suspender ou retomar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="94777-107">Suspending or resuming a database.</span></span>  
  
-   <span data-ttu-id="94777-108">Executar um failover manual planejado (um *failover manual*) ou um failover manual forçado (um *failover forçado*).</span><span class="sxs-lookup"><span data-stu-id="94777-108">Performing a planned manual failover (a *manual failover*) or a forced manual failover (a *forced failover*).</span></span>  
  
-   <span data-ttu-id="94777-109">Criar ou configurar um ouvinte de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94777-109">Creating or configuring an availability group listener.</span></span>  
  
-   <span data-ttu-id="94777-110">Gerenciando [réplicas secundárias legíveis](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) para um determinado grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94777-110">Managing [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="94777-111">Isto envolve a configuração de uma ou mais réplicas para acesso somente leitura ao serem executadas sob a função secundária e configurar o roteamento somente leitura.</span><span class="sxs-lookup"><span data-stu-id="94777-111">This involves configuring one or more replicas to read-only access when running under the secondary role, and configuring read-only routing.</span></span>  
  
-   <span data-ttu-id="94777-112">Gerenciando [backups em réplicas secundárias](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) para um determinado grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94777-112">Managing [backups on secondary replicas](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="94777-113">Isto envolve a configuração de onde você prefere que os trabalhos de backup sejam executados e, em seguida, gere scripts de trabalhos de backup para implementar sua preferência de backup.</span><span class="sxs-lookup"><span data-stu-id="94777-113">This involves configuring where you prefer that backup jobs run and then scripting backup jobs to implement your backup preference.</span></span> <span data-ttu-id="94777-114">Você precisa gerar script de trabalhos de backup para todos os bancos de dados no grupo de disponibilidade em todas as instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda uma réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94777-114">you need to script backup jobs for every database in the availability group on every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica.</span></span>  
  
-   <span data-ttu-id="94777-115">Excluir um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="94777-115">Deleting an availability group.</span></span>  
  
-   <span data-ttu-id="94777-116">Migração entre clusters de Grupos de Disponibilidade AlwaysOn para atualização do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="94777-116">Cross-cluster migration of AlwaysOn Availability Groups for OS upgrade</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="94777-117">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="94777-117">Related Tasks</span></span>  
 <span data-ttu-id="94777-118">**Para configurar um grupo de disponibilidade existente**</span><span class="sxs-lookup"><span data-stu-id="94777-118">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="94777-119">Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-119">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-120">Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-120">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-121">Adicionar um banco de dados a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-121">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="94777-122">Remover um banco de dados secundário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-122">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-123">Remover um banco de dados primário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-123">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-124">Configure a política de failover flexível para controlar as condições de failover automático &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-124">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover &#40;AlwaysOn Availability Groups&#41;</span></span>](configure-flexible-automatic-failover-policy.md)  
  
 <span data-ttu-id="94777-125">**Para gerenciar um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="94777-125">**To manage an availability group**</span></span>  
  
-   [<span data-ttu-id="94777-126">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="94777-127">Executar um failover manual planejado de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-127">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-128">Executar um failover manual forçado de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-128">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-129">Remover um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-129">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="94777-130">**Para gerenciar uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="94777-130">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="94777-131">Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-131">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-132">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-132">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-133">Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-133">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-134">Alterar o modo de disponibilidade de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-134">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="94777-135">Alterar o modo de failover de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-135">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="94777-136">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-136">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="94777-137">Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-137">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="94777-138">Configurar o roteamento somente leitura para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-138">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-139">Alterar o período de tempo limite da sessão de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-139">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="94777-140">**Para gerenciar um banco de dados de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="94777-140">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="94777-141">Adicionar um banco de dados a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-141">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="94777-142">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-142">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-143">Remover um banco de dados primário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-143">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-144">Remover um banco de dados secundário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-144">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="94777-145">Suspender um banco de dados de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-145">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="94777-146">Retomar um banco de dados de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-146">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
 <span data-ttu-id="94777-147">**Para monitorar um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="94777-147">**To monitor an availability group**</span></span>  
  
-   [<span data-ttu-id="94777-148">Monitoramento de grupos de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-148">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
 <span data-ttu-id="94777-149">**Para dar suporte à migração de grupos de disponibilidade para um novo cluster WSFC (migração entre clusters)**</span><span class="sxs-lookup"><span data-stu-id="94777-149">**To support migrating availability groups to a new WSFC cluster (cross-cluster migration)**</span></span>  
  
-   [<span data-ttu-id="94777-150">Alterar o contexto do cluster HADR da instância de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-150">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
-   [<span data-ttu-id="94777-151">Colocar um grupo de disponibilidade offline &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-151">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="94777-152">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="94777-152">Related Content</span></span>  
  
-   <span data-ttu-id="94777-153">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="94777-153">**Blogs:**</span></span>  
  
     [<span data-ttu-id="94777-154">Blogs da equipe do SQL Server AlwaysOn: o blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="94777-154">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="94777-155">Blogs dos engenheiros do CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="94777-155">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="94777-156">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="94777-156">**Videos:**</span></span>  
  
     [<span data-ttu-id="94777-157">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 1: Introduzindo a próxima geração de solução de alta disponibilidade</span><span class="sxs-lookup"><span data-stu-id="94777-157">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="94777-158">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 2: Criando uma solução de disponibilidade de missão crítica usando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="94777-158">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="94777-159">**White papers:**</span><span class="sxs-lookup"><span data-stu-id="94777-159">**White papers:**</span></span>  
  
     [<span data-ttu-id="94777-160">White papers da Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="94777-160">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="94777-161">White papers da equipe de consultoria do cliente do SQL Server</span><span class="sxs-lookup"><span data-stu-id="94777-161">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
  
## <a name="see-also"></a><span data-ttu-id="94777-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94777-162">See Also</span></span>  
 <span data-ttu-id="94777-163">[Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="94777-163">[AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="94777-164">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="94777-164">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="94777-165">Configuração de uma instância de servidor para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-165">Configuration of a Server Instance for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](configuration-of-a-server-instance-for-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="94777-166">[Criação e configuração de grupos de disponibilidade &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="94777-166">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="94777-167">[Secundárias ativas: réplicas secundárias legíveis &#40;Grupos de Disponibilidade AlwaysOn&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="94777-167">[Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="94777-168">Secundárias ativas: backup em réplicas secundárias &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-168">Active Secondaries: Backup on Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md)  
 <span data-ttu-id="94777-169">[Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="94777-169">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 <span data-ttu-id="94777-170">[Políticas AlwaysOn para problemas operacionais com o Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="94777-170">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="94777-171">[Monitoramento de grupos de disponibilidade &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="94777-171">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="94777-172">[Grupos de Disponibilidade AlwaysOn: &#40;de interoperabilidade SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="94777-172">[AlwaysOn Availability Groups: Interoperability &#40;SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="94777-173">[Visão geral das instruções Transact-SQL para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="94777-173">[Overview of Transact-SQL Statements for AlwaysOn Availability Groups &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="94777-174">Visão geral dos cmdlets do PowerShell para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="94777-174">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
