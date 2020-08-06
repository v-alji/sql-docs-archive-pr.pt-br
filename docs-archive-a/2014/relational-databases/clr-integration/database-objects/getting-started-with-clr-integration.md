---
title: Introdução com integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration]
- namespaces [CLR integration]
- database objects [CLR integration], about CLR integration
- stored procedures [CLR integration]
- common language runtime [SQL Server], about CLR integration
- building database objects [CLR integration], about CLR integration
- common language runtime [SQL Server], stored procedures
- common language runtime [SQL Server], namespaces
- Hello World example [CLR integration]
- library [CLR integration]
ms.assetid: c73e628a-f54a-411a-bfe3-6dae519316cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 43c97e411a4d74aa48b88f2edbbe420ae17f3534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568632"
---
# <a name="getting-started-with-clr-integration"></a><span data-ttu-id="6a19b-102">Introdução à integração CLR</span><span class="sxs-lookup"><span data-stu-id="6a19b-102">Getting Started with CLR Integration</span></span>
  <span data-ttu-id="6a19b-103">Este tópico fornece uma visão geral dos namespaces e das bibliotecas necessárias para compilar objetos de banco de dados usando a [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integração com o .NET Framework Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6a19b-103">This topic provides an overview of the namespaces and libraries required to compile database objects using the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="6a19b-104">O tópico também mostra como escrever, compilar e executar um procedimento armazenado CLR simples escrito no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="6a19b-104">The topic also shows you how to write, compile, and run a simple CLR stored procedure written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
## <a name="required-namespaces"></a><span data-ttu-id="6a19b-105">Namespaces obrigatórios</span><span class="sxs-lookup"><span data-stu-id="6a19b-105">Required Namespaces</span></span>  
 <span data-ttu-id="6a19b-106">A partir do [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a19b-106">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6a19b-107">A funcionalidade de integração CLR é exposta em um assembly chamado system.data.dll, que faz parte do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a19b-107">CLR integration functionality is exposed in an assembly called system.data.dll, which is part of the .NET Framework.</span></span> <span data-ttu-id="6a19b-108">Esse assembly pode ser localizado no GAC (cache de assembly global), bem como no diretório do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a19b-108">This assembly can be found in the Global Assembly Cache (GAC) as well as in the .NET Framework directory.</span></span> <span data-ttu-id="6a19b-109">Normalmente uma referência a esse assembly é adicionada automaticamente por ferramentas de linha de comando e pelo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, por isso não é necessário adicioná-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="6a19b-109">A reference to this assembly is typically added automatically by both command line tools and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, so there is no need to add it manually.</span></span>  
  
 <span data-ttu-id="6a19b-110">O assembly system.data.dll contém os namespaces a seguir, que são necessários para compilar objetos de banco de dados de CLR:</span><span class="sxs-lookup"><span data-stu-id="6a19b-110">The system.data.dll assembly contains the following namespaces, which are required for compiling CLR database objects:</span></span>  
  
 `System.Data`  
  
 `System.Data.Sql`  
  
 `Microsoft.SqlServer.Server`  
  
 `System.Data.SqlTypes`  
  
## <a name="writing-a-simple-hello-world-stored-procedure"></a><span data-ttu-id="6a19b-111">Escrevendo um simples procedimento armazenado "Hello World"</span><span class="sxs-lookup"><span data-stu-id="6a19b-111">Writing A Simple "Hello World" Stored Procedure</span></span>  
 <span data-ttu-id="6a19b-112">Copie e cole o seguinte código em Visual C# ou [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic em um editor de texto e salve-o em um arquivo chamado "helloworld.cs" ou "helloworld.vb".</span><span class="sxs-lookup"><span data-stu-id="6a19b-112">Copy and paste the following Visual C# or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic code into a text editor, and save it in a file named "helloworld.cs" or "helloworld.vb".</span></span>  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlTypes;  
  
public class HelloWorldProc  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld(out string text)  
    {  
        SqlContext.Pipe.Send("Hello world!" + Environment.NewLine);  
        text = "Hello world!";  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlTypes  
Imports System.Runtime.InteropServices  
  
Public Class HelloWorldProc  
    <Microsoft.SqlServer.Server.SqlProcedure> _   
    Public Shared  Sub HelloWorld(<Out()> ByRef text as String)  
        SqlContext.Pipe.Send("Hello world!" & Environment.NewLine)  
        text = "Hello world!"  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="6a19b-113">Esse programa simples contém um único método estático em uma classe pública.</span><span class="sxs-lookup"><span data-stu-id="6a19b-113">This simple program contains a single static method on a public class.</span></span> <span data-ttu-id="6a19b-114">Esse método usa duas classes novas, `SqlContext` e `SqlPipe`, para criar objetos de banco de dados gerenciados para produzir uma mensagem de texto simples.</span><span class="sxs-lookup"><span data-stu-id="6a19b-114">This method uses two new classes, `SqlContext` and `SqlPipe`, for creating managed database objects to output a simple text message.</span></span> <span data-ttu-id="6a19b-115">O método também atribui a cadeia de caracteres "Olá, mundo!"</span><span class="sxs-lookup"><span data-stu-id="6a19b-115">The method also assigns the string "Hello world!"</span></span> <span data-ttu-id="6a19b-116">como o valor de um parâmetro out.</span><span class="sxs-lookup"><span data-stu-id="6a19b-116">as the value of an out parameter.</span></span> <span data-ttu-id="6a19b-117">Esse método pode ser declarado como um procedimento armazenado no [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="6a19b-117">This method can be declared as a stored procedure in [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] stored procedure.</span></span>  
  
 <span data-ttu-id="6a19b-118">Agora vamos compilar esse programa como uma biblioteca, carregá-lo no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e executá-lo como um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="6a19b-118">We will now compile this program as a library, load it into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and run it as a stored procedure.</span></span>  
  
## <a name="compiling-the-hello-world-stored-procedure"></a><span data-ttu-id="6a19b-119">Compilando o procedimento armazenado "Hello World"</span><span class="sxs-lookup"><span data-stu-id="6a19b-119">Compiling the "Hello World" Stored Procedure</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)]<span data-ttu-id="6a19b-120">.NET Framework arquivos de redistribuição por padrão.</span><span class="sxs-lookup"><span data-stu-id="6a19b-120">.NET Framework redistribution files by default.</span></span> <span data-ttu-id="6a19b-121">Esses arquivos incluem csc.exe e vbc.exe, os compiladores de linha de comando para os programas Visual C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6a19b-121">These files include csc.exe and vbc.exe, the command-line compilers for Visual C# and Visual Basic programs.</span></span> <span data-ttu-id="6a19b-122">Para compilar nosso exemplo, você precisa modificar sua variável de caminho para que aponte para o diretório que contém csc.exe ou vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="6a19b-122">In order to compile our sample, you must modify your path variable to point to the directory containing csc.exe or vbc.exe.</span></span> <span data-ttu-id="6a19b-123">A seguir está o caminho de instalação padrão do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a19b-123">The following is the default installation path of the .NET Framework.</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\(version)  
```  
  
 <span data-ttu-id="6a19b-124">Version é o número de versão do redistribuível do .NET Framework instalado.</span><span class="sxs-lookup"><span data-stu-id="6a19b-124">Version contains the version number of the installed .NET Framework redistributable.</span></span> <span data-ttu-id="6a19b-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6a19b-125">For example:</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\v2.0.31113  
```  
  
 <span data-ttu-id="6a19b-126">Depois de adicionar o diretório do .NET Framework ao caminho, você pode compilar o exemplo de procedimento armazenado em um assembly com o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="6a19b-126">Once you have added the .NET Framework directory to your path, you can compile the sample stored procedure into an assembly with the following command.</span></span> <span data-ttu-id="6a19b-127">A opção `/target` permite compilá-lo em um assembly.</span><span class="sxs-lookup"><span data-stu-id="6a19b-127">The `/target` option allows you to compile it into an assembly.</span></span>  
  
 <span data-ttu-id="6a19b-128">Para arquivos de origem do Visual C#:</span><span class="sxs-lookup"><span data-stu-id="6a19b-128">For Visual C# source files:</span></span>  
  
```  
csc /target:library helloworld.cs   
```  
  
 <span data-ttu-id="6a19b-129">Para arquivos de origem do Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="6a19b-129">For Visual Basic source files:</span></span>  
  
```  
vbc /target:library helloworld.vb  
```  
  
 <span data-ttu-id="6a19b-130">Esses comandos iniciam o compilador do Visual C# ou do Visual Basic que usa a opção /target para especificar a compilação de uma DLL da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6a19b-130">These commands launch the Visual C# or Visual Basic compiler using the /target option to specify building a library DLL.</span></span>  
  
## <a name="loading-and-running-the-hello-world-stored-procedure-in-sql-server"></a><span data-ttu-id="6a19b-131">Carregando e executando o procedimento armazenado "Hello World" no SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a19b-131">Loading and Running the "Hello World" Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="6a19b-132">Depois que o procedimento de exemplo for compilado com êxito, você poderá testá-lo no [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] e criar uma nova consulta, conectando-se a um banco de dados de teste adequado (por exemplo, o banco de dados de exemplo AdventureWorks).</span><span class="sxs-lookup"><span data-stu-id="6a19b-132">Once the sample procedure has successfully compiled, you can test it in [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] and create a new query, connecting to a suitable test database (for example, the AdventureWorks sample database).</span></span>  
  
 <span data-ttu-id="6a19b-133">A capacidade de executar código CLR (Common Language Runtime) é definida, por padrão, como OFF no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a19b-133">The ability to execute common language runtime (CLR) code is set to OFF by default in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6a19b-134">O código CLR pode ser habilitado usando o procedimento armazenado do sistema **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="6a19b-134">The CLR code can be enabled by using the **sp_configure** system stored procedure.</span></span> <span data-ttu-id="6a19b-135">Para obter mais informações, consulte [Enabling CLR Integration](../clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="6a19b-135">For more information, see [Enabling CLR Integration](../clr-integration-enabling.md).</span></span>  
  
 <span data-ttu-id="6a19b-136">Precisaremos criar o assembly para podermos acessar o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="6a19b-136">We will need to create the assembly so we can access the stored procedure.</span></span> <span data-ttu-id="6a19b-137">Nesse exemplo, vamos pressupor que você criou o assembly helloworld.dll no diretório C:\.</span><span class="sxs-lookup"><span data-stu-id="6a19b-137">For this example, we will assume that you have created the helloworld.dll assembly in the C:\ directory.</span></span> <span data-ttu-id="6a19b-138">Adicione a seguinte instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] à sua consulta.</span><span class="sxs-lookup"><span data-stu-id="6a19b-138">Add the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to your query.</span></span>  
  
```  
CREATE ASSEMBLY helloworld from 'c:\helloworld.dll' WITH PERMISSION_SET = SAFE  
```  
  
 <span data-ttu-id="6a19b-139">Após a criação do assembly, poderemos acessar nosso método HelloWorld usando a instrução create procedure.</span><span class="sxs-lookup"><span data-stu-id="6a19b-139">Once the assembly has been created, we can now access our HelloWorld method by using the create procedure statement.</span></span> <span data-ttu-id="6a19b-140">Chamaremos nosso procedimento armazenado de "hello":</span><span class="sxs-lookup"><span data-stu-id="6a19b-140">We will call our stored procedure "hello":</span></span>  
  
```  
  
CREATE PROCEDURE hello  
@i nchar(25) OUTPUT  
AS  
EXTERNAL NAME helloworld.HelloWorldProc.HelloWorld  
-- if the HelloWorldProc class is inside a namespace (called MyNS),  
-- the last line in the create procedure statement would be  
-- EXTERNAL NAME helloworld.[MyNS.HelloWorldProc].HelloWorld  
```  
  
 <span data-ttu-id="6a19b-141">Após a criação do procedimento, ele poderá ser executado como um procedimento armazenado normal escrito em [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a19b-141">Once the procedure has been created, it can be run just like a normal stored procedure written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6a19b-142">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6a19b-142">Execute the following command:</span></span>  
  
```  
DECLARE @J nchar(25)  
EXEC hello @J out  
PRINT @J  
```  
  
 <span data-ttu-id="6a19b-143">Isso deve resultar na seguinte saída na janela de mensagens do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a19b-143">This should result in the following output in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] messages window.</span></span>  
  
```  
Hello world!  
Hello world!  
```  
  
## <a name="removing-the-hello-world-stored-procedure-sample"></a><span data-ttu-id="6a19b-144">Removendo o exemplo de procedimento armazenado "Hello World"</span><span class="sxs-lookup"><span data-stu-id="6a19b-144">Removing the "Hello World" Stored Procedure Sample</span></span>  
 <span data-ttu-id="6a19b-145">Quando você concluir a execução do exemplo de procedimento armazenado, poderá remover o procedimento e o assembly de seu banco de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="6a19b-145">When you are finished running the sample stored procedure, you can remove the procedure and the assembly from your test database.</span></span>  
  
 <span data-ttu-id="6a19b-146">Primeiro, remova o procedimento usando o comando drop procedure.</span><span class="sxs-lookup"><span data-stu-id="6a19b-146">First, remove the procedure using the drop procedure command.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'hello')  
   drop procedure hello  
```  
  
 <span data-ttu-id="6a19b-147">Após o descarte do procedimento, você poderá remover o assembly que contém seu código de exemplo.</span><span class="sxs-lookup"><span data-stu-id="6a19b-147">Once the procedure has been dropped, you can remove the assembly containing your sample code.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'helloworld')  
   drop assembly helloworld  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a19b-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a19b-148">See Also</span></span>  
 <span data-ttu-id="6a19b-149">[Procedimentos armazenados CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6a19b-149">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 <span data-ttu-id="6a19b-150">[SQL Server extensões específicas em processo para ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span><span class="sxs-lookup"><span data-stu-id="6a19b-150">[SQL Server In-Process Specific Extensions to ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span></span>  
 <span data-ttu-id="6a19b-151">[Depurando objetos de banco de dados CLR](../debugging-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="6a19b-151">[Debugging CLR Database Objects](../debugging-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="6a19b-152">Segurança da integração CLR</span><span class="sxs-lookup"><span data-stu-id="6a19b-152">CLR Integration Security</span></span>](../security/clr-integration-security.md)  
  
  
