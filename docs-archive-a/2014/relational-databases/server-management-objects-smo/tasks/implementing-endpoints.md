---
title: Implementando pontos de extremidade | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- endpoints [SMO]
ms.assetid: f8674dbb-9bc0-488f-9def-e9e0ce1ddf86
author: stevestein
ms.author: sstein
ms.openlocfilehash: 293a661c6e1ad6f6139e30e0824e99686af98f90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684627"
---
# <a name="implementing-endpoints"></a><span data-ttu-id="55169-102">Implementando pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="55169-102">Implementing Endpoints</span></span>
  <span data-ttu-id="55169-103">Um ponto de extremidade é um serviço que pode escutar nativamente solicitações.</span><span class="sxs-lookup"><span data-stu-id="55169-103">An endpoint is a service that can listen natively for requests.</span></span> <span data-ttu-id="55169-104">O SMO dá suporte a vários tipos de pontos de extremidade usando o objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint>.</span><span class="sxs-lookup"><span data-stu-id="55169-104">SMO supports various types of endpoints by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object.</span></span> <span data-ttu-id="55169-105">Para criar um serviço de ponto de extremidade que manipula um tipo específico de carga, que usa um protocolo específico, crie uma instância de um objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint> e defina suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="55169-105">You can create an endpoint service that handles a specific type of payload, which uses a specific protocol, by creating an instance of an <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object and setting its properties.</span></span>  
  
 <span data-ttu-id="55169-106">A propriedade <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint> pode ser usada para especificar os tipos de carga a seguir:</span><span class="sxs-lookup"><span data-stu-id="55169-106">The <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object can be used to specify on of the following payload types:</span></span>  
  
-   <span data-ttu-id="55169-107">Espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="55169-107">Database mirroring</span></span>  
  
-   <span data-ttu-id="55169-108">SOAP (o suporte a pontos de extremidade SOAP está presente no [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] e nas versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="55169-108">SOAP (support for SOAP endpoints is present in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] and earlier [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] versions)</span></span>  
  
-   <span data-ttu-id="55169-109">Agente de Serviço</span><span class="sxs-lookup"><span data-stu-id="55169-109">Service Broker</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)]  
  
 <span data-ttu-id="55169-110">Além disso, a propriedade <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> pode ser usada para especificar os dois protocolos com suporte a seguir:</span><span class="sxs-lookup"><span data-stu-id="55169-110">Also, the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property can be used to specify the following two supported protocols:</span></span>  
  
-   <span data-ttu-id="55169-111">Protocolo HTTP</span><span class="sxs-lookup"><span data-stu-id="55169-111">HTTP protocol</span></span>  
  
-   <span data-ttu-id="55169-112">Protocolo TCP</span><span class="sxs-lookup"><span data-stu-id="55169-112">TCP protocol</span></span>  
  
 <span data-ttu-id="55169-113">Após a especificação do tipo de carga, a carga real pode ser definida usando a propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A>.</span><span class="sxs-lookup"><span data-stu-id="55169-113">Having specified the type of payload, the actual payload can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A> object property.</span></span> <span data-ttu-id="55169-114">A propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.Payload> fornece uma referência a um objeto de carga do tipo especificado para o qual as propriedades podem ser modificadas.</span><span class="sxs-lookup"><span data-stu-id="55169-114">The <xref:Microsoft.SqlServer.Management.Smo.Payload> object property provides a reference to a payload object of the specified type, for which the properties can be modified.</span></span>  
  
 <span data-ttu-id="55169-115">Para o objeto <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload>, especifique a função de espelhamento e se a criptografia está habilitada.</span><span class="sxs-lookup"><span data-stu-id="55169-115">For the <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload> object, you must specify the mirroring role and whether encryption is enabled.</span></span> <span data-ttu-id="55169-116">O objeto <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> requer informações sobre o encaminhamento de mensagens, o número máximo de conexões permitidas e o modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="55169-116">The <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> object requires information about message forwarding, maximum number of connections allowed and the authentication mode.</span></span> <span data-ttu-id="55169-117">O objeto <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> requer a definição de várias propriedades, incluindo a propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> que especifica os métodos de carga SOAP disponíveis para clientes (procedimentos armazenados e funções definidas pelo usuário).</span><span class="sxs-lookup"><span data-stu-id="55169-117">The <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> object requires various properties to be set including the <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> object property that specifies the SOAP payload methods available to clients (stored procedures and user-defined functions).</span></span>  
  
 <span data-ttu-id="55169-118">Da mesma forma, o protocolo real pode ser definido através da propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> que referencia um objeto de protocolo do tipo especificado pela propriedade <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A>.</span><span class="sxs-lookup"><span data-stu-id="55169-118">Similarly, the actual protocol can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> object property that references a protocol object of the type specified by <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property.</span></span> <span data-ttu-id="55169-119">O objeto <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> requer uma lista de endereços IP restritos e informações sobre porta, site e autenticação.</span><span class="sxs-lookup"><span data-stu-id="55169-119">The <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> object requires a list of restricted IP addresses, and port, website, and authentication information.</span></span> <span data-ttu-id="55169-120">O objeto <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> também requer uma lista de endereços IP restritos e informações sobre porta.</span><span class="sxs-lookup"><span data-stu-id="55169-120">The <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> object also requires a list of restricted IP addresses and port information.</span></span>  
  
 <span data-ttu-id="55169-121">Quando o ponto de extremidade estiver sido criado e totalmente definido, usuários do banco de dados, grupos, funções e logons poderão ter o acesso concedido, revogado e negado.</span><span class="sxs-lookup"><span data-stu-id="55169-121">When the endpoint has been created and fully defined, access can be granted to, revoked from, and denied to database users, groups, roles, and logons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55169-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="55169-122">Example</span></span>  
 <span data-ttu-id="55169-123">Para o exemplo de código a seguir, selecione o ambiente de programação, o modelo de programação e a linguagem de programação para criar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="55169-123">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="55169-124">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="55169-124">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-basic"></a><span data-ttu-id="55169-125">Criando um serviço de ponto de extremidade de espelhamento de banco de dados no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55169-125">Creating a Database Mirroring Endpoint Service in Visual Basic</span></span>  
 <span data-ttu-id="55169-126">O exemplo de código demonstra como criar um ponto de extremidade de espelhamento de banco de dados no SMO.</span><span class="sxs-lookup"><span data-stu-id="55169-126">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="55169-127">Isso é necessário antes da criação de um espelho de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55169-127">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="55169-128">Use o <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> e outras propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Database> para criar um espelho de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55169-128">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEndpoints1](SMO How to#SMO_VBEndpoints1)]  -->  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-c"></a><span data-ttu-id="55169-129">Criando um serviço de ponto de extremidade de espelhamento de banco de dados no Visual C#</span><span class="sxs-lookup"><span data-stu-id="55169-129">Creating a Database Mirroring Endpoint Service in Visual C#</span></span>  
 <span data-ttu-id="55169-130">O exemplo de código demonstra como criar um ponto de extremidade de espelhamento de banco de dados no SMO.</span><span class="sxs-lookup"><span data-stu-id="55169-130">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="55169-131">Isso é necessário antes da criação de um espelho de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55169-131">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="55169-132">Use o <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> e outras propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Database> para criar um espelho de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55169-132">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```csharp
{  
            //Set up a database mirroring endpoint on the server before   
        //setting up a database mirror.   
        //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Define an Endpoint object variable for database mirroring.   
            Endpoint ep = default(Endpoint);  
            ep = new Endpoint(srv, "Mirroring_Endpoint");  
            ep.ProtocolType = ProtocolType.Tcp;  
            ep.EndpointType = EndpointType.DatabaseMirroring;  
            //Specify the protocol ports.   
            ep.Protocol.Http.SslPort = 5024;  
            ep.Protocol.Tcp.ListenerPort = 6666;  
            //Specify the role of the payload.   
            ep.Payload.DatabaseMirroring.ServerMirroringRole = ServerMirroringRole.All;  
            //Create the endpoint on the instance of SQL Server.   
            ep.Create();  
            //Start the endpoint.   
            ep.Start();  
            Console.WriteLine(ep.EndpointState);  
        }  
```  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-powershell"></a><span data-ttu-id="55169-133">Criando um serviço de ponto de extremidade de espelhamento de banco de dados no PowerShell</span><span class="sxs-lookup"><span data-stu-id="55169-133">Creating a Database Mirroring Endpoint Service in PowerShell</span></span>  
 <span data-ttu-id="55169-134">O exemplo de código demonstra como criar um ponto de extremidade de espelhamento de banco de dados no SMO.</span><span class="sxs-lookup"><span data-stu-id="55169-134">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="55169-135">Isso é necessário antes da criação de um espelho de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55169-135">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="55169-136">Use o <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> e outras propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Database> para criar um espelho de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55169-136">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get a new endpoint to congure and add  
$ep = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Endpoint -argumentlist $srv,"Mirroring_Endpoint"  
  
#Set some properties  
$ep.ProtocolType = [Microsoft.SqlServer.Management.SMO.ProtocolType]::Tcp  
$ep.EndpointType = [Microsoft.SqlServer.Management.SMO.EndpointType]::DatabaseMirroring  
$ep.Protocol.Http.SslPort = 5024  
$ep.Protocol.Tcp.ListenerPort = 6666 #inline comment  
$ep.Payload.DatabaseMirroring.ServerMirroringRole = [Microsoft.SqlServer.Management.SMO.ServerMirroringRole]::All  
  
# Create the endpoint on the instance  
$ep.Create()  
  
# Start the endpoint  
$ep.Start()  
  
# Report its state  
$ep.EndpointState;  
```  
  
## <a name="see-also"></a><span data-ttu-id="55169-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55169-137">See Also</span></span>  
 [<span data-ttu-id="55169-138">O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="55169-138">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
