---
title: Ingressar uma réplica secundária em um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joinreplica.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
ms.assetid: e5bd2489-097a-490e-8ea1-34fe48378ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c38c2d59a46b15fc9a1dca77ae6a67e8e59e1b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573271"
---
# <a name="join-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="3d034-102">Unir uma réplica secundária a um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3d034-102">Join a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="3d034-103">Este tópico descreve como unir uma réplica secundária a um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d034-103">This topic describes how to join a secondary replica to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="3d034-104">Depois que uma réplica secundária é adicionada a um grupo de disponibilidade AlwaysOn, a réplica secundária deve ser unida ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3d034-104">After a secondary replica is added to an AlwaysOn availability group, the secondary replica must be joined to the availability group.</span></span> <span data-ttu-id="3d034-105">A operação para unir réplica deve ser executada na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que está hospedando a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="3d034-105">The join-replica operation must be performed on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting the secondary replica.</span></span>  
  
-   <span data-ttu-id="3d034-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3d034-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3d034-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3d034-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="3d034-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="3d034-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3d034-109">**Para preparar um banco de dados secundário, usando:**</span><span class="sxs-lookup"><span data-stu-id="3d034-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="3d034-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d034-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3d034-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3d034-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="3d034-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d034-112">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="3d034-113">**Acompanhamento:** [Configurar bancos de dados secundários](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="3d034-113">**Follow Up:** [Configure Secondary Databases](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3d034-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3d034-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3d034-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3d034-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="3d034-116">A réplica primária do grupo de disponibilidade deve estar online no momento.</span><span class="sxs-lookup"><span data-stu-id="3d034-116">The primary replica of the availability group must currently be online.</span></span>  
  
-   <span data-ttu-id="3d034-117">Você deve estar conectado à instância de servidor que hospeda uma réplica secundária que ainda não foi unida ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3d034-117">You must be connected to the server instance that hosts a secondary replica that has not yet have been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="3d034-118">A instância de servidor local deve ser capaz de se conectar ao ponto de extremidade de espelhamento de banco de dados da instância de servidor que está hospedando a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="3d034-118">The local server instance must be able to connect to the database mirroring endpoint of the server instance that is hosting the primary replica.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3d034-119">Se qualquer pré-requisito não for atendido, a operação de junção falhará.</span><span class="sxs-lookup"><span data-stu-id="3d034-119">If any prerequisite is not met, the join operation fails.</span></span> <span data-ttu-id="3d034-120">Após uma tentativa de junção com falha, talvez seja necessário conectar a instância do servidor que hospeda a réplica primária para remover e adicionar novamente a réplica secundária antes que seja possível uni-la ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3d034-120">After a failed join attempt, you might need to connect to the server instance that hosts the primary replica to remove and re-add the secondary replica before you can join it to the availability group.</span></span> <span data-ttu-id="3d034-121">Para obter mais informações, veja [Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) e [Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3d034-121">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) and [Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3d034-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="3d034-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3d034-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="3d034-123">Permissions</span></span>  
 <span data-ttu-id="3d034-124">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="3d034-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3d034-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d034-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3d034-126">**Para unir uma réplica de disponibilidade a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="3d034-126">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="3d034-127">No Pesquisador de Objetos, conecte-se à instância do servidor que hospeda a réplica secundária e clique no nome do servidor para expandir a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="3d034-127">In Object Explorer, connect to the server instance that hosts the secondary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3d034-128">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="3d034-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="3d034-129">Selecione o grupo de disponibilidade da réplica secundária à qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="3d034-129">Select the availability group of the secondary replica to which you are connected.</span></span>  
  
4.  <span data-ttu-id="3d034-130">Clique com o botão direito do mouse na réplica secundária e clique em **Unir a Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="3d034-130">Right-click the secondary replica, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="3d034-131">Isso abre a caixa de diálogo **Unir Réplica a Grupo de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="3d034-131">This opens the **Join Replica to Availability Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="3d034-132">Para unir a réplica secundária ao grupo de disponibilidade, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d034-132">To join the secondary replica to the availability group, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3d034-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3d034-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="3d034-134">**Para unir uma réplica de disponibilidade a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="3d034-134">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="3d034-135">Conecte-se à instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="3d034-135">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="3d034-136">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3d034-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="3d034-137">ALTER AVAILABILITY GROUP *group_name* JOIN</span><span class="sxs-lookup"><span data-stu-id="3d034-137">ALTER AVAILABILITY GROUP *group_name* JOIN</span></span>  
  
     <span data-ttu-id="3d034-138">em que *group_name* é o nome do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3d034-138">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="3d034-139">O exemplo a seguir une a réplica secundária ao grupo de disponibilidade `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="3d034-139">The following example, joins the secondary replica to the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="3d034-140">Para ver esta instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] usada no contexto, veja [Criar um grupo de disponibilidade &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3d034-140">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="3d034-141">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d034-141">Using PowerShell</span></span>  
 <span data-ttu-id="3d034-142">**Para unir uma réplica de disponibilidade a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="3d034-142">**To join an availability replica to an availability group**</span></span>  
  
 <span data-ttu-id="3d034-143">No provedor do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d034-143">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="3d034-144">Altere o diretório (`cd`) para a instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="3d034-144">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="3d034-145">Una a réplica secundária ao grupo de disponibilidade executando o cmdlet **Join-SqlAvailabilityGroup** com o nome do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3d034-145">Join the secondary replica to the availability group by executing the **Join-SqlAvailabilityGroup** cmdlet with the name of the availability group.</span></span>  
  
     <span data-ttu-id="3d034-146">Por exemplo, o comando a seguir une a réplica secundária hospedada pela instância de servidor localizada no caminho especificado ao grupo de disponibilidade denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="3d034-146">For example, the following command joins a secondary replica hosted by the server instance located at the specified path to the availability group named `MyAg`.</span></span>  <span data-ttu-id="3d034-147">Essa instância de servidor deve hospedar uma réplica secundária neste grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3d034-147">This server instance must host a secondary replica in this availability group.</span></span>  
  
    ```powershell
    Join-SqlAvailabilityGroup -Path SQLSERVER:\SQL\SecondaryServer\InstanceName -Name 'MyAg'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="3d034-148">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d034-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="3d034-149">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3d034-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="3d034-150">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3d034-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="3d034-151">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d034-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-configure-secondary-databases"></a><a name="FollowUp"></a><span data-ttu-id="3d034-152">Acompanhamento: configurar bancos de dados secundários</span><span class="sxs-lookup"><span data-stu-id="3d034-152">Follow Up: Configure Secondary Databases</span></span>  
 <span data-ttu-id="3d034-153">Para cada banco de dados do grupo de disponibilidade, você precisa de um banco de dados secundário na instância de servidor que está hospedando a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="3d034-153">For every database in the availability group, you need a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="3d034-154">Você pode configurar bancos de dados secundários antes ou depois que une uma réplica secundária a um grupo de disponibilidade, da seguinte maneira</span><span class="sxs-lookup"><span data-stu-id="3d034-154">You can configure secondary databases either before or after you join a secondary replica to an availability group, as follows:</span></span>  
  
1.  <span data-ttu-id="3d034-155">Restaure o banco de dados e os backups de log recentes de cada banco de dados primário na instância de servidor que hospeda a réplica secundária, usando RESTORE WITH NORECOVERY em cada operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="3d034-155">Restore recent database and log backups of each primary database onto the server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="3d034-156">Para obter mais informações, consulte [Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3d034-156">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="3d034-157">Una cada banco de dados secundário ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3d034-157">Join each secondary database to the availability group.</span></span> <span data-ttu-id="3d034-158">Para obter mais informações, consulte [Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3d034-158">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d034-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3d034-159">See Also</span></span>  
 <span data-ttu-id="3d034-160">[Criação e configuração de grupos de disponibilidade &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3d034-160">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="3d034-161">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3d034-161">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="3d034-162">Solucionar problemas de &#40;de configuração de Grupos de Disponibilidade AlwaysOn SQL Server&#41;excluídos</span><span class="sxs-lookup"><span data-stu-id="3d034-162">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
