---
title: Remover um ouvinte do grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeaglistener.default.f1
helpviewer_keywords:
- Availability Groups [SQL Server], listeners
ms.assetid: fd9bba9a-d29f-4c23-8ecd-aaa049ed5f1b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 057b9c137cb4d8bbbdd03be61df600f7e59b264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571608"
---
# <a name="remove-an-availability-group-listener-sql-server"></a><span data-ttu-id="4c08c-102">Remover um ouvinte de grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4c08c-102">Remove an Availability Group Listener (SQL Server)</span></span>
  <span data-ttu-id="4c08c-103">Este tópico descreve como remover um ouvinte de grupo de disponibilidade em um grupo de disponibilidade AlwaysOn usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c08c-103">This topic describes how to remove an availability group listener from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="4c08c-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4c08c-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4c08c-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4c08c-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="4c08c-106">Recomendações</span><span class="sxs-lookup"><span data-stu-id="4c08c-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4c08c-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="4c08c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4c08c-108">**Para remover um ouvinte usando:**</span><span class="sxs-lookup"><span data-stu-id="4c08c-108">**To remove a listener, using:**</span></span>  
  
     [<span data-ttu-id="4c08c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c08c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4c08c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c08c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="4c08c-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c08c-111">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4c08c-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4c08c-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4c08c-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4c08c-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="4c08c-114">Você deve estar conectado à instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="4c08c-114">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4c08c-115">Recomendações</span><span class="sxs-lookup"><span data-stu-id="4c08c-115">Recommendations</span></span>  
 <span data-ttu-id="4c08c-116">Antes de excluir um ouvinte de grupo de disponibilidade, é recomendável verificar se nenhum aplicativo o está usando.</span><span class="sxs-lookup"><span data-stu-id="4c08c-116">Before you delete an availability group listener, we recommend that you ensure that no applications are using it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4c08c-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="4c08c-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c08c-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="4c08c-118">Permissions</span></span>  
 <span data-ttu-id="4c08c-119">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4c08c-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4c08c-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c08c-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4c08c-121">**Para remover um ouvinte de grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="4c08c-121">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="4c08c-122">No Pesquisador de Objetos, conecte-se à instância do servidor que hospeda a réplica primária e clique no nome do servidor para expandir a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="4c08c-122">In Object Explorer, connect to the server instance that hosts the primary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="4c08c-123">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="4c08c-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="4c08c-124">Expanda o nó do grupo de disponibilidade e expanda o nó **Ouvintes de Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="4c08c-124">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="4c08c-125">Clique com o botão direito do mouse no ouvinte a ser removido e selecione o comando **Excluir** .</span><span class="sxs-lookup"><span data-stu-id="4c08c-125">Right-click the listener to be removed, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="4c08c-126">Isso abre a caixa de diálogo **Remover Ouvinte do Grupo de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="4c08c-126">This opens the **Remove Listener from Availability Group** dialog box.</span></span> <span data-ttu-id="4c08c-127">Para obter mais informações, consulte [Remover ouvinte do grupo de disponibilidade](#AgListenerPropertiesDialog), posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4c08c-127">For more information, see [Remove Listener from Availability Group](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="remove-listener-from-availability-group-dialog-box"></a><a name="AgListenerPropertiesDialog"></a><span data-ttu-id="4c08c-128">Remover ouvinte do grupo de disponibilidade (caixa de diálogo)</span><span class="sxs-lookup"><span data-stu-id="4c08c-128">Remove Listener from Availability Group (Dialog Box)</span></span>  
 <span data-ttu-id="4c08c-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4c08c-129">**Name**</span></span>  
 <span data-ttu-id="4c08c-130">O nome do ouvinte a ser removido.</span><span class="sxs-lookup"><span data-stu-id="4c08c-130">The name of the listener to be removed.</span></span>  
  
 <span data-ttu-id="4c08c-131">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="4c08c-131">**Result**</span></span>  
 <span data-ttu-id="4c08c-132">Exibe um link, **Êxito** ou **Erro**, em que você pode clicar para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c08c-132">Displays a link, either **Success** or **Error**, which you can click for more information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4c08c-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c08c-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="4c08c-134">**Para remover um ouvinte de grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="4c08c-134">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="4c08c-135">Conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="4c08c-135">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="4c08c-136">Use a instrução [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c08c-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="4c08c-137">ALTER AVAILABILITY GROUP *group_name* remover o ouvinte **' *`dns_name`* '**</span><span class="sxs-lookup"><span data-stu-id="4c08c-137">ALTER AVAILABILITY GROUP *group_name* REMOVE LISTENER **'*`dns_name`*'**</span></span>  
  
     <span data-ttu-id="4c08c-138">em que *group_name* é o nome do grupo de disponibilidade, e *dns_name* é o nome DNS do ouvinte do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="4c08c-138">where *group_name* is the name of the availability group and *dns_name* is the DNS name of the availability group listener.</span></span>  
  
     <span data-ttu-id="4c08c-139">O exemplo a seguir exclui o ouvinte do grupo de disponibilidade `AccountsAG` .</span><span class="sxs-lookup"><span data-stu-id="4c08c-139">The following example deletes the listener of the `AccountsAG` availability group.</span></span> <span data-ttu-id="4c08c-140">O nome DNS é AccountsAG_Listener.</span><span class="sxs-lookup"><span data-stu-id="4c08c-140">The DNS name is AccountsAG_Listener.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP AccountsAG REMOVE LISTENER 'AccountsAG_Listener';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4c08c-141">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c08c-141">Using PowerShell</span></span>  
 <span data-ttu-id="4c08c-142">**Para remover um ouvinte de grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="4c08c-142">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="4c08c-143">Defina o padrão (`cd`) para a instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="4c08c-143">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="4c08c-144">Use o cmdlet `Remove-Item` interno para remover um ouvinte.</span><span class="sxs-lookup"><span data-stu-id="4c08c-144">Use the built in `Remove-Item` cmdlet to remove a listener.</span></span> <span data-ttu-id="4c08c-145">Por exemplo, o comando a seguir remove um ouvinte denominado `MyListener` de um grupo de disponibilidade denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="4c08c-145">For example, the following command removes a listener named `MyListener` from an availability group named `MyAg`.</span></span>  
  
    ```powershell
    Remove-Item SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AGListeners\MyListener  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c08c-146">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c08c-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="4c08c-147">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4c08c-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4c08c-148">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4c08c-148">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4c08c-149">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c08c-149">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="4c08c-150">Exibir propriedades do ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c08c-150">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c08c-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4c08c-151">See Also</span></span>  
 <span data-ttu-id="4c08c-152">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4c08c-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="4c08c-153">Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c08c-153">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
