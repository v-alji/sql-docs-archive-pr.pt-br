---
title: Criando uma cadeia de conexão válida usando TCP/IP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine]
- ports [SQL Server], connecting to
- TCP/IP [SQL Server], connection strings
- connection strings [Database Engine], TCP/IP
- aliases [SQL Server], TCP/IP
ms.assetid: ee5dbc2c-1fc6-42bd-bdf5-efa792557934
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f761fa86ec4ed09c13bf4807489754c10b979ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573345"
---
# <a name="creating-a-valid-connection-string-using-tcp-ip"></a><span data-ttu-id="1a1f9-102">Criando uma cadeia de conexão válida usando TCP/IP</span><span class="sxs-lookup"><span data-stu-id="1a1f9-102">Creating a Valid Connection String Using TCP IP</span></span>
  <span data-ttu-id="1a1f9-103">Para criar uma cadeia de conexão válida usando TCP/IP, deve você:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-103">To create a valid connection string using TCP/IP, you must:</span></span>  
  
-   <span data-ttu-id="1a1f9-104">Especificar um **Nome de Alias**.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-104">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="1a1f9-105">Para o **Servidor**, digite um nome do servidor ao qual você possa se conectar usando o utilitário **PING** ou um endereço IP ao qual possa se conectar usando o utilitário **PING** .</span><span class="sxs-lookup"><span data-stu-id="1a1f9-105">For the **Server**, enter either a server name to which you can connect using the **PING** utility, or an IP address to which you can connect using the **PING** utility.</span></span> <span data-ttu-id="1a1f9-106">Para uma instância nomeada, acrescente o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-106">For a named instance append the instance name.</span></span>  
  
-   <span data-ttu-id="1a1f9-107">Especificar **TCP/IP** para o **Protocolo**.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-107">Specify **TCP/IP** for the **Protocol**.</span></span>  
  
-   <span data-ttu-id="1a1f9-108">Opcionalmente, digitar um número de porta para **Número da Porta**.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-108">Optionally, enter a port number for the **Port No**.</span></span> <span data-ttu-id="1a1f9-109">O padrão é 1433, que é o número da porta da instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)] em um servidor.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-109">The default is 1433, which is the port number of the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a server.</span></span> <span data-ttu-id="1a1f9-110">Para se conectar a uma instância nomeada ou a uma instância padrão que não esteja escutando na porta 1433, é necessário fornecer o número da porta, ou iniciar o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a1f9-110">To connect to a named instance or a default instance that is not listening on port 1433, you must provide the port number, or start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span> <span data-ttu-id="1a1f9-111">Para obter informações sobre como configurar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser, consulte [Serviço do SQL Server Browser](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="1a1f9-111">For information on configuring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service, see [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="1a1f9-112">No momento da conexão, o componente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client lê os valores de servidor, protocolo e porta no Registro para o nome de alias especificado e cria uma cadeia de conexão no formato `tcp:<servername>[\<instancename>],<port>` ou `tcp:<IPAddress>[\<instancename>],<port>`.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-112">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and port values from the registry for the specified alias name, and creates a connection string in the format `tcp:<servername>[\<instancename>],<port>` or `tcp:<IPAddress>[\<instancename>],<port>`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a1f9-113">O Firewall do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows fecha a porta 1433 por padrão.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 1433 by default.</span></span> <span data-ttu-id="1a1f9-114">Como o [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se comunica pela porta 1433, você deverá reabri-la se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver configurado para escutar conexões de entrada de cliente usando TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-114">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 1433, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using TCP/IP.</span></span> <span data-ttu-id="1a1f9-115">Para obter informações sobre como configurar um firewall, consulte "Como configurar um firewall para acessar o SQL Server" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ou verifique a documentação do firewall.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-115">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1a1f9-116">e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dão suporte total ao protocolo IP versão 4 (IPv4) e versão 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="1a1f9-116">and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fully support both Internet Protocol version 4 (IPv4) and Internet Protocol version 6 (IPv6).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1a1f9-117">O Configuration Manager aceita os formatos IPv4 e IPv6 para endereços IP.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-117">Configuration Manager accepts both IPv4 and IPv6 formats for IP addresses.</span></span> <span data-ttu-id="1a1f9-118">Para obter informações sobre IPv6, consulte "Conectando com o uso de IPv6" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a1f9-118">For information on IPv6, see "Connecting Using IPv6" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="1a1f9-119">Conectando-se ao servidor local</span><span class="sxs-lookup"><span data-stu-id="1a1f9-119">Connecting to the Local Server</span></span>  
 <span data-ttu-id="1a1f9-120">Ao conectar-se ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no mesmo computador que o cliente, você pode usar `(local)` como o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-120">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)` as the server name.</span></span> <span data-ttu-id="1a1f9-121">Esse procedimento não é incentivado, pois leva a ambiguidade. No entanto, ele pode ser útil quando se sabe que o cliente está sendo executado no computador pretendido.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-121">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="1a1f9-122">Por exemplo, ao criar um aplicativo para usuários móveis desconectados, como uma força de vendas, em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será executado em computadores laptop e armazenará dados de projeto, um cliente conectado a `(local)` sempre se conectaria ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no laptop.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-122">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to `(local)` would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="1a1f9-123">A palavra `localhost` ou um ponto ( **.** ) pode ser usado no lugar de `(local)`.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-123">The word `localhost` or a period (**.**) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="1a1f9-124">Verificando seu protocolo de conexão</span><span class="sxs-lookup"><span data-stu-id="1a1f9-124">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="1a1f9-125">A consulta a seguir retorna o protocolo usado para a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="1a1f9-125">The following query returns the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="1a1f9-126">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1a1f9-126">Examples</span></span>  
 <span data-ttu-id="1a1f9-127">Conectando pelo nome do servidor:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-127">Connecting by server name:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="1a1f9-128">Conectando-se a uma instância nomeada pelo nome do servidor:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-128">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>\<instancename>  
  
```  
  
 <span data-ttu-id="1a1f9-129">Conectando-se a uma porta especificada pelo nome do servidor:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-129">Connecting by server name to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="1a1f9-130">Conectando pelo endereço IP:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-130">Connecting by IP address:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="1a1f9-131">Conectando-se a uma instância nomeada pelo endereço IP:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-131">Connecting by IP address to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>\<instancename>  
  
```  
  
 <span data-ttu-id="1a1f9-132">Conectando-se a uma porta especificada pelo endereço IP:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-132">Connecting by IP address to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port number>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="1a1f9-133">Conectando-se ao computador local usando `(local)`:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-133">Connecting to the local computer using `(local)`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             (local)  
  
```  
  
 <span data-ttu-id="1a1f9-134">Conectando-se ao computador local usando `localhost`:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-134">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost  
  
```  
  
 <span data-ttu-id="1a1f9-135">Conectando-se a uma instância nomeada no computador local `localhost`:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-135">Connecting to a named instance on the local computer `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost\<instancename>  
  
```  
  
 <span data-ttu-id="1a1f9-136">Conectando-se ao computador local usando um ponto:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-136">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .  
  
```  
  
 <span data-ttu-id="1a1f9-137">Conectando-se a uma instância nomeada no computador local usando um ponto:</span><span class="sxs-lookup"><span data-stu-id="1a1f9-137">Connecting to a named instance on the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .\<instancename>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="1a1f9-138">Para obter informações sobre como especificar o protocolo de rede como um parâmetro **sqlcmd** , consulte "Como fazer conexão com o Mecanismo de Banco de Dados usando sqlcmd.exe" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a1f9-138">For information on specifying the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a1f9-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a1f9-139">See Also</span></span>  
 <span data-ttu-id="1a1f9-140">[Criando uma cadeia de conexão válida usando o protocolo de memória compartilhada](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="1a1f9-140">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="1a1f9-141">[Criando uma cadeia de conexão válida usando pipes nomeados](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="1a1f9-141">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="1a1f9-142">Escolhendo um protocolo de rede</span><span class="sxs-lookup"><span data-stu-id="1a1f9-142">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
