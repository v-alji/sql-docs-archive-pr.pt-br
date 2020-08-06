---
title: Enviar a uma fila de mensagens particular remota com a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], remote private message queues
- Message Queue task [Integration Services]
- Script task [Integration Services], examples
ms.assetid: 636314fd-d099-45cd-8bb4-f730d0a06739
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 308815293dfc41f0a0ac60c21ce7f561a5e7f660
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680984"
---
# <a name="sending-to-a-remote-private-message-queue-with-the-script-task"></a><span data-ttu-id="74a99-102">Enviando a uma fila de mensagens particular remota com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="74a99-102">Sending to a Remote Private Message Queue with the Script Task</span></span>
  <span data-ttu-id="74a99-103">O serviço de enfileiramento de mensagens (também conhecido como MSMQ) facilita a comunicação rápida e confiável de desenvolvedores com programas aplicativos, enviando e recebendo mensagens.</span><span class="sxs-lookup"><span data-stu-id="74a99-103">Message Queuing (also known as MSMQ) makes it easy for developers to communicate with application programs quickly and reliably by sending and receiving messages.</span></span> <span data-ttu-id="74a99-104">Uma fila de mensagens pode estar localizada no computador local ou em um computador remoto, e pode ser pública ou particular.</span><span class="sxs-lookup"><span data-stu-id="74a99-104">A message queue may be located on the local computer or a remote computer, and may be public or private.</span></span> <span data-ttu-id="74a99-105">No [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], o gerenciador de conexões do MSMQ e a tarefa Fila de Mensagens não dão suporte ao envio para uma fila privada em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="74a99-105">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the MSMQ connection manager and Message Queue task do not support sending to a private queue on a remote computer.</span></span> <span data-ttu-id="74a99-106">Porém, a tarefa Script facilita o envio de uma mensagem a uma fila particular remota.</span><span class="sxs-lookup"><span data-stu-id="74a99-106">However, by using the Script task, it is easy to send a message to a remote private queue.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74a99-107">Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="74a99-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="74a99-108">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="74a99-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="74a99-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="74a99-109">Description</span></span>  
 <span data-ttu-id="74a99-110">O exemplo a seguir usa um gerenciador de conexões MSMQ existente, junto com objetos e métodos do namespace System.Messaging, para enviar o texto contido em uma variável de pacote a uma fila de mensagens particular remota.</span><span class="sxs-lookup"><span data-stu-id="74a99-110">The following example uses an existing MSMQ connection manager, together with objects and methods from the System.Messaging namespace, to send the text contained in a package variable to a remote private message queue.</span></span> <span data-ttu-id="74a99-111">A chamada para o método M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection (System. Object) do Gerenciador de conexões MSMQ retorna um objeto **MessageQueue** cujo `Send` método realiza essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="74a99-111">The call to the M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection(System.Object) method of the MSMQ connection manager returns a **MessageQueue** object whose `Send` method accomplishes this task.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="74a99-112">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="74a99-112">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="74a99-113">Crie um gerenciador de conexões do MSMQ com o nome padrão.</span><span class="sxs-lookup"><span data-stu-id="74a99-113">Create an MSMQ connection manager with the default name.</span></span> <span data-ttu-id="74a99-114">Defina o caminho de uma fila particular remota válida no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="74a99-114">Set the path of a valid remote private queue, in the following format:</span></span>  
  
    ```  
    FORMATNAME:DIRECT=OS:<computername>\private$\<queuename>  
    ```  
  
2.  <span data-ttu-id="74a99-115">Crie uma [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variável chamada **MessageText** do tipo `String` para passar o texto da mensagem para o script.</span><span class="sxs-lookup"><span data-stu-id="74a99-115">Create an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable named **MessageText** of type `String` to pass the message text into the script.</span></span> <span data-ttu-id="74a99-116">Digite uma mensagem padrão como o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="74a99-116">Enter a default message as the value of the variable.</span></span>  
  
3.  <span data-ttu-id="74a99-117">Adicione uma tarefa Script à superfície de design e edite-a.</span><span class="sxs-lookup"><span data-stu-id="74a99-117">Add a Script Task to the design surface and edit it.</span></span> <span data-ttu-id="74a99-118">Na guia **Script** do **Editor da Tarefa Script**, adicione a variável `MessageText` à propriedade **ReadOnlyVariables** para disponibilizar a variável dentro do script.</span><span class="sxs-lookup"><span data-stu-id="74a99-118">On the **Script** tab of the **Script Task Editor**, add the `MessageText` variable to the **ReadOnlyVariables** property to make the variable available inside the script.</span></span>  
  
4.  <span data-ttu-id="74a99-119">Clique em **Editar Script** para abrir o editor de script VSTA ([!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications).</span><span class="sxs-lookup"><span data-stu-id="74a99-119">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) script editor.</span></span>  
  
5.  <span data-ttu-id="74a99-120">Adicione uma referência do projeto de script ao namespace `System.Messaging`.</span><span class="sxs-lookup"><span data-stu-id="74a99-120">Add a reference in the script project to the `System.Messaging` namespace.</span></span>  
  
6.  <span data-ttu-id="74a99-121">Substitua o conteúdo da janela de script pelo código da seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="74a99-121">Replace the contents of the script window with the code in the following section.</span></span>  
  
## <a name="code"></a><span data-ttu-id="74a99-122">Código</span><span class="sxs-lookup"><span data-stu-id="74a99-122">Code</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Messaging  
  
Public Class ScriptMain  
  
    Public Sub Main()  
  
        Dim remotePrivateQueue As MessageQueue  
        Dim messageText As String  
  
        remotePrivateQueue = _  
            DirectCast(Dts.Connections("Message Queue Connection Manager").AcquireConnection(Dts.Transaction), _  
            MessageQueue)  
        messageText = DirectCast(Dts.Variables("MessageText").Value, String)  
        remotePrivateQueue.Send(messageText)  
  
        Dts.TaskResult = ScriptResults.Success  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Messaging;  
  
public class ScriptMain  
{  
  
    public void Main()  
        {  
  
            MessageQueue remotePrivateQueue = new MessageQueue();  
            string messageText;  
  
            remotePrivateQueue = (MessageQueue)(Dts.Connections["Message Queue Connection Manager"].AcquireConnection(Dts.Transaction) as MessageQueue);  
            messageText = (string)(Dts.Variables["MessageText"].Value);  
            remotePrivateQueue.Send(messageText);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
```  
  
<span data-ttu-id="74a99-123">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="74a99-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="74a99-124">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="74a99-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="74a99-125">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="74a99-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="74a99-126">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="74a99-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a99-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="74a99-127">See Also</span></span>  
 [<span data-ttu-id="74a99-128">Tarefa Fila de Mensagens</span><span class="sxs-lookup"><span data-stu-id="74a99-128">Message Queue Task</span></span>](../control-flow/message-queue-task.md)  
  
  
