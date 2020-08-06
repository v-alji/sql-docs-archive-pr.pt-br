---
title: Conectando-se a uma instância do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, connections
- connections [SMO]
- instances of SQL Server, connections
- SMO [SQL Server], connections
ms.assetid: ad3cf354-b2e3-468b-b986-1232e375fd84
author: stevestein
ms.author: sstein
ms.openlocfilehash: efc21451f4a876c6edfe4a2389ca937d11bc5c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582944"
---
# <a name="connecting-to-an-instance-of-sql-server"></a><span data-ttu-id="9a968-102">Conectando-se a uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a968-102">Connecting to an Instance of SQL Server</span></span>
  <span data-ttu-id="9a968-103">A primeira etapa de programação em um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aplicativo Smo (Management Objects) é criar uma instância do <xref:Microsoft.SqlServer.Management.Smo.Server> objeto e estabelecer sua conexão com uma instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a968-103">The first programming step in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) application is to create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and to establish its connection to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9a968-104">Você pode criar uma instância do objeto <xref:Microsoft.SqlServer.Management.Smo.Server> e estabelecer uma conexão com a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de três maneiras.</span><span class="sxs-lookup"><span data-stu-id="9a968-104">You can create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and establish a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in three ways.</span></span> <span data-ttu-id="9a968-105">A primeira é usar uma variável do objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> para fornecer as informações de conexão.</span><span class="sxs-lookup"><span data-stu-id="9a968-105">The first is using a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable to provide the connection information.</span></span> <span data-ttu-id="9a968-106">A segunda é fornecer as informações de conexão definindo explicitamente as propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="9a968-106">The second is to provide the connection information by explicitly setting the <xref:Microsoft.SqlServer.Management.Smo.Server> object properties.</span></span> <span data-ttu-id="9a968-107">A terceira é transmitir o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no construtor do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="9a968-107">The third is to pass the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span>  
  
 <span data-ttu-id="9a968-108">**Usando um objeto ServerConnection**</span><span class="sxs-lookup"><span data-stu-id="9a968-108">**Using a ServerConnection object**</span></span>  
  
 <span data-ttu-id="9a968-109">A vantagem de usar a variável do objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> é que as informações de conexão podem ser reutilizadas.</span><span class="sxs-lookup"><span data-stu-id="9a968-109">The advantage of using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable is that the connection information can be reused.</span></span> <span data-ttu-id="9a968-110">Declare uma variável do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="9a968-110">Declare a <xref:Microsoft.SqlServer.Management.Smo.Server> object variable.</span></span> <span data-ttu-id="9a968-111">Declare um objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> e defina as propriedades com informações de conexão como o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]e o modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a968-111">Then, declare a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object and set properties with connection information such as the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and the authentication mode.</span></span> <span data-ttu-id="9a968-112">Passe a variável do objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> como parâmetro para o construtor do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="9a968-112">Then, pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable as a parameter to the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span> <span data-ttu-id="9a968-113">Não é recomendável compartilhar conexões entre diferentes objetos de servidor simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="9a968-113">It is not recommended to share connections between different server objects at the same time.</span></span> <span data-ttu-id="9a968-114">Use o método <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> para obter uma cópia das configurações de conexão existentes.</span><span class="sxs-lookup"><span data-stu-id="9a968-114">Use the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to get a copy of the existing connection settings.</span></span>  
  
 <span data-ttu-id="9a968-115">**Definindo explicitamente as propriedades do objeto Server**</span><span class="sxs-lookup"><span data-stu-id="9a968-115">**Setting Server object properties explicitly**</span></span>  
  
 <span data-ttu-id="9a968-116">Como alternativa, você pode declarar a variável do objeto <xref:Microsoft.SqlServer.Management.Smo.Server> e chamar o construtor padrão.</span><span class="sxs-lookup"><span data-stu-id="9a968-116">Alternatively, you can declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and call the default constructor.</span></span> <span data-ttu-id="9a968-117">Dessa maneira, o objeto <xref:Microsoft.SqlServer.Management.Smo.Server> tenta se conectar à instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com todas as configurações de conexão padrão.</span><span class="sxs-lookup"><span data-stu-id="9a968-117">As is, the <xref:Microsoft.SqlServer.Management.Smo.Server> object tries to connect to the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with all the default connection settings.</span></span>  
  
 <span data-ttu-id="9a968-118">**Fornecendo o nome de instância do SQL Server no construtor do objeto Server**</span><span class="sxs-lookup"><span data-stu-id="9a968-118">**Providing the SQL Server instance name in the Server object constructor**</span></span>  
  
 <span data-ttu-id="9a968-119">Declare a variável do objeto <xref:Microsoft.SqlServer.Management.Smo.Server> e passe o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como parâmetro de cadeia de caracteres no construtor.</span><span class="sxs-lookup"><span data-stu-id="9a968-119">Declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and pass the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance name as a string parameter in the constructor.</span></span> <span data-ttu-id="9a968-120">O objeto <xref:Microsoft.SqlServer.Management.Smo.Server> estabelece uma conexão com a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com as configurações de conexão padrão.</span><span class="sxs-lookup"><span data-stu-id="9a968-120">The <xref:Microsoft.SqlServer.Management.Smo.Server> object establishes a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the default connection settings.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="9a968-121">Pool de conexões</span><span class="sxs-lookup"><span data-stu-id="9a968-121">Connection Pooling</span></span>  
 <span data-ttu-id="9a968-122">Normalmente não é necessário chamar o método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> do objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="9a968-122">It is typically not required to call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span> <span data-ttu-id="9a968-123">O SMO estabelecerá automaticamente uma conexão quando for necessário e liberará a conexão com o pool de conexão após concluir as operações.</span><span class="sxs-lookup"><span data-stu-id="9a968-123">SMO will automatically establish a connection when required, and release the connection to the connection pool after it has finished performing operations.</span></span> <span data-ttu-id="9a968-124">Quando o método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> é chamado, a conexão não é liberada para o pool.</span><span class="sxs-lookup"><span data-stu-id="9a968-124">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not released to the pool.</span></span> <span data-ttu-id="9a968-125">Uma chamada explícita do método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> é necessária para liberar a conexão com o pool.</span><span class="sxs-lookup"><span data-stu-id="9a968-125">An explicit call to the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method is required to release the connection to the pool.</span></span> <span data-ttu-id="9a968-126">Além disso, você pode solicitar uma conexão sem pool definindo a propriedade <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> do objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="9a968-126">Additionally, you can request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="multithreaded-applications"></a><span data-ttu-id="9a968-127">Aplicativos multi-threaded</span><span class="sxs-lookup"><span data-stu-id="9a968-127">Multithreaded Applications</span></span>  
 <span data-ttu-id="9a968-128">Para aplicativos multithreaded, um objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> separado deveria ser usado em cada thread.</span><span class="sxs-lookup"><span data-stu-id="9a968-128">For multithreaded applications, a separate <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object should be used in each thread.</span></span>  
  
## <a name="connecting-to-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="9a968-129">Conectando-se a uma instância do SQL Server para RMO</span><span class="sxs-lookup"><span data-stu-id="9a968-129">Connecting to an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="9a968-130">O RMO (Replication Management Objects) usa um método ligeiramente diferente do SMO para conexão a um servidor de replicação.</span><span class="sxs-lookup"><span data-stu-id="9a968-130">Replication Management Objects (RMO) uses a slightly different method from SMO to connect to a replication server.</span></span>  
  
 <span data-ttu-id="9a968-131">Os objetos de programação de RMO exigem que seja feita uma conexão com uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> implementado pelo namespace `Microsoft.SqlServer.Management.Common`.</span><span class="sxs-lookup"><span data-stu-id="9a968-131">RMO programming objects require that a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is made by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object implemented by the `Microsoft.SqlServer.Management.Common` namespace.</span></span> <span data-ttu-id="9a968-132">Essa conexão com o servidor é feita independentemente de um objeto de programação de RMO.</span><span class="sxs-lookup"><span data-stu-id="9a968-132">This connection to the server is made independently of an RMO programming object.</span></span> <span data-ttu-id="9a968-133">Então, ela é passada para o objeto RMO, seja durante a criação da instância, seja por atribuição à propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> do objeto.</span><span class="sxs-lookup"><span data-stu-id="9a968-133">It is then it is passed to the RMO object either during instance creation or by assignment to the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property of the object.</span></span> <span data-ttu-id="9a968-134">Dessa maneira, um objeto de programação de RMO e as instâncias de objeto de conexão podem ser criados e gerenciados separadamente, e um único objeto de conexão pode ser reutilizado com vários objetos de programação de RMO.</span><span class="sxs-lookup"><span data-stu-id="9a968-134">In this manner, an RMO programming object and the connection object instances can be created and managed separately, and a single connection object can be reused with multiple RMO programming objects.</span></span> <span data-ttu-id="9a968-135">As regras a seguir se aplicam a conexões com um servidor de replicação:</span><span class="sxs-lookup"><span data-stu-id="9a968-135">The following rules apply for connections to a replication server:</span></span>  
  
-   <span data-ttu-id="9a968-136">São definidas todas as propriedades da conexão para um objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> especificado.</span><span class="sxs-lookup"><span data-stu-id="9a968-136">All properties for the connection are defined for a specified <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="9a968-137">Cada conexão com uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] precisa ter seu próprio objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="9a968-137">Each connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must have its own <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="9a968-138">Todas as informações sobre autenticação para estabelecer com êxito a conexão e o logon no servidor são fornecidas no objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="9a968-138">All authentication information to make the connection and successfully log on to the server is supplied in the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="9a968-139">Por padrão, as conexões são feitas usando a Autenticação do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="9a968-139">By default, connections are made by using Microsoft Windows Authentication.</span></span> <span data-ttu-id="9a968-140">Para usar a Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> precisa ser definido como False, e <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> e <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> precisam ser definidos com um logon e senha válidos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a968-140">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> must be set to False and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> must be set to a valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logon and password.</span></span> <span data-ttu-id="9a968-141">Credenciais de segurança sempre precisam ser armazenados e manipulados de maneira segura, além de fornecidos em tempo de execução quando possível.</span><span class="sxs-lookup"><span data-stu-id="9a968-141">Security credentials must always be stored and handled securely, and supplied at run time whenever possible.</span></span>  
  
-   <span data-ttu-id="9a968-142">O método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> precisa ser chamado antes de passar a conexão com qualquer objeto de programação de RMO.</span><span class="sxs-lookup"><span data-stu-id="9a968-142">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method must be called before passing the connection to any RMO programming object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9a968-143">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9a968-143">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="9a968-144">Conectando-se à instância local do SQL Server usando a Autenticação do Windows no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a968-144">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="9a968-145">A conexão com a instância local do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não exige muito código.</span><span class="sxs-lookup"><span data-stu-id="9a968-145">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="9a968-146">Em vez disso, ela depende das configurações padrão para o servidor e o método de autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a968-146">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="9a968-147">A primeira operação que exige a recuperação dos dados faz com que uma conexão seja criada.</span><span class="sxs-lookup"><span data-stu-id="9a968-147">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="9a968-148">Este exemplo é um [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] código .NET que se conecta à instância local do usando a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="9a968-148">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB1](SMO How to#SMO_VB1)]  -->  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="9a968-149">Conectando-se à instância local do SQL Server usando a Autenticação do Windows no Visual C#</span><span class="sxs-lookup"><span data-stu-id="9a968-149">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="9a968-150">A conexão com a instância local do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não exige muito código.</span><span class="sxs-lookup"><span data-stu-id="9a968-150">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="9a968-151">Em vez disso, ela depende das configurações padrão para o servidor e o método de autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a968-151">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="9a968-152">A primeira operação que exige a recuperação dos dados faz com que uma conexão seja criada.</span><span class="sxs-lookup"><span data-stu-id="9a968-152">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="9a968-153">Este exemplo é o código Visual C# .NET que se conecta à instância local do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="9a968-153">This example is Visual C# .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//The connection is established when a property is requested.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="9a968-154">Conectando-se a uma instância remota do SQL Server usando a Autenticação do Windows no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a968-154">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="9a968-155">Ao se conectar a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a Autenticação do Windows, você não precisa especificar o tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a968-155">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="9a968-156">A Autenticação do Windows é o padrão.</span><span class="sxs-lookup"><span data-stu-id="9a968-156">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="9a968-157">Este exemplo é um [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] código .NET que se conecta à instância remota do usando a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="9a968-157">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="9a968-158">A variável de cadeia de caracteres *strServer* contém o nome da instância remota.</span><span class="sxs-lookup"><span data-stu-id="9a968-158">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB2](SMO How to#SMO_VB2)]  -->  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="9a968-159">Conectando-se a uma instância remota do SQL Server usando a Autenticação do Windows no Visual C#</span><span class="sxs-lookup"><span data-stu-id="9a968-159">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="9a968-160">Ao se conectar a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a Autenticação do Windows, você não precisa especificar o tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a968-160">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="9a968-161">A Autenticação do Windows é o padrão.</span><span class="sxs-lookup"><span data-stu-id="9a968-161">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="9a968-162">Este exemplo é o código Visual C# .NET que se conecta à instância remota do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="9a968-162">This example is Visual C# .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="9a968-163">A variável de cadeia de caracteres *strServer* contém o nome da instância remota.</span><span class="sxs-lookup"><span data-stu-id="9a968-163">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
```  
{   
//Connect to a remote instance of SQL Server.   
Server srv;   
//The strServer string variable contains the name of a remote instance of SQL Server.   
srv = new Server(strServer);   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-basic"></a><span data-ttu-id="9a968-164">Conectando-se a uma instância do SQL Server usando a Autenticação do SQL Server no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a968-164">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual Basic</span></span>  
 <span data-ttu-id="9a968-165">Ao conectar-se a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], você deve especificar o tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a968-165">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="9a968-166">Este exemplo demonstra o método alternativo de declarar uma variável do objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, que habilita as informações de conexão a serem reutilizadas.</span><span class="sxs-lookup"><span data-stu-id="9a968-166">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="9a968-167">O exemplo é um [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] código .NET que demonstra como se conectar ao remoto e *vPassword* contém o logon e a senha.</span><span class="sxs-lookup"><span data-stu-id="9a968-167">The example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll  
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      Dim sqlServerLogin As [String] = "user_id"  
      Dim password As [String] = "pwd"  
      Dim instanceName As [String] = "instance_name"  
      Dim remoteSvrName As [String] = "remote_server_name"  
  
      ' Connecting to an instance of SQL Server using SQL Server Authentication  
      Dim srv1 As New Server()   ' connects to default instance  
      srv1.ConnectionContext.LoginSecure = False   ' set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin  
      srv1.ConnectionContext.Password = password  
      Console.WriteLine(srv1.Information.Version)   ' connection is established  
  
      ' Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      Dim srvConn As New ServerConnection()  
      srvConn.ServerInstance = ".\" & instanceName   ' connects to named instance  
      srvConn.LoginSecure = False   ' set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin  
      srvConn.Password = password  
      Dim srv2 As New Server(srvConn)  
      Console.WriteLine(srv2.Information.Version)   ' connection is established  
  
      ' For remote connection, remote server name / ServerInstance needs to be specified  
      Dim srvConn2 As New ServerConnection(remoteSvrName)  
      srvConn2.LoginSecure = False  
      srvConn2.Login = sqlServerLogin  
      srvConn2.Password = password  
      Dim srv3 As New Server(srvConn2)  
      Console.WriteLine(srv3.Information.Version)   ' connection is established  
   End Sub  
End Class  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-c"></a><span data-ttu-id="9a968-168">Conectando-se a uma instância do SQL Server usando a Autenticação do SQL Server no Visual C#</span><span class="sxs-lookup"><span data-stu-id="9a968-168">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual C#</span></span>  
 <span data-ttu-id="9a968-169">Ao conectar-se a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], você deve especificar o tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="9a968-169">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="9a968-170">Este exemplo demonstra o método alternativo de declarar uma variável do objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, que habilita as informações de conexão a serem reutilizadas.</span><span class="sxs-lookup"><span data-stu-id="9a968-170">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="9a968-171">O exemplo é o código do Visual C# .NET que demonstra como se conectar ao remoto e *vPassword* contêm o logon e a senha.</span><span class="sxs-lookup"><span data-stu-id="9a968-171">The example is Visual C# .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll  
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {   
      String sqlServerLogin = "user_id";  
      String password = "pwd";  
      String instanceName = "instance_name";  
      String remoteSvrName = "remote_server_name";  
  
      // Connecting to an instance of SQL Server using SQL Server Authentication  
      Server srv1 = new Server();   // connects to default instance  
      srv1.ConnectionContext.LoginSecure = false;   // set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin;  
      srv1.ConnectionContext.Password = password;  
      Console.WriteLine(srv1.Information.Version);   // connection is established  
  
      // Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      ServerConnection srvConn = new ServerConnection();  
      srvConn.ServerInstance = @".\" + instanceName;   // connects to named instance  
      srvConn.LoginSecure = false;   // set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin;  
      srvConn.Password = password;  
      Server srv2 = new Server(srvConn);  
      Console.WriteLine(srv2.Information.Version);   // connection is established  
  
      // For remote connection, remote server name / ServerInstance needs to be specified  
      ServerConnection srvConn2 = new ServerConnection(remoteSvrName);  
      srvConn2.LoginSecure = false;  
      srvConn2.Login = sqlServerLogin;  
      srvConn2.Password = password;  
      Server srv3 = new Server(srvConn2);  
      Console.WriteLine(srv3.Information.Version);   // connection is established  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a968-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a968-172">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
