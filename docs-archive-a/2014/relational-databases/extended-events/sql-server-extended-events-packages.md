---
title: Pacotes de eventos estendidos do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], packages
- xe
ms.assetid: 6bcb04fc-ca04-48f4-b96a-20b604973447
author: rothja
ms.author: jroth
ms.openlocfilehash: 45c452300c008d486bd1f4ab4c92b5f76b96ecd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569460"
---
# <a name="sql-server-extended-events-packages"></a><span data-ttu-id="0df85-102">Pacotes de Eventos Estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0df85-102">SQL Server Extended Events Packages</span></span>
  <span data-ttu-id="0df85-103">Um pacote é um contêiner para objetos de Eventos Estendidos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0df85-103">A package is a container for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Extended Events objects.</span></span> <span data-ttu-id="0df85-104">Há três tipos de pacotes de Eventos Estendidos que incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0df85-104">There are three kinds of Extended Events packages, which include the following:</span></span>  
  
-   <span data-ttu-id="0df85-105">package0 - objetos de sistema de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="0df85-105">package0 - Extended Events system objects.</span></span> <span data-ttu-id="0df85-106">Esse é o pacote padrão.</span><span class="sxs-lookup"><span data-stu-id="0df85-106">This is the default package.</span></span>  
  
-   <span data-ttu-id="0df85-107">sqlserver – objetos relacionados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0df85-107">sqlserver - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] related objects.</span></span>  
  
-   <span data-ttu-id="0df85-108">sqlos – objetos relacionados do Sistema Operacional (SQLOS) do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0df85-108">sqlos - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Operating System (SQLOS) related objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0df85-109">O pacote SecAudit é usado pela Auditoria do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0df85-109">The SecAudit package is used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit.</span></span> <span data-ttu-id="0df85-110">Nenhum dos objetos no pacote está disponível por meio da DDL (linguagem de definição de dados) de Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="0df85-110">None of the objects in the package are available through the Extended Events data definition language (DDL).</span></span>  
  
 <span data-ttu-id="0df85-111">Os pacotes são identificados por um nome, um GUID e o módulo binário que contém o pacote.</span><span class="sxs-lookup"><span data-stu-id="0df85-111">Packages are identified by a name, a GUID, and the binary module that contains the package.</span></span> <span data-ttu-id="0df85-112">Para obter mais informações, veja [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0df85-112">For more information, see [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span></span>  
  
 <span data-ttu-id="0df85-113">Um pacote pode conter qualquer ou todos os objetos a seguir, que serão discutidos em maiores detalhes posteriormente neste tópico:</span><span class="sxs-lookup"><span data-stu-id="0df85-113">A package can contain any or all of the following objects, which are discussed in greater detail later in this topic:</span></span>  
  
-   <span data-ttu-id="0df85-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="0df85-114">Events</span></span>  
  
-   <span data-ttu-id="0df85-115">Destinos</span><span class="sxs-lookup"><span data-stu-id="0df85-115">Targets</span></span>  
  
-   <span data-ttu-id="0df85-116">Ações</span><span class="sxs-lookup"><span data-stu-id="0df85-116">Actions</span></span>  
  
-   <span data-ttu-id="0df85-117">Tipos</span><span class="sxs-lookup"><span data-stu-id="0df85-117">Types</span></span>  
  
-   <span data-ttu-id="0df85-118">Predicados</span><span class="sxs-lookup"><span data-stu-id="0df85-118">Predicates</span></span>  
  
-   <span data-ttu-id="0df85-119">Mapas</span><span class="sxs-lookup"><span data-stu-id="0df85-119">Maps</span></span>  
  
 <span data-ttu-id="0df85-120">Objetos de pacotes diferentes podem ser mesclados em uma sessão de evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-120">Objects from different packages can be mixed in an event session.</span></span> <span data-ttu-id="0df85-121">Para obter mais informações, consulte [Sessões de eventos estendidos do SQL Server](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="0df85-121">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
## <a name="package-contents"></a><span data-ttu-id="0df85-122">Conteúdo do pacote</span><span class="sxs-lookup"><span data-stu-id="0df85-122">Package Contents</span></span>  
 <span data-ttu-id="0df85-123">A ilustração a seguir mostra os objetos que podem existir em pacotes, que estão contidos em um módulo.</span><span class="sxs-lookup"><span data-stu-id="0df85-123">The following illustration shows the objects that can exist in packages, which are contained in a module.</span></span> <span data-ttu-id="0df85-124">Um módulo pode ser um executável ou uma biblioteca de vínculo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="0df85-124">A module can be an executable or a dynamic link library.</span></span>  
  
 <span data-ttu-id="0df85-125">![A relação de um módulo, pacotes e objeto](../../database-engine/media/xepackagesobjects.gif "A relação de um módulo, pacotes e objeto")</span><span class="sxs-lookup"><span data-stu-id="0df85-125">![The relationship of a module, packages, and object](../../database-engine/media/xepackagesobjects.gif "The relationship of a module, packages, and object")</span></span>  
  
### <a name="events"></a><span data-ttu-id="0df85-126">Eventos</span><span class="sxs-lookup"><span data-stu-id="0df85-126">Events</span></span>  
 <span data-ttu-id="0df85-127">Eventos são pontos de interesse de monitoramento no caminho de execução de um programa, como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0df85-127">Events are monitoring points of interest in the execution path of a program, such as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0df85-128">O acionamento de um evento induz ao fato de que o ponto de interesse foi alcançado e traz informações do momento de acionamento do evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-128">An event firing carries with it the fact that the point of interest was reached, and state information from the time the event was fired.</span></span>  
  
 <span data-ttu-id="0df85-129">Os eventos somente podem ser usados para rastreamento ou ações de disparo.</span><span class="sxs-lookup"><span data-stu-id="0df85-129">Events can be used solely for tracing purposes or for triggering actions.</span></span> <span data-ttu-id="0df85-130">Essas ações podem ser síncronas ou assíncronas.</span><span class="sxs-lookup"><span data-stu-id="0df85-130">These actions can either be synchronous or asynchronous.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0df85-131">Um evento não tem qualquer conhecimento das ações que podem ser disparadas em resposta ao acionamento do evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-131">An event does not have any knowledge of the actions that may be triggered in response to the event firing.</span></span>  
  
 <span data-ttu-id="0df85-132">Um conjunto de eventos em um pacote não pode ser alterado depois que o pacote for registrado com o Extended Events.</span><span class="sxs-lookup"><span data-stu-id="0df85-132">A set of events in a package cannot change after the package is registered with Extended Events.</span></span>  
  
 <span data-ttu-id="0df85-133">Todos os eventos têm um esquema de versão que define seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0df85-133">All events have a versioned schema which defines their contents.</span></span> <span data-ttu-id="0df85-134">Esse esquema é composto por colunas de evento com tipos bem definidos.</span><span class="sxs-lookup"><span data-stu-id="0df85-134">This schema is composed of event columns with well defined types.</span></span> <span data-ttu-id="0df85-135">Um evento de um tipo específico sempre tem que fornecer seus dados exatamente na mesma ordem especificada no esquema.</span><span class="sxs-lookup"><span data-stu-id="0df85-135">An event of a specific type must always provide its data in exactly the same order that is specified in the schema.</span></span> <span data-ttu-id="0df85-136">No entanto, um evento de destino não precisa consumir todos os dados fornecidos.</span><span class="sxs-lookup"><span data-stu-id="0df85-136">However, an event target does not have to consume all the data that is provided.</span></span>  
  
#### <a name="event-categorization"></a><span data-ttu-id="0df85-137">Categorização do evento</span><span class="sxs-lookup"><span data-stu-id="0df85-137">Event Categorization</span></span>  
 <span data-ttu-id="0df85-138">O Extended Events usa um modelo de categorização de evento semelhante ao ETW (Rastreamento de Eventos do Windows).</span><span class="sxs-lookup"><span data-stu-id="0df85-138">Extended Events uses an event categorization model similar to Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="0df85-139">Duas propriedades de evento são usadas para categorização, canal e palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="0df85-139">Two event properties are used for categorization, channel and keyword.</span></span> <span data-ttu-id="0df85-140">O uso dessas propriedades dá suporte à integração do Extended Events com o ETW e suas ferramentas.</span><span class="sxs-lookup"><span data-stu-id="0df85-140">Using these properties supports the integration of Extended Events with ETW and its tools.</span></span>  
  
 <span data-ttu-id="0df85-141">**Channel**</span><span class="sxs-lookup"><span data-stu-id="0df85-141">**Channel**</span></span>  
  
 <span data-ttu-id="0df85-142">Um canal identifica a audiência para um evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-142">A channel identifies the audience for an event.</span></span> <span data-ttu-id="0df85-143">Esses canais são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0df85-143">These channels are described in the following table.</span></span>  
  
|<span data-ttu-id="0df85-144">Termo</span><span class="sxs-lookup"><span data-stu-id="0df85-144">Term</span></span>|<span data-ttu-id="0df85-145">Definição</span><span class="sxs-lookup"><span data-stu-id="0df85-145">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="0df85-146">Admin</span><span class="sxs-lookup"><span data-stu-id="0df85-146">Admin</span></span>|<span data-ttu-id="0df85-147">Os eventos Admin são principalmente direcionados aos usuários finais, administradores e suporte.</span><span class="sxs-lookup"><span data-stu-id="0df85-147">Admin events are primarily targeted to the end users, administrators, and support.</span></span> <span data-ttu-id="0df85-148">Os eventos encontrados nos canais admin indicam um problema com uma solução bem definida na qual um administrador pode agir.</span><span class="sxs-lookup"><span data-stu-id="0df85-148">The events that are found in the admin channels indicate a problem with a well-defined solution that an administrator can act on.</span></span> <span data-ttu-id="0df85-149">Um exemplo de um evento admin é quando um aplicativo falha ao se conectar a uma impressora.</span><span class="sxs-lookup"><span data-stu-id="0df85-149">An example of an admin event is when an application fails to connect to a printer.</span></span> <span data-ttu-id="0df85-150">Esses eventos são bem documentados ou têm uma mensagem associada a eles que diz ao leitor o que fazer para retificar o problema.</span><span class="sxs-lookup"><span data-stu-id="0df85-150">These events are either well-documented or have a message associated with them that tells the reader what to do to rectify the problem.</span></span>|  
|<span data-ttu-id="0df85-151">Operacional</span><span class="sxs-lookup"><span data-stu-id="0df85-151">Operational</span></span>|<span data-ttu-id="0df85-152">Eventos operacionais são usados para analisar e diagnosticar um problema ou uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="0df85-152">Operational events are used for analyzing and diagnosing a problem or occurrence.</span></span> <span data-ttu-id="0df85-153">Eles podem ser usados para disparar ferramentas ou tarefas com base no problema ou na ocorrência.</span><span class="sxs-lookup"><span data-stu-id="0df85-153">They can be used to trigger tools or tasks based on the problem or occurrence.</span></span> <span data-ttu-id="0df85-154">Um exemplo de um evento operacional é quando uma impressora é adicionada ou removida de um sistema.</span><span class="sxs-lookup"><span data-stu-id="0df85-154">An example of an operational event is when a printer is added or removed from a system.</span></span>|  
|<span data-ttu-id="0df85-155">Analítico</span><span class="sxs-lookup"><span data-stu-id="0df85-155">Analytic</span></span>|<span data-ttu-id="0df85-156">Eventos analíticos são publicados em grande volume.</span><span class="sxs-lookup"><span data-stu-id="0df85-156">Analytic events are published in high volume.</span></span> <span data-ttu-id="0df85-157">Eles descrevem operação de programa e são geralmente usados em investigações de desempenho.</span><span class="sxs-lookup"><span data-stu-id="0df85-157">They describe program operation and are typically used in performance investigations.</span></span>|  
|<span data-ttu-id="0df85-158">Depurar</span><span class="sxs-lookup"><span data-stu-id="0df85-158">Debug</span></span>|<span data-ttu-id="0df85-159">Eventos depuradores são usados somente por desenvolvedores para diagnosticar um problema de depuração.</span><span class="sxs-lookup"><span data-stu-id="0df85-159">Debug events are used solely by developers to diagnose a problem for debugging.</span></span><br /><br /> <span data-ttu-id="0df85-160">Observação: os eventos no canal de depuração retornam dados de estado específicos da implementação interna.</span><span class="sxs-lookup"><span data-stu-id="0df85-160">Note: Events in the Debug channel return internal implementation-specific state data.</span></span> <span data-ttu-id="0df85-161">Os esquemas e os dados retornados pelos eventos podem mudar ou se tornar inválidos em versões futuras do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0df85-161">The schemas and data that the events return may change or become invalid in future versions of SQL Server.</span></span> <span data-ttu-id="0df85-162">Portanto, eventos no canal de depuração podem mudar ou ser removidos em versões futuras do SQL Server, sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="0df85-162">Therefore, events in the Debug channel may change or be removed in future versions of SQL Server without notice.</span></span>|  
  
 <span data-ttu-id="0df85-163">**Palavra-chave**</span><span class="sxs-lookup"><span data-stu-id="0df85-163">**Keyword**</span></span>  
  
 <span data-ttu-id="0df85-164">Uma palavra-chave é específica do aplicativo e habilita um agrupamento mais refinado dos eventos relacionados, o que facilita a especificação e recuperação de um evento que você quer usar em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="0df85-164">A keyword is application specific and enables a finer-grained grouping of related events, which makes it easier for you to specify and retrieve an event that you want to use in a session.</span></span> <span data-ttu-id="0df85-165">A consulta a seguir pode ser usada para obter informações de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="0df85-165">You can use the following query to obtain keyword information.</span></span>  
  
```  
select map_value Keyword from sys.dm_xe_map_values  
where name = 'keyword_map'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0df85-166">Palavras-chave mapeiam com precisão até o agrupamento atual de eventos de Rastreamento do SQL.</span><span class="sxs-lookup"><span data-stu-id="0df85-166">Keywords map closely to the current grouping of SQL Trace events.</span></span>  
  
### <a name="targets"></a><span data-ttu-id="0df85-167">Destinos</span><span class="sxs-lookup"><span data-stu-id="0df85-167">Targets</span></span>  
 <span data-ttu-id="0df85-168">Destinos são consumidores de evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-168">Targets are event consumers.</span></span> <span data-ttu-id="0df85-169">Os destinos processam eventos de forma síncrona no thread que aciona o evento ou de forma assíncrona em um thread fornecido pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="0df85-169">Targets process events, either synchronously on the thread that fires the event or asynchronously on a system provided thread.</span></span> <span data-ttu-id="0df85-170">Os Eventos Estendidos fornecem vários destinos que você pode usar conforme apropriado para direcionar a saída do evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-170">Extended Events provides several targets that you can use as appropriate for directing event output.</span></span> <span data-ttu-id="0df85-171">Para obter mais informações, consulte [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="0df85-171">For more information, see [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span></span>  
  
### <a name="actions"></a><span data-ttu-id="0df85-172">Ações</span><span class="sxs-lookup"><span data-stu-id="0df85-172">Actions</span></span>  
 <span data-ttu-id="0df85-173">Uma ação é uma resposta ou série de respostas de programa a um evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-173">An action is a programmatic response or series of responses to an event.</span></span> <span data-ttu-id="0df85-174">As ações são associadas a um evento e cada evento pode ter um conjunto exclusivo de ações.</span><span class="sxs-lookup"><span data-stu-id="0df85-174">Actions are bound to an event, and each event may have a unique set of actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0df85-175">Ações destinadas a um conjunto específico de eventos não podem ser associadas a eventos desconhecidos.</span><span class="sxs-lookup"><span data-stu-id="0df85-175">Actions that are intended for a specific set of events cannot bind to unknown events.</span></span>  
  
 <span data-ttu-id="0df85-176">Uma ação associada a um evento é invocada de forma síncrona no thread que acionou o evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-176">An action bound to an event is invoked synchronously on the thread that fired the event.</span></span> <span data-ttu-id="0df85-177">Há muitos tipos de ação e eles têm uma ampla faixa de recursos.</span><span class="sxs-lookup"><span data-stu-id="0df85-177">There are many types of actions and they have a wide range of capabilities.</span></span> <span data-ttu-id="0df85-178">As ações podem:</span><span class="sxs-lookup"><span data-stu-id="0df85-178">Actions can:</span></span>  
  
-   <span data-ttu-id="0df85-179">Capturar um despejo da pilha e inspecionar dados.</span><span class="sxs-lookup"><span data-stu-id="0df85-179">Capture a stack dump and inspect data.</span></span>  
  
-   <span data-ttu-id="0df85-180">Armazenar informações de estado em um contexto local usando armazenamento variável.</span><span class="sxs-lookup"><span data-stu-id="0df85-180">Store state information in a local context using variable storage.</span></span>  
  
-   <span data-ttu-id="0df85-181">Agregar dados de evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-181">Aggregate event data.</span></span>  
  
-   <span data-ttu-id="0df85-182">Anexar dados aos dados de evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-182">Append data to event data.</span></span>  
  
 <span data-ttu-id="0df85-183">Alguns exemplos comuns e bem conhecidos de ações:</span><span class="sxs-lookup"><span data-stu-id="0df85-183">Some typical and well known examples of actions are:</span></span>  
  
-   <span data-ttu-id="0df85-184">Despejo da pilha</span><span class="sxs-lookup"><span data-stu-id="0df85-184">Stack dumper</span></span>  
  
-   <span data-ttu-id="0df85-185">Detecção de plano de execução (só no[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="0df85-185">Execution plan detection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="0df85-186">coleção de pilha (somente[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="0df85-186">stack collection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   <span data-ttu-id="0df85-187">Cálculo de estatísticas em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="0df85-187">Run time statistics calculation</span></span>  
  
-   <span data-ttu-id="0df85-188">Agrupamento de entrada de usuário em exceção</span><span class="sxs-lookup"><span data-stu-id="0df85-188">Gather user input on exception</span></span>  
  
### <a name="predicates"></a><span data-ttu-id="0df85-189">Predicados</span><span class="sxs-lookup"><span data-stu-id="0df85-189">Predicates</span></span>  
 <span data-ttu-id="0df85-190">Predicados são um conjunto de regras lógicas usado para avaliar eventos quando eles são processados.</span><span class="sxs-lookup"><span data-stu-id="0df85-190">Predicates are a set of logical rules that are used to evaluate events when they are processed.</span></span> <span data-ttu-id="0df85-191">Isso permite que o usuário do Extend Events capture dados de evento seletivamente com base em critérios específicos.</span><span class="sxs-lookup"><span data-stu-id="0df85-191">This enables the Extended Events user to selectively capture event data based on specific criteria.</span></span>  
  
 <span data-ttu-id="0df85-192">Predicados podem armazenar dados em um contexto local que podem ser usados para criar predicados que retornam valores verdadeiros uma vez a cada *n* minutos ou a cada *n* vezes que um evento é acionado.</span><span class="sxs-lookup"><span data-stu-id="0df85-192">Predicates can store data in a local context that can be used for creating predicates that return true once every *n* minutes or every *n* times that an event fires.</span></span> <span data-ttu-id="0df85-193">Esse armazenamento de contexto local também pode ser usado para atualizar o predicado dinamicamente, suprimindo, assim, acionamento de evento futuro, caso os eventos contenham dados semelhantes.</span><span class="sxs-lookup"><span data-stu-id="0df85-193">This local context storage can also be used to dynamically update the predicate, thereby suppressing future event firing if the events contain similar data.</span></span>  
  
 <span data-ttu-id="0df85-194">Os predicados têm a capacidade de recuperar informações de contexto, como a ID do thread e os dados específicos do evento.</span><span class="sxs-lookup"><span data-stu-id="0df85-194">Predicates have the ability to retrieve context information, such as the thread ID, as well as event specific data.</span></span> <span data-ttu-id="0df85-195">Os predicados são avaliados como expressões boolianas completas e oferecem suporte a circuito pequeno no primeiro ponto em que toda a expressão é considerada falsa.</span><span class="sxs-lookup"><span data-stu-id="0df85-195">Predicates are evaluated as full Boolean expressions, and support short circuiting at the first point where the entire expression is found to be false.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0df85-196">Predicados com efeitos colaterais não podem ser avaliados se a verificação de um predicado anterior falhar.</span><span class="sxs-lookup"><span data-stu-id="0df85-196">Predicates with side effects may not be evaluated if an earlier predicate check fails.</span></span>  
  
### <a name="types"></a><span data-ttu-id="0df85-197">Tipos</span><span class="sxs-lookup"><span data-stu-id="0df85-197">Types</span></span>  
 <span data-ttu-id="0df85-198">Como os dados são uma coleção de bytes unidos, o comprimento e as características da coleção de bytes são necessários na interpretação dos dados.</span><span class="sxs-lookup"><span data-stu-id="0df85-198">Because data is a collection of bytes strung together, the length and characteristics of the byte collection are required in order to interpret the data.</span></span> <span data-ttu-id="0df85-199">Essas informações são encapsuladas no objeto Tipo.</span><span class="sxs-lookup"><span data-stu-id="0df85-199">This information is encapsulated in the Type object.</span></span> <span data-ttu-id="0df85-200">Os tipos seguintes são fornecidos para objetos de pacote:</span><span class="sxs-lookup"><span data-stu-id="0df85-200">The following types are provided for package objects:</span></span>  
  
-   <span data-ttu-id="0df85-201">event</span><span class="sxs-lookup"><span data-stu-id="0df85-201">event</span></span>  
  
-   <span data-ttu-id="0df85-202">ação</span><span class="sxs-lookup"><span data-stu-id="0df85-202">action</span></span>  
  
-   <span data-ttu-id="0df85-203">destino</span><span class="sxs-lookup"><span data-stu-id="0df85-203">target</span></span>  
  
-   <span data-ttu-id="0df85-204">pred_source</span><span class="sxs-lookup"><span data-stu-id="0df85-204">pred_source</span></span>  
  
-   <span data-ttu-id="0df85-205">pred_compare</span><span class="sxs-lookup"><span data-stu-id="0df85-205">pred_compare</span></span>  
  
-   <span data-ttu-id="0df85-206">tipo</span><span class="sxs-lookup"><span data-stu-id="0df85-206">type</span></span>  
  
 <span data-ttu-id="0df85-207">Para obter mais informações, veja [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0df85-207">For more information, see [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span></span>  
  
### <a name="maps"></a><span data-ttu-id="0df85-208">Mapas</span><span class="sxs-lookup"><span data-stu-id="0df85-208">Maps</span></span>  
 <span data-ttu-id="0df85-209">Uma tabela de mapas mapeia um valor interno para uma cadeia de caracteres que habilita um usuário a saber o que o valor representa.</span><span class="sxs-lookup"><span data-stu-id="0df85-209">A map table maps an internal value to a string, which enables a user to know what the value represents.</span></span> <span data-ttu-id="0df85-210">Em vez de só poder obter um valor numérico, um usuário pode adquirir uma descrição significativa do valor interno.</span><span class="sxs-lookup"><span data-stu-id="0df85-210">Instead of only being able to obtain a numeric value, a user can get a meaningful description of the internal value.</span></span> <span data-ttu-id="0df85-211">A consulta a seguir mostra como obter valores de mapa.</span><span class="sxs-lookup"><span data-stu-id="0df85-211">The following query shows how to obtain map values.</span></span>  
  
```  
select map_key, map_value from sys.dm_xe_map_values  
where name = 'lock_mode'  
```  
  
 <span data-ttu-id="0df85-212">A consulta precedente produz a saída a seguir.</span><span class="sxs-lookup"><span data-stu-id="0df85-212">The preceding query produces the following output.</span></span>  
  
 `map_key     map_value`  
  
 `---------------------`  
  
 `0           NL`  
  
 `1           SCH_S`  
  
 `2           SCH_M`  
  
 `3           S`  
  
 `4           U`  
  
 `5           X`  
  
 `6           IS`  
  
 `7           IU`  
  
 `8           IX`  
  
 `9           SIU`  
  
 `10          SIX`  
  
 `11          UIX`  
  
 `12          BU`  
  
 `13          RS_S`  
  
 `14          RS_U`  
  
 `15          RI_NL`  
  
 `16          RI_S`  
  
 `17          RI_U`  
  
 `18          RI_X`  
  
 `19          RX_S`  
  
 `20          RX_U`  
  
 `21          RX_X`  
  
 `21          RX_X`  
  
 <span data-ttu-id="0df85-213">Usando essa tabela como um exemplo, suponhamos que você tenha uma coluna denominada modo e seu valor seja 5.</span><span class="sxs-lookup"><span data-stu-id="0df85-213">Using this table as an example, assume that you have a column named mode, and its value is 5.</span></span> <span data-ttu-id="0df85-214">A tabela indica que 5 mapeia para X, o que significa que o tipo de bloqueio é Exclusivo.</span><span class="sxs-lookup"><span data-stu-id="0df85-214">The table indicates that 5 maps to X, which means the lock type is Exclusive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df85-215">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0df85-215">See Also</span></span>  
 <span data-ttu-id="0df85-216">[SQL Server sessões de eventos estendidos](sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="0df85-216">[SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md) </span></span>  
 <span data-ttu-id="0df85-217">[SQL Server mecanismo de eventos estendidos](sql-server-extended-events-engine.md) </span><span class="sxs-lookup"><span data-stu-id="0df85-217">[SQL Server Extended Events Engine](sql-server-extended-events-engine.md) </span></span>  
 [<span data-ttu-id="0df85-218">Destinos de eventos estendidos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0df85-218">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
