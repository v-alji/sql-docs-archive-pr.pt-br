---
title: Provedor WMI para classes e propriedades de eventos de servidor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- event classes [WMI]
- WMI Provider for Server Events, events listed
- classes [WMI]
ms.assetid: e2916cd7-a3ed-41e6-97b4-2ee060754cbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 471e77cb7afa4e6aed441dcbbc8b3b70064f6737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684625"
---
# <a name="wmi-provider-for-server-events-classes-and-properties"></a><span data-ttu-id="8b4ca-102">Provedor WMI para classes e propriedades de eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="8b4ca-102">WMI Provider for Server Events Classes and Properties</span></span>
  <span data-ttu-id="8b4ca-103">Os eventos de servidor a seguir constituem o modelo de programação do Provedor WMI para eventos do servidor.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-103">The following server events make up the programming model for the WMI Provider for Server Events.</span></span> <span data-ttu-id="8b4ca-104">Há duas categorias principais de eventos que podem ser consultadas pela emissão de consultas de WQL no provedor.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-104">There are two main categories of events that can be queried by issuing WQL queries against the provider.</span></span> <span data-ttu-id="8b4ca-105">São os eventos DDL (linguagem de definição de dados) e eventos de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-105">These are data definition language (DDL) events and trace events.</span></span> <span data-ttu-id="8b4ca-106">Os eventos QUEUE_ACTIVATION e BROKER_QUEUE_DISABLED do agente de serviço também podem ser consultados.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-106">The QUEUE_ACTIVATION and BROKER_QUEUE_DISABLED service broker events can also be queried.</span></span> <span data-ttu-id="8b4ca-107">Observe a natureza inclusiva dos diagramas de árvore a seguir.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-107">Note the inclusive nature of the following tree diagrams.</span></span> <span data-ttu-id="8b4ca-108">Por exemplo, o evento DDL_ASSEMBLY_EVENTS inclui qualquer evento ALTER_ASSEMBLY, CREATE_ASSEMBLY e DROP_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-108">The DDL_ASSEMBLY_EVENTS event, for example, includes any ALTER_ASSEMBLY, CREATE_ASSEMBLY, and DROP_ASSEMBLY event.</span></span> <span data-ttu-id="8b4ca-109">Da mesma forma, o evento TRC_FULL_TEXT inclui qualquer evento FT_CRAWL_ABORTED, FT_CRAWL_STARTED e FT_CRAWL_STOPPED.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-109">Similarly, the TRC_FULL_TEXT event includes any FT_CRAWL_ABORTED, FT_CRAWL_STARTED, and FT_CRAWL_STOPPED event.</span></span> <span data-ttu-id="8b4ca-110">ALL_EVENTS cobre todos os eventos de DDL, eventos de rastreamento, QUEUE_ACTIVATION e BROKER_QUEUE_DISABLED.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-110">ALL_EVENTS covers all DDL events, trace events, QUEUE_ACTIVATION, and BROKER_QUEUE_DISABLED.</span></span>  
  
 <span data-ttu-id="8b4ca-111">Para saber quais propriedades podem ser examinadas de um evento ou grupo de eventos, consulte o esquema de evento.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-111">To learn which properties can be queried from an event or event group, refer to the event schema.</span></span> <span data-ttu-id="8b4ca-112">Por padrão, o esquema do evento é instalado no seguinte diretório: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events .xsd.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-112">By default, the event schema is installed in the following directory: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span></span>  
  
 <span data-ttu-id="8b4ca-113">Como alternativa, você pode consultar o esquema de evento publicado em [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100) .</span><span class="sxs-lookup"><span data-stu-id="8b4ca-113">Alternatively, you can refer to the event schema published at [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
 <span data-ttu-id="8b4ca-114">Por exemplo, recorrendo ao evento ALTER_DATABASE, você saberá que seu evento pai é DDL_SERVER_LEVEL_EVENTS e suas propriedades são `TSQLCommand` e `DatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-114">For example, by referring to the ALTER_DATABASE event, you will learn that its parent event is DDL_SERVER_LEVEL_EVENTS and its properties are `TSQLCommand` and `DatabaseName`.</span></span> <span data-ttu-id="8b4ca-115">O evento também herda as propriedades `SQLInstance`, `PostTime`, `ComputerName``SPID` e `LoginName`.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-115">The event also inherits the properties `SQLInstance`, `PostTime`, `ComputerName`, `SPID`, and `LoginName`.</span></span> <span data-ttu-id="8b4ca-116">O evento não tem nenhum evento filho.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-116">The event has no children events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b4ca-117">Os procedimentos armazenados do sistema que executam operações similares a DDL também podem acionar notificações de eventos.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-117">System stored procedures that perform DDL-like operations can also fire event notifications.</span></span> <span data-ttu-id="8b4ca-118">Teste as notificações de eventos para determinar suas respostas aos procedimentos armazenados que são executados.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-118">Test your event notifications to determine their responses to system stored procedures that are run.</span></span> <span data-ttu-id="8b4ca-119">Por exemplo, a instrução CREATE TYPE e **sp_addtype** procedimento armazenado acionarão uma notificação de evento que é criada em um evento CREATE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="8b4ca-119">For example, the CREATE TYPE statement and **sp_addtype** stored procedure will both fire an event notification that is created on a CREATE_TYPE event.</span></span> <span data-ttu-id="8b4ca-120">Para obter mais informações, consulte[eventos DDL](../../relational-databases/triggers/ddl-events.md).</span><span class="sxs-lookup"><span data-stu-id="8b4ca-120">For more information, see[DDL Events](../../relational-databases/triggers/ddl-events.md).</span></span>  
  
 <span data-ttu-id="8b4ca-121">**Eventos de linguagem de definição de dados e grupos de eventos**</span><span class="sxs-lookup"><span data-stu-id="8b4ca-121">**Data Definition Language Events and Event Groups**</span></span>  
  
 <span data-ttu-id="8b4ca-122">![Provedor WMI de Árvore de Eventos de Servidor.](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "Provedor WMI de Árvore de Eventos de Servidor.")</span><span class="sxs-lookup"><span data-stu-id="8b4ca-122">![WMI Provider for Server Events Event Tree](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "WMI Provider for Server Events Event Tree")</span></span>  
  
 <span data-ttu-id="8b4ca-123">**Eventos de rastreamento e grupos de eventos**</span><span class="sxs-lookup"><span data-stu-id="8b4ca-123">**Trace Events and Event Groups**</span></span>  
  
 <span data-ttu-id="8b4ca-124">![Eventos de rastreamento e grupos de evento](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Eventos de rastreamento e grupos de evento")</span><span class="sxs-lookup"><span data-stu-id="8b4ca-124">![Trace events and event groups](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Trace events and event groups")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b4ca-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b4ca-125">See Also</span></span>  
 <span data-ttu-id="8b4ca-126">[Provedor WMI para conceitos de eventos de servidor](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="8b4ca-126">[WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span></span>  
 [<span data-ttu-id="8b4ca-127">Usando o WQL com o Provedor WMI para eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="8b4ca-127">Using WQL with the WMI Provider for Server Events</span></span>](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md)  
  
  
