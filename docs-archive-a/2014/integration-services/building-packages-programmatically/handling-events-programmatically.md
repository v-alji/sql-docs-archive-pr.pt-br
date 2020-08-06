---
title: Manipular eventos programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services packages, events
- SQL Server Integration Services packages, events
- SSIS events, programmatically handling
- packages [Integration Services], events
- DtsEventHandler object
- SSIS packages, events
- SSIS events
- events [Integration Services], programmatically
- tasks [Integration Services], events
- IDTSEvents interface
ms.assetid: 0f00bd66-efd5-4f12-9e1c-36195f739332
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70d2d8909df65f775fc3a3034931bb599597068
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572146"
---
# <a name="handling-events-programmatically"></a><span data-ttu-id="c85fc-102">Manipulando eventos programaticamente</span><span class="sxs-lookup"><span data-stu-id="c85fc-102">Handling Events Programmatically</span></span>
  <span data-ttu-id="c85fc-103">O runtime [!INCLUDE[ssIS](../../includes/ssis-md.md)] fornece uma coleção de eventos que ocorrem antes, durante e depois da validação e execução de um pacote.</span><span class="sxs-lookup"><span data-stu-id="c85fc-103">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] runtime provides a collection of events that occur before, during, and after the validation and execution of a package.</span></span> <span data-ttu-id="c85fc-104">Esses eventos podem ser capturados de duas formas.</span><span class="sxs-lookup"><span data-stu-id="c85fc-104">These events can be captured in two ways.</span></span> <span data-ttu-id="c85fc-105">O primeiro método é através da implementação da interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> em uma classe e do fornecimento da classe como um parâmetro para os métodos `Execute` e `Validate` do pacote.</span><span class="sxs-lookup"><span data-stu-id="c85fc-105">The first method is by implementing the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface in a class, and supplying the class as a parameter to the `Execute` and `Validate` methods of the package.</span></span> <span data-ttu-id="c85fc-106">O segundo método é através da criação de objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>, que podem conter outros objetos [!INCLUDE[ssIS](../../includes/ssis-md.md)], tais como tarefas e loops, que são executados quando ocorre um evento em <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="c85fc-106">The second method is by creating <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects, which can contain other [!INCLUDE[ssIS](../../includes/ssis-md.md)] objects, such as tasks and loops, that are executed when an event in <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> occurs.</span></span> <span data-ttu-id="c85fc-107">Essa seção descreve esses dois métodos e fornece exemplos de código para demonstrar o seu uso.</span><span class="sxs-lookup"><span data-stu-id="c85fc-107">This section describes these two methods and provides code examples to demonstrate their use.</span></span>  
  
## <a name="receiving-idtsevents-callbacks"></a><span data-ttu-id="c85fc-108">Recebendo retornos de chamada de IDTSEvents</span><span class="sxs-lookup"><span data-stu-id="c85fc-108">Receiving IDTSEvents Callbacks</span></span>  
 <span data-ttu-id="c85fc-109">Desenvolvedores que criam e executam pacotes programaticamente podem receber notificações de eventos durante o processo de validação e execução através da interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="c85fc-109">Developers who build and execute packages programmatically can receive event notifications during the validation and execution process using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface.</span></span> <span data-ttu-id="c85fc-110">Isso é feito através da criação de uma classe que implementa a interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> e do fornecimento dessa classe como um parâmetro para os métodos `Validate` e `Execute` de um pacote.</span><span class="sxs-lookup"><span data-stu-id="c85fc-110">This is done by creating a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface and providing this class as a parameter to the `Validate` and `Execute` methods of a package.</span></span> <span data-ttu-id="c85fc-111">Os métodos da classe são chamados, então, pelo mecanismo de tempo de execução quando os eventos ocorrem.</span><span class="sxs-lookup"><span data-stu-id="c85fc-111">The methods of the class are then called by the run-time engine when the events occur.</span></span>  
  
 <span data-ttu-id="c85fc-112">A classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> é uma classe que já implementa a interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>; portanto, outro alternativa à implementação direta de <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> é derivar de <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> e substituir os eventos específicos aos quais você deseja responder.</span><span class="sxs-lookup"><span data-stu-id="c85fc-112">The <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class is a class that already implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface; therefore, another alternative to implementing <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> directly is to derive from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> and override the specific events that you want to respond to.</span></span> <span data-ttu-id="c85fc-113">Depois, você fornece sua classe como um parâmetro para os métodos `Validate` e `Execute` do <xref:Microsoft.SqlServer.Dts.Runtime.Package> para receber retornos de chamada de eventos.</span><span class="sxs-lookup"><span data-stu-id="c85fc-113">You then provide your class as a parameter to the `Validate` and `Execute` methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Package> to receive event callbacks.</span></span>  
  
 <span data-ttu-id="c85fc-114">O exemplo de código a seguir demonstra uma classe que deriva de <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>e substitui o método <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="c85fc-114">The following code sample demonstrates a class that derives from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>, and overrides the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A> method.</span></span> <span data-ttu-id="c85fc-115">Em seguida, a classe é fornecida como portanto `Validate` aos `Execute` métodos e do pacote.</span><span class="sxs-lookup"><span data-stu-id="c85fc-115">The class is then provided as aparameter to the `Validate` and `Execute` methods of the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      MyEventsClass eventsClass = new MyEventsClass();  
  
      p.Validate(null, null, eventsClass, null);  
      p.Execute(null, null, eventsClass, null, null);  
  
      Console.Read();  
    }  
  }  
  class MyEventsClass : DefaultEvents  
  {  
    public override void OnPreExecute(Executable exec, ref bool fireAgain)  
    {  
      // TODO: Add custom code to handle the event.  
      Console.WriteLine("The PreExecute event of the " +  
        exec.ToString() + " has been raised.");  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim eventsClass As MyEventsClass = New MyEventsClass()  
  
    p.Validate(Nothing, Nothing, eventsClass, Nothing)  
    p.Execute(Nothing, Nothing, eventsClass, Nothing, Nothing)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
Class MyEventsClass  
  Inherits DefaultEvents  
  
  Public Overrides Sub OnPreExecute(ByVal exec As Executable, ByRef fireAgain As Boolean)  
  
    ' TODO: Add custom code to handle the event.  
    Console.WriteLine("The PreExecute event of the " & _  
      exec.ToString() & " has been raised.")  
  
  End Sub  
  
End Class  
```  
  
## <a name="creating-dtseventhandler-objects"></a><span data-ttu-id="c85fc-116">Criando objetos DtsEventHandler</span><span class="sxs-lookup"><span data-stu-id="c85fc-116">Creating DtsEventHandler Objects</span></span>  
 <span data-ttu-id="c85fc-117">O mecanismo de tempo de execução fornece um sistema de tratamento e notificação de eventos robusto, altamente flexível através do objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="c85fc-117">The run-time engine provides a robust, highly flexible event handling and notification system through the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="c85fc-118">Esses objetos permitem que você crie fluxos de trabalho inteiros dentro do manipulador de eventos, que só são executados quando ocorre o evento ao qual pertence o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="c85fc-118">These objects let you design whole workflows within the event handler, which execute only when the event that the event handler belongs to occurs.</span></span> <span data-ttu-id="c85fc-119">O objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> é um contêiner que é executado quando o evento correspondente de seu objeto pai dispara.</span><span class="sxs-lookup"><span data-stu-id="c85fc-119">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object is a container that is executed when the corresponding event on its parent object fires.</span></span> <span data-ttu-id="c85fc-120">Essa arquitetura permite criar fluxos de trabalho isolados que são executados em resposta a eventos que ocorrem em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="c85fc-120">This architecture lets you create isolated workflows that are executed in response to events that occur on a container.</span></span> <span data-ttu-id="c85fc-121">Como objetos <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> são síncronos, a execução só retoma quando os manipuladores de eventos anexados ao evento retornam.</span><span class="sxs-lookup"><span data-stu-id="c85fc-121">Because <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are synchronous, execution does not resume until the event handlers that are attached to the event have returned.</span></span>  
  
 <span data-ttu-id="c85fc-122">O código a seguir demonstra como criar um objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="c85fc-122">The following code demonstrates how to create a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="c85fc-123">O código adiciona um <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> à coleção <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> do pacote e, depois, cria um objeto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> para o evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> da tarefa.</span><span class="sxs-lookup"><span data-stu-id="c85fc-123">The code adds a <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> collection of the package, and then creates a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object for the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event of the task.</span></span> <span data-ttu-id="c85fc-124">Um <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> é adicionado ao manipulador de eventos, que é executado quando o evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> ocorre para o primeiro <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span><span class="sxs-lookup"><span data-stu-id="c85fc-124">A <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> is added to the event handler, which is executed when the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event occurs for the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span></span> <span data-ttu-id="c85fc-125">Esse exemplo pressupõe que você tem um arquivo chamado C:\Windows\Temp\DemoFile.txt para teste.</span><span class="sxs-lookup"><span data-stu-id="c85fc-125">This example assumes that you have a file that is named C:\Windows\Temp\DemoFile.txt for testing.</span></span> <span data-ttu-id="c85fc-126">Na primeira execução do exemplo, o arquivo é copiado com êxito e o manipulador de eventos não é chamado.</span><span class="sxs-lookup"><span data-stu-id="c85fc-126">The first time that you run the sample, if copies the file successfully and the event handler is not called.</span></span> <span data-ttu-id="c85fc-127">Na segunda execução do exemplo, o <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> não consegue copiar o arquivo (pois o valor de <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> é `false`), o manipulador de eventos é chamado, o segundo <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> exclui o arquivo de origem e o pacote relata falha em função do erro ocorrido.</span><span class="sxs-lookup"><span data-stu-id="c85fc-127">The second time you run the sample, the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> fails to copy the file (because the value of <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> is `false`), the event handler is called, the second <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> deletes the source file, and the package reports failure because of the error that occurred.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c85fc-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c85fc-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string f = "DemoFile.txt";  
      Executable e;  
      TaskHost th;  
      FileSystemTask fst;  
  
      Package p = new Package();  
  
      p.Variables.Add("sourceFile", true, String.Empty,  
        @"C:\Windows\Temp\" + f);  
      p.Variables.Add("destinationFile", true, String.Empty,  
        Path.Combine(Directory.GetCurrentDirectory(), f));  
  
      // Create a first File System task and add it to the package.  
      // This task tries to copy a file from one folder to another.  
      e = p.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask1";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.CopyFile;  
      fst.OverwriteDestinationFile = false;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
      fst.Destination = "destinationFile";  
      fst.IsDestinationPathVariable = true;  
  
      // Add an event handler for the FileSystemTask's OnError event.  
      DtsEventHandler ehOnError = (DtsEventHandler)th.EventHandlers.Add("OnError");  
  
      // Create a second File System task and add it to the event handler.  
      // This task deletes the source file if the event handler is called.  
      e = ehOnError.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask2";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.DeleteFile;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
  
      DTSExecResult vr = p.Validate(null, null, null, null);  
      Console.WriteLine("ValidationResult = " + vr.ToString());  
      if (vr == DTSExecResult.Success)  
      {  
        DTSExecResult er = p.Execute(null, null, null, null, null);  
        Console.WriteLine("ExecutionResult = " + er.ToString());  
        if (er == DTSExecResult.Failure)  
          if (!File.Exists(@"C:\Windows\Temp\" + f))  
            Console.WriteLine("Source file has been deleted by the event handler.");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim f As String = "DemoFile.txt"  
    Dim e As Executable  
    Dim th As TaskHost  
    Dim fst As FileSystemTask  
  
    Dim p As Package = New Package()  
  
    p.Variables.Add("sourceFile", True, String.Empty, _  
      "C:\Windows\Temp\" & f)  
    p.Variables.Add("destinationFile", True, String.Empty, _  
      Path.Combine(Directory.GetCurrentDirectory(), f))  
  
    ' Create a first File System task and add it to the package.  
    ' This task tries to copy a file from one folder to another.  
    e = p.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.CopyFile  
    fst.OverwriteDestinationFile = False  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
    fst.Destination = "destinationFile"  
    fst.IsDestinationPathVariable = True  
  
    ' Add an event handler for the FileSystemTask's OnError event.  
    Dim ehOnError As DtsEventHandler = CType(th.EventHandlers.Add("OnError"), DtsEventHandler)  
  
    ' Create a second File System task and add it to the event handler.  
    ' This task deletes the source file if the event handler is called.  
    e = ehOnError.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.DeleteFile  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
  
    Dim vr As DTSExecResult = p.Validate(Nothing, Nothing, Nothing, Nothing)  
    Console.WriteLine("ValidationResult = " + vr.ToString())  
    If vr = DTSExecResult.Success Then  
      Dim er As DTSExecResult = p.Execute(Nothing, Nothing, Nothing, Nothing, Nothing)  
      Console.WriteLine("ExecutionResult = " + er.ToString())  
      If er = DTSExecResult.Failure Then  
        If Not File.Exists("C:\Windows\Temp\" + f) Then  
          Console.WriteLine("Source file has been deleted by the event handler.")  
        End If  
      End If  
    End If  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="c85fc-129">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c85fc-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c85fc-130">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="c85fc-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c85fc-131">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="c85fc-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c85fc-132">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="c85fc-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85fc-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c85fc-133">See Also</span></span>  
 <span data-ttu-id="c85fc-134">[Manipuladores de eventos do SSIS &#40;Integration Services&#41;](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="c85fc-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="c85fc-135">Adicionar um manipulador de eventos a um pacote</span><span class="sxs-lookup"><span data-stu-id="c85fc-135">Add an Event Handler to a Package</span></span>](../add-an-event-handler-to-a-package.md)  
  
  
