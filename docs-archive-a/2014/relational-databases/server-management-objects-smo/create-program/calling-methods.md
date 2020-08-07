---
title: Chamando métodos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- methods [SMO]
- calling methods
- SQL Server Management Objects, method calling
- SMO [SQL Server], method calling
ms.assetid: c88d5c5f-9ff0-4f84-b2b6-24c6b90fa15e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13216b4c533527d4249471073580d7c86f6b07e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682205"
---
# <a name="calling-methods"></a><span data-ttu-id="2b5fc-102">Chamando métodos</span><span class="sxs-lookup"><span data-stu-id="2b5fc-102">Calling Methods</span></span>
  <span data-ttu-id="2b5fc-103">Os métodos executam tarefas específicas relacionadas ao objeto, como emitir um `Checkpoint` em um banco de dados ou solicitar uma lista enumerada de logons para a instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b5fc-103">Methods perform specific tasks related to the object, such as issuing a `Checkpoint` on a database or requesting an enumerated list of logons for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2b5fc-104">Os métodos executam uma operação em um objeto.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-104">Methods perform an operation on an object.</span></span> <span data-ttu-id="2b5fc-105">Podem assumir parâmetros e frequentemente têm um valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-105">Methods can take parameters and often have a return value.</span></span> <span data-ttu-id="2b5fc-106">O valor de retorno pode ser um tipo de dados simples, um objeto complexo ou uma estrutura que contém muitos membros.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-106">The return value can be a simple data type, a complex object, or a structure that contains many members.</span></span>  
  
 <span data-ttu-id="2b5fc-107">Use o tratamento de exceções para detectar se o método obteve êxito.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-107">Use exception handling to detect whether the method has been successful.</span></span> <span data-ttu-id="2b5fc-108">Para obter mais informações, consulte [Handling SMO Exceptions](handling-smo-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="2b5fc-108">For more information, see [Handling SMO Exceptions](handling-smo-exceptions.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2b5fc-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2b5fc-109">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="using-a-simple-smo-method-in-visual-basic"></a><span data-ttu-id="2b5fc-110">Usando um método SMO simples no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b5fc-110">Using a Simple SMO Method in Visual Basic</span></span>  
 <span data-ttu-id="2b5fc-111">Neste exemplo, o método <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> não utiliza nenhum parâmetro e não tem nenhum valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-111">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods1](SMO How to#SMO_VBMethods1)]  -->  
  
## <a name="using-a-simple-smo-method-in-visual-c"></a><span data-ttu-id="2b5fc-112">Usando um método SMO simples no Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b5fc-112">Using a Simple SMO Method in Visual C#</span></span>  
 <span data-ttu-id="2b5fc-113">Neste exemplo, o método <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> não utiliza nenhum parâmetro e não tem nenhum valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-113">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define a Database object variable by supplying the parent server and the database name arguments in the constructor.   
Database db;   
db = new Database(srv, "Test_SMO_Database");   
//Call the Create method to create the database on the instance of SQL Server.   
db.Create();   
```  
  
 <span data-ttu-id="2b5fc-114">}</span><span class="sxs-lookup"><span data-stu-id="2b5fc-114">}</span></span>  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-basic"></a><span data-ttu-id="2b5fc-115">Usando um método SMO com um parâmetro no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b5fc-115">Using an SMO Method with a Parameter in Visual Basic</span></span>  
 <span data-ttu-id="2b5fc-116">O objeto <xref:Microsoft.SqlServer.Management.Smo.Table> tem um método chamado <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-116">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="2b5fc-117">Esse método exige um parâmetro numérico que especifica o `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-117">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
Dim srv As Server  
srv = New Server  
Dim tb As Table  
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources")  
tb.RebuildIndexes(70)  
```  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-c"></a><span data-ttu-id="2b5fc-118">Usando um método SMO com um parâmetro no Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b5fc-118">Using an SMO Method with a Parameter in Visual C#</span></span>  
 <span data-ttu-id="2b5fc-119">O objeto <xref:Microsoft.SqlServer.Management.Smo.Table> tem um método chamado <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-119">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="2b5fc-120">Esse método exige um parâmetro numérico que especifica o `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-120">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
{   
Server srv = default(Server);   
srv = new Server();   
Table tb = default(Table);   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
}   
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-basic"></a><span data-ttu-id="2b5fc-121">Usando um método de enumeração que retorna um objeto DataTable no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b5fc-121">Using an Enumeration Method that Returns a DataTable Object in Visual Basic</span></span>  
 <span data-ttu-id="2b5fc-122">Esta seção descreve como chamar um método de enumeração e tratar os dados no objeto <xref:System.Data.DataTable> retornado.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-122">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="2b5fc-123">O método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> retorna um objeto <xref:System.Data.DataTable>, que exige navegação adicional para acessar todas as informações de ordenação disponíveis sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b5fc-123">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a <xref:System.Data.DataTable> object, which requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
'Connect to the local, default instance of SQL Server.  
Dim srv As Server  
srv = New Server  
'Call the EnumCollations method and return collation information to DataTable variable.  
Dim d As DataTable  
'Select the returned data into an array of DataRow.  
d = srv.EnumCollations  
'Iterate through the rows and display collation details for the instance of SQL Server.  
Dim r As DataRow  
Dim c As DataColumn  
For Each r In d.Rows  
    Console.WriteLine("==")  
    For Each c In r.Table.Columns  
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)  
    Next  
Next  
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-c"></a><span data-ttu-id="2b5fc-124">Usando um método de enumeração que retorna um objeto DataTable no Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b5fc-124">Using an Enumeration Method that Returns a DataTable Object in Visual C#</span></span>  
 <span data-ttu-id="2b5fc-125">Esta seção descreve como chamar um método de enumeração e tratar os dados no objeto <xref:System.Data.DataTable> retornado.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-125">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="2b5fc-126">O método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> retorna um objeto <xref:System.Data.DataTable> de sistema.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-126">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a system <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="2b5fc-127">O objeto <xref:System.Data.DataTable> exige navegação adicional para acessar todas as informações de ordenação disponíveis sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b5fc-127">The <xref:System.Data.DataTable> object requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumCollations;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=========");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="constructing-an-object-in-visual-basic"></a><span data-ttu-id="2b5fc-128">Construindo um objeto no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b5fc-128">Constructing an Object in Visual Basic</span></span>  
 <span data-ttu-id="2b5fc-129">O construtor de qualquer objeto pode ser chamado usando o operador `New`.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-129">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="2b5fc-130">O construtor do objeto <xref:Microsoft.SqlServer.Management.Smo.Database> é sobrecarregado e a versão do construtor do objeto <xref:Microsoft.SqlServer.Management.Smo.Database> que é usada no exemplo utiliza dois parâmetros: o objeto <xref:Microsoft.SqlServer.Management.Smo.Server> pai ao qual o banco de dados pertence e uma cadeia de caracteres que representa o nome do novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-130">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods4](SMO How to#SMO_VBMethods4)]  -->  
  
## <a name="constructing-an-object-in-visual-c"></a><span data-ttu-id="2b5fc-131">Construindo um objeto no Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b5fc-131">Constructing an Object in Visual C#</span></span>  
 <span data-ttu-id="2b5fc-132">O construtor de qualquer objeto pode ser chamado usando o operador `New`.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-132">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="2b5fc-133">O construtor do objeto <xref:Microsoft.SqlServer.Management.Smo.Database> é sobrecarregado e a versão do construtor do objeto <xref:Microsoft.SqlServer.Management.Smo.Database> que é usada no exemplo utiliza dois parâmetros: o objeto <xref:Microsoft.SqlServer.Management.Smo.Server> pai ao qual o banco de dados pertence e uma cadeia de caracteres que representa o nome do novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-133">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
Table tb;   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.   
Database d;   
d = new Database(srv, "Test_SMO_Database");   
//Create the database on the instance of SQL Server.   
d.Create();   
Console.WriteLine(d.Name);   
}  
```  
  
## <a name="copying-an-smo-object-in-visual-basic"></a><span data-ttu-id="2b5fc-134">Copiando um objeto SMO no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b5fc-134">Copying an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="2b5fc-135">Este exemplo de código usa o método <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> para criar uma cópia do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-135">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="2b5fc-136">O objeto <xref:Microsoft.SqlServer.Management.Smo.Server> representa uma conexão com uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b5fc-136">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VCMethods6](SMO How to#SMO_VCMethods6)]  -->  
  
## <a name="copying-an-smo-object-in-visual-c"></a><span data-ttu-id="2b5fc-137">Copiando um objeto SMO no Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b5fc-137">Copying an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="2b5fc-138">Este exemplo de código usa o método <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> para criar uma cópia do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-138">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="2b5fc-139">O objeto <xref:Microsoft.SqlServer.Management.Smo.Server> representa uma conexão com uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b5fc-139">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv1;   
srv1 = new Server();   
//Modify the default database and the timeout period for the connection.   
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012";   
srv1.ConnectionContext.ConnectTimeout = 30;   
//Make a second connection using a copy of the ConnectionContext property and verify settings.   
Server srv2;   
srv2 = new Server(srv1.ConnectionContext.Copy);   
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString);   
}  
```  
  
## <a name="monitoring-server-processes-in-visual-basic"></a><span data-ttu-id="2b5fc-140">Monitorando processos de servidor no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b5fc-140">Monitoring Server Processes in Visual Basic</span></span>  
 <span data-ttu-id="2b5fc-141">Você pode obter as informações de tipo de status atuais sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] através dos métodos de enumeração.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-141">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="2b5fc-142">O exemplo de código usa o método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> para descobrir informações sobre os processos atuais.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-142">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="2b5fc-143">Ele também demonstra como trabalhar com as colunas e linhas no objeto <xref:System.Data.DataTable> retornado.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-143">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods5](SMO How to#SMO_VBMethods5)]  -->  
  
## <a name="monitoring-server-processes-in-visual-c"></a><span data-ttu-id="2b5fc-144">Monitorando processos de servidor no Visual C#</span><span class="sxs-lookup"><span data-stu-id="2b5fc-144">Monitoring Server Processes in Visual C#</span></span>  
 <span data-ttu-id="2b5fc-145">Você pode obter as informações de tipo de status atuais sobre a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] através dos métodos de enumeração.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-145">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="2b5fc-146">O exemplo de código usa o método <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> para descobrir informações sobre os processos atuais.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-146">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="2b5fc-147">Ele também demonstra como trabalhar com as colunas e linhas no objeto <xref:System.Data.DataTable> retornado.</span><span class="sxs-lookup"><span data-stu-id="2b5fc-147">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumProcesses;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=====");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="see-also"></a><span data-ttu-id="2b5fc-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b5fc-148">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
