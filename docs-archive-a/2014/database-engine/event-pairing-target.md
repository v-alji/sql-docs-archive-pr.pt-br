---
title: Destino de emparelhamento de evento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- pairing target [SQL Server extended events]
- event pairing target
- targets [SQL Server extended events], pairing target
ms.assetid: 3c87dcfb-543a-4bd8-a73d-1390bdf4ffa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a1a6beb1c6996e6e12f16c4555fd9dfcab97617d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681087"
---
# <a name="event-pairing-target"></a><span data-ttu-id="98fac-102">Destino de emparelhamento de evento</span><span class="sxs-lookup"><span data-stu-id="98fac-102">Event Pairing Target</span></span>
  <span data-ttu-id="98fac-103">O destino de emparelhamento de eventos efetua a correspondência entre dois eventos por meio de uma ou mais colunas de dados presentes em cada evento.</span><span class="sxs-lookup"><span data-stu-id="98fac-103">The event pairing target matches two events using one or more columns of data that are present in each event.</span></span> <span data-ttu-id="98fac-104">Muitos eventos vêm em pares, por exemplo, aquisições de bloqueio e liberações de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="98fac-104">Many events come in pairs, for example, lock acquires and lock releases.</span></span> <span data-ttu-id="98fac-105">Após o emparelhamento de uma sequência de eventos, ambos são descartados.</span><span class="sxs-lookup"><span data-stu-id="98fac-105">After an event sequence is paired, both events are discarded.</span></span> <span data-ttu-id="98fac-106">O descarte de conjuntos correspondidos facilita a detecção de aquisições de bloqueios que não foram liberados.</span><span class="sxs-lookup"><span data-stu-id="98fac-106">Discarding matched sets allows for easy detection of lock acquisitions that have not been released.</span></span>  
  
 <span data-ttu-id="98fac-107">Com o uso de filtros no nível de evento, o destino de emparelhamento pode ser usado somente para capturar eventos que não correspondam aos critérios predefinidos.</span><span class="sxs-lookup"><span data-stu-id="98fac-107">By using event-level filters, the pairing target can be used to only capture events that do not match pre-set criteria.</span></span>  
  
 <span data-ttu-id="98fac-108">Ao usar o destino de emparelhamento de evento, você pode escolher dois eventos que serão correspondidos, junto com uma sequência de colunas para executar a correspondência.</span><span class="sxs-lookup"><span data-stu-id="98fac-108">When you use the event pairing target, you can choose two events that will be matched, together with a sequence of columns to perform the matching on.</span></span> <span data-ttu-id="98fac-109">Todas as colunas nessa sequência deverão ser do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="98fac-109">All the columns in this sequence must be of the same type.</span></span>  
  
 <span data-ttu-id="98fac-110">A tabela a seguir descreve as opções disponíveis para configurar um emparelhamento de evento.</span><span class="sxs-lookup"><span data-stu-id="98fac-110">The following table describes the available options for configuring event pairing.</span></span>  
  
|<span data-ttu-id="98fac-111">Opção</span><span class="sxs-lookup"><span data-stu-id="98fac-111">Option</span></span>|<span data-ttu-id="98fac-112">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="98fac-112">Allowed values</span></span>|<span data-ttu-id="98fac-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="98fac-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="98fac-114">begin_event</span><span class="sxs-lookup"><span data-stu-id="98fac-114">begin_event</span></span>|<span data-ttu-id="98fac-115">Qualquer nome de evento presente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="98fac-115">Any event name that is present in the current session.</span></span>|<span data-ttu-id="98fac-116">O nome do evento que especifica o evento inicial em uma sequência emparelhada.</span><span class="sxs-lookup"><span data-stu-id="98fac-116">The event name specifying the beginning event in a paired sequence.</span></span>|  
|<span data-ttu-id="98fac-117">end_event</span><span class="sxs-lookup"><span data-stu-id="98fac-117">end_event</span></span>|<span data-ttu-id="98fac-118">Qualquer nome de evento presente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="98fac-118">Any event name that is present in the current session.</span></span>|<span data-ttu-id="98fac-119">O nome do evento que especifica o evento final em uma sequência emparelhada.</span><span class="sxs-lookup"><span data-stu-id="98fac-119">The event name specifying the ending event in a paired sequence.</span></span>|  
|<span data-ttu-id="98fac-120">begin_matching_columns</span><span class="sxs-lookup"><span data-stu-id="98fac-120">begin_matching_columns</span></span>|<span data-ttu-id="98fac-121">Uma lista delimitada por vírgula, ordenada por nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="98fac-121">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="98fac-122">As colunas em que a correspondência deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="98fac-122">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="98fac-123">end_matching_columns</span><span class="sxs-lookup"><span data-stu-id="98fac-123">end_matching_columns</span></span>|<span data-ttu-id="98fac-124">Uma lista delimitada por vírgula, ordenada por nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="98fac-124">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="98fac-125">As colunas em que a correspondência deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="98fac-125">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="98fac-126">begin_matching_actions</span><span class="sxs-lookup"><span data-stu-id="98fac-126">begin_matching_actions</span></span>|<span data-ttu-id="98fac-127">Uma lista de ações ordenadas, delimitadas por vírgula.</span><span class="sxs-lookup"><span data-stu-id="98fac-127">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="98fac-128">As ações nas quais a correspondência deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="98fac-128">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="98fac-129">end_matching_actions</span><span class="sxs-lookup"><span data-stu-id="98fac-129">end_matching_actions</span></span>|<span data-ttu-id="98fac-130">Uma lista de ações ordenadas, delimitadas por vírgula.</span><span class="sxs-lookup"><span data-stu-id="98fac-130">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="98fac-131">As ações nas quais a correspondência deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="98fac-131">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="98fac-132">respond_to_memory_pressure</span><span class="sxs-lookup"><span data-stu-id="98fac-132">respond_to_memory_pressure</span></span>|<span data-ttu-id="98fac-133">Um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="98fac-133">One of the following values:</span></span><br /><br /> <span data-ttu-id="98fac-134">0 = Não responda.</span><span class="sxs-lookup"><span data-stu-id="98fac-134">0 = Do not respond.</span></span><br /><br /> <span data-ttu-id="98fac-135">1 = Pare de adicionar novos órfãos à lista quando houver pressão de memória.</span><span class="sxs-lookup"><span data-stu-id="98fac-135">1 = Stop adding new orphans to the list when there is memory pressure.</span></span>|<span data-ttu-id="98fac-136">A resposta de destino a eventos de memória.</span><span class="sxs-lookup"><span data-stu-id="98fac-136">The target response to memory events.</span></span> <span data-ttu-id="98fac-137">Se definido como 1 e o servidor estiver com pouca memória, as informações não emparelhadas que estão sendo mantidas serão removidas.</span><span class="sxs-lookup"><span data-stu-id="98fac-137">If set to 1 and the server is low on memory, unpaired information that is being maintained is removed.</span></span>|  
|<span data-ttu-id="98fac-138">max_orphans</span><span class="sxs-lookup"><span data-stu-id="98fac-138">max_orphans</span></span>||<span data-ttu-id="98fac-139">Especifica o número total de eventos ímpares que serão coletados no destino.</span><span class="sxs-lookup"><span data-stu-id="98fac-139">Specifies the total number of unpaired events that will be collected in the target.</span></span> <span data-ttu-id="98fac-140">Quando o limite é atingido, os eventos não emparelhados são removidos na base PEPS (primeiro a entrar, primeiro a sair).</span><span class="sxs-lookup"><span data-stu-id="98fac-140">Once the limit is reached, unpaired events are removed on a first-in, first-out (FIFO) basis.</span></span> <span data-ttu-id="98fac-141">Padrão = 10,000.</span><span class="sxs-lookup"><span data-stu-id="98fac-141">Default = 10,000.</span></span>|  
  
 <span data-ttu-id="98fac-142">Todos os dados associados a um evento são capturados e armazenados para emparelhamento futuro.</span><span class="sxs-lookup"><span data-stu-id="98fac-142">All the data associated with an event is captured and stored for future pairing.</span></span> <span data-ttu-id="98fac-143">Além disso, dados adicionados por ações também são coletados.</span><span class="sxs-lookup"><span data-stu-id="98fac-143">In addition, data added by actions is also collected.</span></span> <span data-ttu-id="98fac-144">Os dados de evento coletados são armazenados na memória e, portanto, têm um limite finito.</span><span class="sxs-lookup"><span data-stu-id="98fac-144">The collected event data is stored in memory, and therefore has a finite limit.</span></span> <span data-ttu-id="98fac-145">Esse limite é baseado na capacidade e na atividade do sistema.</span><span class="sxs-lookup"><span data-stu-id="98fac-145">This limit is based on system capacity and activity.</span></span> <span data-ttu-id="98fac-146">Em vez de usar a quantidade máxima de memória a ser usada como um parâmetro, a quantidade de memória usada terá como base os recursos disponíveis do sistema.</span><span class="sxs-lookup"><span data-stu-id="98fac-146">Instead of taking the maximum amount of memory to be used as a parameter, the amount of memory used will be based on available system resources.</span></span> <span data-ttu-id="98fac-147">Quando esses não estiverem disponíveis, os eventos não emparelhados que foram retidos serão cancelados.</span><span class="sxs-lookup"><span data-stu-id="98fac-147">When these are not available, unpaired events that have been retained will be dropped.</span></span> <span data-ttu-id="98fac-148">Se um evento não tiver sido emparelhado e for cancelado, o evento correspondente aparecerá como um evento não emparelhado.</span><span class="sxs-lookup"><span data-stu-id="98fac-148">If an event has not been paired and is dropped, the matching event will appear as an unpaired event.</span></span>  
  
 <span data-ttu-id="98fac-149">O destino de emparelhamento serializa eventos não emparelhados em um formato XML.</span><span class="sxs-lookup"><span data-stu-id="98fac-149">The pairing target serializes unpaired events to an XML format.</span></span> <span data-ttu-id="98fac-150">Esse formato não se adapta a nenhum esquema.</span><span class="sxs-lookup"><span data-stu-id="98fac-150">This format does not conform to any schema.</span></span> <span data-ttu-id="98fac-151">O formato contém apenas dois tipos de elementos.</span><span class="sxs-lookup"><span data-stu-id="98fac-151">The format only contains two element types.</span></span> <span data-ttu-id="98fac-152">O **\<unpaired>** elemento é a raiz, seguido por um.</span><span class="sxs-lookup"><span data-stu-id="98fac-152">The **\<unpaired>** element is the root, followed by one.</span></span> <span data-ttu-id="98fac-153">**\<event>** elemento para cada evento não emparelhado que está sendo rastreado no momento.</span><span class="sxs-lookup"><span data-stu-id="98fac-153">**\<event>** element for each unpaired event that is currently being tracked.</span></span> <span data-ttu-id="98fac-154">O **\<event>** elemento contém um atributo que contém o nome do evento não emparelhado.</span><span class="sxs-lookup"><span data-stu-id="98fac-154">The **\<event>** element contains one attribute that contains the name of the unpaired event.</span></span>  
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="98fac-155">Adicionando o destino a uma sessão</span><span class="sxs-lookup"><span data-stu-id="98fac-155">Adding the Target to a Session</span></span>  
 <span data-ttu-id="98fac-156">Para adicionar o destino de correspondência de par a uma sessão de Eventos Estendidos, você deve incluir a instrução a seguir ao criar ou alterar uma sessão de evento:</span><span class="sxs-lookup"><span data-stu-id="98fac-156">To add the pair matching target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```  
ADD TARGET package0.pair_matching   
```  
  
 <span data-ttu-id="98fac-157">Isso deve ser seguido por uma instrução SET, para definir os eventos iniciais e finais e quais ações ou colunas devem ser correspondidas.</span><span class="sxs-lookup"><span data-stu-id="98fac-157">You would follow this with a SET statement, to define the beginning and ending events, and which actions or columns to match.</span></span> <span data-ttu-id="98fac-158">O exemplo a seguir mostra a sintaxe de exemplo para corresponder o par dos eventos sqlserver.lock_acquired e sqlserver.lock_released.</span><span class="sxs-lookup"><span data-stu-id="98fac-158">The following example shows sample syntax for pair matching the sqlserver.lock_acquired and sqlserver.lock_released events.</span></span>  
  
```  
   ( SET begin_event = 'sqlserver.lock_acquired',  
      begin_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
      end_event = 'sqlserver.lock_released',  
      end_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
   respond_to_memory_pressure = 1)  
```  
  
 <span data-ttu-id="98fac-159">Pra obter mais informações, consulte [Determinar quais consultas estão mantendo bloqueios](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span><span class="sxs-lookup"><span data-stu-id="98fac-159">For more information, see [Determine Which Queries Are Holding Locks](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span></span>  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="98fac-160">Revisando a saída de destino</span><span class="sxs-lookup"><span data-stu-id="98fac-160">Reviewing the Target Output</span></span>  
 <span data-ttu-id="98fac-161">Para examinar a saída de destino da correspondência de par, você pode usar a consulta a seguir com a substituição de *session_name* pelo nome da sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="98fac-161">To review the output for the pair matching target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```  
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="98fac-162">O exemplo a seguir mostra o formato de saída do destino do emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="98fac-162">The following example shows the pairing target output format.</span></span>  
  
```  
<unpaired truncated = "0" matchedCount = "[matched count]" memoryPressureDroppedCount = " [lost count]">  
    <event name  = "[event name]" package = "[package]" id= "[event ID value]" version = "[event version]">  
    <data name = "[column name]">   
    <type name = "[column type]" package = "[type package]" />   
    <value>[column value]</value>  
    <text value>[text value]</text>>  
        </data>  
    </event>  
</unpaired>  
```  
  
## <a name="see-also"></a><span data-ttu-id="98fac-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98fac-163">See Also</span></span>  
 <span data-ttu-id="98fac-164">[Destinos de eventos estendidos do SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="98fac-164">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="98fac-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98fac-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="98fac-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98fac-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="98fac-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98fac-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-event-session-transact-sql)  
  
  
