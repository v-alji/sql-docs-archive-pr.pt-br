---
title: Gerenciando usuários, funções e logons | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- logins [SMO]
- roles [SMO]
- users [SMO]
ms.assetid: 74e411fa-74ed-49ec-ab58-68c250f2280e
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb53e7b4a5748e46c7cb147e1cda50652d8b8805
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576253"
---
# <a name="managing-users-roles-and-logins"></a><span data-ttu-id="d973e-102">Gerenciando usuários, funções e logons</span><span class="sxs-lookup"><span data-stu-id="d973e-102">Managing Users, Roles, and Logins</span></span>
  <span data-ttu-id="d973e-103">No SMO, os logons são representados pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Login>.</span><span class="sxs-lookup"><span data-stu-id="d973e-103">In SMO, logins are represented by the <xref:Microsoft.SqlServer.Management.Smo.Login> object.</span></span> <span data-ttu-id="d973e-104">Quando o logon existir no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], ele poderá ser adicionado a uma função de servidor.</span><span class="sxs-lookup"><span data-stu-id="d973e-104">When the logon exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it can be added to a server role.</span></span> <span data-ttu-id="d973e-105">A função de servidor é representada pelo objeto <xref:Microsoft.SqlServer.Management.Smo.ServerRole>.</span><span class="sxs-lookup"><span data-stu-id="d973e-105">The server role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ServerRole> object.</span></span> <span data-ttu-id="d973e-106">A função de banco de dados é representada pelo objeto <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> e a função de aplicativo é representada pelo objeto <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole>.</span><span class="sxs-lookup"><span data-stu-id="d973e-106">The database role is represented by the <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> object and the application role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole> object.</span></span>  
  
 <span data-ttu-id="d973e-107">Privilégios associados ao nível de servidor são listados como propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.ServerPermission>.</span><span class="sxs-lookup"><span data-stu-id="d973e-107">Privileges associated with the server level are listed as properties of the <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> object.</span></span> <span data-ttu-id="d973e-108">Os privilégios em nível de servidor podem ser concedidos a, negados a ou revogados de contas de logon individuais.</span><span class="sxs-lookup"><span data-stu-id="d973e-108">The server level privileges can be granted to, denied to, or revoked from individual logon accounts.</span></span>  
  
 <span data-ttu-id="d973e-109">Cada objeto <xref:Microsoft.SqlServer.Management.Smo.Database> possui um objeto <xref:Microsoft.SqlServer.Management.Smo.UserCollection> que especifica todos os usuários do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d973e-109">Every <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.UserCollection> object that specifies all users in the database.</span></span> <span data-ttu-id="d973e-110">Cada usuário é associado a um logon.</span><span class="sxs-lookup"><span data-stu-id="d973e-110">Each user is associated with a logon.</span></span> <span data-ttu-id="d973e-111">Um logon pode ser associado a usuários em mais de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d973e-111">One logon can be associated with users in more than one database.</span></span> <span data-ttu-id="d973e-112">O método <xref:Microsoft.SqlServer.Management.Smo.Login> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> pode ser usado para listar todos os usuários em cada banco de dados associado ao logon.</span><span class="sxs-lookup"><span data-stu-id="d973e-112">The <xref:Microsoft.SqlServer.Management.Smo.Login> object's <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method can be used to list all users in every database that is associated with the logon.</span></span> <span data-ttu-id="d973e-113">Alternativamente, a propriedade <xref:Microsoft.SqlServer.Management.Smo.User> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login> especifica o logon que é associado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="d973e-113">Alternatively, the <xref:Microsoft.SqlServer.Management.Smo.User> object's <xref:Microsoft.SqlServer.Management.Smo.Login> property specifies the logon that is associated with the user.</span></span>  
  
 <span data-ttu-id="d973e-114">Bancos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] também têm funções que especificam um conjunto de privilégios em nível de banco de dados que permitem a um usuário executar tarefas específicas.</span><span class="sxs-lookup"><span data-stu-id="d973e-114">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases also have roles that specify a set of database level privileges that let a user perform specific tasks.</span></span> <span data-ttu-id="d973e-115">Diferente das funções de servidor, as funções de banco de dados não são fixas.</span><span class="sxs-lookup"><span data-stu-id="d973e-115">Unlike server roles, database roles are not fixed.</span></span> <span data-ttu-id="d973e-116">Elas podem ser criadas, modificadas e removidas.</span><span class="sxs-lookup"><span data-stu-id="d973e-116">They can be created, modified, and removed.</span></span> <span data-ttu-id="d973e-117">Privilégios e usuários podem ser designados a uma função de banco de dados para administração em massa.</span><span class="sxs-lookup"><span data-stu-id="d973e-117">Privileges and users can be assigned to a database role for bulk administration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d973e-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d973e-118">Example</span></span>  
 <span data-ttu-id="d973e-119">Para o exemplo de código a seguir, selecione o ambiente de programação, o modelo de programação e a linguagem de programação para criar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d973e-119">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="d973e-120">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="d973e-120">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="enumerating-logins-and-associated-users-in-visual-basic"></a><span data-ttu-id="d973e-121">Enumerando logons e usuários associados no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d973e-121">Enumerating Logins and Associated Users in Visual Basic</span></span>  
 <span data-ttu-id="d973e-122">Cada usuário em um banco de dados é associado a um logon.</span><span class="sxs-lookup"><span data-stu-id="d973e-122">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="d973e-123">O logon pode ser associado a usuários em mais de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d973e-123">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="d973e-124">O exemplo de código mostra como chamar o método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para listar todos os usuários de banco de dados associados ao logon.</span><span class="sxs-lookup"><span data-stu-id="d973e-124">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="d973e-125">O exemplo cria um logon e um usuário no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] para garantir a existência de informações de mapeamento a serem enumeradas.</span><span class="sxs-lookup"><span data-stu-id="d973e-125">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLogins1](SMO How to#SMO_VBLogins1)]  -->  
  
## <a name="enumerating-logins-and-associated-users-in-visual-c"></a><span data-ttu-id="d973e-126">Enumerando logons e usuários associados no Visual C#</span><span class="sxs-lookup"><span data-stu-id="d973e-126">Enumerating Logins and Associated Users in Visual C#</span></span>  
 <span data-ttu-id="d973e-127">Cada usuário em um banco de dados é associado a um logon.</span><span class="sxs-lookup"><span data-stu-id="d973e-127">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="d973e-128">O logon pode ser associado a usuários em mais de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d973e-128">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="d973e-129">O exemplo de código mostra como chamar o método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para listar todos os usuários de banco de dados associados ao logon.</span><span class="sxs-lookup"><span data-stu-id="d973e-129">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="d973e-130">O exemplo cria um logon e um usuário no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] para garantir a existência de informações de mapeamento a serem enumeradas.</span><span class="sxs-lookup"><span data-stu-id="d973e-130">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```csharp
{   
Server srv = new Server();   
//Iterate through each database and display.   
  
foreach ( Database db in srv.Databases) {   
   Console.WriteLine("========");   
   Console.WriteLine("Login Mappings for the database: " + db.Name);   
   Console.WriteLine(" ");   
   //Run the EnumLoginMappings method and return details of database user-login mappings to a DataTable object variable.   
   DataTable d;  
   d = db.EnumLoginMappings();   
   //Display the mapping information.   
   foreach (DataRow r in d.Rows) {   
      foreach (DataColumn c in r.Table.Columns) {   
         Console.WriteLine(c.ColumnName + " = " + r[c]);   
      }   
      Console.WriteLine(" ");   
   }   
}   
}  
```  
  
## <a name="enumerating-logins-and-associated-users-in-powershell"></a><span data-ttu-id="d973e-131">Enumerando logons e usuários associados no PowerShell</span><span class="sxs-lookup"><span data-stu-id="d973e-131">Enumerating Logins and Associated Users in PowerShell</span></span>  
 <span data-ttu-id="d973e-132">Cada usuário em um banco de dados é associado a um logon.</span><span class="sxs-lookup"><span data-stu-id="d973e-132">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="d973e-133">O logon pode ser associado a usuários em mais de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d973e-133">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="d973e-134">O exemplo de código mostra como chamar o método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para listar todos os usuários de banco de dados associados ao logon.</span><span class="sxs-lookup"><span data-stu-id="d973e-134">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="d973e-135">O exemplo cria um logon e um usuário no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] para garantir a existência de informações de mapeamento a serem enumeradas.</span><span class="sxs-lookup"><span data-stu-id="d973e-135">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\Default\Databases  
  
#Iterate through all databases  
 foreach ($db in Get-ChildItem)  
 {  
 "====="  
 "Login Mappings for the database: "+ $db.Name  
  
 #get the datatable containing the mapping from the smo database object  
 $dt = $db.EnumLoginMappings()  
  
 #display the results  
 foreach($row in $dt.Rows)  
     {  
        foreach($col in $row.Table.Columns)  
      {  
        $col.ColumnName + "=" + $row[$col]  
       }
     }  
 }  
```  
  
## <a name="managing-roles-and-users"></a><span data-ttu-id="d973e-136">Gerenciando funções e usuários</span><span class="sxs-lookup"><span data-stu-id="d973e-136">Managing Roles and Users</span></span>  
 <span data-ttu-id="d973e-137">Este exemplo demonstra como gerenciar funções e usuários.</span><span class="sxs-lookup"><span data-stu-id="d973e-137">This sample demonstrates how to how to manage roles and users.</span></span> <span data-ttu-id="d973e-138">O primeiro exemplo usa C# e o segundo usa o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d973e-138">The first sample uses C#, the second Visual Basic.</span></span> <span data-ttu-id="d973e-139">Estes exemplos precisam referenciar os seguintes assemblies:</span><span class="sxs-lookup"><span data-stu-id="d973e-139">These samples need to reference the following assemblies:</span></span>  
  
-   <span data-ttu-id="d973e-140">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="d973e-140">Microsoft.SqlServer.Smo.dll</span></span>  
  
-   <span data-ttu-id="d973e-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="d973e-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
-   <span data-ttu-id="d973e-142">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="d973e-142">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
-   <span data-ttu-id="d973e-143">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="d973e-143">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
```csharp
using Microsoft.SqlServer.Management.Smo;  
using System;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
      Database db = new Database(svr, "TESTDB");  
      db.Create();  
  
      // Creating Logins  
      Login login = new Login(svr, "Login1");  
      login.LoginType = LoginType.SqlLogin;  
      login.Create("password@1");  
  
      Login login2 = new Login(svr, "Login2");  
      login2.LoginType = LoginType.SqlLogin;  
      login2.Create("password@1");  
  
      // Creating Users in the database for the logins created  
      User user1 = new User(db, "User1");  
      user1.Login = "Login1";  
      user1.Create();  
  
      User user2 = new User(db, "User2");  
      user2.Login = "Login2";  
      user2.Create();  
  
      // Creating database permission Sets  
      DatabasePermissionSet dbPermSet = new DatabasePermissionSet(DatabasePermission.AlterAnySchema);  
      dbPermSet.Add(DatabasePermission.AlterAnyUser);  
  
      DatabasePermissionSet dbPermSet2 = new DatabasePermissionSet(DatabasePermission.CreateType);  
      dbPermSet2.Add(DatabasePermission.CreateSchema);  
      dbPermSet2.Add(DatabasePermission.CreateTable);  
  
      // Creating Database roles  
      DatabaseRole role1 = new DatabaseRole(db, "Role1");  
      role1.Create();  
  
      DatabaseRole role2 = new DatabaseRole(db, "Role2");  
      role2.Create();  
  
      // Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name);  
      db.Grant(dbPermSet2, role2.Name);  
  
      // Adding members (Users / Roles) to Role  
      role1.AddMember("User1");  
  
      role2.AddMember("User2");  
  
      // Role1 becomes a member of Role2  
      role2.AddMember("Role1");  
  
      // Enumerating through explicit permissions granted to Role1  
      // enumerates all database permissions for the Grantee  
      DatabasePermissionInfo[] dbPermsRole1 = db.EnumDatabasePermissions("Role1");     
      foreach (DatabasePermissionInfo dbp in dbPermsRole1) {  
         Console.WriteLine(dbp.Grantee + " has " + dbp.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
   }  
}  
```  
  
 <span data-ttu-id="d973e-144">Esta é a versão do Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d973e-144">This is the Visual Basic version:</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
  
Public Class A  
   Public Shared Sub Main()  
      Dim svr As New Server()  
      Dim db As New Database(svr, "TESTDB")  
      db.Create()  
  
      ' Creating Logins  
      Dim login As New Login(svr, "Login1")  
      login.LoginType = LoginType.SqlLogin  
      login.Create("password@1")  
  
      Dim login2 As New Login(svr, "Login2")  
      login2.LoginType = LoginType.SqlLogin  
      login2.Create("password@1")  
  
      ' Creating Users in the database for the logins created  
      Dim user1 As New User(db, "User1")  
      user1.Login = "Login1"  
      user1.Create()  
  
      Dim user2 As New User(db, "User2")  
      user2.Login = "Login2"  
      user2.Create()  
  
      ' Creating database permission Sets  
      Dim dbPermSet As New DatabasePermissionSet(DatabasePermission.AlterAnySchema)  
      dbPermSet.Add(DatabasePermission.AlterAnyUser)  
  
      Dim dbPermSet2 As New DatabasePermissionSet(DatabasePermission.CreateType)  
      dbPermSet2.Add(DatabasePermission.CreateSchema)  
      dbPermSet2.Add(DatabasePermission.CreateTable)  
  
      ' Creating Database roles  
      Dim role1 As New DatabaseRole(db, "Role1")  
      role1.Create()  
  
      Dim role2 As New DatabaseRole(db, "Role2")  
      role2.Create()  
  
      ' Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name)  
      db.Grant(dbPermSet2, role2.Name)  
  
      ' Adding members (Users / Roles) to Role  
      role1.AddMember("User1")  
  
      role2.AddMember("User2")  
  
      ' Role1 becomes a member of Role2  
      role2.AddMember("Role1")  
  
      ' Enumerating through explicit permissions granted to Role1  
      ' enumerates all database permissions for the Grantee  
      Dim dbPermsRole1 As DatabasePermissionInfo() = db.EnumDatabasePermissions("Role1")  
      For Each dbp As DatabasePermissionInfo In dbPermsRole1  
         Console.WriteLine(dbp.Grantee + " has " & dbp.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine(" ")  
   End Sub  
End Class  
```  
