---
title: Retomar um banco de dados de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.resumedatamove.f1
helpviewer_keywords:
- Availability Groups [SQL Server], resuming a database
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], databases
ms.assetid: 20e9147b-e985-4caa-910e-fc4b38dbf9a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a2279940c2502a310e9dac4448bd6029b6e13dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684914"
---
# <a name="resume-an-availability-database-sql-server"></a><span data-ttu-id="93913-102">Retomar um banco de dados de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="93913-102">Resume an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="93913-103">Você pode retomar um banco de dados de disponibilidade suspenso no [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93913-103">You can resume a suspended availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="93913-104">A retomada de um banco de dados suspenso coloca o banco de dados no estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="93913-104">Resuming a suspended database puts the database into the SYNCHRONIZING state.</span></span> <span data-ttu-id="93913-105">A retomada do banco de dados primário também retoma todos os bancos de dados secundários que foram suspensos devido à suspensão do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="93913-105">Resuming the primary database also resumes any of its secondary databases that were suspended as the result of suspending the primary database.</span></span> <span data-ttu-id="93913-106">Se um banco de dados secundário foi suspenso localmente, na instância de servidor que hospeda a réplica secundária, o banco de dados secundário deverá ser retomado localmente.</span><span class="sxs-lookup"><span data-stu-id="93913-106">If any secondary database was suspended locally, from the server instance that hosts the secondary replica, that secondary database must be resumed locally.</span></span> <span data-ttu-id="93913-107">Quando um determinado banco de dados secundário e o banco de dados primário correspondente estiverem no estado SYNCHRONIZING, a sincronização de dados é retomada no banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="93913-107">Once a given secondary database and the corresponding primary database are in the SYNCHRONIZING state, data synchronization resumes on the secondary database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93913-108">Suspender e retomar um banco de dados secundário AlwaysOn não afetam diretamente a disponibilidade do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="93913-108">Suspending and resuming an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="93913-109">Porém, suspender um banco de dados secundário pode afetar os recursos de redundância e failover para o banco de dados primário, até que o banco de dados secundário suspenso seja retomado.</span><span class="sxs-lookup"><span data-stu-id="93913-109">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database, until the suspended secondary database is resumed.</span></span> <span data-ttu-id="93913-110">Isto está em contraste com o espelhamento de banco de dados, onde o estado de espelhamento é suspenso no banco de dados espelho e no banco de dados principal até que o espelhamento seja retomado.</span><span class="sxs-lookup"><span data-stu-id="93913-110">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database until mirroring is resumed.</span></span> <span data-ttu-id="93913-111">Suspender um banco de dados secundário AlwaysOn suspende o movimento de dados em todos os bancos de dados secundários correspondentes, e os recursos de failover e a redundância são eliminados para esse banco de dados até que o banco de dados primário seja retomado.</span><span class="sxs-lookup"><span data-stu-id="93913-111">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="93913-112">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="93913-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="93913-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="93913-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="93913-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="93913-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="93913-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="93913-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="93913-116">**Para retomar um banco de dados secundário usando:**</span><span class="sxs-lookup"><span data-stu-id="93913-116">**To resume a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="93913-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93913-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="93913-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93913-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="93913-119">PowerShell</span><span class="sxs-lookup"><span data-stu-id="93913-119">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="93913-120">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="93913-120">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="93913-121">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="93913-121">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="93913-122">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="93913-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="93913-123">O comando RESUME retorna assim que é aceito pela réplica que hospeda o banco de dados de destino, mas, na verdade, a retomada do banco de dados ocorre de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="93913-123">A RESUME command returns as soon as it has been accepted by the replica that hosts the target database, but actually resuming the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="93913-124">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="93913-124">Prerequisites</span></span>  
  
-   <span data-ttu-id="93913-125">Você deve estar conectado à instância de servidor que hospeda o banco de dados a ser retomado.</span><span class="sxs-lookup"><span data-stu-id="93913-125">You must be connected to the server instance that hosts the database to be resumed.</span></span>  
  
-   <span data-ttu-id="93913-126">O grupo de disponibilidade deve estar online.</span><span class="sxs-lookup"><span data-stu-id="93913-126">The availability group must be online.</span></span>  
  
-   <span data-ttu-id="93913-127">O banco de dados primário deve estar online e disponível.</span><span class="sxs-lookup"><span data-stu-id="93913-127">The primary database must be online and available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="93913-128">Segurança</span><span class="sxs-lookup"><span data-stu-id="93913-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="93913-129">Permissões</span><span class="sxs-lookup"><span data-stu-id="93913-129">Permissions</span></span>  
 <span data-ttu-id="93913-130">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="93913-130">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="93913-131">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="93913-131">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="93913-132">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93913-132">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="93913-133">**Para retomar um banco de dados secundário**</span><span class="sxs-lookup"><span data-stu-id="93913-133">**To resume a secondary database**</span></span>  
  
1.  <span data-ttu-id="93913-134">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica de disponibilidade na qual você deseja retomar o banco de dados e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="93913-134">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to resume a database, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="93913-135">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="93913-135">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="93913-136">Expanda o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="93913-136">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="93913-137">Expanda o nó **Bancos de dados de Disponibilidade** , clique com o botão direito do mouse no banco de dados e clique em **Retomar a Movimentação de Dados**.</span><span class="sxs-lookup"><span data-stu-id="93913-137">Expand the **Availability Databases** node, right-click the database, and click **Resume Data Movement**.</span></span>  
  
5.  <span data-ttu-id="93913-138">Na caixa de diálogo **Retomar a Movimentação de Dados** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="93913-138">In the **Resume Data Movement** dialog box, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93913-139">Para retomar bancos de dados adicionais neste local de réplica, repita as etapas 4 e 5 para cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="93913-139">To resume additional databases on this replica location, repeat steps 4 and 5 for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="93913-140">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93913-140">Using Transact-SQL</span></span>  
 <span data-ttu-id="93913-141">**Para retomar um banco de dados secundário que foi suspenso localmente**</span><span class="sxs-lookup"><span data-stu-id="93913-141">**To resume a secondary database that was suspended locally**</span></span>  
  
1.  <span data-ttu-id="93913-142">Conecte-se à instância do servidor que hospeda a réplica secundária, cujo banco de dados você deseja retomar.</span><span class="sxs-lookup"><span data-stu-id="93913-142">Connect to the server instance that hosts the secondary replica whose database you want to resume.</span></span>  
  
2.  <span data-ttu-id="93913-143">Retome o banco de dados secundário usando a seguinte instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr):</span><span class="sxs-lookup"><span data-stu-id="93913-143">Resume the secondary database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="93913-144">ALTER DATABASE *database_name* Set HADR resume</span><span class="sxs-lookup"><span data-stu-id="93913-144">ALTER DATABASE *database_name* SET HADR RESUME</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="93913-145">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="93913-145">Using PowerShell</span></span>  

### <a name="to-resume-a-secondary-database"></a><span data-ttu-id="93913-146">Para retomar um banco de dados secundário</span><span class="sxs-lookup"><span data-stu-id="93913-146">To resume a secondary database</span></span>
  
1.  <span data-ttu-id="93913-147">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica cujo banco de dados você deseja retomar.</span><span class="sxs-lookup"><span data-stu-id="93913-147">Change directory (`cd`) to the server instance that hosts the replica whose database you want to resume.</span></span> <span data-ttu-id="93913-148">Para obter mais informações, consulte [Pré-requisitos](#Prerequisites)anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="93913-148">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="93913-149">Use o cmdlet **Resume-SqlAvailabilityDatabase** para retomar o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="93913-149">Use the **Resume-SqlAvailabilityDatabase** cmdlet to resume the availability group.</span></span>  
  
     <span data-ttu-id="93913-150">Por exemplo, o comando a seguir retoma a sincronização dos dados para o banco de dados de disponibilidade `MyDb3` no grupo de disponibilidade `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="93913-150">For example, the following command resumes data synchronization for the availability database `MyDb3` in the availability group `MyAg`.</span></span>  
  
    ```powershell
    Resume-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="93913-151">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93913-151">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="93913-152">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="93913-152">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="93913-153">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="93913-153">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="93913-154">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="93913-154">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="93913-155">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="93913-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="93913-156">Suspender um banco de dados de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="93913-156">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="93913-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="93913-157">See Also</span></span>  
 [<span data-ttu-id="93913-158">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="93913-158">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
