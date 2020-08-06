---
title: Executar um failover manual planejado de um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.manualfailover.f1
helpviewer_keywords:
- Availability Groups [SQL Server], failover
- failover [SQL Server], AlwaysOn Availability Groups
ms.assetid: 419f655d-3f9a-4e7d-90b9-f0bab47b3178
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c62942eaa8f4ab4472bca5c7123e5999eb069216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681852"
---
# <a name="perform-a-planned-manual-failover-of-an-availability-group-sql-server"></a><span data-ttu-id="4a8dd-102">Executar um failover manual planejado de um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4a8dd-102">Perform a Planned Manual Failover of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="4a8dd-103"> Este tópico descreve como executar um failover manual sem perda de dados (um *failover manual planejado*) em um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a8dd-103">This topic describes how to perform a manual failover without data loss (a *planned manual failover*) on an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4a8dd-104">Um grupo de disponibilidade faz failover no nível de uma réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-104">An availability group fails over at the level of an availability replica.</span></span> <span data-ttu-id="4a8dd-105">Um failover manual planejado, como qualquer failover do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , faz a transição de uma réplica secundária e, simultaneamente, faz a transição da réplica primária antiga para a função secundária.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-105">A planned manual failover, like any [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] failover, transitions a secondary replica to primary role and, concurrently, transitions the former primary replica to the secondary role.</span></span>  
  
 <span data-ttu-id="4a8dd-106">Um failover manual planejado, que é suportado apenas quando a réplica primária e a réplica secundária de destino estão executando em modo de confirmação síncrona e estão sincronizadas no momento, preserva todos os dados nos bancos de dados secundários que estão unidos ao grupo de disponibilidade em uma réplica secundária de destino.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-106">A planned manual failover, which is supported only when the primary replica and the target secondary replica are running in synchronous-commit mode and are currently synchronized, preserves all the data in the secondary databases that are joined to the availability group on the target secondary replica.</span></span> <span data-ttu-id="4a8dd-107">Quando a réplica primária antiga faz a transição para a função secundária, seus bancos de dados se tornam bancos de dados secundários e começam a ser sincronizados com os novos bancos de dados primários.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-107">Once the former primary replica transitions to the secondary role, its databases become secondary databases and begin synchronizing with the new primary databases.</span></span> <span data-ttu-id="4a8dd-108">Depois que a transição de todos é feita para o estado SYNCHRONIZED, a nova réplica secundária se torna qualificada para servir como o destino de uma futuro failover manual planejado.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-108">After they all transition into the SYNCHRONIZED state, the new secondary replica becomes eligible to serve as the target of a future planned manual failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a8dd-109">Se as réplicas secundárias e primárias estiverem configuradas para o modo de failover automático, quando a réplica secundária for sincronizada, ela também poderá servir como o destino de um failover automático.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-109">If the secondary and primary replicas are both configured for automatic failover mode, once the secondary replica is synchronized, it can also serve as the target for an automatic failover.</span></span> <span data-ttu-id="4a8dd-110">Para obter mais informações, consulte [Modos de disponibilidade &#40;Grupos de Disponibilidade AlwaysOn&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="4a8dd-110">For more information, see [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4a8dd-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4a8dd-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4a8dd-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="4a8dd-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4a8dd-113">Um comando de failover é retornado assim que a réplica secundária de destino aceitar o comando.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-113">A failover command returns as soon as the target secondary replica has accepted the command.</span></span> <span data-ttu-id="4a8dd-114">No entanto, a recuperação de banco de dados ocorre de forma assíncrona depois que o grupo de disponibilidade terminar o failover.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-114">However, database recovery occurs asynchronously after the availability group has finished failing over.</span></span>  
  
-   <span data-ttu-id="4a8dd-115">A consistência do banco de dados entre bancos de dados dentro do grupo de disponibilidade não é mantida no failover.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-115">Cross-database consistency across databases within the availability group is not maintained on failover.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4a8dd-116">Não há suporte para transações entre bancos de dados e transações distribuídas no [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a8dd-116">Cross-database transactions and distributed transactions are not supported by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="4a8dd-117">Para obter mais informações, consulte [Transações envolvendo todos os bancos de dados sem suporte para espelhamento de banco de dados ou Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="4a8dd-117">For more information, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="4a8dd-118">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="4a8dd-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="4a8dd-119">A réplica secundária de destino e a réplica primária devem estar executando em modo de disponibilidade de confirmação síncrona.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-119">The target secondary replica and the primary replica must both be running in synchronous-commit availability mode.</span></span>  
  
-   <span data-ttu-id="4a8dd-120">A réplica primária de destino deve estar sincronizada com a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-120">The target secondary replica must currently be synchronized with the primary replica.</span></span> <span data-ttu-id="4a8dd-121">Isso requer que todos os bancos de dados secundários dessa réplica secundária ao grupo tenham sido unidos ao grupo de disponibilidade e tenham sido sincronizados com os bancos de dados primários correspondentes (quer dizer, os bancos de dados secundários locais devem estar SYNCHRONIZED).</span><span class="sxs-lookup"><span data-stu-id="4a8dd-121">This requires that all the secondary databases on this secondary replica must have been joined to the availability group and be synchronized with their corresponding primary databases (that is, the local secondary databases must be SYNCHRONIZED).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="4a8dd-122">Para determinar a prontidão do failover de uma réplica secundária, consulte a coluna **is_failover_ready** na exibição de gerenciamento dinâmico [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) ou consulte a coluna **Prontidão de Failover** do [Painel de Grupo AlwaysOn](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4a8dd-122">To determine the failover readiness of an secondary replica, query the **is_failover_ready** column in the [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) dynamic management view, or look at the **Failover Readiness** column of the [AlwaysOn Group Dashboard](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
-   <span data-ttu-id="4a8dd-123">Esta tarefa tem suporte apenas na réplica secundária de destino.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-123">This task is supported only on the target secondary replica.</span></span> <span data-ttu-id="4a8dd-124">Você deve estar conectado à instância de servidor que hospeda a réplica secundária de destino.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-124">You must be connected to the server instance that hosts the target secondary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4a8dd-125">Segurança</span><span class="sxs-lookup"><span data-stu-id="4a8dd-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4a8dd-126">Permissões</span><span class="sxs-lookup"><span data-stu-id="4a8dd-126">Permissions</span></span>  
 <span data-ttu-id="4a8dd-127">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-127">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4a8dd-128">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a8dd-128">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4a8dd-129">**Para fazer o failover de um grupo de disponibilidade manualmente**</span><span class="sxs-lookup"><span data-stu-id="4a8dd-129">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="4a8dd-130">No Pesquisador de Objetos, conecte-se a uma instância do servidor que hospeda uma réplica secundária do grupo de disponibilidade que precise passar por failover e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-130">In Object Explorer, connect to a server instance that hosts a secondary replica of the availability group that needs to be failed over, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="4a8dd-131">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="4a8dd-131">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="4a8dd-132">Clique com o botão direito do mouse no grupo de disponibilidade do qual fazer failover e selecione o comando **Failover** .</span><span class="sxs-lookup"><span data-stu-id="4a8dd-132">Right-click the availability group to be failed over, and select the **Failover** command.</span></span>  
  
4.  <span data-ttu-id="4a8dd-133">Isso inicia o Assistente de Grupo de Disponibilidade de Failover.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-133">This launches the Failover Availability Group Wizard.</span></span> <span data-ttu-id="4a8dd-134">Para obter mais informações, veja [Usar o Assistente para Executar Failover de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4a8dd-134">For more information, see [Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4a8dd-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a8dd-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="4a8dd-136">**Para fazer o failover de um grupo de disponibilidade manualmente**</span><span class="sxs-lookup"><span data-stu-id="4a8dd-136">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="4a8dd-137">Conecte-se à instância do servidor que hospeda a réplica secundária de destino.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-137">Connect to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="4a8dd-138">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4a8dd-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="4a8dd-139">ALTER AVAILABILITY GROUP *group_name* FAILOVER</span><span class="sxs-lookup"><span data-stu-id="4a8dd-139">ALTER AVAILABILITY GROUP *group_name* FAILOVER</span></span>  
  
     <span data-ttu-id="4a8dd-140">em que *group_name* é o nome do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-140">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="4a8dd-141">O exemplo a seguir faz failover manual do grupo de disponibilidade *MyAg* para a réplica secundária conectada.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-141">The following example manually fails over the *MyAg* availability group to the connected secondary replica.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAg FAILOVER;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4a8dd-142">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a8dd-142">Using PowerShell</span></span>  
 <span data-ttu-id="4a8dd-143">**Para fazer o failover de um grupo de disponibilidade manualmente**</span><span class="sxs-lookup"><span data-stu-id="4a8dd-143">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="4a8dd-144">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica secundária de destino.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-144">Change directory (`cd`) to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="4a8dd-145">Use o cmdlet `Switch-SqlAvailabilityGroup`.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-145">Use the `Switch-SqlAvailabilityGroup` cmdlet.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4a8dd-146">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="4a8dd-147">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4a8dd-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
     <span data-ttu-id="4a8dd-148">O exemplo a seguir faz failover manual do grupo de disponibilidade *MyAg* para a réplica secundária com o caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-148">The following example manually fails over the *MyAg* availability group to the secondary replica with the specified path.</span></span>  
  
    ```powershell
    Switch-SqlAvailabilityGroup -Path SQLSERVER:\Sql\SecondaryServer\InstanceName\AvailabilityGroups\MyAg  
    ```  
  
 <span data-ttu-id="4a8dd-149">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4a8dd-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="4a8dd-150">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a8dd-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="4a8dd-151">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a8dd-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="follow-up-after-manually-failing-over-an-availability-group"></a><a name="FollowUp"></a> <span data-ttu-id="4a8dd-152">Acompanhamento: após o failover manual de um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="4a8dd-152">Follow Up: After Manually Failing Over an Availability Group</span></span>  
 <span data-ttu-id="4a8dd-153">Se você fez failover fora do [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] do grupo de disponibilidade, ajuste os votos de quorum dos nós WSFC para refletir sua nova configuração de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="4a8dd-153">If you failed over outside of the [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] of the availability group, adjust the quorum votes of the WSFC nodes to reflect your new availability group configuration.</span></span> <span data-ttu-id="4a8dd-154">Para obter mais informações, consulte [Clustering de Failover do Windows Server &#40;WSFC&#41; com SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4a8dd-154">For more information, see [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8dd-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a8dd-155">See Also</span></span>  
 <span data-ttu-id="4a8dd-156">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4a8dd-156">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="4a8dd-157">[Failover e modos de failover &#40;Grupos de Disponibilidade AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="4a8dd-157">[Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="4a8dd-158">Executar um failover manual forçado de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4a8dd-158">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
