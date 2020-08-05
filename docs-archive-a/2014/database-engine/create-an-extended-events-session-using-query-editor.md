---
title: Criar uma sessão de eventos estendidos usando o editor de consultas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- create extended events session
- extended events [SQL Server], create session
ms.assetid: cba0e02b-b201-4863-bf1b-9164e68e5fa8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 648370ecdd2938b6fb425955dc02da8960f884c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574263"
---
# <a name="create-an-extended-events-session-using-query-editor"></a><span data-ttu-id="5349c-102">Criar uma sessão de Eventos Estendidos usando o Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="5349c-102">Create an Extended Events Session Using Query Editor</span></span>
  <span data-ttu-id="5349c-103">Você pode criar uma sessão de Eventos Estendidos usando o Editor de Consulta ou pode criar uma sessão no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="5349c-103">You can create an Extended Events session by using the Query Editor, or you can create a session in Object Explorer.</span></span> <span data-ttu-id="5349c-104">No Pesquisador de objetos, os eventos estendidos fornecem duas interfaces de usuário que você pode usar para criar, modificar e exibir dados de sessão de evento-um assistente que orienta você pelo processo de criação de sessão de evento e uma nova interface de usuário de sessão que fornece opções de configuração mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="5349c-104">In Object Explorer, Extended Events provides two user interfaces you can use to create, modify, and view event session data - a wizard that guides you through the event session creation process, and a New Session UI that provides more advanced configuration options.</span></span> <span data-ttu-id="5349c-105">Você pode criar sessões de Eventos Estendidos para diagnosticar rastreamento de SQL Server que permite resolver problemas como os seguintes:</span><span class="sxs-lookup"><span data-stu-id="5349c-105">You can create Extended Events sessions to diagnose SQL Server tracing, which enables you to resolve issues such as the following:</span></span>  
  
-   <span data-ttu-id="5349c-106">Localizar suas consultas mais caras</span><span class="sxs-lookup"><span data-stu-id="5349c-106">Find your most expensive queries</span></span>  
  
-   <span data-ttu-id="5349c-107">Localizar causas raiz de contenção de trava</span><span class="sxs-lookup"><span data-stu-id="5349c-107">Find root causes of latch contention</span></span>  
  
-   <span data-ttu-id="5349c-108">Localizar uma consulta que está bloqueando outras consultas</span><span class="sxs-lookup"><span data-stu-id="5349c-108">Find a query that is blocking other queries</span></span>  
  
-   <span data-ttu-id="5349c-109">Solucionar problemas de uso excessivo de CPU causados por recompilação de consulta</span><span class="sxs-lookup"><span data-stu-id="5349c-109">Troubleshoot excessive CPU usage caused by query recompilation</span></span>  
  
-   <span data-ttu-id="5349c-110">Solucionando problemas de deadlocks</span><span class="sxs-lookup"><span data-stu-id="5349c-110">Troubleshoot deadlocks</span></span>  
  
 <span data-ttu-id="5349c-111">Para obter informações sobre como criar uma sessão dos Eventos Estendidos usando o Assistente de Nova Sessão, veja [Criar uma sessão de Eventos Estendidos usando o assistente &#40;Pesquisador de Objetos&#41;](../ssms/object/object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="5349c-111">For information about how to create an Extended Events session using the New Session Wizard, see [Create an Extended Events Session Using the Wizard &#40;Object Explorer&#41;](../ssms/object/object-explorer.md).</span></span> <span data-ttu-id="5349c-112">Para obter informações sobre como criar uma sessão dos Eventos Estendidos usando a interface do usuário de Nova Sessão, veja [Criar uma sessão de Eventos Estendidos usando a caixa de diálogo Nova Sessão](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span><span class="sxs-lookup"><span data-stu-id="5349c-112">For information about how to create an Extended Events session using the New Session UI, see [Create an Extended Events Session Using the New Session Dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5349c-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="5349c-113">Permissions</span></span>  
 <span data-ttu-id="5349c-114">Para criar uma sessão de Eventos Estendidos, você deve ter a permissão ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="5349c-114">To create an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="creating-an-extended-events-session-using-query-editor"></a><span data-ttu-id="5349c-115">Criando uma sessão de Eventos Estendidos usando o Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="5349c-115">Creating an Extended Events session using Query Editor</span></span>  
  
#### <a name="to-create-an-extended-events-session"></a><span data-ttu-id="5349c-116">Para criar uma sessão de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="5349c-116">To create an Extended Events session</span></span>  
  
1.  <span data-ttu-id="5349c-117">O procedimento a seguir descreve como criar uma sessão de Eventos Estendidos usando o Editor de Consultas no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5349c-117">The following procedure shows how to create an Extended Events session by using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="5349c-118">Determine quais eventos você deseja usar na sessão.</span><span class="sxs-lookup"><span data-stu-id="5349c-118">Determine which events that you want to use in the session.</span></span> <span data-ttu-id="5349c-119">Para consultar todos os eventos disponíveis, junto com a palavra-chave e o canal, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="5349c-119">To see all the events that are available, together with the keyword and channel, use the following query:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5349c-120">Para obter informações sobre palavras-chave e canais, veja [Pacotes de Eventos Estendidos do SQL Server](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="5349c-120">For information about keywords and channels, see [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span></span>  
  
    ```  
    SELECT p.name, c.event, k.keyword, c.channel, c.description FROM  
       (  
       SELECT event_package = o.package_guid, o.description,   
       event=c.object_name, channel = v.map_value  
       FROM sys.dm_xe_objects o  
       LEFT JOIN sys.dm_xe_object_columns c ON o.name = c.object_name  
       INNER JOIN sys.dm_xe_map_values v ON c.type_name = v.name   
       AND c.column_value = cast(v.map_key AS nvarchar)  
       WHERE object_type = 'event' AND (c.name = 'CHANNEL' or c.name IS NULL)  
       ) c LEFT JOIN   
       (  
       SELECT event_package = c.object_package_guid, event = c.object_name,   
       keyword = v.map_value  
       FROM sys.dm_xe_object_columns c INNER JOIN sys.dm_xe_map_values v   
       ON c.type_name = v.name AND c.column_value = v.map_key   
       AND c.type_package_guid = v.object_package_guid  
       INNER JOIN sys.dm_xe_objects o ON o.name = c.object_name   
       AND o.package_guid = c.object_package_guid  
       WHERE object_type = 'event' AND c.name = 'KEYWORD'   
       ) k  
       ON  
       k.event_package = c.event_package AND (k.event=c.event or k.event IS NULL)  
       INNER JOIN sys.dm_xe_packages p ON p.guid = c.event_package  
    ORDER BY keyword desc, channel, event  
    ```  
  
2.  <span data-ttu-id="5349c-121">Em uma nova janela de consulta, adicione as seguintes instruções para criar uma sessão de evento, substituindo *session_name* pelo nome de sessão que você deseja usar:</span><span class="sxs-lookup"><span data-stu-id="5349c-121">In a new query window, add the following statements to create an event session, replacing *session_name* with the session name that you want to use:</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5349c-122">As etapas de 2 a 6 deste procedimento descrevem cada seção da definição de sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="5349c-122">Steps 2 through 6 of this procedure describe each section of the event session definition.</span></span> <span data-ttu-id="5349c-123">Você adicionaria todas as instruções a uma única janela de consulta antes da execução.</span><span class="sxs-lookup"><span data-stu-id="5349c-123">You would add all the statements to a single query window before executing.</span></span> <span data-ttu-id="5349c-124">Para obter um exemplo completo, consulte a seção Exemplo deste tópico.</span><span class="sxs-lookup"><span data-stu-id="5349c-124">For a full example, see the Example section of this topic.</span></span>  
  
    ```  
    CREATE EVENT SESSION session_name   
    ON SERVER  
    ```  
  
3.  <span data-ttu-id="5349c-125">Adicione os eventos que você deseja monitorar, no formato *package_name*.*event_name*.</span><span class="sxs-lookup"><span data-stu-id="5349c-125">Add the events that you want to monitor, in the format *package_name*.*event_name*.</span></span> <span data-ttu-id="5349c-126">Para cada evento, adicione uma linha semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="5349c-126">For each event, add a line similar to the following:</span></span>  
  
    ```  
    ADD EVENT package_name.event_name  
    ```  
  
     <span data-ttu-id="5349c-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5349c-127">For example:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed,  
    ADD EVENT sqlserver.file_write_completed  
    ```  
  
4.  <span data-ttu-id="5349c-128">(Opcional) Depois que você adicionar um evento, poderá adicionar as ações a serem executadas.</span><span class="sxs-lookup"><span data-stu-id="5349c-128">(Optional) After you add an event, you can add actions to take.</span></span> <span data-ttu-id="5349c-129">Você também pode adicionar predicados.</span><span class="sxs-lookup"><span data-stu-id="5349c-129">You can also add predicates.</span></span> <span data-ttu-id="5349c-130">Os predicados são usados para estabelecer critérios para o momento em que as informações de evento devem ser utilizadas pelo destino.</span><span class="sxs-lookup"><span data-stu-id="5349c-130">Predicates are used to establish criteria for when the event information should be consumed by the target.</span></span> <span data-ttu-id="5349c-131">As ações são adicionadas usando uma cláusula ACTION e os predicados são adicionados usando uma cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="5349c-131">Actions are added by using an ACTION clause, and predicates are added by using a WHERE clause.</span></span> <span data-ttu-id="5349c-132">Por exemplo, para adicionar uma ação e um predicado em que o texto [!INCLUDE[tsql](../includes/tsql-md.md)] é capturado para o evento sqlserver.file_read_completed, em que a ID de arquivo é igual a 1, você incluiria a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="5349c-132">For example, to add an action and predicate where the [!INCLUDE[tsql](../includes/tsql-md.md)] text is captured for the sqlserver.file_read_completed event, where the file ID equals 1, you would include the following statement:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed  
       (ACTION (sqlserver.sql_text)  
       WHERE file_id = 1),  
    ```  
  
    -   <span data-ttu-id="5349c-133">Para exibir quais ações estão disponíveis, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="5349c-133">To view which actions are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS 'package_name', xo.name AS 'action_name', xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'action'  
        AND (xo.capabilities & 1 = 0   
        OR xo.capabilities IS NULL)  
        ORDER BY p.name, xo.name  
        ```  
  
    -   <span data-ttu-id="5349c-134">Para exibir quais predicados estão disponíveis para um evento, use a seguinte consulta, substituindo *event_name* pelo nome do evento para o qual você deseja adicionar um predicado:</span><span class="sxs-lookup"><span data-stu-id="5349c-134">To view which predicates are available for an event, use the following query, replacing *event_name* with the name of the event for which you want to add a predicate:</span></span>  
  
        ```  
        SELECT *  
        FROM sys.dm_xe_object_columns  
        WHERE object_name = 'event_name'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="5349c-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5349c-135">For example:</span></span>  
  
        ```  
        SELECT *   
        FROM sys.dm_xe_object_columns   
        WHERE object_name = 'file_read_completed'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="5349c-136">Esteja atento que você também pode adicionar origens de predicado globais.</span><span class="sxs-lookup"><span data-stu-id="5349c-136">Be aware that you can also add global predicate sources.</span></span> <span data-ttu-id="5349c-137">Uma origem de predicado global pode ser usada em qualquer expressão de predicado.</span><span class="sxs-lookup"><span data-stu-id="5349c-137">A global predicate source can be used in any predicate expression.</span></span> <span data-ttu-id="5349c-138">Para exibir quais origens de predicado globais estão disponíveis, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="5349c-138">To view which global predicate sources are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS package_name, xo.name AS predicate_name  
           , xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'pred_source'  
        ORDER BY p.name, xo.name  
        ```  
  
         <span data-ttu-id="5349c-139">Por exemplo, você poderia usar a seguinte expressão de predicado para especificar que os dados sejam coletados para um evento somente nas cinco primeiras vezes que um evento ocorrer.</span><span class="sxs-lookup"><span data-stu-id="5349c-139">For example, you could use the following predicate expression to specify that data should only be collected for an event the first five times that an event occurs.</span></span>  
  
        ```  
        WHERE package0.counter <= 5  
        ```  
  
5.  <span data-ttu-id="5349c-140">Adicione o destino desejado, onde os dados de evento serão processados e utilizados.</span><span class="sxs-lookup"><span data-stu-id="5349c-140">Add the desired target, where the event data will be processed and consumed.</span></span> <span data-ttu-id="5349c-141">Use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="5349c-141">Use the following format:</span></span>  
  
    ```  
    ADD TARGET package_name.target_name  
    ```  
  
     <span data-ttu-id="5349c-142">O exemplo a seguir adiciona o destino de arquivo assíncrono:</span><span class="sxs-lookup"><span data-stu-id="5349c-142">The following example adds the asynchronous file target:</span></span>  
  
    ```  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
    ```  
  
     <span data-ttu-id="5349c-143">Para exibir a lista de destinos disponíveis, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="5349c-143">To view the list of available targets, use the following query:</span></span>  
  
    ```  
    SELECT p.name AS 'package_name', xo.name AS 'target_name'  
       , xo.description, xo.object_type   
    FROM sys.dm_xe_objects AS xo  
    JOIN sys.dm_xe_packages AS p  
       ON xo.package_guid = p.guid  
    WHERE xo.object_type = 'target'  
    AND (xo.capabilities & 1 = 0  
    OR xo.capabilities IS NULL)  
    ORDER BY p.name, xo.name  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="5349c-144">Para obter informações sobre os diferentes tipos de destino, veja [Destinos de Eventos Estendidos do SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="5349c-144">For information about the different target types, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
6.  <span data-ttu-id="5349c-145">Revise e adicione qualquer opção de configuração adicional.</span><span class="sxs-lookup"><span data-stu-id="5349c-145">Review and add any additional configuration options.</span></span> <span data-ttu-id="5349c-146">Por exemplo, você pode configurar opções como modo de retenção de evento, quanto tempo os eventos permanecerão armazenados em buffer na memória ou se a sessão de evento deverá iniciar automaticamente quando o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] for iniciado.</span><span class="sxs-lookup"><span data-stu-id="5349c-146">For example, you can configure options such as the event retention mode, how long events are buffered in memory, or whether the event session should start automatically when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="5349c-147">As opções são descritas no tópico [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5349c-147">The options are described in the topic [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span></span> <span data-ttu-id="5349c-148">Saiba que os valores padrão serão atribuídos se essas opções não forem especificadas.</span><span class="sxs-lookup"><span data-stu-id="5349c-148">Be aware that default values are assigned if these options are not specified.</span></span>  
  
7.  <span data-ttu-id="5349c-149">Inicie a sessão.</span><span class="sxs-lookup"><span data-stu-id="5349c-149">Start the session.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5349c-150">Para obter mais informações sobre como exibir os resultados da sessão, veja o tópico correspondente do tipo de destino usado no nó [Destinos de eventos estendidos do SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) dos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="5349c-150">For more information about how to view the session results, see the corresponding topic for the target type that you used in the [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) node of Books Online.</span></span>  
  
 <span data-ttu-id="5349c-151">O exemplo a seguir cria uma sessão de Eventos Estendidos chamada IOActivity que captura as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="5349c-151">The following example creates an Extended Events session named IOActivity that captures the following information:</span></span>  
  
-   <span data-ttu-id="5349c-152">Dados de evento para leituras de arquivo concluídas, incluindo o texto associado do [!INCLUDE[tsql](../includes/tsql-md.md)] para leituras de arquivo onde a ID de arquivo é igual a 1.</span><span class="sxs-lookup"><span data-stu-id="5349c-152">Event data for completed file reads, including the associated [!INCLUDE[tsql](../includes/tsql-md.md)] text for file reads where the file ID is equal to 1.</span></span>  
  
-   <span data-ttu-id="5349c-153">Dados de evento para gravações de arquivo concluídas.</span><span class="sxs-lookup"><span data-stu-id="5349c-153">Event data for completed file writes.</span></span>  
  
-   <span data-ttu-id="5349c-154">Dados de evento sobre o momento em que os dados são gravados no cache de log para o arquivo de log físico.</span><span class="sxs-lookup"><span data-stu-id="5349c-154">Event data for when data is written from the log cache to the physical log file.</span></span>  
  
 <span data-ttu-id="5349c-155">A sessão envia a saída para um destino de arquivo.</span><span class="sxs-lookup"><span data-stu-id="5349c-155">The session sends the output to a file target.</span></span>  
  
```  
CREATE EVENT SESSION IOActivity  
ON SERVER  
  
ADD EVENT sqlserver.file_read_completed  
   (  
   ACTION (sqlserver.sql_text)  
   WHERE file_id = 1),  
ADD EVENT sqlserver.file_write_completed,  
ADD EVENT sqlserver.databases_log_flush  
  
ADD TARGET package0.asynchronous_file_target   
   (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
```  
  
## <a name="see-also"></a><span data-ttu-id="5349c-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5349c-156">See Also</span></span>  
 <span data-ttu-id="5349c-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5349c-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="5349c-158">[Destinos de eventos estendidos do SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="5349c-158">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 [<span data-ttu-id="5349c-159">Pacotes de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5349c-159">SQL Server Extended Events Packages</span></span>](../relational-databases/extended-events/sql-server-extended-events-packages.md)  
  
  
