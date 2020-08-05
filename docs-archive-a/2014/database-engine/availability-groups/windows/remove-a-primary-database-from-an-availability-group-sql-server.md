---
title: Remover um banco de dados primário de um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeprimarydb.f1
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 6d4ca31e-ddf0-44bf-be5e-a5da060bf096
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6fafaf6464431d68f8cfdf9dc9d8fa844a42a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571609"
---
# <a name="remove-a-primary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="e1ae1-102">Remover um banco de dados primário de um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e1ae1-102">Remove a Primary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="e1ae1-103">Este tópico descreve como remover o banco de dados primário e os bancos de dados secundários correspondentes de um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1ae1-103">This topic describes how to remove both the primary database and the corresponding secondary database(s) from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="e1ae1-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="e1ae1-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e1ae1-105">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="e1ae1-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="e1ae1-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="e1ae1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e1ae1-107">**Para remover um banco de dados de disponibilidade usando:**</span><span class="sxs-lookup"><span data-stu-id="e1ae1-107">**To remove an availability database, using:**</span></span>  
  
     [<span data-ttu-id="e1ae1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1ae1-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e1ae1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1ae1-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="e1ae1-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ae1-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="e1ae1-111">**Acompanhamento:**  [depois de remover um banco de dados de disponibilidade de um grupo de disponibilidade](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="e1ae1-111">**Follow Up:**  [After Removing an Availability Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e1ae1-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e1ae1-112">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="e1ae1-113">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="e1ae1-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="e1ae1-114">Esta tarefa tem suporte apenas em réplicas primárias.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-114">This task is supported only on primary replicas.</span></span> <span data-ttu-id="e1ae1-115">Você deve estar conectado à instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e1ae1-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="e1ae1-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e1ae1-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="e1ae1-117">Permissions</span></span>  
 <span data-ttu-id="e1ae1-118">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e1ae1-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1ae1-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="e1ae1-120">**Para remover um banco de dados de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="e1ae1-120">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="e1ae1-121">No Pesquisador de Objetos, conecte-se à instância do servidor que hospeda a réplica primária do banco de dados ou bancos de dados a serem removidos e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-121">In Object Explorer, connect to the server instance that hosts the primary replica of the database or databases to be removed, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e1ae1-122">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="e1ae1-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="e1ae1-123">Selecione o grupo de disponibilidade e expanda o nó **Bancos de Dados de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="e1ae1-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="e1ae1-124">Essa etapa depende de se você deseja remover vários grupos de bancos de dados ou apenas um banco de dados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e1ae1-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="e1ae1-125">Para remover vários bancos de dados, use o painel **Detalhes do Pesquisador de Objetos** para exibir e selecionar todos os bancos de dados que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="e1ae1-126">Para obter mais informações, veja [Usar os detalhes do Pesquisador de Objetos para monitorar grupos de disponibilidade &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e1ae1-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="e1ae1-127">Para remover um único banco de dados, selecione-o no painel **Pesquisador de Objetos** ou no painel **Detalhes do Pesquisador de Objetos** .</span><span class="sxs-lookup"><span data-stu-id="e1ae1-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="e1ae1-128">Clique com o botão direito do mouse no banco de dados ou bancos de dados selecionados e selecione **Remover Banco de Dados do Grupo de Disponibilidade** no menu de comando.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-128">Right-click the selected database or databases, and select **Remove Database from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="e1ae1-129">Na caixa de diálogo **Remover Bancos de Dados do Grupo de Disponibilidade** , para remover todos os bancos de dados listados, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-129">In the **Remove Databases from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="e1ae1-130">Se você não desejar remover todos os bancos de dados listados, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-130">If you do not want to remove all them, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e1ae1-131">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1ae1-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="e1ae1-132">**Para remover um banco de dados de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="e1ae1-132">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="e1ae1-133">Conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-133">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="e1ae1-134">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e1ae1-134">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="e1ae1-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span><span class="sxs-lookup"><span data-stu-id="e1ae1-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span></span>  
  
     <span data-ttu-id="e1ae1-136">em que *group_name* é o nome do grupo de disponibilidade e *database_name* é o nome do banco de dados a ser removido.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-136">where *group_name* is the name of the availability group and *database_name* is the name of the database to be removed.</span></span>  
  
     <span data-ttu-id="e1ae1-137">O exemplo a seguir remove um banco de dados denominado `Db6` do grupo de disponibilidade `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="e1ae1-137">The following example removes a databases named `Db6` from the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE DATABASE Db6;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="e1ae1-138">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ae1-138">Using PowerShell</span></span>  
 <span data-ttu-id="e1ae1-139">**Para remover um banco de dados de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="e1ae1-139">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="e1ae1-140">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-140">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="e1ae1-141">Use o cmdlet `Remove-SqlAvailabilityDatabase`, especificando o nome do banco de dados de disponibilidade a ser removido do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-141">Use the `Remove-SqlAvailabilityDatabase` cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="e1ae1-142">Quando você está conectado a uma instância do servidor que hospeda a réplica primária, o banco de dados primário e os bancos de dados secundários correspondentes são todos removidos do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-142">When you are connected to the server instance that hosts the primary replica, the primary database and its corresponding secondary databases are all removed from the availability group.</span></span>  
  
     <span data-ttu-id="e1ae1-143">Por exemplo, o comando a seguir remove o banco de dados de disponibilidade `MyDb9` do grupo de disponibilidade denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-143">For example, the following command removes the availability database `MyDb9` from the availability group named `MyAg`.</span></span> <span data-ttu-id="e1ae1-144">Como o comando é executado na instância do servidor que hospeda a réplica primária, o banco de dados primário e todos os bancos de dados secundários correspondentes são removidos do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-144">Because the command is executed on the server instance that hosts the primary replica, the primary database and all its corresponding secondary databases are removed from the availability group.</span></span> <span data-ttu-id="e1ae1-145">A sincronização de dados não ocorrerá mais para este banco de dados em nenhuma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-145">Data synchronization will no longer occur for this database on any secondary replica.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\PrimaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb9  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="e1ae1-146">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="e1ae1-147">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e1ae1-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="e1ae1-148">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e1ae1-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="e1ae1-149">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ae1-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-an-availability-database-from-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="e1ae1-150">Acompanhamento: depois de remover um banco de dados de disponibilidade de um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="e1ae1-150">Follow Up: After Removing an Availability Database from an Availability Group</span></span>  
 <span data-ttu-id="e1ae1-151">A remoção de um banco de dados de disponibilidade do grupo de disponibilidade termina a sincronização de dados entre o banco de dados primário antigo e os bancos de dados secundários correspondentes.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-151">Removing an availability database from its availability group ends data synchronization between the former primary database and the corresponding secondary databases.</span></span> <span data-ttu-id="e1ae1-152">O banco de dados primário antigo permanece online.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-152">The former primary database remains online.</span></span> <span data-ttu-id="e1ae1-153">Todos os bancos de dados secundários correspondentes são colocados no estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-153">Every corresponding secondary database is placed in the RESTORING state.</span></span>  
  
 <span data-ttu-id="e1ae1-154">Neste ponto, há maneiras alternativas de lidar com um banco de dados secundário removido:</span><span class="sxs-lookup"><span data-stu-id="e1ae1-154">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="e1ae1-155">Se você não precisar mais de um determinado banco de dados secundário, você poderá removê-lo.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-155">If you no longer need a given secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="e1ae1-156">Para obter mais informações, veja [Excluir um banco de dados](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="e1ae1-156">For more information, see [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="e1ae1-157">Se desejar acessar um banco de dados secundário depois que ele foi removido do grupo de disponibilidade, você poderá recuperá-lo.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-157">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="e1ae1-158">No entanto, se você recuperar um banco de dados secundário removido, dois bancos de dados independentes divergentes com o mesmo nome estarão online.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-158">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="e1ae1-159">Você deve verificar se os clientes podem acessar só um deles, normalmente o banco de dados primário mais recente.</span><span class="sxs-lookup"><span data-stu-id="e1ae1-159">You must make sure that clients can access only one of them, typically the most recent primary database.</span></span>  
  
     <span data-ttu-id="e1ae1-160">Para obter mais informações, veja [Recuperar um banco de dados sem restaurar dados &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="e1ae1-160">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ae1-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1ae1-161">See Also</span></span>  
 <span data-ttu-id="e1ae1-162">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e1ae1-162">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="e1ae1-163">Remover um banco de dados secundário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1ae1-163">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
