---
title: Criando, alterando e removendo padrões | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- defaults [SMO]
ms.assetid: c30ac3b9-8150-4264-ba4c-c549f44261ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: 747f7ff60122c5265cd68060063946a3e22d0301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684635"
---
# <a name="creating-altering-and-removing-defaults"></a><span data-ttu-id="e599d-102">Criando, alterando e removendo padrões</span><span class="sxs-lookup"><span data-stu-id="e599d-102">Creating, Altering, and Removing Defaults</span></span>
  <span data-ttu-id="e599d-103">No [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), a restrição padrão é representada pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Default>.</span><span class="sxs-lookup"><span data-stu-id="e599d-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), the default constraint is represented by the <xref:Microsoft.SqlServer.Management.Smo.Default> object.</span></span>  
  
 <span data-ttu-id="e599d-104">A propriedade <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Default> é usada para definir o valor a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="e599d-104">The <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Default> object is used to set the value to be inserted.</span></span> <span data-ttu-id="e599d-105">Ela pode ser uma constante ou uma instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] que retorna um valor constante, como GETDATE().</span><span class="sxs-lookup"><span data-stu-id="e599d-105">This can be a constant or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement that returns a constant value, such as GETDATE().</span></span> <span data-ttu-id="e599d-106">A propriedade <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> não pode ser modificada usando o método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="e599d-106">The <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property cannot be modified by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="e599d-107">Em vez disso, o objeto <xref:Microsoft.SqlServer.Management.Smo.Default> deve ser descartado e recriado.</span><span class="sxs-lookup"><span data-stu-id="e599d-107">Instead, the <xref:Microsoft.SqlServer.Management.Smo.Default> object must be dropped and re-created.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e599d-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e599d-108">Example</span></span>  
 <span data-ttu-id="e599d-109">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e599d-109">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="e599d-110">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="e599d-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-default-in-visual-basic"></a><span data-ttu-id="e599d-111">Criando, alterando e removendo um padrão no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e599d-111">Creating, Altering, and Removing a Default in Visual Basic</span></span>  
 <span data-ttu-id="e599d-112">Este exemplo de código mostra como criar um padrão que seja texto simples e outro padrão que seja uma instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e599d-112">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="e599d-113">O padrão deve ser anexado à coluna através do método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> e desanexado através do método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="e599d-113">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaults1](SMO How to#SMO_VBDefaults1)]  -->  
  
## <a name="creating-altering-and-removing-a-default-in-visual-c"></a><span data-ttu-id="e599d-114">Criando, alterando e removendo um padrão no Visual C#</span><span class="sxs-lookup"><span data-stu-id="e599d-114">Creating, Altering, and Removing a Default in Visual C#</span></span>  
 <span data-ttu-id="e599d-115">Este exemplo de código mostra como criar um padrão que seja texto simples e outro padrão que seja uma instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e599d-115">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="e599d-116">O padrão deve ser anexado à coluna através do método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> e desanexado através do método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="e599d-116">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
```csharp
{
          Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database  db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Default object variable by supplying the parent database and the default name   
            //in the constructor.   
            Default def = new Default(db, "Test_Default2");  
  
            //Set the TextHeader and TextBody properties that define the default.   
            def.TextHeader = "CREATE DEFAULT [Test_Default2] AS";  
            def.TextBody = "GetDate()";  
  
            //Create the default on the instance of SQL Server.   
            def.Create();  
  
            //Bind the default to a column in a table in AdventureWorks2012  
            def.BindToColumn("SpecialOffer", "StartDate", "Sales");  
  
            //Unbind the default from the column and remove it from the database.   
            def.UnbindFromColumn("SpecialOffer", "StartDate", "Sales");  
            def.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-default-in-powershell"></a><span data-ttu-id="e599d-117">Criando, alterando e removendo um padrão no PowerShell</span><span class="sxs-lookup"><span data-stu-id="e599d-117">Creating, Altering, and Removing a Default in PowerShell</span></span>  
 <span data-ttu-id="e599d-118">Este exemplo de código mostra como criar um padrão que seja texto simples e outro padrão que seja uma instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e599d-118">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="e599d-119">O padrão deve ser anexado à coluna através do método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> e desanexado através do método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="e599d-119">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
#Define a Default object variable by supplying the parent database and the default name in the constructor.  
$def = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Default `  
-argumentlist $db, "Test_Default2"  
  
#Set the TextHeader and TextBody properties that define the default.   
$def.TextHeader = "CREATE DEFAULT [Test_Default2] AS"  
$def.TextBody = "GetDate()"  
  
#Create the default on the instance of SQL Server.   
$def.Create()  
  
#Bind the default to the column.   
$def.BindToColumn("SpecialOffer", "StartDate", "Sales")  
  
#Unbind the default from the column and remove it from the database.   
$def.UnbindFromColumn("SpecialOffer", "StartDate", "Sales")  
$def.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e599d-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e599d-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Default>  
