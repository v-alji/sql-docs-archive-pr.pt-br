---
title: Configurar um servidor para escutar em uma porta TCP específica (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fixed port
- static ports
- ports [SQL Server], assigning numbers
- assigning port numbers
- dynamic ports [SQL Server]
- TCP/IP [SQL Server], port numbers
ms.assetid: 2276a5ed-ae3f-4855-96d8-f5bf01890640
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb740910c65580e8ea3170d03481e6cb628860
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569655"
---
# <a name="configure-a-server-to-listen-on-a-specific-tcp-port-sql-server-configuration-manager"></a><span data-ttu-id="001ba-102">Configurar um servidor para escuta em uma porta TCP específica (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="001ba-102">Configure a Server to Listen on a Specific TCP Port (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="001ba-103">Este tópico descreve como configurar uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] para escutar em uma porta fixa específica usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="001ba-103">This topic describes how to configure an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to listen on a specific fixed port by using the SQL Server Configuration Manager.</span></span> <span data-ttu-id="001ba-104">Se habilitada, a instância padrão do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] escutará na porta TCP 1433.</span><span class="sxs-lookup"><span data-stu-id="001ba-104">If enabled, the default instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on TCP port 1433.</span></span> <span data-ttu-id="001ba-105">As instâncias nomeadas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e do [!INCLUDE[ssEW](../../includes/ssew-md.md)] são configuradas para portas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="001ba-105">Named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] are configured for dynamic ports.</span></span> <span data-ttu-id="001ba-106">Isso significa que elas selecionam uma porta disponível quando o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é iniciado.</span><span class="sxs-lookup"><span data-stu-id="001ba-106">This means they select an available port when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service is started.</span></span> <span data-ttu-id="001ba-107">Ao conectar-se a uma instância nomeada através de um firewall, configure o [!INCLUDE[ssDE](../../includes/ssde-md.md)] para escutar em uma porta específica, para que a porta adequada possa ser aberta no firewall.</span><span class="sxs-lookup"><span data-stu-id="001ba-107">When you are connecting to a named instance through a firewall, configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on a specific port, so that the appropriate port can be opened in the firewall.</span></span>  
  
 <span data-ttu-id="001ba-108">Para obter mais informações sobre as configurações padrão do Firewall do Windows e uma descrição das portas TCP que afetam o Mecanismo de Banco de Dados, o Analysis Services, o Reporting Services e o Integration Services, veja [Configurar o Firewall do Windows para permitir acesso ao SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="001ba-108">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="001ba-109">Ao selecionar um número de porta, consulte [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) para obter uma lista de números de porta atribuídos a aplicativos específicos.</span><span class="sxs-lookup"><span data-stu-id="001ba-109">When selecting a port number, consult [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) for a list of port numbers that are assigned to specific applications.</span></span> <span data-ttu-id="001ba-110">Selecione um número de porta não atribuído.</span><span class="sxs-lookup"><span data-stu-id="001ba-110">Select an unassigned port number.</span></span> <span data-ttu-id="001ba-111">Para obter mais informações, consulte [O intervalo de porta dinâmica para TCP/IP mudou no Windows Vista e no Windows Server 2008](https://support.microsoft.com/kb/929851).</span><span class="sxs-lookup"><span data-stu-id="001ba-111">For more information, see [The default dynamic port range for TCP/IP has changed in Windows Vista and in Windows Server 2008](https://support.microsoft.com/kb/929851).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="001ba-112">O mecanismo de banco de dados começa a escutar em uma nova porta quando é reiniciado.</span><span class="sxs-lookup"><span data-stu-id="001ba-112">The Database Engine begins listening on a new port when restarted.</span></span> <span data-ttu-id="001ba-113">Entretanto, o serviço de Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] monitora o Registro e relata o novo número de porta, assim que a configuração é alterada, mesmo que o mecanismo de banco de dados não esteja usando essa porta.</span><span class="sxs-lookup"><span data-stu-id="001ba-113">However the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service monitors the registry and reports the new port number as soon as the configuration is changed, even though the Database Engine might not be using it.</span></span> <span data-ttu-id="001ba-114">Reinicie o mecanismo de banco de dados para garantir a consistência e evitar falhas de conexão.</span><span class="sxs-lookup"><span data-stu-id="001ba-114">Restart the Database Engine to ensure consistency and avoid connection failures.</span></span>  
  
 <span data-ttu-id="001ba-115">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="001ba-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="001ba-116">**Para configurar um servidor para escutar em uma porta TCP específica usando:**</span><span class="sxs-lookup"><span data-stu-id="001ba-116">**To configure a server to listen on a specific TCP port, using:**</span></span>  
  
     [<span data-ttu-id="001ba-117">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="001ba-117">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="001ba-118">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="001ba-118">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-assign-a-tcpip-port-number-to-the-sql-server-database-engine"></a><span data-ttu-id="001ba-119">Para atribuir um número de porta TCP/IP ao Mecanismo de Banco de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="001ba-119">To assign a TCP/IP port number to the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="001ba-120">No SQL Server Configuration Manager, no painel do console, expanda **Configuração de Rede do SQL Server**, expanda **Protocolos de \<instance name>** e, depois, clique duas vezes em **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="001ba-120">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, expand **Protocols for \<instance name>**, and then double-click **TCP/IP**.</span></span>  
  
2.  <span data-ttu-id="001ba-121">Na caixa de diálogo **Propriedades de TCP/IP** , na guia **Endereços IP** , vários endereços IP aparecem no formato **IP1**, **IP2**, até **IPAll**.</span><span class="sxs-lookup"><span data-stu-id="001ba-121">In the **TCP/IP Properties** dialog box, on the **IP Addresses** tab, several IP addresses appear in the format **IP1**, **IP2**, up to **IPAll**.</span></span> <span data-ttu-id="001ba-122">Um desses é para o endereço IP do adaptador de loopback, 127.0.0.1.</span><span class="sxs-lookup"><span data-stu-id="001ba-122">One of these is for the IP address of the loopback adapter, 127.0.0.1.</span></span> <span data-ttu-id="001ba-123">Endereços IP adicionais aparecem para cada Endereço IP no computador.</span><span class="sxs-lookup"><span data-stu-id="001ba-123">Additional IP addresses appear for each IP Address on the computer.</span></span> <span data-ttu-id="001ba-124">Clique com o botão direito do mouse em cada endereço e clique em **Propriedades** para identificar o endereço IP que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="001ba-124">Right-click each address, and then click **Properties** to identify the IP address that you want to configure.</span></span>  
  
3.  <span data-ttu-id="001ba-125">Se a caixa de diálogo **Portas TCP Dinâmicas** contiver **0**, indicando que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] está escutando em portas dinâmicas, exclua o 0.</span><span class="sxs-lookup"><span data-stu-id="001ba-125">If the **TCP Dynamic Ports** dialog box contains **0**, indicating the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is listening on dynamic ports, delete the 0.</span></span>  
  
4.  <span data-ttu-id="001ba-126">Na área da caixa **Propriedades** de **IP**_n_, na caixa **Porta TCP**, digite o número da porta em que esse endereço IP deverá escutar e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="001ba-126">In the **IP**_n_ **Properties** area box, in the **TCP Port** box, type the port number you want this IP address to listen on, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="001ba-127">No painel do console, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="001ba-127">In the console pane, click **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="001ba-128">No painel de detalhes, clique com o botão direito do mouse em **SQL Server (** \<instance name> **)** e depois clique em **Reiniciar** para interromper e reiniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="001ba-128">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="001ba-129">Após configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para escutar em uma porta específica, há três maneiras de se conectar a uma porta específica com um aplicativo cliente:</span><span class="sxs-lookup"><span data-stu-id="001ba-129">After you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on a specific port, there are three ways to connect to a specific port with a client application:</span></span>  
  
-   <span data-ttu-id="001ba-130">Execute o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no servidor para conectar-se à instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] pelo nome.</span><span class="sxs-lookup"><span data-stu-id="001ba-130">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance by name.</span></span>  
  
-   <span data-ttu-id="001ba-131">Crie um alias no cliente, especificando o número da porta.</span><span class="sxs-lookup"><span data-stu-id="001ba-131">Create an alias on the client, specifying the port number.</span></span>  
  
-   <span data-ttu-id="001ba-132">Programe o cliente para se conectar usando uma cadeia de conexão personalizada.</span><span class="sxs-lookup"><span data-stu-id="001ba-132">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="001ba-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="001ba-133">See Also</span></span>  
 [<span data-ttu-id="001ba-134">Criar ou excluir um alias de servidor para ser usado por um cliente &#40;SQL Server Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="001ba-134">Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;</span></span>](create-or-delete-a-server-alias-for-use-by-a-client.md)  
  
  
