---
title: Enviar uma mensagem de email HTML com a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Send Mail task [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], HTML mail message
ms.assetid: dd2b1eef-b04f-4946-87ab-7bc56bb525ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c1a967b52a84e1ff9c2e54c48e40f4d149b2dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678866"
---
# <a name="sending-an-html-mail-message-with-the-script-task"></a><span data-ttu-id="520aa-102">Enviando uma mensagem de email HTML com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="520aa-102">Sending an HTML Mail Message with the Script Task</span></span>
  <span data-ttu-id="520aa-103">A tarefa SendMail do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] oferece suporte apenas a mensagens de email em formato de texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="520aa-103">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] SendMail task only supports mail messages in plain text format.</span></span> <span data-ttu-id="520aa-104">Porém, você pode enviar mensagens de email HTML facilmente usando a tarefa Script e as capacidades de email do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="520aa-104">However you can easily send HTML mail messages by using the Script task and the mail capabilities of the .NET Framework.</span></span>

> [!NOTE]
>  <span data-ttu-id="520aa-105">Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="520aa-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="520aa-106">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="520aa-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="520aa-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="520aa-107">Description</span></span>
 <span data-ttu-id="520aa-108">O exemplo a seguir usa o namespace `System.Net.Mail` para configurar e enviar uma mensagem de email HTML.</span><span class="sxs-lookup"><span data-stu-id="520aa-108">The following example uses the `System.Net.Mail` namespace to configure and send an HTML mail message.</span></span> <span data-ttu-id="520aa-109">O script obtém o Para, o De, o Assunto e o corpo do email das variáveis do pacote, usa-os para criar uma nova `MailMessag` e define sua propriedade `IsBodyHtml` para `True`.</span><span class="sxs-lookup"><span data-stu-id="520aa-109">The script obtains the To, From, Subject, and body of the e-mail from package variables, uses them to create a new `MailMessag`e, and sets its `IsBodyHtml` property to `True`.</span></span> <span data-ttu-id="520aa-110">Em seguida, obtém o nome do servidor SMTP de uma outra variável do pacote, inicializa uma instância do `System.Net.Mail.SmtpClient` e chama seu método `Send` para enviar a mensagem HTML.</span><span class="sxs-lookup"><span data-stu-id="520aa-110">Then it obtains the SMTP server name from another package variable, initializes an instance of `System.Net.Mail.SmtpClient`, and calls its `Send` method to send the HTML message.</span></span> <span data-ttu-id="520aa-111">O exemplo encapsula a funcionalidade de envio da mensagem em uma sub-rotina que pode ser reutilizada em outros scripts.</span><span class="sxs-lookup"><span data-stu-id="520aa-111">The sample encapsulates the message sending functionality in a subroutine that could be reused in other scripts.</span></span>

#### <a name="to-configure-this-script-task-example-without-an-smtp-connection-manager"></a><span data-ttu-id="520aa-112">Para configurar este exemplo de tarefa Script sem um gerenciador de conexões SMTP</span><span class="sxs-lookup"><span data-stu-id="520aa-112">To configure this Script Task example without an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="520aa-113">Crie variáveis de cadeia de caracteres denominadas `HtmlEmailTo`, `HtmlEmailFrom` e `HtmlEmailSubject` e atribua a elas valores apropriados para uma mensagem de teste válida.</span><span class="sxs-lookup"><span data-stu-id="520aa-113">Create string variables named `HtmlEmailTo`, `HtmlEmailFrom`, and `HtmlEmailSubject` and assign appropriate values to them for a valid test message.</span></span>

2.  <span data-ttu-id="520aa-114">Crie uma variável String denominada `HtmlEmailBody` e atribua a ela uma cadeia de caracteres de marcação HTML.</span><span class="sxs-lookup"><span data-stu-id="520aa-114">Create a string variable named `HtmlEmailBody` and assign a string of HTML markup to it.</span></span> <span data-ttu-id="520aa-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="520aa-115">For example:</span></span>

    ```
    <html><body><h1>Testing</h1><p>This is a <b>test</b> message.</p></body></html>
    ```

3.  <span data-ttu-id="520aa-116">Crie uma variável de cadeia de caracteres denominada `HtmlEmailServer` e atribua o nome de um servidor SMTP disponível que aceite mensagens de saída anônimas.</span><span class="sxs-lookup"><span data-stu-id="520aa-116">Create a string variable named `HtmlEmailServer` and assign the name of an available SMTP server that accepts anonymous outgoing messages.</span></span>

4.  <span data-ttu-id="520aa-117">Atribua todas as cinco variáveis à propriedade **ReadOnlyVariables** de uma nova tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="520aa-117">Assign all five of these variables to the **ReadOnlyVariables** property of a new Script task.</span></span>

5.  <span data-ttu-id="520aa-118">Importe os namespaces `System.Net` e `System.Net.Mail` para seu código.</span><span class="sxs-lookup"><span data-stu-id="520aa-118">Import the `System.Net` and `System.Net.Mail` namespaces into your code.</span></span>

 <span data-ttu-id="520aa-119">O código de exemplo neste tópico obtém o nome do servidor SMTP de uma variável do pacote.</span><span class="sxs-lookup"><span data-stu-id="520aa-119">The sample code in this topic obtains the SMTP server name from a package variable.</span></span> <span data-ttu-id="520aa-120">Contudo, você também pode tirar proveito de um gerenciador de conexões SMTP para encapsular as informações da conexão e extrair o nome do servidor do gerenciador de conexões em seu código.</span><span class="sxs-lookup"><span data-stu-id="520aa-120">However, you could also take advantage of an SMTP connection manager to encapsulate the connection information, and extract the server name from the connection manager in your code.</span></span> <span data-ttu-id="520aa-121">O método <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> do gerenciador de conexões SMTP retorna uma cadeia de caracteres no formato seguinte:</span><span class="sxs-lookup"><span data-stu-id="520aa-121">The <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> method of the SMTP connection manager returns a string in the following format:</span></span>

 `SmtpServer=smtphost;UseWindowsAuthentication=False;EnableSsl=False;`

 <span data-ttu-id="520aa-122">Você pode usar o método `String.Split` para separar essa lista de argumentos em uma matriz de cadeias de caracteres individuais a cada ponto-e-vírgula (;) ou sinal de igual (=) e, em seguida, extrair o segundo argumento (subscript 1) da matriz como o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="520aa-122">You can use the `String.Split` method to separate this argument list into an array of individual strings at each semicolon (;) or equal sign (=), and then extract the second argument (subscript 1) from the array as the server name.</span></span>

#### <a name="to-configure-this-script-task-example-with-an-smtp-connection-manager"></a><span data-ttu-id="520aa-123">Para configurar este exemplo de tarefa Script com um gerenciador de conexões SMTP</span><span class="sxs-lookup"><span data-stu-id="520aa-123">To configure this Script Task example with an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="520aa-124">Modifique a tarefa Script configurada anteriormente removendo a variável `HtmlEmailServer` da lista de **ReadOnlyVariables**.</span><span class="sxs-lookup"><span data-stu-id="520aa-124">Modify the Script task configured earlier by removing the `HtmlEmailServer` variable from the list of **ReadOnlyVariables**.</span></span>

2.  <span data-ttu-id="520aa-125">Substitua a linha do código que obtém o nome do servidor:</span><span class="sxs-lookup"><span data-stu-id="520aa-125">Replace the line of code that obtains the server name:</span></span>

    ```
    Dim smtpServer As String = _
      Dts.Variables("HtmlEmailServer").Value.ToString
    ```

     <span data-ttu-id="520aa-126">pelas seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="520aa-126">with the following lines:</span></span>

    ```
    Dim smtpConnectionString As String = _
      DirectCast(Dts.Connections("SMTP Connection Manager").AcquireConnection(Dts.Transaction), String)
    Dim smtpServer As String = _
      smtpConnectionString.Split(New Char() {"="c, ";"c})(1)
    ```

## <a name="code"></a><span data-ttu-id="520aa-127">Código</span><span class="sxs-lookup"><span data-stu-id="520aa-127">Code</span></span>

```vb
Public Sub Main()

  Dim htmlMessageTo As String = _
    Dts.Variables("HtmlEmailTo").Value.ToString
  Dim htmlMessageFrom As String = _
    Dts.Variables("HtmlEmailFrom").Value.ToString
  Dim htmlMessageSubject As String = _
    Dts.Variables("HtmlEmailSubject").Value.ToString
  Dim htmlMessageBody As String = _
    Dts.Variables("HtmlEmailBody").Value.ToString
  Dim smtpServer As String = _
    Dts.Variables("HtmlEmailServer").Value.ToString

  SendMailMessage( _
      htmlMessageTo, htmlMessageFrom, _
      htmlMessageSubject, htmlMessageBody, _
      True, smtpServer)

  Dts.TaskResult = ScriptResults.Success

End Sub

Private Sub SendMailMessage( _
    ByVal SendTo As String, ByVal From As String, _
    ByVal Subject As String, ByVal Body As String, _
    ByVal IsBodyHtml As Boolean, ByVal Server As String)

  Dim htmlMessage As MailMessage
  Dim mySmtpClient As SmtpClient

  htmlMessage = New MailMessage( _
    SendTo, From, Subject, Body)
  htmlMessage.IsBodyHtml = IsBodyHtml

  mySmtpClient = New SmtpClient(Server)
  mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials
  mySmtpClient.Send(htmlMessage)

End Sub
```

```csharp
public void Main()
        {

            string htmlMessageTo = Dts.Variables["HtmlEmailTo"].Value.ToString();
            string htmlMessageFrom = Dts.Variables["HtmlEmailFrom"].Value.ToString();
            string htmlMessageSubject = Dts.Variables["HtmlEmailSubject"].Value.ToString();
            string htmlMessageBody = Dts.Variables["HtmlEmailBody"].Value.ToString();
            string smtpServer = Dts.Variables["HtmlEmailServer"].Value.ToString();

            SendMailMessage(htmlMessageTo, htmlMessageFrom, htmlMessageSubject, htmlMessageBody, true, smtpServer);

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private void SendMailMessage(string SendTo, string From, string Subject, string Body, bool IsBodyHtml, string Server)
        {

            MailMessage htmlMessage;
            SmtpClient mySmtpClient;

            htmlMessage = new MailMessage(SendTo, From, Subject, Body);
            htmlMessage.IsBodyHtml = IsBodyHtml;

            mySmtpClient = new SmtpClient(Server);
            mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials;
            mySmtpClient.Send(htmlMessage);

        }
```

<span data-ttu-id="520aa-128">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="520aa-128">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="520aa-129">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="520aa-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="520aa-130">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="520aa-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="520aa-131">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="520aa-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="520aa-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="520aa-132">See Also</span></span>
 [<span data-ttu-id="520aa-133">Tarefa Enviar Email</span><span class="sxs-lookup"><span data-stu-id="520aa-133">Send Mail Task</span></span>](../control-flow/send-mail-task.md)


