---
title: Carregando e executando um pacote local de forma programática | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Integration Services packages, running
- events [Integration Services], capturing
- packages [Integration Services], running
- loading packages programmatically
- Visual Basic [Integration Services]
- running packages [Integration Services]
- programmatically load and run packages [SSIS]
ms.assetid: 2f9fc1a8-a001-4c54-8c64-63b443725422
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a29faf623c02fea4fd8722c235f595f0fe4492e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679393"
---
# <a name="loading-and-running-a-local-package-programmatically"></a><span data-ttu-id="158bd-102">Carregando e executando um pacote local programaticamente</span><span class="sxs-lookup"><span data-stu-id="158bd-102">Loading and Running a Local Package Programmatically</span></span>
  <span data-ttu-id="158bd-103">É possível executar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] conforme necessário ou em horários predeterminados por meio dos métodos descritos em [Executando pacotes](../packages/run-integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="158bd-103">You can run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages as needed or at predetermined times by using the methods described in [Running Packages](../packages/run-integration-services-ssis-packages.md).</span></span> <span data-ttu-id="158bd-104">Entretanto, bastam algumas linhas de código para executar um pacote de um aplicativo personalizado, como, por exemplo, um aplicativo Windows Forms, um aplicativo do console, um formulário/serviço da Web ASP.NET ou um serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="158bd-104">However, with only a few lines of code, you can also run a package from a custom application such as a Windows Forms application, a console application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
 <span data-ttu-id="158bd-105">Esse tópico discute:</span><span class="sxs-lookup"><span data-stu-id="158bd-105">This topic discusses:</span></span>  
  
-   <span data-ttu-id="158bd-106">Carregando um pacote programaticamente</span><span class="sxs-lookup"><span data-stu-id="158bd-106">Loading a package programmatically</span></span>  
  
-   <span data-ttu-id="158bd-107">Executando um pacote programaticamente</span><span class="sxs-lookup"><span data-stu-id="158bd-107">Running a package programmatically</span></span>  
  
 <span data-ttu-id="158bd-108">Todos os métodos usados nesse tópico para carregar e executar pacotes exigem uma referência ao assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="158bd-108">All of the methods used in this topic to load and run packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="158bd-109">Depois de adicionar a referência em um projeto novo, importe o namespace <xref:Microsoft.SqlServer.Dts.Runtime> com uma instrução `using` ou `Imports`.</span><span class="sxs-lookup"><span data-stu-id="158bd-109">After adding the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="loading-a-package-programmatically"></a><span data-ttu-id="158bd-110">Carregando um pacote programaticamente</span><span class="sxs-lookup"><span data-stu-id="158bd-110">Loading a Package Programmatically</span></span>  
 <span data-ttu-id="158bd-111">Para carregar um pacote programaticamente no computador local, se o pacote for armazenado local ou remotamente, chame um destes métodos:</span><span class="sxs-lookup"><span data-stu-id="158bd-111">To load a package programmatically on the local computer, whether the package is stored locally or remotely, call one of the following methods:</span></span>  
  
|<span data-ttu-id="158bd-112">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="158bd-112">Storage Location</span></span>|<span data-ttu-id="158bd-113">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="158bd-113">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="158bd-114">Arquivo</span><span class="sxs-lookup"><span data-stu-id="158bd-114">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>|  
|<span data-ttu-id="158bd-115">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="158bd-115">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="158bd-116">Os métodos da classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> para trabalhar com o Repositório de Pacotes SSIS só dão suporte a ".", localhost ou ao nome do servidor local.</span><span class="sxs-lookup"><span data-stu-id="158bd-116">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="158bd-117">Você não pode usar "(local)".</span><span class="sxs-lookup"><span data-stu-id="158bd-117">You cannot use "(local)".</span></span>  
  
## <a name="running-a-package-programmatically"></a><span data-ttu-id="158bd-118">Executando um pacote programaticamente</span><span class="sxs-lookup"><span data-stu-id="158bd-118">Running a Package Programmatically</span></span>  
 <span data-ttu-id="158bd-119">O desenvolvimento de um aplicativo personalizado em código gerenciado que executa um pacote no computador local requer a abordagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="158bd-119">Developing a custom application in managed code that runs a package on the local computer requires the following approach.</span></span> <span data-ttu-id="158bd-120">As etapas resumidas aqui são demonstradas no exemplo de aplicativo de console a seguir.</span><span class="sxs-lookup"><span data-stu-id="158bd-120">The steps summarized here are demonstrated in the sample console application that follows.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically"></a><span data-ttu-id="158bd-121">Para executar um pacote programaticamente no computador local</span><span class="sxs-lookup"><span data-stu-id="158bd-121">To run a package on the local computer programmatically</span></span>  
  
1.  <span data-ttu-id="158bd-122">Inicie o ambiente de desenvolvimento do Visual Studio e crie um aplicativo novo no idioma de desenvolvimento de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="158bd-122">Start the Visual Studio development environment, and create a new application in your preferred development language.</span></span> <span data-ttu-id="158bd-123">Esse exemplo usa um aplicativo de console; contudo, você também pode executar um pacote de um aplicativo Windows Forms, de um formulário/serviço da Web ASP.NET ou de um serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="158bd-123">This example uses a console application; however you can also run a package from a Windows Forms application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
2.  <span data-ttu-id="158bd-124">No menu **Projeto**, clique em **Adicionar Referência** e adicione uma referência a **Microsoft.SqlServer.ManagedDTS.dll**.</span><span class="sxs-lookup"><span data-stu-id="158bd-124">On the **Project** menu, click **Add Reference** and add a reference to **Microsoft.SqlServer.ManagedDTS.dll**.</span></span> <span data-ttu-id="158bd-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="158bd-125">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="158bd-126">Use a `Imports` instrução Visual Basic ou a `using` instrução C# para importar o namespace **Microsoft. SqlServer. Dts. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="158bd-126">Use the Visual Basic `Imports` statement or the C# `using` statement to import the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
4.  <span data-ttu-id="158bd-127">Adicione o código a seguir na rotina principal.</span><span class="sxs-lookup"><span data-stu-id="158bd-127">Add the following code in the main routine.</span></span> <span data-ttu-id="158bd-128">O aplicativo de console completo deve ter a aparência do exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="158bd-128">The completed console application should look like the following example.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="158bd-129">O código de exemplo demonstra o carregamento do pacote do sistema de arquivos através do método <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>.</span><span class="sxs-lookup"><span data-stu-id="158bd-129">The sample code demonstrates loading the package from the file system by using the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A> method.</span></span> <span data-ttu-id="158bd-130">Mas você também pode carregar o pacote a partir do banco de dados MSDB, chamando o método <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>, ou a partir do repositório do pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], chamando o método <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>.</span><span class="sxs-lookup"><span data-stu-id="158bd-130">However you can also load the package from the MSDB database by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> method, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> method.</span></span>  
  
5.  <span data-ttu-id="158bd-131">Execute o projeto.</span><span class="sxs-lookup"><span data-stu-id="158bd-131">Run the project.</span></span> <span data-ttu-id="158bd-132">O código de exemplo executa o pacote de exemplo CalculatedColumns que é instalado com os exemplos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158bd-132">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="158bd-133">O resultado da execução do pacote é exibido na janela de console.</span><span class="sxs-lookup"><span data-stu-id="158bd-133">The result of package execution is displayed in the console window.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="158bd-134">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="158bd-134">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, Nothing)  
    pkgResults = pkg.Execute()  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, null);  
      pkgResults = pkg.Execute();  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
## <a name="capturing-events-from-a-running-package"></a><span data-ttu-id="158bd-135">Capturando eventos de um pacote em execução</span><span class="sxs-lookup"><span data-stu-id="158bd-135">Capturing Events from a Running Package</span></span>  
 <span data-ttu-id="158bd-136">Quando você executar um pacote programaticamente, conforme mostrado no exemplo anterior, talvez também queira capturar erros e outros eventos que ocorram durante a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="158bd-136">When you run a package programmatically as shown in the preceding sample, you may also want to capture errors and other events that occur as the package executes.</span></span> <span data-ttu-id="158bd-137">Para fazer isso, adicione uma classe herdada da classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> e passe uma referência para essa classe quando carregar o pacote.</span><span class="sxs-lookup"><span data-stu-id="158bd-137">You can accomplish this by adding a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class, and by passing a reference to that class when you load the package.</span></span> <span data-ttu-id="158bd-138">Embora o exemplo a seguir capture apenas o evento <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A>, há vários outros eventos que a classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> permite que você capture.</span><span class="sxs-lookup"><span data-stu-id="158bd-138">Although the following example captures only the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A> event, there are many other events that the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class lets you capture.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically-and-capture-package-events"></a><span data-ttu-id="158bd-139">Para executar um pacote programaticamente no computador local e capturar eventos de pacote</span><span class="sxs-lookup"><span data-stu-id="158bd-139">To run a package on the local computer programmatically and capture package events</span></span>  
  
1.  <span data-ttu-id="158bd-140">Siga as etapas do exemplo anterior para criar um projeto para esse exemplo.</span><span class="sxs-lookup"><span data-stu-id="158bd-140">Follow the steps in the preceding example to create a project for this example.</span></span>  
  
2.  <span data-ttu-id="158bd-141">Adicione o código a seguir na rotina principal.</span><span class="sxs-lookup"><span data-stu-id="158bd-141">Add the following code in the main routine.</span></span> <span data-ttu-id="158bd-142">O aplicativo de console completo deve ter a aparência do exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="158bd-142">The completed console application should look like the following example.</span></span>  
  
3.  <span data-ttu-id="158bd-143">Execute o projeto.</span><span class="sxs-lookup"><span data-stu-id="158bd-143">Run the project.</span></span> <span data-ttu-id="158bd-144">O código de exemplo executa o pacote de exemplo CalculatedColumns que é instalado com os exemplos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="158bd-144">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="158bd-145">O resultado da execução do pacote é exibido na janela de console, junto com eventuais erros.</span><span class="sxs-lookup"><span data-stu-id="158bd-145">The result of package execution is displayed in the console window, along with any errors that occur.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="158bd-146">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="158bd-146">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    Dim eventListener As New EventListener()  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, eventListener)  
    pkgResults = pkg.Execute(Nothing, Nothing, eventListener, Nothing, Nothing)  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
  
Class EventListener  
  Inherits DefaultEvents  
  
  Public Overrides Function OnError(ByVal source As Microsoft.SqlServer.Dts.Runtime.DtsObject, _  
    ByVal errorCode As Integer, ByVal subComponent As String, ByVal description As String, _  
    ByVal helpFile As String, ByVal helpContext As Integer, _  
    ByVal idofInterfaceWithError As String) As Boolean  
  
    ' Add application-specific diagnostics here.  
    Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description)  
    Return False  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppWithEventsCS  
{  
  class MyEventListener : DefaultEvents  
  {  
    public override bool OnError(DtsObject source, int errorCode, string subComponent,   
      string description, string helpFile, int helpContext, string idofInterfaceWithError)  
    {  
      // Add application-specific diagnostics here.  
      Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description);  
      return false;  
    }  
  }  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      MyEventListener eventListener = new MyEventListener();  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, eventListener);  
      pkgResults = pkg.Execute(null, null, eventListener, null, null);  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
<span data-ttu-id="158bd-147">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="158bd-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="158bd-148">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="158bd-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="158bd-149">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="158bd-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="158bd-150">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="158bd-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="158bd-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="158bd-151">See Also</span></span>  
 <span data-ttu-id="158bd-152">[Compreendendo as diferenças entre a execução local e remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="158bd-152">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="158bd-153">[Carregando e executando um pacote remoto programaticamente](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="158bd-153">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="158bd-154">Carregando a saída de um pacote local</span><span class="sxs-lookup"><span data-stu-id="158bd-154">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
