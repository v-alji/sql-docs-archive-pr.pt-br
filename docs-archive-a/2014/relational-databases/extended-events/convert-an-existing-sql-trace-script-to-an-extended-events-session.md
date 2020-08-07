---
title: Converter um script de rastreamento do SQL existente em uma sessão de eventos estendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, convert script to extended events
- extended events [SQL Server], convert SQL Trace script
ms.assetid: 4c8f29e6-0a37-490f-88b3-33493871b3f9
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e5b0d0e20fbf4fd55398c130abf6cfff128ebe8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576406"
---
# <a name="convert-an-existing-sql-trace-script-to-an-extended-events-session"></a><span data-ttu-id="d38ef-102">Converter um script existente de Rastreamento do SQL em uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="d38ef-102">Convert an Existing SQL Trace Script to an Extended Events Session</span></span>
  <span data-ttu-id="d38ef-103">Se você tiver um script de Rastreamento do SQL que deseja converter em sessão de Eventos Estendidos, poderá usar os procedimentos deste tópico para criar uma sessão de Eventos Estendidos equivalente.</span><span class="sxs-lookup"><span data-stu-id="d38ef-103">If you have an existing SQL Trace script that you want to convert to an Extended Events session, you can use the procedures in this topic to create an equivalent Extended Events session.</span></span> <span data-ttu-id="d38ef-104">Usando as informações das tabelas de sistema trace_xe_action_map e trace_xe_event_map, você pode coletar as informações que precisa para fazer a conversão.</span><span class="sxs-lookup"><span data-stu-id="d38ef-104">By using the information in the trace_xe_action_map and trace_xe_event_map system tables, you can collect the information that you must have to do the conversion.</span></span>  
  
 <span data-ttu-id="d38ef-105">As etapas incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d38ef-105">The steps include the following:</span></span>  
  
1.  <span data-ttu-id="d38ef-106">Execute o script existente para criar uma sessão de Rastreamento do SQL obter a ID do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="d38ef-106">Execute the existing script to create a SQL Trace session, and then obtain the ID of the trace.</span></span>  
  
2.  <span data-ttu-id="d38ef-107">Execute uma consulta que usa a função fn_trace_geteventinfo para localizar os Eventos Estendidos e as ações e eventos para cada classe de evento Rastreamento do SQL e suas colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="d38ef-107">Run a query that uses the fn_trace_geteventinfo function to find the equivalent Extended Events events and actions for each SQL Trace event class and its associated columns.</span></span>  
  
3.  <span data-ttu-id="d38ef-108">Use a função fn_trace_getfilterinfo para listar os filtros e as ações equivalentes de Eventos Estendidos a serem usados.</span><span class="sxs-lookup"><span data-stu-id="d38ef-108">Use the fn_trace_getfilterinfo function to list the filters and the equivalent Extended Events actions to use.</span></span>  
  
4.  <span data-ttu-id="d38ef-109">Crie manualmente uma sessão de Eventos Estendidos, usando os eventos, as ações e os predicados (filtros) equivalentes de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="d38ef-109">Manually create an Extended Events session, using the equivalent Extended Events events, actions, and predicates (filters).</span></span>  
  
## <a name="to-obtain-the-trace-id"></a><span data-ttu-id="d38ef-110">Para obter a ID de rastreamento</span><span class="sxs-lookup"><span data-stu-id="d38ef-110">To obtain the trace ID</span></span>  
  
1.  <span data-ttu-id="d38ef-111">Abra o script de Rastreamento do SQL no Editor de Consultas e execute o script para criar a sessão de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="d38ef-111">Open the SQL Trace script in Query Editor, and then execute the script to create the trace session.</span></span> <span data-ttu-id="d38ef-112">Saiba que a sessão de rastreamento não precisa estar em execução para concluir este procedimento.</span><span class="sxs-lookup"><span data-stu-id="d38ef-112">Note that the trace session does not need to be running to complete this procedure.</span></span>  
  
2.  <span data-ttu-id="d38ef-113">Obtenha a ID do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="d38ef-113">Obtain the ID of the trace.</span></span> <span data-ttu-id="d38ef-114">Para fazer isso, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="d38ef-114">To do this, use the following query:</span></span>  
  
    ```sql
    SELECT * FROM sys.traces;  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="d38ef-115">ID de Rastreamento 1 geralmente indica o rastreamento padrão.</span><span class="sxs-lookup"><span data-stu-id="d38ef-115">Trace ID 1 typically indicates the default trace.</span></span>  
  
## <a name="to-determine-the-extended-events-equivalents"></a><span data-ttu-id="d38ef-116">Para determinar os equivalentes de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="d38ef-116">To determine the Extended Events equivalents</span></span>  
  
1.  <span data-ttu-id="d38ef-117">Para determinar os eventos e as ações equivalentes de Eventos Estendidos, execute a seguinte consulta, em que *trace_id* é definido como o valor da ID de rastreamento que você obteve no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="d38ef-117">To determine the equivalent Extended Events events and actions, run the following query, where *trace_id* is set to the value of the trace ID that you obtained in the previous procedure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d38ef-118">Nesse exemplo, a ID do rastreamento padrão (1) é usada.</span><span class="sxs-lookup"><span data-stu-id="d38ef-118">In this example, the trace ID for the default trace (1) is used.</span></span>  
  
    ```sql
    USE MASTER;  
    GO  
    DECLARE @trace_id int;  
    SET @trace_id = 1;  
    SELECT DISTINCT el.eventid, em.package_name, em.xe_event_name AS 'event'  
       , el.columnid, ec.xe_action_name AS 'action'  
    FROM (sys.fn_trace_geteventinfo(@trace_id) AS el  
       LEFT OUTER JOIN sys.trace_xe_event_map AS em  
          ON el.eventid = em.trace_event_id)  
    LEFT OUTER JOIN sys.trace_xe_action_map AS ec  
       ON el.columnid = ec.trace_column_id  
    WHERE em.xe_event_name IS NOT NULL AND ec.xe_action_name IS NOT NULL;  
    ```  
  
     <span data-ttu-id="d38ef-119">A ID de evento, o nome de pacote, o nome de evento, a ID de coluna e o nome de ação equivalentes dos Eventos Estendidos são retornados.</span><span class="sxs-lookup"><span data-stu-id="d38ef-119">The equivalent Extended Events event ID, package name, event name, column ID and action name are returned.</span></span> <span data-ttu-id="d38ef-120">Você usará essa saída no procedimento "Para criar a sessão de Eventos Estendidos" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d38ef-120">You will use this output in the procedure "To create the Extended Events session" later in this topic.</span></span>  
  
     <span data-ttu-id="d38ef-121">Em alguns casos, a coluna filtrada é mapeada para um campo de dados de evento incluído por padrão no evento de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="d38ef-121">In some cases, the filtered column maps to an event data field that is included by default in the Extended Events event.</span></span> <span data-ttu-id="d38ef-122">Portanto, a coluna "Extended_Events_action_name" será NULL.</span><span class="sxs-lookup"><span data-stu-id="d38ef-122">Therefore, the "Extended_Events_action_name" column will be NULL.</span></span> <span data-ttu-id="d38ef-123">Se isso acontecer, você deve fazer o seguinte para determinar qual campo de dados é equivalente à coluna filtrada:</span><span class="sxs-lookup"><span data-stu-id="d38ef-123">If this occurs, you must do the following to determine which data field is equivalent to the filtered column:</span></span>  
  
    1.  <span data-ttu-id="d38ef-124">Para as ações que retornam NULL, identifique quais classes de evento de Rastreamento do SQL no script contém a coluna que está sendo filtrada.</span><span class="sxs-lookup"><span data-stu-id="d38ef-124">For the actions that return NULL, identify which SQL Trace event classes in the script contain the column that is being filtered.</span></span>  
  
         <span data-ttu-id="d38ef-125">Por exemplo, você pode ter usado a classe de evento SP:StmtCompleted e especificado um filtro no nome de coluna de rastreamento Duração (ID 45 da classe de evento de Rastreamento do SQL e ID 13 da coluna de Rastreamento do SQL).</span><span class="sxs-lookup"><span data-stu-id="d38ef-125">For example, you may have used the SP:StmtCompleted event class, and specified a filter on the Duration trace column name (SQL Trace event class ID 45, and SQL Trace column ID 13).</span></span> <span data-ttu-id="d38ef-126">Nesse caso, o nome de ação aparecerá como NULL nos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="d38ef-126">In this case, the action name will appear as NULL in the query results.</span></span>  
  
    2.  <span data-ttu-id="d38ef-127">Para cada classe de evento de Rastreamento do SQL identificada na etapa anterior, localize o nome de evento equivalente de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="d38ef-127">For each SQL Trace event class that you identified in the previous step, find the equivalent Extended Events event name.</span></span> <span data-ttu-id="d38ef-128">(Se você não tiver certeza do nome do evento equivalente, use a consulta no tópico [Exibir os Eventos Estendidos equivalentes às classes de evento de Rastreamento do SQL](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span><span class="sxs-lookup"><span data-stu-id="d38ef-128">(If you are not sure of the equivalent event name, use the query in the topic [View the Extended Events Equivalents to SQL Trace Event Classes](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span></span>  
  
    3.  <span data-ttu-id="d38ef-129">Use a seguinte consulta a fim de identificar os campos de dados corretos para os eventos que você identificado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="d38ef-129">Use the following query to identify the correct data fields to use for the events that you identified in the previous step.</span></span> <span data-ttu-id="d38ef-130">A consulta mostra os campos de dados de Eventos Estendidos na coluna "event_field".</span><span class="sxs-lookup"><span data-stu-id="d38ef-130">The query shows the Extended Events data fields in the "event_field" column.</span></span> <span data-ttu-id="d38ef-131">Na consulta, substitua *<event_name>* pelo nome de um evento que você especificou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="d38ef-131">In the query, replace *<event_name>* with the name of an event that you specified in the previous step.</span></span>  
  
        ```sql
        SELECT xp.name package_name, xe.name event_name  
           ,xc.name event_field, xc.description  
        FROM sys.trace_xe_event_map AS em  
        INNER JOIN sys.dm_xe_objects AS xe  
           ON em.xe_event_name = xe.name  
        INNER JOIN sys.dm_xe_packages AS xp  
           ON xe.package_guid = xp.guid AND em.package_name = xp.name  
        INNER JOIN sys.dm_xe_object_columns AS xc  
           ON xe.name = xc.object_name  
        WHERE xe.object_type = 'event' AND xc.column_type <> 'readonly'  
           AND em.xe_event_name = '<event_name>';  
        ```  
  
         <span data-ttu-id="d38ef-132">Por exemplo, a classe de evento SP: StmtCompleted é mapeada para o evento sp_statement_completed do Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="d38ef-132">For example, the SP:StmtCompleted event class maps to the sp_statement_completed Extended Events event.</span></span> <span data-ttu-id="d38ef-133">Se você especificar sp_statement_completed como nome de evento da consulta, a coluna "event_field" mostrará os campos que são incluídos por padrão no evento.</span><span class="sxs-lookup"><span data-stu-id="d38ef-133">If you specify sp_statement_completed as the event name in the query, the "event_field" column shows the fields that are included by default with the event.</span></span> <span data-ttu-id="d38ef-134">Observando os campos, você constatará que há um campo "duração".</span><span class="sxs-lookup"><span data-stu-id="d38ef-134">Looking at the fields, you can see that there is a "duration" field.</span></span> <span data-ttu-id="d38ef-135">Para criar o filtro na sessão equivalente de Eventos Estendidos, você adicionará um predicado como "WHERE duration > 0".</span><span class="sxs-lookup"><span data-stu-id="d38ef-135">To create the filter in the equivalent Extended Events session, you would add a predicate such as "WHERE duration > 0".</span></span> <span data-ttu-id="d38ef-136">Para obter um exemplo, consulte o procedimento "Para criar a sessão de Eventos Estendidos" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d38ef-136">For an example, see the "To create the Extended Events session" procedure in this topic.</span></span>  
  
## <a name="to-create-the-extended-events-session"></a><span data-ttu-id="d38ef-137">Para criar a sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="d38ef-137">To create the Extended Events session</span></span>  
 <span data-ttu-id="d38ef-138">Use o Editor de Consultas para criar a sessão de Eventos Estendidos e gravar a saída em um destino de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d38ef-138">Use Query Editor to create the Extended Events session, and to write the output to a file target.</span></span> <span data-ttu-id="d38ef-139">As etapas a seguir descrevem uma única consulta, com explicações para mostrar como criar a consulta.</span><span class="sxs-lookup"><span data-stu-id="d38ef-139">The following steps describe a single query, with explanations to show you how to build the query.</span></span> <span data-ttu-id="d38ef-140">Para obter o exemplo de consulta completo, consulte a seção "Exemplo" deste tópico.</span><span class="sxs-lookup"><span data-stu-id="d38ef-140">For the full query example, see the "Example" section of this topic.</span></span>  
  
1.  <span data-ttu-id="d38ef-141">Adicione instruções para criar a sessão de evento, substituindo*session_name* pelo nome que você deseja usar para a sessão de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="d38ef-141">Add statements to create the event session, replacing s*ession_name* with the name that you want to use for the Extended Events session.</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [Session_Name] ON SERVER;  
    CREATE EVENT SESSION [Session_Name]  
    ON SERVER;  
    ```  
  
2.  <span data-ttu-id="d38ef-142">Adicione os eventos e as ações de Eventos Estendidos que foram retornados como saída no procedimento "Determinar os equivalentes de Eventos Estendidos" e adicione os predicados (filtros) que você identificou no procedimento "Para determinar os filtros usados no script".</span><span class="sxs-lookup"><span data-stu-id="d38ef-142">Add the Extended Events events and actions that were returned as output in the procedure "Determine the Extended Events equivalents", and add the predicates (filters) that you identified in the procedure "To determine the filters that were used in the script".</span></span>  
  
     <span data-ttu-id="d38ef-143">O exemplo a seguir usa um script de Rastreamento do SQL que inclui as classes de evento SQL:StmtStarting e SP:StmtCompleted, com filtros para ID e duração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d38ef-143">The following example uses a SQL Trace script that includes the SQL:StmtStarting and SP:StmtCompleted event classes, with filters for session ID and duration.</span></span> <span data-ttu-id="d38ef-144">A saída de exemplo da consulta no procedimento "Determinar os equivalentes de Eventos Estendidos" retornou este conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="d38ef-144">Sample output for the query in the "Determine the Extended Events equivalents" procedure returned the following result set:</span></span>  
  
    ```  
    Eventid  package_name  event                   columnid  action  
    44       sqlserver     sp_statement_starting   6         nt_username  
    44       sqlserver     sp_statement_starting   9         client_pid  
    44       sqlserver     sp_statement_starting   10        client_app_name  
    44       sqlserver     sp_statement_starting   11        server_principal_name  
    44       sqlserver     sp_statement_starting   12        session_id  
    45       sqlserver     sp_statement_completed  6         nt_username  
    45       sqlserver     sp_statement_completed  9         client_pid  
    45       sqlserver     sp_statement_completed  10        client_app_name  
    45       sqlserver     sp_statement_completed  11        server_principal_name  
    45       sqlserver     sp_statement_completed  12        session_id  
    ```  
  
     <span data-ttu-id="d38ef-145">Para converter isso no equivalente de Eventos Estendidos, são adicionados os eventos sqlserver.sp_statement_starting e sqlserver.sp_statement_completed com uma lista de ações.</span><span class="sxs-lookup"><span data-stu-id="d38ef-145">To convert this to the Extended Events equivalent, the sqlserver.sp_statement_starting and the sqlserver.sp_statement_completed events are added, with a list of actions.</span></span> <span data-ttu-id="d38ef-146">As instruções de predicado são incluídas como cláusulas WHERE.</span><span class="sxs-lookup"><span data-stu-id="d38ef-146">Predicate statements are included as WHERE clauses.</span></span>  
  
    ```sql
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       )  
    ```  
  
3.  <span data-ttu-id="d38ef-147">Adicione o destino de arquivo assíncrono, substituindo os caminhos de arquivo com a localização em que você deseja salvar a saída.</span><span class="sxs-lookup"><span data-stu-id="d38ef-147">Add the asynchronous file target, replacing the file paths with the location where you want to save the output.</span></span> <span data-ttu-id="d38ef-148">Ao especificar o destino de arquivo, você deve incluir um arquivo de log e um arquivo de caminho de arquivo de metadados.</span><span class="sxs-lookup"><span data-stu-id="d38ef-148">When specifying the file target, you must include a log file and metadata file path file.</span></span>  
  
    ```sql
    ADD TARGET package0.asynchronous_file_target(  
       SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="to-view-the-results"></a><span data-ttu-id="d38ef-149">Para exibir os resultados</span><span class="sxs-lookup"><span data-stu-id="d38ef-149">To view the results</span></span>  
  
1.  <span data-ttu-id="d38ef-150">Você pode usar a função sys.fn_xe_file_target_read_file para exibir a saída.</span><span class="sxs-lookup"><span data-stu-id="d38ef-150">You can use the sys.fn_xe_file_target_read_file function to view the output.</span></span> <span data-ttu-id="d38ef-151">Para fazer isso, execute a seguinte consulta, substituindo os caminhos de arquivo pelos caminhos que você especificou:</span><span class="sxs-lookup"><span data-stu-id="d38ef-151">To do this, run the following query, replacing the file paths with the paths that you specified:</span></span>  
  
    ```sql
    SELECT *, CAST(event_data as XML) AS 'event_data_XML'  
    FROM sys.fn_xe_file_target_read_file('c:\temp\ExtendedEventsStoredProcs*.xel', 'c:\temp\ExtendedEventsStoredProcs*.xem', NULL, NULL);  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="d38ef-152">A conversão dos dados de evento como XML é opcional.</span><span class="sxs-lookup"><span data-stu-id="d38ef-152">Casting the event data as XML is optional.</span></span>  
  
     <span data-ttu-id="d38ef-153">Para obter mais informações sobre a função sys.fn_xe_file_target_read_file, consulte [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d38ef-153">For more information about the sys.fn_xe_file_target_read_file function, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [session_name] ON SERVER;  
    CREATE EVENT SESSION [session_name]  
    ON SERVER  
  
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       );  
  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="example"></a><span data-ttu-id="d38ef-154">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d38ef-154">Example</span></span>  
  
```sql
IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
   DROP EVENT SESSION [session_name] ON SERVER;  
CREATE EVENT SESSION [session_name]  
ON SERVER  
  
ADD EVENT sqlserver.sp_statement_starting  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59   
   ),  
  
ADD EVENT sqlserver.sp_statement_completed  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59 AND duration > 0  
   )  
  
ADD TARGET package0.asynchronous_file_target  
   (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
```  
  
## <a name="see-also"></a><span data-ttu-id="d38ef-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d38ef-155">See Also</span></span>  
 [<span data-ttu-id="d38ef-156">Exibir os Eventos Estendidos equivalentes às classes de rastreamento de eventos do SQL</span><span class="sxs-lookup"><span data-stu-id="d38ef-156">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>](view-the-extended-events-equivalents-to-sql-trace-event-classes.md)  
  
  
