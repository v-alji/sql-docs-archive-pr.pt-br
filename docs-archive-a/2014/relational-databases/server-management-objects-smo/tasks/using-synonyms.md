---
title: Usando sinônimos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- synonyms [SMO]
ms.assetid: db0a9022-9549-43e5-b6b3-deb236f05fb8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5e8416dc3daea3b173fae92e5454a8a65c399e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583456"
---
# <a name="using-synonyms"></a><span data-ttu-id="bf59f-102">Usando sinônimos</span><span class="sxs-lookup"><span data-stu-id="bf59f-102">Using Synonyms</span></span>
  <span data-ttu-id="bf59f-103">Um sinônimo é um nome alternativo de um objeto com escopo de esquema.</span><span class="sxs-lookup"><span data-stu-id="bf59f-103">A synonym is an alternative name for a schema-scoped object.</span></span> <span data-ttu-id="bf59f-104">No SMO, os sinônimos são representados pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Synonym>.</span><span class="sxs-lookup"><span data-stu-id="bf59f-104">In SMO, synonyms are represented by the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object.</span></span> <span data-ttu-id="bf59f-105">O objeto <xref:Microsoft.SqlServer.Management.Smo.Synonym> é um filho do objeto <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="bf59f-105">The <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is a child of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span> <span data-ttu-id="bf59f-106">Isso significa que sinônimos só são válidos dentro do escopo do banco de dados no qual eles são definidos.</span><span class="sxs-lookup"><span data-stu-id="bf59f-106">This means that synonyms are valid only within the scope of the database in which they are defined.</span></span> <span data-ttu-id="bf59f-107">Porém, o sinônimo pode se referir a objetos em outro banco de dados, ou em uma instância remota do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf59f-107">However, the synonym can refer to objects on another database, or on a remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bf59f-108">O objeto que recebe um nome alternativo é conhecido como o objeto base.</span><span class="sxs-lookup"><span data-stu-id="bf59f-108">The object that is given an alternative name is known as the base object.</span></span> <span data-ttu-id="bf59f-109">A propriedade do nome do objeto <xref:Microsoft.SqlServer.Management.Smo.Synonym> é o nome alternativo fornecido ao objeto base.</span><span class="sxs-lookup"><span data-stu-id="bf59f-109">The name property of the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is the alternative name given to the base object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf59f-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bf59f-110">Example</span></span>  
 <span data-ttu-id="bf59f-111">Para o exemplo de código a seguir, selecione o ambiente de programação, o modelo de programação e a linguagem de programação para criar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bf59f-111">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="bf59f-112">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="bf59f-112">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-synonym-in-visual-basic"></a><span data-ttu-id="bf59f-113">Criando um sinônimo no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf59f-113">Creating a Synonym in Visual Basic</span></span>  
 <span data-ttu-id="bf59f-114">O exemplo de código mostra como criar um sinônimo ou um nome alternativo para um objeto com escopo de esquema.</span><span class="sxs-lookup"><span data-stu-id="bf59f-114">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="bf59f-115">Aplicativos cliente podem usar uma única referência para o objeto base através de um sinônimo, em vez de usar um nome com várias partes para fazer referência ao objeto base.</span><span class="sxs-lookup"><span data-stu-id="bf59f-115">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBSynonyms1](SMO How to#SMO_VBSynonyms1)]  -->  
  
## <a name="creating-a-synonym-in-visual-c"></a><span data-ttu-id="bf59f-116">Criando um sinônimo no Visual C#</span><span class="sxs-lookup"><span data-stu-id="bf59f-116">Creating a Synonym in Visual C#</span></span>  
 <span data-ttu-id="bf59f-117">O exemplo de código mostra como criar um sinônimo ou um nome alternativo para um objeto com escopo de esquema.</span><span class="sxs-lookup"><span data-stu-id="bf59f-117">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="bf59f-118">Aplicativos cliente podem usar uma única referência para o objeto base através de um sinônimo, em vez de usar um nome com várias partes para fazer referência ao objeto base.</span><span class="sxs-lookup"><span data-stu-id="bf59f-118">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Synonym object variable by supplying the   
            //parent database, name, and schema arguments in the constructor.   
            //The name is also a synonym of the name of the base object.   
            Synonym syn = new Synonym(db, "Shop", "Sales");  
  
            //Specify the base object, which is the object on which   
            //the synonym is based.   
            syn.BaseDatabase = "AdventureWorks2012";  
            syn.BaseSchema = "Sales";  
            syn.BaseObject = "Store";  
            syn.BaseServer = srv.Name;  
  
            //Create the synonym on the instance of SQL Server.   
            syn.Create();  
        }  
```  
  
## <a name="creating-a-synonym-in-powershell"></a><span data-ttu-id="bf59f-119">Criando um sinônimo no PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf59f-119">Creating a Synonym in PowerShell</span></span>  
 <span data-ttu-id="bf59f-120">O exemplo de código mostra como criar um sinônimo ou um nome alternativo para um objeto com escopo de esquema.</span><span class="sxs-lookup"><span data-stu-id="bf59f-120">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="bf59f-121">Aplicativos cliente podem usar uma única referência para o objeto base através de um sinônimo, em vez de usar um nome com várias partes para fazer referência ao objeto base.</span><span class="sxs-lookup"><span data-stu-id="bf59f-121">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#And the database object corresponding to Adventureworks  
$db = $srv.Databases["AdventureWorks2012"]  
  
$syn = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Synonym -ArgumentList $db, "Shop", "Sales"  
  
#Specify the base object, which is the object on which the synonym is based.  
$syn.BaseDatabase = "AdventureWorks2012"  
$syn.BaseSchema = "Sales"  
$syn.BaseObject = "Store"  
$syn.BaseServer = $srv.Name  
  
#Create the synonym on the instance of SQL Server.  
$syn.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf59f-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf59f-122">See Also</span></span>  
 [<span data-ttu-id="bf59f-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bf59f-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
