---
title: Alterar o modo de failover de uma réplica de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover modes [SQL Server]
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], failover modes
- Availability Groups [SQL Server], configuring
ms.assetid: 619a826f-8e65-48eb-8c34-39497d238279
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d946440e2950192299c42652babb4082790dbd03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685305"
---
# <a name="change-the-failover-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="c2f33-102">Alterar o modo de failover de uma réplica de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c2f33-102">Change the Failover Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="c2f33-103">Este tópico descreve como alterar o modo de failover de uma réplica de disponibilidade em um grupo de disponibilidade AlwaysOn no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2f33-103">This topic describes how to change the failover mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="c2f33-104">O modo de failover é uma propriedade de réplica que determina o modo de failover para réplicas que executam sob modo de disponibilidade de confirmação síncrona.</span><span class="sxs-lookup"><span data-stu-id="c2f33-104">The failover mode is a replica property that determines the failover mode for replicas that run under synchronous-commit availability mode.</span></span> <span data-ttu-id="c2f33-105">Para obter mais informações, consulte [Failover e modos de failover &#40;Grupos de disponibilidade AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) e [Modos de disponibilidade &#40;Grupos de disponibilidade AlwaysOn&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c2f33-105">For more information, see [Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) and [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c2f33-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c2f33-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="c2f33-107">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="c2f33-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="c2f33-108">Esta tarefa tem suporte apenas em réplicas primárias.</span><span class="sxs-lookup"><span data-stu-id="c2f33-108">This task is supported only on primary replicas.</span></span> <span data-ttu-id="c2f33-109">Você deve estar conectado à instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="c2f33-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="c2f33-110">As FCIs (Instâncias de cluster de failover) do SQL Server não dão suporte ao failover automático por grupos de disponibilidade, de modo que qualquer réplica de disponibilidade que esteja hospedado por um FCI só pode ser configurada para failover manual.</span><span class="sxs-lookup"><span data-stu-id="c2f33-110">SQL Server Failover Cluster Instances (FCIs) do not support automatic failover by availability groups, so any availability replica that is hosted by an FCI can only be configured for manual failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c2f33-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="c2f33-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c2f33-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="c2f33-112">Permissions</span></span>  
 <span data-ttu-id="c2f33-113">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="c2f33-113">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c2f33-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c2f33-114">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c2f33-115">**Para alterar o modo de failover de uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="c2f33-115">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="c2f33-116">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="c2f33-116">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="c2f33-117">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="c2f33-117">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="c2f33-118">Clique no grupo de disponibilidade cuja réplica você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="c2f33-118">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="c2f33-119">Clique com o botão direito do mouse na réplica e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c2f33-119">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="c2f33-120">Na caixa de diálogo **Propriedades da Réplica de Disponibilidade** , use a lista suspensa **Modo de failover** para alterar o modo de failover desta réplica.</span><span class="sxs-lookup"><span data-stu-id="c2f33-120">In the **Availability Replica Properties** dialog box, use the **Failover mode** drop list to change the failover mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c2f33-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c2f33-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="c2f33-122">**Para alterar o modo de failover de uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="c2f33-122">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="c2f33-123">Conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="c2f33-123">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="c2f33-124">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c2f33-124">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="c2f33-125">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span><span class="sxs-lookup"><span data-stu-id="c2f33-125">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="c2f33-126">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="c2f33-126">WITH ( {</span></span>  
  
     <span data-ttu-id="c2f33-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="c2f33-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="c2f33-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="c2f33-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="c2f33-129">}  )</span><span class="sxs-lookup"><span data-stu-id="c2f33-129">}  )</span></span>  
  
     <span data-ttu-id="c2f33-130">onde</span><span class="sxs-lookup"><span data-stu-id="c2f33-130">where</span></span>  
  
    -   <span data-ttu-id="c2f33-131">*group_name* é o nome do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c2f33-131">*group_name* is the name of the availability group.</span></span>  
  
    -   <span data-ttu-id="c2f33-132">{ '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }</span><span class="sxs-lookup"><span data-stu-id="c2f33-132">{ '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }</span></span>  
  
         <span data-ttu-id="c2f33-133">Especifica o endereço da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda a réplica de disponibilidade a ser alterada.</span><span class="sxs-lookup"><span data-stu-id="c2f33-133">Specifies the address of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica to be altered.</span></span> <span data-ttu-id="c2f33-134">Os componentes desse endereço são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="c2f33-134">The components of this address are as follows:</span></span>  
  
         <span data-ttu-id="c2f33-135">*system_name*</span><span class="sxs-lookup"><span data-stu-id="c2f33-135">*system_name*</span></span>  
         <span data-ttu-id="c2f33-136">É o nome do NetBIOS do sistema de computador no qual reside uma instância autônoma do servidor.</span><span class="sxs-lookup"><span data-stu-id="c2f33-136">Is the NetBIOS name of the computer system on which a stand-alone server instance resides.</span></span>  
  
         <span data-ttu-id="c2f33-137">*FCI_network_name*</span><span class="sxs-lookup"><span data-stu-id="c2f33-137">*FCI_network_name*</span></span>  
         <span data-ttu-id="c2f33-138">É o nome de rede usado para acessar um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no qual uma instância de servidor de destino é um parceiro de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (um FCI).</span><span class="sxs-lookup"><span data-stu-id="c2f33-138">Is the network name that is used to access a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster in which a target server instance is a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover partner (an FCI).</span></span>  
  
         <span data-ttu-id="c2f33-139">*instance_name*</span><span class="sxs-lookup"><span data-stu-id="c2f33-139">*instance_name*</span></span>  
         <span data-ttu-id="c2f33-140">É o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda a réplica de disponibilidade de destino.</span><span class="sxs-lookup"><span data-stu-id="c2f33-140">Is the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the target availability replica.</span></span> <span data-ttu-id="c2f33-141">Para uma instância de servidor padrão, *instance_name* é opcional.</span><span class="sxs-lookup"><span data-stu-id="c2f33-141">For a default server instance, *instance_name* is optional.</span></span>  
  
     <span data-ttu-id="c2f33-142">Para obter mais informações sobre esses parâmetros, veja [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c2f33-142">For more information about these parameters, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="c2f33-143">O exemplo a seguir, inserido na réplica primária do grupo de disponibilidade *MyAG* , altera o modo de failover para failover automático na réplica de disponibilidade localizada na instância de servidor padrão em um computador denominado *COMPUTER01*.</span><span class="sxs-lookup"><span data-stu-id="c2f33-143">The following example, entered on the primary replica of the *MyAG* availability group, changes the failover mode to automatic failover on the availability replica that is located on the default server instance on a computer named *COMPUTER01*.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP MyAG MODIFY REPLICA ON 'COMPUTER01' WITH  
       (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="c2f33-144">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2f33-144">Using PowerShell</span></span>  

### <a name="to-change-the-failover-mode-of-an-availability-replica"></a><span data-ttu-id="c2f33-145">Para alterar o modo de failover de uma réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c2f33-145">To change the failover mode of an availability replica</span></span>
  
1.  <span data-ttu-id="c2f33-146">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="c2f33-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="c2f33-147">Use o cmdlet `Set-SqlAvailabilityReplica` com o parâmetro `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="c2f33-147">Use the `Set-SqlAvailabilityReplica` cmdlet with the `FailoverMode` parameter.</span></span> <span data-ttu-id="c2f33-148">Ao definir uma réplica como failover automático, talvez seja preciso usar o parâmetro `AvailabilityMode` para alterar a réplica para o modo de disponibilidade de confirmação síncrona.</span><span class="sxs-lookup"><span data-stu-id="c2f33-148">When setting a replica to automatic failover, you might need to use the `AvailabilityMode` parameter to change the replica to synchronous-commit availability mode.</span></span>  
  
     <span data-ttu-id="c2f33-149">Por exemplo, o comando a seguir modifica a réplica `MyReplica` no grupo de disponibilidade `MyAg` para usar o modo de disponibilidade de confirmação síncrona e para oferecer suporte ao failover automático.</span><span class="sxs-lookup"><span data-stu-id="c2f33-149">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\Replicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="c2f33-150">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2f33-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="c2f33-151">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c2f33-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="c2f33-152">Para configurar e usar o provedor de SQL Server PowerShell, consulte [provedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c2f33-152">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c2f33-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2f33-153">See Also</span></span>  
 [<span data-ttu-id="c2f33-154">Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c2f33-154">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="c2f33-155">[Modos de disponibilidade &#40;Grupos de Disponibilidade AlwaysOn&#41;](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="c2f33-155">[Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="c2f33-156">Failover e modos de failover &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="c2f33-156">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md) 
