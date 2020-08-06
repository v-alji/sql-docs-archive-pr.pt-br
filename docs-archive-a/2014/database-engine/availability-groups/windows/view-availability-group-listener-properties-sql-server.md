---
title: Exibir propriedades do ouvinte do grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistenerproperties.general.f1
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
ms.assetid: aca0d016-3228-40b8-bdc3-285ed6d9b280
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7fe316394a030350ceb12a0d1b8e2d48ee1d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569659"
---
# <a name="view-availability-group-listener-properties-sql-server"></a><span data-ttu-id="ece19-102">Exibir propriedades do ouvinte do grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ece19-102">View Availability Group Listener Properties (SQL Server)</span></span>
  <span data-ttu-id="ece19-103">Este tópico descreve como exibir as propriedades de um *ouvinte de grupo de disponibilidade* AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ece19-103">This topic describes how to view the properties of an AlwaysOn *availability group listener* by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="ece19-104">**Para exibir as propriedades do ouvinte, usando:**</span><span class="sxs-lookup"><span data-stu-id="ece19-104">**To view listener properties, using:**</span></span>  
  
     [<span data-ttu-id="ece19-105">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ece19-105">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ece19-106">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ece19-106">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ece19-107">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ece19-107">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ece19-108">**Para exibir as propriedades do ouvinte**</span><span class="sxs-lookup"><span data-stu-id="ece19-108">**To view listener properties**</span></span>  
  
1.  <span data-ttu-id="ece19-109">No Pesquisador de Objetos, conecte-se a uma instância de servidor que hospeda qualquer réplica de disponibilidade do grupo de disponibilidade cujo ouvinte você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="ece19-109">In Object Explorer, connect to a server instance that hosts any availability replica of the availability group whose listener you want to view.</span></span> <span data-ttu-id="ece19-110">Clique no nome do servidor para expandir a arvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="ece19-110">Click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ece19-111">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="ece19-111">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="ece19-112">Expanda o nó do grupo de disponibilidade e expanda o nó **Ouvintes de Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="ece19-112">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="ece19-113">Clique com o botão direito do mouse no ouvinte que você deseja exibir e selecione o comando **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="ece19-113">Right-click the listener that you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="ece19-114">Isso abre a caixa de diálogo **Propriedades do Ouvinte do Grupo de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="ece19-114">This opens the **Availability Group Listener Properties** dialog box.</span></span> <span data-ttu-id="ece19-115">Para obter mais informações, veja [Propriedades do Ouvinte do Grupo de Disponibilidade (caixa de diálogo)](#AgListenerPropertiesDialog), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ece19-115">For more information, see [Availability Group Listener Properties (Dialog Box)](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="availability-group-listener-properties-dialog-box"></a><a name="AgListenerPropertiesDialog"></a> <span data-ttu-id="ece19-116">Propriedades do Ouvinte do Grupo de Disponibilidade (caixa de diálogo)</span><span class="sxs-lookup"><span data-stu-id="ece19-116">Availability Group Listener Properties (Dialog Box)</span></span>  
 <span data-ttu-id="ece19-117">**Nome DNS do Ouvinte**</span><span class="sxs-lookup"><span data-stu-id="ece19-117">**Listener DNS Name**</span></span>  
 <span data-ttu-id="ece19-118">O nome da rede do ouvinte do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ece19-118">The network name of the availability group listener.</span></span>  
  
 <span data-ttu-id="ece19-119">**Porta**</span><span class="sxs-lookup"><span data-stu-id="ece19-119">**Port**</span></span>  
 <span data-ttu-id="ece19-120">A porta TCP usada pelo ouvinte.</span><span class="sxs-lookup"><span data-stu-id="ece19-120">The TCP port used by this listener.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ece19-121">Se você estiver conectado com a réplica primária, poderá usar esse campo para modificar o número da porta do ouvinte.</span><span class="sxs-lookup"><span data-stu-id="ece19-121">If you are connected the primary replica, you can use this field to modify the port number of the listener.</span></span> <span data-ttu-id="ece19-122">Isso exige a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ece19-122">This requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
 <span data-ttu-id="ece19-123">**Modo de Rede**</span><span class="sxs-lookup"><span data-stu-id="ece19-123">**Network Mode**</span></span>  
 <span data-ttu-id="ece19-124">Indica o protocolo TCP usado pelo ouvinte, pode ser:</span><span class="sxs-lookup"><span data-stu-id="ece19-124">Indicates the TCP protocol used by the listener, one of:</span></span>  
  
 <span data-ttu-id="ece19-125">**DHCP**</span><span class="sxs-lookup"><span data-stu-id="ece19-125">**DHCP**</span></span>  
 <span data-ttu-id="ece19-126">O ouvinte usa um endereço IP dinâmico que é atribuído por um servidor que executa o Protocolo DHCP.</span><span class="sxs-lookup"><span data-stu-id="ece19-126">The listener uses an dynamic IP address that is assigned by a server running the Dynamic Host Configuration Protocol (DHCP).</span></span>  
  
 <span data-ttu-id="ece19-127">**IP Estático**</span><span class="sxs-lookup"><span data-stu-id="ece19-127">**Static IP**</span></span>  
 <span data-ttu-id="ece19-128">O ouvinte usa um ou mais endereços IP estáticos.</span><span class="sxs-lookup"><span data-stu-id="ece19-128">The listener uses one or more Static IP addresses.</span></span> <span data-ttu-id="ece19-129">Para acessar diferentes sub-redes, um ouvinte de grupo de disponibilidade deve usar endereços IP estáticos.</span><span class="sxs-lookup"><span data-stu-id="ece19-129">To access the different subnets, an availability group listener must use static IP addresses.</span></span>  
  
 <span data-ttu-id="ece19-130">A grade exibe cada uma das sub-redes nas quais o ouvinte escuta, e o endereço IP associado àquela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="ece19-130">The grid displays each of the subnets on which the listener listens and the IP address associated with that subnet.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ece19-131">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ece19-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="ece19-132">**Para exibir as propriedades do ouvinte**</span><span class="sxs-lookup"><span data-stu-id="ece19-132">**To view listener properties**</span></span>  
  
 <span data-ttu-id="ece19-133">Para monitorar os ouvintes de disponibilidade, use as seguintes exibições:</span><span class="sxs-lookup"><span data-stu-id="ece19-133">To monitor the availability group listeners, use the following views:</span></span>  
  
 [<span data-ttu-id="ece19-134">sys.availability_group_listener_ip_addresses</span><span class="sxs-lookup"><span data-stu-id="ece19-134">sys.availability_group_listener_ip_addresses</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listener-ip-addresses-transact-sql)  
 <span data-ttu-id="ece19-135">Retorna uma linha para cada endereço IP virtual compatível que está online atualmente para um ouvinte de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ece19-135">Returns a row for every conformant virtual IP address that is currently online for an availability group listener.</span></span>  
  
 <span data-ttu-id="ece19-136">**Nomes de colunas:** listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span><span class="sxs-lookup"><span data-stu-id="ece19-136">**Column names:** listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span></span>  
  
 [<span data-ttu-id="ece19-137">sys.availability_group_listeners</span><span class="sxs-lookup"><span data-stu-id="ece19-137">sys.availability_group_listeners</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listeners-transact-sql)  
 <span data-ttu-id="ece19-138">Para um determinado grupo de disponibilidade, retorna zero linhas indicando que nenhum nome de rede está associado ao grupo de disponibilidade ou retorna uma linha para cada configuração de ouvinte de grupo de disponibilidade no cluster do WSFC.</span><span class="sxs-lookup"><span data-stu-id="ece19-138">For a given availability group, returns either zero rows indicating that no network name is associated with the availability group, or returns a row for each availability-group listener configuration in the WSFC cluster.</span></span>  
  
 <span data-ttu-id="ece19-139">**Nomes de colunas:** group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span><span class="sxs-lookup"><span data-stu-id="ece19-139">**Column names:** group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span></span>  
  
 [<span data-ttu-id="ece19-140">sys.dm_tcp_listener_states</span><span class="sxs-lookup"><span data-stu-id="ece19-140">sys.dm_tcp_listener_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tcp-listener-states-transact-sql)  
 <span data-ttu-id="ece19-141">Retorna uma linha que contém informações de estado dinâmico para cada ouvinte de TCP.</span><span class="sxs-lookup"><span data-stu-id="ece19-141">Returns a row containing dynamic-state information for each TCP listener.</span></span>  
  
 <span data-ttu-id="ece19-142">**Nomes de colunas:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span><span class="sxs-lookup"><span data-stu-id="ece19-142">**Column names:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ece19-143">Para obter mais informações sobre como usar o [!INCLUDE[tsql](../../../includes/tsql-md.md)] para monitorar seu ambiente do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , veja [Monitorar grupos de disponibilidade &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ece19-143">For more information about using [!INCLUDE[tsql](../../../includes/tsql-md.md)] to monitor your [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] environment, see [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ece19-144">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ece19-144">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ece19-145">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ece19-145">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="ece19-146">Remover um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ece19-146">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ece19-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ece19-147">See Also</span></span>  
 <span data-ttu-id="ece19-148">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ece19-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="ece19-149">[Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="ece19-149">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="ece19-150">Monitorar grupos de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ece19-150">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
