---
title: Codificar um provedor de logs personalizado | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom log providers [Integration Services], coding
ms.assetid: 979a29ca-956e-4fdd-ab47-f06e84cead7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d529420207ac065ae5ecb3c1d984de3021845b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680987"
---
# <a name="coding-a-custom-log-provider"></a><span data-ttu-id="36b03-102">Codificando um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="36b03-102">Coding a Custom Log Provider</span></span>
  <span data-ttu-id="36b03-103">Depois de criar uma classe que herda da classe base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> e aplicar o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> a essa classe, você deve substituir a implementação das propriedades e dos métodos da classe base para fornecer sua funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="36b03-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="36b03-104">Para amostras funcionais de provedores de logs personalizados, consulte [Desenvolver uma interface do usuário para um provedor de logs personalizado](developing-a-user-interface-for-a-custom-log-provider.md).</span><span class="sxs-lookup"><span data-stu-id="36b03-104">For working samples of custom log providers, see [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md).</span></span>  
  
## <a name="configuring-the-log-provider"></a><span data-ttu-id="36b03-105">Configurando o provedor de log</span><span class="sxs-lookup"><span data-stu-id="36b03-105">Configuring the Log Provider</span></span>  
  
### <a name="initializing-the-log-provider"></a><span data-ttu-id="36b03-106">Inicializando o provedor de log</span><span class="sxs-lookup"><span data-stu-id="36b03-106">Initializing the Log Provider</span></span>  
 <span data-ttu-id="36b03-107">Você substitui o método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> para armazenar em cache as referências à coleção de conexões e à interface de eventos.</span><span class="sxs-lookup"><span data-stu-id="36b03-107">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> method to cache references to the connections collection and the events interface.</span></span> <span data-ttu-id="36b03-108">Você poderá usar essas referências armazenadas em cache posteriormente em outros métodos do provedor de log.</span><span class="sxs-lookup"><span data-stu-id="36b03-108">You can use these cached references later in other methods of the log provider.</span></span>  
  
### <a name="using-the-configstring-property"></a><span data-ttu-id="36b03-109">Utilizando a propriedade ConfigString</span><span class="sxs-lookup"><span data-stu-id="36b03-109">Using the ConfigString Property</span></span>  
 <span data-ttu-id="36b03-110">Em tempo de design, um provedor de logs recebe informações de configuração da coluna **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="36b03-110">At design time, a log provider receives configuration information from the **Configuration** column.</span></span> <span data-ttu-id="36b03-111">Essas informações de configuração correspondem à propriedade <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> do provedor de log.</span><span class="sxs-lookup"><span data-stu-id="36b03-111">This configuration information corresponds to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property of the log provider.</span></span> <span data-ttu-id="36b03-112">Por padrão, esta coluna contém uma caixa de texto da qual você pode recuperar informações de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="36b03-112">By default, this column contains a text box from which you can retrieve any string information.</span></span> <span data-ttu-id="36b03-113">A maioria dos provedores de log fornecida com o [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] usa essa propriedade para armazenar o nome do gerenciador de conexões que o provedor usa para se conectar com uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="36b03-113">Most of the log providers included with [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] use this property to store the name of the connection manager that the provider uses to connect to an external data source.</span></span> <span data-ttu-id="36b03-114">Se o provedor de logs usar a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>, use o método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> para validar essa propriedade e verificar se ela está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="36b03-114">If your log provider uses the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property, use the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to validate this property and make sure that the property is set correctly.</span></span>  
  
### <a name="validating-the-log-provider"></a><span data-ttu-id="36b03-115">Validando o provedor de log.</span><span class="sxs-lookup"><span data-stu-id="36b03-115">Validating the Log Provider</span></span>  
 <span data-ttu-id="36b03-116">Substitua o método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> para verificar se o provedor foi configurado corretamente e se está pronto para execução.</span><span class="sxs-lookup"><span data-stu-id="36b03-116">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to make sure that the provider has been configured correctly and is ready for execution.</span></span> <span data-ttu-id="36b03-117">Normalmente, um nível mínimo de validação é para verificar se a <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="36b03-117">Typically, a minimum level of validation is to make sure that the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> is set correctly.</span></span> <span data-ttu-id="36b03-118">A execução não pode continuar até que o provedor de log retorne <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> do método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="36b03-118">Execution cannot continue until the log provider returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="36b03-119">O exemplo de código a seguir mostra uma implementação de <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> que verifica se o nome do gerenciador de conexões está especificado, se o gerenciador de conexões existe no pacote e se ele retorna um nome de arquivo na propriedade <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="36b03-119">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> that makes sure that the name of a connection manager name is specified, that the connection manager exists in the package, and that the connection manager returns a file name in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override DTSExecResult Validate(IDTSInfoEvents infoEvents)  
{  
    if (this.ConfigString.Length == 0 || connections.Contains(ConfigString) == false)  
    {  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
        return DTSExecResult.Failure;  
    }  
    else  
    {  
        string fileName = connections[ConfigString].AcquireConnection(null) as string;  
  
        if (fileName == null || fileName.Length == 0)  
        {  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
            return DTSExecResult.Failure;  
        }  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As IDTSInfoEvents) As DTSExecResult  
    If Me.ConfigString.Length = 0 Or connections.Contains(ConfigString) = False Then  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
        Return DTSExecResult.Failure  
    Else   
        Dim fileName As String =  connections(ConfigString).AcquireConnectionCType(as string, Nothing)  
  
        If fileName = Nothing Or fileName.Length = 0 Then  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
            Return DTSExecResult.Failure  
        End If  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
### <a name="persisting-the-log-provider"></a><span data-ttu-id="36b03-120">Persistência do provedor de log</span><span class="sxs-lookup"><span data-stu-id="36b03-120">Persisting the Log Provider</span></span>  
 <span data-ttu-id="36b03-121">Normalmente você não tem que implementar a persistência personalizada em um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="36b03-121">Ordinarily you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="36b03-122">A persistência personalizada é necessária somente quando as propriedades de um objeto usam tipos de dados complexos.</span><span class="sxs-lookup"><span data-stu-id="36b03-122">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="36b03-123">Para obter mais informações, consulte [Desenvolvendo objetos personalizados para o Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="36b03-123">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="logging-with-the-log-provider"></a><span data-ttu-id="36b03-124">Registrando em log com o provedor de log</span><span class="sxs-lookup"><span data-stu-id="36b03-124">Logging with the Log Provider</span></span>  
 <span data-ttu-id="36b03-125">Há três métodos de tempo de execução que devem ser substituídos por todos os provedores de log: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="36b03-125">There are three run-time methods that must be overridden by all log providers: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="36b03-126">Durante a validação e execução de um único pacote, são chamados os métodos <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="36b03-126">During the validation and execution of a single package, the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods are called more than one time.</span></span> <span data-ttu-id="36b03-127">Verifique se seu código personalizado não faz com que as entradas de log anteriores sejam substituídas pela próxima abertura e fechamento de log.</span><span class="sxs-lookup"><span data-stu-id="36b03-127">Make sure that your custom code does not cause earlier log entries to be overwritten by the next opening and closing of the log.</span></span> <span data-ttu-id="36b03-128">Se você optou por registrar em log os eventos de validação em seu pacote de teste, o primeiro evento registrado que deverá ver é o OnPreValidate. Se, em vez disso, o primeiro evento registrado que você visualizar for o PackageStart, os eventos de validação iniciais foram substituídos.</span><span class="sxs-lookup"><span data-stu-id="36b03-128">If you have selected to log validation events in your test package, the first logged event that you should see is OnPreValidate; if instead the first logged event that you see is PackageStart, the initial validation events have been overwritten.</span></span>  
  
### <a name="opening-the-log"></a><span data-ttu-id="36b03-129">Abrindo o log</span><span class="sxs-lookup"><span data-stu-id="36b03-129">Opening the Log</span></span>  
 <span data-ttu-id="36b03-130">A maioria dos provedores de log se conecta a fontes de dados externas, como um arquivo ou banco de dados, para armazenar as informações do evento coletadas durante a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="36b03-130">Most log providers connect to an external data source, such as a file or database, to store the event information that is collected during package execution.</span></span> <span data-ttu-id="36b03-131">Como com qualquer outro objeto no runtime, a conexão com a fonte de dados externa normalmente é realizada por meio de objetos do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="36b03-131">As with any other object in the runtime, connecting to the external data source is typically accomplished by using connection manager objects.</span></span>  
  
 <span data-ttu-id="36b03-132">O método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> é chamado no início da execução do pacote. Substitua esse método para estabelecer uma conexão com a fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="36b03-132">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method is called at the start of package execution.Override this method to establish a connection to the external data source.</span></span>  
  
 <span data-ttu-id="36b03-133">O código de exemplo seguinte mostra um provedor de log que abre um arquivo de texto para gravação durante o <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="36b03-133">The following sample code shows a log provider that opens a text file for writing during <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span></span> <span data-ttu-id="36b03-134">Ele abre o arquivo chamando o método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> do gerenciador de conexões que foi especificado na propriedade <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="36b03-134">It opens the file by calling the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager that was specified in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override void OpenLog()  
{  
    if(!this.connections.Contains(this.ConfigString))  
        throw new Exception("The ConnectionManager " + this.ConfigString + " does not exist in the Connections collection.");  
  
    this.connectionManager = connections[ConfigString];  
    string filePath = this.connectionManager.AcquireConnection(null) as string;  
  
    if(filePath == null || filePath.Length == 0)  
        throw new Exception("The ConnectionManager " + this.ConfigString + " is not a valid FILE ConnectionManager");  
  
    //  Create a StreamWriter to append to.  
    sw = new StreamWriter(filePath,true);  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString());  
}  
```  
  
```vb  
Public Overrides  Sub OpenLog()  
    If Not Me.connections.Contains(Me.ConfigString) Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " does not exist in the Connections collection.")  
    End If  
  
    Me.connectionManager = connections(ConfigString)  
    Dim filePath As String =  Me.connectionManager.AcquireConnectionCType(as string, Nothing)  
  
    If filePath = Nothing Or filePath.Length = 0 Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " is not a valid FILE ConnectionManager")  
    End If  
  
    '  Create a StreamWriter to append to.  
    sw = New StreamWriter(filePath,True)  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString())  
End Sub  
```  
  
### <a name="writing-log-entries"></a><span data-ttu-id="36b03-135">Gravando entradas de log</span><span class="sxs-lookup"><span data-stu-id="36b03-135">Writing Log Entries</span></span>  
 <span data-ttu-id="36b03-136">O método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> é chamado sempre que um objeto no pacote aciona um evento chamando um método Fire\<event> em uma das interfaces do evento.</span><span class="sxs-lookup"><span data-stu-id="36b03-136">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method is called every time that an object in the package raises an event by calling a Fire\<event> method on one of the event interfaces.</span></span> <span data-ttu-id="36b03-137">Cada evento normalmente é gerado com informações sobre seu contexto e uma mensagem explicativa.</span><span class="sxs-lookup"><span data-stu-id="36b03-137">Each event is raised with information about its context and usually an explanatory message.</span></span> <span data-ttu-id="36b03-138">Entretanto, nem toda chamada para o método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> inclui informações de cada parâmetro do método.</span><span class="sxs-lookup"><span data-stu-id="36b03-138">However, not every call to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method includes information for every method parameter.</span></span> <span data-ttu-id="36b03-139">Por exemplo, alguns eventos padrão cujos nomes são autoexplicativos não fornecem MessageText e DataCode e DataBytes são destinados para informações suplementares opcionais.</span><span class="sxs-lookup"><span data-stu-id="36b03-139">For example, some standard events whose names are self-explanatory do not provide MessageText, and DataCode and DataBytes are intended for optional supplemental information.</span></span>  
  
 <span data-ttu-id="36b03-140">O exemplo de código seguinte implementa o método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> e grava os eventos no fluxo que foi aberto na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="36b03-140">The following code example implements the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method, and writes the events to the stream that was opened in the previous section.</span></span>  
  
```csharp  
public override void Log(string logEntryName, string computerName, string operatorName, string sourceName, string sourceID, string executionID, string messageText, DateTime startTime, DateTime endTime, int dataCode, byte[] dataBytes)  
{  
    sw.Write(logEntryName + ",");  
    sw.Write(computerName + ",");  
    sw.Write(operatorName + ",");  
    sw.Write(sourceName + ",");  
    sw.Write(sourceID + ",");  
    sw.Write(messageText + ",");  
    sw.Write(dataBytes + ",");  
    sw.WriteLine("");  
}  
```  
  
```vb  
Public Overrides  Sub Log(ByVal logEnTryName As String, ByVal computerName As String, ByVal operatorName As String, ByVal sourceName As String, ByVal sourceID As String, ByVal executionID As String, ByVal messageText As String, ByVal startTime As DateTime, ByVal endTime As DateTime, ByVal dataCode As Integer, ByVal dataBytes() As Byte)  
    sw.Write(logEnTryName + ",")  
    sw.Write(computerName + ",")  
    sw.Write(operatorName + ",")  
    sw.Write(sourceName + ",")  
    sw.Write(sourceID + ",")  
    sw.Write(messageText + ",")  
    sw.Write(dataBytes + ",")  
    sw.WriteLine("")  
End Sub  
```  
  
### <a name="closing-the-log"></a><span data-ttu-id="36b03-141">Fechando o log</span><span class="sxs-lookup"><span data-stu-id="36b03-141">Closing the Log</span></span>  
 <span data-ttu-id="36b03-142">O método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> é chamado no final da execução do pacote, depois que todos os objetos do pacote concluíram a execução ou quando o pacote para devido a erros.</span><span class="sxs-lookup"><span data-stu-id="36b03-142">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method is called at the end of package execution, after all the objects in the package have completed execution, or, when the package stops because of errors.</span></span>  
  
 <span data-ttu-id="36b03-143">O exemplo de código a seguir demonstra uma implementação do método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> que fecha o fluxo de arquivos aberto durante o método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="36b03-143">The following code example demonstrates an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method that closes the file stream that was opened during the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method.</span></span>  
  
```csharp  
public override void CloseLog()  
{  
    if (sw != null)  
    {  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString());  
        sw.Close();  
    }  
}  
```  
  
```vb  
Public Overrides  Sub CloseLog()  
    If Not sw Is Nothing Then  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString())  
        sw.Close()  
    End If  
End Sub  
```  
  
<span data-ttu-id="36b03-144">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="36b03-144">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="36b03-145">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="36b03-145">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="36b03-146">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="36b03-146">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="36b03-147">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="36b03-147">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b03-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36b03-148">See Also</span></span>  
 <span data-ttu-id="36b03-149">[Criar um provedor de logs personalizado](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="36b03-149">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="36b03-150">Desenvolver uma interface do usuário para um provedor de logs personalizado</span><span class="sxs-lookup"><span data-stu-id="36b03-150">Developing a User Interface for a Custom Log Provider</span></span>](developing-a-user-interface-for-a-custom-log-provider.md)  
  
  
