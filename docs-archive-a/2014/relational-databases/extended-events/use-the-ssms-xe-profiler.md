---
title: Usar a sessão de system_health | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], system health session
- extended events [SQL Server], system_health session
- system_health session [SQL Server extended events]
- system health session [SQL Server extended events]
ms.assetid: 1e1fad43-d747-4775-ac0d-c50648e56d78
author: yualan
ms.author: alayu
ms.openlocfilehash: 86c3221fb4c0ea0690b369888ac8f2f9f82d6ef9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569456"
---
# <a name="use-the-system_health-session"></a><span data-ttu-id="2b984-102">Usar a sessão de system_health</span><span class="sxs-lookup"><span data-stu-id="2b984-102">Use the system_health Session</span></span>
  <span data-ttu-id="2b984-103">A sessão system_health é uma sessão de Eventos Estendidos, incluída por padrão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b984-103">The system_health session is an Extended Events session that is included by default with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2b984-104">Essa sessão é iniciada automaticamente quando o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] é iniciado e executa sem qualquer efeito notável de desempenho.</span><span class="sxs-lookup"><span data-stu-id="2b984-104">This session starts automatically when the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] starts, and runs without any noticeable performance effects.</span></span> <span data-ttu-id="2b984-105">A sessão coleta dados do sistema que você pode usar para ajudar a solucionar problemas de desempenho no [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b984-105">The session collects system data that you can use to help troubleshoot performance issues in the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="2b984-106">Portanto, é recomendável não interromper ou excluir a sessão.</span><span class="sxs-lookup"><span data-stu-id="2b984-106">Therefore, we recommend that you do not stop or delete the session.</span></span>  
  
 <span data-ttu-id="2b984-107">As informações coletadas pela sessão, incluem:</span><span class="sxs-lookup"><span data-stu-id="2b984-107">The session collects information that includes the following:</span></span>  
  
-   <span data-ttu-id="2b984-108">O sql_text e o session_id de qualquer sessão que encontre um erro tenha uma severidade >= 20.</span><span class="sxs-lookup"><span data-stu-id="2b984-108">The sql_text and session_id for any sessions that encounter an error that has a severity >=20.</span></span>  
  
-   <span data-ttu-id="2b984-109">O sql_text e o session_id de qualquer sessão que encontre um erro relacionado à memória.</span><span class="sxs-lookup"><span data-stu-id="2b984-109">The sql_text and session_id for any sessions that encounter a memory-related error.</span></span> <span data-ttu-id="2b984-110">Os erros incluem 17803, 701, 802, 8645, 8651, 8657 e 8902.</span><span class="sxs-lookup"><span data-stu-id="2b984-110">The errors include 17803, 701, 802, 8645, 8651, 8657 and 8902.</span></span>  
  
-   <span data-ttu-id="2b984-111">Um registro de qualquer problema de agendador que não esteja respondendo.</span><span class="sxs-lookup"><span data-stu-id="2b984-111">A record of any non-yielding scheduler problems.</span></span> <span data-ttu-id="2b984-112">(Esses registros aparecem no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como o erro 17883.)</span><span class="sxs-lookup"><span data-stu-id="2b984-112">(These appear in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log as error 17883.)</span></span>  
  
-   <span data-ttu-id="2b984-113">Qualquer deadlock que tenha sido detectado.</span><span class="sxs-lookup"><span data-stu-id="2b984-113">Any deadlocks that are detected.</span></span>  
  
-   <span data-ttu-id="2b984-114">O callstack, o sql_text e o session_id de qualquer sessão que teve esperas em travas (ou outros recursos interessantes) por > 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="2b984-114">The callstack, sql_text, and session_id for any sessions that have waited on latches (or other interesting resources) for > 15 seconds.</span></span>  
  
-   <span data-ttu-id="2b984-115">O callstack, o sql_text e o session_id de qualquer sessão que teve esperas em travas por > 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="2b984-115">The callstack, sql_text, and session_id for any sessions that have waited on locks for > 30 seconds.</span></span>  
  
-   <span data-ttu-id="2b984-116">O callstack, o sql_text e o session_id de qualquer sessão que teve esperas em travas por muito tempo por esperas preemptivas.</span><span class="sxs-lookup"><span data-stu-id="2b984-116">The callstack, sql_text, and session_id for any sessions that have waited for a long time for preemptive waits.</span></span> <span data-ttu-id="2b984-117">A duração varia de acordo com o tipo de espera.</span><span class="sxs-lookup"><span data-stu-id="2b984-117">The duration varies by wait type.</span></span> <span data-ttu-id="2b984-118">Uma espera preventiva ocorre quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está esperando por chamadas de API externas.</span><span class="sxs-lookup"><span data-stu-id="2b984-118">A preemptive wait is where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for external API calls.</span></span>  
  
-   <span data-ttu-id="2b984-119">A pilha de chamadas e a session_id para alocação de CLR e falhas de alocação virtual.</span><span class="sxs-lookup"><span data-stu-id="2b984-119">The callstack and session_id for CLR allocation and virtual allocation failures.</span></span>  
  
-   <span data-ttu-id="2b984-120">Os eventos de ring_buffer para o agente de memória, monitor de agendador, OOM de nó de memória, segurança e conectividade.</span><span class="sxs-lookup"><span data-stu-id="2b984-120">The ring_buffer events for the memory broker, scheduler monitor, memory node OOM, security, and connectivity.</span></span>  
  
-   <span data-ttu-id="2b984-121">Resultados de componente de sistema de sp_server_diagnostics.</span><span class="sxs-lookup"><span data-stu-id="2b984-121">System component results from sp_server_diagnostics.</span></span>  
  
-   <span data-ttu-id="2b984-122">A integridade da instância coletada por scheduler_monitor_system_health_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="2b984-122">Instance health collected by scheduler_monitor_system_health_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="2b984-123">Falhas de alocação de CLR.</span><span class="sxs-lookup"><span data-stu-id="2b984-123">CLR Allocation failures.</span></span>  
  
-   <span data-ttu-id="2b984-124">Erros de conectividade usando connectivity_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="2b984-124">Connectivity errors using connectivity_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="2b984-125">Erros de segurança usando security_error_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="2b984-125">Security errors using security_error_ring_buffer_recorded.</span></span>  
  
## <a name="viewing-the-session-data"></a><span data-ttu-id="2b984-126">Exibindo os dados da sessão</span><span class="sxs-lookup"><span data-stu-id="2b984-126">Viewing the Session Data</span></span>  
 <span data-ttu-id="2b984-127">A sessão usa o destino do buffer de anéis para armazenar os dados.</span><span class="sxs-lookup"><span data-stu-id="2b984-127">The session uses the ring buffer target to store the data.</span></span> <span data-ttu-id="2b984-128">Para exibir os dados da sessão, use a consulta a seguir:</span><span class="sxs-lookup"><span data-stu-id="2b984-128">To view the session data, use the following query:</span></span>  
  
```  
SELECT CAST(xet.target_data as xml) FROM sys.dm_xe_session_targets xet  
JOIN sys.dm_xe_sessions xe  
ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'system_health'  
```  
  
 <span data-ttu-id="2b984-129">Para visualizar os dados de sessão do arquivo de evento, use a interface de usuário de eventos estendidos disponível no Management Studio.</span><span class="sxs-lookup"><span data-stu-id="2b984-129">To view the session data from the event file, use the Extended Events user interface available in Management Studio.</span></span> <span data-ttu-id="2b984-130">Consulte [exibir dados de sessão de evento](../../database-engine/view-event-session-data.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2b984-130">See [View Event Session Data](../../database-engine/view-event-session-data.md) for more information.</span></span>  
  
## <a name="restoring-the-system_health-session"></a><span data-ttu-id="2b984-131">Restaurando a sessão de system_health</span><span class="sxs-lookup"><span data-stu-id="2b984-131">Restoring the system_health Session</span></span>  
 <span data-ttu-id="2b984-132">Se você excluir a sessão de system_health, poderá restaurá-la por meio da execução do arquivo **u_tables.sql** no Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="2b984-132">If you delete the system_health session, you can restore it by executing the **u_tables.sql** file in Query Editor.</span></span> <span data-ttu-id="2b984-133">Esse arquivo está localizado na pasta seguinte, onde C: representa a unidade onde você instalou os arquivos de programa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="2b984-133">This file is located in the following folder, where C: represents the drive where you installed the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] program files:</span></span>  
  
 <span data-ttu-id="2b984-134">C:\Arquivos de Programas\microsoft SQL Server\MSSQL12. \<*instanceid*> \MSSQL\Install</span><span class="sxs-lookup"><span data-stu-id="2b984-134">C:\Program Files\Microsoft SQL Server\MSSQL12.\<*instanceid*>\MSSQL\Install</span></span>  
  
 <span data-ttu-id="2b984-135">Lembre-se de que, depois de restaurar a sessão, você deve iniciá-la com a instrução ALTER EVENT SESSION ou usando o nó **Eventos Estendidos** no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="2b984-135">Be aware that after you restore the session, you must start the session by using the ALTER EVENT SESSION statement or by using the **Extended Events** node in Object Explorer.</span></span> <span data-ttu-id="2b984-136">Caso contrário, a sessão será iniciada automaticamente na próxima vez que você reiniciar o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b984-136">Otherwise, the session starts automatically the next time that you restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b984-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b984-137">See Also</span></span>  
 [<span data-ttu-id="2b984-138">Ferramentas de Eventos Estendidos</span><span class="sxs-lookup"><span data-stu-id="2b984-138">Extended Events Tools</span></span>](extended-events-tools.md)  
  
  
