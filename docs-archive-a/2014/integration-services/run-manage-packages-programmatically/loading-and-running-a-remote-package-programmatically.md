---
title: Carregando e executando um pacote remoto de forma programática | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- remote packages [Integration Services]
ms.assetid: 9f6ef376-3408-46bf-b5fa-fc7b18c689c9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 06565140ae8ea3603461e2944e242aa91213de47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684805"
---
# <a name="loading-and-running-a-remote-package-programmatically"></a><span data-ttu-id="45ff8-102">Carregando e executando um pacote remoto programaticamente</span><span class="sxs-lookup"><span data-stu-id="45ff8-102">Loading and Running a Remote Package Programmatically</span></span>
  <span data-ttu-id="45ff8-103">Para executar pacotes remotos de um computador local que não tenha o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado, inicie-os de forma que eles sejam executados no computador remoto em que o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="45ff8-103">To run remote packages from a local computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, start the packages so that they run on the remote computer on which [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span> <span data-ttu-id="45ff8-104">Para isso, o computador local deve usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, um serviço Web ou um componente remoto para iniciar os pacotes no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="45ff8-104">You do this by having the local computer use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, a Web service, or a remote component to start the packages on the remote computer.</span></span> <span data-ttu-id="45ff8-105">Se você tentar iniciar os pacotes remotos diretamente do computador local, eles serão carregados e tentarão executar do computador local.</span><span class="sxs-lookup"><span data-stu-id="45ff8-105">If you try to start the remote packages directly from the local computer, the packages will load onto and try to run from the local computer.</span></span> <span data-ttu-id="45ff8-106">Se o computador local não tiver o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado, os pacotes não serão executados.</span><span class="sxs-lookup"><span data-stu-id="45ff8-106">If the local computer does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, the packages will not run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45ff8-107">Não é possível executar pacotes fora do [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] em um computador cliente que não tem o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado e os termos do licenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] talvez não permitam a instalação do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] em computadores adicionais.</span><span class="sxs-lookup"><span data-stu-id="45ff8-107">You cannot run packages outside [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing might not let you install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> <span data-ttu-id="45ff8-108">O [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é um componente de servidor e não é redistribuível a computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="45ff8-108">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span>  
  
 <span data-ttu-id="45ff8-109">Alternadamente, você pode executar um pacote remoto de um computador local que tenha o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado.</span><span class="sxs-lookup"><span data-stu-id="45ff8-109">Alternately, you can run a remote package from a local computer that has [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed.</span></span> <span data-ttu-id="45ff8-110">Para obter mais informações, consulte [Carregando e executando um pacote local de forma programática](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="45ff8-110">For more information, see [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span></span>  
  
##  <a name="running-a-remote-package-on-the-remote-computer"></a><a name="top"></a> <span data-ttu-id="45ff8-111">Executando um pacote remoto no computador remoto</span><span class="sxs-lookup"><span data-stu-id="45ff8-111">Running a Remote Package on the Remote Computer</span></span>  
 <span data-ttu-id="45ff8-112">Como mencionado acima, há vários modos com os quais você pode executar um pacote remoto em um servidor remoto:</span><span class="sxs-lookup"><span data-stu-id="45ff8-112">As mentioned above, there are multiple ways in which you can run a remote package on a remote server:</span></span>  
  
-   [<span data-ttu-id="45ff8-113">Usar o SQL Server Agent para executar o pacote remoto de forma programática</span><span class="sxs-lookup"><span data-stu-id="45ff8-113">Use SQL Server Agent to run the remote package programmatically</span></span>](#agent)  
  
-   [<span data-ttu-id="45ff8-114">Usar um serviço Web ou componente remoto para executar o pacote remoto de forma programática</span><span class="sxs-lookup"><span data-stu-id="45ff8-114">Use a Web service or remote component to run the remote package programmatically</span></span>](#service)  
  
 <span data-ttu-id="45ff8-115">Quase todos os métodos que são usados neste tópico para carregar e salvar pacotes requerem uma referência ao assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="45ff8-115">Almost all the methods that are used in this topic to load and save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="45ff8-116">A exceção é a abordagem ADO.NET demonstrada neste tópico para executar o procedimento armazenado **sp_start_job** , que requer apenas uma referência a `System.Data` .</span><span class="sxs-lookup"><span data-stu-id="45ff8-116">The exception is the ADO.NET approach demonstrated in this topic for executing the **sp_start_job** stored procedure, which requires only a reference to `System.Data`.</span></span> <span data-ttu-id="45ff8-117">Depois que você acrescentar a referência ao assembly `Microsoft.SqlServer.ManagedDTS` em um projeto novo, importe o namespace <xref:Microsoft.SqlServer.Dts.Runtime> com uma instrução `using` ou `Imports`.</span><span class="sxs-lookup"><span data-stu-id="45ff8-117">After you add the reference to the `Microsoft.SqlServer.ManagedDTS` assembly in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
###  <a name="using-sql-server-agent-to-run-a-remote-package-programmatically-on-the-server"></a><a name="agent"></a> <span data-ttu-id="45ff8-118">Usando o SQL Server Agent para executar um pacote remoto de forma programática no servidor</span><span class="sxs-lookup"><span data-stu-id="45ff8-118">Using SQL Server Agent to Run a Remote Package Programmatically on the Server</span></span>  
 <span data-ttu-id="45ff8-119">O exemplo do código seguinte demonstra como usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent programaticamente para executar um pacote remoto no servidor.</span><span class="sxs-lookup"><span data-stu-id="45ff8-119">The following code sample demonstrates how to programmatically use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run a remote package on the server.</span></span> <span data-ttu-id="45ff8-120">O exemplo de código chama o procedimento armazenado do sistema, **sp_start_job**, que inicia um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="45ff8-120">The code sample calls the system stored procedure, **sp_start_job**, which launches a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="45ff8-121">O trabalho que o procedimento lança é chamado `RunSSISPackage`, e esse trabalho está no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="45ff8-121">The job that the procedure launches is named `RunSSISPackage`, and this job is on the remote computer.</span></span> <span data-ttu-id="45ff8-122">O trabalho `RunSSISPackage` executa o pacote no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="45ff8-122">The `RunSSISPackage` job then runs the package on the remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45ff8-123">O valor retornado do procedimento armazenado **sp_start_job** indica se ele pôde iniciar o trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent com êxito.</span><span class="sxs-lookup"><span data-stu-id="45ff8-123">The return value of the **sp_start_job** stored procedure indicates whether the stored procedure was able to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job successfully.</span></span> <span data-ttu-id="45ff8-124">O valor de retorno não indica se o pacote teve sucesso ou falhou.</span><span class="sxs-lookup"><span data-stu-id="45ff8-124">The return value does not indicate whether the package succeeded or failed.</span></span>  
  
 <span data-ttu-id="45ff8-125">Para obter informações sobre como solucionar problemas de pacotes executados nos trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consulte o artigo da Microsoft, [Um pacote do SSIS não é executado quando chamado em uma etapa de trabalho do SQL Server Agent](https://support.microsoft.com/kb/918760).</span><span class="sxs-lookup"><span data-stu-id="45ff8-125">For information on troubleshooting packages that are run from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, see the Microsoft article, [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760).</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="45ff8-126">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="45ff8-126">Sample Code</span></span>  
  
```vb  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
  
    Dim jobConnection As SqlConnection  
    Dim jobCommand As SqlCommand  
    Dim jobReturnValue As SqlParameter  
    Dim jobParameter As SqlParameter  
    Dim jobResult As Integer  
  
    jobConnection = New SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI")  
    jobCommand = New SqlCommand("sp_start_job", jobConnection)  
    jobCommand.CommandType = CommandType.StoredProcedure  
  
    jobReturnValue = New SqlParameter("@RETURN_VALUE", SqlDbType.Int)  
    jobReturnValue.Direction = ParameterDirection.ReturnValue  
    jobCommand.Parameters.Add(jobReturnValue)  
  
    jobParameter = New SqlParameter("@job_name", SqlDbType.VarChar)  
    jobParameter.Direction = ParameterDirection.Input  
    jobCommand.Parameters.Add(jobParameter)  
    jobParameter.Value = "RunSSISPackage"  
  
    jobConnection.Open()  
    jobCommand.ExecuteNonQuery()  
    jobResult = DirectCast(jobCommand.Parameters("@RETURN_VALUE").Value, Integer)  
    jobConnection.Close()  
  
    Select Case jobResult  
      Case 0  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.")  
      Case Else  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.")  
    End Select  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace LaunchSSISPackageAgent_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      SqlConnection jobConnection;  
      SqlCommand jobCommand;  
      SqlParameter jobReturnValue;  
      SqlParameter jobParameter;  
      int jobResult;  
  
      jobConnection = new SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI");  
      jobCommand = new SqlCommand("sp_start_job", jobConnection);  
      jobCommand.CommandType = CommandType.StoredProcedure;  
  
      jobReturnValue = new SqlParameter("@RETURN_VALUE", SqlDbType.Int);  
      jobReturnValue.Direction = ParameterDirection.ReturnValue;  
      jobCommand.Parameters.Add(jobReturnValue);  
  
      jobParameter = new SqlParameter("@job_name", SqlDbType.VarChar);  
      jobParameter.Direction = ParameterDirection.Input;  
      jobCommand.Parameters.Add(jobParameter);  
      jobParameter.Value = "RunSSISPackage";  
  
      jobConnection.Open();  
      jobCommand.ExecuteNonQuery();  
      jobResult = (Int32)jobCommand.Parameters["@RETURN_VALUE"].Value;  
      jobConnection.Close();  
  
      switch (jobResult)  
      {  
        case 0:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.");  
          break;  
        default:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.");  
          break;  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
 
  
###  <a name="using-a-web-service-or-remote-component-to-run-a-remote-package-programmatically"></a><a name="service"></a> <span data-ttu-id="45ff8-127">Usando um serviço Web ou componente remoto para executar um pacote remoto de forma programática</span><span class="sxs-lookup"><span data-stu-id="45ff8-127">Using a Web Service or Remote Component to Run a Remote Package Programmatically</span></span>  
 <span data-ttu-id="45ff8-128">A solução anterior para executar pacotes programaticamente no servidor não requer nenhum código personalizado no servidor.</span><span class="sxs-lookup"><span data-stu-id="45ff8-128">The previous solution for running packages programmatically on the server does not require any custom code on the server.</span></span> <span data-ttu-id="45ff8-129">Porém, você pode preferir uma solução que não confie no SQL Server Agent para executar pacotes.</span><span class="sxs-lookup"><span data-stu-id="45ff8-129">However, you may prefer a solution that does not rely on SQL Server Agent to execute packages.</span></span> <span data-ttu-id="45ff8-130">O exemplo seguinte demonstra um serviço Web que pode ser criado no servidor para iniciar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] localmente, e um aplicativo de teste que pode ser usado para chamar o serviço Web de um computador cliente.</span><span class="sxs-lookup"><span data-stu-id="45ff8-130">The following example demonstrates a Web service that can be created on the server to start [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages locally, and a test application that can be used to call the Web service from a client computer.</span></span> <span data-ttu-id="45ff8-131">Se preferir criar um componente remoto em vez de um serviço Web, use a mesma lógica de código com poucas alterações em um componente remoto.</span><span class="sxs-lookup"><span data-stu-id="45ff8-131">If you prefer to create a remote component instead of a Web service, you can use the same code logic with very few changes in a remote component.</span></span> <span data-ttu-id="45ff8-132">Porém, um componente remoto pode requerer configurações mais extensas que um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="45ff8-132">However a remote component may require more extensive configuration than a Web service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="45ff8-133">Com suas configurações padrão de autenticação e autorização, um serviço Web geralmente não tem permissões suficientes para acessar o SQL Server ou o sistema de arquivos para carregar e executar pacotes.</span><span class="sxs-lookup"><span data-stu-id="45ff8-133">With its default settings for authentication and authorization, a Web service generally does not have sufficient permissions to access SQL Server or the file system to load and execute packages.</span></span> <span data-ttu-id="45ff8-134">Talvez você precise atribuir permissões apropriadas ao serviço Web definindo suas configurações de autenticação e autorização no arquivo **web.config** e atribuindo permissões de banco de dados e sistema de arquivos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="45ff8-134">You may have to assign appropriate permissions to the Web service by configuring its authentication and authorization settings in the **web.config** file and assigning database and file system permissions as appropriate.</span></span> <span data-ttu-id="45ff8-135">Uma discussão completa sobre permissões de Web, banco de dados e sistema de arquivos estão além do escopo deste tópico.</span><span class="sxs-lookup"><span data-stu-id="45ff8-135">A complete discussion of Web, database, and file system permissions is beyond the scope of this topic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="45ff8-136">Os métodos da classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> para funcionar com o Repositório de Pacotes do SSIS dão suporte apenas a “.”, localhost ou ao nome do servidor local.</span><span class="sxs-lookup"><span data-stu-id="45ff8-136">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="45ff8-137">Você não pode usar "(local)".</span><span class="sxs-lookup"><span data-stu-id="45ff8-137">You cannot use "(local)".</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="45ff8-138">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="45ff8-138">Sample Code</span></span>  
 <span data-ttu-id="45ff8-139">Os exemplos de código seguintes mostram como criar e testar o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="45ff8-139">The following code samples show how to create and test the Web service.</span></span>  
  
#### <a name="creating-the-web-service"></a><span data-ttu-id="45ff8-140">Criando o serviço Web</span><span class="sxs-lookup"><span data-stu-id="45ff8-140">Creating the Web Service</span></span>  
 <span data-ttu-id="45ff8-141">Um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pode ser carregado diretamente de um arquivo, diretamente de um SQL Server ou do Armazenamento de Pacotes SSIS, que gerencia o armazenamento de pacotes no SQL Server e em pastas especiais de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="45ff8-141">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can be loaded directly from a file, directly from SQL Server, or from the SSIS Package Store, which manages package storage in both SQL Server and special file system folders.</span></span> <span data-ttu-id="45ff8-142">Esse exemplo suporta todas as opções disponíveis usando uma construção `Select Case` ou `switch` para selecionar a sintaxe apropriada para iniciar o pacote e concatenar os argumentos de entrada adequadamente.</span><span class="sxs-lookup"><span data-stu-id="45ff8-142">This sample supports all the available options by using a `Select Case` or `switch` construct to select the appropriate syntax for starting the package and to concatenate the input arguments appropriately.</span></span> <span data-ttu-id="45ff8-143">O método LaunchPackage do serviço Web retorna o resultado da execução do pacote como um valor inteiro em vez de um valor <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, de forma que os computadores cliente não requeiram uma referência a qualquer assembly do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45ff8-143">The LaunchPackage Web service method returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span>  
  
###### <a name="to-create-a-web-service-to-run-packages-on-the-server-programmatically"></a><span data-ttu-id="45ff8-144">Para criar um serviço Web para executar pacotes programaticamente no servidor</span><span class="sxs-lookup"><span data-stu-id="45ff8-144">To create a Web service to run packages on the server programmatically</span></span>  
  
1.  <span data-ttu-id="45ff8-145">Abra o Visual Studio e crie um projeto de serviço Web na linguagem de programação de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="45ff8-145">Open Visual Studio and create a Web service project in your preferred programming language.</span></span> <span data-ttu-id="45ff8-146">O código de exemplo usa o nome LaunchSSISPackageService para o projeto.</span><span class="sxs-lookup"><span data-stu-id="45ff8-146">The sample code uses the name LaunchSSISPackageService for the project.</span></span>  
  
2.  <span data-ttu-id="45ff8-147">Adicione uma referência a `Microsoft.SqlServer.ManagedDTS` e adicione uma `Imports` `using` instrução ou ao arquivo de código para o namespace **Microsoft. SqlServer. Dts. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="45ff8-147">Add a reference to `Microsoft.SqlServer.ManagedDTS` and add an `Imports` or `using` statement to the code file for the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
3.  <span data-ttu-id="45ff8-148">Cole o código de exemplo para o método LaunchPackage do serviço Web na classe.</span><span class="sxs-lookup"><span data-stu-id="45ff8-148">Paste the sample code for the LaunchPackage Web service method into the class.</span></span> <span data-ttu-id="45ff8-149">(O exemplo mostra os conteúdos inteiros da janela de código).</span><span class="sxs-lookup"><span data-stu-id="45ff8-149">(The sample shows the whole contents of the code window.)</span></span>  
  
4.  <span data-ttu-id="45ff8-150">Construa e teste o serviço Web fornecendo um conjunto de valores válidos para os argumentos de entrada do método LaunchPackage que aponte para um pacote existente.</span><span class="sxs-lookup"><span data-stu-id="45ff8-150">Build and test the Web service by providing a set of valid values for the input arguments of the LaunchPackage method that point to an existing package.</span></span> <span data-ttu-id="45ff8-151">Por exemplo, se o pacote package1.dtsx estiver armazenado no servidor em C:\Meus Pacotes, passe "arquivo" como valor de sourceType, "C:\Meus Pacotes" como valor de sourceLocation e "package1" (sem a extensão) como o valor de packageName.</span><span class="sxs-lookup"><span data-stu-id="45ff8-151">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of the sourceType, "C:\My Packages" as the value of sourceLocation, and "package1" (without the extension) as the value of packageName.</span></span>  
  
```vb  
Imports System.Web  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.IO  
  
<WebService(Namespace:="http://dtsue/")> _  
<WebServiceBinding(ConformsTo:=WsiProfiles.BasicProfile1_1)> _  
<Global.Microsoft.VisualBasic.CompilerServices.DesignerGenerated()> _  
Public Class LaunchSSISPackageService  
  Inherits System.Web.Services.WebService  
  
  ' LaunchPackage Method Parameters:  
  ' 1. sourceType: file, sql, dts  
  ' 2. sourceLocation: file system folder, (none), logical folder  
  ' 3. packageName: for file system, ".dtsx" extension is appended  
  
  <WebMethod()> _  
  Public Function LaunchPackage( _  
    ByVal sourceType As String, _  
    ByVal sourceLocation As String, _  
    ByVal packageName As String) As Integer 'DTSExecResult  
  
    Dim packagePath As String  
    Dim myPackage As Package  
    Dim integrationServices As New Application  
  
    ' Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName)  
  
    Select Case sourceType  
      Case "file"  
        ' Package is stored as a file.  
        ' Add extension if not present.  
        If String.IsNullOrEmpty(Path.GetExtension(packagePath)) Then  
          packagePath = String.Concat(packagePath, ".dtsx")  
        End If  
        If File.Exists(packagePath) Then  
          myPackage = integrationServices.LoadPackage(packagePath, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid file location: " & packagePath)  
        End If  
      Case "sql"  
        ' Package is stored in MSDB.  
        ' Combine logical path and package name.  
        If integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty) Then  
          myPackage = integrationServices.LoadFromSqlServer( _  
            packageName, "(local)", String.Empty, String.Empty, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case "dts"  
        ' Package is managed by SSIS Package Store.  
        ' Default logical paths are File System and MSDB.  
        If integrationServices.ExistsOnDtsServer(packagePath, ".") Then  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case Else  
        Throw New ApplicationException( _  
          "Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.")  
    End Select  
  
    Return myPackage.Execute()  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.IO;  
  
[WebService(Namespace = "http://dtsue/")]  
[WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
public class LaunchSSISPackageServiceCS : System.Web.Services.WebService  
{  
  public LaunchSSISPackageServiceCS()  
  {  
    }  
  
  // LaunchPackage Method Parameters:  
  // 1. sourceType: file, sql, dts  
  // 2. sourceLocation: file system folder, (none), logical folder  
  // 3. packageName: for file system, ".dtsx" extension is appended  
  
  [WebMethod]  
  public int LaunchPackage(string sourceType, string sourceLocation, string packageName)  
  {   
  
    string packagePath;  
    Package myPackage;  
    Application integrationServices = new Application();  
  
    // Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName);  
  
    switch(sourceType)  
    {  
      case "file":  
        // Package is stored as a file.  
        // Add extension if not present.  
        if (String.IsNullOrEmpty(Path.GetExtension(packagePath)))  
        {  
          packagePath = String.Concat(packagePath, ".dtsx");  
        }  
        if (File.Exists(packagePath))  
        {  
          myPackage = integrationServices.LoadPackage(packagePath, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid file location: "+packagePath);  
        }  
        break;  
      case "sql":  
        // Package is stored in MSDB.  
        // Combine logical path and package name.  
        if (integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty))  
        {  
          myPackage = integrationServices.LoadFromSqlServer(packageName, "(local)", String.Empty, String.Empty, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      case "dts":  
        // Package is managed by SSIS Package Store.  
        // Default logical paths are File System and MSDB.  
        if (integrationServices.ExistsOnDtsServer(packagePath, "."))  
        {  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      default:  
        throw new ApplicationException("Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.");  
    }  
  
    return (Int32)myPackage.Execute();  
  
  }  
  
}  
```  
  
#### <a name="testing-the-web-service"></a><span data-ttu-id="45ff8-152">Testando o serviço Web</span><span class="sxs-lookup"><span data-stu-id="45ff8-152">Testing the Web Service</span></span>  
 <span data-ttu-id="45ff8-153">O aplicativo de console do exemplo seguinte usa o serviço Web para executar um pacote.</span><span class="sxs-lookup"><span data-stu-id="45ff8-153">The following sample console application uses the Web service to run a package.</span></span> <span data-ttu-id="45ff8-154">O método LaunchPackage do serviço Web retorna o resultado da execução do pacote como um inteiro, em vez de um valor <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, de forma que os computadores cliente não exijam uma referência a nenhum assembly do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45ff8-154">The LaunchPackage method of the Web service returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span> <span data-ttu-id="45ff8-155">O exemplo cria uma enumeração privada cujos valores espelham os valores <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> para informar os resultados da execução.</span><span class="sxs-lookup"><span data-stu-id="45ff8-155">The sample creates a private enumeration whose values mirror the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> values to report the results of execution.</span></span>  
  
###### <a name="to-create-a-console-application-to-test-the-web-service"></a><span data-ttu-id="45ff8-156">Para criar um aplicativo de console para testar o serviço Web</span><span class="sxs-lookup"><span data-stu-id="45ff8-156">To create a console application to test the Web service</span></span>  
  
1.  <span data-ttu-id="45ff8-157">No Visual Studio, adicione um aplicativo de console novo usando a linguagem de programação de sua preferência para a mesma solução que contém o projeto de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="45ff8-157">In Visual Studio, add a new console application, using your preferred programming language, to the same solution that contains the Web service project.</span></span> <span data-ttu-id="45ff8-158">O código de exemplo usa o nome LaunchSSISPackageTest para o projeto.</span><span class="sxs-lookup"><span data-stu-id="45ff8-158">The sample code uses the name LaunchSSISPackageTest for the project.</span></span>  
  
2.  <span data-ttu-id="45ff8-159">Defina o aplicativo de console novo como o projeto de inicialização na solução.</span><span class="sxs-lookup"><span data-stu-id="45ff8-159">Set the new console application as the startup project in the solution.</span></span>  
  
3.  <span data-ttu-id="45ff8-160">Adicione uma referência Web ao projeto de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="45ff8-160">Add a Web reference for the Web service project.</span></span> <span data-ttu-id="45ff8-161">Se necessário, ajuste a declaração variável no código de exemplo para o nome que você atribui ao objeto de proxy de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="45ff8-161">If necessary, adjust the variable declaration in the sample code for the name that you assign to the Web service proxy object.</span></span>  
  
4.  <span data-ttu-id="45ff8-162">Cole o código de exemplo para a rotina principal e a enumeração privada no código.</span><span class="sxs-lookup"><span data-stu-id="45ff8-162">Paste the sample code for the Main routine and the private enumeration into the code.</span></span> <span data-ttu-id="45ff8-163">(O exemplo mostra os conteúdos inteiros da janela de código).</span><span class="sxs-lookup"><span data-stu-id="45ff8-163">(The sample shows the whole contents of the code window.)</span></span>  
  
5.  <span data-ttu-id="45ff8-164">Edite a linha de código, que chama o método LaunchPackage para fornecer um conjunto de valores válidos para os argumentos de entrada, que aponte para um pacote existente.</span><span class="sxs-lookup"><span data-stu-id="45ff8-164">Edit the line of code that calls the LaunchPackage method to provide a set of valid values for the input arguments that point to an existing package.</span></span> <span data-ttu-id="45ff8-165">Por exemplo, se package1.dtsx estiver armazenado no servidor em C:\Meus Pacotes, passe "arquivo" como valor de `sourceType`, "C:\Meus Pacotes" como valor de `sourceLocation` e "package1" (sem a extensão) como o valor de `packageName`.</span><span class="sxs-lookup"><span data-stu-id="45ff8-165">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of `sourceType`, "C:\My Packages" as the value of `sourceLocation`, and "package1" (without the extension) as the value of `packageName`.</span></span>  
  
```vb  
Module LaunchSSISPackageTest  
  
  Sub Main()  
  
    Dim launchPackageService As New LaunchSSISPackageService.LaunchSSISPackageService  
    Dim packageResult As Integer  
  
    Try  
      packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage")  
    Catch ex As Exception  
      ' The type of exception returned by a Web service is:  
      '  System.Web.Services.Protocols.SoapException  
      Console.WriteLine("The following exception occurred: " & ex.Message)  
    End Try  
  
    Console.WriteLine(CType(packageResult, PackageExecutionResult).ToString)  
    Console.ReadKey()  
  
  End Sub  
  
  Private Enum PackageExecutionResult  
    PackageSucceeded  
    PackageFailed  
    PackageCompleted  
    PackageWasCancelled  
  End Enum  
  
End Module  
```  
  
```csharp  
using System;  
  
namespace LaunchSSISPackageSvcTestCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS launchPackageService = new LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS();  
      int packageResult = 0;  
  
      try  
      {  
        packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage");  
      }  
      catch (Exception ex)  
      {  
        // The type of exception returned by a Web service is:  
        //  System.Web.Services.Protocols.SoapException  
        Console.WriteLine("The following exception occurred: " + ex.Message);  
      }  
  
      Console.WriteLine(((PackageExecutionResult)packageResult).ToString());  
      Console.ReadKey();  
  
    }  
  
    private enum PackageExecutionResult  
    {  
      PackageSucceeded,  
      PackageFailed,  
      PackageCompleted,  
      PackageWasCancelled  
    };  
  
  }  
}  
```  
  

  
## <a name="external-resources"></a><span data-ttu-id="45ff8-166">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="45ff8-166">External Resources</span></span>  
  
-   <span data-ttu-id="45ff8-167">Vídeo [Como automatizar a execução de pacote do SSIS usando o SQL Server Agent (vídeo do SQL Server)](https://technet.microsoft.com/sqlserver/ff686764.aspx), em technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="45ff8-167">Video, [How to: Automate SSIS Package Execution by Using the SQL Server Agent (SQL Server Video)](https://technet.microsoft.com/sqlserver/ff686764.aspx), on technet.microsoft.com</span></span>  
  
<span data-ttu-id="45ff8-168">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="45ff8-168">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="45ff8-169">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="45ff8-169">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="45ff8-170">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="45ff8-170">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="45ff8-171">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="45ff8-171">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ff8-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45ff8-172">See Also</span></span>  
 <span data-ttu-id="45ff8-173">[Compreendendo as diferenças entre a execução local e remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="45ff8-173">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="45ff8-174">[Carregando e executando um pacote local programaticamente](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="45ff8-174">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 [<span data-ttu-id="45ff8-175">Carregando a saída de um pacote local</span><span class="sxs-lookup"><span data-stu-id="45ff8-175">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
