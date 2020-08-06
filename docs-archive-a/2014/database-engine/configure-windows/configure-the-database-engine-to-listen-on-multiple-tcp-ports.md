---
title: Configurar o Mecanismo de Banco de Dados para escutar em várias portas TCP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- ports [SQL Server], multiple
- TDS
- listen on multiple ports
- endpoints [SQL Server], TDS
- adding ports
- tabular data stream
- multiple ports
ms.assetid: 8e955033-06ef-403f-b813-3d8241b62f1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab803bcaa5ab6b6187c1a994abef02f81ae105c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570244"
---
# <a name="configure-the-database-engine-to-listen-on-multiple-tcp-ports"></a><span data-ttu-id="67b0a-102">Configurar o Mecanismo de Banco de Dados para escuta em várias portas TCP</span><span class="sxs-lookup"><span data-stu-id="67b0a-102">Configure the Database Engine to Listen on Multiple TCP Ports</span></span>
  <span data-ttu-id="67b0a-103">Este tópico descreve como configurar o [!INCLUDE[ssDE](../../includes/ssde-md.md)] para escutar em diversas portas TCP no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="67b0a-103">This topic describes how to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on multiple TCP ports in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="67b0a-104">Quando TCP/IP está habilitado para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o [!INCLUDE[ssDE](../../includes/ssde-md.md)] escutará conexões de entrada em um ponto de conexão que consiste em um endereço IP e número de porta TCP. Os procedimentos a seguir criam um ponto de extremidade de protocolo TDS, de forma que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escutará em uma porta TCP adicional.</span><span class="sxs-lookup"><span data-stu-id="67b0a-104">When TCP/IP is enabled for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will listen for incoming connections on a connection point consisting of an IP address and TCP port number.The following procedures create a tabular data stream (TDS) endpoint, so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will listen on an additional TCP port.</span></span>  
  
 <span data-ttu-id="67b0a-105">Possíveis razões para criar um segundo ponto de extremidade de protocolo TDS são:</span><span class="sxs-lookup"><span data-stu-id="67b0a-105">Possible reasons to create a second TDS endpoint include:</span></span>  
  
-   <span data-ttu-id="67b0a-106">Aumentar a segurança configurando o firewall para restringir o acesso ao ponto de extremidade padrão para computadores cliente locais em uma sub-rede específica.</span><span class="sxs-lookup"><span data-stu-id="67b0a-106">Increase security by configuring the firewall to restrict access to the default endpoint to local client computers on a specific subnet.</span></span> <span data-ttu-id="67b0a-107">Manter o acesso à Internet do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que sua equipe de suporte crie um novo ponto de extremidade que o firewall expõe para a Internet, restringindo os direitos de conexão a este ponto de extremidade para sua equipe de suporte ao servidor.</span><span class="sxs-lookup"><span data-stu-id="67b0a-107">Maintain Internet access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for your support team by creating a new endpoint that the firewall exposes to the Internet, and restricting connection rights to this endpoint to your server support team.</span></span>  
  
-   <span data-ttu-id="67b0a-108">Ajustar as conexões para processadores específicos ao usar Acesso de Memória Não uniforme (NUMA).</span><span class="sxs-lookup"><span data-stu-id="67b0a-108">Affinitizing connections to specific processors when using Non-Uniform Memory Access (NUMA).</span></span>  
  
 <span data-ttu-id="67b0a-109">A configuração de um ponto de extremidade de protocolo TDS consiste nas seguintes etapas, que podem ser efetuadas em qualquer ordem:</span><span class="sxs-lookup"><span data-stu-id="67b0a-109">Configuring a TDS endpoint consists of the following steps, which can be done in any order:</span></span>  
  
-   <span data-ttu-id="67b0a-110">Crie o ponto de extremidade de protocolo TDS para a porta TCP e restaure o acesso ao ponto de extremidade padrão, se apropriado.</span><span class="sxs-lookup"><span data-stu-id="67b0a-110">Create the TDS endpoint for the TCP port, and restore access to the default endpoint if appropriate.</span></span>  
  
-   <span data-ttu-id="67b0a-111">Conceda acesso ao ponto de extremidade para as entidades de servidor desejadas.</span><span class="sxs-lookup"><span data-stu-id="67b0a-111">Grant access to the endpoint to the desired server principals.</span></span>  
  
-   <span data-ttu-id="67b0a-112">Especifique o número da porta TCP para o endereço IP selecionado.</span><span class="sxs-lookup"><span data-stu-id="67b0a-112">Specify the TCP port number for the selected IP address.</span></span>  
  
 <span data-ttu-id="67b0a-113">Para obter mais informações sobre as configurações padrão do Firewall do Windows e uma descrição das portas TCP que afetam o Mecanismo de Banco de Dados, o Analysis Services, o Reporting Services e o Integration Services, veja [Configurar o Firewall do Windows para permitir acesso ao SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="67b0a-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-create-a-tds-endpoint"></a><span data-ttu-id="67b0a-114">Criar um ponto de extremidade de protocolo TDS</span><span class="sxs-lookup"><span data-stu-id="67b0a-114">To create a TDS endpoint</span></span>  
  
-   <span data-ttu-id="67b0a-115">Emita a seguinte instrução para criar um ponto de extremidade chamado **CustomConnection** para a porta 1500 de todos os endereços TCP disponíveis no servidor.</span><span class="sxs-lookup"><span data-stu-id="67b0a-115">Issue the following statement to create an endpoint named **CustomConnection** for port 1500 for all available TCP addresses on the server.</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE ENDPOINT [CustomConnection]  
    STATE = STARTED  
    AS TCP  
       (LISTENER_PORT = 1500, LISTENER_IP =ALL)  
    FOR TSQL() ;  
    GO  
    ```  
  
 <span data-ttu-id="67b0a-116">Ao criar um ponto de extremidade [!INCLUDE[tsql](../../includes/tsql-md.md)] novo, as permissões de conexão para o grupo **público** são revogadas para o ponto de extremidade de protocolo TDS padrão.</span><span class="sxs-lookup"><span data-stu-id="67b0a-116">When you create a new [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoint, connect permissions for **public** are revoked for the default TDS endpoint.</span></span> <span data-ttu-id="67b0a-117">Se o acesso ao grupo **público** for necessário para o ponto de extremidade padrão, aplique novamente esta permissão usando a instrução `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` .</span><span class="sxs-lookup"><span data-stu-id="67b0a-117">If access to the **public** group is needed for the default endpoint, reapply this permission by using the `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` statement.</span></span>  
  
#### <a name="to-grant-access-to-the-endpoint"></a><span data-ttu-id="67b0a-118">Conceder acesso ao ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="67b0a-118">To grant access to the endpoint</span></span>  
  
-   <span data-ttu-id="67b0a-119">Emita a seguinte instrução para conceder acesso ao ponto de extremidade **CustomConnection** para o grupo SQLSupport no domínio da corporação.</span><span class="sxs-lookup"><span data-stu-id="67b0a-119">Issue the following statement to grant access to the **CustomConnection** endpoint to the SQLSupport group in the corp domain.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[CustomConnection] to [corp\SQLSupport] ;  
    GO  
    ```  
  
#### <a name="to-configure-the-sql-server-database-engine-to-listen-on-an-additional-tcp-port"></a><span data-ttu-id="67b0a-120">Configurar o Mecanismo de Banco de Dados do SQL Server para efetuar a escuta em uma porta TCP adicional</span><span class="sxs-lookup"><span data-stu-id="67b0a-120">To configure the SQL Server Database Engine to listen on an additional TCP port</span></span>  
  
1.  <span data-ttu-id="67b0a-121">No SQL Server Configuration Manager, expanda **Configuração de Rede do SQL Server** e clique em **Protocolos para** _<instance_name>_ .</span><span class="sxs-lookup"><span data-stu-id="67b0a-121">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for**_<instance_name>_.</span></span>  
  
2.  <span data-ttu-id="67b0a-122">Expanda **Protocolos para** _<instance_name>_ e clique em **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="67b0a-122">Expand **Protocols for**_<instance_name>_, and then click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="67b0a-123">No painel direito, clique com o botão direito do mouse em cada endereço IP desabilitado que você deseja habilitar e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="67b0a-123">In the right pane, right-click each disabled IP address that you want to enable, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="67b0a-124">Clique com o botão direito do mouse em **IPAll**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="67b0a-124">Right-click **IPAll**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="67b0a-125">Na caixa **Porta TCP** , digite as portas nas quais deseja que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] efetue a escura, separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="67b0a-125">In the **TCP Port** box, type the ports that you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, separated by commas.</span></span> <span data-ttu-id="67b0a-126">Em nosso exemplo, se a porta padrão 1433 estiver listada, digite `,1500` para a caixa ler `1433,1500` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="67b0a-126">In our example, if the default port 1433 is listed, type `,1500` so the box reads `1433,1500`, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67b0a-127">Se você não estiver habilitando a porta em todos os endereços IP, configure a porta adicional na caixa de propriedades para apenas o endereço desejado.</span><span class="sxs-lookup"><span data-stu-id="67b0a-127">If you are not enabling the port on all IP addresses, configure the additional port in the property box for only for the desired address.</span></span> <span data-ttu-id="67b0a-128">Em seguida, no painel de console, clique com o botão direito do mouse em **TCP/IP**, clique em **Propriedades**e, na caixa **Escutar Tudo** , selecione **Não**.</span><span class="sxs-lookup"><span data-stu-id="67b0a-128">Then, in the console pane, right-click **TCP/IP**, click **Properties**, and in the **Listen All** box, select **No**.</span></span>  
  
6.  <span data-ttu-id="67b0a-129">No painel esquerdo, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="67b0a-129">In the left pane, click **SQL Server Services**.</span></span>  
  
7.  <span data-ttu-id="67b0a-130">No painel direito, clique com o botão direito do mouse em **SQL Server** _<instance_name>_ e clique em **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="67b0a-130">In the right pane, right-click **SQL Server**_<instance_name>_, and then click **Restart**.</span></span>  
  
     <span data-ttu-id="67b0a-131">Quando o [!INCLUDE[ssDE](../../includes/ssde-md.md)] reiniciar, o log de erros listará as portas nas quais o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está escutando.</span><span class="sxs-lookup"><span data-stu-id="67b0a-131">When the [!INCLUDE[ssDE](../../includes/ssde-md.md)] restarts, the Error log will list the ports on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening.</span></span>  
  
#### <a name="to-connect-to-the-new-endpoint"></a><span data-ttu-id="67b0a-132">Conectar-se ao novo ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="67b0a-132">To connect to the new endpoint</span></span>  
  
-   <span data-ttu-id="67b0a-133">Emita a instrução a seguir para se conectar ao ponto de extremidade **CustomConnection** da instância padrão do SQL Server no servidor chamado ACCT, usando uma conexão confiável, e assumindo que o usuário é membro do grupo [corp\SQLSupport].</span><span class="sxs-lookup"><span data-stu-id="67b0a-133">Issue the following statement to connect to the **CustomConnection** endpoint of the default instance of SQL Server on the server named ACCT, using a trusted connection, and assuming the user is a member of the [corp\SQLSupport] group.</span></span>  
  
    ```  
    sqlcmd -SACCT,1500  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="67b0a-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67b0a-134">See Also</span></span>  
 <span data-ttu-id="67b0a-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67b0a-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="67b0a-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67b0a-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="67b0a-137">[Permissões GRANT do ponto de extremidade &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67b0a-137">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="67b0a-138">Mapear portas TCP/IP para nós NUMA &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="67b0a-138">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)  
  
  
