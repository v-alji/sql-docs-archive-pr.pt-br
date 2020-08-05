---
title: Adicionar tarefas programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], packages
- adding package tasks
ms.assetid: 5d4652d5-228c-4238-905c-346dd8503fdf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa61eb2fb87f45fe5b534b96280b8b4e2c21788d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572654"
---
# <a name="adding-tasks-programmatically"></a><span data-ttu-id="23e14-102">Adicionando tarefas programaticamente</span><span class="sxs-lookup"><span data-stu-id="23e14-102">Adding Tasks Programmatically</span></span>
  <span data-ttu-id="23e14-103">As tarefas podem ser adicionadas aos seguintes tipos de objetos no mecanismo de tempo de execução:</span><span class="sxs-lookup"><span data-stu-id="23e14-103">Tasks can be added to the following types of objects in the run-time engine:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Package>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Sequence>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>  
  
 <span data-ttu-id="23e14-104">Essas classes são consideradas contêineres e todas herdam a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A>.</span><span class="sxs-lookup"><span data-stu-id="23e14-104">These classes are considered containers, and they all inherit the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A> property.</span></span> <span data-ttu-id="23e14-105">Os contêineres podem conter uma coleção de tarefas, que são objetos executáveis processados pelo runtime durante a execução do contêiner.</span><span class="sxs-lookup"><span data-stu-id="23e14-105">Containers can contain a collection of tasks, which are executable objects processed by the runtime during execution of the container.</span></span> <span data-ttu-id="23e14-106">A ordem de execução dos objetos na coleção é determinada em qualquer conjunto <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> em cada tarefa dos contêineres.</span><span class="sxs-lookup"><span data-stu-id="23e14-106">The order of execution of the objects in the collection is determined any <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> set on each task in the containers.</span></span> <span data-ttu-id="23e14-107">Restrições de precedência habilitam a ramificação da execução com base no êxito, falha ou conclusão de um <xref:Microsoft.SqlServer.Dts.Runtime.Executable> na coleção.</span><span class="sxs-lookup"><span data-stu-id="23e14-107">Precedence constraints enable execution branching based on the success, failure, or completion of an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> in the collection.</span></span>  
  
 <span data-ttu-id="23e14-108">Cada contêiner tem uma coleção <xref:Microsoft.SqlServer.Dts.Runtime.Executables> que contém os objetos individuais <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="23e14-108">Each container has an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection that contains the individual <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects.</span></span> <span data-ttu-id="23e14-109">Cada tarefa executável herda e implementa os métodos <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="23e14-109">Each executable task inherits and implements the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> method and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> method.</span></span> <span data-ttu-id="23e14-110">Esses dois métodos são chamados pelo mecanismo de tempo de execução para processar cada <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="23e14-110">These two methods are called by the run-time engine to process each <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span></span>  
  
 <span data-ttu-id="23e14-111">Para adicionar uma tarefa a um pacote, você precisa de um contêiner com uma coleção existente <xref:Microsoft.SqlServer.Dts.Runtime.Executables>.</span><span class="sxs-lookup"><span data-stu-id="23e14-111">To add a task to a package, you need a container with an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> existing collection.</span></span> <span data-ttu-id="23e14-112">Em geral, a tarefa a ser adicionada à coleção é um pacote.</span><span class="sxs-lookup"><span data-stu-id="23e14-112">Most of the time, the task that you will add to the collection is a package.</span></span> <span data-ttu-id="23e14-113">Para adicionar o executável da nova tarefa na coleção para esse contêiner, chame o método <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="23e14-113">To add the new task executable into the collection for that container, you call the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method .</span></span> <span data-ttu-id="23e14-114">O método possui um único parâmetro, uma cadeia de caracteres, que contém CLSID, PROGID, o moniker STOCK ou o <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> da tarefa você está adicionando.</span><span class="sxs-lookup"><span data-stu-id="23e14-114">The method has a single parameter, a string, that contains the CLSID, PROGID, STOCK moniker, or <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> of the task you are adding.</span></span>  
  
## <a name="task-names"></a><span data-ttu-id="23e14-115">Nomes de tarefas</span><span class="sxs-lookup"><span data-stu-id="23e14-115">Task Names</span></span>  
 <span data-ttu-id="23e14-116">Embora você possa especificar uma tarefa pelo nome ou pela ID, o moniker `STOCK` é o parâmetro mais usado no método <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="23e14-116">Although you can specify a task by name or by ID, the `STOCK` moniker is the parameter used most often in the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method.</span></span> <span data-ttu-id="23e14-117">Para adicionar uma tarefa a um executável identificado pelo moniker `STOCK`, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="23e14-117">To add a task to an executable identified by the `STOCK` moniker, use the following syntax:</span></span>  
  
```csharp  
Executable exec = package.Executables.Add("STOCK:BulkInsertTask");  
  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add("STOCK:BulkInsertTask")  
  
```  
  
 <span data-ttu-id="23e14-118">A lista a seguir mostra os nomes de cada tarefa que são usados depois do moniker `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="23e14-118">The following list shows the names for each task that are used after the `STOCK` moniker.</span></span>  
  
-   <span data-ttu-id="23e14-119">ActiveXScriptTask</span><span class="sxs-lookup"><span data-stu-id="23e14-119">ActiveXScriptTask</span></span>  
  
-   <span data-ttu-id="23e14-120">BulkInsertTask</span><span class="sxs-lookup"><span data-stu-id="23e14-120">BulkInsertTask</span></span>  
  
-   <span data-ttu-id="23e14-121">ExecuteProcessTask</span><span class="sxs-lookup"><span data-stu-id="23e14-121">ExecuteProcessTask</span></span>  
  
-   <span data-ttu-id="23e14-122">ExecutePackageTask</span><span class="sxs-lookup"><span data-stu-id="23e14-122">ExecutePackageTask</span></span>  
  
-   <span data-ttu-id="23e14-123">Exec80PackageTask</span><span class="sxs-lookup"><span data-stu-id="23e14-123">Exec80PackageTask</span></span>  
  
-   <span data-ttu-id="23e14-124">FileSystemTask</span><span class="sxs-lookup"><span data-stu-id="23e14-124">FileSystemTask</span></span>  
  
-   <span data-ttu-id="23e14-125">FTPTask</span><span class="sxs-lookup"><span data-stu-id="23e14-125">FTPTask</span></span>  
  
-   <span data-ttu-id="23e14-126">MSMQTask</span><span class="sxs-lookup"><span data-stu-id="23e14-126">MSMQTask</span></span>  
  
-   <span data-ttu-id="23e14-127">PipelineTask</span><span class="sxs-lookup"><span data-stu-id="23e14-127">PipelineTask</span></span>  
  
-   <span data-ttu-id="23e14-128">ScriptTask</span><span class="sxs-lookup"><span data-stu-id="23e14-128">ScriptTask</span></span>  
  
-   <span data-ttu-id="23e14-129">SendMailTask</span><span class="sxs-lookup"><span data-stu-id="23e14-129">SendMailTask</span></span>  
  
-   <span data-ttu-id="23e14-130">SQLTask</span><span class="sxs-lookup"><span data-stu-id="23e14-130">SQLTask</span></span>  
  
-   <span data-ttu-id="23e14-131">TransferStoredProceduresTask</span><span class="sxs-lookup"><span data-stu-id="23e14-131">TransferStoredProceduresTask</span></span>  
  
-   <span data-ttu-id="23e14-132">TransferLoginsTask</span><span class="sxs-lookup"><span data-stu-id="23e14-132">TransferLoginsTask</span></span>  
  
-   <span data-ttu-id="23e14-133">TransferErrorMessagesTask</span><span class="sxs-lookup"><span data-stu-id="23e14-133">TransferErrorMessagesTask</span></span>  
  
-   <span data-ttu-id="23e14-134">TransferJobsTask</span><span class="sxs-lookup"><span data-stu-id="23e14-134">TransferJobsTask</span></span>  
  
-   <span data-ttu-id="23e14-135">TransferObjectsTask</span><span class="sxs-lookup"><span data-stu-id="23e14-135">TransferObjectsTask</span></span>  
  
-   <span data-ttu-id="23e14-136">TransferDatabaseTask</span><span class="sxs-lookup"><span data-stu-id="23e14-136">TransferDatabaseTask</span></span>  
  
-   <span data-ttu-id="23e14-137">WebServiceTask</span><span class="sxs-lookup"><span data-stu-id="23e14-137">WebServiceTask</span></span>  
  
-   <span data-ttu-id="23e14-138">WmiDataReaderTask</span><span class="sxs-lookup"><span data-stu-id="23e14-138">WmiDataReaderTask</span></span>  
  
-   <span data-ttu-id="23e14-139">WmiEventWatcherTask</span><span class="sxs-lookup"><span data-stu-id="23e14-139">WmiEventWatcherTask</span></span>  
  
-   <span data-ttu-id="23e14-140">XMLTask</span><span class="sxs-lookup"><span data-stu-id="23e14-140">XMLTask</span></span>  
  
 <span data-ttu-id="23e14-141">Se preferir uma sintaxe mais explícita ou se a tarefa a ser adicionada não possuir um moniker STOCK, você poderá adicionar a tarefa ao executável usando o nome longo.</span><span class="sxs-lookup"><span data-stu-id="23e14-141">If you prefer a more explicit syntax, or if the task that you want to add does not have a STOCK moniker, you can add the task to the executable using its long name.</span></span> <span data-ttu-id="23e14-142">Essa sintaxe requer que você também especifique o número da versão da tarefa.</span><span class="sxs-lookup"><span data-stu-id="23e14-142">This syntax requires that you also specify the version number of the task.</span></span>  
  
```csharp  
Executable exec = package.Executables.Add(  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " +  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " +  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91");  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add( _  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " & _  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " & _  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91")  
```  
  
 <span data-ttu-id="23e14-143">Você pode obter o nome longo para a tarefa programaticamente, sem precisar especificar a versão da tarefa, usando a propriedade **AssemblyQualifiedName** da classe, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="23e14-143">You can obtain the long name for the task programmatically, without having to specify the task version, by using the **AssemblyQualifiedName** property of the class, as shown in the following example.</span></span> <span data-ttu-id="23e14-144">Esse exemplo precisa de uma referência ao assembly Microsoft.SqlServer.SQLTask.</span><span class="sxs-lookup"><span data-stu-id="23e14-144">This example requires a reference to the Microsoft.SqlServer.SQLTask assembly.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask;  
...  
      Executable exec = package.Executables.Add(  
        typeof(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName);  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask  
...  
    Dim exec As Executable = package.Executables.Add( _  
      GetType(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName)  
```  
  
 <span data-ttu-id="23e14-145">O exemplo de código a seguir mostra como criar uma coleção <xref:Microsoft.SqlServer.Dts.Runtime.Executables> a partir de um novo pacote e, depois, adicionar uma tarefa Sistema de Arquivos e uma tarefa Inserção em Massa à coleção, através de seus monikers `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="23e14-145">The following code example shows how to create an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection from a new package, and then add a File System task and a Bulk Insert task to the collection, by using their `STOCK` monikers.</span></span> <span data-ttu-id="23e14-146">Esse exemplo precisa de uma referência aos assemblies Microsoft.SqlServer.FileSystemTask e Microsoft.SqlServer.BulkInsertTask.</span><span class="sxs-lookup"><span data-stu-id="23e14-146">This example requires a reference to the Microsoft.SqlServer.FileSystemTask and Microsoft.SqlServer.BulkInsertTask assemblies.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thBulkInsertTask = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        Console.WriteLine("Type {0}", taskHost.InnerObject.ToString());  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thBulkInsertTask As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      Console.WriteLine("Type {0}", taskHost.InnerObject.ToString())  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="23e14-147">**Saída de exemplo:**</span><span class="sxs-lookup"><span data-stu-id="23e14-147">**Sample Output:**</span></span>  
  
 `Type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
## <a name="taskhost-container"></a><span data-ttu-id="23e14-148">Contêiner TaskHost</span><span class="sxs-lookup"><span data-stu-id="23e14-148">TaskHost Container</span></span>  
 <span data-ttu-id="23e14-149">A classe <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> é um contêiner que não aparece na interface gráfica do usuário, mas é muito importante na programação.</span><span class="sxs-lookup"><span data-stu-id="23e14-149">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class is a container that does not appear in the graphical user interface, but is very important in programming.</span></span> <span data-ttu-id="23e14-150">Essa classe é um wrapper de cada tarefa.</span><span class="sxs-lookup"><span data-stu-id="23e14-150">This class is a wrapper for every task.</span></span> <span data-ttu-id="23e14-151">As tarefas que são adicionadas ao pacote através do método <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> como um objeto <xref:Microsoft.SqlServer.Dts.Runtime.Executable> podem ser convertidas um objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="23e14-151">Tasks that are added to the package by using the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object can be cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object.</span></span> <span data-ttu-id="23e14-152">Quando uma tarefa é convertida como um <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, você pode usar propriedades e métodos adicionais na tarefa.</span><span class="sxs-lookup"><span data-stu-id="23e14-152">When a task is cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, you can use additional properties and methods on the task.</span></span> <span data-ttu-id="23e14-153">Além disso, a própria tarefa pode ser acessada através da propriedade <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="23e14-153">Also, the task itself can be accessed through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="23e14-154">Dependendo das suas necessidades, você pode optar por manter a tarefa como um objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> para poder usar as propriedades da tarefa através da coleção <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="23e14-154">Depending on your needs, you may decide to keep the task as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object so that you can use the properties of the task through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection.</span></span> <span data-ttu-id="23e14-155">A vantagem de usar o <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> é que você pode escrever mais códigos genéricos.</span><span class="sxs-lookup"><span data-stu-id="23e14-155">The advantage of using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> is that you can write more generic code.</span></span> <span data-ttu-id="23e14-156">Se precisar de código muito específico para uma tarefa, converta a tarefa para seu objeto apropriado.</span><span class="sxs-lookup"><span data-stu-id="23e14-156">If you need very specific code for a task, then you should cast the task to its appropriate object.</span></span>  
  
 <span data-ttu-id="23e14-157">O exemplo de código a seguir mostra como converter um <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, que contém um <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>em um objeto <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>.</span><span class="sxs-lookup"><span data-stu-id="23e14-157">The following code example shows how to cast a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, that contains a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> object.</span></span>  
  
```csharp  
BulkInsertTask myTask = thBulkInsertTask.InnerObject as BulkInsertTask;  
```  
  
```vb  
Dim myTask As BulkInsertTask = CType(thBulkInsertTask.InnerObject, BulkInsertTask)  
```  
  
 <span data-ttu-id="23e14-158">O exemplo de código a seguir mostra como converter o executável em um <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, e depois usar a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> para determinar que tipo de executável está contido no host.</span><span class="sxs-lookup"><span data-stu-id="23e14-158">The following code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property to determine which type of executable is contained by the host.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask1 = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thFileSystemTask2 = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask)  
        {  
          // Do work with FileSystemTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        else if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask)  
        {  
          // Do work with BulkInsertTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        // Add additional statements to check InnerObject, if desired.  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask1 As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thFileSystemTask2 As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      If TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask Then  
        ' Do work with FileSystemTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      ElseIf TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask Then  
        ' Do work with BulkInsertTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      End If  
      ' Add additional statements to check InnerObject, if desired.  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="23e14-159">**Saída de exemplo:**</span><span class="sxs-lookup"><span data-stu-id="23e14-159">**Sample Output:**</span></span>  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
 <span data-ttu-id="23e14-160">A instrução <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> retorna um executável que é convertido em um objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> do objeto <xref:Microsoft.SqlServer.Dts.Runtime.Executable> recém-criado.</span><span class="sxs-lookup"><span data-stu-id="23e14-160">The <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> statement returns an executable that is cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object from the newly created <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object.</span></span>  
  
 <span data-ttu-id="23e14-161">Para definir propriedades ou chamar métodos no objeto novo, você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="23e14-161">To set properties or to call methods on the new object, you have two options:</span></span>  
  
1.  <span data-ttu-id="23e14-162">Use a coleção <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="23e14-162">Use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="23e14-163">Por exemplo, para obter uma propriedade do objeto, use `th.Properties["propertyname"].GetValue(th))`.</span><span class="sxs-lookup"><span data-stu-id="23e14-163">For example, to obtain a property from the object, use `th.Properties["propertyname"].GetValue(th))`.</span></span> <span data-ttu-id="23e14-164">Para definir uma propriedade, use `th.Properties["propertyname"].SetValue(th, <value>);`.</span><span class="sxs-lookup"><span data-stu-id="23e14-164">To set a property, use `th.Properties["propertyname"].SetValue(th, <value>);`.</span></span>  
  
2.  <span data-ttu-id="23e14-165">Converta o <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> na classe de tarefa.</span><span class="sxs-lookup"><span data-stu-id="23e14-165">Cast the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task class.</span></span> <span data-ttu-id="23e14-166">Por exemplo, para converter a tarefa Inserção em Massa em um <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> depois de sua adição a um pacote como um <xref:Microsoft.SqlServer.Dts.Runtime.Executable> e, subsequentemente, converter em um <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, use `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span><span class="sxs-lookup"><span data-stu-id="23e14-166">For example, to cast the Bulk Insert task to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> after it has been added to a package as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> and subsequently cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, use `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span></span>  
  
 <span data-ttu-id="23e14-167">O uso da classe <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> em código, em vez de sua conversão na classe específica da tarefa apresenta as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="23e14-167">Using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class in code, instead of casting to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="23e14-168">O provedor <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> não precisa de uma referência ao assembly no código.</span><span class="sxs-lookup"><span data-stu-id="23e14-168">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> provider does not require a reference to the assembly in the code.</span></span>  
  
-   <span data-ttu-id="23e14-169">Você pode criar rotinas com código genérico que funcionam para qualquer tarefa, pois você não precisa saber o nome da tarefa no momento de compilação.</span><span class="sxs-lookup"><span data-stu-id="23e14-169">You can code generic routines that work for any task, because you do not have to know the name of the task at compile time.</span></span> <span data-ttu-id="23e14-170">Tais rotinas genéricas incluem métodos onde você transmite o nome da tarefa para o método; o código do método funciona para todas as tarefas.</span><span class="sxs-lookup"><span data-stu-id="23e14-170">Such generic routines include methods where you pass in the name of the task to the method, and the method code works for all tasks.</span></span> <span data-ttu-id="23e14-171">Esse é um método bom para escrever código de teste.</span><span class="sxs-lookup"><span data-stu-id="23e14-171">This is a good method for writing test code.</span></span>  
  
 <span data-ttu-id="23e14-172">A conversão do <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> na classe específica de tarefa apresenta as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="23e14-172">Casting from the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="23e14-173">O projeto do Visual Studio oferece conclusão de instrução (IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="23e14-173">The Visual Studio project gives you statement completion (IntelliSense).</span></span>  
  
-   <span data-ttu-id="23e14-174">O código pode ser executado mais rápido.</span><span class="sxs-lookup"><span data-stu-id="23e14-174">The code may run faster.</span></span>  
  
-   <span data-ttu-id="23e14-175">Objetos específicos da tarefa permitem associação inicial e as otimizações resultantes.</span><span class="sxs-lookup"><span data-stu-id="23e14-175">Task-specific objects enable early binding and the resulting optimizations.</span></span> <span data-ttu-id="23e14-176">Para obter mais informações sobre associações iniciais e tardias, consulte o tópico "Early and Late Binding" no Visual Basic Language Concepts.</span><span class="sxs-lookup"><span data-stu-id="23e14-176">For more information about early and late binding, see the topic "Early and Late Binding" in Visual Basic Language Concepts.</span></span>  
  
 <span data-ttu-id="23e14-177">O exemplo de código a seguir expande o conceito de reutilização do código de tarefa.</span><span class="sxs-lookup"><span data-stu-id="23e14-177">The following code example expands on the concept of reusing task code.</span></span> <span data-ttu-id="23e14-178">Em vez de converter tarefas nos equivalentes de sua classe específica, o exemplo de código mostra como converter o executável em um <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, e depois usa o <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> para escrever o código genérico em relação a todas as tarefas.</span><span class="sxs-lookup"><span data-stu-id="23e14-178">Instead of casting tasks to their specific class equivalents, the code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then uses the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> to write generic code against all the tasks.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
  
      string[] tasks = { "STOCK:SQLTask", "STOCK:ScriptTask",   
        "STOCK:ExecuteProcessTask", "STOCK:PipelineTask",   
        "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask" };  
  
      foreach (string s in tasks)  
      {  
        TaskHost taskhost = package.Executables.Add(s) as TaskHost;  
        DtsProperties props = taskhost.Properties;  
        Console.WriteLine("Enumerating properties on " + taskhost.Name);  
        Console.WriteLine(" TaskHost.InnerObject is " + taskhost.InnerObject.ToString());  
        Console.WriteLine();  
  
        foreach (DtsProperty prop in props)  
        {  
          Console.WriteLine("Properties for " + prop.Name);  
          Console.WriteLine("Name : " + prop.Name);  
          Console.WriteLine("Type : " + prop.Type.ToString());  
          Console.WriteLine("Readable : " + prop.Get.ToString());  
          Console.WriteLine("Writable : " + prop.Set.ToString());  
          Console.WriteLine();  
        }  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package = New Package()  
  
    Dim tasks() As String = New String() {"STOCK:SQLTask", "STOCK:ScriptTask", _  
              "STOCK:ExecuteProcessTask", "STOCK:PipelineTask", _  
              "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask"}  
  
    For Each s As String In tasks  
  
      Dim taskhost As TaskHost = CType(package.Executables.Add(s), TaskHost)  
      Dim props As DtsProperties = taskhost.Properties  
      Console.WriteLine("Enumerating properties on " & taskhost.Name)  
      Console.WriteLine(" TaskHost.InnerObject is " & taskhost.InnerObject.ToString())  
      Console.WriteLine()  
  
      For Each prop As DtsProperty In props  
        Console.WriteLine("Properties for " + prop.Name)  
        Console.WriteLine(" Name : " + prop.Name)  
        Console.WriteLine(" Type : " + prop.Type.ToString())  
        Console.WriteLine(" Readable : " + prop.Get.ToString())  
        Console.WriteLine(" Writable : " + prop.Set.ToString())  
        Console.WriteLine()  
      Next  
  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="23e14-179">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="23e14-179">External Resources</span></span>  
 <span data-ttu-id="23e14-180">Entrada no blog, [EzAPI – Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) (EzAPI – atualizado para o SQL Server 2012) em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="23e14-180">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="23e14-181">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="23e14-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="23e14-182">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="23e14-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="23e14-183">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="23e14-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="23e14-184">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="23e14-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e14-185">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23e14-185">See Also</span></span>  
 [<span data-ttu-id="23e14-186">Conectando tarefas programaticamente</span><span class="sxs-lookup"><span data-stu-id="23e14-186">Connecting Tasks Programmatically</span></span>](../building-packages-programmatically/connecting-tasks-programmatically.md)  
  
  
