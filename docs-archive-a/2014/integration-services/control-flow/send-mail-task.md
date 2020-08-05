---
title: Tarefa Enviar Email | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.f1
helpviewer_keywords:
- mail [Integration Services]
- Send Mail task
- e-mail [Integration Services]
- messages [Integration Services]
- sending messages
ms.assetid: fe0b7cbc-fe8e-4fe2-95b4-2953efff5869
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c93723f3c443705acc14226ce07f456da4d5a884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570803"
---
# <a name="send-mail-task"></a><span data-ttu-id="24b27-102">Tarefa Enviar Email</span><span class="sxs-lookup"><span data-stu-id="24b27-102">Send Mail Task</span></span>
  <span data-ttu-id="24b27-103">A tarefa Enviar Email envia uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="24b27-103">The Send Mail task sends an e-mail message.</span></span> <span data-ttu-id="24b27-104">Usando a tarefa Enviar Email, um pacote pode enviar mensagens se as tarefas no fluxo de trabalho do pacote tiverem êxito ou falharem ou enviar mensagens em resposta a um evento que o pacote ativa em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="24b27-104">By using the Send Mail task, a package can send messages if tasks in the package workflow succeed or fail, or send messages in response to an event that the package raises at run time.</span></span> <span data-ttu-id="24b27-105">Por exemplo, a tarefa pode notificar um administrador de banco de dados sobre o êxito ou a falha da tarefa Fazer Backup do Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="24b27-105">For example, the task can notify a database administrator about the success or failure of the Backup Database task.</span></span>  
  
 <span data-ttu-id="24b27-106">Você pode configurar a tarefa Enviar Email das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="24b27-106">You can configure the Send Mail task in the following ways:</span></span>  
  
-   <span data-ttu-id="24b27-107">Fornecendo o texto da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="24b27-107">Provide the message text for the e-mail message.</span></span>  
  
-   <span data-ttu-id="24b27-108">Fornecendo uma linha de assunto para a mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="24b27-108">Provide a subject line for the e-mail message.</span></span>  
  
-   <span data-ttu-id="24b27-109">Definindo o nível de prioridade da mensagem.</span><span class="sxs-lookup"><span data-stu-id="24b27-109">Set the priority level of the message.</span></span> <span data-ttu-id="24b27-110">A tarefa dá suporte a três níveis de prioridade: normal, baixa e alta.</span><span class="sxs-lookup"><span data-stu-id="24b27-110">The task supports three priority levels: normal, low, and high.</span></span>  
  
-   <span data-ttu-id="24b27-111">Especificando os destinatários nas linhas Para, Cc e Cco.</span><span class="sxs-lookup"><span data-stu-id="24b27-111">Specify the recipients on the To, Cc, and Bcc lines.</span></span> <span data-ttu-id="24b27-112">Se a tarefa especificar vários destinatários, eles serão separados por ponto-e-vírgulas.</span><span class="sxs-lookup"><span data-stu-id="24b27-112">If the task specifies multiple recipients, they are separated by semicolons.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="24b27-113">As linhas Para, Cc e Cco são limitadas a 256 caracteres cada, conforme os padrões da Internet.</span><span class="sxs-lookup"><span data-stu-id="24b27-113">The To, Cc, and Bcc lines are limited to 256 characters each in accordance with Internet standards.</span></span>  
  
-   <span data-ttu-id="24b27-114">Incluindo anexos.</span><span class="sxs-lookup"><span data-stu-id="24b27-114">Include attachments.</span></span> <span data-ttu-id="24b27-115">Se a tarefa especificar vários anexos, eles serão separados pelo caractere barra vertical (|).</span><span class="sxs-lookup"><span data-stu-id="24b27-115">If the task specifies multiple attachments, they are separated by the pipe (|) character.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="24b27-116">Se um arquivo de anexo não existir quando o pacote for executado, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="24b27-116">If an attachment file does not exist when the package runs, an error occurs.</span></span>  
  
-   <span data-ttu-id="24b27-117">Especificando o gerenciador de conexões SMTP a ser usado.</span><span class="sxs-lookup"><span data-stu-id="24b27-117">Specify the SMTP connection manager to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="24b27-118">O gerenciador de conexões SMTP dá suporte apenas para autenticação anônima e Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="24b27-118">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="24b27-119">Ele não suporta a autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="24b27-119">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="24b27-120">O texto da mensagem pode ser uma cadeia de caracteres que você fornece, uma conexão com um arquivo que contém o texto ou o nome de uma variável que contém o texto.</span><span class="sxs-lookup"><span data-stu-id="24b27-120">The message text can be a string that you provide, a connection to a file that contains the text, or the name of a variable that contains the text.</span></span> <span data-ttu-id="24b27-121">A tarefa usa um gerenciador de conexões de arquivos para se conectar a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="24b27-121">The task uses a File connection manager to connect to a file.</span></span> <span data-ttu-id="24b27-122">Para obter mais informações, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="24b27-122">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="24b27-123">A tarefa usa um gerenciador de conexões SMTP para se conectar a um servidor de email.</span><span class="sxs-lookup"><span data-stu-id="24b27-123">The task uses an SMTP connection manager to connect to a mail server.</span></span> <span data-ttu-id="24b27-124">Para obter mais informações, consulte [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="24b27-124">For more information, see [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="custom-logging-messages-available-on-the-send-mail-task"></a><span data-ttu-id="24b27-125">Mensagens de log personalizadas disponíveis na tarefa Enviar Email</span><span class="sxs-lookup"><span data-stu-id="24b27-125">Custom Logging Messages Available on the Send Mail Task</span></span>  
 <span data-ttu-id="24b27-126">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Enviar Email.</span><span class="sxs-lookup"><span data-stu-id="24b27-126">The following table lists the custom log entries for the Send Mail task.</span></span> <span data-ttu-id="24b27-127">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](../performance/integration-services-ssis-logging.md) e [Mensagens personalizadas para log](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="24b27-127">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="24b27-128">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="24b27-128">Log entry</span></span>|<span data-ttu-id="24b27-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="24b27-129">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="24b27-130">Indica que a tarefa começou a enviar uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="24b27-130">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="24b27-131">Indica que a tarefa terminou de enviar uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="24b27-131">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="24b27-132">Fornece informações descritivas sobre a tarefa.</span><span class="sxs-lookup"><span data-stu-id="24b27-132">Provides descriptive information about the task.</span></span>|  
  
## <a name="configuring-the-send-mail-task"></a><span data-ttu-id="24b27-133">Configurando a tarefa Enviar Email</span><span class="sxs-lookup"><span data-stu-id="24b27-133">Configuring the Send Mail Task</span></span>  
 <span data-ttu-id="24b27-134">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="24b27-134">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="24b27-135">Para obter informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="24b27-135">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="24b27-136">Editor da Tarefa Enviar Email &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="24b27-136">Send Mail Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="24b27-137">Editor da Tarefa Enviar Email &#40;Página Email&#41;</span><span class="sxs-lookup"><span data-stu-id="24b27-137">Send Mail Task Editor &#40;Mail Page&#41;</span></span>](../send-mail-task-editor-mail-page.md)  
  
-   [<span data-ttu-id="24b27-138">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="24b27-138">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="24b27-139">Para obter informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="24b27-139">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.SendMailTask.SendMailTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="24b27-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="24b27-140">Related Tasks</span></span>  
 <span data-ttu-id="24b27-141">Para obter informações sobre como definir essas propriedades no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , clique em [Definir as propriedades de uma tarefa ou de um contêiner](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="24b27-141">For information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="24b27-142">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="24b27-142">Related Content</span></span>  
  
-   <span data-ttu-id="24b27-143">Artigo técnico sobre [Como enviar email com notificação de entrega em C#](https://go.microsoft.com/fwlink/?LinkId=237625)no site shareourideas.com</span><span class="sxs-lookup"><span data-stu-id="24b27-143">Technical article, [How to send email with delivery notification in C#](https://go.microsoft.com/fwlink/?LinkId=237625), on shareourideas.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b27-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24b27-144">See Also</span></span>  
 <span data-ttu-id="24b27-145">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="24b27-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="24b27-146">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="24b27-146">Control Flow</span></span>](control-flow.md)  
  
  
