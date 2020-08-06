---
title: Exibir propriedades da réplica de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- ', policies'
ms.assetid: 14fed3c4-8ecc-4e1c-931d-a7ec1e9f9e90
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ca7b0508907b4d86c9ee627438a3f18e1b01fdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681190"
---
# <a name="view-availability-replica-properties-sql-server"></a><span data-ttu-id="80379-102">Exibir as propriedades da réplica de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="80379-102">View Availability Replica Properties (SQL Server)</span></span>
  <span data-ttu-id="80379-103">Este tópico descreve como exibir as propriedades de uma réplica de disponibilidade para um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80379-103">This topic describes how to view the properties of an availability replica for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="80379-104">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="80379-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="80379-105">**Para exibir e alterar as propriedades de uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="80379-105">**To view and change properties an availability replica**</span></span>  
  
1.  <span data-ttu-id="80379-106">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="80379-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="80379-107">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="80379-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="80379-108">Expanda o grupo de disponibilidade ao qual a réplica de disponibilidade pertence e expanda o nó **Réplicas de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="80379-108">Expand the availability group to which the availability replica belongs, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="80379-109">Clique com o botão direito do mouse na réplica de disponibilidade cujas propriedades você deseja exibir e selecione o comando **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="80379-109">Right-click the availability replica whose properties you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="80379-110">Na caixa de diálogo **Propriedades da Réplica de Disponibilidade** , use a página **Geral** para exibir as propriedades dessa réplica.</span><span class="sxs-lookup"><span data-stu-id="80379-110">In the **Availability Replica Properties** dialog box, use the **General** page to view the properties of this replica.</span></span> <span data-ttu-id="80379-111">Se estiver conectado à réplica primária, você poderá alterar as seguintes propriedades: modo de disponibilidade, modo de failover, acesso de conexão para a função primária, acesso de leitura para a função secundária (secundária legível) e o valor do tempo limite de sessão.</span><span class="sxs-lookup"><span data-stu-id="80379-111">If you are connected to the primary replica, you can change the following properties: availability mode, failover mode, connection access for the primary role, read-access for the secondary role (readable-secondary), and the session-timeout value.</span></span> <span data-ttu-id="80379-112">Para obter mais informações, consulte [Propriedades da réplica de disponibilidade &#40;página geral&#41;](availability-replica-properties-general-page.md).</span><span class="sxs-lookup"><span data-stu-id="80379-112">For more information, see  [Availability Replica Properties &#40;General Page&#41;](availability-replica-properties-general-page.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="80379-113">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="80379-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="80379-114">**Para exibir as propriedades e os estados de réplicas de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="80379-114">**To view properties and states of availability replicas**</span></span>  
  
 <span data-ttu-id="80379-115">Para exibir as propriedades e os estados de réplicas de disponibilidade, use as seguintes exibições e a função do sistema:</span><span class="sxs-lookup"><span data-stu-id="80379-115">To view the properties and states of availability replicas, use the following views and system function:</span></span>  
  
 [<span data-ttu-id="80379-116">sys.availability_replicas</span><span class="sxs-lookup"><span data-stu-id="80379-116">sys.availability_replicas</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql)  
 <span data-ttu-id="80379-117">Retorna uma linha para cada réplica de disponibilidade em cada grupo de disponibilidade para o qual a instância local do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hospeda uma réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="80379-117">Returns a row for every availability replica in each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span>  
  
 <span data-ttu-id="80379-118">**Nomes de colunas:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span><span class="sxs-lookup"><span data-stu-id="80379-118">**Column names:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span></span>  
  
 [<span data-ttu-id="80379-119">sys.availability_read_only_routing_lists</span><span class="sxs-lookup"><span data-stu-id="80379-119">sys.availability_read_only_routing_lists</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
 <span data-ttu-id="80379-120">Retorna uma linha para a lista de roteamento somente leitura de cada réplica de disponibilidade em um grupo de disponibilidade AlwaysOn do cluster de failover WSFC.</span><span class="sxs-lookup"><span data-stu-id="80379-120">Returns a row for the read only routing list of each availability replica in an AlwaysOn availability group in the WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="80379-121">**Nomes de colunas:** replica_id, routing_priority, read_only_replica_id</span><span class="sxs-lookup"><span data-stu-id="80379-121">**Column names:** replica_id, routing_priority, read_only_replica_id</span></span>  
  
 [<span data-ttu-id="80379-122">sys.dm_hadr_availability_replica_cluster_nodes</span><span class="sxs-lookup"><span data-stu-id="80379-122">sys.dm_hadr_availability_replica_cluster_nodes</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-nodes-transact-sql)  
 <span data-ttu-id="80379-123">Retorna uma linha para cada réplica de disponibilidade (independentemente do estado de junção) dos grupos de disponibilidade AlwaysOn no cluster do WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="80379-123">Returns a row for every availability replica (regardless of join state) of the AlwaysOn availability groups in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="80379-124">**Nomes de colunas:** group_name, replica_server_name, node_name</span><span class="sxs-lookup"><span data-stu-id="80379-124">**Column names:** group_name, replica_server_name, node_name</span></span>  
  
 [<span data-ttu-id="80379-125">sys.dm_hadr_availability_replica_cluster_states</span><span class="sxs-lookup"><span data-stu-id="80379-125">sys.dm_hadr_availability_replica_cluster_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-states-transact-sql)  
 <span data-ttu-id="80379-126">Retorna uma linha para cada réplica (independentemente do estado de junção) de todos os grupos de disponibilidade AlwaysOn (independentemente do local da réplica) no cluster do WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="80379-126">Returns a row for each replica (regardless of join state) of all AlwaysOn availability groups (regardless of replica location) in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="80379-127">**Nomes de colunas:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span><span class="sxs-lookup"><span data-stu-id="80379-127">**Column names:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span></span>  
  
 [<span data-ttu-id="80379-128">sys.dm_hadr_availability_replica_states</span><span class="sxs-lookup"><span data-stu-id="80379-128">sys.dm_hadr_availability_replica_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-states-transact-sql)  
 <span data-ttu-id="80379-129">Retorna uma linha que mostra o estado de cada réplica de disponibilidade local e uma linha para cada réplica de disponibilidade remota no mesmo grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="80379-129">Returns a row showing the state of each local availability replica and a row for each remote availability replica in the same availability group.</span></span>  
  
 <span data-ttu-id="80379-130">**Nomes de colunas:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description e last_connect_error_timestamp</span><span class="sxs-lookup"><span data-stu-id="80379-130">**Column names:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description, and last_connect_error_timestamp</span></span>  
  
 [<span data-ttu-id="80379-131">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="80379-131">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
 <span data-ttu-id="80379-132">Determina se a réplica atual é a réplica de backup preferencial.</span><span class="sxs-lookup"><span data-stu-id="80379-132">Determines whether the current replica is the preferred backup replica.</span></span> <span data-ttu-id="80379-133">Retornará 1 se o banco de dados na instância do servidor atual for a réplica preferencial.</span><span class="sxs-lookup"><span data-stu-id="80379-133">Returns 1 if the database on the current server instance is the preferred replica.</span></span> <span data-ttu-id="80379-134">Caso contrário, retornará 0.</span><span class="sxs-lookup"><span data-stu-id="80379-134">Otherwise, it returns 0.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80379-135">Para obter informações sobre contadores de desempenho para réplicas de disponibilidade (o objeto de desempenho **SQLServer:Availability Replica**  ), consulte [SQL Server, Réplica de Disponibilidade](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="80379-135">For information about performance counters for availability replicas (the **SQLServer:Availability Replica**  performance object), see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="80379-136">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="80379-136">Related Tasks</span></span>  
 <span data-ttu-id="80379-137">**Para exibir informações sobre os grupos de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="80379-137">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="80379-138">Exibir as propriedades do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-138">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="80379-139">Exibir propriedades do ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-139">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="80379-140">Políticas AlwaysOn para problemas operacionais com o Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-140">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="80379-141">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="80379-142">Monitorar grupos de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-142">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="80379-143">**Para gerenciar réplicas de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="80379-143">**To manage availability replicas**</span></span>  
  
-   [<span data-ttu-id="80379-144">Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-144">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="80379-145">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-145">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="80379-146">Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-146">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="80379-147">Alterar o modo de disponibilidade de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-147">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="80379-148">Alterar o modo de failover de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-148">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="80379-149">Alterar o período de tempo limite da sessão de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-149">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="80379-150">Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-150">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="80379-151">**Para gerenciar um banco de dados de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="80379-151">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="80379-152">Adicionar um banco de dados a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-152">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="80379-153">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-153">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="80379-154">Suspender um banco de dados de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-154">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="80379-155">Retomar um banco de dados de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-155">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="80379-156">Remover um banco de dados secundário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-156">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="80379-157">Remover um banco de dados primário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-157">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="80379-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="80379-158">See Also</span></span>  
 <span data-ttu-id="80379-159">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="80379-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="80379-160">[Monitorar grupos de disponibilidade &#40;&#41;Transact-SQL](monitor-availability-groups-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="80379-160">[Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) </span></span>  
 <span data-ttu-id="80379-161">[Políticas AlwaysOn para problemas operacionais com o Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="80379-161">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 [<span data-ttu-id="80379-162">Administração de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="80379-162">Administration of an Availability Group &#40;SQL Server&#41;</span></span>](administration-of-an-availability-group-sql-server.md)  
  
  
