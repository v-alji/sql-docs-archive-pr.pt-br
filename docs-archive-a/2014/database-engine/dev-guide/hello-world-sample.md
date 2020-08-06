---
title: Exemplo de Olá, Mundo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: fed6c358-f5ee-4d4c-9ad6-089778383ba7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d5616c1d4ef6428a011c8e36be3757931039c9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685898"
---
# <a name="hello-world-sample"></a><span data-ttu-id="d7d6c-102">Exemplo Hello World</span><span class="sxs-lookup"><span data-stu-id="d7d6c-102">Hello World Sample</span></span>
  <span data-ttu-id="d7d6c-103">O exemplo Hello World demonstra as operações básicas envolvidas na criação, na implantação e no teste de um procedimento armazenado com base na integração CLR (common language runtime).</span><span class="sxs-lookup"><span data-stu-id="d7d6c-103">The Hello World sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="d7d6c-104">Esse exemplo também demonstra como retornar dados por meio de um registro, que é dinamicamente construído pelo procedimento armazenado e retornado ao chamador.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-104">This sample also demonstrates how to return data through a record, which is dynamically constructed by the stored procedure and returned to the caller.</span></span>  
  
 <span data-ttu-id="d7d6c-105">O `HelloWorld` procedimento armazenado retorna a cadeia de caracteres "Olá, mundo!"</span><span class="sxs-lookup"><span data-stu-id="d7d6c-105">The `HelloWorld` stored procedure returns the string "Hello world!"</span></span> <span data-ttu-id="d7d6c-106">em um conjunto de resultados que consiste em uma linha.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-106">in a result set consisting of one row.</span></span> <span data-ttu-id="d7d6c-107">Este exemplo ilustra alguns usos para as classes [Microsoft. SqlServer. Server. SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft. SqlServer. Server. SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) e [Microsoft. SqlServer. Server. pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span><span class="sxs-lookup"><span data-stu-id="d7d6c-107">This example illustrates some uses for the classes [Microsoft.SqlServer.Server.SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft.SqlServer.Server.SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) and [Microsoft.SqlServer.Server.Pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d7d6c-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d7d6c-108">Prerequisites</span></span>  
 <span data-ttu-id="d7d6c-109">Para criar e executar este projeto, o software a seguir deve estar instalado:</span><span class="sxs-lookup"><span data-stu-id="d7d6c-109">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d7d6c-110">ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-110">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="d7d6c-111">É possível obter o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express gratuitamente no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site [de Documentação e Amostras do](https://www.microsoft.com/sql-server/sql-server-editions-express)Express</span><span class="sxs-lookup"><span data-stu-id="d7d6c-111">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="d7d6c-112">O banco de dados AdventureWorks que está disponível no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site [do](https://go.microsoft.com/fwlink/?linkid=62796)Developer</span><span class="sxs-lookup"><span data-stu-id="d7d6c-112">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="d7d6c-113">.NET Framework SDK 2.0 ou posterior ou Microsoft Visual Studio 2005 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-113">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="d7d6c-114">Você pode obter o .NET Framework SDK gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-114">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="d7d6c-115">Além disso, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="d7d6c-115">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="d7d6c-116">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando deve ter a integração CLR habilitada.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="d7d6c-117">Para habilitar a integração CLR, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="d7d6c-117">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="d7d6c-118">Habilitando integração CLR</span><span class="sxs-lookup"><span data-stu-id="d7d6c-118">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="d7d6c-119">Execute os seguintes comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d7d6c-119">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="d7d6c-120">Para habilitar o CLR, é necessário ter a permissão `ALTER SETTINGS` de nível de servidor, que é mantida implicitamente por membros das funções de servidor fixas `sysadmin` e `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-120">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="d7d6c-121">O banco de dados AdventureWorks deve estar instalado na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-121">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="d7d6c-122">Se você não for um administrador da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está usando, será preciso solicitar que um administrador conceda a permissão **CreateAssembly** a você para que seja possível concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-122">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="d7d6c-123">Compilando o exemplo</span><span class="sxs-lookup"><span data-stu-id="d7d6c-123">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="d7d6c-124">Crie e execute o exemplo seguindo estas instruções:</span><span class="sxs-lookup"><span data-stu-id="d7d6c-124">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="d7d6c-125">Abra um prompt de comando do Visual Studio ou do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-125">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="d7d6c-126">Se necessário, crie um diretório para o seu exemplo.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-126">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="d7d6c-127">Para este exemplo, usaremos C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-127">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="d7d6c-128">Em c:\MySample, crie `HelloWorld.vb` (para o exemplo do Visual Basic) ou `HelloWorld.cs` (para o exemplo do C#) e copie o código de exemplo adequado do Visual Basic ou do C# (a seguir) no arquivo.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-128">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="d7d6c-129">Compile o código de exemplo no prompt de linha de comando executando uma das seguintes ações, de acordo com sua opção de linguagem.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-129">Compile the sample code from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `vbc C:HelloWorld.vb /target:library`  
  
    -   `csc /target:library HelloWorld.cs`  
  
5.  <span data-ttu-id="d7d6c-130">Copie o código de instalação [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `Install.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-130">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="d7d6c-131">Implante o assembly e o procedimento armazenado executando o seguinte</span><span class="sxs-lookup"><span data-stu-id="d7d6c-131">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql -v root = "C:\MySample\"`  
  
7.  <span data-ttu-id="d7d6c-132">Copie o script de comando de teste do [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `test.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-132">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
8.  <span data-ttu-id="d7d6c-133">Execute o script de teste com o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="d7d6c-133">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
9. <span data-ttu-id="d7d6c-134">Copie o script de limpeza [!INCLUDE[tsql](../../includes/tsql-md.md)] em um arquivo e salve-o como `cleanup.sql` no diretório de exemplo.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-134">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
10. <span data-ttu-id="d7d6c-135">Execute o script com o seguinte comando</span><span class="sxs-lookup"><span data-stu-id="d7d6c-135">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="d7d6c-136">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="d7d6c-136">Sample Code</span></span>  
 <span data-ttu-id="d7d6c-137">As listagens de código deste exemplo são as seguintes.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-137">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="d7d6c-138">C#</span><span class="sxs-lookup"><span data-stu-id="d7d6c-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
public partial class StoredProcedures  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld()  
    {  
        Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 12);  
        SqlDataRecord greetingRecord  
            = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
        greetingRecord.SetString(0, "Hello world!");  
        SqlContext.Pipe.Send(greetingRecord);  
    }  
};  
  
```  
  
 <span data-ttu-id="d7d6c-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7d6c-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public NotInheritable Class StoredProcedures  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorld()  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 12)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, "Hello World!")  
        SqlContext.Pipe.Send(greetingRecord)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="d7d6c-140">Este é o script de instalação do [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`) que implanta o assembly e cria o procedimento armazenado no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-140">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
set @SamplesPath = '$(root)'  
CREATE ASSEMBLY HelloWorld   
FROM @SamplesPath + 'HelloWorld.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorld  
--(  
--    @Greeting nvarchar(12) OUTPUT  
--)  
AS EXTERNAL NAME HelloWorld.[StoredProcedures].HelloWorld;  
GO  
```  
  
 <span data-ttu-id="d7d6c-141">Esse é o `test.sql`, que testa o exemplo por meio da execução do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-141">This is `test.sql`, which tests the sample by executing the stored procedure.</span></span>  
  
```  
use AdventureWorks  
go  
execute usp_HelloWorld  
  
USE AdventureWorks;  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
```  
  
 <span data-ttu-id="d7d6c-142">O [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir remove o assembly e o procedimento armazenado do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d7d6c-142">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7d6c-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7d6c-143">See Also</span></span>  
 [<span data-ttu-id="d7d6c-144">Cenários de uso e exemplos para a integração do CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="d7d6c-144">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
