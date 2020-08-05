---
title: Exibir propriedades do grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server]
ms.assetid: 61243c87-bd62-4510-863f-2a8f347caf1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b7d1f57a9bd29b6c65160ec9a163bc77dfca48b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572185"
---
# <a name="view-availability-group-properties-sql-server"></a><span data-ttu-id="31bba-102">Exibir propriedades do grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31bba-102">View Availability Group Properties (SQL Server)</span></span>
  <span data-ttu-id="31bba-103">Este tópico descreve como exibir as propriedades de um grupo de disponibilidade para um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31bba-103">This topic describes how to view the properties of an availability group for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  

  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="31bba-104">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="31bba-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="31bba-105">**Para exibir e alterar as propriedades de um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="31bba-105">**To view and change the properties an availability group**</span></span>  
  
1.  <span data-ttu-id="31bba-106">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="31bba-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="31bba-107">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="31bba-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="31bba-108">Clique com o botão direito do mouse no grupo de disponibilidade cujas propriedades você deseja exibir e selecione o comando **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="31bba-108">Right-click the availability group whose properties you want to view, and select the **Properties** command.</span></span>  
  
4.  <span data-ttu-id="31bba-109">Na caixa de diálogo **Propriedades do Grupo de disponibilidade** , use as páginas **Geral** e **Preferências de Backup** para exibir e, em alguns casos, alterar as propriedades do grupo de disponibilidade selecionado.</span><span class="sxs-lookup"><span data-stu-id="31bba-109">In the **Availability Group Properties** dialog box, use the **General** and **Backup Preferences** pages to view and, in some cases, change properties of the selected availability group.</span></span> <span data-ttu-id="31bba-110">Para obter mais informações, consulte [Propriedades do grupo de disponibilidade e novo grupo de disponibilidade &#40;Página Geral&#41;](availability-group-properties-new-availability-group-general-page.md) e [Propriedades do grupo de disponibilidade: novo grupo de disponibilidade &#40;Página Preferências de backup&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span><span class="sxs-lookup"><span data-stu-id="31bba-110">For more information, see [Availability Group Properties and New Availability Group &#40;General Page&#41;](availability-group-properties-new-availability-group-general-page.md) and [Availability Group Properties: New Availability Group &#40;Backup Preferences Page&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span></span>  
  
     <span data-ttu-id="31bba-111">Use a página **Permissões** para exibir os logons, funções e permissões explícitas atuais associados ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31bba-111">Use the **Permissions** page to view the current logins, roles, and explicit permissions associated with the availability group.</span></span> <span data-ttu-id="31bba-112">Para obter mais informações, consulte [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span><span class="sxs-lookup"><span data-stu-id="31bba-112">For more information, see [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="31bba-113">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31bba-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="31bba-114">**Para exibir as propriedades e o estado de um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="31bba-114">**To view the properties and state of an availability group**</span></span>  
  
 <span data-ttu-id="31bba-115">Para consultar as propriedades e os estados de grupos de disponibilidade para os quais a instância do servidor hospeda uma réplica de disponibilidade, use as exibições a seguir:</span><span class="sxs-lookup"><span data-stu-id="31bba-115">To query the properties and states of the availability groups for which the server instance hosts an availability replica, use the following views:</span></span>  
  
 [<span data-ttu-id="31bba-116">sys.availability_groups</span><span class="sxs-lookup"><span data-stu-id="31bba-116">sys.availability_groups</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-transact-sql)  
 <span data-ttu-id="31bba-117">Retorna uma linha para cada grupo de disponibilidade para o qual a instância local do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hospeda uma réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31bba-117">Returns a row for each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span> <span data-ttu-id="31bba-118">Cada linha contém uma cópia armazenada em cache dos metadados do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31bba-118">Each row contains a cached copy of the availability group metadata.</span></span>  
  
 <span data-ttu-id="31bba-119">**Nomes de colunas:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="31bba-119">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="31bba-120">sys.availability_groups_cluster</span><span class="sxs-lookup"><span data-stu-id="31bba-120">sys.availability_groups_cluster</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-cluster-transact-sql)  
 <span data-ttu-id="31bba-121">Retorna uma linha para cada grupo de disponibilidade no cluster do WSFC.</span><span class="sxs-lookup"><span data-stu-id="31bba-121">Returns a row for each availability group in the WSFC cluster.</span></span> <span data-ttu-id="31bba-122">Cada linha contém os metadados do grupo de disponibilidade do cluster do WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="31bba-122">Each row contains the availability group metadata from the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="31bba-123">**Nomes de colunas:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="31bba-123">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="31bba-124">sys.dm_hadr_availability_group_states</span><span class="sxs-lookup"><span data-stu-id="31bba-124">sys.dm_hadr_availability_group_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-group-states-transact-sql)  
 <span data-ttu-id="31bba-125">Retorna uma linha para cada grupo de disponibilidade que possui uma réplica de disponibilidade na instância local do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31bba-125">Returns a row for each availability group that possesses an availability replica on the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="31bba-126">Cada linha exibe os estados que definem a integridade de um determinado grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31bba-126">Each row displays the states that define the health of a given availability group.</span></span>  
  
 <span data-ttu-id="31bba-127">**Nomes de colunas:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span><span class="sxs-lookup"><span data-stu-id="31bba-127">**Column names:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="31bba-128">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="31bba-128">Related Tasks</span></span>  
 <span data-ttu-id="31bba-129">**Para exibir informações sobre os grupos de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="31bba-129">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="31bba-130">Exibir as propriedades da réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-130">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="31bba-131">Exibir propriedades do ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-131">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="31bba-132">Políticas AlwaysOn para problemas operacionais com o Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-132">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="31bba-133">Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-133">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="31bba-134">Monitorar grupos de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-134">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="31bba-135">**Para configurar um grupo de disponibilidade existente**</span><span class="sxs-lookup"><span data-stu-id="31bba-135">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="31bba-136">Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-136">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31bba-137">Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-137">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31bba-138">Adicionar um banco de dados a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-138">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="31bba-139">Remover um banco de dados secundário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-139">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31bba-140">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-140">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="31bba-141">Remover um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-141">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="31bba-142">Remover um banco de dados primário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-142">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31bba-143">Remover um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-143">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="31bba-144">**Para fazer o failover de um grupo de disponibilidade manualmente**</span><span class="sxs-lookup"><span data-stu-id="31bba-144">**To manually fail over an availability group**</span></span>  
  
-   [<span data-ttu-id="31bba-145">Executar um failover manual planejado de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-145">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="31bba-146">Executar um failover manual forçado de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="31bba-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31bba-147">See Also</span></span>  
 <span data-ttu-id="31bba-148">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [monitorar grupos de disponibilidade &#40;políticas AlwaysOn do Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [para problemas operacionais com](always-on-policies-for-operational-issues-always-on-availability.md) o grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31bba-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md)</span></span> 
  
  
