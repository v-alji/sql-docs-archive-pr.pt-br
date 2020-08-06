---
title: Manipulando exceções SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SMO [SQL Server], exceptions
- exceptions [SMO]
- SQL Server Management Objects, exceptions
- inner exceptions [SMO]
ms.assetid: 4c725ff2-6588-44ca-b86a-87979e164153
author: stevestein
ms.author: sstein
ms.openlocfilehash: f4ae9e475a019c9bf874ee3f8365f3f3ac8e19d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582930"
---
# <a name="handling-smo-exceptions"></a><span data-ttu-id="6ec0b-102">Manipulando exceções SMO</span><span class="sxs-lookup"><span data-stu-id="6ec0b-102">Handling SMO Exceptions</span></span>
  <span data-ttu-id="6ec0b-103">No código gerenciado, as exceções são geradas quando ocorre um erro.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-103">In managed code, exceptions are thrown when an error occurs.</span></span> <span data-ttu-id="6ec0b-104">Os métodos e propriedades do SMO não informam êxito ou falha no valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-104">SMO methods and properties do not report success or failure in the return value.</span></span> <span data-ttu-id="6ec0b-105">Em vez disso, as exceções podem ser capturadas e manipuladas por um manipulador de exceções.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-105">Instead, exceptions can be caught and handled by an exception handler.</span></span>  
  
 <span data-ttu-id="6ec0b-106">Existem classes diferentes de exceção no SMO.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-106">Different exception classes exist in the SMO.</span></span> <span data-ttu-id="6ec0b-107">As informações sobre a exceção podem ser obtidas das propriedades de exceção, como a propriedade `Message`, que fornece uma mensagem de texto sobre a exceção.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-107">Information about the exception can be extracted from the exception properties such as the `Message` property that gives a text message about the exception.</span></span>  
  
 <span data-ttu-id="6ec0b-108">As instruções que manipulam exceção são específicas da linguagem de programação.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-108">The exception handling statements are specific to the programming language.</span></span> <span data-ttu-id="6ec0b-109">Por exemplo, no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic a instrução é `Catch`.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-109">For example, in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic it is the `Catch` statement.</span></span>  
  
## <a name="inner-exceptions"></a><span data-ttu-id="6ec0b-110">Exceções internas</span><span class="sxs-lookup"><span data-stu-id="6ec0b-110">Inner Exceptions</span></span>  
 <span data-ttu-id="6ec0b-111">As exceções podem ser gerais ou específicas.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-111">Exceptions can either be general or specific.</span></span> <span data-ttu-id="6ec0b-112">As exceções gerais contêm um conjunto de exceções específicas.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-112">General exceptions contain a set of specific exceptions.</span></span> <span data-ttu-id="6ec0b-113">Várias instruções `Catch` podem ser usadas para tratar erros antecipados e deixar os erros restantes sem solução no código geral de manipulação de exceção.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-113">Several `Catch` statements can be used to handle anticipated errors and let remaining errors fall through to general exception handling code.</span></span> <span data-ttu-id="6ec0b-114">Normalmente, as exceções ocorrem em uma sequência em cascata.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-114">Exceptions often occur in a cascading sequence.</span></span> <span data-ttu-id="6ec0b-115">Com frequência, a exceção do SMO é causada por uma exceção SQL.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-115">Frequently, an SMO exception might have been caused by an SQL exception.</span></span> <span data-ttu-id="6ec0b-116">Para detectar isso, use a propriedade `InnerException` sucessivamente para determinar a exceção original que causou a exceção final de nível superior.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-116">The way to detect this is to use the `InnerException` property successively to determine the original exception that caused the final, top-level exception.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ec0b-117">A `SQLException` exceção é declarada no namespace **System. Data. SqlClient** .</span><span class="sxs-lookup"><span data-stu-id="6ec0b-117">The `SQLException` exception is declared in the **System.Data.SqlClient** namespace.</span></span>  
  
 <span data-ttu-id="6ec0b-118">![Um diagrama que mostra os níveis a partir dos quais uma exceção](../../../database-engine/dev-guide/media/exception-flow.gif "Um diagrama que mostra os níveis a partir dos quais uma exceção")</span><span class="sxs-lookup"><span data-stu-id="6ec0b-118">![A diagram that shows the levels from which an excp](../../../database-engine/dev-guide/media/exception-flow.gif "A diagram that shows the levels from which an excp")</span></span>  
  
 <span data-ttu-id="6ec0b-119">O diagrama mostra o fluxo de exceções pelas camadas do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-119">The diagram shows the flow of exceptions through the layers of the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ec0b-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6ec0b-120">Example</span></span>  
 <span data-ttu-id="6ec0b-121">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="6ec0b-122">Para obter mais informações, consulte [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) ou [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="6ec0b-122">For more information, see [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) or [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="catching-an-exception-in-visual-basic"></a><span data-ttu-id="6ec0b-123">Capturando uma exceção no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6ec0b-123">Catching an Exception in Visual Basic</span></span>  
 <span data-ttu-id="6ec0b-124">Este exemplo de código mostra como usar a instrução `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] para capturar uma exceção do SMO.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-124">This code example shows how to use the `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] statement to catch a SMO exception.</span></span> <span data-ttu-id="6ec0b-125">Todas as exceções do SMO têm o tipo SmoException e estão listadas na referência de SMO.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-125">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="6ec0b-126">A sequência de exceções internas é exibida para mostrar a raiz do erro.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-126">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="6ec0b-127">Para obter mais informações, consulte a documentação do [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-127">For more information, see the [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET documentation.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBExceptions1](SMO How to#SMO_VBExceptions1)]  -->  
  
## <a name="catching-an-exception-in-visual-c"></a><span data-ttu-id="6ec0b-128">Capturando uma exceção no Visual C#</span><span class="sxs-lookup"><span data-stu-id="6ec0b-128">Catching an Exception in Visual C#</span></span>  
 <span data-ttu-id="6ec0b-129">Este exemplo de código mostra como usar a instrução Visual C# `Try...Catch...Finally` para capturar uma exceção do SMO.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-129">This code example shows how to use the `Try...Catch...Finally` Visual C# statement to catch a SMO exception.</span></span> <span data-ttu-id="6ec0b-130">Todas as exceções do SMO têm o tipo SmoException e estão listadas na referência de SMO.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-130">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="6ec0b-131">A sequência de exceções internas é exibida para mostrar a raiz do erro.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-131">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="6ec0b-132">Para obter mais informações, consulte a documentação do Visual C#.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-132">For more information, see the Visual C# documentation.</span></span>  
  
```  
{   
//This sample requires the Microsoft.SqlServer.Management.Smo.Agent namespace to be included.   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define an Operator object variable by supplying the parent SQL Agent and the name arguments in the constructor.   
//Note that the Operator type requires [] parenthesis to differentiate it from a Visual Basic key word.   
op = new Operator(srv.JobServer, "Test_Operator");   
op.Create();   
//Start exception handling.   
try {   
    //Create the operator again to cause an SMO exception.   
    OperatorCategory opx;   
    opx = new OperatorCategory(srv.JobServer, "Test_Operator");   
    opx.Create();   
}   
//Catch the SMO exception   
catch (SmoException smoex) {   
    Console.WriteLine("This is an SMO Exception");   
   //Display the SMO exception message.   
   Console.WriteLine(smoex.Message);   
   //Display the sequence of non-SMO exceptions that caused the SMO exception.   
   Exception ex;   
   ex = smoex.InnerException;   
   while (!object.ReferenceEquals(ex.InnerException, (null))) {   
      Console.WriteLine(ex.InnerException.Message);   
      ex = ex.InnerException;   
    }   
    }   
   //Catch other non-SMO exceptions.   
   catch (Exception ex) {   
      Console.WriteLine("This is not an SMO exception.");   
}   
}  
```  
  
  
