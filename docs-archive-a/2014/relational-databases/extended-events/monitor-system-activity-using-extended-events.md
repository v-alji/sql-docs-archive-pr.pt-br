---
title: Monitorar a atividade do sistema usando Eventos Estendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- xe
- extended events [SQL Server], monitoring system activity
ms.assetid: d83ad88f-818c-49fe-a9a9-299f704fca53
author: rothja
ms.author: jroth
ms.openlocfilehash: d847d156d8244ede533e684c9e6b753d7d7b5047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569468"
---
# <a name="monitor-system-activity-using-extended-events"></a><span data-ttu-id="df94c-102">Monitorar a atividade do sistema usando Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="df94c-102">Monitor System Activity Using Extended Events</span></span>
  <span data-ttu-id="df94c-103">Este procedimento ilustra como os Eventos Estendidos podem ser usados com o Rastreamento de Eventos do Windows (ETW) para monitorar a atividade do sistema.</span><span class="sxs-lookup"><span data-stu-id="df94c-103">This procedure illustrates how Extended Events can be used with Event Tracing for Windows (ETW) to monitor system activity.</span></span> <span data-ttu-id="df94c-104">O procedimento também mostra como são usadas as instruções CREATE EVENT SESSION, ALTER EVENT SESSION e DROP EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="df94c-104">The procedure also shows how the CREATE EVENT SESSION, ALTER EVENT SESSION, and DROP EVENT SESSION statements are used.</span></span>  
  
 <span data-ttu-id="df94c-105">A realização dessas tarefas envolve o uso do Editor de Consultas no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para aplicar o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="df94c-105">Accomplishing these tasks involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span> <span data-ttu-id="df94c-106">O procedimento também requer o uso do prompt de comando para executar comandos ETW.</span><span class="sxs-lookup"><span data-stu-id="df94c-106">The procedure also requires using the command prompt to run ETW commands.</span></span>  
  
### <a name="to-monitor-system-activity-using-extended-events"></a><span data-ttu-id="df94c-107">Para monitorar a atividade do sistema usando Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="df94c-107">To monitor system activity using Extended Events</span></span>  
  
1.  <span data-ttu-id="df94c-108">No Editor de Consultas, emita as instruções a seguir para criar uma sessão de eventos e adicionar dois eventos.</span><span class="sxs-lookup"><span data-stu-id="df94c-108">In Query Editor, issue the following statements to create an event session and add two events.</span></span> <span data-ttu-id="df94c-109">Esses eventos, checkpoint_begin e checkpoint_end, são acionados no início e no final de um ponto de verificação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="df94c-109">These events, checkpoint_begin and checkpoint_end, fire at the beginning and end of a database checkpoint.</span></span>  
  
    ```  
    CREATE EVENT SESSION test0  
    ON SERVER  
    ADD EVENT sqlserver.checkpoint_begin,  
    ADD EVENT sqlserver.checkpoint_end  
    WITH (MAX_DISPATCH_LATENCY = 1 SECONDS)  
    go  
    ```  
  
2.  <span data-ttu-id="df94c-110">Adicione o destino da segmentação com 32 segmentos, para contar o número de pontos de verificação com base na ID de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="df94c-110">Add the bucketing target with 32 buckets to count the number of checkpoints based on the database ID.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.histogram  
    (  
          SET slots = 32, filtering_event_name = 'sqlserver.checkpoint_end', source_type = 0, source = 'database_id'  
    )  
    go  
    ```  
  
3.  <span data-ttu-id="df94c-111">Emita as instruções a seguir para adicionar o destino do ETW.</span><span class="sxs-lookup"><span data-stu-id="df94c-111">Issue the following statements to add the ETW target.</span></span> <span data-ttu-id="df94c-112">Isso lhe permitirá examinar os eventos de início e fim, utilizados para determinar a duração do ponto de verificação.</span><span class="sxs-lookup"><span data-stu-id="df94c-112">This will enable you to see the begin and end events, which is used to determine how long the checkpoint takes.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.etw_classic_sync_target  
    go  
    ```  
  
4.  <span data-ttu-id="df94c-113">Emita as instruções a seguir para iniciar a sessão e começar a coleta de eventos.</span><span class="sxs-lookup"><span data-stu-id="df94c-113">Issue the following statements to start the session and begin event collection.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = start  
    go  
    ```  
  
5.  <span data-ttu-id="df94c-114">Emita as instruções a seguir para provocar o acionamento de três eventos.</span><span class="sxs-lookup"><span data-stu-id="df94c-114">Issue the following statements to cause three events to fire.</span></span>  
  
    ```  
    USE tempdb  
          checkpoint  
    go  
    USE master  
          checkpoint  
          checkpoint  
    go  
    ```  
  
6.  <span data-ttu-id="df94c-115">Emita as instruções a seguir para exibir as contagens dos eventos.</span><span class="sxs-lookup"><span data-stu-id="df94c-115">Issue the following statements to view the event counts.</span></span>  
  
    ```  
    SELECT CAST(xest.target_data AS xml) Bucketizer_Target_Data_in_XML  
    FROM sys.dm_xe_session_targets xest  
    JOIN sys.dm_xe_sessions xes ON xes.address = xest.event_session_address  
    JOIN sys.server_event_sessions ses ON xes.name = ses.name  
    WHERE xest.target_name = 'histogram' AND xes.name = 'test0'  
    go  
    ```  
  
7.  <span data-ttu-id="df94c-116">No prompt de comando, emita os comandos a seguir para exibir os dados do ETW.</span><span class="sxs-lookup"><span data-stu-id="df94c-116">At the command prompt, issue the following commands to view the ETW data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df94c-117">Para obter ajuda sobre o comando **tracerpt** , no prompt de comando, digite `tracerpt /?`.</span><span class="sxs-lookup"><span data-stu-id="df94c-117">To get help for the **tracerpt** command, at the command prompt, enter `tracerpt /?`.</span></span>  
  
    ```  
    logman query -ets --- List the ETW sessions. This is optional.  
    logman update XE_DEFAULT_ETW_SESSION -fd -ets --- Flush the ETW log.  
    tracerpt %temp%\xeetw.etl -o xeetw.txt --- Dump the events so they can be seen.  
    ```  
  
8.  <span data-ttu-id="df94c-118">Emita as instruções a seguir para parar a sessão de eventos e removê-la do servidor.</span><span class="sxs-lookup"><span data-stu-id="df94c-118">Issue the following statements to stop the event session and remove it from the server.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = STOP  
    go  
  
    DROP EVENT SESSION test0  
    ON SERVER  
    go  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="df94c-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df94c-119">See Also</span></span>  
 <span data-ttu-id="df94c-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="df94c-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="df94c-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="df94c-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 <span data-ttu-id="df94c-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="df94c-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="df94c-123">Exibições de catálogo de eventos estendidos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="df94c-123">Extended Events Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql)  
 <span data-ttu-id="df94c-124">[Exibições de gerenciamento dinâmico de eventos estendidos](../views/views.md) </span><span class="sxs-lookup"><span data-stu-id="df94c-124">[Extended Events Dynamic Management Views](../views/views.md) </span></span>  
 [<span data-ttu-id="df94c-125">Destinos de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="df94c-125">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
