---
title: Usar políticas AlwaysOn para exibir a integridade de um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6f1bcbc3-1220-4071-8e53-4b957f5d3089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c4444afc2348b2407dc19c1c12761ef0251631e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685277"
---
# <a name="use-alwayson-policies-to-view-the-health-of-an-availability-group-sql-server"></a><span data-ttu-id="fed40-102">Use as políticas AlwaysOn para exibir a integridade de um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fed40-102">Use AlwaysOn Policies to View the Health of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="fed40-103">Este tópico descreve como determinar a integridade operacional de um grupo de disponibilidade AlwaysOn usando a política AlwaysOn no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fed40-103">This topic describes how to determine the operational health of an AlwaysOn availability group by using an AlwaysOn policy in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="fed40-104">Para obter informações sobre o gerenciamento baseado em políticas AlwaysOn, consulte [políticas AlwaysOn para problemas operacionais com o grupos de disponibilidade AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="fed40-104">For information about AlwaysOn Policy Based Management, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fed40-105">Para políticas de AlwaysOn, os nomes das categorias são usados como IDs.</span><span class="sxs-lookup"><span data-stu-id="fed40-105">For AlwaysOn policies, the category names are used as IDs.</span></span> <span data-ttu-id="fed40-106">A alteração do nome de uma categoria AlwaysOn interrompe sua funcionalidade de avaliação de integridade.</span><span class="sxs-lookup"><span data-stu-id="fed40-106">Changing the name of an AlwaysOn category would break its health-evaluation functionality.</span></span> <span data-ttu-id="fed40-107">Portanto, os nomes das categorias AlwaysOn nunca devem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="fed40-107">Therefore, the names of AlwaysOn category should never be modified.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fed40-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fed40-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fed40-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="fed40-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fed40-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="fed40-110">Permissions</span></span>  
 <span data-ttu-id="fed40-111">Requer as permissões CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="fed40-111">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="using-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="fed40-112">Usando o painel AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="fed40-112">Using the AlwaysOn Dashboard</span></span>  
 <span data-ttu-id="fed40-113">**Para abrir o Painel de AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="fed40-113">**To open the AlwaysOn Dashboard**</span></span>  
  
1.  <span data-ttu-id="fed40-114">No Pesquisador de Objetos, conecte-se à instância do servidor que hospeda uma das réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fed40-114">In Object Explorer, connect to the server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="fed40-115">Para exibir informações sobre todas as réplicas de disponibilidade em um grupo de disponibilidade, use a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="fed40-115">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="fed40-116">Clique no nome do servidor para expandir a arvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="fed40-116">Click the server name to expand the server tree.</span></span>  
  
3.  <span data-ttu-id="fed40-117">Expanda o nó **Alta Disponibilidade AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="fed40-117">Expand the **AlwaysOn High Availability** node.</span></span>  
  
     <span data-ttu-id="fed40-118">Clique com o botão direito do mouse no nó **Grupos de Disponibilidade** ou expanda esse nó e clique com o botão direito do mouse em um grupo de disponibilidade específico.</span><span class="sxs-lookup"><span data-stu-id="fed40-118">Either right-click the **Availability Groups** node or expand this node and right-click a specific availability group.</span></span>  
  
4.  <span data-ttu-id="fed40-119">Selecione o comando **Mostrar Painel** .</span><span class="sxs-lookup"><span data-stu-id="fed40-119">Select the **Show Dashboard** command.</span></span>  
  
 <span data-ttu-id="fed40-120">Para obter informações sobre como usar o Painel AlwaysOn, consulte [Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="fed40-120">For information about how to use the AlwaysOn Dashboard, see [Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="fed40-121">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fed40-121">Using PowerShell</span></span>  
 <span data-ttu-id="fed40-122">**Usar políticas AlwaysOn para exibir a integridade de um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="fed40-122">**Use AlwaysOn policies to view the health of an availability group**</span></span>  
  
1.  <span data-ttu-id="fed40-123">Defina o padrão (`cd`) como uma instância de servidor que hospeda uma das réplicas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fed40-123">Set default (`cd`) to a server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="fed40-124">Para exibir informações sobre todas as réplicas de disponibilidade em um grupo de disponibilidade, use a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="fed40-124">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="fed40-125">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="fed40-125">Use the following cmdlets:</span></span>  
  
     `Test-SqlAvailabilityGroup`  
     <span data-ttu-id="fed40-126">Avalia a integridade de um grupo de disponibilidade avaliando as políticas do PBM (gerenciamento baseado em políticas) do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fed40-126">Assesses the health of an availability group by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="fed40-127">Você deve ter as permissões CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fed40-127">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="fed40-128">Por exemplo, o comando a seguir mostra todos os grupos de disponibilidade com o estado de integridade "Error" na instância de servidor `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="fed40-128">For example, the following command shows all availability groups with a health state of "Error" on the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups |
        Test-SqlAvailabilityGroup |
        Where-Object { $_.HealthState -eq "Error" }  
    ```  
  
     `Test-SqlAvailabilityReplica`  
     <span data-ttu-id="fed40-129">Avalia a integridade de réplicas de disponibilidade avaliando as políticas do PBM (gerenciamento baseado em políticas) do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fed40-129">Assesses the health of availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="fed40-130">Você deve ter as permissões CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION para executar esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fed40-130">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="fed40-131">Por exemplo, o comando a seguir avalia a integridade da réplica de disponibilidade denominada `MyReplica` no grupo de disponibilidade `MyAg` e gera um breve resumo.</span><span class="sxs-lookup"><span data-stu-id="fed40-131">For example, the following command evaluates the health of the availability replica named `MyReplica` in the availability group `MyAg` and outputs a brief summary.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityReplica -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
     `Test-SqlDatabaseReplicaState`  
     <span data-ttu-id="fed40-132">Avalia a integridade de um banco de dados de disponibilidade em todas as réplicas de disponibilidade unidas avaliando as políticas do PBM (gerenciamento baseado em políticas) do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fed40-132">Assesses the health of an availability database on all joined availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span>  
  
     <span data-ttu-id="fed40-133">Por exemplo, o comando a seguir avalia a integridade de todos os bancos de dados de disponibilidade no grupo de disponibilidade `MyAg` e gera um breve resumo para cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fed40-133">For example, the following command evaluates the health of all availability databases in the availability group `MyAg` and outputs a brief summary for each database.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\DatabaseReplicaStates |
        Test-SqlDatabaseReplicaState  
    ```  
  
     <span data-ttu-id="fed40-134">Esses cmdlets aceitam as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fed40-134">These cmdlets accept the following options:</span></span>  
  
    |<span data-ttu-id="fed40-135">Opção</span><span class="sxs-lookup"><span data-stu-id="fed40-135">Option</span></span>|<span data-ttu-id="fed40-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="fed40-136">Description</span></span>|  
    |------------|-----------------|  
    |`AllowUserPolicies`|<span data-ttu-id="fed40-137">Executa as políticas de usuário localizadas nas categorias de políticas AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="fed40-137">Runs user policies found in the AlwaysOn policy categories.</span></span>|  
    |`InputObject`|<span data-ttu-id="fed40-138">Uma coleção de objetos que representam grupos de disponibilidade, réplicas de disponibilidade ou estados de bancos de dados de disponibilidade (dependendo de qual cmdlet que você está usando).</span><span class="sxs-lookup"><span data-stu-id="fed40-138">A collection of objects that, represent availability groups, availability replicas, or availability database states (depending on which cmdlet you are using).</span></span> <span data-ttu-id="fed40-139">O cmdlet computará a integridade dos objetos especificados.</span><span class="sxs-lookup"><span data-stu-id="fed40-139">The cmdlet will compute the health of the specified objects.</span></span>|  
    |`NoRefresh`|<span data-ttu-id="fed40-140">Quando esse parâmetro estiver definido, o cmdlet não atualizará manualmente os objetos especificados pelo parâmetro `-Path` ou `-InputObject`.</span><span class="sxs-lookup"><span data-stu-id="fed40-140">When this parameter is set, the cmdlet will not manually refresh the objects specified by the `-Path` or `-InputObject` parameter.</span></span>|  
    |`Path`|<span data-ttu-id="fed40-141">O caminho para o grupo de disponibilidade, uma ou mais réplicas de disponibilidade ou o estado do cluster de réplicas do banco de dados de disponibilidade (dependendo do cmdlet que você está usando).</span><span class="sxs-lookup"><span data-stu-id="fed40-141">The path to the availability group, one or more availability replicas, or database replica cluster state of the availability database (depending on which cmdlet you are using).</span></span> <span data-ttu-id="fed40-142">Esse é um parâmetro opcional.</span><span class="sxs-lookup"><span data-stu-id="fed40-142">This is an optional parameter.</span></span> <span data-ttu-id="fed40-143">Se não for especificado, o valor desse parâmetro será padronizado como o local de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="fed40-143">If not specified, the value of this parameter defaults to the current working location.</span></span>|  
    |`ShowPolicyDetails`|<span data-ttu-id="fed40-144">Mostra o resultado de cada avaliação de política executada por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fed40-144">Shows the result of each policy evaluation performed by this cmdlet.</span></span> <span data-ttu-id="fed40-145">O cmdlet produz um objeto por avaliação de política e esse objeto tem campos que descrevem os resultados da avaliação (se a política é aprovada ou não, o nome e a categoria da política e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="fed40-145">The cmdlet outputs one object per policy evaluation, and this object has fields describing the results of evaluation (whether the policy passed or not, the policy name and category, and so forth).</span></span>|  
  
     <span data-ttu-id="fed40-146">Por exemplo, o comando `Test-SqlAvailabilityGroup` a seguir especifica o parâmetro `-ShowPolicyDetails` para mostrar o resultado de cada avaliação de política executada por esse cmdlet para cada política de gerenciamento baseada em políticas (PBM) que foi executada no grupo de disponibilidade denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="fed40-146">For example, the following `Test-SqlAvailabilityGroup` command specifies the `-ShowPolicyDetails` parameter to show the result of each policy evaluation performed by this cmdlet for each policy-based management (PBM) policy that was executed on the availability group named `MyAg`.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\AgName -ShowPolicyDetails  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="fed40-147">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fed40-147">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="fed40-148">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fed40-148">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="fed40-149">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fed40-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="fed40-150">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fed40-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="fed40-151">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="fed40-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="fed40-152">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="fed40-152">Related Content</span></span>  
 <span data-ttu-id="fed40-153">**SQL Server Blogs da equipe AlwaysOn – monitorando a integridade do AlwaysOn com o PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="fed40-153">**SQL Server AlwaysOn Team Blogs-Monitoring AlwaysOn Health with PowerShell:**</span></span>  
  
-   [<span data-ttu-id="fed40-154">Parte 1: Visão geral básica de cmdlet</span><span class="sxs-lookup"><span data-stu-id="fed40-154">Part 1: Basic Cmdlet Overview</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-1-basic-cmdlet-overview)  
  
-   [<span data-ttu-id="fed40-155">Parte 2: Uso avançado de cmdlet</span><span class="sxs-lookup"><span data-stu-id="fed40-155">Part 2: Advanced Cmdlet Usage</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/the-alwayson-health-model-part-2-extending-the-health-model)  
  
-   [<span data-ttu-id="fed40-156">Parte 3: Um simples aplicativo de monitoramento</span><span class="sxs-lookup"><span data-stu-id="fed40-156">Part 3: A Simple Monitoring Application</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-3-a-simple-monitoring-application)  
  
-   [<span data-ttu-id="fed40-157">Parte 4: Integração com o SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="fed40-157">Part 4: Integration with SQL Server Agent</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-4-integration-with-sql-server-agent)  
  
## <a name="see-also"></a><span data-ttu-id="fed40-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fed40-158">See Also</span></span>  
 <span data-ttu-id="fed40-159">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fed40-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="fed40-160">[Administração de um grupo de disponibilidade &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fed40-160">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="fed40-161">[Monitoramento de grupos de disponibilidade &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fed40-161">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="fed40-162">Políticas AlwaysOn para problemas operacionais com grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fed40-162">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-policies-for-operational-issues-always-on-availability.md) 
