---
title: Usar o painel AlwaysOn (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
- Availability Groups [SQL Server], dashboard
ms.assetid: c9ba2589-139e-42bc-99e1-94546717c64d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4ce0072bcd6642dcb4f3ac63e04c98786bd550e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571597"
---
# <a name="use-the-alwayson-dashboard-sql-server-management-studio"></a><span data-ttu-id="daa14-102">Use the AlwaysOn Dashboard (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="daa14-102">Use the AlwaysOn Dashboard (SQL Server Management Studio)</span></span>
  <span data-ttu-id="daa14-103">Os administradores de banco de dados usam o Painel AlwaysOn para obter uma visão específica da integridade de um grupo de disponibilidade AlwaysOn e suas réplicas de disponibilidade e bancos de dados no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daa14-103">Database administrators use the AlwaysOn Dashboard to obtains an at-a-glance view the health of an AlwaysOn availability group and its availability replicas and databases in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="daa14-104">Alguns dos usos típicos do Painel AlwaysOn são:</span><span class="sxs-lookup"><span data-stu-id="daa14-104">Some of the typical uses for the AlwaysOn Dashboard are:</span></span>  
  
-   <span data-ttu-id="daa14-105">Escolhendo uma réplica para um failover manual.</span><span class="sxs-lookup"><span data-stu-id="daa14-105">Choosing a replica for a manual failover.</span></span>  
  
-   <span data-ttu-id="daa14-106">Estimando a perda de dados se você forçar um failover.</span><span class="sxs-lookup"><span data-stu-id="daa14-106">Estimating data loss if you force failover.</span></span>  
  
-   <span data-ttu-id="daa14-107">Avaliando o desempenho da sincronização de dados.</span><span class="sxs-lookup"><span data-stu-id="daa14-107">Evaluating data-synchronization performance.</span></span>  
  
-   <span data-ttu-id="daa14-108">Avaliando o impacto do desempenho de uma réplica secundária de confirmação síncrona</span><span class="sxs-lookup"><span data-stu-id="daa14-108">Evaluating the performance impact of a synchronous-commit secondary replica</span></span>  
  
 <span data-ttu-id="daa14-109">O Painel AlwaysOn fornece estados e indicadores importantes de desempenho do grupo que permitem tomar decisões operacionais de alta disponibilidade usando os seguintes tipos de informações.</span><span class="sxs-lookup"><span data-stu-id="daa14-109">The AlwaysOn Dashboard provides key availability group states and performance indicators allowing you to easily make high availability operational decisions using the following types of information.</span></span>  
  
-   <span data-ttu-id="daa14-110">Estado de acúmulo da réplica</span><span class="sxs-lookup"><span data-stu-id="daa14-110">Replica roll-up state</span></span>  
  
-   <span data-ttu-id="daa14-111">Modo e estado da sincronização</span><span class="sxs-lookup"><span data-stu-id="daa14-111">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="daa14-112">Perda de dados estimada</span><span class="sxs-lookup"><span data-stu-id="daa14-112">Estimate Data Loss</span></span>  
  
-   <span data-ttu-id="daa14-113">Tempo de recuperação estimado (refazer recuperação do atraso)</span><span class="sxs-lookup"><span data-stu-id="daa14-113">Estimated Recovery Time (redo catch up)</span></span>  
  
-   <span data-ttu-id="daa14-114">Detalhes da réplica de banco de dados</span><span class="sxs-lookup"><span data-stu-id="daa14-114">Database Replica details</span></span>  
  
-   <span data-ttu-id="daa14-115">Modo e estado da sincronização</span><span class="sxs-lookup"><span data-stu-id="daa14-115">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="daa14-116">Tempo para restauração do log</span><span class="sxs-lookup"><span data-stu-id="daa14-116">Time to restore log</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="daa14-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="daa14-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="daa14-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="daa14-118">Prerequisites</span></span>  
 <span data-ttu-id="daa14-119">Conecte-se à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (instância de servidor) que hospeda a réplica primária ou secundária de um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-119">You must be connected to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (server instance) that hosts either the primary replica or a secondary replica of an availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="daa14-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="daa14-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="daa14-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="daa14-121">Permissions</span></span>  
 <span data-ttu-id="daa14-122">Requer as permissões CONNECT, VIEW SERVER STATE e VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="daa14-122">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="to-start-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="daa14-123">Para iniciar o painel AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="daa14-123">To start the AlwaysOn Dashboard</span></span>  
  
1.  <span data-ttu-id="daa14-124">No Pesquisador de Objetos, conecte à instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na qual você deseja executar o Painel AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="daa14-124">In Object Explorer, connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on which you want to run the AlwaysOn Dashboard.</span></span>  
  
2.  <span data-ttu-id="daa14-125">Expanda o nó **Alta Disponibilidade AlwaysOn**, clique com o botão direito do mouse em **Grupos de Disponibilidade** e clique em **Mostrar Painel**.</span><span class="sxs-lookup"><span data-stu-id="daa14-125">Expand the **AlwaysOn High Availability** node, right-click the **Availability Groups** node, and then click **Show Dashboard**.</span></span>  
  
###  <a name="to-change-alwayson-dashboard-options"></a><a name="DashboardOptions"></a><span data-ttu-id="daa14-126">Para alterar as opções do painel AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="daa14-126">To Change AlwaysOn Dashboard Options</span></span>  
 <span data-ttu-id="daa14-127">Você pode usar a caixa de diálogo [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Opções** para configurar o comportamento do Painel AlwaysOn do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para atualização e habilitação automática de uma política de AlwaysOn definida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="daa14-127">You can use the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** dialog box to configure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn Dashboard behavior for automatic refreshing and enabling an auto-defined AlwaysOn policy.</span></span>  
  
1.  <span data-ttu-id="daa14-128">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="daa14-128">From the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="daa14-129">Para atualizar o painel automaticamente, na caixa de diálogo **Opções** , selecione **Ativar atualização automática**, digite o intervalo de atualização em segundos e o número de vezes que você deseja repetir a conexão.</span><span class="sxs-lookup"><span data-stu-id="daa14-129">To automatically refresh the dashboard, in the **Options** dialog box, select **Turn on automatic refresh**, enter the refresh interval in seconds, and then enter the number of times you want to retry the connection.</span></span>  
  
3.  <span data-ttu-id="daa14-130">Para habilitar uma política definida pelo usuário, selecione **Habilitar política AlwaysOn definida pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="daa14-130">To enable a user-defined policy, select **Enable user-defined AlwaysOn policy**.</span></span>  
  
##  <a name="availability-group-summary"></a><a name="AvGroupsView"></a><span data-ttu-id="daa14-131">Resumo do grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="daa14-131">Availability Group Summary</span></span>  
 <span data-ttu-id="daa14-132">A tela de grupo de disponibilidade exibe uma linha de resumo para cada grupo de disponibilidade para o qual a instância de servidor conectada hospeda uma réplica.</span><span class="sxs-lookup"><span data-stu-id="daa14-132">The availability group screen displays a summary line for each availability group for which the connected server instance hosts a replica.</span></span> <span data-ttu-id="daa14-133">Esse painel exibe as seguintes colunas.</span><span class="sxs-lookup"><span data-stu-id="daa14-133">This pane displays the following columns.</span></span>  
  
 <span data-ttu-id="daa14-134">**Nome do grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="daa14-134">**Availability Group Name**</span></span>  
 <span data-ttu-id="daa14-135">O nome de um grupo de disponibilidade para o qual a instância local hospeda uma réplica.</span><span class="sxs-lookup"><span data-stu-id="daa14-135">The name of an availability group for which the connected server instance hosts a replica.</span></span>  
  
 <span data-ttu-id="daa14-136">**Instância primária**</span><span class="sxs-lookup"><span data-stu-id="daa14-136">**Primary Instance**</span></span>  
 <span data-ttu-id="daa14-137">O nome da instância do servidor que está hospedando a réplica primária do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-137">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="daa14-138">**Modo de Failover**</span><span class="sxs-lookup"><span data-stu-id="daa14-138">**Failover Mode**</span></span>  
 <span data-ttu-id="daa14-139">Exibe o modo de failover para o qual a réplica está configurada.</span><span class="sxs-lookup"><span data-stu-id="daa14-139">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="daa14-140">Os valores possíveis do modo de failover são:</span><span class="sxs-lookup"><span data-stu-id="daa14-140">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="daa14-141">**Automático**.</span><span class="sxs-lookup"><span data-stu-id="daa14-141">**Automatic**.</span></span> <span data-ttu-id="daa14-142">Indica que uma ou mais réplicas estão em modo de failover automático.</span><span class="sxs-lookup"><span data-stu-id="daa14-142">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="daa14-143">**Manual**.</span><span class="sxs-lookup"><span data-stu-id="daa14-143">**Manual**.</span></span> <span data-ttu-id="daa14-144">Indica que nenhuma réplica está em modo de failover automático.</span><span class="sxs-lookup"><span data-stu-id="daa14-144">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="daa14-145">**Problemas**</span><span class="sxs-lookup"><span data-stu-id="daa14-145">**Issues**</span></span>  
 <span data-ttu-id="daa14-146">Clique no link **Problemas** para abrir documentação de solução de problemas para determinado problema.</span><span class="sxs-lookup"><span data-stu-id="daa14-146">Click the **Issues** link to open troubleshooting documentation for a given issue.</span></span> <span data-ttu-id="daa14-147">Para obter uma lista de todos os problemas da política AlwaysOn, consulte [políticas AlwaysOn para problemas operacionais com o grupos de disponibilidade AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="daa14-147">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="daa14-148">Clique nos títulos das colunas para classificar as informações de grupo de disponibilidade pelo nome do grupo de disponibilidade, a instância primária, o modo de failover ou o Problema.</span><span class="sxs-lookup"><span data-stu-id="daa14-148">Click the column headings to sort the availability group information by the name of the availability group, primary instance, failover mode, or Issue.</span></span>  
  
##  <a name="availability-group-details"></a><a name="AvGroupDetails"></a> <span data-ttu-id="daa14-149">Detalhes do grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="daa14-149">Availability Group Details</span></span>  
 <span data-ttu-id="daa14-150">As informações de detalhes a seguir são exibidas para o grupo de disponibilidade que você seleciona na tela de resumo:</span><span class="sxs-lookup"><span data-stu-id="daa14-150">The following detail information is displayed for the availability group that you select from the summary screen:</span></span>  
  
 <span data-ttu-id="daa14-151">**Estado do grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="daa14-151">**Availability group state**</span></span>  
 <span data-ttu-id="daa14-152">Exibe o estado de integridade do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-152">Displays the state of health for the availability group.</span></span>  
  
 <span data-ttu-id="daa14-153">**Primary instance**</span><span class="sxs-lookup"><span data-stu-id="daa14-153">**Primary instance**</span></span>  
 <span data-ttu-id="daa14-154">O nome da instância do servidor que está hospedando a réplica primária do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-154">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="daa14-155">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="daa14-155">**Failover mode**</span></span>  
 <span data-ttu-id="daa14-156">Exibe o modo de failover para o qual a réplica está configurada.</span><span class="sxs-lookup"><span data-stu-id="daa14-156">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="daa14-157">Os valores possíveis do modo de failover são:</span><span class="sxs-lookup"><span data-stu-id="daa14-157">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="daa14-158">**Automático**.</span><span class="sxs-lookup"><span data-stu-id="daa14-158">**Automatic**.</span></span> <span data-ttu-id="daa14-159">Indica que uma ou mais réplicas estão em modo de failover automático.</span><span class="sxs-lookup"><span data-stu-id="daa14-159">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="daa14-160">**Manual**.</span><span class="sxs-lookup"><span data-stu-id="daa14-160">**Manual**.</span></span> <span data-ttu-id="daa14-161">Indica que nenhuma réplica está em modo de failover automático.</span><span class="sxs-lookup"><span data-stu-id="daa14-161">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="daa14-162">**Estado do cluster**</span><span class="sxs-lookup"><span data-stu-id="daa14-162">**Cluster state**</span></span>  
 <span data-ttu-id="daa14-163">O nome e o estado do cluster onde a instância do servidor conectado e o grupo de disponibilidade são nós membros.</span><span class="sxs-lookup"><span data-stu-id="daa14-163">Name and state of the cluster where the instance of the connected server and the availability group is a member node.</span></span>  
  
##  <a name="availability-replica-details"></a><a name="AvReplicaDetails"></a> <span data-ttu-id="daa14-164">Detalhes da réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="daa14-164">Availability Replica Details</span></span>  
 <span data-ttu-id="daa14-165">O painel **Réplica de Disponibilidade** exibe as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="daa14-165">The **Availability replica** pane displays the following columns:</span></span>  
  
 <span data-ttu-id="daa14-166">**Nome**</span><span class="sxs-lookup"><span data-stu-id="daa14-166">**Name**</span></span>  
 <span data-ttu-id="daa14-167">O nome da instância do servidor que hospeda a réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-167">The name of the server instance that hosts the availability replica.</span></span> <span data-ttu-id="daa14-168">Essa coluna é mostrada por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-168">This column is shown by default.</span></span>  
  
 <span data-ttu-id="daa14-169">**Função**</span><span class="sxs-lookup"><span data-stu-id="daa14-169">**Role**</span></span>  
 <span data-ttu-id="daa14-170">Indica a função atual da réplica de disponibilidade, **Primária** ou **Secundária**.</span><span class="sxs-lookup"><span data-stu-id="daa14-170">Indicates the current role of the availability replica, either **Primary** or **Secondary**.</span></span> <span data-ttu-id="daa14-171">Para obter informações sobre as funções do [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], consulte [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="daa14-171">For information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] roles, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span> <span data-ttu-id="daa14-172">Essa coluna é mostrada por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-172">This column is shown by default.</span></span>  
  
 <span data-ttu-id="daa14-173">**Modo de Failover**</span><span class="sxs-lookup"><span data-stu-id="daa14-173">**Failover Mode**</span></span>  
 <span data-ttu-id="daa14-174">Exibe o modo de failover para o qual a réplica está configurada.</span><span class="sxs-lookup"><span data-stu-id="daa14-174">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="daa14-175">Os valores possíveis do modo de failover são:</span><span class="sxs-lookup"><span data-stu-id="daa14-175">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="daa14-176">**Automático**.</span><span class="sxs-lookup"><span data-stu-id="daa14-176">**Automatic**.</span></span> <span data-ttu-id="daa14-177">Indica que uma ou mais réplicas estão em modo de failover automático.</span><span class="sxs-lookup"><span data-stu-id="daa14-177">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="daa14-178">**Manual**.</span><span class="sxs-lookup"><span data-stu-id="daa14-178">**Manual**.</span></span> <span data-ttu-id="daa14-179">Indica que nenhuma réplica está em modo de failover automático.</span><span class="sxs-lookup"><span data-stu-id="daa14-179">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="daa14-180">**Estado da Sincronização**</span><span class="sxs-lookup"><span data-stu-id="daa14-180">**Synchronization State**</span></span>  
 <span data-ttu-id="daa14-181">Indica se uma réplica secundária está sincronizada no momento com a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-181">Indicates whether a secondary replica is currently synchronized with primary replica.</span></span> <span data-ttu-id="daa14-182">Essa coluna é mostrada por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-182">This column is shown by default.</span></span> <span data-ttu-id="daa14-183">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="daa14-183">The possible values are:</span></span>  
  
-   <span data-ttu-id="daa14-184">**Não sincronizado**.</span><span class="sxs-lookup"><span data-stu-id="daa14-184">**Not Synchronized**.</span></span> <span data-ttu-id="daa14-185">Um ou mais bancos de dados na réplica não estão sincronizado ou ainda não foram unidos ao grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-185">One or more databases in the replica are not synchronized or have not yet been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="daa14-186">**Sincronizando**.</span><span class="sxs-lookup"><span data-stu-id="daa14-186">**Synchronizing**.</span></span> <span data-ttu-id="daa14-187">Um ou mais bancos de dados na réplica estão sendo sincronizados.</span><span class="sxs-lookup"><span data-stu-id="daa14-187">One or more databases in the replica are being synchronized.</span></span>  
  
-   <span data-ttu-id="daa14-188">**Sincronizado**.</span><span class="sxs-lookup"><span data-stu-id="daa14-188">**Synchronized**.</span></span> <span data-ttu-id="daa14-189">Todos os bancos de dados na réplica secundária são sincronizados com os bancos de dados primário correspondentes na réplica primária atual, se houver, ou na réplica primária mais recente.</span><span class="sxs-lookup"><span data-stu-id="daa14-189">All databases in the secondary replica are synchronized with the corresponding primary databases on the current primary replica, if any, or on the last primary replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="daa14-190">Em modo de desempenho, o banco de dados nunca está no estado sincronizado.</span><span class="sxs-lookup"><span data-stu-id="daa14-190">In performance mode, the database is never in the synchronized state.</span></span>  
  
-   <span data-ttu-id="daa14-191">**NULL**.</span><span class="sxs-lookup"><span data-stu-id="daa14-191">**NULL**.</span></span> <span data-ttu-id="daa14-192">Estado desconhecido.</span><span class="sxs-lookup"><span data-stu-id="daa14-192">Unknown state.</span></span> <span data-ttu-id="daa14-193">Este valor ocorre quando a instância do servidor local não pode se comunicar com o cluster de failover do WSFC (isto é, o nó local não faz parte do quorum do WSFC).</span><span class="sxs-lookup"><span data-stu-id="daa14-193">This value occurs when the local server instance cannot communicate with the WSFC failover cluster (that is the local node is not part of WSFC quorum).</span></span>  
  
 <span data-ttu-id="daa14-194">**Problemas**</span><span class="sxs-lookup"><span data-stu-id="daa14-194">**Issues**</span></span>  
 <span data-ttu-id="daa14-195">Lista o nome do problema.</span><span class="sxs-lookup"><span data-stu-id="daa14-195">Lists the issue name.</span></span> <span data-ttu-id="daa14-196">Esse valor é mostrado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-196">This value is shown by default.</span></span> <span data-ttu-id="daa14-197">Para obter uma lista de todos os problemas da política AlwaysOn, consulte [políticas AlwaysOn para problemas operacionais com o grupos de disponibilidade AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="daa14-197">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="daa14-198">**Modo de Disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="daa14-198">**Availability Mode**</span></span>  
 <span data-ttu-id="daa14-199">Indica a propriedade de réplica que você define separadamente para cada réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-199">Indicates the replica property that you set separately for each availability replica.</span></span> <span data-ttu-id="daa14-200">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-200">This value is hidden by default.</span></span> <span data-ttu-id="daa14-201">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="daa14-201">The possible values are:</span></span>  
  
-   <span data-ttu-id="daa14-202">**Assíncrono**.</span><span class="sxs-lookup"><span data-stu-id="daa14-202">**Asynchronous**.</span></span> <span data-ttu-id="daa14-203">A réplica secundária nunca é sincronizada com a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-203">The secondary replica never becomes synchronized with the primary replica.</span></span>  
  
-   <span data-ttu-id="daa14-204">**Síncrono**.</span><span class="sxs-lookup"><span data-stu-id="daa14-204">**Synchronous**.</span></span> <span data-ttu-id="daa14-205">Ao ficar em dia com o banco de dados primário, um banco de dados secundário entra nesse estado e permanece em dia, desde que a sincronização continue para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="daa14-205">When catching up to the primary database, a secondary database enters this state, and it remains caught up as long as data synchronization continues for the database.</span></span>  
  
 <span data-ttu-id="daa14-206">**Modo de Conexão Primário**</span><span class="sxs-lookup"><span data-stu-id="daa14-206">**Primary Connection Mode**</span></span>  
 <span data-ttu-id="daa14-207">Indica o modo usado para conexão à réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-207">Indicates the mode that is used to connect to the primary replica.</span></span>  <span data-ttu-id="daa14-208">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-208">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-209">**Modo de Conexão Secundário**</span><span class="sxs-lookup"><span data-stu-id="daa14-209">**Secondary Connection Mode**</span></span>  
 <span data-ttu-id="daa14-210">Indica o modo usado para conexão à réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-210">Indicates the mode that is used to connect to the secondary replica.</span></span>  <span data-ttu-id="daa14-211">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-211">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-212">**Estado da Conexão**</span><span class="sxs-lookup"><span data-stu-id="daa14-212">**Connection State**</span></span>  
 <span data-ttu-id="daa14-213">Indica se uma réplica secundária está conectada atualmente à réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-213">Indicates whether a secondary replica is currently connected to the primary replica.</span></span> <span data-ttu-id="daa14-214">Essa coluna é ocultada por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-214">This column is hidden by default.</span></span> <span data-ttu-id="daa14-215">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="daa14-215">The possible values are:</span></span>  
  
-   <span data-ttu-id="daa14-216">**Desconectado**.</span><span class="sxs-lookup"><span data-stu-id="daa14-216">**Disconnected**.</span></span> <span data-ttu-id="daa14-217">Para uma réplica de disponibilidade remota, indica que ela está desconectada da réplica de disponibilidade local.</span><span class="sxs-lookup"><span data-stu-id="daa14-217">For a remote availability replica, indicates that it is disconnected from the local availability replica.</span></span> <span data-ttu-id="daa14-218">A resposta da réplica local ao estado Desconectado depende de sua função, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="daa14-218">The response of the local replica to the Disconnected state depends on its role, as follows:</span></span>  
  
    -   <span data-ttu-id="daa14-219">na réplica primária, se uma réplica secundária estiver desconectada, os bancos de dados secundários serão marcados como **Não Sincronizado** na réplica primária, e a réplica primária esperará que a secundária seja reconectada.</span><span class="sxs-lookup"><span data-stu-id="daa14-219">On the primary replica, if a secondary replica is disconnected, the secondary databases are marked as **Not Synchronized** on the primary replica, and the primary replica waits for the secondary to reconnect.</span></span>  
  
    -   <span data-ttu-id="daa14-220">Na réplica secundária, ao detectar que está desconectada, a réplica secundária tentará reconectar-se à réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-220">On the secondary replica, upon detecting that it is disconnected, the secondary replica attempts to reconnect to the primary replica.</span></span>  
  
-   <span data-ttu-id="daa14-221">**Conectado**.</span><span class="sxs-lookup"><span data-stu-id="daa14-221">**Connected**.</span></span> <span data-ttu-id="daa14-222">Uma réplica de disponibilidade remota que está conectada atualmente à réplica local.</span><span class="sxs-lookup"><span data-stu-id="daa14-222">A remote availability replica that is currently connected to the local replica.</span></span>  
  
 <span data-ttu-id="daa14-223">**Estado Operacional**</span><span class="sxs-lookup"><span data-stu-id="daa14-223">**Operational State**</span></span>  
 <span data-ttu-id="daa14-224">Indica o estado operacional atual da réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-224">Indicates the current operational state of the secondary replica.</span></span> <span data-ttu-id="daa14-225">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-225">This value is hidden by default.</span></span> <span data-ttu-id="daa14-226">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="daa14-226">The possible values are:</span></span>  
  
 <span data-ttu-id="daa14-227">**0**. Failover pendente</span><span class="sxs-lookup"><span data-stu-id="daa14-227">**0**. Pending failover</span></span>  
  
 <span data-ttu-id="daa14-228">**1**. Pendente</span><span class="sxs-lookup"><span data-stu-id="daa14-228">**1**. Pending</span></span>  
  
 <span data-ttu-id="daa14-229">**2**. Online</span><span class="sxs-lookup"><span data-stu-id="daa14-229">**2**. Online</span></span>  
  
 <span data-ttu-id="daa14-230">**3**. Offline</span><span class="sxs-lookup"><span data-stu-id="daa14-230">**3**. Offline</span></span>  
  
 <span data-ttu-id="daa14-231">**4**. Falhou</span><span class="sxs-lookup"><span data-stu-id="daa14-231">**4**. Failed</span></span>  
  
 <span data-ttu-id="daa14-232">**5**. Com falha, sem quorum</span><span class="sxs-lookup"><span data-stu-id="daa14-232">**5**. Failed, no quorum</span></span>  
  
 <span data-ttu-id="daa14-233">**NULL**.</span><span class="sxs-lookup"><span data-stu-id="daa14-233">**NULL**.</span></span> <span data-ttu-id="daa14-234">A réplica não é local</span><span class="sxs-lookup"><span data-stu-id="daa14-234">Replica is not local</span></span>  
  
 <span data-ttu-id="daa14-235">**Número do Último Erro de Conexão.**</span><span class="sxs-lookup"><span data-stu-id="daa14-235">**Last Connection Error No.**</span></span>  
 <span data-ttu-id="daa14-236">O número do último erro de conexão.</span><span class="sxs-lookup"><span data-stu-id="daa14-236">Number of the last connection error.</span></span>  <span data-ttu-id="daa14-237">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-237">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-238">**Descrição do Último Erro de Conexão**</span><span class="sxs-lookup"><span data-stu-id="daa14-238">**Last Connection Error Description**</span></span>  
 <span data-ttu-id="daa14-239">A descrição do último erro de conexão.</span><span class="sxs-lookup"><span data-stu-id="daa14-239">Description of the last connection error.</span></span>  <span data-ttu-id="daa14-240">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-240">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-241">**Carimbo de Data/Hora do Último Erro de Conexão**</span><span class="sxs-lookup"><span data-stu-id="daa14-241">**Last Connection Error Timestamp**</span></span>  
 <span data-ttu-id="daa14-242">O carimbo de data/hora do último erro de conexão.</span><span class="sxs-lookup"><span data-stu-id="daa14-242">Timestamp of the last connection error.</span></span> <span data-ttu-id="daa14-243">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-243">This value is hidden by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="daa14-244">Para obter informações sobre contadores de desempenho para réplicas de disponibilidade, veja [SQL Server, Réplica de Disponibilidade](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="daa14-244">For information about performance counters for availability replicas, see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
##  <a name="to-group-availability-group-information"></a><a name="AvDbDetails"></a> <span data-ttu-id="daa14-245">Para agrupar informações do grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="daa14-245">To Group Availability Group Information</span></span>  
 <span data-ttu-id="daa14-246">Para agrupar as informações, clique em **Agrupar por**e selecione uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="daa14-246">To group the information, click **Group by**, and select one of the following:</span></span>  
  
-   <span data-ttu-id="daa14-247">**Réplicas de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="daa14-247">**Availability replicas**</span></span>  
  
-   <span data-ttu-id="daa14-248">**Bancos de dados de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="daa14-248">**Availability databases**</span></span>  
  
-   <span data-ttu-id="daa14-249">**Estado de sincronização**</span><span class="sxs-lookup"><span data-stu-id="daa14-249">**Synchronization state**</span></span>  
  
-   <span data-ttu-id="daa14-250">**Prontidão de failover**</span><span class="sxs-lookup"><span data-stu-id="daa14-250">**Failover readiness**</span></span>  
  
-   <span data-ttu-id="daa14-251">**Problemas**</span><span class="sxs-lookup"><span data-stu-id="daa14-251">**Issues**</span></span>  
  
 <span data-ttu-id="daa14-252">O painel que exibe as informações agrupadas exibe as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="daa14-252">The pane that displays the grouped information displays the following columns:</span></span>  
  
 <span data-ttu-id="daa14-253">**Nome**</span><span class="sxs-lookup"><span data-stu-id="daa14-253">**Name**</span></span>  
 <span data-ttu-id="daa14-254">O nome do banco de dados de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-254">The name of the availability database.</span></span> <span data-ttu-id="daa14-255">Esse valor é mostrado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-255">This value is shown by default.</span></span>  
  
 <span data-ttu-id="daa14-256">**Réplica**</span><span class="sxs-lookup"><span data-stu-id="daa14-256">**Replica**</span></span>  
 <span data-ttu-id="daa14-257">O nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda a réplica de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="daa14-257">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span> <span data-ttu-id="daa14-258">Esse valor é mostrado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-258">This value is shown by default.</span></span>  
  
 <span data-ttu-id="daa14-259">**Estado da Sincronização**</span><span class="sxs-lookup"><span data-stu-id="daa14-259">**Synchronization State**</span></span>  
 <span data-ttu-id="daa14-260">Indica se um banco de dados de disponibilidade está sincronizado no momento com a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-260">Indicates whether the availability database is currently synchronized with primary replica.</span></span> <span data-ttu-id="daa14-261">Esse valor é mostrado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-261">This value is shown by default.</span></span> <span data-ttu-id="daa14-262">Os possíveis estados de sincronização são:</span><span class="sxs-lookup"><span data-stu-id="daa14-262">The possible synchronization states are:</span></span>  
  
-   <span data-ttu-id="daa14-263">**Não sincronizando**.</span><span class="sxs-lookup"><span data-stu-id="daa14-263">**Not synchronizing**.</span></span>  
  
    -   <span data-ttu-id="daa14-264">Para uma função primária, indica que o banco de dados não está pronto para sincronizar seu log de transações com os bancos de dados secundários correspondentes.</span><span class="sxs-lookup"><span data-stu-id="daa14-264">For the primary role, indicates that the database is not ready to synchronize its transaction log with the corresponding secondary databases.</span></span>  
  
    -   <span data-ttu-id="daa14-265">Para um banco de dados secundário, indica que o banco de dados não iniciou a sincronização de log devido a um problema de conexão, está sendo suspenso ou está passando por estados de transição durante a inicialização ou uma troca de função.</span><span class="sxs-lookup"><span data-stu-id="daa14-265">For a secondary database, indicates that the database has not started log synchronization because of a connection issue, is being suspended, or is going through transition states during startup or a role switch.</span></span>  
  
-   <span data-ttu-id="daa14-266">**Sincronizando**.</span><span class="sxs-lookup"><span data-stu-id="daa14-266">**Synchronizing**.</span></span>  
  
     <span data-ttu-id="daa14-267">Em uma réplica primária:</span><span class="sxs-lookup"><span data-stu-id="daa14-267">On a primary replica:</span></span>  
  
    -   <span data-ttu-id="daa14-268">Para um banco de dados primário, indica que este banco de dados está pronto para aceitar uma solicitação de exame de um banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="daa14-268">For a primary database, indicates that this database is ready to accept a scan request from a secondary database.</span></span>  
  
    -   <span data-ttu-id="daa14-269">Em uma réplica secundária, indica que há movimentação de dados ativa em andamento para este banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="daa14-269">On a secondary replica, indicates that there is active data movement going on for that secondary database.</span></span>  
  
     <span data-ttu-id="daa14-270">Em uma réplica secundária, indica que há movimentação de dados ativa em andamento para esta réplica.</span><span class="sxs-lookup"><span data-stu-id="daa14-270">On a secondary replica, indicates that there is active data movement going on for that replica.</span></span>  
  
-   <span data-ttu-id="daa14-271">**Sincronizado**.</span><span class="sxs-lookup"><span data-stu-id="daa14-271">**Synchronized**.</span></span>  
  
     <span data-ttu-id="daa14-272">Para um banco de dados primário, indica se pelo menos um banco de dados secundário é sincronizado.</span><span class="sxs-lookup"><span data-stu-id="daa14-272">For a primary database, indicates that at least one secondary database is synchronized.</span></span>  
  
     <span data-ttu-id="daa14-273">Para um banco de dados secundário, indica se o banco de dados está sincronizado com o banco de dados primário correspondente.</span><span class="sxs-lookup"><span data-stu-id="daa14-273">For a secondary database, indicates that the database is synchronized with the corresponding primary database.</span></span>  
  
-   <span data-ttu-id="daa14-274">**Revertendo**.</span><span class="sxs-lookup"><span data-stu-id="daa14-274">**Reverting**.</span></span>  
  
     <span data-ttu-id="daa14-275">Indica a fase do processo de desfazer em que um banco de dados secundário está obtendo páginas ativamente do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="daa14-275">Indicates the phase in the undo process when a secondary database is actively getting pages from the primary database.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="daa14-276">Quando um banco de dados está no estado REVERTING, um failover forçado da réplica secundária pode deixar o banco de dados em um estado no qual não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="daa14-276">When a database is in the REVERTING state, forcing failover to the secondary replica can leave that database in a state in which it cannot be started.</span></span>  
  
-   <span data-ttu-id="daa14-277">**Inicializando**.</span><span class="sxs-lookup"><span data-stu-id="daa14-277">**Initializing**.</span></span>  
  
     <span data-ttu-id="daa14-278">Indica a fase de desfazer em que o log de transações que exigiu que um banco de dados secundário ficasse em dia com o LSN de desfazer está sendo enviado e protegido em uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-278">Indicates the phase of undo when the transaction log required for a secondary database to catch up to the undo LSN is being shipped and hardened on a secondary replica.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="daa14-279">Quando um banco de dados está no estado INITIALIZING, um failover forçado da réplica secundária sempre deixará esse banco de dados em um estado no qual não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="daa14-279">When a database is in the INITIALIZING state, forcing failover to the secondary replica will always leave that database in a state in which it cannot be started.</span></span>  
  
 <span data-ttu-id="daa14-280">**Prontidão de Failover**</span><span class="sxs-lookup"><span data-stu-id="daa14-280">**Failover Readiness**</span></span>  
 <span data-ttu-id="daa14-281">Indica em qual réplica de disponibilidade pode ser feito failover com ou sem perda de dados potencial.</span><span class="sxs-lookup"><span data-stu-id="daa14-281">Indicates which availability replica can be failed over with or without potential data loss.</span></span> <span data-ttu-id="daa14-282">Essa coluna é mostrada por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-282">This column is shown by default.</span></span> <span data-ttu-id="daa14-283">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="daa14-283">The possible values are:</span></span>  
  
-   <span data-ttu-id="daa14-284">**Perda de Dados**</span><span class="sxs-lookup"><span data-stu-id="daa14-284">**Data Loss**</span></span>  
  
-   <span data-ttu-id="daa14-285">**Sem Perda de Dados**</span><span class="sxs-lookup"><span data-stu-id="daa14-285">**No Data Loss**</span></span>  
  
 <span data-ttu-id="daa14-286">**Problemas**</span><span class="sxs-lookup"><span data-stu-id="daa14-286">**Issues**</span></span>  
 <span data-ttu-id="daa14-287">Lista o nome do problema.</span><span class="sxs-lookup"><span data-stu-id="daa14-287">Lists the issue name.</span></span> <span data-ttu-id="daa14-288">Essa coluna é mostrada por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-288">This column is shown by default.</span></span> <span data-ttu-id="daa14-289">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="daa14-289">The possible values are:</span></span>  
  
-   <span data-ttu-id="daa14-290">**Avisos**.</span><span class="sxs-lookup"><span data-stu-id="daa14-290">**Warnings**.</span></span> <span data-ttu-id="daa14-291">Clique para exibir os problemas de limites e avisos.</span><span class="sxs-lookup"><span data-stu-id="daa14-291">Click to display the thresholds and warnings issues.</span></span>  
  
-   <span data-ttu-id="daa14-292">**Crítico**.</span><span class="sxs-lookup"><span data-stu-id="daa14-292">**Critical**.</span></span> <span data-ttu-id="daa14-293">Clique para exibir os problemas críticos.</span><span class="sxs-lookup"><span data-stu-id="daa14-293">Click to display the critical issues.</span></span>  
  
 <span data-ttu-id="daa14-294">Para obter uma lista de todos os problemas da política AlwaysOn, consulte [políticas AlwaysOn para problemas operacionais com o grupos de disponibilidade AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="daa14-294">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="daa14-295">**Suspenso**</span><span class="sxs-lookup"><span data-stu-id="daa14-295">**Suspended**</span></span>  
 <span data-ttu-id="daa14-296">Indica se o banco de dados está **Suspenso** ou **Retomado**.</span><span class="sxs-lookup"><span data-stu-id="daa14-296">Indicates whether the database is **Suspended** or has been **Resumed**.</span></span> <span data-ttu-id="daa14-297">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-297">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-298">**Motivo da Suspensão**</span><span class="sxs-lookup"><span data-stu-id="daa14-298">**Suspend Reason**</span></span>  
 <span data-ttu-id="daa14-299">Indica o motivo do estado de suspensão.</span><span class="sxs-lookup"><span data-stu-id="daa14-299">Indicates the reason for the suspended state.</span></span> <span data-ttu-id="daa14-300">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-300">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-301">**Perda de dados estimada (segundos)**</span><span class="sxs-lookup"><span data-stu-id="daa14-301">**Estimate Data Loss (seconds)**</span></span>  
 <span data-ttu-id="daa14-302">Indica a diferença de tempo do último registro de log de transação na réplica primária e na réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-302">Indicates the time difference of the last transaction log record in the primary replica and secondary replica.</span></span> <span data-ttu-id="daa14-303">Se a réplica primária falhar, todos os registros de log de transação dentro da janela de tempo serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="daa14-303">If the primary replica fails, all transaction log records within the time window will be lost.</span></span> <span data-ttu-id="daa14-304">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-304">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-305">**Tempo de Recuperação estimado (segundos)**</span><span class="sxs-lookup"><span data-stu-id="daa14-305">**Estimated Recovery Time (seconds)**</span></span>  
 <span data-ttu-id="daa14-306">Indica o tempo em segundos necessário para refazer o tempo de recuperação do atraso.</span><span class="sxs-lookup"><span data-stu-id="daa14-306">Indicates the time in seconds it takes to redo the catch-up time.</span></span> <span data-ttu-id="daa14-307">O *tempo de recuperação do atraso* é o tempo necessário para a réplica secundária ficar em dia com a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-307">The *catch-up time* is the time it will take for the secondary replica to catch up with the primary replica.</span></span> <span data-ttu-id="daa14-308">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-308">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-309">**Desempenho da Sincronização (segundos)**</span><span class="sxs-lookup"><span data-stu-id="daa14-309">**Synchronization Performance (seconds)**</span></span>  
 <span data-ttu-id="daa14-310">Indica o tempo, em segundos, necessário para a sincronização entre as réplicas primária e a secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-310">Indicates the time in seconds it takes to synchronize between the primary and secondary replicas.</span></span> <span data-ttu-id="daa14-311">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-311">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-312">**Tamanho da Fila de Envio de Log (KB)**</span><span class="sxs-lookup"><span data-stu-id="daa14-312">**Log Send Queue Size (KB)**</span></span>  
 <span data-ttu-id="daa14-313">Indica a quantidade de registros de log nos arquivos de log do banco de dados primário que não foram enviados à réplica de disponibilidade secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-313">Indicates the amount of log records in the log files of the primary database that have not been sent to the secondary replica.</span></span> <span data-ttu-id="daa14-314">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-314">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-315">**Taxa de Envio de log (KB/segundo)**</span><span class="sxs-lookup"><span data-stu-id="daa14-315">**Log Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="daa14-316">Indica a taxa em KB por segundo na qual estão sendo enviados registros de log à réplica secundária. Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-316">Indicates the rate in KB per second at which log records are being sent to the secondary replica This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-317">**Tamanho da Fila de Restauração (KB)**</span><span class="sxs-lookup"><span data-stu-id="daa14-317">**Redo Queue Size (KB)**</span></span>  
 <span data-ttu-id="daa14-318">Indica a quantidade de registros de log nos arquivos de log da réplica secundária que ainda não foram refeitos.</span><span class="sxs-lookup"><span data-stu-id="daa14-318">Indicates the amount of log records in the log files of the secondary replica that have not yet been redone.</span></span> <span data-ttu-id="daa14-319">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-319">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-320">**Taxa de Restauração (KB/segundo)**</span><span class="sxs-lookup"><span data-stu-id="daa14-320">**Redo Rate (KB/sec)**</span></span>  
 <span data-ttu-id="daa14-321">Indica a taxa em KB por segundo na qual os registros de log estão sendo refeitos.</span><span class="sxs-lookup"><span data-stu-id="daa14-321">Indicates the rate in KB per second at which the log records are being redone.</span></span> <span data-ttu-id="daa14-322">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-322">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-323">**Taxa de Envio do Fluxo de Arquivos (KB/s)**</span><span class="sxs-lookup"><span data-stu-id="daa14-323">**FileStream Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="daa14-324">Indica a taxa do Fluxo de Arquivos, em KB por segundo, na qual as transações estão sendo enviadas à réplica.</span><span class="sxs-lookup"><span data-stu-id="daa14-324">Indicates the rate of the FileStream in KB per second at which transactions are being sent to the replica.</span></span> <span data-ttu-id="daa14-325">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-325">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-326">**LSN de Fim de Log**</span><span class="sxs-lookup"><span data-stu-id="daa14-326">**End of Log LSN**</span></span>  
 <span data-ttu-id="daa14-327">Indica o LSN (número de sequência de log) real que corresponde ao último registro de log no cache de log nas réplicas primária e secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-327">Indicates the actual log sequence number (LSN) that corresponds to the last log record in the log cache on the primary and secondary replicas.</span></span> <span data-ttu-id="daa14-328">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-328">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-329">**LSN de Recuperação**</span><span class="sxs-lookup"><span data-stu-id="daa14-329">**Recovery LSN**</span></span>  
 <span data-ttu-id="daa14-330">Indica o final do log de transações antes de a réplica gravar outro novo registro de log depois da recuperação ou do failover na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-330">Indicates the end of the transaction log before the replica writes any new log records after recovery or failover on the primary replica.</span></span> <span data-ttu-id="daa14-331">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-331">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-332">**LSN de Truncamento**</span><span class="sxs-lookup"><span data-stu-id="daa14-332">**Truncation LSN**</span></span>  
 <span data-ttu-id="daa14-333">Indica o valor mínimo de truncamento de log para a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-333">Indicates the minimum log truncation value for the primary replica.</span></span> <span data-ttu-id="daa14-334">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-334">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-335">**LSN da Última Confirmação**</span><span class="sxs-lookup"><span data-stu-id="daa14-335">**Last Commit LSN**</span></span>  
 <span data-ttu-id="daa14-336">Indica a LSN real que corresponde ao último registro de confirmação no log de transações.</span><span class="sxs-lookup"><span data-stu-id="daa14-336">Indicates the actual LSN corresponding to the last commit record in the transaction log.</span></span> <span data-ttu-id="daa14-337">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-337">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-338">**Hora da Última Confirmação**</span><span class="sxs-lookup"><span data-stu-id="daa14-338">**Last Commit Time**</span></span>  
 <span data-ttu-id="daa14-339">Indica a hora correspondente ao último registro de confirmação.</span><span class="sxs-lookup"><span data-stu-id="daa14-339">Indicates the time corresponding to the last commit record.</span></span> <span data-ttu-id="daa14-340">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-340">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-341">**LSN do Último Envio**</span><span class="sxs-lookup"><span data-stu-id="daa14-341">**Last Sent LSN**</span></span>  
 <span data-ttu-id="daa14-342">Indica o ponto até o qual todos os blocos de log foram enviados pela réplica primária.</span><span class="sxs-lookup"><span data-stu-id="daa14-342">Indicates the point up to which all log blocks have been sent by the primary replica.</span></span> <span data-ttu-id="daa14-343">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-343">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-344">**Hora do Último Envio**</span><span class="sxs-lookup"><span data-stu-id="daa14-344">**Last Sent Time**</span></span>  
 <span data-ttu-id="daa14-345">Indica a hora em que o último bloco de log foi enviado.</span><span class="sxs-lookup"><span data-stu-id="daa14-345">Indicates the time when the last log block was sent.</span></span> <span data-ttu-id="daa14-346">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-346">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-347">**LSN do Último Recebimento**</span><span class="sxs-lookup"><span data-stu-id="daa14-347">**Last Received LSN**</span></span>  
 <span data-ttu-id="daa14-348">Indica o ponto até o qual todos os blocos de log foram recebidos pela réplica secundária que hospeda o banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="daa14-348">Indicates the point up to which all log blocks have been received by the secondary replica that hosts the secondary database.</span></span> <span data-ttu-id="daa14-349">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-349">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-350">**Hora do Último Recebimento**</span><span class="sxs-lookup"><span data-stu-id="daa14-350">**Last Received Time**</span></span>  
 <span data-ttu-id="daa14-351">Indica a hora em que o identificador do bloco de log da última mensagem recebida foi lido na réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-351">Indicates the time when the log block identifier in last message received was read on the secondary replica.</span></span> <span data-ttu-id="daa14-352">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-352">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-353">**LSN da Última Proteção**</span><span class="sxs-lookup"><span data-stu-id="daa14-353">**Last Hardened LSN**</span></span>  
 <span data-ttu-id="daa14-354">Indica o ponto até o qual todos os registros de log foram liberados para disco na réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-354">Indicates the point up to which all log records have been flushed to disk on the secondary replica.</span></span> <span data-ttu-id="daa14-355">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-355">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-356">**Hora da Última Proteção**</span><span class="sxs-lookup"><span data-stu-id="daa14-356">**Last Hardened Time**</span></span>  
 <span data-ttu-id="daa14-357">Indica a hora em que o identificador do bloco de log foi recebido para a última LSN de proteção na réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-357">Indicates the time when the log-block identifier was received for the last hardened LSN on the secondary replica.</span></span> <span data-ttu-id="daa14-358">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-358">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-359">**LSN da Última Operação de Refazer**</span><span class="sxs-lookup"><span data-stu-id="daa14-359">**Last Redone LSN**</span></span>  
 <span data-ttu-id="daa14-360">Indica a LSN real do registro de log que foi refeito pela última vez na réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="daa14-360">Indicates the actual LSN of the log record that was redone last on the secondary replica.</span></span> <span data-ttu-id="daa14-361">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-361">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="daa14-362">**Hora da Última Operação de Refazer**</span><span class="sxs-lookup"><span data-stu-id="daa14-362">**Last Redone Time**</span></span>  
 <span data-ttu-id="daa14-363">Indica a hora em que o último registro de log que foi refeito no banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="daa14-363">Indicates the time when the last log record was redone on the secondary database.</span></span> <span data-ttu-id="daa14-364">Esse valor é ocultado por padrão.</span><span class="sxs-lookup"><span data-stu-id="daa14-364">This value is hidden by default.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="daa14-365">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="daa14-365">Related Tasks</span></span>  
  
-   [<span data-ttu-id="daa14-366">Use políticas AlwaysOn para exibir a integridade de um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="daa14-366">Use AlwaysOn Policies to View the Health of an Availability Group &#40;SQL Server&#41;</span></span>](use-always-on-policies-to-view-the-health-of-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="daa14-367">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="daa14-367">See Also</span></span>  
 <span data-ttu-id="daa14-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="daa14-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span></span>  
 [<span data-ttu-id="daa14-369">Monitoramento de grupos de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="daa14-369">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
