---
title: Remover um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.deleteag.f1
helpviewer_keywords:
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], dropping
ms.assetid: 4b7f7f62-43a3-49db-a72e-22d4d7c2ddbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c17b7d5b362d8b4030d66ebf7ba0e425495410e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571602"
---
# <a name="remove-an-availability-group-sql-server"></a><span data-ttu-id="31aa3-102">Remover um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31aa3-102">Remove an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="31aa3-103">Este tópico descreve como excluir (descartar) um grupo de disponibilidade AlwaysOn usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31aa3-103">This topic describes how to delete (drop) an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="31aa3-104">Se uma instância de servidor que hospeda uma das réplicas de disponibilidade estiver offline quando você exclui um grupo de disponibilidade, ela removerá a réplica de disponibilidade local quando estiver online novamente.</span><span class="sxs-lookup"><span data-stu-id="31aa3-104">If a server instance that hosts one of the availability replicas is offline when you delete an availability group, after coming online, the server instance will drop the local availability replica.</span></span> <span data-ttu-id="31aa3-105">O descarte de um grupo de disponibilidade exclui qualquer ouvinte de grupo de disponibilidade associado.</span><span class="sxs-lookup"><span data-stu-id="31aa3-105">Dropping an availability group deletes any associated availability group listener.</span></span>  
  
 <span data-ttu-id="31aa3-106">Observe que, se for necessário, você pode remover um grupo de disponibilidade de qualquer nó WSFC (Windows Server Failover Clustering) que processa as credenciais de segurança corretas para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31aa3-106">Note that, if necessary, you can drop an availability group from any Windows Server Failover Clustering (WSFC) node that possesses the correct security credentials for the availability group.</span></span> <span data-ttu-id="31aa3-107">Isso permite excluir um grupo de disponibilidade quando nenhuma de suas réplicas de disponibilidade permanece.</span><span class="sxs-lookup"><span data-stu-id="31aa3-107">This enables you to delete an availability group when none of its availability replicas remain.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="31aa3-108">Se possível, remova o grupo de disponibilidade somente quando ele estiver conectado à instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="31aa3-108">If possible, remove the availability group only while connected to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="31aa3-109">Quando o grupo de disponibilidade é removido da réplica primária, são permitidas alterações nos bancos de dados primários antigos (sem proteção de alta disponibilidade).</span><span class="sxs-lookup"><span data-stu-id="31aa3-109">When the availability group is dropped from the primary replica, changes are allowed in the former primary databases (without high availability protection).</span></span> <span data-ttu-id="31aa3-110">Quando um grupo de disponibilidade é excluído de uma réplica secundária, a réplica primária fica no estado RESTORING, e as alterações não são permitidas nos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="31aa3-110">Deleting an availability group from a secondary replica leaves the primary replica in the RESTORING state, and changes are not allowed on the databases.</span></span>  
  
-   <span data-ttu-id="31aa3-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="31aa3-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="31aa3-112">Limitações e recomendações</span><span class="sxs-lookup"><span data-stu-id="31aa3-112">Limitations and Recommendations</span></span>](#Restrictions)  
  
     [<span data-ttu-id="31aa3-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="31aa3-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="31aa3-114">**Para excluir um grupo de disponibilidade usando:**</span><span class="sxs-lookup"><span data-stu-id="31aa3-114">**To delete an availability group, using:**</span></span>  
  
     [<span data-ttu-id="31aa3-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="31aa3-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="31aa3-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31aa3-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="31aa3-117">PowerShell</span><span class="sxs-lookup"><span data-stu-id="31aa3-117">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="31aa3-118">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="31aa3-118">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="31aa3-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="31aa3-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-recommendations"></a><a name="Restrictions"></a><span data-ttu-id="31aa3-120">Limitações e recomendações</span><span class="sxs-lookup"><span data-stu-id="31aa3-120">Limitations and Recommendations</span></span>  
  
-   <span data-ttu-id="31aa3-121">Quando o grupo de disponibilidade está online, excluí-lo de uma réplica secundária faz com que a réplica primária passe para o estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="31aa3-121">When the availability group is online, deleting it from a secondary replica causes the primary replica to transition to the RESTORING state.</span></span> <span data-ttu-id="31aa3-122">Portanto, se for possível, remova o grupo de disponibilidade somente da instância do servidor que hospeda a réplica principal.</span><span class="sxs-lookup"><span data-stu-id="31aa3-122">Therefore, if possible, remove the availability group only from the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="31aa3-123">Se você excluir um grupo de disponibilidade de um computador que foi removido do cluster de failover WSFC, o grupo de disponibilidade só será excluído localmente.</span><span class="sxs-lookup"><span data-stu-id="31aa3-123">If you delete an availability group from a computer that has been removed or evicted from the WSFC failover cluster, the availability group is only deleted locally.</span></span>  
  
-   <span data-ttu-id="31aa3-124">Evite remover um grupo de disponibilidade quando o cluster WSFC (Windows Server Failover Clustering) não tem quorum.</span><span class="sxs-lookup"><span data-stu-id="31aa3-124">Avoid dropping an availability group when the Windows Server Failover Clustering (WSFC) cluster has no quorum.</span></span> <span data-ttu-id="31aa3-125">Caso seja necessário remover um grupo de disponibilidade enquanto o cluster perde quorum, o grupo de disponibilidade de metadados armazenado no cluster não será removido.</span><span class="sxs-lookup"><span data-stu-id="31aa3-125">If you must drop an availability group while the cluster lacks quorum, the metadata availability group that is stored in the cluster is not removed.</span></span> <span data-ttu-id="31aa3-126">Depois que o cluster recuperar o quorum, será necessário remover novamente o grupo de disponibilidade para removê-lo do cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="31aa3-126">After the cluster regains quorum, you will need to drop the availability group again to remove it from the WSFC cluster.</span></span>  
  
-   <span data-ttu-id="31aa3-127">Em uma réplica secundária, DROP AVAILABILITY GROUP só deve ser usado para fins de emergência.</span><span class="sxs-lookup"><span data-stu-id="31aa3-127">On a secondary replica, DROP AVAILABILITY GROUP should only be used only for emergency purposes.</span></span> <span data-ttu-id="31aa3-128">Isso ocorre porque, ao remover um grupo de disponibilidade, você o coloca offline.</span><span class="sxs-lookup"><span data-stu-id="31aa3-128">This is because dropping an availability group takes the availability group offline.</span></span> <span data-ttu-id="31aa3-129">Se você remover o grupo de disponibilidade de uma réplica secundária, a réplica primária não poderá determinar se o estado OFFLINE ocorreu devido à perda de quorum, a um failover forçado ou a um comando DROP AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="31aa3-129">If you drop the availability group from a secondary replica, the primary replica cannot determine whether the OFFLINE state occurred because of quorum loss, a forced failover, or a DROP AVAILABILITY GROUP command.</span></span> <span data-ttu-id="31aa3-130">A réplica primária passa para o estado RESTORING para evitar uma possível situação de separação.</span><span class="sxs-lookup"><span data-stu-id="31aa3-130">The primary replica transitions to the RESTORING state to prevent a possible split-brain situation.</span></span> <span data-ttu-id="31aa3-131">Para obter mais informações, consulte [How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (Como funcionam os comportamentos de DROP AVAILABILITY GROUP) (blog CSS SQL Server Engineers).</span><span class="sxs-lookup"><span data-stu-id="31aa3-131">For more information, see [How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="31aa3-132">Segurança</span><span class="sxs-lookup"><span data-stu-id="31aa3-132">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="31aa3-133">Permissões</span><span class="sxs-lookup"><span data-stu-id="31aa3-133">Permissions</span></span>  
 <span data-ttu-id="31aa3-134">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="31aa3-134">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span> <span data-ttu-id="31aa3-135">Para remover um grupo de disponibilidade que não é hospedado pela instância de servidor local, você precisará da permissão CONTROL SERVER ou CONTROL nesse grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31aa3-135">To drop an availability group that is not hosted by the local server instance you need CONTROL SERVER permission or CONTROL permission on that Availability Group.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="31aa3-136">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="31aa3-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="31aa3-137">**Para excluir um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="31aa3-137">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="31aa3-138">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária, se possível, ou conecte-se a outra instância de servidor que é habilitada para Grupos de Disponibilidade AlwaysOn em um nó WSFC que possuem as credenciais de segurança corretas para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31aa3-138">In Object Explorer, connect to the server instance that hosts primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span> <span data-ttu-id="31aa3-139">Expanda a árvore de servidor.</span><span class="sxs-lookup"><span data-stu-id="31aa3-139">Expand the server tree.</span></span>  
  
2.  <span data-ttu-id="31aa3-140">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="31aa3-140">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="31aa3-141">Essa etapa depende de se você deseja excluir vários grupos de disponibilidade ou apenas um grupo de disponibilidade da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="31aa3-141">This step depends on whether you want to delete multiple availability groups or only one availability group, as follows:</span></span>  
  
    -   <span data-ttu-id="31aa3-142">Para excluir vários grupos de disponibilidade (cujas réplicas primárias estão na instância de servidor conectada), use o painel **Detalhes do Pesquisador de Objetos** para exibir e selecionar todos os grupos de disponibilidade que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="31aa3-142">To delete multiple availability groups (whose primary replicas are on the connected server instance), use the **Object Explorer Details** pane to view and select all the availability groups that you want to delete.</span></span> <span data-ttu-id="31aa3-143">Para obter mais informações, veja [Usar os detalhes do Pesquisador de Objetos para monitorar grupos de disponibilidade &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="31aa3-143">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="31aa3-144">Para excluir um único grupo de disponibilidade, selecione-o no painel **Pesquisador de Objetos** ou no painel **Detalhes do Pesquisador de Objetos** .</span><span class="sxs-lookup"><span data-stu-id="31aa3-144">To delete a single availability group, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
4.  <span data-ttu-id="31aa3-145">Clique com o botão direito do mouse no grupo ou grupos de disponibilidade selecionados e selecione o comando **Excluir** .</span><span class="sxs-lookup"><span data-stu-id="31aa3-145">Right-click the selected availability group or groups, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="31aa3-146">Na caixa de diálogo **Remover Grupo de Disponibilidade** , para excluir todos os grupos de disponibilidade listados, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="31aa3-146">In the **Remove Availability Group** dialog box, to delete all the listed availability groups, click **OK**.</span></span> <span data-ttu-id="31aa3-147">Se você não desejar remover todos os grupos de disponibilidade listados, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="31aa3-147">If you do not want to remove all the listed availability groups, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="31aa3-148">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="31aa3-148">Using Transact-SQL</span></span>  
 <span data-ttu-id="31aa3-149">**Para excluir um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="31aa3-149">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="31aa3-150">Conecte-se à instância de servidor que hospeda a réplica primária, se possível, ou conecte-se a outra instância de servidor que é habilitada para Grupos de Disponibilidade AlwaysOn em um nó WSFC que possuem as credenciais de segurança corretas para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31aa3-150">Connect to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="31aa3-151">Use a instrução [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) , da seguinte maneira</span><span class="sxs-lookup"><span data-stu-id="31aa3-151">Use the [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) statement, as follows</span></span>  
  
     <span data-ttu-id="31aa3-152">DROP AVAILABILITY GROUP *group_name*</span><span class="sxs-lookup"><span data-stu-id="31aa3-152">DROP AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="31aa3-153">em que *group_name* é o nome do grupo de disponibilidade a ser removido.</span><span class="sxs-lookup"><span data-stu-id="31aa3-153">where *group_name* is the name of the availability group to be dropped.</span></span>  
  
     <span data-ttu-id="31aa3-154">O exemplo a seguir exclui o grupo de disponibilidade `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="31aa3-154">The following example deletes the `MyAG` availability group.</span></span>  
  
    ```sql
    DROP AVAILABILITY GROUP MyAG;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="31aa3-155">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="31aa3-155">Using PowerShell</span></span>  
 <span data-ttu-id="31aa3-156">**Para excluir um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="31aa3-156">**To delete an availability group**</span></span>  
  
 <span data-ttu-id="31aa3-157">No provedor do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell:</span><span class="sxs-lookup"><span data-stu-id="31aa3-157">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="31aa3-158">Altere o diretório (`cd`) na instância de servidor que hospeda a réplica primária, se possível, ou conecte-se a outra instância de servidor que é habilitada para Grupos de Disponibilidade AlwaysOn em um nó WSFC que possuem as credenciais de segurança corretas para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31aa3-158">Change directory (`cd`) to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="31aa3-159">Use o cmdlet **Remove-SqlAvailabilityGroup** .</span><span class="sxs-lookup"><span data-stu-id="31aa3-159">Use the **Remove-SqlAvailabilityGroup** cmdlet.</span></span>  
  
     <span data-ttu-id="31aa3-160">Por exemplo, o comando a seguir remove o grupo de disponibilidade denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="31aa3-160">For example, the following command removes the availability group named `MyAg`.</span></span> <span data-ttu-id="31aa3-161">Este comando pode ser executado em qualquer instância de servidor que hospeda uma réplica de disponibilidade para o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="31aa3-161">This command can be executed on any server instance that hosts an availability replica for the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="31aa3-162">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31aa3-162">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="31aa3-163">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="31aa3-163">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="31aa3-164">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="31aa3-164">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="31aa3-165">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="31aa3-165">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="31aa3-166">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="31aa3-166">Related Content</span></span>  
  
-   <span data-ttu-id="31aa3-167">[How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (Como funcionam os comportamentos de DROP AVAILABILITY GROUP) (blog CSS SQL Server Engineers)</span><span class="sxs-lookup"><span data-stu-id="31aa3-167">[How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31aa3-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31aa3-168">See Also</span></span>  
 <span data-ttu-id="31aa3-169">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31aa3-169">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="31aa3-170">Criação e configuração de grupos de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31aa3-170">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
