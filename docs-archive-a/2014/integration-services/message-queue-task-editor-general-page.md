---
title: Editor da tarefa fila de mensagens (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.general.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 09368b18-37a5-4321-a173-7cfe5d42d2a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dcec75f3a4dd85efb7c97226c592d6b1e1bb26ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583724"
---
# <a name="message-queue-task-editor-general-page"></a><span data-ttu-id="01b61-102">Editor da Tarefa Fila de Mensagens (página Geral)</span><span class="sxs-lookup"><span data-stu-id="01b61-102">Message Queue Task Editor (General Page)</span></span>
  <span data-ttu-id="01b61-103">Use a **página Geral** da caixa de diálogo do **Editor da Tarefa Fila de Mensagens** para nomear e descrever a tarefa Fila de Mensagens, especificar o formato da mensagem e indicar se a tarefa envia ou recebe mensagens.</span><span class="sxs-lookup"><span data-stu-id="01b61-103">Use the **General page** of the **Message Queue Task Editor** dialog box to name and describe the Message Queue task, to specify the message format, and to indicate whether the task sends or receives messages.</span></span>  
  
 <span data-ttu-id="01b61-104">Para obter informações sobre essa tarefa, consulte [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="01b61-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="01b61-105">Opções</span><span class="sxs-lookup"><span data-stu-id="01b61-105">Options</span></span>  
 <span data-ttu-id="01b61-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="01b61-106">**Name**</span></span>  
 <span data-ttu-id="01b61-107">Forneça um nome exclusivo para a tarefa Fila de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="01b61-107">Provide a unique name for the Message Queue task.</span></span> <span data-ttu-id="01b61-108">Esse nome é usado como rótulo no ícone de tarefa.</span><span class="sxs-lookup"><span data-stu-id="01b61-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01b61-109">Os nomes das tarefas devem ser exclusivos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="01b61-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="01b61-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="01b61-110">**Description**</span></span>  
 <span data-ttu-id="01b61-111">Digite uma descrição para a tarefa Fila de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="01b61-111">Type a description of the Message Queue task.</span></span>  
  
 <span data-ttu-id="01b61-112">**Use2000Format**</span><span class="sxs-lookup"><span data-stu-id="01b61-112">**Use2000Format**</span></span>  
 <span data-ttu-id="01b61-113">Indique se deseja usar o formato 2000 do serviço de enfileiramento de mensagens (também conhecido como MSMQ).</span><span class="sxs-lookup"><span data-stu-id="01b61-113">Indicate whether to use the 2000 format of Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="01b61-114">O padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="01b61-114">The default is `False`.</span></span>  
  
 <span data-ttu-id="01b61-115">**MSMQConnection**</span><span class="sxs-lookup"><span data-stu-id="01b61-115">**MSMQConnection**</span></span>  
 <span data-ttu-id="01b61-116">Selecione um gerenciador de conexões MSMQ existente ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="01b61-116">Select an existing MSMQ connection manager or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="01b61-117">**Tópicos relacionados**: [Gerenciador de conexões MSMQ](connection-manager/msmq-connection-manager.md), [Editor do Gerenciador de conexões MSMQ](../../2014/integration-services/msmq-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="01b61-117">**Related Topics**: [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md), [MSMQ Connection Manager Editor](../../2014/integration-services/msmq-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="01b61-118">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="01b61-118">**Message**</span></span>  
 <span data-ttu-id="01b61-119">Especifique se a tarefa Fila de Mensagens envia ou recebe mensagens.</span><span class="sxs-lookup"><span data-stu-id="01b61-119">Specify whether the Message Queue task sends or receive messages.</span></span> <span data-ttu-id="01b61-120">Se você selecionar **Enviar mensagem**, será listada a página Enviar no painel esquerdo da caixa de diálogo; se você selecionar **Receber mensagem**, será listada a página Receber.</span><span class="sxs-lookup"><span data-stu-id="01b61-120">If you select **Send message**, the Send page is listed in the left pane of the dialog box; if you select **Receive message**, the Receive page is listed.</span></span> <span data-ttu-id="01b61-121">Por padrão, esse valor está definido como **Enviar mensagem**.</span><span class="sxs-lookup"><span data-stu-id="01b61-121">By default, this value is set to **Send message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b61-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="01b61-122">See Also</span></span>  
 <span data-ttu-id="01b61-123">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="01b61-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="01b61-124">[Editor da tarefa fila de mensagens &#40;página receber&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="01b61-124">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 <span data-ttu-id="01b61-125">[Editor da tarefa fila de mensagens &#40;Enviar página&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="01b61-125">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 [<span data-ttu-id="01b61-126">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="01b61-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
