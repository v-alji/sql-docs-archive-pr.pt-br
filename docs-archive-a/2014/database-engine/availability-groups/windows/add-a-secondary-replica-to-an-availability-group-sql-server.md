---
title: Adicionar uma réplica secundária a um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 6669dcce-85f9-495f-aadf-7f62cff4a9da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 498103a781641c72e166c6b11663f5248ae5ccfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570264"
---
# <a name="add-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="bd2cf-102">Adicionar uma réplica secundária a um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bd2cf-102">Add a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="bd2cf-103">Este tópico descreve como adicionar uma réplica secundária a um grupo de disponibilidade AlwaysOn existente usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd2cf-103">This topic describes how to add a secondary replica to an existing AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="bd2cf-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="bd2cf-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bd2cf-105">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="bd2cf-105">Prerequisites and Restrictions</span></span>](#PrerequisitesRestrictions)  
  
     [<span data-ttu-id="bd2cf-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="bd2cf-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bd2cf-107">**Para adicionar uma réplica usando:**</span><span class="sxs-lookup"><span data-stu-id="bd2cf-107">**To add a replica, using:**</span></span>  
  
     [<span data-ttu-id="bd2cf-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd2cf-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bd2cf-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd2cf-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="bd2cf-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd2cf-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="bd2cf-111">**Acompanhamento:**  [depois de adicionar uma réplica secundária](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="bd2cf-111">**Follow Up:**  [After Adding a Secondary Replica](#FollowUp)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="bd2cf-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bd2cf-112">Before You Begin</span></span>  
 <span data-ttu-id="bd2cf-113">É recomendável que você leia esta seção antes de tentar criar seu primeiro grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-113">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
##  <a name="prerequisites-and-restrictions"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="bd2cf-114">Pré-requisitos e restrições</span><span class="sxs-lookup"><span data-stu-id="bd2cf-114">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="bd2cf-115">Você deve estar conectado à instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
 <span data-ttu-id="bd2cf-116">Para obter mais informações, consulte [Pré-requisitos, restrições e recomendações para grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="bd2cf-116">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bd2cf-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="bd2cf-117">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bd2cf-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="bd2cf-118">Permissions</span></span>  
 <span data-ttu-id="bd2cf-119">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bd2cf-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd2cf-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="bd2cf-121">**Para adicionar uma réplica**</span><span class="sxs-lookup"><span data-stu-id="bd2cf-121">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="bd2cf-122">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica primária e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-122">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="bd2cf-123">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="bd2cf-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="bd2cf-124">Clique com o botão direito do mouse no grupo de disponibilidade e selecione um dos comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="bd2cf-124">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="bd2cf-125">Para iniciar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade, selecione o comando **Adicionar Réplica** .</span><span class="sxs-lookup"><span data-stu-id="bd2cf-125">Select the **Add Replica** command to launch the Add Replica to Availability Group Wizard.</span></span> <span data-ttu-id="bd2cf-126">Para obter mais informações, veja [Usar o Assistente para Adicionar Réplica ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bd2cf-126">For more information, see [Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
    -   <span data-ttu-id="bd2cf-127">Opcionalmente, selecione o comando **Propriedades** para abrir a caixa de diálogo **Propriedades do Grupo de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="bd2cf-127">Alternatively, select the **Properties** command to open the **Availability Group Properties** dialog box.</span></span> <span data-ttu-id="bd2cf-128">As etapas para adicionar uma réplica nesta caixa de diálogo são:</span><span class="sxs-lookup"><span data-stu-id="bd2cf-128">The steps for adding a replica in this dialog box are as follows:</span></span>  
  
        1.  <span data-ttu-id="bd2cf-129">No painel **Réplicas de Disponibilidade** da caixa de diálogo, clique no botão **Adicionar** .</span><span class="sxs-lookup"><span data-stu-id="bd2cf-129">In the **Availability Replicas** pane of the dialog box, click the **Add** button.</span></span> <span data-ttu-id="bd2cf-130">Isso cria e seleciona uma entrada de réplica na qual o campo Instância do Servidor em branco é selecionado.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-130">This creates and selects a replica entry in which the blank Server Instance field is selected.</span></span>  
  
        2.  <span data-ttu-id="bd2cf-131">Insira o nome de uma instância do servidor que atenda aos pré-requisitos para hospedar uma réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-131">Enter the name of a server instance that meets the prerequisites for hosting an availability replica.</span></span>  
  
         <span data-ttu-id="bd2cf-132">Para adicionar mais uma réplica, repita as etapas acima.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-132">To add an additional replicas, repeat the preceding steps.</span></span> <span data-ttu-id="bd2cf-133">Ao concluir a especificação das réplicas, clique em **OK** para concluir a operação.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-133">When you are done specifying replicas, click **OK** to complete the operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bd2cf-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bd2cf-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="bd2cf-135">**Para adicionar uma réplica**</span><span class="sxs-lookup"><span data-stu-id="bd2cf-135">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="bd2cf-136">Conecte-se à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-136">Connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="bd2cf-137">Adicione a nova réplica secundária ao grupo de disponibilidade usando a cláusula ADD REPLICA ON da instrução ALTER AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-137">Add the new secondary replica to the availability group by using the ADD REPLICA ON clause of the ALTER AVAILABILITY GROUP statement.</span></span> <span data-ttu-id="bd2cf-138">As opções ENDPOINT_URL, AVAILABILITY_MODE e FAILOVER_MODE são necessárias em uma cláusula ADD REPLICA ON.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-138">The ENDPOINT_URL, AVAILABILITY_MODE, and FAILOVER_MODE options are required in an ADD REPLICA ON clause.</span></span> <span data-ttu-id="bd2cf-139">As outras opções de réplica – BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE e SESSION_TIMEOUT – são opcionais.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-139">The other replica options- BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE, and SESSION_TIMEOUT-are optional.</span></span> <span data-ttu-id="bd2cf-140">Para obter mais informações, consulte [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bd2cf-140">For more information, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="bd2cf-141">Por exemplo, a instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] a seguir cria uma nova réplica para um grupo de disponibilidade denominado `MyAG` na instância de servidor padrão hospedada por `COMPUTER04`cuja URL de ponto de extremidade é `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-141">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement creates a new replica to an availability group named `MyAG` on the default server instance hosted by `COMPUTER04`, whose endpoint URL is `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span></span> <span data-ttu-id="bd2cf-142">Esta réplica dá suporte a failover manual e ao modo de disponibilidade de confirmação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-142">This replica supports manual failover and asynchronous-commit availability mode.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG ADD REPLICA ON 'COMPUTER04'   
       WITH (  
             ENDPOINT_URL = 'TCP://COMPUTER04.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="bd2cf-143">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd2cf-143">Using PowerShell</span></span>  
 <span data-ttu-id="bd2cf-144">**Para adicionar uma réplica**</span><span class="sxs-lookup"><span data-stu-id="bd2cf-144">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="bd2cf-145">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-145">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="bd2cf-146">Use o cmdlet **New-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="bd2cf-146">Use the **New-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="bd2cf-147">Por exemplo, o comando a seguir adiciona uma réplica de disponibilidade a um grupo de disponibilidade existente denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-147">For example, the following command adds an availability replica to an existing availability group named `MyAg`.</span></span> <span data-ttu-id="bd2cf-148">Esta réplica dá suporte a failover manual e ao modo de disponibilidade de confirmação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-148">This replica supports manual failover and asynchronous-commit availability mode.</span></span> <span data-ttu-id="bd2cf-149">Na função secundária, esta réplica dará suporte a conexões de acesso de leitura, permitindo descarregar o processamento somente leitura para esta réplica.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-149">In the secondary role, this replica will support read access connections, allowing you to offload read-only processing to this replica.</span></span>  
  
    ```powershell
    $agPath = "SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
    $endpointURL = "TCP://PrimaryServerName.domain.com:5022"  
    $failoverMode = "Manual"  
    $availabilityMode = "AsynchronousCommit"  
    $secondaryReadMode = "AllowAllConnections"  
  
    New-SqlAvailabilityReplica -Name SecondaryServer\Instance `   
    -EndpointUrl $endpointURL `   
    -FailoverMode $failoverMode `   
    -AvailabilityMode $availabilityMode `   
    -ConnectionModeInSecondaryRole $secondaryReadMode `   
    -Path $agPath  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="bd2cf-150">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="bd2cf-151">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bd2cf-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="bd2cf-152">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bd2cf-152">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="bd2cf-153">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd2cf-153">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-adding-a-secondary-replica"></a><a name="FollowUp"></a> <span data-ttu-id="bd2cf-154">Acompanhamento: depois de adicionar uma réplica secundária</span><span class="sxs-lookup"><span data-stu-id="bd2cf-154">Follow Up: After Adding a Secondary Replica</span></span>  
 <span data-ttu-id="bd2cf-155">Para adicionar uma réplica para um grupo de disponibilidade existente, você deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="bd2cf-155">To add a replica for an existing availability group, you must perform the following steps:</span></span>  
  
1.  <span data-ttu-id="bd2cf-156">Conecte-se à instância do servidor que deve hospedar a nova réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-156">Connect to the server instance that is going to host the new secondary replica.</span></span>  
  
2.  <span data-ttu-id="bd2cf-157">Una a nova réplica secundária ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-157">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="bd2cf-158">Para obter mais informações, veja [Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd2cf-158">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="bd2cf-159">Para cada banco de dados do grupo de disponibilidade, crie um banco de dados secundário na instância do servidor que está hospedando a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-159">For each database in the availability group, create a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="bd2cf-160">Para obter mais informações, consulte [Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd2cf-160">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="bd2cf-161">Una cada um dos novos bancos de dados secundários ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="bd2cf-161">Join each of the new secondary databases to the availability group.</span></span> <span data-ttu-id="bd2cf-162">Para obter mais informações, consulte [Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd2cf-162">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="bd2cf-163">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="bd2cf-163">Related Tasks</span></span>  
 <span data-ttu-id="bd2cf-164">**Para gerenciar uma réplica de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="bd2cf-164">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="bd2cf-165">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2cf-165">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="bd2cf-166">Remover uma réplica secundária de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2cf-166">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="bd2cf-167">Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2cf-167">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="bd2cf-168">Alterar o modo de disponibilidade de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2cf-168">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="bd2cf-169">Alterar o modo de failover de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2cf-169">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="bd2cf-170">Alterar o período de tempo limite da sessão de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2cf-170">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="bd2cf-171">Alterar o período de tempo limite da sessão de uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2cf-171">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd2cf-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bd2cf-172">See Also</span></span>  
 <span data-ttu-id="bd2cf-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd2cf-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="bd2cf-174">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bd2cf-174">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="bd2cf-175">[Criação e configuração de grupos de disponibilidade &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bd2cf-175">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="bd2cf-176">[Use o painel AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="bd2cf-176">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="bd2cf-177">Monitorar grupos de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bd2cf-177">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
