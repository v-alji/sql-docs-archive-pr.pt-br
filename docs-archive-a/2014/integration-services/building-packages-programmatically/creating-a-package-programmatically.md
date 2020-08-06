---
title: Criar um pacote programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SSIS packages, creating
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
ms.assetid: e44bcc70-32d3-43e8-a84b-29aef819d5d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1159784fc95dd86d9d33c4354291cc7c52812982
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680603"
---
# <a name="creating-a-package-programmatically"></a><span data-ttu-id="95659-102">Criando um pacote programaticamente</span><span class="sxs-lookup"><span data-stu-id="95659-102">Creating a Package Programmatically</span></span>
  <span data-ttu-id="95659-103">O objeto <xref:Microsoft.SqlServer.Dts.Runtime.Package> é o contêiner de alto nível para todos os outros objetos em uma solução de projeto do [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95659-103">The <xref:Microsoft.SqlServer.Dts.Runtime.Package> object is the top-level container for all other objects in an [!INCLUDE[ssIS](../../includes/ssis-md.md)] project solution.</span></span> <span data-ttu-id="95659-104">Como contêiner de alto nível, o pacote é o primeiro objeto criado, e os objetos subsequentes são adicionados a ele e executados dentro do contexto do pacote.</span><span class="sxs-lookup"><span data-stu-id="95659-104">As the top-level container, the package is the first object created, and subsequent objects are added to it, and then executed within the context of the package.</span></span> <span data-ttu-id="95659-105">O próprio pacote não move nem transforma dados.</span><span class="sxs-lookup"><span data-stu-id="95659-105">The package itself does not move or transform data.</span></span> <span data-ttu-id="95659-106">O pacote confia nas tarefas que contém para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="95659-106">The package relies on the tasks it contains to perform the work.</span></span> <span data-ttu-id="95659-107">As tarefas executam a maioria do trabalho executado por um pacote e definem a funcionalidade de um pacote.</span><span class="sxs-lookup"><span data-stu-id="95659-107">Tasks perform most of the work performed by a package, and define the functionality of a package.</span></span> <span data-ttu-id="95659-108">Um pacote é criado e executado com apenas três linhas de código, mas várias tarefas e objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> são adicionados para acrescentar funcionalidades ao seu pacote.</span><span class="sxs-lookup"><span data-stu-id="95659-108">A package is created and executed with just three lines of code, but various tasks and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects are added to give additional functionality to your package.</span></span> <span data-ttu-id="95659-109">Esta seção discute como criar um pacote programaticamente.</span><span class="sxs-lookup"><span data-stu-id="95659-109">This section discusses how to programmatically create a package.</span></span> <span data-ttu-id="95659-110">Ela não fornece informações sobre como criar as tarefas ou o <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="95659-110">It does not provide information about how to create the tasks or the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span> <span data-ttu-id="95659-111">Essas informações são discutidas em seções posteriores.</span><span class="sxs-lookup"><span data-stu-id="95659-111">These are covered in later sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95659-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="95659-112">Example</span></span>  
 <span data-ttu-id="95659-113">Para gravar um código usando o ambiente de desenvolvimento integrado (IDE) do Visual Studio, uma referência ao Microsoft.SqlServer.ManagedDTS.DLL é necessária para criar uma instrução `using` (`Imports` no Visual Basic .NET) para o Microsoft.SqlServer.Dts.Runtime.</span><span class="sxs-lookup"><span data-stu-id="95659-113">To write code using the Visual Studio IDE, a reference to Microsoft.SqlServer.ManagedDTS.DLL is required in order to create a `using` statement (`Imports` in Visual Basic .NET) to the Microsoft.SqlServer.Dts.Runtime.</span></span> <span data-ttu-id="95659-114">O exemplo de código seguinte demonstra como criar um pacote vazio.</span><span class="sxs-lookup"><span data-stu-id="95659-114">The following code sample demonstrates creating an empty package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package;  
      package = new Package();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package  
    package = New Package  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="95659-115">Para compilar e executar o exemplo, pressione F5 no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="95659-115">To compile and run the sample, press F5 in Visual Studio.</span></span> <span data-ttu-id="95659-116">Para implementar o código usando o compilador C#, **csc.exe**, no prompt de comando para compilar, use as referências a seguir de comando e arquivo, substituindo o *\<filename>* pelo nome do arquivo .cs ou .vb, e dando a ele um *\<outputfilename>* de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="95659-116">To build the code using the C# compiler, **csc.exe**, at the command prompt to compile, use the following command and file references, replacing the *\<filename>* with the name of the .cs or .vb file, and giving it an *\<outputfilename>* of your choice.</span></span>  
  
 <span data-ttu-id="95659-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="95659-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="95659-118">Para compilar o código usando o compilador do Visual Basic .NET, **vbc.exe**, no prompt de comando para compilar, use o comando e as referências de arquivo a seguir.</span><span class="sxs-lookup"><span data-stu-id="95659-118">To build the code using the Visual Basic .NET compiler, **vbc.exe**, at the command prompt to compile, use the following command and file references.</span></span>  
  
 <span data-ttu-id="95659-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="95659-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="95659-120">Você também pode criar um pacote carregando um pacote existente que foi salvo em disco, no sistema de arquivos, ou no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95659-120">You can also create a package by loading an existing package that was saved on disk, in the file system, or to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="95659-121">A diferença é que o objeto <xref:Microsoft.SqlServer.Dts.Runtime.Application> é criado primeiro e depois o objeto do pacote é preenchido por um dos métodos sobrecarregados do aplicativo: `LoadPackage` para arquivos simples, `LoadFromSQLServer` para pacotes salvos no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> para pacotes salvos no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="95659-121">The difference is that the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object is first created, and then the package object is filled by one of the Application's overloaded methods: `LoadPackage` for flat files, `LoadFromSQLServer` for packages saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> for packages saved to the file system.</span></span> <span data-ttu-id="95659-122">O exemplo seguinte carrega um pacote existente do disco e exibe várias propriedades no pacote.</span><span class="sxs-lookup"><span data-stu-id="95659-122">The following example loads an existing package from disk, and then views several properties on the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class ApplicationTests  
  {  
    static void Main(string[] args)  
    {  
      // The variable pkg points to the location of the  
      // ExecuteProcess package sample that was installed with  
      // the SSIS samples.  
      string pkg = @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx";  
  
      Application app = new Application();  
      Package p = app.LoadPackage(pkg, null);  
  
      // Now that the package is loaded, we can query on  
      // its properties.  
      int n = p.Configurations.Count;  
      DtsProperty p2 = p.Properties["VersionGUID"];  
      DTSProtectionLevel pl = p.ProtectionLevel;  
  
      Console.WriteLine("Number of configurations = " + n.ToString());  
      Console.WriteLine("VersionGUID = " + (string)p2.GetValue(p));  
      Console.WriteLine("ProtectionLevel = " + pl.ToString());  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module ApplicationTests  
  
  Sub Main()  
  
    ' The variable pkg points to the location of the  
    ' ExecuteProcess package sample that was installed with  
    ' the SSIS samples.  
    Dim pkg As String = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx"  
  
    Dim app As Application = New Application()  
    Dim p As Package = app.LoadPackage(pkg, Nothing)  
  
    ' Now that the package is loaded, we can query on  
    ' its properties.  
    Dim n As Integer = p.Configurations.Count  
    Dim p2 As DtsProperty = p.Properties("VersionGUID")  
    Dim pl As DTSProtectionLevel = p.ProtectionLevel  
  
    Console.WriteLine("Number of configurations = " & n.ToString())  
    Console.WriteLine("VersionGUID = " & CType(p2.GetValue(p), String))  
    Console.WriteLine("ProtectionLevel = " & pl.ToString())  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="95659-123">**Saída de exemplo:**</span><span class="sxs-lookup"><span data-stu-id="95659-123">**Sample Output:**</span></span>  
  
 `Number of configurations = 2`  
  
 `VersionGUID = {09016682-89B8-4406-AAC9-AF1E527FF50F}`  
  
 `ProtectionLevel = DontSaveSensitive`  
  
## <a name="external-resources"></a><span data-ttu-id="95659-124">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="95659-124">External Resources</span></span>  
  
-   <span data-ttu-id="95659-125">Entrada de blog, [API Sample – OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), (Amostra de API – origem e destino de OleDB) em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="95659-125">Blog entry, [API Sample - OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), on blogs.msdn.com.</span></span>  
  
-   <span data-ttu-id="95659-126">Entrada no blog, [EzAPI – Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) (EzAPI – atualizado para o SQL Server 2012) em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="95659-126">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="95659-127">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="95659-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="95659-128">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="95659-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="95659-129">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="95659-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="95659-130">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="95659-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95659-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95659-131">See Also</span></span>  
 [<span data-ttu-id="95659-132">Adicionar tarefas programaticamente</span><span class="sxs-lookup"><span data-stu-id="95659-132">Adding Tasks Programmatically</span></span>](../building-packages-programmatically/adding-tasks-programmatically.md)  
  
  
