---
title: Service Broker com Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 881c20e5-1c99-44eb-b393-09fc5ea0f122
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da179219363422c4ec242d29be61f35dd1609823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574288"
---
# <a name="service-broker-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="fd34c-102">Service Broker com grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fd34c-102">Service Broker with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="fd34c-103">Este tópico contém informações sobre como configurar o Service Broker para funcionar com o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd34c-103">This topic contains information about configuring Service Broker to work with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="fd34c-104">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="fd34c-104">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="fd34c-105">Requisitos de um serviço em um grupo de disponibilidade para receber mensagens remotas</span><span class="sxs-lookup"><span data-stu-id="fd34c-105">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>](#ReceiveRemoteMessages)  
  
-   [<span data-ttu-id="fd34c-106">Requisitos para enviar mensagens para um serviço remoto em um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="fd34c-106">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>](#SendRemoteMessages)  
  
##  <a name="requirements-for-a-service-in-an-availability-group-to-receive-remote-messages"></a><a name="ReceiveRemoteMessages"></a> <span data-ttu-id="fd34c-107">Requisitos para um serviço em um grupo de disponibilidade para receber mensagens remotas</span><span class="sxs-lookup"><span data-stu-id="fd34c-107">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>  
  
1.  <span data-ttu-id="fd34c-108">**Verifique se o grupo de disponibilidade tem um ouvinte.**</span><span class="sxs-lookup"><span data-stu-id="fd34c-108">**Ensure that the availability group possesses a listener.**</span></span>  
  
     <span data-ttu-id="fd34c-109">Para obter mais informações, consulte [Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fd34c-109">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="fd34c-110">**Verifique se o ponto de extremidade do Service Broker existe e se está configurado corretamente.**</span><span class="sxs-lookup"><span data-stu-id="fd34c-110">**Ensure that the Service Broker endpoint exists and is correctly configured.**</span></span>  
  
     <span data-ttu-id="fd34c-111">Em toda instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda uma réplica de disponibilidade para o grupo de disponibilidade, configure o ponto de extremidade do Service Broker, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fd34c-111">On every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica for the availability group, configure the Service Broker endpoint, as follows:</span></span>  
  
    -   <span data-ttu-id="fd34c-112">Defina LISTENER_IP como 'ALL'.</span><span class="sxs-lookup"><span data-stu-id="fd34c-112">Set LISTENER_IP to 'ALL'.</span></span> <span data-ttu-id="fd34c-113">Esta configuração habilitará conexões em qualquer endereço IP válido que estiver associado ao ouvinte do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fd34c-113">This setting enables connections on any valid IP address that is bound to the availability group listener.</span></span>  
  
    -   <span data-ttu-id="fd34c-114">Defina a PORT do Service Broker como o mesmo número de porta em todas as instâncias do servidor de host.</span><span class="sxs-lookup"><span data-stu-id="fd34c-114">Set the Service Broker PORT to the same port number on all the host server instances.</span></span>  
  
        > [!TIP]  
        >  <span data-ttu-id="fd34c-115">Para exibir o número da porta do ponto de extremidade do Service Broker em determinada instância de servidor, consulte a coluna **port** da exibição de catálogo [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) , em que **type_desc** = 'SERVICE_BROKER'.</span><span class="sxs-lookup"><span data-stu-id="fd34c-115">To view the port number of the Service Broker endpoint on a given server instance, query the **port** column of the [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) catalog view, where **type_desc** = 'SERVICE_BROKER'.</span></span>  
  
     <span data-ttu-id="fd34c-116">O exemplo a seguir cria um ponto de extremidade do Service Broker autenticado do Windows que usa a porta de Service Broker padrão (4022) e escuta todos os endereços IP válidos.</span><span class="sxs-lookup"><span data-stu-id="fd34c-116">The following example creates a Windows authenticated Service Broker endpoint that uses the default Service Broker port (4022) and listens to all valid IP addresses.</span></span>  
  
    ```  
    CREATE ENDPOINT [SSBEndpoint]  
        STATE = STARTED  
        AS TCP  (LISTENER_PORT = 4022, LISTENER_IP = ALL )  
        FOR SERVICE_BROKER (AUTHENTICATION = WINDOWS)  
    ```  
  
     <span data-ttu-id="fd34c-117">Para obter mais informações, veja [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fd34c-117">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
3.  <span data-ttu-id="fd34c-118">**Conceda a permissão CONNECT no ponto de extremidade.**</span><span class="sxs-lookup"><span data-stu-id="fd34c-118">**Grant CONNECT permission on the endpoint.**</span></span>  
  
     <span data-ttu-id="fd34c-119">Conceda permissão CONNECT no ponto de extremidade do Service Broker para PUBLIC ou para um logon.</span><span class="sxs-lookup"><span data-stu-id="fd34c-119">Grant CONNECT permission on the Service Broker endpoint either to PUBLIC or to a login.</span></span>  
  
     <span data-ttu-id="fd34c-120">O exemplo a seguir concede a conexão em um ponto de extremidade do Service Broker nomeado `broker_endpoint` para PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="fd34c-120">The following example grants the connection on a Service Broker endpoint named `broker_endpoint` to PUBLIC.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[broker_endpoint] TO [PUBLIC]  
    ```  
  
     <span data-ttu-id="fd34c-121">Para obter mais informações, veja [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fd34c-121">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span>  
  
4.  <span data-ttu-id="fd34c-122">**Verifique se msdb contém uma rota AutoCreatedLocal ou uma rota para o serviço específico.**</span><span class="sxs-lookup"><span data-stu-id="fd34c-122">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fd34c-123">Por padrão, cada banco de dados de usuário, inclusive **msdb**, contém a rota **AutoCreatedLocal**.</span><span class="sxs-lookup"><span data-stu-id="fd34c-123">By default, each user database, including **msdb**, contains the route **AutoCreatedLocal**.</span></span> <span data-ttu-id="fd34c-124">Essa rota corresponde a qualquer nome de serviço e instância do broker e especifica que a mensagem deve ser entregue na instância atual.</span><span class="sxs-lookup"><span data-stu-id="fd34c-124">This route matches any service name and broker instance and specifies that the message should be delivered within the current instance.</span></span> <span data-ttu-id="fd34c-125">**AutoCreatedLocal** tem prioridade inferior a rotas que especificam explicitamente um serviço que se comunica com uma instância remota.</span><span class="sxs-lookup"><span data-stu-id="fd34c-125">**AutoCreatedLocal** has lower priority than routes that explicitly specify a specific service that communicates with a remote instance.</span></span>  
  
     <span data-ttu-id="fd34c-126">Para obter informações sobre como criar rotas, veja [Exemplos de roteamento do Service Broker](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (na versão do [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] dos Manuais Online) e [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fd34c-126">For information about creating routes, see [Service Broker Routing Examples](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (in the [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] version of Books Online) and [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
##  <a name="requirements-for-sending-messages-to-a-remote-service-in-an-availability-group"></a><a name="SendRemoteMessages"></a> <span data-ttu-id="fd34c-127">Requisitos para enviar mensagens para um serviço remoto em um grupo de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="fd34c-127">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>  
  
1.  <span data-ttu-id="fd34c-128">**Criar uma rota para o serviço de destino.**</span><span class="sxs-lookup"><span data-stu-id="fd34c-128">**Create a route to the target service.**</span></span>  
  
     <span data-ttu-id="fd34c-129">Configure a rota da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fd34c-129">Configure the route as follows:</span></span>  
  
    -   <span data-ttu-id="fd34c-130">Defina ADDRESS como o endereço IP de ouvinte de grupo de disponibilidade que hospeda o banco de dados de serviço.</span><span class="sxs-lookup"><span data-stu-id="fd34c-130">Set ADDRESS to the listener IP address of availability group that hosts the service database.</span></span>  
  
    -   <span data-ttu-id="fd34c-131">Defina PORT como a porta que você especificou no ponto de extremidade do Service Broker de cada instância remota do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fd34c-131">Set PORT to the port that you specified in the Service Broker endpoint of each of the remote SQL Server instances.</span></span>  
  
     <span data-ttu-id="fd34c-132">O exemplo a seguir cria uma rota nomeada `RouteToTargetService` para o serviço `ISBNLookupRequestService` .</span><span class="sxs-lookup"><span data-stu-id="fd34c-132">The following example creates a route named `RouteToTargetService` for the `ISBNLookupRequestService` service.</span></span> <span data-ttu-id="fd34c-133">A rota destina-se ao ouvinte do grupo de disponibilidade, `MyAgListener`, que usa a porta 4022.</span><span class="sxs-lookup"><span data-stu-id="fd34c-133">The route targets the availability group listener, `MyAgListener`, which uses port 4022.</span></span>  
  
    ```  
    CREATE ROUTE [RouteToTargetService] WITH   
    SERVICE_NAME = 'ISBNLookupRequestService',   
    ADDRESS = 'TCP://MyAgListener:4022';  
  
    ```  
  
     <span data-ttu-id="fd34c-134">Para obter mais informações, veja [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fd34c-134">For more information, see [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
2.  <span data-ttu-id="fd34c-135">**Verifique se msdb contém uma rota AutoCreatedLocal ou uma rota para o serviço específico.**</span><span class="sxs-lookup"><span data-stu-id="fd34c-135">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span> <span data-ttu-id="fd34c-136">(Para obter mais informações, veja [Requisitos para que um serviço em um grupo de disponibilidade receba mensagens remotas](#ReceiveRemoteMessages), acima neste tópico.)</span><span class="sxs-lookup"><span data-stu-id="fd34c-136">(For more information, see [Requirements for a Service in an Availability Group to Receive Remote Messages](#ReceiveRemoteMessages), earlier in this topic.)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fd34c-137">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="fd34c-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="fd34c-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd34c-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
  
-   [<span data-ttu-id="fd34c-139">CREATE ROUTE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd34c-139">CREATE ROUTE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-route-transact-sql)  
  
-   [<span data-ttu-id="fd34c-140">GRANT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd34c-140">GRANT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-transact-sql)  
  
-   <span data-ttu-id="fd34c-141">[Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fd34c-141">[Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="fd34c-142">Criação e configuração de grupos de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fd34c-142">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="fd34c-143">Configurar contas de logon para espelhamento de banco de dados ou Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fd34c-143">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd34c-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd34c-144">See Also</span></span>  
 <span data-ttu-id="fd34c-145">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fd34c-145">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="fd34c-146">[Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="fd34c-146">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="fd34c-147">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="fd34c-147">SQL Server Service Broker</span></span>](../../configure-windows/sql-server-service-broker.md)  
  
  
