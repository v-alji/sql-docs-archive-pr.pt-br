---
title: SQL Server, objeto de Ativação do Broker | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Broker Activation
- Broker Activation object
ms.assetid: cd9b6880-c924-42c7-b333-09c303317c0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4048c2baecaeb4bde7a1e215a15e8c51a60a01bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680393"
---
# <a name="sql-server-broker-activation-object"></a><span data-ttu-id="12208-102">SQL Server, objeto Broker Activation</span><span class="sxs-lookup"><span data-stu-id="12208-102">SQL Server, Broker Activation Object</span></span>
  <span data-ttu-id="12208-103">O objeto de desempenho **SQLServer:BrokerActivation** contém contadores de desempenho que relatam informações sobre a ativação de procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="12208-103">The **SQLServer:BrokerActivation** performance object contains performance counters that report information on stored procedure activation.</span></span> <span data-ttu-id="12208-104">A tabela a seguir lista os contadores contidos nesse objeto.</span><span class="sxs-lookup"><span data-stu-id="12208-104">The table below lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="12208-105">Contadores do SQL Server:BrokerActivation</span><span class="sxs-lookup"><span data-stu-id="12208-105">SQL Server Broker Activation counters</span></span>|<span data-ttu-id="12208-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="12208-106">Description</span></span>|  
|-------------------------------------------|-----------------|  
|<span data-ttu-id="12208-107">**Procedimentos Armazenados Invocados/s**</span><span class="sxs-lookup"><span data-stu-id="12208-107">**Stored Procedures Invoked/sec**</span></span>|<span data-ttu-id="12208-108">Este contador informa o número total de procedimentos armazenados de ativação invocados por todos os monitores de fila na instância, por segundo.</span><span class="sxs-lookup"><span data-stu-id="12208-108">This counter reports the total number of activation stored procedures invoked by all queue monitors in the instance per second.</span></span>|  
|<span data-ttu-id="12208-109">**Limite de Tarefas Atingido**</span><span class="sxs-lookup"><span data-stu-id="12208-109">**Task Limit Reached**</span></span>|<span data-ttu-id="12208-110">Este contador informa o número total de vezes que um monitor de fila teria iniciado uma nova tarefa, mas não o fez porque o número máximo de tarefas da fila já se encontra em execução.</span><span class="sxs-lookup"><span data-stu-id="12208-110">This counter reports the total number of times that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="12208-111">**Limite de Tarefas Atingido/s**</span><span class="sxs-lookup"><span data-stu-id="12208-111">**Task Limit Reached/sec**</span></span>|<span data-ttu-id="12208-112">Este contador informa o número total de vezes, por segundo, que um monitor de fila teria iniciado uma nova tarefa, mas não o fez porque o número máximo de tarefas da fila já se encontra em execução.</span><span class="sxs-lookup"><span data-stu-id="12208-112">This counter reports the number of times per second that a queue monitor would have started a new task, but did not because the maximum number of tasks for the queue is already running.</span></span>|  
|<span data-ttu-id="12208-113">**Tarefas Anuladas/s**</span><span class="sxs-lookup"><span data-stu-id="12208-113">**Tasks Aborted/sec**</span></span>|<span data-ttu-id="12208-114">Este contador informa o número total de tarefas de procedimentos armazenados de ativação que acabaram em erro ou foram anuladas por um monitor de fila devido a falha em receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="12208-114">This counter reports the number of activation stored procedure tasks that end with an error, or are aborted by a queue monitor for failing to receive messages.</span></span>|  
|<span data-ttu-id="12208-115">**Tarefas em Execução**</span><span class="sxs-lookup"><span data-stu-id="12208-115">**Tasks Running**</span></span>|<span data-ttu-id="12208-116">Este contador informa o número de procedimentos armazenados de ativação que se encontram atualmente em execução.</span><span class="sxs-lookup"><span data-stu-id="12208-116">This counter reports the number of activation stored procedures that are currently running.</span></span>|  
|<span data-ttu-id="12208-117">**Tarefas Iniciadas/s**</span><span class="sxs-lookup"><span data-stu-id="12208-117">**Tasks Started/sec**</span></span>|<span data-ttu-id="12208-118">Este contador informa o número total de procedimentos armazenados de ativação iniciados, por segundo, por todos os monitores de fila na instância.</span><span class="sxs-lookup"><span data-stu-id="12208-118">This counter reports the number of activation stored procedures started per second by all queue monitors in the instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12208-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12208-119">See Also</span></span>  
 <span data-ttu-id="12208-120">[.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12208-120">[sys.dm_broker_activated_tasks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-activated-tasks-transact-sql) </span></span>  
 <span data-ttu-id="12208-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12208-121">[sys.dm_broker_queue_monitors &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-broker-queue-monitors-transact-sql) </span></span>  
 [<span data-ttu-id="12208-122">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="12208-122">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
