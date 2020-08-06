---
title: Implementar notificações de evento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], target service
- target service [SQL Server]
- event notifications [SQL Server], creating
ms.assetid: 29ac8f68-a28a-4a77-b67b-a8663001308c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a89c66ca5c3b420fff14c087bd604b16c641369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574610"
---
# <a name="implement-event-notifications"></a><span data-ttu-id="b70ec-102">Implementar notificações de evento</span><span class="sxs-lookup"><span data-stu-id="b70ec-102">Implement Event Notifications</span></span>
  <span data-ttu-id="b70ec-103">Para implementar uma notificação de evento, antes é necessário criar um serviço de destino para receber as notificações de evento e só então a notificação.</span><span class="sxs-lookup"><span data-stu-id="b70ec-103">To implement an event notification, you must first create a target service to receive event notifications, and then create the event notification.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="b70ec-104">deve ser configurada para notificações de eventos que enviam mensagens a um agente de serviços em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="b70ec-104">dialog security should be configured for event notifications that send messages to a service broker on a remote server.</span></span> <span data-ttu-id="b70ec-105">A segurança de caixa de diálogo deve ser configurada manualmente, de acordo com o modelo de segurança completo.</span><span class="sxs-lookup"><span data-stu-id="b70ec-105">Dialog security must be configured manually according to the full security model.</span></span>  
  
## <a name="creating-the-target-service"></a><span data-ttu-id="b70ec-106">Criando o serviço de destino</span><span class="sxs-lookup"><span data-stu-id="b70ec-106">Creating the Target Service</span></span>  
 <span data-ttu-id="b70ec-107">Não é necessário criar um serviço que inicie o [!INCLUDE[ssSB](../../includes/sssb-md.md)], pois o [!INCLUDE[ssSB](../../includes/sssb-md.md)] inclui o tipo de mensagem específica e o contrato de notificação de evento a seguir:</span><span class="sxs-lookup"><span data-stu-id="b70ec-107">You do not have to create a [!INCLUDE[ssSB](../../includes/sssb-md.md)]-initiating service because [!INCLUDE[ssSB](../../includes/sssb-md.md)] includes the following specific message type and contract for event notifications:</span></span>  
  
```  
https://schemas.microsoft.com/SQL/Notifications/PostEventNotification  
```  
  
 <span data-ttu-id="b70ec-108">O serviço de destino que recebe as notificações de eventos deve honrar esse contrato preexistente.</span><span class="sxs-lookup"><span data-stu-id="b70ec-108">The target service that receives event notifications must honor this preexisting contract.</span></span>  
  
 <span data-ttu-id="b70ec-109">**Para criar um serviço de destino**:</span><span class="sxs-lookup"><span data-stu-id="b70ec-109">**To create a target service**:</span></span>  
  
1.  <span data-ttu-id="b70ec-110">Crie uma fila para receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="b70ec-110">Create a queue to receive messages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b70ec-111">A fila recebe o seguinte tipo de mensagem: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span><span class="sxs-lookup"><span data-stu-id="b70ec-111">The queue receives the following message type: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span></span>  
  
2.  <span data-ttu-id="b70ec-112">Crie um serviço na fila que faça referência ao contrato de notificações de evento.</span><span class="sxs-lookup"><span data-stu-id="b70ec-112">Create a service on the queue that references the event notifications contract.</span></span>  
  
3.  <span data-ttu-id="b70ec-113">Crie uma rota no serviço para definir o endereço para o qual o [!INCLUDE[ssSB](../../includes/sssb-md.md)] deve enviar mensagens para o serviço.</span><span class="sxs-lookup"><span data-stu-id="b70ec-113">Create a route on the service to define the address to which [!INCLUDE[ssSB](../../includes/sssb-md.md)] sends messages for the service.</span></span> <span data-ttu-id="b70ec-114">Para notificações de evento que visem um serviço no mesmo banco de dados, especifique `ADDRESS = 'LOCAL'`.</span><span class="sxs-lookup"><span data-stu-id="b70ec-114">For event notifications that target a service in the same database, specify `ADDRESS = 'LOCAL'`.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="b70ec-115">roteamento determina o serviço que recebe as mensagens de notificação.</span><span class="sxs-lookup"><span data-stu-id="b70ec-115">routing determines the service that receives the notification messages.</span></span> <span data-ttu-id="b70ec-116">Se a notificação de evento visar um serviço em um servidor remoto, tanto o servidor de origem, quanto o servidor de destino devem ter rotas definidas neles mesmos a fim de garantir a comunicação nas duas direções.</span><span class="sxs-lookup"><span data-stu-id="b70ec-116">If the event notification targets a service on a remote server, both the source server and the target server must have routes defined on them to make sure that two-way communication occurs.</span></span>  
  
 <span data-ttu-id="b70ec-117">O exemplo a seguir cria uma fila, um serviço na fila e uma rota no serviço para manipular mensagens do contrato de notificação de evento.</span><span class="sxs-lookup"><span data-stu-id="b70ec-117">The following example creates a queue, a service on the queue, and a route on the service to handle messages from the event notification contract.</span></span>  
  
```  
CREATE QUEUE NotifyQueue ;  
GO  
CREATE SERVICE NotifyService  
ON QUEUE NotifyQueue  
(  
[https://schemas.microsoft.com/SQL/Notifications/PostEventNotification]  
);  
GO  
CREATE ROUTE NotifyRoute  
WITH SERVICE_NAME = 'NotifyService',  
ADDRESS = 'LOCAL';  
GO  
```  
  
## <a name="creating-the-event-notification"></a><span data-ttu-id="b70ec-118">Criando a notificação de evento</span><span class="sxs-lookup"><span data-stu-id="b70ec-118">Creating the Event Notification</span></span>  
 <span data-ttu-id="b70ec-119">As notificações de evento são criadas por meio da instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION e descartadas pela instrução DROP EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="b70ec-119">Event notifications are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION statement, and are dropped by using the DROP EVENT NOTIFICATION STATEMENT.</span></span> <span data-ttu-id="b70ec-120">Para modificar uma notificação de evento, você deve descartar e recriar a notificação de evento.</span><span class="sxs-lookup"><span data-stu-id="b70ec-120">To modify an event notification, you must drop and re-create the event notification.</span></span>  
  
 <span data-ttu-id="b70ec-121">O exemplo a seguir cria a notificação de evento `CreateDatabaseNotification`.</span><span class="sxs-lookup"><span data-stu-id="b70ec-121">The following example creates the event notification `CreateDatabaseNotification`.</span></span> <span data-ttu-id="b70ec-122">Essa notificação envia uma mensagem sobre quaisquer eventos `CREATE_DATABASE` que ocorrerem no servidor para o serviço `NotifyService` criado previamente.</span><span class="sxs-lookup"><span data-stu-id="b70ec-122">This notification sends a message about any `CREATE_DATABASE` event that occurs on the server to the `NotifyService` service that was previously created.</span></span>  
  
```  
CREATE EVENT NOTIFICATION CreateDatabaseNotification  
ON SERVER  
FOR CREATE_DATABASE  
TO SERVICE 'NotifyService', '8140a771-3c4b-4479-8ac0-81008ab17984' ;  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="b70ec-123">Notificações de evento reconhecem eventos CREATE_SCHEMA e definições <schema_element> de instruções CREATE SCHEMA como eventos separados.</span><span class="sxs-lookup"><span data-stu-id="b70ec-123">Event notifications recognize CREATE_SCHEMA events and the <schema_element> definitions of CREATE SCHEMA statements as separate events.</span></span> <span data-ttu-id="b70ec-124">Por exemplo, suponha que seja criada  uma notificação de evento nos eventos CREATE_SCHEMA e CREATE_TABLE e você execute o lote a seguir.</span><span class="sxs-lookup"><span data-stu-id="b70ec-124">For example, an event notification is created on both the CREATE_SCHEMA and CREATE_TABLE events, and you run the following batch.</span></span>  
>   
>  `CREATE SCHEMA s`  
>   
>  `CREATE TABLE t1 (col1 int)`  
>   
>  <span data-ttu-id="b70ec-125">Nesse caso, a notificação de evento é emitida duas vezes: uma, quando ocorre o evento CREATE_SCHEMA e, outra vez, quando ocorre o evento CREATE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="b70ec-125">In this case, the event notification is raised two times: Onne time when the CREATE_SCHEMA event occurs, and again when the CREATE_TABLE event occurs.</span></span> <span data-ttu-id="b70ec-126">Recomendamos evitar criar notificações de evento ao mesmo tempo em eventos CREATE_SCHEMA e em textos <schema_element> de quaisquer definições CREATE SCHEMA correspondentes ou criar lógica em seu aplicativo para evitar capturar dados de eventos indesejados.</span><span class="sxs-lookup"><span data-stu-id="b70ec-126">We recommend that you either avoid creating event notifications on both the CREATE_SCHEMA events and the <schema_element> texts of any corresponding CREATE SCHEMA definitions, or build logic into your application to avoid capturing unwanted event data.</span></span>  
  
 <span data-ttu-id="b70ec-127">**Para criar uma notificação de evento**</span><span class="sxs-lookup"><span data-stu-id="b70ec-127">**To create an event notification**</span></span>  
  
-   [<span data-ttu-id="b70ec-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b70ec-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-notification-transact-sql)  
  
 <span data-ttu-id="b70ec-129">**Para descartar uma notificação de evento**</span><span class="sxs-lookup"><span data-stu-id="b70ec-129">**To drop an event notification**</span></span>  
  
-   [<span data-ttu-id="b70ec-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b70ec-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-event-notification-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="b70ec-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b70ec-131">See Also</span></span>  
 <span data-ttu-id="b70ec-132">[Obter informações sobre notificações de eventos](event-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="b70ec-132">[Get Information About Event Notifications](event-notifications.md) </span></span>  
 [<span data-ttu-id="b70ec-133">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b70ec-133">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
