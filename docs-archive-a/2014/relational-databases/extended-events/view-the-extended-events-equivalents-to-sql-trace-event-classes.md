---
title: Exibir os Eventos Estendidos equivalentes às classes do Rastreamento do SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, extended events equivalents
- extended events [SQL Server], SQL Trace equivalents
- extended events [SQL Server], user configurable events
ms.assetid: 7f24104c-201d-4361-9759-f78a27936011
author: rothja
ms.author: jroth
ms.openlocfilehash: 37459359f9f6cb7e3951b705c4007477ec43e36a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678737"
---
# <a name="view-the-extended-events-equivalents-to-sql-trace-event-classes"></a><span data-ttu-id="b4e1e-102">Exibir os Eventos Estendidos equivalentes às classes de evento de Rastreamento do SQL</span><span class="sxs-lookup"><span data-stu-id="b4e1e-102">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>
  <span data-ttu-id="b4e1e-103">Se você desejar usar os Eventos Estendidos para coletar dados de evento equivalentes a colunas e classes de evento do Rastreamento do SQL, será útil entender como os eventos do Rastreamento do SQL são mapeados para os eventos e as ações dos Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-103">If you want to use Extended Events to collect event data that is equivalent to SQL Trace event classes and columns, it is useful to understand how the SQL Trace events map to Extended Events events and actions.</span></span>  
  
 <span data-ttu-id="b4e1e-104">Você pode usar o seguinte procedimento para exibir os eventos e as ações dos Eventos Estendidos que são equivalentes a cada evento do Rastreamento do SQL e suas colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-104">You can use the following procedure to view the Extended Events events and actions that are equivalent to each SQL Trace event and its associated columns.</span></span>  
  
## <a name="to-view-the-extended-events-equivalents-to-sql-trace-events-using-query-editor"></a><span data-ttu-id="b4e1e-105">Para exibir os equivalentes de Eventos Estendidos a eventos do Rastreamento do SQL usando o Editor de Consulta</span><span class="sxs-lookup"><span data-stu-id="b4e1e-105">To view the Extended Events equivalents to SQL Trace events using Query Editor</span></span>  
  
-   <span data-ttu-id="b4e1e-106">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], execute a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-106">From Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], run the following query:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    SELECT DISTINCT  
       tb.trace_event_id,  
       te.name AS 'Event Class',  
       em.package_name AS 'Package',  
       em.xe_event_name AS 'XEvent Name',  
       tb.trace_column_id,  
       tc.name AS 'SQL Trace Column',  
       am.xe_action_name as 'Extended Events action'  
    FROM (sys.trace_events te LEFT OUTER JOIN sys.trace_xe_event_map em  
       ON te.trace_event_id = em.trace_event_id) LEFT OUTER JOIN sys.trace_event_bindings tb  
       ON em.trace_event_id = tb.trace_event_id LEFT OUTER JOIN sys.trace_columns tc  
       ON tb.trace_column_id = tc.trace_column_id LEFT OUTER JOIN sys.trace_xe_action_map am  
       ON tc.trace_column_id = am.trace_column_id  
    ORDER BY te.name, tc.name  
    ```  
  
 <span data-ttu-id="b4e1e-107">Ao exibir os resultados, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-107">When you view the results, note the following:</span></span>  
  
-   <span data-ttu-id="b4e1e-108">Se todas as colunas retornarem NULL com exceção da coluna Event Class, isso indicará que a classe de evento não foi migrada do Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-108">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="b4e1e-109">Se apenas o valor da coluna Extended Events for NULL, isso indicará que qualquer um das seguintes condições é verdadeira:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-109">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="b4e1e-110">A coluna Rastreamento do SQL é mapeada para um dos campos de dados associados ao evento de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-110">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b4e1e-111">Cada evento dos Eventos Estendidos tem um conjunto padrão de campos de dados que são incluídos automaticamente no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-111">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="b4e1e-112">A coluna de ação não tem um equivalente significativo dos Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-112">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="b4e1e-113">Um exemplo disso é a coluna EventClass no Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-113">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="b4e1e-114">Essa coluna não é necessária nos Eventos Estendidos porque o nome do evento atende ao mesmo objetivo.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-114">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="b4e1e-115">Para as classes de evento do Rastreamento do SQL configuráveis pelo usuário (UserConfigurable:1 a UserConfigurable:9), os Eventos Estendidos usam um único evento para substituí-las.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-115">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="b4e1e-116">O evento é chamado user_event.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-116">The event is named user_event.</span></span> <span data-ttu-id="b4e1e-117">Este evento é gerado por meio de sp_trace_generateevent, o mesmo procedimento armazenado usado pelo Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-117">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="b4e1e-118">O evento user_event é retornado, independentemente de qual ID de evento é passada para o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-118">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="b4e1e-119">No entanto, um campo event_id é retornado como parte dos dados do evento.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-119">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="b4e1e-120">Isso permite a você criar um predicado baseado na ID do evento.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-120">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="b4e1e-121">Por exemplo, se você usar UserConfigurable:0 (ID de evento = 82) no código, poderá adicionar o evento user_event à sessão e especificar o predicado “event_id = 82”.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-121">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="b4e1e-122">Portanto, você não precisa alterar o código, pois o procedimento armazenado sp_trace_generateevent gera o evento user_event dos Eventos Estendidos, e a classe de evento equivalente do Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-122">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
-   <span data-ttu-id="b4e1e-123">Se todas as colunas retornarem NULL com exceção da coluna Event Class, isso indicará que a classe de evento não foi migrada do Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-123">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="b4e1e-124">Se apenas o valor da coluna Extended Events for NULL, isso indicará que qualquer um das seguintes condições é verdadeira:</span><span class="sxs-lookup"><span data-stu-id="b4e1e-124">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="b4e1e-125">A coluna Rastreamento do SQL é mapeada para um dos campos de dados associados ao evento de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-125">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b4e1e-126">Cada evento dos Eventos Estendidos tem um conjunto padrão de campos de dados que são incluídos automaticamente no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-126">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="b4e1e-127">A coluna de ação não tem um equivalente significativo dos Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-127">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="b4e1e-128">Um exemplo disso é a coluna EventClass no Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-128">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="b4e1e-129">Essa coluna não é necessária nos Eventos Estendidos porque o nome do evento atende ao mesmo objetivo.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-129">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="b4e1e-130">Para as classes de evento do Rastreamento do SQL configuráveis pelo usuário (UserConfigurable:1 a UserConfigurable:9), os Eventos Estendidos usam um único evento para substituí-las.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-130">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="b4e1e-131">O evento é chamado user_event.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-131">The event is named user_event.</span></span> <span data-ttu-id="b4e1e-132">Este evento é gerado por meio de sp_trace_generateevent, o mesmo procedimento armazenado usado pelo Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-132">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="b4e1e-133">O evento user_event é retornado, independentemente de qual ID de evento é passada para o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-133">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="b4e1e-134">No entanto, um campo event_id é retornado como parte dos dados do evento.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-134">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="b4e1e-135">Isso permite a você criar um predicado baseado na ID do evento.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-135">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="b4e1e-136">Por exemplo, se você usar UserConfigurable:0 (ID de evento = 82) no código, poderá adicionar o evento user_event à sessão e especificar o predicado “event_id = 82”.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-136">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="b4e1e-137">Portanto, você não precisa alterar o código, pois o procedimento armazenado sp_trace_generateevent gera o evento user_event dos Eventos Estendidos, e a classe de evento equivalente do Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="b4e1e-137">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e1e-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4e1e-138">See Also</span></span>  
 [<span data-ttu-id="b4e1e-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b4e1e-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)  
  
  
