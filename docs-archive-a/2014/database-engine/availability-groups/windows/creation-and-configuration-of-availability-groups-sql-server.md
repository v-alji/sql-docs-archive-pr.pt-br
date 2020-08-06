---
title: Criação e configuração de grupos de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], creating
ms.assetid: 7f89fab8-6ee2-4273-9de0-e594bfb9407f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc33da393527c19985f5e7b214ba4bc02dc2f3af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686368"
---
# <a name="creation-and-configuration-of-availability-groups-sql-server"></a><span data-ttu-id="a1215-102">Criação e configuração de grupos de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a1215-102">Creation and Configuration of Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="a1215-103">Os tópicos desta seção explicam como implantar uma implementação do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] em instâncias do [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] que residem nos diferentes nós WSFC (Windows Server Failover Clustering) em um único cluster de failover WSFC.</span><span class="sxs-lookup"><span data-stu-id="a1215-103">The topics in this section explain how to deploy a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] implementation on instances of [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] that reside on different Windows Server Failover Clustering (WSFC) nodes within a single WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="a1215-104">Antes de criar seu primeiro grupo de disponibilidade, é altamente recomendável que você se familiarize com as informações nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a1215-104">Before you create your first availability group, we strongly recommend that you familiarize yourself with the information in the following topics:</span></span>  
  
 [<span data-ttu-id="a1215-105">Pré-requisitos, restrições e recomendações para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-105">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
 <span data-ttu-id="a1215-106">Este tópico descreve os pré-requisitos, as restrições e recomendações para computadores; nós WSFC; instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; grupos de disponibilidade, réplicas e bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="a1215-106">This topic describes the prerequisites, restrictions, and recommendations for computers; WSFC nodes; instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; availability groups, replicas, and databases.</span></span> <span data-ttu-id="a1215-107">Este tópico também contém informações sobre considerações de segurança.</span><span class="sxs-lookup"><span data-stu-id="a1215-107">This topic also contains information about security considerations.</span></span>  
  
 [<span data-ttu-id="a1215-108">Introdução com Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-108">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="a1215-109">Contém informações sobre as etapas de configuração de uma instância de servidor, criação de um grupo de disponibilidade, configuração do grupo de disponibilidade para conexões de cliente, gerenciamento de grupos de disponibilidade e monitoramento de grupos de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="a1215-109">Contains information about the steps for configuring a server instance, creating an availability group, configuring the availability group for client connections, managing availability groups, and monitoring availability groups.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a1215-110">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a1215-110">Related Tasks</span></span>  
 <span data-ttu-id="a1215-111">**Para configurar uma instância de servidor para o[!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="a1215-111">**To configure a server instance for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]**</span></span>  
  
-   [<span data-ttu-id="a1215-112">Habilitar e desabilitar grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-112">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="a1215-113">Criar um ponto de extremidade de espelhamento de banco de dados para Grupos de Disponibilidade AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-113">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="a1215-114">Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-114">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="a1215-115">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-115">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
 <span data-ttu-id="a1215-116">**Para começar a configurar Grupos de Disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="a1215-116">**To get started with configuring AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="a1215-117">Introdução com Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-117">Getting Started with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](getting-started-with-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="a1215-118">**Para criar e configurar um novo grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="a1215-118">**To create and configure a new availability group**</span></span>  
  
-   [<span data-ttu-id="a1215-119">Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-119">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a1215-120">Criar um grupo de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-120">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="a1215-121">Criar um grupo de disponibilidade &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-121">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="a1215-122">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-122">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a1215-123">Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-123">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="a1215-124">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-124">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="a1215-125">Configurar a política de failover flexível para controlar condições de failover automático (grupos de disponibilidade AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="a1215-125">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="a1215-126">Configurar backup em réplicas de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="a1215-127">Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-127">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="a1215-128">Configurar o roteamento somente leitura para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-128">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="a1215-129">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-129">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="a1215-130">Iniciar a movimentação de dados em um banco de dado secundário AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-130">Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;</span></span>](start-data-movement-on-an-always-on-secondary-database-sql-server.md)  
  
-   [<span data-ttu-id="a1215-131">Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-131">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="a1215-132">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-132">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="a1215-133">Gerenciamento de logons e trabalhos para os bancos de dados de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-133">Management of Logins and Jobs for the Databases of an Availability Group &#40;SQL Server&#41;</span></span>](../../logins-and-jobs-for-availability-group-databases.md)  
  
 <span data-ttu-id="a1215-134">**Para solucionar problemas**</span><span class="sxs-lookup"><span data-stu-id="a1215-134">**To troubleshoot**</span></span>  
  
-   [<span data-ttu-id="a1215-135">Solução de problemas de configuração de Grupos de Disponibilidade AlwaysOn (SQL Server) excluída</span><span class="sxs-lookup"><span data-stu-id="a1215-135">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="a1215-136">Solucionar problemas de uma operação de adição de arquivo com falha &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="a1215-136">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="a1215-137">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="a1215-137">Related Content</span></span>  
  
-   <span data-ttu-id="a1215-138">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="a1215-138">**Blogs:**</span></span>  
  
     [<span data-ttu-id="a1215-139">Série de aprendizado do AlwaysON - HADRON: uso de trabalho do pool para bancos de dados habilitados do HADRON</span><span class="sxs-lookup"><span data-stu-id="a1215-139">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="a1215-140">Blogs da equipe do SQL Server AlwaysOn: o blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="a1215-140">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="a1215-141">Blogs dos engenheiros do CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1215-141">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="a1215-142">**Vídeos:**</span><span class="sxs-lookup"><span data-stu-id="a1215-142">**Videos:**</span></span>  
  
     [<span data-ttu-id="a1215-143">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 1: Introduzindo a próxima geração de solução de alta disponibilidade</span><span class="sxs-lookup"><span data-stu-id="a1215-143">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="a1215-144">Microsoft SQL Server codinome "Denali" Série AlwaysOn, Parte 2: Criando uma solução de disponibilidade de missão crítica usando AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="a1215-144">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="a1215-145">**Whitepapers:**</span><span class="sxs-lookup"><span data-stu-id="a1215-145">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="a1215-146">Guia de soluções AlwaysOn do Microsoft SQL Server para alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="a1215-146">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="a1215-147">White papers da Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="a1215-147">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="a1215-148">White papers da equipe de consultoria do cliente do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1215-148">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="a1215-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a1215-149">See Also</span></span>  
 <span data-ttu-id="a1215-150">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a1215-150">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="a1215-151">[Administração de um grupo de disponibilidade &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a1215-151">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="a1215-152">[Políticas AlwaysOn para problemas operacionais com Grupos de Disponibilidade AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="a1215-152">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="a1215-153">[Monitoramento de grupos de disponibilidade &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a1215-153">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="a1215-154">Grupos de disponibilidade AlwaysOn: interoperabilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a1215-154">AlwaysOn Availability Groups: Interoperability (SQL Server)</span></span>](always-on-availability-groups-interoperability-sql-server.md)  
  
