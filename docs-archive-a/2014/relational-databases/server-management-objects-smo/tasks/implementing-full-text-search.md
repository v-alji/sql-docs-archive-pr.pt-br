---
title: Implementando a pesquisa de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- full-text search [SMO]
ms.assetid: 9ce9ad9c-f671-4760-90b5-e0c8ca051473
author: stevestein
ms.author: sstein
ms.openlocfilehash: f8b797e2a38c9136c34b7058b539fca522e03229
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678695"
---
# <a name="implementing-full-text-search"></a><span data-ttu-id="30902-102">Implementando a pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="30902-102">Implementing Full-Text Search</span></span>
  <span data-ttu-id="30902-103">A pesquisa de texto completo está disponível por instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e é representada no SMO pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Server.FullTextService%2A>.</span><span class="sxs-lookup"><span data-stu-id="30902-103">Full-text search is available per instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and is represented in SMO by the <xref:Microsoft.SqlServer.Management.Smo.Server.FullTextService%2A> object.</span></span> <span data-ttu-id="30902-104">O objeto <xref:Microsoft.SqlServer.Management.Smo.FullTextService> reside sob o objeto `Server`.</span><span class="sxs-lookup"><span data-stu-id="30902-104">The <xref:Microsoft.SqlServer.Management.Smo.FullTextService> object resides under the `Server` object.</span></span> <span data-ttu-id="30902-105">Ele é usado para gerenciar as opções de configuração do serviço de Pesquisa de Texto Completo da [!INCLUDE[msCoName](../../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30902-105">It is used to manage the configuration options for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Full Text Search service.</span></span> <span data-ttu-id="30902-106">O objeto <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalogCollection> pertence ao objeto <xref:Microsoft.SqlServer.Management.Smo.Database> e é uma coleção de objetos <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> que representam catálogos de texto completo definidos para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="30902-106">The <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalogCollection> object belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object and it is a collection of <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> objects that represent full-text catalogs defined for the database.</span></span> <span data-ttu-id="30902-107">Você só pode ter um índice de texto completo definido para cada tabela, diferente de índices normais.</span><span class="sxs-lookup"><span data-stu-id="30902-107">You can only have one full-text index defined for each table, unlike normal indexes.</span></span> <span data-ttu-id="30902-108">Isso é representado por um objeto <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> no objeto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="30902-108">This is represented by a <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> object in the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
 <span data-ttu-id="30902-109">Para criar uma serviço de pesquisa de texto completo, você precisa ter um catálogo de texto completo definido no banco de dados e um índice de pesquisa de texto completo definido em uma das tabelas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="30902-109">To create a full-text search service, you must have a full-text catalog defined on the database and a full-text search index defined on one of the tables in the database.</span></span>  
  
 <span data-ttu-id="30902-110">Primeiro, crie um catálogo de texto completo no banco de dados chamando o construtor <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> e especificando o nome do catálogo.</span><span class="sxs-lookup"><span data-stu-id="30902-110">First, create a full-text catalog on the database by calling the <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> constructor and specifying the catalog name.</span></span> <span data-ttu-id="30902-111">Depois, crie o índice de texto completo chamando o construtor e especificando a tabela na qual ele será criado.</span><span class="sxs-lookup"><span data-stu-id="30902-111">Then, create the full-text index by calling the constructor and specifying the table on which it is to be created.</span></span> <span data-ttu-id="30902-112">Depois, você poderá adicionar colunas de índice ao índice de texto completo, usando o objeto <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> e fornecendo o nome da coluna dentro da tabela.</span><span class="sxs-lookup"><span data-stu-id="30902-112">You can then add index columns for the full-text index, by using the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> object and providing the name of the column within the table.</span></span> <span data-ttu-id="30902-113">Em seguida, defina a propriedade <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.CatalogName%2A> para o catálogo criado.</span><span class="sxs-lookup"><span data-stu-id="30902-113">Then, set the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.CatalogName%2A> property to the catalog you have created.</span></span> <span data-ttu-id="30902-114">Finalmente, chame o método <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.Create%2A> e crie o índice de texto completo na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30902-114">Finally, call the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.Create%2A> method and create the full-text index on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="30902-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="30902-115">Example</span></span>  
 <span data-ttu-id="30902-116">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="30902-116">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="30902-117">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="30902-117">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-full-text-search-service-in-visual-basic"></a><span data-ttu-id="30902-118">Criando um serviço de pesquisa de texto completo no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30902-118">Creating a Full-Text Search Service in Visual Basic</span></span>  
 <span data-ttu-id="30902-119">Este exemplo de código cria um catálogo de pesquisa de texto completo para a tabela `ProductCategory` no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30902-119">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="30902-120">Ele cria um índice de pesquisa de texto completo na coluna Nome da tabela `ProductCategory` .</span><span class="sxs-lookup"><span data-stu-id="30902-120">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="30902-121">O índice de pesquisa de texto completo exige que haja um índice exclusivo já definido na coluna.</span><span class="sxs-lookup"><span data-stu-id="30902-121">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.SqlEnum.dll   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      ' Connect to the local, default instance of SQL Server.  
      Dim srv As Server = Nothing  
      srv = New Server()  
  
      ' Reference the AdventureWorks database.  
      Dim db As Database = Nothing  
      db = srv.Databases("AdventureWorks")  
  
      ' Reference the ProductCategory table.  
      Dim tb As Table = Nothing  
      tb = db.Tables("ProductCategory", "Production")  
  
      ' Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
      Dim ftc As FullTextCatalog = Nothing  
      ftc = New FullTextCatalog(db, "Test_Catalog")  
      ftc.IsDefault = True  
  
      ' Create the Full-Text Search catalog on the instance of SQL Server.  
      ftc.Create()  
  
      ' Define a FullTextIndex object varaible by supplying the parent table argument in the constructor.  
      Dim fti As FullTextIndex = Nothing  
      fti = New FullTextIndex(tb)  
  
      ' Define a FullTextIndexColumn object variable by supplying the parent index and column name arguments in the constructor.  
      Dim ftic As FullTextIndexColumn = Nothing  
      ftic = New FullTextIndexColumn(fti, "Name")  
  
      ' Add the indexed column to the index.  
      fti.IndexedColumns.Add(ftic)  
      fti.ChangeTracking = ChangeTracking.Automatic  
  
      ' Specify the unique index on the table that is required by the Full Text Search index.  
      fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
      ' Specify the catalog associated with the index.  
      fti.CatalogName = "Test_Catalog"  
  
      ' Create the Full Text Search index on the instance of SQL Server.  
      fti.Create()  
   End Sub  
End Class  
```  
  
## <a name="creating-a-full-text-search-service-in-visual-c"></a><span data-ttu-id="30902-122">Criando um serviço de pesquisa de texto completo no Visual C#</span><span class="sxs-lookup"><span data-stu-id="30902-122">Creating a Full-Text Search Service in Visual C#</span></span>  
 <span data-ttu-id="30902-123">Este exemplo de código cria um catálogo de pesquisa de texto completo para a tabela `ProductCategory` no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30902-123">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="30902-124">Ele cria um índice de pesquisa de texto completo na coluna Nome da tabela `ProductCategory` .</span><span class="sxs-lookup"><span data-stu-id="30902-124">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="30902-125">O índice de pesquisa de texto completo exige que haja um índice exclusivo já definido na coluna.</span><span class="sxs-lookup"><span data-stu-id="30902-125">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.SqlEnum.dll   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {  
      // Connect to the local, default instance of SQL Server.  
      Server srv = default(Server);  
      srv = new Server();  
  
      // Reference the AdventureWorks database.  
      Database db = default(Database);  
      db = srv.Databases ["AdventureWorks"];  
  
      // Reference the ProductCategory table.  
      Table tb = default(Table);  
      tb = db.Tables["ProductCategory", "Production"];  
  
      // Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
      FullTextCatalog ftc = default(FullTextCatalog);  
      ftc = new FullTextCatalog(db, "Test_Catalog");  
      ftc.IsDefault = true;  
  
      // Create the Full-Text Search catalog on the instance of SQL Server.  
      ftc.Create();  
  
      // Define a FullTextIndex object varaible by supplying the parent table argument in the constructor.  
      FullTextIndex fti = default(FullTextIndex);  
      fti = new FullTextIndex(tb);  
  
      // Define a FullTextIndexColumn object variable by supplying the parent index and column name arguments in the constructor.  
      FullTextIndexColumn ftic = default(FullTextIndexColumn);  
      ftic = new FullTextIndexColumn(fti, "Name");  
  
      // Add the indexed column to the index.  
      fti.IndexedColumns.Add(ftic);  
      fti.ChangeTracking = ChangeTracking.Automatic;  
  
      // Specify the unique index on the table that is required by the Full Text Search index.  
      fti.UniqueIndexName = "AK_ProductCategory_Name";  
  
      // Specify the catalog associated with the index.  
      fti.CatalogName = "Test_Catalog";  
  
      // Create the Full Text Search index on the instance of SQL Server.  
      fti.Create();  
   }  
}  
```  
  
## <a name="creating-a-full-text-search-service-in-powershell"></a><span data-ttu-id="30902-126">Criando um serviço de pesquisa de texto completo no PowerShell</span><span class="sxs-lookup"><span data-stu-id="30902-126">Creating a Full-Text Search Service in PowerShell</span></span>  
 <span data-ttu-id="30902-127">Este exemplo de código cria um catálogo de pesquisa de texto completo para a tabela `ProductCategory` no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30902-127">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="30902-128">Ele cria um índice de pesquisa de texto completo na coluna Nome da tabela `ProductCategory` .</span><span class="sxs-lookup"><span data-stu-id="30902-128">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="30902-129">O índice de pesquisa de texto completo exige que haja um índice exclusivo já definido na coluna.</span><span class="sxs-lookup"><span data-stu-id="30902-129">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```powershell
# Example of implementing a full text search on the default instance.  
# Set the path context to the local, default instance of SQL Server and database tables  
  
CD \sql\localhost\default\databases  
$db = Get-Item AdventureWorks2012  
  
CD AdventureWorks\tables  
  
#Get a reference to the table  
$tb = Get-Item Production.ProductCategory  
  
# Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
  
$ftc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextCatalog -ArgumentList $db, "Test_Catalog2"  
$ftc.IsDefault = $true  
  
# Create the Full Text Search catalog on the instance of SQL Server.  
$ftc.Create()  
  
# Define a FullTextIndex object variable by supplying the parent table argument in the constructor.  
$fti = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndex -ArgumentList $tb  
  
#  Define a FullTextIndexColumn object variable by supplying the parent index
#  and column name arguments in the constructor.  
  
$ftic = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndexColumn -ArgumentList $fti, "Name"  
  
# Add the indexed column to the index.  
$fti.IndexedColumns.Add($ftic)  
  
# Set change tracking  
$fti.ChangeTracking = [Microsoft.SqlServer.Management.SMO.ChangeTracking]::Automatic  
  
# Specify the unique index on the table that is required by the Full Text Search index.  
$fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
# Specify the catalog associated with the index.  
$fti.CatalogName = "Test_Catalog2"  
  
# Create the Full Text Search Index  
$fti.Create()  
```  
