---
title: Configurar o roteamento somente leitura para um grupo de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- read-only routing
- Availability Groups [SQL Server], readable secondary replicas
- Availability Groups [SQL Server], read-only routing
- readable secondary replicas
- Availability Groups [SQL Server], client connectivity
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 7bd89ddd-0403-4930-a5eb-3c78718533d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d51d1db75caa29814a01fc1f49bfdd49b403c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576003"
---
# <a name="configure-read-only-routing-for-an-availability-group-sql-server"></a><span data-ttu-id="cbea0-102">Configurar o roteamento somente leitura para um grupo de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cbea0-102">Configure Read-Only Routing for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="cbea0-103">Para configurar um grupo de disponibilidade AlwaysOn para oferecer suporte ao roteamento somente leitura no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], você pode usar o [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbea0-103">To configure an AlwaysOn availability group to support read-only routing in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can use either [!INCLUDE[tsql](../../../includes/tsql-md.md)] or PowerShell.</span></span> <span data-ttu-id="cbea0-104">*Roteamento somente leitura* refere-se à capacidade de o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] rotear solicitações de conexão somente leitura para uma [réplica secundária legível](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) AlwaysOn disponível (ou seja, uma réplica que é configurada para permitir cargas de trabalho somente leitura ao ser executada sob a função secundária).</span><span class="sxs-lookup"><span data-stu-id="cbea0-104">*Read-only routing* refers to the ability of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to route qualifying read-only connection requests to an available AlwaysOn [readable secondary replica](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) (that is, a replica that is configured to allow read-only workloads when running under the secondary role).</span></span> <span data-ttu-id="cbea0-105">Para dar suporte ao roteamento somente leitura, o grupo de disponibilidade deve ter um [ouvinte do grupo de disponibilidade](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-105">To support read-only routing, the availability group must possess an [availability group listener](../../listeners-client-connectivity-application-failover.md).</span></span> <span data-ttu-id="cbea0-106">Clientes somente leitura devem direcionar suas solicitações de conexão para este ouvinte e as cadeias de conexão do cliente devem especificar a intenção do aplicativo como "somente leitura."</span><span class="sxs-lookup"><span data-stu-id="cbea0-106">Read-only clients must direct their connection requests to this listener, and the client's connection strings must specify the application intent as "read-only."</span></span> <span data-ttu-id="cbea0-107">Ou seja, elas devem ser *solicitações de conexão de intenção de leitura*.</span><span class="sxs-lookup"><span data-stu-id="cbea0-107">That is, they must be *read-intent connection requests*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbea0-108">Para obter informações sobre como configurar uma réplica secundária legível, veja [Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-108">For information about how to configure a readable secondary replica, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="cbea0-109">A configuração do roteamento somente leitura não tem suporte do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbea0-109">Configuring read-only routing is not supported by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cbea0-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cbea0-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="cbea0-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cbea0-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="cbea0-112">O grupo de disponibilidade deve possuir um ouvinte de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="cbea0-112">The availability group must possess an availability group listener.</span></span> <span data-ttu-id="cbea0-113">Para obter mais informações, consulte [Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-113">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   <span data-ttu-id="cbea0-114">Uma ou mais réplicas de disponibilidade devem ser configuradas para aceitar somente leitura na função secundária (ou seja, para serem [réplicas secundárias legíveis](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn% 20Availability% 20Groups \) . MD)).</span><span class="sxs-lookup"><span data-stu-id="cbea0-114">One or more availability replicas must be configured to accept read-only in the secondary role (that is, to be [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn%20Availability%20Groups\).md)).</span></span> <span data-ttu-id="cbea0-115">Para obter mais informações, consulte [Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-115">For more information, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>  
  
-   <span data-ttu-id="cbea0-116">Você deve estar conectado à instância do servidor que hospeda a réplica primária atual.</span><span class="sxs-lookup"><span data-stu-id="cbea0-116">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
###  <a name="what-replica-properties-do-you-need-to-configure-to-support-read-only-routing"></a><a name="RORReplicaProperties"></a> <span data-ttu-id="cbea0-117">Quais as propriedades de réplica você precisa configurar para dar suporte a roteamento somente leitura?</span><span class="sxs-lookup"><span data-stu-id="cbea0-117">What Replica Properties Do you Need to Configure to Support Read-Only Routing?</span></span>  
  
-   <span data-ttu-id="cbea0-118">Para cada réplica secundária legível que deve dar suporte a roteamento somente leitura, você precisa especificar uma *URL de roteamento somente leitura*.</span><span class="sxs-lookup"><span data-stu-id="cbea0-118">For each readable secondary replica that is to support read-only routing, you need to specify a *read-only routing URL*.</span></span> <span data-ttu-id="cbea0-119">Esta URL só entra em vigor quando a réplica local estiver sendo executada sob a função secundária.</span><span class="sxs-lookup"><span data-stu-id="cbea0-119">This URL takes effect only when the local replica is running under the secondary role.</span></span> <span data-ttu-id="cbea0-120">A URL do roteamento somente leitura deve ser especificada réplica por réplica, quando necessário.</span><span class="sxs-lookup"><span data-stu-id="cbea0-120">The read-only routing URL must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="cbea0-121">Cada URL de roteamento somente leitura é usada para solicitações de conexão de intenção de leitura para uma réplica secundária legível específica.</span><span class="sxs-lookup"><span data-stu-id="cbea0-121">Each read-only routing URL is used for routing read-intent connection requests to a specific readable secondary replica.</span></span> <span data-ttu-id="cbea0-122">Normalmente, toda réplica secundária legível é atribuída uma URL de roteamento somente leitura.</span><span class="sxs-lookup"><span data-stu-id="cbea0-122">Typically, every readable secondary replica is assigned a read-only routing URL.</span></span>  
  
     <span data-ttu-id="cbea0-123">Para obter informações sobre como calcular a URL de roteamento somente leitura de uma réplica de disponibilidade, consulte [Calculando read_only_routing_url de AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="cbea0-123">For information about calculating the read-only routing URL for an availability replica, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
-   <span data-ttu-id="cbea0-124">Para cada réplica de disponibilidade que você quer dar suporte a roteamento somente leitura quando é a réplica primária, você precisará especificar uma *lista de roteamento somente leitura*.</span><span class="sxs-lookup"><span data-stu-id="cbea0-124">For each availability replica that you want to support read-only routing when it is the primary replica, you need to specify a *read-only routing list*.</span></span> <span data-ttu-id="cbea0-125">Uma determinada lista de roteamento somente leitura só entra em vigor quando a réplica local estiver sendo executada em uma função primária.</span><span class="sxs-lookup"><span data-stu-id="cbea0-125">A given read-only routing list takes effect only when the local replica is running under the primary role.</span></span> <span data-ttu-id="cbea0-126">Essa lista deve ser especificada réplica por réplica, quando necessário.</span><span class="sxs-lookup"><span data-stu-id="cbea0-126">This list must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="cbea0-127">Normalmente, cada lista de roteamento somente leitura deveria conter todas as URLs de roteamento somente leitura, com a URL da réplica local no final da lista.</span><span class="sxs-lookup"><span data-stu-id="cbea0-127">Typically, each read-only routing list would contain every read-only routing URL, with the URL of the local replica at the end of the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbea0-128">As solicitações e conexão de intenção de leitura são roteadas para a primeira réplica secundária legível disponível na lista de roteamento somente leitura da réplica primária atual.</span><span class="sxs-lookup"><span data-stu-id="cbea0-128">Read-intent connection requests are routed to the first available readable secondary on the read-only routing list of the current primary replica.</span></span> <span data-ttu-id="cbea0-129">Não há nenhum balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="cbea0-129">There is no load balancing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbea0-130">Para obter informações sobre ouvintes do grupo de disponibilidade e mais informações sobre roteamento somente leitura, veja [Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-130">For information about availability group listeners and more information about read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cbea0-131">Segurança</span><span class="sxs-lookup"><span data-stu-id="cbea0-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cbea0-132">Permissões</span><span class="sxs-lookup"><span data-stu-id="cbea0-132">Permissions</span></span>  
  
|<span data-ttu-id="cbea0-133">Tarefa</span><span class="sxs-lookup"><span data-stu-id="cbea0-133">Task</span></span>|<span data-ttu-id="cbea0-134">Permissões</span><span class="sxs-lookup"><span data-stu-id="cbea0-134">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="cbea0-135">Para configurar réplicas ao criar um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="cbea0-135">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="cbea0-136">Requer a associação na função de servidor fixa **sysadmin** e a permissão de servidor CREATE AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="cbea0-136">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="cbea0-137">Para modificar uma réplica de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="cbea0-137">To modify an availability replica</span></span>|<span data-ttu-id="cbea0-138">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="cbea0-138">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cbea0-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cbea0-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="cbea0-140">**Para configurar o roteamento somente leitura**</span><span class="sxs-lookup"><span data-stu-id="cbea0-140">**To Configure read-only routing**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbea0-141">Para obter um exemplo de código, veja [Exemplo (Transact-SQL)](#TsqlExample), mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="cbea0-141">For a code example, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="cbea0-142">Conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="cbea0-142">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="cbea0-143">Se você estiver especificando uma réplica para um novo grupo de disponibilidade, use a instrução [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbea0-143">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="cbea0-144">Se você estiver adicionando ou modificando uma réplica para um grupo de disponibilidade existente, use a instrução [ALTER Availability Group](/sql/t-sql/statements/alter-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbea0-144">If you are adding or modifying a replica for an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="cbea0-145">Para configurar o roteamento somente leitura para a função secundária, na cláusula ADD REPLICA ou MODIFY REPLICA WITH, especifique a opção SECONDARY_ROLE, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="cbea0-145">To configure read-only routing for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="cbea0-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **= '** TCP **:// *`system-address`* : *`port`* ')**</span><span class="sxs-lookup"><span data-stu-id="cbea0-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **='** TCP **://*`system-address`*:*`port`*')**</span></span>  
  
         <span data-ttu-id="cbea0-147">Os parâmetros da URL de roteamento somente leitura são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="cbea0-147">The parameters of the read-only routing URL are as follows:</span></span>  
  
         <span data-ttu-id="cbea0-148">*system-address*</span><span class="sxs-lookup"><span data-stu-id="cbea0-148">*system-address*</span></span>  
         <span data-ttu-id="cbea0-149">É uma cadeia de caracteres, como um nome de sistema, um nome de domínio totalmente qualificado ou um endereço IP, que identifica de forma exclusiva o sistema do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="cbea0-149">Is a string, such as a system name, a fully qualified domain name, or an IP address, that unambiguously identifies the destination computer system.</span></span>  
  
         <span data-ttu-id="cbea0-150">*port*</span><span class="sxs-lookup"><span data-stu-id="cbea0-150">*port*</span></span>  
         <span data-ttu-id="cbea0-151">É um número de porta que é usado pelo mecanismo de banco de dados da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbea0-151">Is a port number that is used by the Database Engine of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="cbea0-152">Por exemplo:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span><span class="sxs-lookup"><span data-stu-id="cbea0-152">For example:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span></span>  
  
         <span data-ttu-id="cbea0-153">Em uma cláusula MODIFY REPLICA, o ALLOW_CONNECTIONS será opcional se a réplica já estiver configurada para permitir conexões somente leitura.</span><span class="sxs-lookup"><span data-stu-id="cbea0-153">In a MODIFY REPLICA clause the ALLOW_CONNECTIONS is optional if the replica is already configured to allow read-only connections.</span></span>  
  
         <span data-ttu-id="cbea0-154">Para obter mais informações, consulte [Calculando read_only_routing_url de AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="cbea0-154">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="cbea0-155">Para configurar o roteamento somente leitura para a função primária, na cláusula ADD REPLICA ou MODIFY REPLICA WITH, especifique a opção PRIMARY_ROLE, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="cbea0-155">To configure read-only routing for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="cbea0-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **= (' *`server`* '** [ **,**... *n* ] **))**</span><span class="sxs-lookup"><span data-stu-id="cbea0-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **=('*`server`*'** [ **,**...*n* ] **))**</span></span>  
  
         <span data-ttu-id="cbea0-157">em que *server* identifica uma instância de servidor que hospeda uma réplica secundária somente leitura em um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="cbea0-157">where, *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span>  
  
         <span data-ttu-id="cbea0-158">Por exemplo:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span><span class="sxs-lookup"><span data-stu-id="cbea0-158">For example:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="cbea0-159">Você precisa definir a URl de roteamento somente leitura antes de configurar a lista de roteamento somente leitura.</span><span class="sxs-lookup"><span data-stu-id="cbea0-159">You must set the read-only routing URL before configuring the read-only routing list.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="cbea0-160">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cbea0-160">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="cbea0-161">O exemplo a seguir modifica duas réplicas de disponibilidade de um grupo de disponibilidade existente, `AG1` para oferecer suporte ao roteamento somente leitura quando uma dessas réplicas possui a função primária no momento.</span><span class="sxs-lookup"><span data-stu-id="cbea0-161">The following example modifies two availability replicas of an existing availability group, `AG1` to support read-only routing if one of these replicas currently owns the primary role.</span></span> <span data-ttu-id="cbea0-162">Para identificar as instâncias de servidor que hospedam a réplica de disponibilidade, este exemplo especifica os nomes da instância –`COMPUTER01` e `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="cbea0-162">To identify the server instances that host the availability replica, this example specifies the instance names-`COMPUTER01` and `COMPUTER02`.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER02.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER02','COMPUTER01')));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER01','COMPUTER02')));  
GO
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="cbea0-163">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbea0-163">Using PowerShell</span></span>  

### <a name="to-configure-read-only-routing"></a><span data-ttu-id="cbea0-164">Para configurar o roteamento somente leitura</span><span class="sxs-lookup"><span data-stu-id="cbea0-164">To Configure read-only routing</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="cbea0-165">Para obter um exemplo de código, consulte [Exemplo (PowerShell)](#PSExample), posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="cbea0-165">For a code example, see [Example (PowerShell)](#PSExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="cbea0-166">Defina o padrão (`cd`) para a instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="cbea0-166">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="cbea0-167">Ao adicionar uma réplica de disponibilidade a um grupo de disponibilidade, use o cmdlet `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="cbea0-167">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="cbea0-168">Ao modificar uma réplica de disponibilidade existente, use o cmdlet `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="cbea0-168">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="cbea0-169">Os parâmetros relevantes são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="cbea0-169">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="cbea0-170">Para configurar o roteamento somente leitura para a função secundária, especifique o parâmetro **parâmetro readonlyroutingconnectionurl " *`url`* "** .</span><span class="sxs-lookup"><span data-stu-id="cbea0-170">To configure read-only routing for the secondary role, specify the **ReadonlyRoutingConnectionUrl"*`url`*"** parameter.</span></span>  
  
         <span data-ttu-id="cbea0-171">em que *url* é o FQDN (nome de domínio totalmente qualificado de conectividade) e a porta a ser usada no roteamento para a réplica em conexões somente leitura.</span><span class="sxs-lookup"><span data-stu-id="cbea0-171">where, *url* is the connectivity fully-qualified domain name (FQDN) and port to use when routing to the replica for read-only connections.</span></span> <span data-ttu-id="cbea0-172">Por exemplo: `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span><span class="sxs-lookup"><span data-stu-id="cbea0-172">For example:  `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span></span>  
  
         <span data-ttu-id="cbea0-173">Para obter mais informações, consulte [Calculando read_only_routing_url de AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="cbea0-173">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="cbea0-174">Para configurar o acesso de conexão para a função primária, especifique **ReadonlyRoutingList " *`server`* "** [ **,**... *n* ], em que *Server* identifica uma instância de servidor que hospeda uma réplica secundária somente leitura no grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="cbea0-174">To configure connection access for the primary role, specify **ReadonlyRoutingList"*`server`*"** [ **,**...*n* ], where *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span> <span data-ttu-id="cbea0-175">Por exemplo: `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span><span class="sxs-lookup"><span data-stu-id="cbea0-175">For example:  `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="cbea0-176">Você precisa definir a URl de roteamento somente leitura de uma réplica antes de configurar sua lista de roteamento somente leitura.</span><span class="sxs-lookup"><span data-stu-id="cbea0-176">You must set the read-only routing URL of a replica before configuring its read-only routing list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbea0-177">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbea0-177">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="cbea0-178">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-178">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="cbea0-179">Para configurar e usar o provedor de SQL Server PowerShell, consulte [provedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md) e [obter ajuda SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-179">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) and [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>
  
###  <a name="example-powershell"></a><a name="PSExample"></a> <span data-ttu-id="cbea0-180">Exemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cbea0-180">Example (PowerShell)</span></span>  
 <span data-ttu-id="cbea0-181">O exemplo a seguir configura a réplica primária e uma réplica secundária em um grupo de disponibilidade para o roteamento somente leitura.</span><span class="sxs-lookup"><span data-stu-id="cbea0-181">The following example configures the primary replica and one secondary replica in an availability group for read-only routing.</span></span> <span data-ttu-id="cbea0-182">Primeiro, o exemplo atribui uma URL de roteamento somente leitura a cada réplica.</span><span class="sxs-lookup"><span data-stu-id="cbea0-182">First, the example assigns a read-only routing URL to each replica.</span></span> <span data-ttu-id="cbea0-183">Em seguida, ele define a lista de roteamento somente leitura na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="cbea0-183">Then it sets the read-only routing list on the primary replica.</span></span> <span data-ttu-id="cbea0-184">As conexões com o conjunto de propriedades "ReadOnly" na cadeia de conexão serão redirecionados à réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="cbea0-184">Connections with the "ReadOnly" property set in the connection string will be redirected to the secondary replica.</span></span> <span data-ttu-id="cbea0-185">Se a réplica secundária não estiver legível (conforme determinado pela configuração `ConnectionModeInSecondaryRole`), a conexão será direcionada de volta para a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="cbea0-185">If this secondary replica is not readable (as determined by the `ConnectionModeInSecondaryRole` setting), the connection will be directed back to the primary replica.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  
$secondaryReplica = Get-Item "AvailabilityReplicas\SecondaryServer"  
  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://PrimaryServer.domain.com:1433" -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://SecondaryServer.domain.com:1433" -InputObject $secondaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingList "SecondaryServer","PrimaryServer" -InputObject $primaryReplica  
```  
  
##  <a name="follow-up-after-configuring-read-only-routing"></a><a name="FollowUp"></a> <span data-ttu-id="cbea0-186">Acompanhamento: Depois de configurar o roteamento somente leitura</span><span class="sxs-lookup"><span data-stu-id="cbea0-186">Follow Up: After Configuring Read-Only Routing</span></span>  
 <span data-ttu-id="cbea0-187">Quando a réplica primária atual e as réplicas secundárias legíveis são configuradas para oferecer suporte ao roteamento somente leitura em ambas as funções, as réplicas secundárias legíveis podem receber solicitações de conexão com intenção de leitura de clientes que se conectam pelo ouvinte de grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="cbea0-187">Once the current primary replica and the readable secondary replicas are configured to support read-only routing in both roles, the readable secondary replicas can receive read read-intent connection requests from clients that connect via the availability group listener.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="cbea0-188">Ao usar o [utilitário bcp](../../../tools/bcp-utility.md) ou o [utilitário sqlcmd](../../../tools/sqlcmd-utility.md), você pode especificar o acesso somente leitura a qualquer réplica secundária que esteja habilitada para acesso somente leitura, especificando a `-K ReadOnly` opção.</span><span class="sxs-lookup"><span data-stu-id="cbea0-188">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
###  <a name="requirements-and-recommendations-for-client-connection-strings"></a><a name="ConnStringReqsRecs"></a> <span data-ttu-id="cbea0-189">Requisitos e recomendações para cadeias de conexão de cliente</span><span class="sxs-lookup"><span data-stu-id="cbea0-189">Requirements and Recommendations for Client Connection-Strings</span></span>  
 <span data-ttu-id="cbea0-190">Para que um aplicativo cliente use o roteamento somente leitura, sua cadeia de conexão deve atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="cbea0-190">For a client application to use read-only routing, its connection string must satisfy the following requirements:</span></span>  
  
-   <span data-ttu-id="cbea0-191">Usar o protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="cbea0-191">Use the TCP protocol.</span></span>  
  
-   <span data-ttu-id="cbea0-192">Definir o atributo/propriedade de intenção do aplicativo como readonly.</span><span class="sxs-lookup"><span data-stu-id="cbea0-192">Set the application intent attribute/property to readonly.</span></span>  
  
-   <span data-ttu-id="cbea0-193">Referenciar o ouvinte de um grupo de disponibilidade que está configurado para oferecer suporte ao roteamento somente leitura.</span><span class="sxs-lookup"><span data-stu-id="cbea0-193">Reference the listener of an availability group that is configured to support read-only routing.</span></span>  
  
-   <span data-ttu-id="cbea0-194">Referenciar um banco de dados nesse grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="cbea0-194">Reference a database in that availability group.</span></span>  
  
 <span data-ttu-id="cbea0-195">Além disso, é recomendável que cadeias de conexão habilitem o failover de várias sub-redes, oferecendo suporte a um thread de cliente paralelo para cada réplica em cada sub-rede.</span><span class="sxs-lookup"><span data-stu-id="cbea0-195">In addition, we recommend that connection strings enable multi-subnet failover, which supports a parallel client thread for each replica on each subnet.</span></span> <span data-ttu-id="cbea0-196">Isso minimiza o tempo de reconexão do cliente após um failover.</span><span class="sxs-lookup"><span data-stu-id="cbea0-196">This minimizes client reconnection time after a failover.</span></span>  
  
 <span data-ttu-id="cbea0-197">A sintaxe de uma cadeia de conexão depende do provedor SQL Server que um aplicativo está usando.</span><span class="sxs-lookup"><span data-stu-id="cbea0-197">The syntax for a connection string depends on the SQL Server provider an application is using.</span></span> <span data-ttu-id="cbea0-198">A cadeia de conexão de exemplo a seguir para o provedor de dados .NET Framework 4.0.2 para SQL Server ilustra as partes de uma cadeia de conexão que são necessárias e recomendadas no roteamento somente leitura.</span><span class="sxs-lookup"><span data-stu-id="cbea0-198">The following example connection string for the .NET Framework Data Provider 4.0.2 for SQL Server illustrates the parts of a connection string that are required and recommended to work for read-only routing.</span></span>  
  
```  
Server=tcp:MyAgListener,1433;Database=Db1;IntegratedSecurity=SSPI;ApplicationIntent=ReadOnly;MultiSubnetFailover=True  
```  
  
 <span data-ttu-id="cbea0-199">Para obter mais informações sobre a intenção do aplicativo somente leitura e o roteamento somente leitura, veja [Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-199">For more information about read-only application intent and read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
### <a name="if-read-only-routing-is-not-working-correctly"></a><span data-ttu-id="cbea0-200">Se o roteamento somente leitura não estiver funcionando corretamente</span><span class="sxs-lookup"><span data-stu-id="cbea0-200">If Read-Only Routing is Not Working Correctly</span></span>  
 <span data-ttu-id="cbea0-201">Para obter informações sobre como solucionar problemas de uma configuração de roteamento somente leitura, veja [O roteamento somente leitura não está funcionando corretamente](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cbea0-201">For information about troubleshooting a read-only routing configuration, see [Read-Only Routing is Not Working Correctly](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cbea0-202">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="cbea0-202">Related Tasks</span></span>  

### <a name="to-view-read-only-routing-configurations"></a><span data-ttu-id="cbea0-203">Para exibir configurações do roteamento somente leitura</span><span class="sxs-lookup"><span data-stu-id="cbea0-203">To view read-only routing configurations</span></span>
  
-   [<span data-ttu-id="cbea0-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cbea0-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
  
-   <span data-ttu-id="cbea0-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (coluna **read_only_routing_url**)</span><span class="sxs-lookup"><span data-stu-id="cbea0-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (**read_only_routing_url** column)</span></span>  
  
### <a name="to-configure-client-connection-access"></a><span data-ttu-id="cbea0-206">Para configurar o acesso de conexão de cliente</span><span class="sxs-lookup"><span data-stu-id="cbea0-206">To configure client connection access</span></span>
  
-   [<span data-ttu-id="cbea0-207">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cbea0-207">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="cbea0-208">Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cbea0-208">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
### <a name="to-use-connection-strings-in-applications"></a><span data-ttu-id="cbea0-209">Para usar cadeias de conexão em aplicativos</span><span class="sxs-lookup"><span data-stu-id="cbea0-209">To use connection strings in applications</span></span>
  
-   [<span data-ttu-id="cbea0-210">Suporte do SQL Server Native Client à alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="cbea0-210">SQL Server Native Client Support for High Availability, Disaster Recovery</span></span>](../../../relational-databases/native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md)  
  
-   [<span data-ttu-id="cbea0-211">Usando palavras-chave da cadeia de conexão com o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="cbea0-211">Using Connection String Keywords with SQL Server Native Client</span></span>](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="cbea0-212">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="cbea0-212">Related Content</span></span>  
  
-   <span data-ttu-id="cbea0-213">**Blogs:**</span><span class="sxs-lookup"><span data-stu-id="cbea0-213">**Blogs:**</span></span>  
  
     [<span data-ttu-id="cbea0-214">Calculando read_only_routing_url de AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="cbea0-214">Calculating read_only_routing_url for AlwaysOn</span></span>](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson)  
  
     [<span data-ttu-id="cbea0-215">Blogs da equipe do SQL Server AlwaysOn: o blog oficial da equipe do SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="cbea0-215">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="cbea0-216">Blogs dos engenheiros do CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="cbea0-216">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="cbea0-217">**White papers:**</span><span class="sxs-lookup"><span data-stu-id="cbea0-217">**White papers:**</span></span>  
  
     [<span data-ttu-id="cbea0-218">White papers da Microsoft para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="cbea0-218">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="cbea0-219">White papers da equipe de consultoria do cliente do SQL Server</span><span class="sxs-lookup"><span data-stu-id="cbea0-219">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="cbea0-220">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cbea0-220">See Also</span></span>  
 <span data-ttu-id="cbea0-221">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cbea0-221">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="cbea0-222">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cbea0-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="cbea0-223">[Secundárias ativas: réplicas secundárias legíveis (Grupos de Disponibilidade AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="cbea0-223">[Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 <span data-ttu-id="cbea0-224">[Sobre o acesso de conexão de cliente a réplicas de disponibilidade &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cbea0-224">[About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span></span>  
 [<span data-ttu-id="cbea0-225">Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cbea0-225">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
