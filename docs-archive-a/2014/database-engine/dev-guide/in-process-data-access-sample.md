---
title: Exemplo de acesso a dados em processo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 155be272-4f9a-4d86-9f4f-714c4f45b49a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 62201474be26abdc5fe6e8f470b4896d51b9b106
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685896"
---
# <a name="in-process-data-access-sample"></a><span data-ttu-id="6a16c-102">Exemplo de acesso a dados em processo</span><span class="sxs-lookup"><span data-stu-id="6a16c-102">In-Process Data Access Sample</span></span>
  <span data-ttu-id="6a16c-103">O exemplo `InProcessDataAccess` contém diversas funções simples que demonstram vários recursos do provedor de acesso a dados em processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CLR.</span><span class="sxs-lookup"><span data-stu-id="6a16c-103">The `InProcessDataAccess` sample contains a number of simple functions that demonstrate various features of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CLR in-process data access provider.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6a16c-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6a16c-104">Prerequisites</span></span>  
 <span data-ttu-id="6a16c-105">Para criar e executar este projeto, o software a seguir deve estar instalado:</span><span class="sxs-lookup"><span data-stu-id="6a16c-105">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6a16c-106">ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="6a16c-106">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="6a16c-107">É possível obter o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express gratuitamente no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site [de Documentação e Amostras do](https://www.microsoft.com/sql-server/sql-server-editions-express)Express</span><span class="sxs-lookup"><span data-stu-id="6a16c-107">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="6a16c-108">O banco de dados AdventureWorks que está disponível no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site [do](https://go.microsoft.com/fwlink/?linkid=62796)Developer</span><span class="sxs-lookup"><span data-stu-id="6a16c-108">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="6a16c-109">.NET Framework SDK 2.0 ou posterior ou Microsoft Visual Studio 2005 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6a16c-109">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="6a16c-110">Você pode obter o .NET Framework SDK gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="6a16c-110">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="6a16c-111">Além disso, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="6a16c-111">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="6a16c-112">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando deve ter a integração CLR habilitada.</span><span class="sxs-lookup"><span data-stu-id="6a16c-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="6a16c-113">Para habilitar a integração CLR, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="6a16c-113">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="6a16c-114">Habilitando integração CLR</span><span class="sxs-lookup"><span data-stu-id="6a16c-114">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="6a16c-115">Execute os seguintes comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="6a16c-115">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="6a16c-116">Para habilitar o CLR, é necessário ter a permissão `ALTER SETTINGS` de nível de servidor, que é mantida implicitamente por membros das funções de servidor fixas `sysadmin` e `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="6a16c-116">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="6a16c-117">O banco de dados AdventureWorks deve estar instalado na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando.</span><span class="sxs-lookup"><span data-stu-id="6a16c-117">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="6a16c-118">Se você não for um administrador da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está usando, será preciso solicitar que um administrador conceda a permissão **CreateAssembly** a você para que seja possível concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="6a16c-118">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="6a16c-119">Compilando o exemplo</span><span class="sxs-lookup"><span data-stu-id="6a16c-119">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="6a16c-120">Crie e execute o exemplo seguindo estas instruções:</span><span class="sxs-lookup"><span data-stu-id="6a16c-120">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="6a16c-121">Abra um prompt de comando do Visual Studio ou do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a16c-121">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="6a16c-122">Se necessário, crie um diretório para o seu exemplo.</span><span class="sxs-lookup"><span data-stu-id="6a16c-122">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="6a16c-123">Para este exemplo, usaremos C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="6a16c-123">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="6a16c-124">Em c:\MySample, crie `inprocda.vb` (para o exemplo do Visual Basic) ou `inprocda.cs` (para o exemplo do C#) e copie o código de exemplo adequado do Visual Basic ou do C# (a seguir) no arquivo.</span><span class="sxs-lookup"><span data-stu-id="6a16c-124">In c:\MySample, create `inprocda.vb` (for the Visual Basic sample) or `inprocda.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="6a16c-125">Compile o código de exemplo no assembly necessário na linha de comando por meio da execução de uma das seguintes opções, dependendo de sua opção de idioma.</span><span class="sxs-lookup"><span data-stu-id="6a16c-125">Compile the sample code into the required assembly from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /target:library InProcDA.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.XML.dll /target:library inprocda.cs`  
  
5.  <span data-ttu-id="6a16c-126">Copie o código de instalação [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `Install.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="6a16c-126">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="6a16c-127">Se o exemplo tiver sido instalado em um diretório diferente de `C:\MySample\`, edite o arquivo `Install.sql` conforme indicado para apontar para esse local.</span><span class="sxs-lookup"><span data-stu-id="6a16c-127">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
7.  <span data-ttu-id="6a16c-128">Implante o assembly, o procedimento armazenado e as funções com a seguinte execução</span><span class="sxs-lookup"><span data-stu-id="6a16c-128">Deploy the assembly, stored procedure and functions by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
8.  <span data-ttu-id="6a16c-129">Copie o código de instalação [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `test.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="6a16c-129">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `test.sql` in the sample directory.</span></span>  
  
9. <span data-ttu-id="6a16c-130">Teste o aplicativo por meio da execução da seguinte linha no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="6a16c-130">Test the application by executing the following line at the command prompt:</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
10. <span data-ttu-id="6a16c-131">Copie o script de limpeza [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `cleanup.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="6a16c-131">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
11. <span data-ttu-id="6a16c-132">Execute o script com o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="6a16c-132">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="6a16c-133">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="6a16c-133">Sample Code</span></span>  
 <span data-ttu-id="6a16c-134">As listagens de código deste exemplo são as seguintes.</span><span class="sxs-lookup"><span data-stu-id="6a16c-134">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="6a16c-135">C#</span><span class="sxs-lookup"><span data-stu-id="6a16c-135">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;  
public sealed class DataAccessDemo  
{  
        private DataAccessDemo()  
        {  
        }  
  
        /// <summary>  
/// Simple example to send a message to the client.  
/// </summary>  
public static void SendMessage(string msg)  
{  
SqlContext.Pipe.Send("Message from server: " + msg);  
}  
  
/// <summary>  
/// Simple example of performing data access within  
/// a function  
/// </summary>  
/// <returns></returns>  
        [Microsoft.SqlServer.Server.SqlFunction(DataAccess = Microsoft.SqlServer.Server.DataAccessKind.Read)]  
public static string ReportSqlVersion()  
{  
            using (SqlConnection conn = new SqlConnection("context connection=true"))  
            {  
                //create a command from the current context  
                SqlCommand cmd = conn.CreateCommand();  
  
                //execute something  
                cmd.CommandText = "select @@version";  
  
                conn.Open();  
                //return results as scalar  
                return (string)cmd.ExecuteScalar();  
            }  
}  
  
/// <summary>  
/// Create a result set on the fly and send it to the client.  
/// </summary>  
public static void SendTransientResultSet()  
{  
//create the metadata for the columns  
            Microsoft.SqlServer.Server.SqlMetaData[] columnSchema   
                = new Microsoft.SqlServer.Server.SqlMetaData[] {  
new Microsoft.SqlServer.Server.SqlMetaData("stringcol", SqlDbType.NVarChar, 128)  
};  
  
//create a record based on that metadata  
            SqlDataRecord newRecord = new SqlDataRecord(columnSchema);  
  
//populate it  
newRecord.SetString(0, "Hello World!");  
  
//send it  
SqlContext.Pipe.Send(newRecord);  
}  
  
/// <summary>  
/// Execute a command and send the results to the client directly.  
/// </summary>  
public static void ExecuteToClient()  
{  
            using (SqlConnection conn = new SqlConnection("context connection=true"))  
            {  
                SqlCommand cmd = conn.CreateCommand();  
  
                cmd.CommandText = "select @@version";  
                conn.Open();  
                SqlContext.Pipe.ExecuteAndSend(cmd);  
            }  
}  
  
/// <summary>  
/// Execute a command and send the resultig reader to the client  
/// </summary>  
public static void SendReaderToClient()  
{  
            using (SqlConnection conn = new SqlConnection("context connection=true"))  
            {  
                SqlCommand cmd = conn.CreateCommand();  
  
                cmd.CommandText = "select @@version";  
                conn.Open();  
                SqlDataReader rdr = cmd.ExecuteReader();  
                try  
                {  
                    SqlContext.Pipe.Send(rdr);  
                }  
                finally  
                {  
                    rdr.Close();  
                }  
            }  
}  
  
};  
```  
  
 <span data-ttu-id="6a16c-136">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a16c-136">Visual Basic</span></span>  
  
```  
Imports Microsoft.SqlServer.Server  
Imports Microsoft.VisualBasic  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Diagnostics  
Partial Public NotInheritable Class DataAccessDemo  
    Private Sub New()  
    End Sub  
  
    ''' <summary>  
    ''' Simple example of performing data access within a function  
    ''' </summary>  
    ''' <returns></returns>  
    <SqlFunction(DataAccess:=DataAccessKind.Read)> _  
    Public Shared Function ReportSqlVersion() As SqlString  
        Using conn As New SqlConnection("context connection=true")  
            'create a command from the current context  
            Dim cmd As SqlCommand = conn.CreateCommand()  
  
            'execute something  
            cmd.CommandText = "SELECT @@VERSION"  
  
            conn.Open()  
  
            'return results as scalar  
            Return CType(cmd.ExecuteScalar(), String)  
        End Using  
    End Function  
  
    ''' <summary>  
    ''' Simple example to send a message to the client.  
    ''' </summary>  
    Public Shared Sub SendMessage(ByVal msg As String)  
        SqlContext.Pipe.Send(("Message from server: " & msg))  
    End Sub  
  
    ''' <summary>  
    ''' Create a result set on the fly and send it to the client.  
    ''' </summary>  
    Public Shared Sub SendTransientResultSet()  
        'create the metadata for the columns  
        Dim columnSchema() As Microsoft.SqlServer.Server.SqlMetaData _  
            = {New SqlMetaData("stringcol", SqlDbType.NVarChar, 128)}  
  
        'create a record based on that metadata  
        Dim newRecord As New SqlDataRecord(columnSchema)  
  
        'populate it  
        newRecord.SetString(0, "Hello World!")  
  
        'send it  
        SqlContext.Pipe.Send(newRecord)  
    End Sub  
  
    ''' <summary>  
    ''' Execute a command and send the results to the client directly.  
    ''' </summary>  
    Public Shared Sub ExecuteToClient()  
        Using conn As New SqlConnection("context connection=true")  
            Dim cmd As SqlCommand = conn.CreateCommand()  
  
            cmd.CommandText = "SELECT @@VERSION"  
            conn.Open()  
            SqlContext.Pipe.ExecuteAndSend(cmd)  
        End Using  
    End Sub  
  
    ''' <summary>  
    ''' Execute a command and send the resulting reader to the client  
    ''' </summary>  
    Public Shared Sub SendReaderToClient()  
        Using conn As New SqlConnection("context connection=true")  
            Dim cmd As SqlCommand = conn.CreateCommand()  
            cmd.CommandText = "SELECT @@VERSION"  
            conn.Open()  
            Dim rdr As SqlDataReader = cmd.ExecuteReader()  
            Try  
                SqlContext.Pipe.Send(rdr)  
            Finally  
                rdr.Close()  
            End Try  
        End Using  
    End Sub  
  
End Class  
  
```  
  
 <span data-ttu-id="6a16c-137">Este é o script de instalação do [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`) que implanta o assembly e cria os procedimentos armazenados e a função necessários para este exemplo.</span><span class="sxs-lookup"><span data-stu-id="6a16c-137">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedures and function required by this example.</span></span>  
  
```  
USE AdventureWorks;  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendMessage')  
DROP PROCEDURE SendMessage;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendTransientResultSet')  
DROP PROCEDURE SendTransientResultSet;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'ExecuteToClient')  
DROP PROCEDURE ExecuteToClient;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendReaderToClient')  
DROP PROCEDURE SendReaderToClient;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE name = N'ReportSqlVersion' and (type = 'FS' or type = 'FT'))    
DROP FUNCTION [ReportSqlVersion];  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = N'InProcDA') DROP ASSEMBLY InProcDA;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
  
-- You may need to modify the value of the this variable if you have installed the sample someplace other than the default location.  
set @SamplesPath = N'C:\MySample\'  
CREATE ASSEMBLY InProcDA FROM @SamplesPath + 'InProcDA.dll'  
WITH permission_set = SAFE;  
GO  
  
CREATE PROCEDURE [SendMessage] @msg nvarchar(4000)  
AS  
EXTERNAL NAME [InProcDA].[DataAccessDemo].[SendMessage];  
GO  
  
CREATE FUNCTION [ReportSqlVersion]() RETURNS nvarchar(4000)  
AS EXTERNAL NAME [InProcDA].[DataAccessDemo].[ReportSqlVersion];  
GO  
  
CREATE PROCEDURE [SendTransientResultSet]  
AS  
EXTERNAL NAME [InProcDA].[DataAccessDemo].[SendTransientResultSet];  
GO  
  
CREATE PROCEDURE [ExecuteToClient]  
AS  
EXTERNAL NAME [InProcDA].[DataAccessDemo].[ExecuteToClient];  
GO  
  
CREATE PROCEDURE [SendReaderToClient]  
AS  
EXTERNAL NAME [InProcDA].[DataAccessDemo].[SendReaderToClient];  
GO  
```  
  
 <span data-ttu-id="6a16c-138">O seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)] ( `test.sql` ) testa o exemplo, exercitando os procedimentos armazenados e a função definida neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="6a16c-138">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] (`test.sql`) tests the example by exercising the stored procedures and function defined in this sample.</span></span>  
  
```  
USE AdventureWorks;  
GO  
  
-- send a message to the client  
EXEC SendMessage  N'This is a test message.';  
  
-- exec a function that does data access  
SELECT dbo.ReportSqlVersion();  
  
-- exec the proc that sends a result set to the client  
EXEC SendTransientResultSet;  
  
EXEC ExecuteToClient;  
  
EXEC SendReaderToClient;  
  
USE master;  
GO  
  
```  
  
 <span data-ttu-id="6a16c-139">O [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir remove o assembly, a função e os procedimentos armazenados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6a16c-139">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly, function and stored procedures from the database.</span></span>  
  
```  
  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendMessage')  
DROP PROCEDURE SendMessage;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendTransientResultSet')  
DROP PROCEDURE SendTransientResultSet;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'ExecuteToClient')  
DROP PROCEDURE ExecuteToClient;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'SendReaderToClient')  
DROP PROCEDURE SendReaderToClient;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE name = N'ReportSqlVersion' and (type = 'FS' or type = 'FT'))    
DROP FUNCTION [ReportSqlVersion];  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = N'InProcDA') DROP ASSEMBLY InProcDA;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a16c-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a16c-140">See Also</span></span>  
 [<span data-ttu-id="6a16c-141">Cenários de uso e exemplos para a integração do CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="6a16c-141">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
