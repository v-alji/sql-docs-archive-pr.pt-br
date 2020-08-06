---
title: Obter informações sobre notificações de eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], metadata
- status information [SQL Server], event notifications
- metadata [SQL Server], event notifications
ms.assetid: 8bc10867-66d6-4f57-ac32-a6c29f3327cd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8d8271b6279910321058d01c7b2f96b1df62bd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680857"
---
# <a name="get-information-about-event-notifications"></a><span data-ttu-id="16266-102">Obter informações sobre notificações de eventos</span><span class="sxs-lookup"><span data-stu-id="16266-102">Get Information About Event Notifications</span></span>
  <span data-ttu-id="16266-103">As exibições de catálogo a seguir estão disponíveis para consultar metadados sobre notificações de eventos.</span><span class="sxs-lookup"><span data-stu-id="16266-103">The following catalog views are available to query metadata about event notifications.</span></span>  
  
 <span data-ttu-id="16266-104">**Para obter informações sobre notificações de eventos em nível que não seja de servidor**</span><span class="sxs-lookup"><span data-stu-id="16266-104">**To get information about nonserver-level event notifications**</span></span>  
  
-   [<span data-ttu-id="16266-105">sys.event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="16266-105">sys.event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="16266-106">Para exibir metadados sobre qualquer notificação de eventos em **sys.event_notifications** criada no nível do banco de dados, é necessário ter, no mínimo, o seguinte: permissão CONTROL, ALTER, TAKE OWNERSHIP ou VIEW DEFINITION no banco de dados, permissão ALTER ANY DATABASE EVENT NOTIFICATION ou ser o proprietário da notificação de eventos.</span><span class="sxs-lookup"><span data-stu-id="16266-106">To view metadata about any event notification in **sys.event_notifications** created at the database level, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the database, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span> <span data-ttu-id="16266-107">Para notificações de eventos criadas em uma fila específica, é necessário ter, no mínimo, o seguinte: permissão CONTROL, ALTER, TAKE OWNERSHIP ou VIEW DEFINITION no objeto, permissão ALTER ANY DATABASE EVENT NOTIFICATION ou ser o proprietário da notificação de eventos.</span><span class="sxs-lookup"><span data-stu-id="16266-107">For event notifications created on a specific queue, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the object, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span>  
  
 <span data-ttu-id="16266-108">**Para obter informações sobre notificações de eventos em nível de servidor**</span><span class="sxs-lookup"><span data-stu-id="16266-108">**To get information about server-level event notifications**</span></span>  
  
-   [<span data-ttu-id="16266-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="16266-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="16266-110">É necessário ter, no mínimo, o seguinte: permissão CONTROL ou VIEW ANY DEFINITION no servidor, permissão ALTER ANY EVENT NOTIFICATION ou ser o logon ou proprietário da notificação de eventos para poder exibir metadados sobre qualquer notificação de eventos em **sys.server_event_notifications**.</span><span class="sxs-lookup"><span data-stu-id="16266-110">At the minimum, you must have the following: CONTROL or VIEW ANY DEFINITION permission on the server, be the logon or owner of the event notification, or have ALTER ANY EVENT NOTIFICATION permission to view metadata about any event notification in **sys.server_event_notifications**.</span></span>  
  
 <span data-ttu-id="16266-111">**Para obter informações sobre todos os eventos que podem acionar notificações de eventos**</span><span class="sxs-lookup"><span data-stu-id="16266-111">**To get information about all events that can fire event notifications**</span></span>  
  
-   [<span data-ttu-id="16266-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="16266-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notification-event-types-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="16266-113">Essa exibição de catálogo não retorna grupos de eventos.</span><span class="sxs-lookup"><span data-stu-id="16266-113">This catalog view does not return event groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16266-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16266-114">See Also</span></span>  
 [<span data-ttu-id="16266-115">Notificações de eventos</span><span class="sxs-lookup"><span data-stu-id="16266-115">Event Notifications</span></span>](event-notifications.md)  
  
  
