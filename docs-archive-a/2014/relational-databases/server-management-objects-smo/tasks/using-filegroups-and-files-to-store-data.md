---
title: Usando grupos de arquivos e arquivo para armazenar dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- filegroups [SMO]
- storing data [SMO]
- files [SMO]
- files [SMO], about files
- storage [SMO]
ms.assetid: 7e2327ce-e1a6-4904-83d1-0944b24a7b43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15ac5fd0c43c9b58432a774ae11aeb6500f0403b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582385"
---
# <a name="using-filegroups-and-files-to-store-data"></a><span data-ttu-id="134a3-102">Usando grupos de arquivos e arquivos para armazenar dados</span><span class="sxs-lookup"><span data-stu-id="134a3-102">Using Filegroups and Files to Store Data</span></span>
  <span data-ttu-id="134a3-103">Arquivos de dados são usados para armazenar arquivos de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="134a3-103">Data files are used to store database files.</span></span> <span data-ttu-id="134a3-104">Os arquivos de dados são subdivididos em grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="134a3-104">The data files are subdivided into file groups.</span></span> <span data-ttu-id="134a3-105">O objeto <xref:Microsoft.SqlServer.Management.Smo.Database> tem uma propriedade <xref:Microsoft.SqlServer.Management.Smo.Database.FileGroups%2A> que referencia um objeto <xref:Microsoft.SqlServer.Management.Smo.FileGroupCollection>.</span><span class="sxs-lookup"><span data-stu-id="134a3-105">The <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.Database.FileGroups%2A> property that references a <xref:Microsoft.SqlServer.Management.Smo.FileGroupCollection> object.</span></span> <span data-ttu-id="134a3-106">Cada objeto <xref:Microsoft.SqlServer.Management.Smo.FileGroup> nessa coleção tem uma propriedade <xref:Microsoft.SqlServer.Management.Smo.FileGroup.Files%2A>.</span><span class="sxs-lookup"><span data-stu-id="134a3-106">Each <xref:Microsoft.SqlServer.Management.Smo.FileGroup> object in that collection has a <xref:Microsoft.SqlServer.Management.Smo.FileGroup.Files%2A> property.</span></span> <span data-ttu-id="134a3-107">Essa propriedade se refere a uma coleção <xref:Microsoft.SqlServer.Management.Smo.DataFileCollection> que contém todos os arquivos de dados pertencentes ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="134a3-107">This property refers to a <xref:Microsoft.SqlServer.Management.Smo.DataFileCollection> collection that contains all the data files that belong to the database.</span></span> <span data-ttu-id="134a3-108">Um grupo de arquivos é usado especialmente para agrupar arquivos que são usados para armazenar um objeto de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="134a3-108">A file group is principally used to group files together that are used to store a database object.</span></span> <span data-ttu-id="134a3-109">Um dos motivos que leva à difusão de um objeto de banco de dados por vários arquivos é que isso pode melhorar o desempenho, especialmente quando os arquivos são armazenados em unidades de disco diferentes.</span><span class="sxs-lookup"><span data-stu-id="134a3-109">One reason for spreading a database object over several files is that it can improve performance, especially if the files are stored on different disk drives.</span></span>  
  
 <span data-ttu-id="134a3-110">Cada banco de dados que é criado automaticamente tem um grupo de arquivos nomeado "Primário" e um arquivo de dados com o mesmo nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="134a3-110">Every database that is created automatically has a file group named "Primary" and a data file with the same name as the database.</span></span> <span data-ttu-id="134a3-111">Outros arquivos e grupos podem ser adicionados às coleções.</span><span class="sxs-lookup"><span data-stu-id="134a3-111">Additional files and groups can be added to the collections.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="134a3-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="134a3-112">Examples</span></span>  
 <span data-ttu-id="134a3-113">Para os exemplos de código a seguir, selecione o ambiente de programação, o modelo de programação e a linguagem de programação para criar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="134a3-113">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="134a3-114">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="134a3-114">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-visual-basic"></a><span data-ttu-id="134a3-115">Adicionando FileGroups e DataFiles a um banco de dados no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="134a3-115">Adding FileGroups and DataFiles to a Database in Visual Basic</span></span>  
 <span data-ttu-id="134a3-116">O grupo de arquivos primário e o arquivo de dados são criados automaticamente com valores de propriedade padrão.</span><span class="sxs-lookup"><span data-stu-id="134a3-116">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="134a3-117">O exemplo de código especifica alguns valores de propriedade a serem usados.</span><span class="sxs-lookup"><span data-stu-id="134a3-117">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="134a3-118">Caso contrário, os valores de propriedade padrão são usados.</span><span class="sxs-lookup"><span data-stu-id="134a3-118">Otherwise, the default property values are used.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBFileGroups1](SMO How to#SMO_VBFileGroups1)]  -->  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-visual-c"></a><span data-ttu-id="134a3-119">Adicionando FileGroups e DataFiles a um banco de dados no Visual C#</span><span class="sxs-lookup"><span data-stu-id="134a3-119">Adding FileGroups and DataFiles to a Database in Visual C#</span></span>  
 <span data-ttu-id="134a3-120">O grupo de arquivos primário e o arquivo de dados são criados automaticamente com valores de propriedade padrão.</span><span class="sxs-lookup"><span data-stu-id="134a3-120">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="134a3-121">O exemplo de código especifica alguns valores de propriedade a serem usados.</span><span class="sxs-lookup"><span data-stu-id="134a3-121">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="134a3-122">Caso contrário, os valores de propriedade padrão são usados.</span><span class="sxs-lookup"><span data-stu-id="134a3-122">Otherwise, the default property values are used.</span></span>  
  
```csharp
{  
            Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define a FileGroup object called SECONDARY on the database.   
            FileGroup fg1 = default(FileGroup);  
            fg1 = new FileGroup(db, "SECONDARY");  
            //Call the Create method to create the file group on the instance of SQL Server.   
            fg1.Create();  
            //Define a DataFile object on the file group and set the FileName property.   
            DataFile df1 = default(DataFile);  
            df1 = new DataFile(fg1, "datafile1");  
            df1.FileName = "c:\\Program Files\\Microsoft SQL Server\\MSSQL.1\\MSSQL\\Data\\datafile2.ndf";  
            //Call the Create method to create the data file on the instance of SQL Server.   
            df1.Create();  
        }  
```  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-powershell"></a><span data-ttu-id="134a3-123">Adicionando grupos de arquivos e arquivos de dados a um banco de dados no PowerShell</span><span class="sxs-lookup"><span data-stu-id="134a3-123">Adding FileGroups and DataFiles to a Database in PowerShell</span></span>  
 <span data-ttu-id="134a3-124">O grupo de arquivos primário e o arquivo de dados são criados automaticamente com valores de propriedade padrão.</span><span class="sxs-lookup"><span data-stu-id="134a3-124">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="134a3-125">O exemplo de código especifica alguns valores de propriedade a serem usados.</span><span class="sxs-lookup"><span data-stu-id="134a3-125">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="134a3-126">Caso contrário, os valores de propriedade padrão são usados.</span><span class="sxs-lookup"><span data-stu-id="134a3-126">Otherwise, the default property values are used.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default\Databases\  
  
#And the database object corresponding to AdventureWorks2012.  
$db = get-item AdventureWorks2012  
  
#Create a new filegroup  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "SECONDARY"  
$fg1.Create()  
  
#Define a DataFile object on the file group and set the FileName property.   
$df1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.DataFile -argumentlist $fg1, "datafile1"  
  
#Make sure to have a directory created to hold the designated data file  
$df1.FileName = "c:\\TestData\\datafile2.ndf"  
  
#Call the Create method to create the data file on the instance of SQL Server.   
$df1.Create()  
```  
  
## <a name="creating-altering-and-removing-a-log-file-in-visual-basic"></a><span data-ttu-id="134a3-127">Criando, alterando e removendo um arquivo de log no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="134a3-127">Creating, Altering, and Removing a Log File in Visual Basic</span></span>  
 <span data-ttu-id="134a3-128">O exemplo de código cria um objeto <xref:Microsoft.SqlServer.Management.Smo.LogFile>, altera uma das propriedades e remove-o do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="134a3-128">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBFileGroups3](SMO How to#SMO_VBFileGroups3)]  -->  
  
## <a name="creating-altering-and-removing-a-log-file-in-visual-c"></a><span data-ttu-id="134a3-129">Criando, alterando e removendo um arquivo de log no Visual C#</span><span class="sxs-lookup"><span data-stu-id="134a3-129">Creating, Altering, and Removing a Log File in Visual C#</span></span>  
 <span data-ttu-id="134a3-130">O exemplo de código cria um objeto <xref:Microsoft.SqlServer.Management.Smo.LogFile>, altera uma das propriedades e remove-o do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="134a3-130">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define a LogFile object and set the database, name, and file name properties in the constructor.   
            LogFile lf1 = default(LogFile);  
            lf1 = new LogFile(db, "logfile1", "c:\\Program Files\\Microsoft SQL Server\\MSSQL.10_50.MSSQLSERVER\\MSSQL\\Data\\logfile1.ldf");  
            //Set the file growth to 6%.   
            lf1.GrowthType = FileGrowthType.Percent;  
            lf1.Growth = 6;  
            //Run the Create method to create the log file on the instance of SQL Server.   
            lf1.Create();  
            //Alter the growth percentage.
            lf1.Growth = 7;  
            lf1.Alter();  
            //Remove the log file.
            lf1.Drop();
```  
  
## <a name="creating-altering-and-removing-a-log-file-in-powershell"></a><span data-ttu-id="134a3-131">Criando, alterando e removendo um arquivo de log no PowerShell</span><span class="sxs-lookup"><span data-stu-id="134a3-131">Creating, Altering, and Removing a Log File in PowerShell</span></span>  
 <span data-ttu-id="134a3-132">O exemplo de código cria um objeto <xref:Microsoft.SqlServer.Management.Smo.LogFile>, altera uma das propriedades e remove-o do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="134a3-132">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
```powershell
#Load the assembly containing the enums used in this example  
[reflection.assembly]::LoadWithPartialName("Microsoft.SqlServer.SqlEnum")  
  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default\Databases\  
  
#And the database object corresponding to AdventureWorks2012  
$db = get-item AdventureWorks2012  
  
#Create a filegroup  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Secondary"  
  
#Call the Create method to create the file group on the instance of SQL Server.   
$fg1.Create()  
  
#Define a LogFile object on the file group and set the FileName property.   
$lf1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.LogFile -argumentlist $db, "LogFile2"  
  
#Set a location for it - make sure the directory exists  
$lf1.FileName = "logfile1", "c:\\Program Files\\Microsoft SQL Server\\MSSQL.10_50.MSSQLSERVER\\MSSQL\\Data\\logfile1.ldf"  
  
#Set file growth to 6%  
$lf1.GrowthType = [Microsoft.SqlServer.Management.Smo.FileGrowthType]::Percent  
$lf1.Growth = 6.0  
  
#Call the Create method to create the data file on the instance of SQL Server.   
$lf1.Create()  
  
#Alter a value and drop the log file  
$lf1.Growth = 7.0  
$lf1.Alter()  
$lf1.Drop()
```  
  
## <a name="see-also"></a><span data-ttu-id="134a3-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="134a3-133">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.FileGroup>   
 [<span data-ttu-id="134a3-134">Arquivos e grupos de arquivos do banco de dados</span><span class="sxs-lookup"><span data-stu-id="134a3-134">Database Files and Filegroups</span></span>](../../databases/database-files-and-filegroups.md)  
