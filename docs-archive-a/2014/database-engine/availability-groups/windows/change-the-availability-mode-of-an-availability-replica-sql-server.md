---
title: Alterar o modo de disponibilidade de uma réplica de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], availability modes
ms.assetid: c4da8f25-fb1b-45a4-8bf2-195df6df634c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1636f3ea86e083e47276423b120dbc8d3744d387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685310"
---
# <a name="change-the-availability-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="c9e57-102">Alterar o modo de disponibilidade de uma réplica de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c9e57-102">Change the Availability Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="c9e57-103">Este tópico descreve como alterar o modo de disponibilidade de uma réplica de disponibilidade em um grupo de disponibilidade AlwaysOn no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9e57-103">This topic describes how to change the availability mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="c9e57-104">O modo de disponibilidade é uma propriedade de réplica que controla se a réplica confirma de forma assíncrona ou síncrona.</span><span class="sxs-lookup"><span data-stu-id="c9e57-104">The availability mode is a replica property that controls the whether the replica commits asynchronously or synchronously.</span></span> <span data-ttu-id="c9e57-105">O*modo de confirmação assíncrona* maximiza o desempenho às custas da alta disponibilidade e dá suporte apenas ao failover manual forçado (com possível perda de dados), que costuma ser chamado de *failover forçado*.</span><span class="sxs-lookup"><span data-stu-id="c9e57-105">*Asynchronous-commit mode* maximizes performance at the expense of high availability and supports only forced manual failover (with possible data loss), typically called *forced failover*.</span></span> <span data-ttu-id="c9e57-106">O*modo de confirmação síncrona* enfatiza a alta disponibilidade sobre o desempenho e, quando a réplica secundária é sincronizada, dá suporte ao failover manual e, opcionalmente, ao failover automático.</span><span class="sxs-lookup"><span data-stu-id="c9e57-106">*Synchronous-commit mode* emphasizes high availability over performance and, once the secondary replica is synchronized, supports manual failover and, optionally, automatic failover.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c9e57-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c9e57-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c9e57-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c9e57-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="c9e57-109">Você deve estar conectado à instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="c9e57-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c9e57-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="c9e57-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c9e57-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="c9e57-111">Permissions</span></span>  
 <span data-ttu-id="c9e57-112">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="c9e57-112">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c9e57-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9e57-113">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c9e57-114">**Para alterar o modo de disponibilidade de um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="c9e57-114">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="c9e57-115">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="c9e57-115">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="c9e57-116">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="c9e57-116">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="c9e57-117">Clique no grupo de disponibilidade cuja réplica você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="c9e57-117">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="c9e57-118">Clique com o botão direito do mouse na réplica e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c9e57-118">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="c9e57-119">Na caixa de diálogo **Propriedades da Réplica de Disponibilidade** , use a lista suspensa **Modo de disponibilidade** para alterar o modo de disponibilidade desta réplica.</span><span class="sxs-lookup"><span data-stu-id="c9e57-119">In the **Availability Replica Properties** dialog box, use the **Availability mode** drop list to change the availability mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c9e57-120">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9e57-120">Using Transact-SQL</span></span>  
 <span data-ttu-id="c9e57-121">**Para alterar o modo de disponibilidade de um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="c9e57-121">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="c9e57-122">Conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="c9e57-122">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="c9e57-123">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c9e57-123">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="c9e57-124">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span><span class="sxs-lookup"><span data-stu-id="c9e57-124">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="c9e57-125">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="c9e57-125">WITH ( {</span></span>  
  
     <span data-ttu-id="c9e57-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="c9e57-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="c9e57-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="c9e57-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="c9e57-128">} )</span><span class="sxs-lookup"><span data-stu-id="c9e57-128">} )</span></span>  
  
     <span data-ttu-id="c9e57-129">em que *group_name* é o nome do grupo de disponibilidade e *server_name* é o nome da instância do servidor que hospeda a réplica a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="c9e57-129">where *group_name* is the name of the availability group and *server_name* is the name of the server instance that hosts the replica to be modified.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9e57-130">FAILOVER_MODE = AUTOMATIC terá suporte apenas se você também especificar AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span><span class="sxs-lookup"><span data-stu-id="c9e57-130">FAILOVER_MODE = AUTOMATIC is supported only if you also specify AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span></span>  
  
     <span data-ttu-id="c9e57-131">O exemplo a seguir, inserido na réplica primária do grupo de disponibilidade `AccountsAG` , altera os modos de disponibilidade e de failover para confirmação síncrona e failover automático, respectivamente, para a réplica hospedada pela instância de servidor `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="c9e57-131">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the availability and failover modes to synchronous commit and automatic failover, respectively, for the replica hosted by the `INSTANCE09` server instance.</span></span>  
  
    ```  
  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (AVAILABILITY_MODE = SYNCHRONOUS_COMMIT);  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="c9e57-132">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9e57-132">Using PowerShell</span></span>

### <a name="to-change-the-availability-mode-of-an-availability-group"></a><span data-ttu-id="c9e57-133">Para alterar o modo de disponibilidade de um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c9e57-133">To change the availability mode of an availability group</span></span>
  
1.  <span data-ttu-id="c9e57-134">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="c9e57-134">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="c9e57-135">Use o cmdlet `Set-SqlAvailabilityReplica` com o parâmetro `AvailabilityMode` e, opcionalmente, o parâmetro `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="c9e57-135">Use the `Set-SqlAvailabilityReplica` cmdlet with the `AvailabilityMode` parameter and, optionally, the `FailoverMode` parameter.</span></span>  
  
     <span data-ttu-id="c9e57-136">Por exemplo, o comando a seguir modifica a réplica `MyReplica` no grupo de disponibilidade `MyAg` para usar o modo de disponibilidade de confirmação síncrona e para oferecer suporte ao failover automático.</span><span class="sxs-lookup"><span data-stu-id="c9e57-136">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `   
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9e57-137">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9e57-137">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="c9e57-138">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c9e57-138">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="c9e57-139">Para configurar e usar o provedor de SQL Server PowerShell, consulte [provedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c9e57-139">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c9e57-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9e57-140">See Also</span></span>  
 <span data-ttu-id="c9e57-141">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9e57-141">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="c9e57-142">[Modos de disponibilidade (Grupos de Disponibilidade AlwaysOn)](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="c9e57-142">[Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="c9e57-143">Failover e modos de failover &#40;Grupos de Disponibilidade AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="c9e57-143">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md)  
