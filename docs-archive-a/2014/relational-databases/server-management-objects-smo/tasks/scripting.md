---
title: Scripts | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- dependencies [SMO]
- scripts [SMO]
ms.assetid: 13a35511-3987-426b-a3b7-3b2e83900dc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: bf46798597de021976cefa943a17500e773f9274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680862"
---
# <a name="scripting"></a><span data-ttu-id="5aa20-102">Scripting</span><span class="sxs-lookup"><span data-stu-id="5aa20-102">Scripting</span></span>
  <span data-ttu-id="5aa20-103">A geração de scripts no SMO é controlada pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Scripter> e seus objetos filho ou pelo método `Script` em objetos individuais.</span><span class="sxs-lookup"><span data-stu-id="5aa20-103">Scripting in SMO is controlled by the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects, or the `Script` method on individual objects.</span></span> <span data-ttu-id="5aa20-104">O <xref:Microsoft.SqlServer.Management.Smo.Scripter> objeto controla o mapeamento fora das relações de dependência para objetos em uma instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5aa20-104">The <xref:Microsoft.SqlServer.Management.Smo.Scripter> object controls the mapping out of dependency relationships for objects on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5aa20-105">A geração de scripts avançada usando o objeto <xref:Microsoft.SqlServer.Management.Smo.Scripter> e seus objetos filhos é um processo trifásico:</span><span class="sxs-lookup"><span data-stu-id="5aa20-105">Advanced scripting by using the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects is a three phase process:</span></span>  
  
1.  <span data-ttu-id="5aa20-106">Descoberta</span><span class="sxs-lookup"><span data-stu-id="5aa20-106">Discovery</span></span>  
  
2.  <span data-ttu-id="5aa20-107">Geração de lista</span><span class="sxs-lookup"><span data-stu-id="5aa20-107">List generation</span></span>  
  
3.  <span data-ttu-id="5aa20-108">Geração de scripts</span><span class="sxs-lookup"><span data-stu-id="5aa20-108">Script generation</span></span>  
  
 <span data-ttu-id="5aa20-109">A fase de descoberta usa o objeto <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker>.</span><span class="sxs-lookup"><span data-stu-id="5aa20-109">The discovery phase uses the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object.</span></span> <span data-ttu-id="5aa20-110">Dada uma lista de URNs de objetos, o método <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> retorna um objeto <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> para os objetos na lista de URNs.</span><span class="sxs-lookup"><span data-stu-id="5aa20-110">Given an URN list of objects, the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object returns a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object for the objects in the URN list.</span></span> <span data-ttu-id="5aa20-111">O parâmetro booliano *fParents* é usado para selecionar se os pais ou filhos do objeto especificado devem ser descobertos.</span><span class="sxs-lookup"><span data-stu-id="5aa20-111">The Boolean *fParents* parameter is used to select whether the parents or the children of the specified object are to be discovered.</span></span> <span data-ttu-id="5aa20-112">A árvore de dependência pode ser modificada nesta fase.</span><span class="sxs-lookup"><span data-stu-id="5aa20-112">The dependency tree can be modified at this stage.</span></span>  
  
 <span data-ttu-id="5aa20-113">Na fase de geração de lista, a árvore é transmitida e a lista resultante é retornada.</span><span class="sxs-lookup"><span data-stu-id="5aa20-113">In the list generation phase, the tree is passed in and the resulting list is returned.</span></span> <span data-ttu-id="5aa20-114">Essa lista de objetos está em ordem de scripts e pode ser manipulada.</span><span class="sxs-lookup"><span data-stu-id="5aa20-114">This object list is in scripting order and can be manipulated.</span></span>  
  
 <span data-ttu-id="5aa20-115">As fases da geração de lista usam o método <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> para retornar um <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span><span class="sxs-lookup"><span data-stu-id="5aa20-115">The list generation phases use the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> method to return a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span></span> <span data-ttu-id="5aa20-116">O <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> pode ser modificado nesta fase.</span><span class="sxs-lookup"><span data-stu-id="5aa20-116">The <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> can be modified at this stage.</span></span>  
  
 <span data-ttu-id="5aa20-117">Na terceira e última fases, um script é gerado com a lista especificada e opções de script.</span><span class="sxs-lookup"><span data-stu-id="5aa20-117">In the third and final phase, a script is generated with the specified list and scripting options.</span></span> <span data-ttu-id="5aa20-118">O resultado é retornado como um objeto do sistema <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="5aa20-118">The result is returned as a <xref:System.Collections.Specialized.StringCollection> system object.</span></span> <span data-ttu-id="5aa20-119">Nesta fase, os nomes de objetos dependentes são extraídos da coleção de itens do objeto <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> e de propriedades tais como <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> e <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="5aa20-119">In this phase the dependent object names are then extracted from the Items collection of the <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object and properties such as <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> and <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5aa20-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5aa20-120">Example</span></span>  
 <span data-ttu-id="5aa20-121">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5aa20-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="5aa20-122">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="5aa20-122">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="5aa20-123">Este exemplo de código exige uma instrução `Imports` para o namespace System.Collections.Specialized.</span><span class="sxs-lookup"><span data-stu-id="5aa20-123">This code example requires an `Imports` statement for the System.Collections.Specialized namespace.</span></span> <span data-ttu-id="5aa20-124">Insira isto junto com as outras instruções Imports, antes de qualquer declaração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5aa20-124">Insert this with the other Imports statements, before any declarations in the application.</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
Imports System.Collections.Specialized  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-basic"></a><span data-ttu-id="5aa20-125">Gerando scripts das dependências para um banco de dados no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5aa20-125">Scripting Out the Dependencies for a Database in Visual Basic</span></span>  
 <span data-ttu-id="5aa20-126">Este exemplo de código mostra como descobrir as dependências e iterar pela lista para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="5aa20-126">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
  
Public Class A  
   Public Shared Sub Main()  
      ' database name  
      Dim dbName As [String] = "AdventureWorksLT2012"   ' database name  
  
      ' Connect to the local, default instance of SQL Server.   
      Dim srv As New Server()  
  
      ' Reference the database.    
      Dim db As Database = srv.Databases(dbName)  
  
      ' Define a Scripter object and set the required scripting options.   
      Dim scrp As New Scripter(srv)  
      scrp.Options.ScriptDrops = False  
      scrp.Options.WithDependencies = True  
      scrp.Options.Indexes = True   ' To include indexes  
      scrp.Options.DriAllConstraints = True   ' to include referential constraints in the script  
  
      ' Iterate through the tables in database and script each one. Display the script.  
      For Each tb As Table In db.Tables  
         ' check if the table is not a system table  
         If tb.IsSystemObject = False Then  
            Console.WriteLine("-- Scripting for table " + tb.Name)  
  
            ' Generating script for table tb  
            Dim sc As System.Collections.Specialized.StringCollection = scrp.Script(New Urn() {tb.Urn})  
            For Each st As String In sc  
               Console.WriteLine(st)  
            Next  
            Console.WriteLine("--")  
         End If  
      Next  
   End Sub  
End Class  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-c"></a><span data-ttu-id="5aa20-127">Gerando scripts das dependências para um banco de dados no Visual C#</span><span class="sxs-lookup"><span data-stu-id="5aa20-127">Scripting Out the Dependencies for a Database in Visual C#</span></span>  
 <span data-ttu-id="5aa20-128">Este exemplo de código mostra como descobrir as dependências e iterar pela lista para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="5aa20-128">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
  
public class A {  
   public static void Main() {   
      String dbName = "AdventureWorksLT2012"; // database name  
  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
  
      // Reference the database.    
      Database db = srv.Databases[dbName];  
  
      // Define a Scripter object and set the required scripting options.   
      Scripter scrp = new Scripter(srv);  
      scrp.Options.ScriptDrops = false;  
      scrp.Options.WithDependencies = true;  
      scrp.Options.Indexes = true;   // To include indexes  
      scrp.Options.DriAllConstraints = true;   // to include referential constraints in the script  
  
      // Iterate through the tables in database and script each one. Display the script.     
      foreach (Table tb in db.Tables) {   
         // check if the table is not a system table  
         if (tb.IsSystemObject == false) {  
            Console.WriteLine("-- Scripting for table " + tb.Name);  
  
            // Generating script for table tb  
            System.Collections.Specialized.StringCollection sc = scrp.Script(new Urn[]{tb.Urn});  
            foreach (string st in sc) {  
               Console.WriteLine(st);  
            }  
            Console.WriteLine("--");  
         }  
      }   
   }  
}  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-powershell"></a><span data-ttu-id="5aa20-129">Gerando scripts das dependências para um banco de dados no PowerShell</span><span class="sxs-lookup"><span data-stu-id="5aa20-129">Scripting Out the Dependencies for a Database in PowerShell</span></span>  
 <span data-ttu-id="5aa20-130">Este exemplo de código mostra como descobrir as dependências e iterar pela lista para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="5aa20-130">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
# Create a Scripter object and set the required scripting options.  
$scrp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Scripter -ArgumentList (Get-Item .)  
$scrp.Options.ScriptDrops = $false  
$scrp.Options.WithDependencies = $true  
$scrp.Options.IncludeIfNotExists = $true  
  
# Set the path context to the tables in AdventureWorks2012.  
CD Databases\AdventureWorks2012\Tables  
  
foreach ($Item in Get-ChildItem)  
 {    
 $scrp.Script($Item)  
 }  
```  
