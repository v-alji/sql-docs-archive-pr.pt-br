---
title: Remover uma réplica secundária de um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removesecondaryar.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 35ddc8b6-3e7c-4417-9a0a-d4987a09ddf7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e3f2b35ec9cf27f2f7b23714a41665f2709837a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571604"
---
# <a name="remove-a-secondary-replica-from-an-availability-group-sql-server"></a><span data-ttu-id="26529-102">Remover uma réplica secundária de um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="26529-102">Remove a Secondary Replica from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="26529-103">Este tópico descreve como remover uma réplica secundária de um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26529-103">This topic describes how to remove a secondary replica from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="26529-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="26529-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="26529-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="26529-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="26529-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="26529-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="26529-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="26529-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="26529-108">**Para remover uma réplica secundária usando:**</span><span class="sxs-lookup"><span data-stu-id="26529-108">**To remove a secondary replica, using:**</span></span>  
  
     [<span data-ttu-id="26529-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26529-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="26529-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26529-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="26529-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="26529-111">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="26529-112">**Acompanhamento:**  [depois de remover uma réplica secundária](#PostBestPractices)</span><span class="sxs-lookup"><span data-stu-id="26529-112">**Follow Up:**  [After Removing a Secondary Replica](#PostBestPractices)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="26529-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="26529-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="26529-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="26529-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="26529-115">Esta tarefa tem suporte apenas na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="26529-115">This task is supported only on the primary replica.</span></span>  
  
-   <span data-ttu-id="26529-116">Apenas uma réplica secundária pode ser removida de um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="26529-116">Only a secondary replica can be removed from an availability group.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="26529-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="26529-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="26529-118">Conecte-se à instância do servidor que hospeda a réplica primária do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="26529-118">You must be connected to the server instance that hosts the primary replica of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="26529-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="26529-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="26529-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="26529-120">Permissions</span></span>  
 <span data-ttu-id="26529-121">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="26529-121">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="26529-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26529-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="26529-123">**Para remover uma réplica secundária**</span><span class="sxs-lookup"><span data-stu-id="26529-123">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="26529-124">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="26529-124">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="26529-125">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="26529-125">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="26529-126">Selecione o grupo de disponibilidade e expanda o nó **Réplicas de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="26529-126">Select the availability group, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="26529-127">Essa etapa depende de se você deseja remover várias réplicas ou apenas uma réplica, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="26529-127">This step depends on whether you want to remove multiple replicas or only one replica, as follows:</span></span>  
  
    -   <span data-ttu-id="26529-128">Para remover várias réplicas, use o painel **Detalhes do Pesquisador de Objetos** para exibir e selecionar todas as réplicas que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="26529-128">To remove multiple replicas, use the **Object Explorer Details** pane to view and select all the replicas that you want to remove.</span></span> <span data-ttu-id="26529-129">Para obter mais informações, veja [Usar os detalhes do Pesquisador de Objetos para monitorar grupos de disponibilidade &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="26529-129">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="26529-130">Para remover uma única réplica, selecione-a no painel **Pesquisador de Objetos** ou no painel **Detalhes do Pesquisador de Objetos** .</span><span class="sxs-lookup"><span data-stu-id="26529-130">To remove a single replica, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="26529-131">Clique com o botão direito do mouse na réplica ou réplicas secundárias selecionadas e selecione **Remover do Grupo de Disponibilidade** no menu de comando.</span><span class="sxs-lookup"><span data-stu-id="26529-131">Right-click the selected secondary replica or replicas, and select **Remove from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="26529-132">Na caixa de diálogo **Remover Réplicas Secundárias do Grupo de Disponibilidade** , para remover todas as réplicas secundárias listadas, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="26529-132">In the **Remove Secondary Replicas from Availability Group** dialog box, to remove all the listed secondary replicas, click **OK**.</span></span> <span data-ttu-id="26529-133">Se você não desejar remover todas as réplicas listadas, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="26529-133">If you do not want to remove all the listed replicas, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="26529-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26529-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="26529-135">**Para remover uma réplica secundária**</span><span class="sxs-lookup"><span data-stu-id="26529-135">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="26529-136">Conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="26529-136">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="26529-137">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="26529-137">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="26529-138">ALTER AVAILABILITY GROUP *group_name* REMOVE REPLICA ON '*instance_name*' [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="26529-138">ALTER AVAILABILITY GROUP *group_name* REMOVE REPLICA ON '*instance_name*' [,...*n*]</span></span>  
  
     <span data-ttu-id="26529-139">em que *group_name* é o nome do grupo de disponibilidade e *instance_name* é a instância do servidor no qual a réplica secundária está localizada.</span><span class="sxs-lookup"><span data-stu-id="26529-139">where *group_name* is the name of the availability group and *instance_name* is the server instance where the secondary replica is located.</span></span>  
  
     <span data-ttu-id="26529-140">O exemplo a seguir remove a réplica secundária do grupo de disponibilidade *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="26529-140">The following example removes a secondary replica from the *MyAG* availability group.</span></span> <span data-ttu-id="26529-141">A réplica secundária de destino está localizada em uma instância de servidor denominada *HADR_INSTANCE* em um computador denominado *COMPUTER02*.</span><span class="sxs-lookup"><span data-stu-id="26529-141">The target secondary replica is located on a server instance named *HADR_INSTANCE* on a computer named *COMPUTER02*.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE REPLICA ON 'COMPUTER02\HADR_INSTANCE';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="26529-142">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="26529-142">Using PowerShell</span></span>  
 <span data-ttu-id="26529-143">**Para remover uma réplica secundária**</span><span class="sxs-lookup"><span data-stu-id="26529-143">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="26529-144">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="26529-144">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="26529-145">Use o cmdlet **Remove-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="26529-145">Use the **Remove-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="26529-146">Por exemplo, o comando a seguir remove a réplica de disponibilidade no servidor `MyReplica` do grupo de disponibilidade denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="26529-146">For example, the following command removes the availability replica on the server `MyReplica` from the availability group named `MyAg`.</span></span>  <span data-ttu-id="26529-147">Este comando deve ser executado na instância do servidor que hospeda a réplica primária do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="26529-147">This command must be run on the server instance that hosts the primary replica of the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityReplica -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="26529-148">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26529-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="26529-149">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="26529-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="26529-150">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="26529-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="26529-151">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="26529-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-replica"></a><a name="PostBestPractices"></a> <span data-ttu-id="26529-152">Acompanhamento: depois de remover uma réplica secundária</span><span class="sxs-lookup"><span data-stu-id="26529-152">Follow Up: After Removing a Secondary Replica</span></span>  
 <span data-ttu-id="26529-153">Se você especificar uma réplica que não esteja disponível atualmente, quando a réplica for colocada online, descobrirá que foi removida.</span><span class="sxs-lookup"><span data-stu-id="26529-153">If you specify a replica that is currently unavailable, when the replica comes online, it will discover that it has been removed.</span></span>  
  
 <span data-ttu-id="26529-154">A remoção de uma réplica faz com que ela pare de receber dados.</span><span class="sxs-lookup"><span data-stu-id="26529-154">Removing a replica causes it to stop receiving data.</span></span> <span data-ttu-id="26529-155">Depois que uma réplica secundária confirmar que foi removida do repositório global, a réplica removerá as configurações de grupo de disponibilidade de seus bancos de dados, que permanecem na instância do servidor local no estado RECOVERING.</span><span class="sxs-lookup"><span data-stu-id="26529-155">After a secondary replica confirms that it has been removed from the global store, the replica removes the availability group settings from its databases, which remain on the local server instance in the RECOVERING state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26529-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26529-156">See Also</span></span>  
 <span data-ttu-id="26529-157">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="26529-157">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="26529-158">[Adicionar uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="26529-158">[Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span></span>  
 [<span data-ttu-id="26529-159">Remover um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="26529-159">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
