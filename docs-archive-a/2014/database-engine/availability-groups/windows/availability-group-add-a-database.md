---
title: Adicionar um banco de dados a um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 2a54eef8-9e8e-4e04-909c-6970112d55cc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0907cf711cac65ad77a8948841d92705fdc1eac9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569683"
---
# <a name="add-a-database-to-an-availability-group-sql-server"></a><span data-ttu-id="b4c48-102">Adicionar um banco de dados a um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4c48-102">Add a Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="b4c48-103">Este tópico descreve como adicionar um banco de dados a um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4c48-103">This topic describes how to add a database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="b4c48-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b4c48-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b4c48-105">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="b4c48-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="b4c48-106">Permissões</span><span class="sxs-lookup"><span data-stu-id="b4c48-106">Permissions</span></span>](#Permissions)  
  
-   <span data-ttu-id="b4c48-107">**Para adicionar um banco de dados a um grupo de disponibilidade usando:**</span><span class="sxs-lookup"><span data-stu-id="b4c48-107">**To add a database to an availability group, using:**</span></span>  
  
     [<span data-ttu-id="b4c48-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b4c48-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b4c48-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4c48-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b4c48-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4c48-110">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b4c48-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b4c48-111">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="b4c48-112">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="b4c48-112">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="b4c48-113">Você deve estar conectado à instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="b4c48-113">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="b4c48-114">O banco de dados deve residir na instância do servidor que hospeda a réplica primária e atender aos pré-requisitos e restrições para bancos de dados de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b4c48-114">The database must reside on the server instance that hosts the primary replica and comply with the prerequisites and restrictions for availability databases.</span></span> <span data-ttu-id="b4c48-115">Para obter mais informações, consulte [Pré-requisitos, restrições e recomendações para grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="b4c48-115">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b4c48-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="b4c48-116">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b4c48-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="b4c48-117">Permissions</span></span>  
 <span data-ttu-id="b4c48-118">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="b4c48-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b4c48-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b4c48-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b4c48-120">**Para adicionar um banco de dados a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="b4c48-120">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="b4c48-121">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="b4c48-121">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b4c48-122">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="b4c48-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="b4c48-123">Clique com o botão direito do mouse no grupo de disponibilidade e selecione um dos comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4c48-123">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="b4c48-124">Para iniciar o Assistente para Adicionar Banco de Dados a um Grupo de Disponibilidade, selecione o comando **Adicionar Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="b4c48-124">To launch the Add Database to Availability Group Wizard, select the **Add Database** command.</span></span> <span data-ttu-id="b4c48-125">Para obter mais informações, consulte [Usar o Assistente para Adicionar Banco de Dados ao Grupo de disponibilidade &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b4c48-125">For more information, see [Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span></span>  
  
    -   <span data-ttu-id="b4c48-126">Para adicionar um ou mais bancos de dados especificando-os na caixa de diálogo **Propriedades do Grupo de Disponibilidade** , selecione o comando **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="b4c48-126">To add one or more databases by specifying them in the **Availability Group Properties** dialog box, select the **Properties** command.</span></span> <span data-ttu-id="b4c48-127">As etapas para adicionar um banco de dados são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="b4c48-127">The steps for adding a database are as follows:</span></span>  
  
        1.  <span data-ttu-id="b4c48-128">No painel **Bancos de dados de Disponibilidade** , clique no botão **Adicionar** .</span><span class="sxs-lookup"><span data-stu-id="b4c48-128">In the **Availability Databases** pane, click the **Add** button.</span></span> <span data-ttu-id="b4c48-129">Isto cria e seleciona um campo de banco de dados em branco.</span><span class="sxs-lookup"><span data-stu-id="b4c48-129">This creates and selects a blank database field.</span></span>  
  
        2.  <span data-ttu-id="b4c48-130">Digite o nome de um banco de dados que atenda aos pré-requisitos dos bancos de dados de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b4c48-130">Enter the name of a database that meets the availability-databases prerequisites.</span></span>  
  
         <span data-ttu-id="b4c48-131">Para adicionar outro banco de dados, repita as etapas acima.</span><span class="sxs-lookup"><span data-stu-id="b4c48-131">To add another database, repeat the preceding steps.</span></span> <span data-ttu-id="b4c48-132">Ao concluir a especificação dos bancos de dados é feito, clique em **OK** para concluir a operação.</span><span class="sxs-lookup"><span data-stu-id="b4c48-132">When you are done specifying databases, click **OK** to complete the operation.</span></span>  
  
         <span data-ttu-id="b4c48-133">Depois que você usar a caixa de diálogo **Propriedades do Grupo de Disponibilidade** para adicionar um banco de dados a um grupo de disponibilidade, configure o banco de dados secundário correspondente em cada instância de servidor que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="b4c48-133">After you use the **Availability Group Properties** dialog box to add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="b4c48-134">Para obter mais informações, consulte [Iniciar movimentação de dados em um banco de dados secundário AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4c48-134">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b4c48-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4c48-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="b4c48-136">**Para adicionar um banco de dados a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="b4c48-136">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="b4c48-137">Conecte-se à instância de servidor que hospeda a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="b4c48-137">Connect to the server instance that hosts the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="b4c48-138">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b4c48-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="b4c48-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="b4c48-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span></span>  
  
     <span data-ttu-id="b4c48-140">em que *group_name* é o nome do grupo de disponibilidade e *database_name* é o nome de um banco de dados a ser adicionado ao grupo.</span><span class="sxs-lookup"><span data-stu-id="b4c48-140">where *group_name* is the name of the availability group and *database_name* is the name of a database to be added to the group.</span></span>  
  
     <span data-ttu-id="b4c48-141">O exemplo a seguir adiciona o banco de dados *MyDb3* ao grupo de disponibilidade *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="b4c48-141">The following example adds the *MyDb3* database to the *MyAG* availability group.</span></span>  
  
    ```  
    -- Connect to the server instance that hosts the primary replica.  
    -- Add an existing database to the availability group.  
    ALTER AVAILABILITY GROUP MyAG ADD DATABASE MyDb3;  
    GO  
    ```  
  
3.  <span data-ttu-id="b4c48-142">Depois que você adicionar um banco de dados a um grupo de disponibilidade, configure o banco de dados secundário correspondente em cada instância de servidor que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="b4c48-142">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="b4c48-143">Para obter mais informações, consulte [Iniciar movimentação de dados em um banco de dados secundário AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4c48-143">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="b4c48-144">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4c48-144">Using PowerShell</span></span>  
 <span data-ttu-id="b4c48-145">**Para adicionar um banco de dados a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="b4c48-145">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="b4c48-146">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="b4c48-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="b4c48-147">Use o cmdlet `Add-SqlAvailabilityDatabase`.</span><span class="sxs-lookup"><span data-stu-id="b4c48-147">Use the `Add-SqlAvailabilityDatabase` cmdlet.</span></span>  
  
     <span data-ttu-id="b4c48-148">Por exemplo, o comando a seguir adiciona o banco de dados secundário `MyDd` ao grupo de disponibilidade `MyAG` , cuja réplica primária é hospedada por `PrimaryServer\InstanceName`.</span><span class="sxs-lookup"><span data-stu-id="b4c48-148">For example, the following command adds the secondary database `MyDd` to the `MyAG` availability group, whose primary replica is hosted by `PrimaryServer\InstanceName`.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase `   
     -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAG `   
     -Database "MyDb"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4c48-149">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4c48-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="b4c48-150">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b4c48-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
3.  <span data-ttu-id="b4c48-151">Depois que você adicionar um banco de dados a um grupo de disponibilidade, configure o banco de dados secundário correspondente em cada instância de servidor que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="b4c48-151">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="b4c48-152">Para obter mais informações, consulte [Iniciar movimentação de dados em um banco de dados secundário AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4c48-152">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="b4c48-153">Para configurar e usar o provedor de SQL Server PowerShell, consulte [provedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="b4c48-153">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>

 <span data-ttu-id="b4c48-154">O exemplo a seguir mostra o processo completo para preparar um banco de dados secundário de um banco de dados na instância de servidor que hospeda a réplica primária de um grupo de disponibilidade, adicionando o banco de dados a um grupo de disponibilidade (como um banco de dados primário) e unindo o banco de dados secundário ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b4c48-154">The following example shows the full process for preparing a secondary database from a database on the server instance that hosts the primary replica of an availability group, adding the database to an availability group (as a primary database), and then joining the secondary database to the availability group.</span></span> <span data-ttu-id="b4c48-155">Primeiro, o exemplo faz backup do banco de dados e de seu log de transação.</span><span class="sxs-lookup"><span data-stu-id="b4c48-155">First, the example backs up the database and its transaction log.</span></span> <span data-ttu-id="b4c48-156">Em seguida, o exemplo restaura os backups de banco de dados e log para as instâncias de servidor que hospedam uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="b4c48-156">Then the example restores the database and log backups to the server instances that host a secondary replica.</span></span>  
  
 <span data-ttu-id="b4c48-157">O exemplo chama `Add-SqlAvailabilityDatabase` duas vezes: primeiro na réplica primária para adicionar o banco de dados ao grupo de disponibilidade e, em seguida, na réplica secundária para unir o banco de dados secundário nessa réplica para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="b4c48-157">The example calls `Add-SqlAvailabilityDatabase` twice: first on the primary replica to add the database to the availability group, and then on the secondary replica to join the secondary database on that replica to the availability group.</span></span> <span data-ttu-id="b4c48-158">Se você tiver mais de uma réplica secundária, restaure e junção una o banco de dados secundário em cada um deles.</span><span class="sxs-lookup"><span data-stu-id="b4c48-158">If you have more than one secondary replica, restore and join the secondary database on each of them.</span></span>  
  
```powershell
$DatabaseBackupFile = "\\share\backups\MyDatabase.bak"  
$LogBackupFile = "\\share\backups\MyDatabase.trn"  
$MyAgPrimaryPath = "SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
$MyAgSecondaryPath = "SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAg"  
  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "PrimaryServer\InstanceName"  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "PrimaryServer\InstanceName" -BackupAction 'Log'  
  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "SecondaryServer\InstanceName" -NoRecovery  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "SecondaryServer\InstanceName" -RestoreAction 'Log' -NoRecovery  
  
Add-SqlAvailabilityDatabase -Path $MyAgPrimaryPath -Database "MyDatabase"  
Add-SqlAvailabilityDatabase -Path $MyAgSecondaryPath -Database "MyDatabase"
```  
  
## <a name="see-also"></a><span data-ttu-id="b4c48-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4c48-159">See Also</span></span>  
 <span data-ttu-id="b4c48-160">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b4c48-160">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="b4c48-161">[Criação e configuração de grupos de disponibilidade &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b4c48-161">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="b4c48-162">[Use o painel AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b4c48-162">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="b4c48-163">Monitorar grupos de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c48-163">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
