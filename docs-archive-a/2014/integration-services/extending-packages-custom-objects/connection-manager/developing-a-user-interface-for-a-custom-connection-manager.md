---
title: Desenvolver uma interface do usuário para um gerenciador de conexões personalizado | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], developing user interface
- custom user interface [Integration Services], custom connection manager
ms.assetid: 908bf2ac-fc84-4af8-a869-1cb43573d2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc0e9f2a76f3d97c925c44219683ca6cd655e43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573199"
---
# <a name="developing-a-user-interface-for-a-custom-connection-manager"></a><span data-ttu-id="8339d-102">Desenvolvendo uma interface do usuário para um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="8339d-102">Developing a User Interface for a Custom Connection Manager</span></span>
  <span data-ttu-id="8339d-103">Depois de ter substituído a implementação das propriedades e dos métodos da classe de base para fornecer sua funcionalidade personalizada, talvez você queira criar uma interface do usuário personalizada para seu gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="8339d-103">After you have overridden the implementation of the properties and methods of the base class to provide your custom functionality, you may want to create a custom user interface for your connection manager.</span></span> <span data-ttu-id="8339d-104">Se você não criar uma interface de usuário personalizada, os usuários poderão configurar seu gerenciador de conexões somente utilizando a janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="8339d-104">If you do not create a custom user interface, users can configure your connection manager only by using the Properties window.</span></span>  
  
 <span data-ttu-id="8339d-105">Em um projeto ou assembly de interface do usuário personalizado, você normalmente tem duas classes – uma classe que implementa <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> e o formulário do Windows exibido para reunir informações do usuário.</span><span class="sxs-lookup"><span data-stu-id="8339d-105">In a custom user interface project or assembly, you normally have two classes-a class that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>, and the Windows form that it displays to gather information from the user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8339d-106">Depois de assinar e criar sua interface do usuário personalizada e instalá-la no cache de assembly global, conforme descrito em [Codificar um gerenciador de conexões personalizado](../building-deploying-and-debugging-custom-objects.md), lembre-se de fornecer o nome totalmente qualificado desta classe na propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8339d-106">After signing and building your custom user interface and installing it in the global assembly cache as described in [Coding a Custom Connection Manager](../building-deploying-and-debugging-custom-objects.md), remember to provide the fully qualified name of this class in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8339d-107">A maioria das tarefas, fontes e destinos incluídos no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] funcionam somente com tipos específicos de gerenciadores de conexões internos.</span><span class="sxs-lookup"><span data-stu-id="8339d-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="8339d-108">Portanto, esses exemplos não podem ser testados com as tarefas e componentes internos.</span><span class="sxs-lookup"><span data-stu-id="8339d-108">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="coding-the-user-interface-class"></a><span data-ttu-id="8339d-109">Codificando a classe de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="8339d-109">Coding the User Interface Class</span></span>  
 <span data-ttu-id="8339d-110">A interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> tem quatro métodos: <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="8339d-110">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface has four methods: <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A>.</span></span> <span data-ttu-id="8339d-111">As seções seguintes descrevem esses quatro métodos.</span><span class="sxs-lookup"><span data-stu-id="8339d-111">The following sections describe these four methods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8339d-112">Talvez não seja necessário gravar nenhum código para o método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A>, se nenhuma limpeza for exigida quando o usuário excluir uma instância do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="8339d-112">You may not need to write any code for the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Delete%2A> method if no cleanup is required when the user deletes an instance of the connection manager.</span></span>  
  
### <a name="initializing-the-user-interface"></a><span data-ttu-id="8339d-113">Inicializando a interface do usuário</span><span class="sxs-lookup"><span data-stu-id="8339d-113">Initializing the User Interface</span></span>  
 <span data-ttu-id="8339d-114">No método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A>, o designer fornece uma referência para o gerenciador de conexões que está sendo configurado, dessa forma a classe de interface do usuário pode modificar as propriedades do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="8339d-114">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A> method, the designer provides a reference to the connection manager that is being configured so that the user interface class can modify the connection manager's properties.</span></span> <span data-ttu-id="8339d-115">Conforme mostrado no código a seguir, seu código precisa armazenar em cache a referência ao gerenciador de conexões para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="8339d-115">As shown in the following code, your code needs to cache the reference to the connection managerfor later use.</span></span>  
  
```vb  
Public Sub Initialize(ByVal connectionManager As Microsoft.SqlServer.Dts.Runtime.ConnectionManager, ByVal serviceProvider As System.IServiceProvider) Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize  
  
    _connectionManager = connectionManager  
    _serviceProvider = serviceProvider  
  
  End Sub  
```  
  
```csharp  
public void Initialize(Microsoft.SqlServer.Dts.Runtime.ConnectionManager connectionManager, System.IServiceProvider serviceProvider)  
{  
  
  _connectionManager = connectionManager;  
  _serviceProvider = serviceProvider;  
  
}  
```  
  
### <a name="creating-a-new-instance-of-the-user-interface"></a><span data-ttu-id="8339d-116">Criando uma nova instância da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="8339d-116">Creating a New Instance of the User Interface</span></span>  
 <span data-ttu-id="8339d-117">O método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, que não é um construtor, é chamado após o método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A> quando o usuário cria uma nova instância do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="8339d-117">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> method, which is not a constructor, is called after the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Initialize%2A> method when the user creates a new instance of the connection manager.</span></span> <span data-ttu-id="8339d-118">No método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A>, você normalmente quer exibir o formulário para editar, a menos que o usuário tivesse copiado e colado um gerenciador de conexões existente.</span><span class="sxs-lookup"><span data-stu-id="8339d-118">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> method, you usually want to display the form for editing, unless the user has copied and pasted an existing connection manager.</span></span> <span data-ttu-id="8339d-119">O código seguinte mostra uma implementação desse método.</span><span class="sxs-lookup"><span data-stu-id="8339d-119">The following code shows an implementation of this method.</span></span>  
  
```vb  
Public Function [New](ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, ByVal connectionUIArgs As Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs) As Boolean Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New  
  
  Dim clipboardService As IDtsClipboardService  
  
  clipboardService = _  
    DirectCast(_serviceProvider.GetService(GetType(IDtsClipboardService)), IDtsClipboardService)  
  If Not clipboardService Is Nothing Then  
    ' If the connection manager has been copied and pasted, take no action.  
    If clipboardService.IsPasteActive Then  
      Return True  
    End If  
  End If  
  
  Return EditSqlConnection(parentWindow)  
  
End Function  
```  
  
```csharp  
public bool New(System.Windows.Forms.IWin32Window parentWindow, Microsoft.SqlServer.Dts.Runtime.Connections connections, Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs connectionUIArgs)  
  {  
    IDtsClipboardService clipboardService;  
  
    clipboardService = (IDtsClipboardService)_serviceProvider.GetService(typeof(IDtsClipboardService));  
    if (clipboardService != null)  
    // If connection manager has been copied and pasted, take no action.  
    {  
      if (clipboardService.IsPasteActive)  
      {  
        return true;  
      }  
    }  
  
    return EditSqlConnection(parentWindow);  
  }  
```  
  
### <a name="editing-the-connection-manager"></a><span data-ttu-id="8339d-120">Editando o gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="8339d-120">Editing the Connection Manager</span></span>  
 <span data-ttu-id="8339d-121">Como o formulário para edição é chamado por meio dos métodos <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>, é conveniente utilizar uma função auxiliar para encapsular o código que exibe o formulário.</span><span class="sxs-lookup"><span data-stu-id="8339d-121">Because the form for editing is called from both the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.New%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> methods, it is convenient to use a helper function to encapsulate the code that displays the form.</span></span> <span data-ttu-id="8339d-122">O código seguinte mostra uma implementação dessa função auxiliar.</span><span class="sxs-lookup"><span data-stu-id="8339d-122">The following code shows an implementation of this helper function.</span></span>  
  
```vb  
Private Function EditSqlConnection(ByVal parentWindow As IWin32Window) As Boolean  
  
  Dim sqlCMUIForm As New SqlConnMgrUIFormVB  
  
  sqlCMUIForm.Initialize(_connectionManager, _serviceProvider)  
  If sqlCMUIForm.ShowDialog(parentWindow) = DialogResult.OK Then  
    Return True  
  Else  
    Return False  
  End If  
  
End Function  
```  
  
```csharp  
private bool EditSqlConnection(IWin32Window parentWindow)  
 {  
  
   SqlConnMgrUIFormCS sqlCMUIForm = new SqlConnMgrUIFormCS();  
  
   sqlCMUIForm.Initialize(_connectionManager, _serviceProvider);  
   if (sqlCMUIForm.ShowDialog(parentWindow) == DialogResult.OK)  
   {  
     return true;  
   }  
   else  
   {  
     return false;  
   }  
  
 }  
```  
  
 <span data-ttu-id="8339d-123">No método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A>, você tem que simplesmente exibir o formulário para editar.</span><span class="sxs-lookup"><span data-stu-id="8339d-123">In the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> method, you simply have to display the form for editing.</span></span> <span data-ttu-id="8339d-124">O código seguinte mostra uma implementação do método <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> que usa uma função auxiliar para encapsular o código para o formulário.</span><span class="sxs-lookup"><span data-stu-id="8339d-124">The following code shows an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit%2A> method that uses a helper function to encapsulate the code for the form.</span></span>  
  
```vb  
Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, ByVal connectionUIArg As Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs) As Boolean Implements Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI.Edit  
  
  Return EditSqlConnection(parentWindow)  
  
End Function  
```  
  
```csharp  
public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Microsoft.SqlServer.Dts.Runtime.Connections connections, Microsoft.SqlServer.Dts.Runtime.Design.ConnectionManagerUIArgs connectionUIArg)  
{  
  
  return EditSqlConnection(parentWindow);  
  
}  
```  
  
## <a name="coding-the-user-interface-form"></a><span data-ttu-id="8339d-125">Codificando o formulário de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="8339d-125">Coding the User Interface Form</span></span>  
 <span data-ttu-id="8339d-126">Depois de criar a classe de interface do usuário que implementa os métodos da interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>, você deverá criar um formulário do Windows onde o usuário possa configurar as propriedades do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="8339d-126">After creating the user interface class that implements the methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface, you must create a Windows form where the user can configure the properties of your connection manager.</span></span>  
  
### <a name="initializing-the-user-interface-form"></a><span data-ttu-id="8339d-127">Inicializando o formulário de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="8339d-127">Initializing the User Interface Form</span></span>  
 <span data-ttu-id="8339d-128">Quando você exibir seu formulário personalizado para editar, poderá transmitir uma referência ao gerenciador de conexões que está sendo editado.</span><span class="sxs-lookup"><span data-stu-id="8339d-128">When you display your custom form for editing, you can pass a reference to the connection manager that is being edited.</span></span> <span data-ttu-id="8339d-129">Você pode transmitir essa referência utilizando um construtor personalizado para a classe de formulário ou criando seu próprio método `Initialize`, conforme mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="8339d-129">You can pass this reference either by using a custom constructor for the form class, or by creating your own `Initialize` method as shown here.</span></span>  
  
```vb  
Public Sub Initialize(ByVal connectionManager As ConnectionManager, ByVal serviceProvider As IServiceProvider)  
  
  _connectionManager = connectionManager  
  _serviceProvider = serviceProvider  
  ConfigureControlsFromConnectionManager()  
  EnableControls()  
  
End Sub  
```  
  
```csharp  
public void Initialize(ConnectionManager connectionManager, IServiceProvider serviceProvider)  
 {  
  
   _connectionManager = connectionManager;  
   _serviceProvider = serviceProvider;  
   ConfigureControlsFromConnectionManager();  
   EnableControls();  
  
 }  
```  
  
### <a name="setting-properties-on-the-user-interface-form"></a><span data-ttu-id="8339d-130">Definindo propriedades no formulário de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="8339d-130">Setting Properties on the User Interface Form</span></span>  
 <span data-ttu-id="8339d-131">Finalmente, sua classe de formulário precisa de uma função auxiliar que preencha os controles no formulário quando ele for primeiramente carregado com os valores existentes ou padrão das propriedades do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="8339d-131">Finally, your form class needs a helper function that populates the controls on the form when it is first loaded with the existing or the default values of the properties of the connection manager.</span></span> <span data-ttu-id="8339d-132">Sua classe de formulário também precisa de uma função similar que defina os valores das propriedades para os valores inseridos pelo usuário quando o usuário clicar em OK e fechar o formulário.</span><span class="sxs-lookup"><span data-stu-id="8339d-132">Your form class also needs a similar function that sets the values of the properties to the values entered by the user when the user clicks OK and closes the form.</span></span>  
  
```vb  
Private Const CONNECTIONNAME_BASE As String = "SqlConnectionManager"  
  
Private Sub ConfigureControlsFromConnectionManager()  
  
  Dim tempName As String  
  Dim tempServerName As String  
  Dim tempDatabaseName As String  
  
  With _connectionManager  
  
    tempName = .Properties("Name").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempName) Then  
      _connectionName = tempName  
    Else  
      _connectionName = CONNECTIONNAME_BASE  
    End If  
  
    tempServerName = .Properties("ServerName").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempServerName) Then  
      _serverName = tempServerName  
      txtServerName.Text = _serverName  
    End If  
  
    tempDatabaseName = .Properties("DatabaseName").GetValue(_connectionManager).ToString  
    If Not String.IsNullOrEmpty(tempDatabaseName) Then  
      _databaseName = tempDatabaseName  
      txtDatabaseName.Text = _databaseName  
    End If  
  
  End With  
  
End Sub  
  
Private Sub ConfigureConnectionManagerFromControls()  
  
  With _connectionManager  
    .Properties("Name").SetValue(_connectionManager, _connectionName)  
    .Properties("ServerName").SetValue(_connectionManager, _serverName)  
    .Properties("DatabaseName").SetValue(_connectionManager, _databaseName)  
  End With  
  
End Sub  
```  
  
```csharp  
private const string CONNECTIONNAME_BASE = "SqlConnectionManager";  
  
private void ConfigureControlsFromConnectionManager()  
 {  
  
   string tempName;  
   string tempServerName;  
   string tempDatabaseName;  
  
   {  
     tempName = _connectionManager.Properties["Name"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempName))  
     {  
       _connectionName = tempName;  
     }  
     else  
     {  
       _connectionName = CONNECTIONNAME_BASE;  
     }  
  
     tempServerName = _connectionManager.Properties["ServerName"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempServerName))  
     {  
       _serverName = tempServerName;  
       txtServerName.Text = _serverName;  
     }  
  
     tempDatabaseName = _connectionManager.Properties["DatabaseName"].GetValue(_connectionManager).ToString();  
     if (!String.IsNullOrEmpty(tempDatabaseName))  
     {  
       _databaseName = tempDatabaseName;  
       txtDatabaseName.Text = _databaseName;  
     }  
  
   }  
  
 }  
  
 private void ConfigureConnectionManagerFromControls()  
 {  
  
   {  
     _connectionManager.Properties["Name"].SetValue(_connectionManager, _connectionName);  
     _connectionManager.Properties["ServerName"].SetValue(_connectionManager, _serverName);  
     _connectionManager.Properties["DatabaseName"].SetValue(_connectionManager, _databaseName);  
   }  
  
 }  
```  
  
<span data-ttu-id="8339d-133">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8339d-133">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8339d-134">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="8339d-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8339d-135">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="8339d-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8339d-136">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="8339d-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8339d-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8339d-137">See Also</span></span>  
 <span data-ttu-id="8339d-138">[Criando um Gerenciador de conexões personalizado](creating-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="8339d-138">[Creating a Custom Connection Manager](creating-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="8339d-139">Codificando um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="8339d-139">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
  
  
