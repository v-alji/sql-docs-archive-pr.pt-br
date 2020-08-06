---
title: Editor da tarefa Enviar email (página email) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.mail.f1
helpviewer_keywords:
- Send Mail Task Editor
ms.assetid: adb385d5-ef24-4d18-b9ea-b39e00a7075e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 52cab62f3c88ea248b76061664547fd8f1314099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685849"
---
# <a name="send-mail-task-editor-mail-page"></a><span data-ttu-id="b7848-102">Editor da tarefa Enviar Email (página Email)</span><span class="sxs-lookup"><span data-stu-id="b7848-102">Send Mail Task Editor (Mail Page)</span></span>
  <span data-ttu-id="b7848-103">Use a página **Email** da caixa de diálogo do **Editor da Tarefa Enviar Email** para especificar destinatários, o tipo de mensagem e a prioridade de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="b7848-103">Use the **Mail** page of the **Send Mail Task Editor** dialog box to specify recipients, message type, and priority for a message.</span></span> <span data-ttu-id="b7848-104">Você também pode anexar arquivos à mensagem.</span><span class="sxs-lookup"><span data-stu-id="b7848-104">You can also attach files to the message.</span></span> <span data-ttu-id="b7848-105">O texto da mensagem pode ser uma cadeia de caracteres fornecida por você, uma conexão com um arquivo que contém o texto ou o nome de uma variável que contém o texto.</span><span class="sxs-lookup"><span data-stu-id="b7848-105">The message text can be a string you provide, a file connection to a file that contains the text, or the name of a variable that contains the text.</span></span>  
  
 <span data-ttu-id="b7848-106">Para obter informações sobre essa tarefa, consulte [Send Mail Task](control-flow/send-mail-task.md).</span><span class="sxs-lookup"><span data-stu-id="b7848-106">To learn about this task, see [Send Mail Task](control-flow/send-mail-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b7848-107">Opções</span><span class="sxs-lookup"><span data-stu-id="b7848-107">Options</span></span>  
 <span data-ttu-id="b7848-108">**SMTPConnection**</span><span class="sxs-lookup"><span data-stu-id="b7848-108">**SMTPConnection**</span></span>  
 <span data-ttu-id="b7848-109">Selecione um gerenciador de conexões SMTP na lista ou clique em **\<New connection...>** para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="b7848-109">Select an SMTP connection manager in the list, or click **\<New connection...>** to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b7848-110">O gerenciador de conexões SMTP dá suporte apenas para autenticação anônima e Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b7848-110">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="b7848-111">Ele não suporta a autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="b7848-111">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="b7848-112">**Tópicos relacionados:** [Gerenciador de Conexões SMTP](connection-manager/smtp-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="b7848-112">**Related Topics:** [SMTP Connection Manager](connection-manager/smtp-connection-manager.md)</span></span>  
  
 <span data-ttu-id="b7848-113">**De**</span><span class="sxs-lookup"><span data-stu-id="b7848-113">**From**</span></span>  
 <span data-ttu-id="b7848-114">Especifique o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="b7848-114">Specify the e-mail address of the sender.</span></span>  
  
 <span data-ttu-id="b7848-115">**Para**</span><span class="sxs-lookup"><span data-stu-id="b7848-115">**To**</span></span>  
 <span data-ttu-id="b7848-116">Forneça os endereços de email dos destinatários, separados por ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="b7848-116">Provide the e-mail addresses of the recipients, delimited by semicolons.</span></span>  
  
 <span data-ttu-id="b7848-117">**Cc**</span><span class="sxs-lookup"><span data-stu-id="b7848-117">**Cc**</span></span>  
 <span data-ttu-id="b7848-118">Especifique os endereços de email de outras pessoas que também receberão cópias da mensagem, separando todos os emails por ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="b7848-118">Specify the e-mail addresses, delimited by semicolons, of individuals who also receive copies of the message.</span></span>  
  
 <span data-ttu-id="b7848-119">**Cco**</span><span class="sxs-lookup"><span data-stu-id="b7848-119">**Bcc**</span></span>  
 <span data-ttu-id="b7848-120">Especifique os endereços de email de outras pessoas que também receberão cópias da mensagem com cópia oculta (Cco), separando todos os emails por ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="b7848-120">Specify the e-mail addresses, delimited by semicolons, of individuals who receive blind carbon copies (Bcc) copies of the message.</span></span>  
  
 <span data-ttu-id="b7848-121">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="b7848-121">**Subject**</span></span>  
 <span data-ttu-id="b7848-122">Indique o assunto da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="b7848-122">Provide a subject for the e-mail message.</span></span>  
  
 <span data-ttu-id="b7848-123">**MessageSourceType**</span><span class="sxs-lookup"><span data-stu-id="b7848-123">**MessageSourceType**</span></span>  
 <span data-ttu-id="b7848-124">Selecione o tipo de origem da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b7848-124">Select the source type of the message.</span></span> <span data-ttu-id="b7848-125">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b7848-125">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="b7848-126">Valor</span><span class="sxs-lookup"><span data-stu-id="b7848-126">Value</span></span>|<span data-ttu-id="b7848-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="b7848-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7848-128">**Entrada Direta**</span><span class="sxs-lookup"><span data-stu-id="b7848-128">**Direct input**</span></span>|<span data-ttu-id="b7848-129">Defina a origem do texto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b7848-129">Set the source to the message text.</span></span> <span data-ttu-id="b7848-130">Selecionar este valor faz com que seja exibida a opção dinâmica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="b7848-130">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="b7848-131">**Conexão do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="b7848-131">**File connection**</span></span>|<span data-ttu-id="b7848-132">Defina a origem do arquivo que contém o texto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b7848-132">Set the source to the file that contains the message text.</span></span> <span data-ttu-id="b7848-133">Selecionar este valor faz com que seja exibida a opção dinâmica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="b7848-133">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="b7848-134">**Variável**</span><span class="sxs-lookup"><span data-stu-id="b7848-134">**Variable**</span></span>|<span data-ttu-id="b7848-135">Defina a origem de uma variável que contém o texto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b7848-135">Set the source to a variable that contains the message text.</span></span> <span data-ttu-id="b7848-136">Selecionar este valor faz com que seja exibida a opção dinâmica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="b7848-136">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
  
 <span data-ttu-id="b7848-137">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="b7848-137">**Priority**</span></span>  
 <span data-ttu-id="b7848-138">Defina a prioridade da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b7848-138">Set the priority of the message.</span></span>  
  
 <span data-ttu-id="b7848-139">**Anexos**</span><span class="sxs-lookup"><span data-stu-id="b7848-139">**Attachments**</span></span>  
 <span data-ttu-id="b7848-140">Forneça os nomes de arquivo dos anexos à mensagem de email, separados por uma barra vertical (|).</span><span class="sxs-lookup"><span data-stu-id="b7848-140">Provide the file names of attachments to the e-mail message, delimited by the pipe (|) character.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7848-141">As linhas Para, Cc e Cco são limitadas a 256 caracteres, de acordo com os padrões da Internet.</span><span class="sxs-lookup"><span data-stu-id="b7848-141">The To, Cc, and Bcc lines are limited to 256 characters in accordance with Internet standards.</span></span>  
  
## <a name="messagesourcetype-dynamic-options"></a><span data-ttu-id="b7848-142">Opções dinâmicas de MessageSourceType</span><span class="sxs-lookup"><span data-stu-id="b7848-142">MessageSourceType Dynamic Options</span></span>  
  
### <a name="messagesourcetype--direct-input"></a><span data-ttu-id="b7848-143">MessageSourceType = Entrada direta</span><span class="sxs-lookup"><span data-stu-id="b7848-143">MessageSourceType = Direct Input</span></span>  
 <span data-ttu-id="b7848-144">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="b7848-144">**MessageSource**</span></span>  
 <span data-ttu-id="b7848-145">Digite o texto da mensagem ou clique no botão Procurar (...) e digite a mensagem na caixa de diálogo **Origem da mensagem**.</span><span class="sxs-lookup"><span data-stu-id="b7848-145">Type the message text or click the browse button (...) and then type the message in the **Message source** dialog box.</span></span>  
  
### <a name="messagesourcetype--file-connection"></a><span data-ttu-id="b7848-146">MessageSourceType = Conexão do arquivo</span><span class="sxs-lookup"><span data-stu-id="b7848-146">MessageSourceType = File connection</span></span>  
 <span data-ttu-id="b7848-147">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="b7848-147">**MessageSource**</span></span>  
 <span data-ttu-id="b7848-148">Selecione um gerenciador de conexões de Arquivos na lista ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="b7848-148">Select a File connection manager in the list or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="b7848-149">**Tópicos relacionados:** [Gerenciador de conexões de arquivos](connection-manager/file-connection-manager.md), [Editor do Gerenciador de conexões de Arquivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="b7848-149">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="messagesourcetype--variable"></a><span data-ttu-id="b7848-150">MessageSourceType = Variável</span><span class="sxs-lookup"><span data-stu-id="b7848-150">MessageSourceType = Variable</span></span>  
 <span data-ttu-id="b7848-151">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="b7848-151">**MessageSource**</span></span>  
 <span data-ttu-id="b7848-152">Selecione uma variável na lista ou clique em \<**New variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="b7848-152">Select a variable in the list or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="b7848-153">**Tópicos relacionados:** [Variáveis do Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Adicionar variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="b7848-153">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7848-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b7848-154">See Also</span></span>  
 <span data-ttu-id="b7848-155">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b7848-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b7848-156">[Editor da tarefa Enviar email &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="b7848-156">[Send Mail Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="b7848-157">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="b7848-157">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
