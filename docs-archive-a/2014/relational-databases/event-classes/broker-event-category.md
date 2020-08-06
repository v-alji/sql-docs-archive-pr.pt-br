---
title: Categoria de evento Broker | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Broker event category
- Broker event category [SQL Server]
- event classes [SQL Server], Broker event category
ms.assetid: 470dc93c-0dda-4d89-829b-937738d59b31
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23f839416e3404bfdf0a7e61d1b1e8dbbb90ec95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570070"
---
# <a name="broker-event-category"></a><span data-ttu-id="45264-102">Categoria de evento Broker</span><span class="sxs-lookup"><span data-stu-id="45264-102">Broker Event Category</span></span>
  <span data-ttu-id="45264-103">A categoria de evento **Broker** contém eventos gerais do Service Broker.</span><span class="sxs-lookup"><span data-stu-id="45264-103">The **Broker** event category contains general Service Broker events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45264-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="45264-104">In This Section</span></span>  
  
|<span data-ttu-id="45264-105">Tópico</span><span class="sxs-lookup"><span data-stu-id="45264-105">Topic</span></span>|<span data-ttu-id="45264-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="45264-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="45264-107">Classe de evento Broker:Activation</span><span class="sxs-lookup"><span data-stu-id="45264-107">Broker:Activation Event Class</span></span>](broker-activation-event-class.md)|<span data-ttu-id="45264-108">Um evento gerado quando um monitor de fila inicia um procedimento armazenado de ativação.</span><span class="sxs-lookup"><span data-stu-id="45264-108">An event generated when a queue monitor starts an activation stored procedure.</span></span>|  
|[<span data-ttu-id="45264-109">Classe de evento Broker:Connection</span><span class="sxs-lookup"><span data-stu-id="45264-109">Broker:Connection Event Class</span></span>](broker-connection-event-class.md)|<span data-ttu-id="45264-110">Um evento gerado para informar o status de uma conexão de transporte gerenciada pelo Service Broker.</span><span class="sxs-lookup"><span data-stu-id="45264-110">An event generated to report the status of a transport connection managed by Service Broker.</span></span>|  
|[<span data-ttu-id="45264-111">Classe de evento Broker:Conversation</span><span class="sxs-lookup"><span data-stu-id="45264-111">Broker:Conversation Event Class</span></span>](broker-conversation-event-class.md)|<span data-ttu-id="45264-112">Um evento gerado para reportar o progresso de uma conversa.</span><span class="sxs-lookup"><span data-stu-id="45264-112">An event generated to report the progress of a conversation.</span></span>|  
|[<span data-ttu-id="45264-113">Classe de evento Broker:Conversation Group</span><span class="sxs-lookup"><span data-stu-id="45264-113">Broker:Conversation Group Event Class</span></span>](broker-conversation-group-event-class.md)|<span data-ttu-id="45264-114">Um evento gerado quando o banco de dados cria ou descarta um grupo de conversa.</span><span class="sxs-lookup"><span data-stu-id="45264-114">An event generated when the database creates or drops a conversation group.</span></span>|  
|[<span data-ttu-id="45264-115">Classe de evento Broker:Corrupted Message</span><span class="sxs-lookup"><span data-stu-id="45264-115">Broker:Corrupted Message Event Class</span></span>](broker-corrupted-message-event-class.md)|<span data-ttu-id="45264-116">Um evento gerado para informar que o banco de dados recebeu uma mensagem corrompida.</span><span class="sxs-lookup"><span data-stu-id="45264-116">An event generated to report that the database has received a corrupt message.</span></span>|  
|[<span data-ttu-id="45264-117">Classe de evento Broker:Forwarded Message Dropped</span><span class="sxs-lookup"><span data-stu-id="45264-117">Broker:Forwarded Message Dropped Event Class</span></span>](broker-forwarded-message-dropped-event-class.md)|<span data-ttu-id="45264-118">Um evento gerado quando o SQL Server descarta uma mensagem do Service Broker que deveria ter sido encaminhada.</span><span class="sxs-lookup"><span data-stu-id="45264-118">An event generated when SQL Server drops a Service Broker message that was to have been forwarded.</span></span>|  
|[<span data-ttu-id="45264-119">Classe de evento Broker:Forwarded Message Sent</span><span class="sxs-lookup"><span data-stu-id="45264-119">Broker:Forwarded Message Sent Event Class</span></span>](broker-forwarded-message-sent-event-class.md)|<span data-ttu-id="45264-120">Um evento gerado quando o SQL Server encaminha uma mensagem do Service Broker.</span><span class="sxs-lookup"><span data-stu-id="45264-120">An event generated when SQL Server forwards a Service Broker message.</span></span>|  
|[<span data-ttu-id="45264-121">Classe de evento Broker:Message Classify</span><span class="sxs-lookup"><span data-stu-id="45264-121">Broker:Message Classify Event Class</span></span>](broker-message-classify-event-class.md)|<span data-ttu-id="45264-122">Um evento gerado quando o Service Broker determina o roteamento de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="45264-122">An event generated when Service Broker determines the routing for a message.</span></span>|  
|[<span data-ttu-id="45264-123">Classe de evento Broker:Message Drop</span><span class="sxs-lookup"><span data-stu-id="45264-123">Broker:Message Drop Event Class</span></span>](broker-message-drop-event-class.md)|<span data-ttu-id="45264-124">Um evento gerado quando o Service Broker é incapaz de reter uma mensagem recebida que deveria ter sido entregue a um serviço dessa instância.</span><span class="sxs-lookup"><span data-stu-id="45264-124">An event generated when Service Broker is unable to retain a received message that should have been delivered to a service in this instance</span></span>|  
|[<span data-ttu-id="45264-125">Agente: Classe de evento Remote Message Ack</span><span class="sxs-lookup"><span data-stu-id="45264-125">Broker:Remote Message Ack Event Class</span></span>](broker-remote-message-ack-event-class.md)|<span data-ttu-id="45264-126">Um evento gerado quando o Service Broker envia ou recebe uma confirmação de mensagem.</span><span class="sxs-lookup"><span data-stu-id="45264-126">An event generated when Service Broker sends or receives a message acknowledgement.</span></span>|  
  
 <span data-ttu-id="45264-127">Também são fornecidos dois eventos de auditoria de segurança para o Service Broker.</span><span class="sxs-lookup"><span data-stu-id="45264-127">Two security audit events are also provided for Service Broker.</span></span> <span data-ttu-id="45264-128">Para obter mais informações sobre esses eventos, consulte [Classe de evento Audit Broker Login](audit-broker-login-event-class.md) e [Classe de evento Audit Broker Conversation](audit-broker-conversation-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="45264-128">For more information on those events, see [Audit Broker Login Event Class](audit-broker-login-event-class.md) and [Audit Broker Conversation Event Class](audit-broker-conversation-event-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45264-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45264-129">See Also</span></span>  
 [<span data-ttu-id="45264-130">Categoria de evento de auditoria de segurança</span><span class="sxs-lookup"><span data-stu-id="45264-130">Security Audit Event Category</span></span>](https://docs.microsoft.com/bi-reference/trace-events/security-audit-event-category)  
  
  
