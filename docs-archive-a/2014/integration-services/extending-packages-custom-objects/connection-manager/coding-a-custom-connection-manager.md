---
title: Codificar um gerenciador de conexões personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], coding
ms.assetid: b12b6778-1f01-4a7d-984d-73f2f7630aa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 793d70ba0a9ae6176ab35c82e16b9aba8c9ba2cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683616"
---
# <a name="coding-a-custom-connection-manager"></a><span data-ttu-id="31a60-102">Codificando um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="31a60-102">Coding a Custom Connection Manager</span></span>
  <span data-ttu-id="31a60-103">Depois de criar uma classe que herda da classe base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> e aplicar o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> a essa classe, você deve substituir a implementação das propriedades e dos métodos da classe base para fornecer sua funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="31a60-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="31a60-104">Para obter exemplos de gerenciadores de conexão personalizados, consulte [Desenvolver uma interface do usuário para um gerenciador de conexões personalizado](developing-a-user-interface-for-a-custom-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="31a60-104">For samples of custom connection managers, see [Developing a User Interface for a Custom Connection Manager](developing-a-user-interface-for-a-custom-connection-manager.md).</span></span> <span data-ttu-id="31a60-105">Os exemplos de código mostrados neste tópico foram extraídos do exemplo do Gerenciador de Conexões Personalizado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31a60-105">The code examples shown in this topic are drawn from the SQL Server Custom Connection Manager sample.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31a60-106">A maioria das tarefas, fontes e destinos incluídos no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] funcionam somente com tipos específicos de gerenciadores de conexões internos.</span><span class="sxs-lookup"><span data-stu-id="31a60-106">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="31a60-107">Portanto, esses exemplos não podem ser testados com as tarefas e componentes internos.</span><span class="sxs-lookup"><span data-stu-id="31a60-107">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="configuring-the-connection-manager"></a><span data-ttu-id="31a60-108">Configurando o gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="31a60-108">Configuring the Connection Manager</span></span>  
  
### <a name="setting-the-connectionstring-property"></a><span data-ttu-id="31a60-109">Definindo a propriedade ConnectionString</span><span class="sxs-lookup"><span data-stu-id="31a60-109">Setting the ConnectionString Property</span></span>  
 <span data-ttu-id="31a60-110">A propriedade <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> é uma propriedade importante e a única propriedade exclusiva para um gerenciador de conexões personalizado.</span><span class="sxs-lookup"><span data-stu-id="31a60-110">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property is an important property and the only property unique to a custom connection manager.</span></span> <span data-ttu-id="31a60-111">O gerenciador de conexões usa o valor dessa propriedade para se conectar à fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="31a60-111">The connection manager uses the value of this property to connect to the external data source.</span></span> <span data-ttu-id="31a60-112">Se você estiver combinando várias outras propriedades, como nome de servidor e nome de banco de dados, para criar a cadeia de conexão você pode usar uma função auxiliar para montar a cadeia, substituindo alguns valores de um modelo de cadeia de conexão pelo novo valor fornecido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="31a60-112">If you are combining several other properties, such as server name and database name, to create the connection string, you can use a helper function to assemble the string by replacing certain values in a connection string template with the new value supplied by the user.</span></span> <span data-ttu-id="31a60-113">O exemplo de código seguinte mostra uma implementação da propriedade <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> que confia em uma função auxiliar para montar a cadeia.</span><span class="sxs-lookup"><span data-stu-id="31a60-113">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property that relies on a helper function to assemble the string.</span></span>  
  
```vb  
' Default values.  
Private _serverName As String = "(local)"  
Private _databaseName As String = "AdventureWorks"  
Private _connectionString As String = String.Empty  
  
Private Const CONNECTIONSTRING_TEMPLATE As String = _  
  "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI"  
  
Public Property ServerName() As String  
  Get  
    Return _serverName  
  End Get  
  Set(ByVal value As String)  
    _serverName = value  
  End Set  
End Property  
  
Public Property DatabaseName() As String  
  Get  
    Return _databaseName  
  End Get  
  Set(ByVal value As String)  
    _databaseName = value  
  End Set  
End Property  
  
Public Overrides Property ConnectionString() As String  
  Get  
    UpdateConnectionString()  
    Return _connectionString  
  End Get  
  Set(ByVal value As String)  
    _connectionString = value  
  End Set  
End Property  
  
Private Sub UpdateConnectionString()  
  
  Dim temporaryString As String = CONNECTIONSTRING_TEMPLATE  
  
  If Not String.IsNullOrEmpty(_serverName) Then  
    temporaryString = temporaryString.Replace("<servername>", _serverName)  
  End If  
  If Not String.IsNullOrEmpty(_databaseName) Then  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName)  
  End If  
  
  _connectionString = temporaryString  
  
End Sub  
```  
  
```csharp  
// Default values.  
private string _serverName = "(local)";  
private string _databaseName = "AdventureWorks";  
private string _connectionString = String.Empty;  
  
private const string CONNECTIONSTRING_TEMPLATE = "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI";  
  
public string ServerName  
{  
  get  
  {  
    return _serverName;  
  }  
  set  
  {  
    _serverName = value;  
  }  
}  
  
public string DatabaseName  
{  
  get  
  {  
    return _databaseName;  
  }  
  set  
  {  
    _databaseName = value;  
  }  
}  
  
public override string ConnectionString  
{  
  get  
  {  
    UpdateConnectionString();  
    return _connectionString;  
  }  
  set  
  {  
    _connectionString = value;  
  }  
}  
  
private void UpdateConnectionString()  
{  
  
  string temporaryString = CONNECTIONSTRING_TEMPLATE;  
  
  if (!String.IsNullOrEmpty(_serverName))  
  {  
    temporaryString = temporaryString.Replace("<servername>", _serverName);  
  }  
  
  if (!String.IsNullOrEmpty(_databaseName))  
  {  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName);  
  }  
  
  _connectionString = temporaryString;  
  
}  
```  
  
### <a name="validating-the-connection-manager"></a><span data-ttu-id="31a60-114">Validando o gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="31a60-114">Validating the Connection Manager</span></span>  
 <span data-ttu-id="31a60-115">Você anula o método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> para ter certeza de que o gerenciador de conexões foi configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="31a60-115">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method to make sure that the connection manager has been configured correctly.</span></span> <span data-ttu-id="31a60-116">No mínimo, você deve validar o formato da cadeia de conexão e se certificar de que foram fornecidos valores para todos os argumentos.</span><span class="sxs-lookup"><span data-stu-id="31a60-116">At a minimum, you should validate the format of the connection string and make sure that values have been provided for all arguments.</span></span> <span data-ttu-id="31a60-117">A execução não pode continuar até que o gerenciador de conexões retorne <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> do método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="31a60-117">Execution cannot continue until the connection manager returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="31a60-118">O exemplo de código seguinte mostra uma implementação de <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> que assegura que o usuário especificou um nome de servidor para a conexão.</span><span class="sxs-lookup"><span data-stu-id="31a60-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> that makes sure that the user has specified a server name for the connection.</span></span>  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  If String.IsNullOrEmpty(_serverName) Then  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0)  
    Return DTSExecResult.Failure  
  Else  
    Return DTSExecResult.Success  
  End If  
  
End Function  
```  
  
```csharp  
public override Microsoft.SqlServer.Dts.Runtime.DTSExecResult Validate(Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  if (String.IsNullOrEmpty(_serverName))  
  {  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0);  
    return DTSExecResult.Failure;  
  }  
  else  
  {  
    return DTSExecResult.Success;  
  }  
  
}  
```  
  
### <a name="persisting-the-connection-manager"></a><span data-ttu-id="31a60-119">Persistindo o gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="31a60-119">Persisting the Connection Manager</span></span>  
 <span data-ttu-id="31a60-120">Normalmente, você não tem que implementar a persistência personalizada em um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="31a60-120">Usually, you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="31a60-121">A persistência personalizada é necessária somente quando as propriedades de um objeto usam tipos de dados complexos.</span><span class="sxs-lookup"><span data-stu-id="31a60-121">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="31a60-122">Para obter mais informações, consulte [Desenvolvendo objetos personalizados para o Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="31a60-122">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="working-with-the-external-data-source"></a><span data-ttu-id="31a60-123">Trabalhando com a fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="31a60-123">Working with the External Data Source</span></span>  
 <span data-ttu-id="31a60-124">Os métodos que suportam a conexão a uma fonte de dados externa são os métodos mais importantes de um gerenciador de conexões personalizado.</span><span class="sxs-lookup"><span data-stu-id="31a60-124">The methods that support connecting to an external data source are the most important methods of a custom connection manager.</span></span> <span data-ttu-id="31a60-125">Os métodos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> são chamados em vários momentos durante o tempo de design e o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="31a60-125">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods are called at various times during both design time and run time.</span></span>  
  
### <a name="acquiring-the-connection"></a><span data-ttu-id="31a60-126">Adquirindo a conexão</span><span class="sxs-lookup"><span data-stu-id="31a60-126">Acquiring the Connection</span></span>  
 <span data-ttu-id="31a60-127">Você precisa decidir que tipo de objeto é apropriado para o método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> para voltar de seu gerenciador de conexões personalizado.</span><span class="sxs-lookup"><span data-stu-id="31a60-127">You need to decide what type of object it is appropriate for the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method to return from your custom connection manager.</span></span> <span data-ttu-id="31a60-128">Por exemplo, um gerenciador de conexões de Arquivo retorna somente uma cadeia que contém um caminho e um nome de arquivo, enquanto o gerenciador de conexões ADO.NET retorna um objeto de conexão gerenciado que já está aberto.</span><span class="sxs-lookup"><span data-stu-id="31a60-128">For example, a File connection manager returns only a string that contains a path and filename, whereas an ADO.NET connection manager returns a managed connection object that is already open.</span></span> <span data-ttu-id="31a60-129">Um gerenciador de conexões OLE DB retorna um objeto de conexão do OLE DB nativo que não pode ser usado a partir do código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="31a60-129">An OLE DB connection manager returns a native OLE DB connection object that cannot be used from managed code.</span></span> <span data-ttu-id="31a60-130">O gerenciador de conexões SQL Server personalizado, do qual são tirados os snippets de códigos deste tópico, retorna um objeto `SqlConnection` aberto.</span><span class="sxs-lookup"><span data-stu-id="31a60-130">The custom SQL Server connection manager, from which the code snippets in this topic are taken, returns an open `SqlConnection` object.</span></span>  
  
 <span data-ttu-id="31a60-131">Os usuários do seu gerenciador de conexões precisam saber antecipadamente que tipo de objeto devem esperar, assim podem converter o objeto retornado para o tipo apropriado e acessar seus métodos e propriedades.</span><span class="sxs-lookup"><span data-stu-id="31a60-131">Users of your connection manager need to know in advance what type of object to expect, so that they can cast the returned object to the appropriate type and access its methods and properties.</span></span>  
  
```vb  
Public Overrides Function AcquireConnection(ByVal txn As Object) As Object  
  
  Dim sqlConnection As New SqlConnection  
  
  UpdateConnectionString()  
  
  With sqlConnection  
    .ConnectionString = _connectionString  
    .Open()  
  End With  
  
  Return sqlConnection  
  
End Function  
```  
  
```csharp  
public override object AcquireConnection(object txn)  
{  
  
  SqlConnection sqlConnection = new SqlConnection();  
  
  UpdateConnectionString();  
  
  {  
    sqlConnection.ConnectionString = _connectionString;  
    sqlConnection.Open();  
  }  
  
  return sqlConnection;  
  
}  
```  
  
### <a name="releasing-the-connection"></a><span data-ttu-id="31a60-132">Liberando a conexão</span><span class="sxs-lookup"><span data-stu-id="31a60-132">Releasing the Connection</span></span>  
 <span data-ttu-id="31a60-133">A ação adotada no método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> depende do tipo de objeto que você retornou do método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="31a60-133">The action that you take in the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> method depends on the type of object that you returned from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span> <span data-ttu-id="31a60-134">Se houver um objeto de conexão aberto, você deve fechá-lo e liberar qualquer recurso que esteja usando.</span><span class="sxs-lookup"><span data-stu-id="31a60-134">If there is an open connection object, you should close it and to release any resources that it is using.</span></span> <span data-ttu-id="31a60-135">Se <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> retornou só um valor da cadeia de caracteres, nenhuma ação precisa ser tomada.</span><span class="sxs-lookup"><span data-stu-id="31a60-135">If <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> returned only a string value, no action needs to be taken.</span></span>  
  
```vb  
Public Overrides Sub ReleaseConnection(ByVal connection As Object)  
  
  Dim sqlConnection As SqlConnection  
  
  sqlConnection = DirectCast(connection, SqlConnection)  
  
  If sqlConnection.State <> ConnectionState.Closed Then  
    sqlConnection.Close()  
  End If  
  
End Sub  
```  
  
```csharp  
public override void ReleaseConnection(object connection)  
{  
  SqlConnection sqlConnection;  
  sqlConnection = (SqlConnection)connection;  
  if (sqlConnection.State != ConnectionState.Closed)  
    sqlConnection.Close();  
}  
```  
  
<span data-ttu-id="31a60-136">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="31a60-136">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="31a60-137">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="31a60-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="31a60-138">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="31a60-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="31a60-139">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="31a60-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a60-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31a60-140">See Also</span></span>  
 <span data-ttu-id="31a60-141">[Criando um Gerenciador de conexões personalizado](creating-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="31a60-141">[Creating a Custom Connection Manager](creating-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="31a60-142">Desenvolvendo uma interface do usuário para um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="31a60-142">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
