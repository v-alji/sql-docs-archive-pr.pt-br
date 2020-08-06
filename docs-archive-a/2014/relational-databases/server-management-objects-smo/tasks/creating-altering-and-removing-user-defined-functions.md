---
title: Criando, alterando e removendo funções definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- user-defined functions [SMO]
ms.assetid: 0ebebd3b-0775-41c2-989d-aa4cf81af12a
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9ff6d1b6e675d41e96f26fc24e6e0dd4ba69454
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582926"
---
# <a name="creating-altering-and-removing-user-defined-functions"></a><span data-ttu-id="3af82-102">Criando, alterando e removendo funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="3af82-102">Creating, Altering, and Removing User-Defined Functions</span></span>
  <span data-ttu-id="3af82-103">O <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> objeto fornece funcionalidade que permite que os usuários gerenciem funções definidas pelo usuário programaticamente no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3af82-103">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object provides functionality that lets users programmatically manage user-defined functions in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3af82-104">Funções definidas pelo usuário dão suporte a parâmetros de entrada e saída, e também a referências diretas a colunas de tabela.</span><span class="sxs-lookup"><span data-stu-id="3af82-104">User-defined functions support input and output parameters, and also support direct references to table columns.</span></span>  
  
 <span data-ttu-id="3af82-105">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] exige o registro de assemblies dentro de um banco de dados antes de sua utilização dentro de procedimentos armazenados, funções definidas pelo usuário, gatilhos e tipos de dados definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3af82-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires assemblies to be registered within a database before these can be used inside stored procedures, user defined functions, triggers, and user defined data types.</span></span> <span data-ttu-id="3af82-106">O SMO dá suporte a esse recurso com o objeto <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly>.</span><span class="sxs-lookup"><span data-stu-id="3af82-106">SMO supports this feature with the <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object.</span></span>  
  
 <span data-ttu-id="3af82-107">O objeto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> referencia o assembly .NET com as propriedades <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A> e <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A>.</span><span class="sxs-lookup"><span data-stu-id="3af82-107">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references the .NET assembly with the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A>, and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A> properties.</span></span>  
  
 <span data-ttu-id="3af82-108">Quando o objeto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> referenciar um assembly .NET, registre o assembly criando um objeto <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> e adicionando-o ao objeto <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection>, que pertence ao objeto <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="3af82-108">When the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references a .NET assembly, you must register the assembly by creating a <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object and adding it to the <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection> object, which belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3af82-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3af82-109">Example</span></span>  
 <span data-ttu-id="3af82-110">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3af82-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="3af82-111">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="3af82-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-basic"></a><span data-ttu-id="3af82-112">Criando uma função escalar definida pelo usuário no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3af82-112">Creating a Scalar User-Defined Function in Visual Basic</span></span>  
 <span data-ttu-id="3af82-113">Este exemplo de código mostra como criar e remover uma função escalar definida pelo usuário que possui um parâmetro do objeto <xref:System.DateTime> de entrada e um tipo de retorno inteiro no [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af82-113">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="3af82-114">A função definida pelo usuário é criada no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3af82-114">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="3af82-115">O exemplo cria uma função definida pelo usuário, ISOweek, que usa um argumento de data e calcula o número da semana ISO.</span><span class="sxs-lookup"><span data-stu-id="3af82-115">The example creates a user-defined function, ISOweek, which takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="3af82-116">Para que essa função calcule corretamente, defina a opção DATEFIRST do banco de dados como 1 antes da função ser chamada.</span><span class="sxs-lookup"><span data-stu-id="3af82-116">For this function to calculate correctly, the database DATEFIRST option must be set to 1 before the function is called.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBUserDefFuncs1](SMO How to#SMO_VBUserDefFuncs1)]  -->  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-c"></a><span data-ttu-id="3af82-117">Criando uma função escalar definida pelo usuário no Visual C#</span><span class="sxs-lookup"><span data-stu-id="3af82-117">Creating a Scalar User-Defined Function in Visual C#</span></span>  
 <span data-ttu-id="3af82-118">Este exemplo de código mostra como criar e remover uma função escalar definida pelo usuário que possui um parâmetro do objeto <xref:System.DateTime> de entrada e um tipo de retorno inteiro no [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af82-118">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="3af82-119">A função definida pelo usuário é criada no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3af82-119">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="3af82-120">O exemplo cria a função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3af82-120">The example creates the user-defined function.</span></span> <span data-ttu-id="3af82-121">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="3af82-121">`ISOweek`.</span></span> <span data-ttu-id="3af82-122">Essa função usa um argumento de data e calcula o número da semana ISO.</span><span class="sxs-lookup"><span data-stu-id="3af82-122">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="3af82-123">Para que essa função seja calculada corretamente, a opção `DATEFIRST` do banco de dados deve ser definida como `1` antes da função ser chamada.</span><span class="sxs-lookup"><span data-stu-id="3af82-123">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
           Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
           Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a UserDefinedFunction object variable by supplying the parent database and the name arguments in the constructor.   
            UserDefinedFunction udf = new UserDefinedFunction(db, "IsOWeek");  
  
            //Set the TextMode property to false and then set the other properties.   
            udf.TextMode = false;  
            udf.DataType = DataType.Int;  
            udf.ExecutionContext = ExecutionContext.Caller;  
            udf.FunctionType = UserDefinedFunctionType.Scalar;  
            udf.ImplementationType = ImplementationType.TransactSql;  
  
            //Add a parameter.   
  
     UserDefinedFunctionParameter par = new UserDefinedFunctionParameter(udf, "@DATE", DataType.DateTime);  
            udf.Parameters.Add(par);  
  
            //Set the TextBody property to define the user-defined function.   
            udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;";  
  
            //Create the user-defined function on the instance of SQL Server.   
            udf.Create();  
  
            //Remove the user-defined function.   
            udf.Drop();  
        }  
```  
  
## <a name="creating-a-scalar-user-defined-function-in-powershell"></a><span data-ttu-id="3af82-124">Criando uma função escalar definida pelo usuário no PowerShell</span><span class="sxs-lookup"><span data-stu-id="3af82-124">Creating a Scalar User-Defined Function in PowerShell</span></span>  
 <span data-ttu-id="3af82-125">Este exemplo de código mostra como criar e remover uma função escalar definida pelo usuário que possui um parâmetro do objeto <xref:System.DateTime> de entrada e um tipo de retorno inteiro no [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af82-125">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="3af82-126">A função definida pelo usuário é criada no banco de dados [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3af82-126">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="3af82-127">O exemplo cria a função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3af82-127">The example creates the user-defined function.</span></span> <span data-ttu-id="3af82-128">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="3af82-128">`ISOweek`.</span></span> <span data-ttu-id="3af82-129">Essa função usa um argumento de data e calcula o número da semana ISO.</span><span class="sxs-lookup"><span data-stu-id="3af82-129">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="3af82-130">Para que essa função seja calculada corretamente, a opção `DATEFIRST` do banco de dados deve ser definida como `1` antes da função ser chamada.</span><span class="sxs-lookup"><span data-stu-id="3af82-130">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a user defined function object variable by supplying the parent database and name arguments in the constructor.
$udf  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunction -argumentlist $db, "IsOWeek"  
  
# Set the TextMode property to false and then set the other properties.
$udf.TextMode = $false  
$udf.DataType = [Microsoft.SqlServer.Management.SMO.DataType]::Int
$udf.ExecutionContext = [Microsoft.SqlServer.Management.SMO.ExecutionContext]::Caller  
$udf.FunctionType = [Microsoft.SqlServer.Management.SMO.UserDefinedFunctionType]::Scalar  
$udf.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Define a Parameter object variable by supplying the parent function, name and type arguments in the constructor.  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$par  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunctionParameter -argumentlist $udf, "@DATE",$type  
  
# Add the parameter to the function  
$udf.Parameters.Add($par)  
  
#Set the TextBody property to define the user-defined function.
$udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;"  
  
# Create the user-defined function on the instance of SQL Server.
$udf.Create()  
  
# Remove the user-defined function.
$udf.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="3af82-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3af82-131">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>  
