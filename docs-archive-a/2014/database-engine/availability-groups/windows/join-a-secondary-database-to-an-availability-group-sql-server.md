---
title: Ingressar um banco de dados secundário em um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joindbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: fd7efe79-c1f9-497d-bfe7-b2a2b2321cf5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0d79325bcde33d13688003de079a42a9601cc41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573272"
---
# <a name="join-a-secondary-database-to-an-availability-group-sql-server"></a><span data-ttu-id="28ac5-102">Unir um banco de dados secundário a um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="28ac5-102">Join a Secondary Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="28ac5-103">Este tópico explica como unir um banco de dados secundário a um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28ac5-103">This topic explains how to join a secondary database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="28ac5-104">Após preparar um banco de dados secundário para uma réplica secundária, você precisará unir o banco de dados ao grupo de disponibilidade o quanto antes.</span><span class="sxs-lookup"><span data-stu-id="28ac5-104">After you prepare a secondary database for a secondary replica, you need to join the database to the availability group as soon as possible.</span></span> <span data-ttu-id="28ac5-105">Isso iniciará a movimentação de dados do banco de dados primário correspondente para o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="28ac5-105">This will start data movement from the corresponding primary database to the secondary database.</span></span>  
  
-   <span data-ttu-id="28ac5-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="28ac5-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="28ac5-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="28ac5-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="28ac5-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="28ac5-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="28ac5-109">**Para preparar um banco de dados secundário, usando:**</span><span class="sxs-lookup"><span data-stu-id="28ac5-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="28ac5-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28ac5-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="28ac5-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28ac5-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="28ac5-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="28ac5-112">PowerShell</span></span>](#PowerShellProcedure)  
  
> [!NOTE]  
>  <span data-ttu-id="28ac5-113">Para obter informações sobre o que acontece depois que um banco de dados secundário ingressa no grupo, consulte [visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28ac5-113">For information about what happens after a secondary database joins the group, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="28ac5-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="28ac5-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="28ac5-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="28ac5-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="28ac5-116">Você deve estar conectado à instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="28ac5-116">You must be connected to the server instance that hosts the secondary replica.</span></span>  
  
-   <span data-ttu-id="28ac5-117">A réplica secundária já deve estar unida ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28ac5-117">The secondary replica must already be joined to the availability group.</span></span> <span data-ttu-id="28ac5-118">Para obter mais informações, veja [Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28ac5-118">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
-   <span data-ttu-id="28ac5-119">O banco de dados secundário deve ter sido preparado recentemente.</span><span class="sxs-lookup"><span data-stu-id="28ac5-119">The secondary database must have been prepared recently.</span></span> <span data-ttu-id="28ac5-120">Para obter mais informações, consulte [Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28ac5-120">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="28ac5-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="28ac5-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="28ac5-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="28ac5-122">Permissions</span></span>  
 <span data-ttu-id="28ac5-123">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="28ac5-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="28ac5-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28ac5-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="28ac5-125">**Para unir um banco de dados secundário a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="28ac5-125">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="28ac5-126">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica secundária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="28ac5-126">In Object Explorer, connect to the server instance that hosts the secondary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="28ac5-127">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="28ac5-127">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="28ac5-128">Expanda o grupo de disponibilidade a ser alterado e expanda o nó **Bancos de Dados de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="28ac5-128">Expand the availability group that you want to change, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="28ac5-129">Clique com o botão direito do mouse no banco de dados e clique em **Unir a um Grupo de Disponibilidade**.</span><span class="sxs-lookup"><span data-stu-id="28ac5-129">Right-click the database, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="28ac5-130">Isso abre a caixa de diálogo **Unir Bancos de Dados a Grupo de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="28ac5-130">This opens the **Join Databases to Availability Group** dialog box.</span></span> <span data-ttu-id="28ac5-131">Verifique o nome do grupo de disponibilidade que é exibido na barra de título e os nomes de banco de dados exibidos na grade. Clique em **OK**ou em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="28ac5-131">Verify the availability group name, which is displayed on the title bar, and database name or names displayed in the grid, and click **OK**, or click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="28ac5-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28ac5-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="28ac5-133">**Para unir um banco de dados secundário a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="28ac5-133">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="28ac5-134">Conecte-se à instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="28ac5-134">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="28ac5-135">Use a [cláusula SET HADR da instrução ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="28ac5-135">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="28ac5-136">ALTER DATABASE *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span><span class="sxs-lookup"><span data-stu-id="28ac5-136">ALTER DATABASE *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>  
  
     <span data-ttu-id="28ac5-137">em que *database_name* é o nome de um banco de dados a ser associado e *group_name* é o nome do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28ac5-137">where *database_name* is the name of a database to be joined and *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="28ac5-138">O exemplo a seguir une o banco de dados secundário `Db1` à réplica secundária local do grupo de disponibilidade `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="28ac5-138">The following example joins the secondary database, `Db1`, to the local secondary replica of the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER DATABASE Db1 SET HADR AVAILABILITY GROUP = MyAG;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="28ac5-139">Para ver esta instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] usada no contexto, veja [Criar um grupo de disponibilidade &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="28ac5-139">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="28ac5-140">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="28ac5-140">Using PowerShell</span></span>  
 <span data-ttu-id="28ac5-141">**Para unir um banco de dados secundário a um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="28ac5-141">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="28ac5-142">Altere o diretório (`cd`) para a instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="28ac5-142">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="28ac5-143">Use o cmdlet `Add-SqlAvailabilityDatabase` para unir um ou mais bancos de dados secundários ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="28ac5-143">Use the `Add-SqlAvailabilityDatabase` cmdlet to join one or more secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="28ac5-144">Por exemplo, o comando a seguir une um banco de dados secundário, `Db1`, ao grupo de disponibilidade `MyAG` em uma das instâncias de servidor que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="28ac5-144">For example, the following command joins a secondary database, `Db1`, to the availability group `MyAG` on one of the server instances that hosts a secondary replica.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase -Path SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAG -Database "Db1"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="28ac5-145">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ac5-145">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="28ac5-146">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="28ac5-146">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="28ac5-147">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="28ac5-147">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="28ac5-148">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="28ac5-148">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="28ac5-149">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="28ac5-149">Related Tasks</span></span>  
  
-   [<span data-ttu-id="28ac5-150">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28ac5-150">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="28ac5-151">Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28ac5-151">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="28ac5-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28ac5-152">See Also</span></span>  
 <span data-ttu-id="28ac5-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28ac5-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="28ac5-154">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28ac5-154">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="28ac5-155">Solucionar problemas de &#40;de configuração de Grupos de Disponibilidade AlwaysOn SQL Server&#41;excluídos</span><span class="sxs-lookup"><span data-stu-id="28ac5-155">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
