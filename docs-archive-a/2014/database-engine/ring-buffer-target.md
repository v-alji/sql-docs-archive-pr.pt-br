---
title: Destino do buffer de anéis | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events], ring buffer target
- ring buffer target [SQL Server extended events]
ms.assetid: 54494e11-b56b-43b7-aa5e-c8724e56b251
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 186e847bb9f9b621543119c25510dc5d6107e274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582102"
---
# <a name="ring-buffer-target"></a><span data-ttu-id="dffb4-102">Destino de buffer de anel</span><span class="sxs-lookup"><span data-stu-id="dffb4-102">Ring Buffer Target</span></span>
  <span data-ttu-id="dffb4-103">O destino de buffer de anel mantém brevemente dados de eventos na memória.</span><span class="sxs-lookup"><span data-stu-id="dffb4-103">The ring buffer target briefly holds event data in memory.</span></span> <span data-ttu-id="dffb4-104">Esse destino pode gerenciar eventos de uma das duas maneiras possíveis.</span><span class="sxs-lookup"><span data-stu-id="dffb4-104">This target can manage events in one of two modes.</span></span>  
  
-   <span data-ttu-id="dffb4-105">O primeiro modo é basicamente o FIFO (primeiro a entrar, primeiro a sair), no qual o evento mais antigo é descartado quando toda a memória alocada ao destino é usada.</span><span class="sxs-lookup"><span data-stu-id="dffb4-105">The first mode is strict first-in first-out (FIFO), where the oldest event is discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="dffb4-106">Nesse modo (o padrão), a opção occurrence_number é definida como 0.</span><span class="sxs-lookup"><span data-stu-id="dffb4-106">In this mode (the default), the occurrence_number option is set to 0.</span></span>  
  
-   <span data-ttu-id="dffb4-107">O segundo modo é o FIFO por evento, no qual um número especificado de eventos de cada tipo é mantido.</span><span class="sxs-lookup"><span data-stu-id="dffb4-107">The second mode is per-event FIFO, where a specified number of events of each type is kept.</span></span> <span data-ttu-id="dffb4-108">Nesse modo, os eventos mais antigos de cada tipo são descartados quando toda a memória alocada para o destino é usada.</span><span class="sxs-lookup"><span data-stu-id="dffb4-108">In this mode, the oldest events of each type are discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="dffb4-109">Você pode configurar a opção occurrence_number para especificar o número de eventos de cada tipo a ser mantido.</span><span class="sxs-lookup"><span data-stu-id="dffb4-109">You can configure the occurrence_number option to specify the number of events of each type to keep.</span></span>  
  
 <span data-ttu-id="dffb4-110">A tabela a seguir descreve as opções disponíveis para configurar o destino de buffer de anel.</span><span class="sxs-lookup"><span data-stu-id="dffb4-110">The following table describes the available options for configuring the ring buffer target.</span></span>  
  
|<span data-ttu-id="dffb4-111">Opção</span><span class="sxs-lookup"><span data-stu-id="dffb4-111">Option</span></span>|<span data-ttu-id="dffb4-112">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="dffb4-112">Allowed values</span></span>|<span data-ttu-id="dffb4-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="dffb4-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="dffb4-114">max_memory</span><span class="sxs-lookup"><span data-stu-id="dffb4-114">max_memory</span></span>|<span data-ttu-id="dffb4-115">Qualquer inteiro de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="dffb4-115">Any 32-bit integer.</span></span> <span data-ttu-id="dffb4-116">Esse valor é opcional.</span><span class="sxs-lookup"><span data-stu-id="dffb4-116">This value is optional.</span></span>|<span data-ttu-id="dffb4-117">A quantidade máxima de memória, em kilobytes (KB), para usar.</span><span class="sxs-lookup"><span data-stu-id="dffb4-117">The maximum amount of memory in kilobytes (KB) to use.</span></span> <span data-ttu-id="dffb4-118">Os eventos existentes são descartados com base no limite atingido primeiro: max_event_limit ou max_memory.</span><span class="sxs-lookup"><span data-stu-id="dffb4-118">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="dffb4-119">O valor máximo é 4194303 KB.</span><span class="sxs-lookup"><span data-stu-id="dffb4-119">The maximum value is 4194303 KB.</span></span> <span data-ttu-id="dffb4-120">Uma consideração cuidadosa deve ser feita antes de definir o tamanho do buffer de anéis para limites no intervalo de GB, pois ele pode afetar outros consumidores de memória no SQL Server</span><span class="sxs-lookup"><span data-stu-id="dffb4-120">A careful consideration should be made before setting the ring buffer size to limits in the GB range as it may impact other memory consumers in SQL Server</span></span>|  
|<span data-ttu-id="dffb4-121">max_event_limit</span><span class="sxs-lookup"><span data-stu-id="dffb4-121">max_event_limit</span></span>|<span data-ttu-id="dffb4-122">Qualquer inteiro de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="dffb4-122">Any 32-bit integer.</span></span> <span data-ttu-id="dffb4-123">Esse valor é opcional.</span><span class="sxs-lookup"><span data-stu-id="dffb4-123">This value is optional.</span></span>|<span data-ttu-id="dffb4-124">O número máximo de eventos mantidos no ring_buffer.</span><span class="sxs-lookup"><span data-stu-id="dffb4-124">The maximum number of events kept in the ring_buffer.</span></span> <span data-ttu-id="dffb4-125">Os eventos existentes são descartados com base no limite atingido primeiro: max_event_limit ou max_memory.</span><span class="sxs-lookup"><span data-stu-id="dffb4-125">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="dffb4-126">Padrão = 1000.</span><span class="sxs-lookup"><span data-stu-id="dffb4-126">Default = 1000.</span></span>|  
|<span data-ttu-id="dffb4-127">occurrence_number</span><span class="sxs-lookup"><span data-stu-id="dffb4-127">occurrence_number</span></span>|<span data-ttu-id="dffb4-128">Um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="dffb4-128">One of the following values:</span></span><br /><br /> <span data-ttu-id="dffb4-129">0 (o padrão) = O evento mais antigo é descartado quando toda a memória alocada ao destino é usada.</span><span class="sxs-lookup"><span data-stu-id="dffb4-129">0 (the default) = Oldest event is discarded when all the memory allocated to the target is used.</span></span><br /><br /> <span data-ttu-id="dffb4-130">Qualquer inteiro de 32 bits = o número de eventos de cada tipo a ser mantido antes de ser descartado em uma base FIFO por evento.</span><span class="sxs-lookup"><span data-stu-id="dffb4-130">Any 32-bit integer = The number of events of each type to keep before being discarded on a per-event FIFO basis.</span></span><br /><br /> <br /><br /> <span data-ttu-id="dffb4-131">Esse valor é opcional.</span><span class="sxs-lookup"><span data-stu-id="dffb4-131">This value is optional.</span></span>|<span data-ttu-id="dffb4-132">O modo FIFO a ser usado e, se definido com um valor maior que 0, o número preferencial de eventos de cada tipo a ser mantido no buffer.</span><span class="sxs-lookup"><span data-stu-id="dffb4-132">The FIFO mode to use, and, if set to a value greater than 0, the preferred number of events of each type to keep in the buffer.</span></span>|
| &nbsp; | &nbsp; | &nbsp; |
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="dffb4-133">Adicionando o destino a uma sessão</span><span class="sxs-lookup"><span data-stu-id="dffb4-133">Adding the Target to a Session</span></span>  
 <span data-ttu-id="dffb4-134">Para adicionar o destino de buffer de anel a uma sessão de Eventos Estendidos, você deve incluir a instrução a seguir ao criar ou alterar uma sessão de evento:</span><span class="sxs-lookup"><span data-stu-id="dffb4-134">To add the ring buffer target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```sql
ADD TARGET package0.ring_buffer  
```  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="dffb4-135">Revisando a saída de destino</span><span class="sxs-lookup"><span data-stu-id="dffb4-135">Reviewing the Target Output</span></span>  
 <span data-ttu-id="dffb4-136">Para examinar o destino do buffer de anel, você pode usar a consulta a seguir com a substituição de *session_name* pelo nome da sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="dffb4-136">To review the output from the ring buffer target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```sql
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="dffb4-137">O exemplo a seguir mostra o formato de saída do destino do buffer de anel.</span><span class="sxs-lookup"><span data-stu-id="dffb4-137">The following example shows the ring buffer target output format.</span></span>  
  
```  
<RingBufferTarget eventsPerSec="" processingTime="" totalEventsProcessed="" eventCount="" droppedCount="" memoryUsed="">  
 <event name="" package="" id="" version="" timestamp="">  
    <data name="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </data>  
    <action name="" package="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </action>  
  </event>  
</RingBufferTarget>  
```


## <a name="see-also"></a><span data-ttu-id="dffb4-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dffb4-138">See Also</span></span>

- [<span data-ttu-id="dffb4-139">Destinos de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="dffb4-139">SQL Server Extended Events Targets</span></span>](../../2014/database-engine/sql-server-extended-events-targets.md)
- [<span data-ttu-id="dffb4-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dffb4-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="dffb4-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dffb4-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-session-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="dffb4-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dffb4-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](https://docs.microsoft.com/sql/t-sql/statements/alter-event-session-transact-sql?view=sql-server-2016)

