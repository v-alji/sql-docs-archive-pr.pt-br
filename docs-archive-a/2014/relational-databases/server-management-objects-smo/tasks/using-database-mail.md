---
title: Usando Database Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- e-mail [SMO]
- Database Mail [SMO]
- mail [SMO]
ms.assetid: 7605390f-b485-48cc-8d97-e364a066067b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ceec7417638f53427ed5a62101f2fdb6d7440a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680859"
---
# <a name="using-database-mail"></a><span data-ttu-id="48d63-102">Usando o Database Mail</span><span class="sxs-lookup"><span data-stu-id="48d63-102">Using Database Mail</span></span>
  <span data-ttu-id="48d63-103">No SMO, o subsistema Database Mail é representado pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> que é referenciado pela propriedade <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A>.</span><span class="sxs-lookup"><span data-stu-id="48d63-103">In SMO, the Database Mail subsystem is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object that is referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property.</span></span> <span data-ttu-id="48d63-104">Através do objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> do SMO, você pode configurar o subsistema Database Mail e gerenciar perfis e contas de email.</span><span class="sxs-lookup"><span data-stu-id="48d63-104">By using the SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object, you can configure the Database Mail subsystem and manage profiles and mail accounts.</span></span> <span data-ttu-id="48d63-105">O objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> do SMO pertence ao objeto `Server`. Isso significa que o escopo das contas de email está em nível de servidor.</span><span class="sxs-lookup"><span data-stu-id="48d63-105">The SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object belongs to the `Server` object, meaning that scope of the mail accounts is at the server level.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="48d63-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="48d63-106">Examples</span></span>  
 <span data-ttu-id="48d63-107">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="48d63-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="48d63-108">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="48d63-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="48d63-109">Para programas que usam [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Database Mail, você deve incluir a `Imports` instrução para qualificar o namespace de email.</span><span class="sxs-lookup"><span data-stu-id="48d63-109">For programs that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Database Mail, you must include the `Imports` statement to qualify the Mail namespace.</span></span> <span data-ttu-id="48d63-110">Insira a instrução após outras instruções `Imports`, antes de qualquer declaração no aplicativo, como:</span><span class="sxs-lookup"><span data-stu-id="48d63-110">Insert the statement after the other `Imports` statements, before any declarations in the application, such as:</span></span>  
  
 `Imports Microsoft.SqlServer.Management.Smo`  
  
 `Imports Microsoft.SqlServer.Management.Common`  
  
 `Imports Microsoft.SqlServer.Management.Smo.Mail`  
  
## <a name="creating-a-database-mail-account-by-using-visual-basic"></a><span data-ttu-id="48d63-111">Criando uma conta de email de banco de dados usando o Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48d63-111">Creating a Database Mail Account by Using Visual Basic</span></span>  
 <span data-ttu-id="48d63-112">Este exemplo de código mostra como criar uma conta de email no SMO.</span><span class="sxs-lookup"><span data-stu-id="48d63-112">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="48d63-113">O Database Mail é representado pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> e referenciado pela propriedade <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="48d63-113">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="48d63-114">O SMO pode ser usado para configurar programaticamente o Database Mail, mas não pode ser usado para enviar ou tratar emails recebidos.</span><span class="sxs-lookup"><span data-stu-id="48d63-114">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
 <span data-ttu-id="48d63-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="48d63-115">VB.NET</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMail1](SMO How to#SMO_VBMail1)]  -->  
  
## <a name="creating-a-database-mail-account-by-using-visual-c"></a><span data-ttu-id="48d63-116">Criando uma conta de email de banco de dados usando o Visual C#</span><span class="sxs-lookup"><span data-stu-id="48d63-116">Creating a Database Mail Account by Using Visual C#</span></span>  
 <span data-ttu-id="48d63-117">Este exemplo de código mostra como criar uma conta de email no SMO.</span><span class="sxs-lookup"><span data-stu-id="48d63-117">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="48d63-118">O Database Mail é representado pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> e referenciado pela propriedade <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="48d63-118">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="48d63-119">O SMO pode ser usado para configurar programaticamente o Database Mail, mas não pode ser usado para enviar ou tratar emails recebidos.</span><span class="sxs-lookup"><span data-stu-id="48d63-119">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
```csharp  
{  
         //Connect to the local, default instance of SQL Server.  
         Server srv = default(Server);   
           srv = new Server();   
           //Define the Database Mail service with a SqlMail object variable   
           //and reference it using the Server Mail property.   
           SqlMail sm;   
           sm = srv.Mail;   
           //Define and create a mail account by supplying the Database Mail  
           //service, name, description, display name, and email address  
           //arguments in the constructor.   
           MailAccount a = default(MailAccount);   
           a = new MailAccount(sm, "AdventureWorks2012 Administrator", "AdventureWorks2012 Automated Mailer", "Mail account for administrative e-mail.", "dba@Adventure-Works.com");   
           a.Create();    
}  
```  
  
## <a name="creating-a-database-mail-account-by-using-powershell"></a><span data-ttu-id="48d63-120">Criando uma conta de email de banco de dados usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="48d63-120">Creating a Database Mail Account by Using PowerShell</span></span>  
 <span data-ttu-id="48d63-121">Este exemplo de código mostra como criar uma conta de email no SMO.</span><span class="sxs-lookup"><span data-stu-id="48d63-121">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="48d63-122">O Database Mail é representado pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> e referenciado pela propriedade <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="48d63-122">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="48d63-123">O SMO pode ser usado para configurar programaticamente o Database Mail, mas não pode ser usado para enviar ou tratar emails recebidos.</span><span class="sxs-lookup"><span data-stu-id="48d63-123">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>
  
```powershell  
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define the Database Mail; reference it using the Server Mail property.  
$sm = $srv.Mail  
  
#Define and create a mail account by supplying the Database Mail service,  
#name, description, display name, and email address arguments in the constructor.  
$a = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Mail.MailAccount -ArgumentList $sm, `  
"Adventure Works Administrator", "Adventure Works Automated Mailer",`  
 "Mail account for administrative e-mail.", "dba@Adventure-Works.com"  
$a.Create()  
```  
