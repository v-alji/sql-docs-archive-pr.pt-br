---
title: MSSQL_ENG014160 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014160 error
ms.assetid: d0f3855e-d095-4a81-a5bd-9d7ad51f2c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3351567a31a0a0384ab8957073ab0457ef0ea7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569359"
---
# <a name="mssql_eng014160"></a><span data-ttu-id="73b76-102">MSSQL_ENG014160</span><span class="sxs-lookup"><span data-stu-id="73b76-102">MSSQL_ENG014160</span></span>
    
## <a name="message-details"></a><span data-ttu-id="73b76-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="73b76-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73b76-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="73b76-104">Product Name</span></span>|<span data-ttu-id="73b76-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="73b76-105">SQL Server</span></span>|  
|<span data-ttu-id="73b76-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="73b76-106">Event ID</span></span>|<span data-ttu-id="73b76-107">14160</span><span class="sxs-lookup"><span data-stu-id="73b76-107">14160</span></span>|  
|<span data-ttu-id="73b76-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="73b76-108">Event Source</span></span>|<span data-ttu-id="73b76-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="73b76-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="73b76-110">Componente</span><span class="sxs-lookup"><span data-stu-id="73b76-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="73b76-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="73b76-111">Symbolic Name</span></span>||  
|<span data-ttu-id="73b76-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="73b76-112">Message Text</span></span>|<span data-ttu-id="73b76-113">O limite [%s:%s] da publicação [%s] foi definido.</span><span class="sxs-lookup"><span data-stu-id="73b76-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="73b76-114">Uma ou mais assinaturas nesta publicação expiraram.</span><span class="sxs-lookup"><span data-stu-id="73b76-114">One or more subscriptions to this publication have expired.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="73b76-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="73b76-115">Explanation</span></span>  
 <span data-ttu-id="73b76-116">A replicação permite habilitar avisos para várias condições.</span><span class="sxs-lookup"><span data-stu-id="73b76-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="73b76-117">Isso inclui expiração de assinatura iminente.</span><span class="sxs-lookup"><span data-stu-id="73b76-117">This includes imminent subscription expiration.</span></span> <span data-ttu-id="73b76-118">As assinaturas podem expirar se não forem sincronizadas em um *período de retenção*especificado.</span><span class="sxs-lookup"><span data-stu-id="73b76-118">Subscriptions can expire if they are not synchronized within a specified *retention period*.</span></span> <span data-ttu-id="73b76-119">Para obter mais informações, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="73b76-119">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="73b76-120">Ao habilitar um aviso usando o Replication Monitor ou o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), você especifica um limite que determina quando um aviso é disparado.</span><span class="sxs-lookup"><span data-stu-id="73b76-120">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="73b76-121">Quando esse limite é atingido ou excedido, um aviso é exibido no Replication Monitor e um evento é gravado no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="73b76-121">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="73b76-122">Ao atingir um limite, também é possível disparar um alerta do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="73b76-122">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="73b76-123">Para obter mais informações, consulte [Definir limites e avisos no Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) e [Monitorar a replicação de forma programática](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="73b76-123">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73b76-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="73b76-124">User Action</span></span>  
 <span data-ttu-id="73b76-125">A solução desse problema depende do motivo pelo qual o aviso foi gerado:</span><span class="sxs-lookup"><span data-stu-id="73b76-125">The resolution for this issue depends on the reason the warning was raised:</span></span>  
  
-   <span data-ttu-id="73b76-126">Se o limite foi excedido, mas a assinatura ainda não expirou, sincronize a assinatura.</span><span class="sxs-lookup"><span data-stu-id="73b76-126">If the threshold has been exceeded, but the subscription has not yet expired, synchronize the subscription.</span></span> <span data-ttu-id="73b76-127">Para obter mais informações, consulte [Sincronizar dados](synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="73b76-127">For more information, see [Synchronize Data](synchronize-data.md).</span></span>  
  
-   <span data-ttu-id="73b76-128">Se o agente estiver em execução, mas não estiver replicando alterações corretamente, isso pode fazer com que a assinatura expire.</span><span class="sxs-lookup"><span data-stu-id="73b76-128">If the agent has been running, but has not been replicating changes properly, this can cause the subscription to expire.</span></span> <span data-ttu-id="73b76-129">Para replicação transacional, certifique-se de que o Distribution Agent e o Log Reader Agent estão em execução.</span><span class="sxs-lookup"><span data-stu-id="73b76-129">For transactional replication, make sure that the Distribution Agent and Log Reader Agent are running.</span></span> <span data-ttu-id="73b76-130">Para replicação de mesclagem, certifique-se de que o Merge Agent está em execução.</span><span class="sxs-lookup"><span data-stu-id="73b76-130">For merge replication, make sure the Merge Agent is running.</span></span> <span data-ttu-id="73b76-131">Para obter informações sobre como iniciar esses agentes, consulte [iniciar e parar um Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) e [conceitos dos executáveis do agente de replicação](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="73b76-131">For information about how to start these agents, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="73b76-132">Se a assinatura tiver expirado, será necessário reiniciar ou descartar e recriar a assinatura, dependendo do tipo de assinatura e há quanto tempo expirou.</span><span class="sxs-lookup"><span data-stu-id="73b76-132">If the subscription has expired, it must either be reinitialized or dropped and re-created, depending on the type of subscription and how long it has been expired.</span></span> <span data-ttu-id="73b76-133">Para obter mais informações, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="73b76-133">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b76-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73b76-134">See Also</span></span>  
 [<span data-ttu-id="73b76-135">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="73b76-135">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
