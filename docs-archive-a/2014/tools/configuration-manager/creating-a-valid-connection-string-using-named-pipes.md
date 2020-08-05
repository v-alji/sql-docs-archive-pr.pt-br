---
title: Criando uma cadeia de conexão válida usando pipes nomeados | Microsoft Docs
description: Saiba como criar uma cadeia de conexão válida ao usar o protocolo de pipes nomeados para se conectar a uma instância do SQL Server. Exibir exemplos de nomes de pipe válidos.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], named pipes
- pipes [SQL Server]
- pipes [SQL Server], connecting to
- aliases [SQL Server], named pipes
- Named Pipes [SQL Server], connection strings
ms.assetid: 90930ff2-143b-4651-8ae3-297103600e4f
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f3e1d01e9e5b7b1d1c0d1bb822bf233ceee636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573347"
---
# <a name="creating-a-valid-connection-string-using-named-pipes"></a><span data-ttu-id="08f6c-104">Criando uma cadeia de conexão válida usando pipes nomeados</span><span class="sxs-lookup"><span data-stu-id="08f6c-104">Creating a Valid Connection String Using Named Pipes</span></span>
  <span data-ttu-id="08f6c-105">A menos que seja alterado pelo usuário, quando a instância padrão do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escuta no protocolo de pipes nomeados, ela é usada `\\.\pipe\sql\query` como o nome do pipe.</span><span class="sxs-lookup"><span data-stu-id="08f6c-105">Unless changed by the user, when the default instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on the named pipes protocol, it uses `\\.\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="08f6c-106">O ponto indica que o computador é local, `pipe` indica que a conexão é um pipe nomeado e `sql\query` é o nome do pipe.</span><span class="sxs-lookup"><span data-stu-id="08f6c-106">The period indicates that the computer is the local computer, `pipe` indicates that the connection is a named pipe, and `sql\query` is the name of the pipe.</span></span> <span data-ttu-id="08f6c-107">Para conectar ao pipe padrão, o alias deve ter `\\<computer_name>\pipe\sql\query` como nome do pipe.</span><span class="sxs-lookup"><span data-stu-id="08f6c-107">To connect to the default pipe, the alias must have `\\<computer_name>\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="08f6c-108">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiver sido configurado para escutar em um pipe diferente, o nome do pipe deverá usar esse pipe.</span><span class="sxs-lookup"><span data-stu-id="08f6c-108">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been configured to listen on a different pipe, the pipe name must use that pipe.</span></span> <span data-ttu-id="08f6c-109">Por exemplo, se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver usando `\\.\pipe\unit\app` como o pipe, o alias deverá usar `\\<computer_name>\pipe\unit\app` como o nome do pipe.</span><span class="sxs-lookup"><span data-stu-id="08f6c-109">For instance, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using `\\.\pipe\unit\app` as the pipe, the alias must use `\\<computer_name>\pipe\unit\app` as the pipe name.</span></span>  
  
 <span data-ttu-id="08f6c-110">Para criar um nome de pipe válido, deve você:</span><span class="sxs-lookup"><span data-stu-id="08f6c-110">To create a valid pipe name, you must:</span></span>  
  
-   <span data-ttu-id="08f6c-111">Especificar um **Nome de Alias**.</span><span class="sxs-lookup"><span data-stu-id="08f6c-111">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="08f6c-112">Selecione **pipes nomeados** como o **protocolo**.</span><span class="sxs-lookup"><span data-stu-id="08f6c-112">Select **Named Pipes** as the **Protocol**.</span></span>  
  
-   <span data-ttu-id="08f6c-113">Insira o **nome do pipe**.</span><span class="sxs-lookup"><span data-stu-id="08f6c-113">Enter the **Pipe Name**.</span></span> <span data-ttu-id="08f6c-114">Como alternativa, você pode deixar o **nome do pipe** em branco e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager concluirá o nome do pipe apropriado depois de especificar o **protocolo** e o **servidor**</span><span class="sxs-lookup"><span data-stu-id="08f6c-114">Alternatively, you can leave **Pipe Name** blank and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager will complete the appropriate pipe name after you specify the **Protocol** and **Server**</span></span>  
  
-   <span data-ttu-id="08f6c-115">Especifique um **servidor**.</span><span class="sxs-lookup"><span data-stu-id="08f6c-115">Specify a **Server**.</span></span> <span data-ttu-id="08f6c-116">Para uma instância nomeada, você pode fornecer um nome de servidor e um nome de instância.</span><span class="sxs-lookup"><span data-stu-id="08f6c-116">For a named instance you can provide a server name and instance name.</span></span>  
  
 <span data-ttu-id="08f6c-117">No momento da conexão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componente cliente nativo lê os valores de servidor, protocolo e nome de pipe do registro para o nome de alias especificado e cria um nome de pipe no formato `np:\\<computer_name>\pipe\<pipename>` ou `np:\\<IPAddress>\pipe\<pipename>` . Para uma instância nomeada, o nome do pipe padrão é `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query` .</span><span class="sxs-lookup"><span data-stu-id="08f6c-117">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and pipe name values from the registry for the specified alias name, and creates a pipe name in the format `np:\\<computer_name>\pipe\<pipename>` or `np:\\<IPAddress>\pipe\<pipename>`.For a named instance, the default pipe name is `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08f6c-118">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] Firewall do Windows fecha a porta 445 por padrão.</span><span class="sxs-lookup"><span data-stu-id="08f6c-118">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 445 by default.</span></span> <span data-ttu-id="08f6c-119">Como o [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se comunica pela porta 445, você deverá reabri-la se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver configurado para escutar conexões de entrada usando pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="08f6c-119">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 445, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using named pipes.</span></span> <span data-ttu-id="08f6c-120">Para obter informações sobre como configurar um firewall, consulte "Como configurar um firewall para acessar o SQL Server" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ou verifique a documentação do firewall.</span><span class="sxs-lookup"><span data-stu-id="08f6c-120">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="08f6c-121">Conectando-se ao servidor local</span><span class="sxs-lookup"><span data-stu-id="08f6c-121">Connecting to the Local Server</span></span>  
 <span data-ttu-id="08f6c-122">Ao conectar-se ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no mesmo computador que o cliente, você pode usar `(local)` como o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="08f6c-122">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)`as the server name.</span></span> <span data-ttu-id="08f6c-123">O uso de `(local)` não é incentivado, pois leva a ambiguidade; no entanto, ele pode ser útil quando se sabe que o cliente está sendo executado no computador pretendido.</span><span class="sxs-lookup"><span data-stu-id="08f6c-123">Using `(local)` is not encouraged because it leads to ambiguity; however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="08f6c-124">Por exemplo, ao criar um aplicativo para usuários móveis desconectados, como uma força de vendas, em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será executado em computadores laptop e armazenará dados de projeto, um cliente conectado a (local) sempre se conectaria ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no laptop.</span><span class="sxs-lookup"><span data-stu-id="08f6c-124">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to (local) would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="08f6c-125">A palavra `localhost` ou um ponto (.) pode ser usado no lugar de `(local)`.</span><span class="sxs-lookup"><span data-stu-id="08f6c-125">The word `localhost` or a period (.) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="08f6c-126">Verificando seu protocolo de conexão</span><span class="sxs-lookup"><span data-stu-id="08f6c-126">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="08f6c-127">A consulta a seguir retornará o protocolo usado para a conexão atual.</span><span class="sxs-lookup"><span data-stu-id="08f6c-127">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="08f6c-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="08f6c-128">Examples</span></span>  
 <span data-ttu-id="08f6c-129">Conectando-se ao pipe padrão pelo nome do servidor:</span><span class="sxs-lookup"><span data-stu-id="08f6c-129">Connecting by server name to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="08f6c-130">Conectando-se ao pipe padrão pelo Endereço IP:</span><span class="sxs-lookup"><span data-stu-id="08f6c-130">Connecting by IP Address to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <leave blank>  
Protocol           Named Pipes  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="08f6c-131">Conectando-se ao pipe não padrão pelo nome do servidor:</span><span class="sxs-lookup"><span data-stu-id="08f6c-131">Connecting by server name to a non-default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\unit\app  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="08f6c-132">Conectando-se a uma instância nomeada pelo nome do servidor:</span><span class="sxs-lookup"><span data-stu-id="08f6c-132">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\MSSQL$<instancename>\SQL\query  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="08f6c-133">Conectando-se ao computador local usando `localhost`:</span><span class="sxs-lookup"><span data-stu-id="08f6c-133">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             localhost  
  
```  
  
 <span data-ttu-id="08f6c-134">Conectando-se ao computador local usando um ponto:</span><span class="sxs-lookup"><span data-stu-id="08f6c-134">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <left blank>  
Protocol           Named Pipes  
Server             .  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="08f6c-135">Para especificar o protocolo de rede como um parâmetro **sqlcmd** , consulte "como conectar-se ao Mecanismo de Banco de Dados usando sqlcmd.exe" nos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manuais online do.</span><span class="sxs-lookup"><span data-stu-id="08f6c-135">To specify the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f6c-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08f6c-136">See Also</span></span>  
 <span data-ttu-id="08f6c-137">[Criando uma cadeia de conexão válida usando o protocolo de memória compartilhada](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="08f6c-137">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="08f6c-138">[Criando uma cadeia de conexão válida usando IP TCP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="08f6c-138">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 [<span data-ttu-id="08f6c-139">Escolhendo um protocolo de rede</span><span class="sxs-lookup"><span data-stu-id="08f6c-139">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
