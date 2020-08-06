---
title: Editor do Gerenciador de conexões MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msmqconnectionmanager.f1
helpviewer_keywords:
- MSMQ Connection Manager Editor
ms.assetid: ef842cb4-82da-4550-85fe-9bedbc1e77c7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41d4231ce121d596c8d818485eccf5ddf6127470
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570112"
---
# <a name="msmq-connection-manager-editor"></a><span data-ttu-id="04bae-102">Editor do Gerenciador de Conexões MSMQ</span><span class="sxs-lookup"><span data-stu-id="04bae-102">MSMQ Connection Manager Editor</span></span>
  <span data-ttu-id="04bae-103">Use a caixa de diálogo **Gerenciador de Conexões MSMQ** para especificar o caminho do Serviço de Enfileiramento de Mensagens (também conhecido como MSMQ).</span><span class="sxs-lookup"><span data-stu-id="04bae-103">Use the **MSMQ Connection Manager** dialog box to specify the path to a Message Queuing (also known as MSMQ) message queue.</span></span>  
  
 <span data-ttu-id="04bae-104">Para saber mais sobre o Gerenciador de Conexões MSMQ, consulte [Gerenciador de Conexões MSMQ](connection-manager/msmq-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="04bae-104">To learn more about the MSMQ connection manager, see [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04bae-105">O gerenciador de conexões MSMQ aceita filas públicas e privadas locais e filas públicas remotas.</span><span class="sxs-lookup"><span data-stu-id="04bae-105">The MSMQ connection manager supports local public and private queues and remote public queues.</span></span> <span data-ttu-id="04bae-106">Não dá suporte a filas privadas remotas.</span><span class="sxs-lookup"><span data-stu-id="04bae-106">It does not support remote private queues.</span></span> <span data-ttu-id="04bae-107">Para obter uma solução alternativa que usa a tarefa Script, consulte [Enviando a uma fila de mensagens particular remota com a tarefa Script](control-flow/script-task.md).</span><span class="sxs-lookup"><span data-stu-id="04bae-107">For a workaround that uses the Script Task, see [Sending to a Remote Private Message Queue with the Script Task](control-flow/script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="04bae-108">Opções</span><span class="sxs-lookup"><span data-stu-id="04bae-108">Options</span></span>  
 <span data-ttu-id="04bae-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="04bae-109">**Name**</span></span>  
 <span data-ttu-id="04bae-110">Forneça um nome exclusivo para o gerenciador de conexões MSMQ no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="04bae-110">Provide a unique name for the MSMQ connection manager in the workflow.</span></span> <span data-ttu-id="04bae-111">O nome fornecido será exibido no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04bae-111">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="04bae-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="04bae-112">**Description**</span></span>  
 <span data-ttu-id="04bae-113">Descreva o gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="04bae-113">Describe the connection manager.</span></span> <span data-ttu-id="04bae-114">Como prática recomendável, descreva o gerenciador de conexões em termos de objetivo, para tornar os pacotes autodocumentados e mais fáceis de manter.</span><span class="sxs-lookup"><span data-stu-id="04bae-114">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="04bae-115">**Caminho**</span><span class="sxs-lookup"><span data-stu-id="04bae-115">**Path**</span></span>  
 <span data-ttu-id="04bae-116">Digite o caminho completo da fila de mensagens.</span><span class="sxs-lookup"><span data-stu-id="04bae-116">Type the complete path of the message queue.</span></span> <span data-ttu-id="04bae-117">O formato do caminho depende do tipo de fila.</span><span class="sxs-lookup"><span data-stu-id="04bae-117">The format of the path depends on the type of queue.</span></span>  
  
|<span data-ttu-id="04bae-118">Tipo de fila</span><span class="sxs-lookup"><span data-stu-id="04bae-118">Queue type</span></span>|<span data-ttu-id="04bae-119">Exemplo de caminho</span><span class="sxs-lookup"><span data-stu-id="04bae-119">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="04bae-120">Público</span><span class="sxs-lookup"><span data-stu-id="04bae-120">Public</span></span>|<span data-ttu-id="04bae-121">\<computer name>\\<nome da fila\></span><span class="sxs-lookup"><span data-stu-id="04bae-121">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="04bae-122">Privado</span><span class="sxs-lookup"><span data-stu-id="04bae-122">Private</span></span>|<span data-ttu-id="04bae-123">\<computer name>\Private$\\<nome da fila\></span><span class="sxs-lookup"><span data-stu-id="04bae-123">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="04bae-124">Você pode usar um "." para representar o computador local.</span><span class="sxs-lookup"><span data-stu-id="04bae-124">You can use "." to represent the local computer.</span></span>  
  
 <span data-ttu-id="04bae-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="04bae-125">**Test**</span></span>  
 <span data-ttu-id="04bae-126">Depois de configurar o Gerenciador de Conexões MSMQ, confirme se a conexão é viável clicando em **Testar**.</span><span class="sxs-lookup"><span data-stu-id="04bae-126">After configuring the MSMQ connection manager, confirm that the connection is viable by clicking **Test**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04bae-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="04bae-127">See Also</span></span>  
 [<span data-ttu-id="04bae-128">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="04bae-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
