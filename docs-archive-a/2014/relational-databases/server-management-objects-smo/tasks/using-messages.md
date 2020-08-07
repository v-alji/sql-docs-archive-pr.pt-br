---
title: Usando mensagens | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- messages [SMO]
ms.assetid: 4037a866-4826-4c1f-890c-e7e3658adf13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53b2e0fa4be2dfd53cdd8f4f0cacb7ae0bd79edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582384"
---
# <a name="using-messages"></a><span data-ttu-id="20107-102">Usando mensagens</span><span class="sxs-lookup"><span data-stu-id="20107-102">Using Messages</span></span>
  <span data-ttu-id="20107-103">No SMO, mensagens do sistema são representadas pelo objeto <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> que pertence ao objeto `Server`.</span><span class="sxs-lookup"><span data-stu-id="20107-103">In SMO, system messages are represented by the <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> object that belongs to the `Server` object.</span></span> <span data-ttu-id="20107-104">Como as mensagens do sistema não podem ser modificadas, as propriedades do objeto `SystemMessage` são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="20107-104">Because the system messages cannot be modified, `SystemMessage` object properties are read-only.</span></span>  
  
 <span data-ttu-id="20107-105">Mensagens definidas pelo usuário são representadas programaticamente no SMO pelo objeto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection>.</span><span class="sxs-lookup"><span data-stu-id="20107-105">User-defined messages are represented programmatically in SMO by the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection> object.</span></span> <span data-ttu-id="20107-106">Mensagens existentes, definidas pelo usuário, podem ser descobertas através da iteração pela coleção.</span><span class="sxs-lookup"><span data-stu-id="20107-106">Existing user-defined messages can be discovered by iterating through the collection.</span></span> <span data-ttu-id="20107-107">Para gerar novas mensagens definidas pelo usuário, você pode criar uma instância de um novo objeto `UserDefinedMessage` e definir as propriedades adequadas.</span><span class="sxs-lookup"><span data-stu-id="20107-107">New user-defined messages can be created by instantiating a new `UserDefinedMessage` object and setting the appropriate properties.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="20107-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="20107-108">Examples</span></span>  
 <span data-ttu-id="20107-109">Para os exemplos de código a seguir, selecione o ambiente de programação, o modelo de programação e a linguagem de programação para criar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="20107-109">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="20107-110">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="20107-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="finding-a-particular-system-message-in-visual-basic"></a><span data-ttu-id="20107-111">Localizando uma mensagem de sistema específica no Visual Basic .NET</span><span class="sxs-lookup"><span data-stu-id="20107-111">Finding a Particular System Message in Visual Basic</span></span>  
 <span data-ttu-id="20107-112">O exemplo de código mostra como identificar uma mensagem de sistema através do número de identificação e como exibir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="20107-112">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMessages1](SMO How to#SMO_VBMessages1)]  -->  
  
## <a name="finding-a-particular-system-message-in-visual-c"></a><span data-ttu-id="20107-113">Localizando uma mensagem do sistema específica no Visual Basic C#</span><span class="sxs-lookup"><span data-stu-id="20107-113">Finding a Particular System Message in Visual C#</span></span>  
 <span data-ttu-id="20107-114">O exemplo de código mostra como identificar uma mensagem de sistema através do número de identificação e como exibir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="20107-114">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference an existing system message using the   
            //ItemByIdAndLanguage method.   
            SystemMessage msg = default(SystemMessage);  
            msg = srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
        }  
```  
  
## <a name="finding-a-particular-system-message-in-powershell"></a><span data-ttu-id="20107-115">Localizando uma mensagem do sistema específica no PowerShell</span><span class="sxs-lookup"><span data-stu-id="20107-115">Finding a Particular System Message in PowerShell</span></span>  
 <span data-ttu-id="20107-116">O exemplo de código mostra como identificar uma mensagem de sistema através do número de identificação e como exibir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="20107-116">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get the message 14126 in US English and display it  
$msg = $srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english")  
$msg.ID.ToString() + " "+ $msg.Text  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-basic"></a><span data-ttu-id="20107-117">Adicionando uma nova mensagem definida pelo usuário no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20107-117">Adding a New User-Defined Message in Visual Basic</span></span>  
 <span data-ttu-id="20107-118">O exemplo de código demonstra como criar uma mensagem definida pelo usuário com uma identificação maior que 50000.</span><span class="sxs-lookup"><span data-stu-id="20107-118">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```vb
Dim mysrv As Server  
mysrv = New Server  
Dim udm As UserDefinedMessage  
udm = New UserDefinedMessage(mysrv, 50003, "us_english", 16, "Test message")  
udm.Create()  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-c"></a><span data-ttu-id="20107-119">Adicionando uma nova mensagem definida pelo usuário no Visual Basic C#</span><span class="sxs-lookup"><span data-stu-id="20107-119">Adding a New User-Defined Message in Visual C#</span></span>  
 <span data-ttu-id="20107-120">O exemplo de código demonstra como criar uma mensagem definida pelo usuário com uma identificação maior que 50000.</span><span class="sxs-lookup"><span data-stu-id="20107-120">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```csharp
{
            Server mysrv = new Server();  
  
            UserDefinedMessage udm = new UserDefinedMessage(mysrv, 50030, "us_english",16, "Test message");  
            udm.Create();  
             UserDefinedMessage  msg = mysrv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
  
        }  
```  
  
## <a name="adding-a-new-user-defined-message-in-powershell"></a><span data-ttu-id="20107-121">Adicionando uma nova mensagem definida pelo usuário no PowerShell</span><span class="sxs-lookup"><span data-stu-id="20107-121">Adding a New User-Defined Message in PowerShell</span></span>
 <span data-ttu-id="20107-122">O exemplo de código demonstra como criar uma mensagem definida pelo usuário com uma identificação maior que 50000.</span><span class="sxs-lookup"><span data-stu-id="20107-122">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a new message
$udm = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedMessage -ArgumentList `  
$srv, 50030, "us_english", 16, "Test message"  
$udm.Create()  
$msg = $srv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
$msg  
```  
