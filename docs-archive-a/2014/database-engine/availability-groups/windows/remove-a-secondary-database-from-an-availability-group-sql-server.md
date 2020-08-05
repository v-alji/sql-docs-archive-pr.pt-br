---
title: Remover um banco de dados secundário de um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.unjoindb.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], databases
ms.assetid: 4e51a570-58d7-4f01-9390-4198f3602576
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1c3de0afd73b46ae5594d26d1763f5bd78483efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571607"
---
# <a name="remove-a-secondary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="68f9f-102">Remover um banco de dados primário de um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="68f9f-102">Remove a Secondary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="68f9f-103">Este tópico descreve como remover um banco de dados secundário de um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68f9f-103">This topic describes how to remove a secondary database from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="68f9f-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="68f9f-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="68f9f-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="68f9f-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="68f9f-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="68f9f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="68f9f-107">**Para remover um banco de dados secundário usando:**</span><span class="sxs-lookup"><span data-stu-id="68f9f-107">**To remove a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="68f9f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68f9f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="68f9f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68f9f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="68f9f-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f9f-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="68f9f-111">**Acompanhamento:**  [depois de remover um banco de dados secundário de um grupo de disponibilidade](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="68f9f-111">**Follow Up:**  [After Removing a Secondary Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="68f9f-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="68f9f-112">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>   
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="68f9f-113">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="68f9f-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="68f9f-114">Esta tarefa tem suporte apenas em réplicas secundárias.</span><span class="sxs-lookup"><span data-stu-id="68f9f-114">This task is supported only on secondary replicas.</span></span> <span data-ttu-id="68f9f-115">Você deve estar conectado à instância do servidor que hospeda a réplica secundária da qual o banco de dados deve ser removido.</span><span class="sxs-lookup"><span data-stu-id="68f9f-115">You must be connected to the server instance that hosts the secondary replica from which the database is to be removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="68f9f-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="68f9f-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="68f9f-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="68f9f-117">Permissions</span></span>  
 <span data-ttu-id="68f9f-118">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="68f9f-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="68f9f-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68f9f-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="68f9f-120">**Para remover um banco de dados secundário de um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="68f9f-120">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="68f9f-121">Em Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica secundária da qual você deseja remover um ou mais bancos de dados secundários e expanda a árvore de servidor.</span><span class="sxs-lookup"><span data-stu-id="68f9f-121">In Object Explorer, connect to the server instance that hosts the secondary replica from which you want to remove one or more secondary databases, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="68f9f-122">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="68f9f-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="68f9f-123">Selecione o grupo de disponibilidade e expanda o nó **Bancos de Dados de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="68f9f-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="68f9f-124">Essa etapa depende de se você deseja remover vários grupos de bancos de dados ou apenas um banco de dados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="68f9f-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="68f9f-125">Para remover vários bancos de dados, use o painel **Detalhes do Pesquisador de Objetos** para exibir e selecionar todos os bancos de dados que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="68f9f-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="68f9f-126">Para obter mais informações, veja [Usar os detalhes do Pesquisador de Objetos para monitorar grupos de disponibilidade &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="68f9f-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="68f9f-127">Para remover um único banco de dados, selecione-o no painel **Pesquisador de Objetos** ou no painel **Detalhes do Pesquisador de Objetos** .</span><span class="sxs-lookup"><span data-stu-id="68f9f-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="68f9f-128">Clique com o botão direito do mouse no banco de dados ou bancos de dados selecionados e selecione **Remover Banco de Dados Secundário** no menu de comando.</span><span class="sxs-lookup"><span data-stu-id="68f9f-128">Right-click the selected database or databases, and select **Remove Secondary Database** in the command menu.</span></span>  
  
6.  <span data-ttu-id="68f9f-129">Na caixa de diálogo **Remover Banco de Dados do Grupo de Disponibilidade** , para remover todos os bancos de dados listados, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="68f9f-129">In the **Remove Database from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="68f9f-130">Se você não desejar remover todos os bancos de dados listados, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="68f9f-130">If you do not want to remove all the listed databases, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="68f9f-131">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68f9f-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="68f9f-132">**Para remover um banco de dados secundário de um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="68f9f-132">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="68f9f-133">Conecte-se à instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="68f9f-133">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="68f9f-134">Use a [cláusula SET HADR da instrução ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="68f9f-134">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="68f9f-135">ALTER DATABASE *database_name* SET HADR OFF</span><span class="sxs-lookup"><span data-stu-id="68f9f-135">ALTER DATABASE *database_name* SET HADR OFF</span></span>  
  
     <span data-ttu-id="68f9f-136">em que *database_name* é o nome de um banco de dados secundário a ser removido do grupo de disponibilidade ao qual pertence.</span><span class="sxs-lookup"><span data-stu-id="68f9f-136">where *database_name* is the name of a secondary database to be removed from the availability group to which it belongs.</span></span>  
  
     <span data-ttu-id="68f9f-137">O exemplo a seguir remove o banco de dados secundário local *MyDb2* de seu grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="68f9f-137">The following example removes the local secondary database *MyDb2* from its availability group.</span></span>  
  
    ```sql
    ALTER DATABASE MyDb2 SET HADR OFF;  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="68f9f-138">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f9f-138">Using PowerShell</span></span>  
 <span data-ttu-id="68f9f-139">**Para remover um banco de dados secundário de um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="68f9f-139">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="68f9f-140">Altere o diretório (`cd`) para a instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="68f9f-140">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="68f9f-141">Use o cmdlet **Remove-SqlAvailabilityDatabase** , especificando o nome do banco de dados de disponibilidade a ser removido do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="68f9f-141">Use the **Remove-SqlAvailabilityDatabase** cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="68f9f-142">Quando você está conectado a uma instância do servidor que hospeda uma réplica secundária, apenas o banco de dados secundário local é removido do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="68f9f-142">When you are connected to a server instance that hosts a secondary replica, only the local secondary database is removed from the availability group.</span></span>  
  
     <span data-ttu-id="68f9f-143">Por exemplo, o comando a seguir remove o banco de dados secundário `MyDb8` da réplica secundária hospedada pela instância de servidor denominada `SecondaryComputer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="68f9f-143">For example, the following command removes the secondary database `MyDb8` from the secondary replica hosted by the server instance named `SecondaryComputer\Instance`.</span></span> <span data-ttu-id="68f9f-144">A sincronização de dados para os bancos de dados secundários removidos é encerrada.</span><span class="sxs-lookup"><span data-stu-id="68f9f-144">Data synchronization to the removed secondary databases ceases.</span></span> <span data-ttu-id="68f9f-145">Este comando não afeta o banco de dados primário ou nenhum outro banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="68f9f-145">This command does not affect the primary database or any other secondary databases.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\SecondaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb8  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="68f9f-146">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f9f-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="68f9f-147">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="68f9f-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="68f9f-148">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="68f9f-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="68f9f-149">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f9f-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-database-from-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="68f9f-150">Acompanhamento: depois de remover um banco de dados secundário de um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="68f9f-150">Follow Up: After Removing a Secondary Database from an Availability Group</span></span>  
 <span data-ttu-id="68f9f-151">Quando um banco de dados secundário é removido, ele não é mais unido ao grupo de disponibilidade, e todas as informações sobre o banco de dados secundário removido são descartadas pelo grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="68f9f-151">When a secondary database is removed, it is no longer joined to the availability group and all information about the removed secondary database is discarded by the availability group.</span></span> <span data-ttu-id="68f9f-152">O banco de dados secundário removido é colocado no estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="68f9f-152">The removed secondary database is placed in the RESTORING state.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="68f9f-153">Pouco tempo depois de remover um banco de dados secundário, você poderá reiniciar a sincronização de dados AlwaysOn no banco de dados reassociando-o ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="68f9f-153">For a short time after removing a secondary database, you might be able to restart AlwaysOn data synchronization on the database by re-joining it to the availability group.</span></span> <span data-ttu-id="68f9f-154">Para obter mais informações, consulte [Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="68f9f-154">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="68f9f-155">Neste ponto, há maneiras alternativas de lidar com um banco de dados secundário removido:</span><span class="sxs-lookup"><span data-stu-id="68f9f-155">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="68f9f-156">Se você não precisar mais do banco de dados secundário, você poderá removê-lo.</span><span class="sxs-lookup"><span data-stu-id="68f9f-156">If you no longer need the secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="68f9f-157">Para obter mais informações, consulte [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) ou [Excluir um banco de dados](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="68f9f-157">For more information, see [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) or [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="68f9f-158">Se desejar acessar um banco de dados secundário depois que ele foi removido do grupo de disponibilidade, você poderá recuperá-lo.</span><span class="sxs-lookup"><span data-stu-id="68f9f-158">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="68f9f-159">No entanto, se você recuperar um banco de dados secundário removido, dois bancos de dados independentes divergentes com o mesmo nome estarão online.</span><span class="sxs-lookup"><span data-stu-id="68f9f-159">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="68f9f-160">Você deve ter certeza de que os clientes podem acessar apenas o banco de dados primário atual.</span><span class="sxs-lookup"><span data-stu-id="68f9f-160">You must make sure that clients can access only the current primary database.</span></span>  
  
     <span data-ttu-id="68f9f-161">Para obter mais informações, veja [Recuperar um banco de dados sem restaurar dados &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="68f9f-161">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f9f-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68f9f-162">See Also</span></span>  
 <span data-ttu-id="68f9f-163">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="68f9f-163">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="68f9f-164">Remover um banco de dados primário de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="68f9f-164">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
