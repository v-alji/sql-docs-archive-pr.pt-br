---
title: MSSQLSERVER_32044 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32044 (Database Engine error)
ms.assetid: f2d073be-d9a1-4837-8a38-028d3e3403bd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27d9655c3a908f1302f048c6f68159d4f610367a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573077"
---
# <a name="mssqlserver_32044"></a><span data-ttu-id="48265-102">MSSQLSERVER_32044</span><span class="sxs-lookup"><span data-stu-id="48265-102">MSSQLSERVER_32044</span></span>
    
## <a name="details"></a><span data-ttu-id="48265-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="48265-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48265-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="48265-104">Product Name</span></span>|<span data-ttu-id="48265-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="48265-105">SQL Server</span></span>|  
|<span data-ttu-id="48265-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="48265-106">Event ID</span></span>|<span data-ttu-id="48265-107">32044</span><span class="sxs-lookup"><span data-stu-id="48265-107">32044</span></span>|  
|<span data-ttu-id="48265-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="48265-108">Event Source</span></span>|<span data-ttu-id="48265-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="48265-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="48265-110">Componente</span><span class="sxs-lookup"><span data-stu-id="48265-110">Component</span></span>|<span data-ttu-id="48265-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="48265-111">SQLEngine</span></span>|  
|<span data-ttu-id="48265-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="48265-112">Symbolic Name</span></span>|<span data-ttu-id="48265-113">SQLErrorNum32044</span><span class="sxs-lookup"><span data-stu-id="48265-113">SQLErrorNum32044</span></span>|  
|<span data-ttu-id="48265-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="48265-114">Message Text</span></span>|<span data-ttu-id="48265-115">O alerta de 'sobrecarga de confirmação de espelho' foi ativado.</span><span class="sxs-lookup"><span data-stu-id="48265-115">The alert for 'mirror commit overhead' has been raised.</span></span> <span data-ttu-id="48265-116">O valor atual '%d' ultrapassa o limite '%d'.</span><span class="sxs-lookup"><span data-stu-id="48265-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="48265-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="48265-117">Explanation</span></span>  
 <span data-ttu-id="48265-118">Esse evento de espelhamento de banco de dados é emitido na instância do servidor principal para indicar que o tempo de espera de confirmação de agregação foi alcançado ou excedeu um valor de limite especificado pelo usuário devido ao espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="48265-118">This database mirroring event is issued on the principal server instance to indicate that the aggregate commit wait time reached or exceeded a user-specified threshold value because of database mirroring.</span></span> <span data-ttu-id="48265-119">O tempo de espera é o produto do número de transações e do tempo de cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="48265-119">The wait time is the product of the number of transactions and the time of each.</span></span> <span data-ttu-id="48265-120">Por exemplo, os dois casos a seguir produzem 1.000 milissegundos de tempo de espera: 1.000 transações \* 1 milissegundo e 1 transação \* 1.000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="48265-120">For example, the following cases both produce 1000 milliseconds of wait time: 1000 transactions \* 1 millisecond, and 1 transaction \* 1000 milliseconds.</span></span> <span data-ttu-id="48265-121">Um tempo de espera de confirmação aumentado pode ser causado por um surto na contagem de transações, atrasos no envio do log ou atrasos na liberação do log na instância do servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="48265-121">An increased commit wait time can be caused by a surge in the transaction count, delays in sending the log, or delays in flushing the log on the mirror server instance.</span></span>  
  
 <span data-ttu-id="48265-122">A quantidade de sobrecarga espelhada confirmada é uma métrica de desempenho que pode ajudar a avaliar o impacto do desempenho atual de operação síncrona.</span><span class="sxs-lookup"><span data-stu-id="48265-122">The amount of mirror commit overhead is a performance metric that can help you evaluate the current performance impact of synchronous operation.</span></span> <span data-ttu-id="48265-123">Essa métrica só é relevante no modo de segurança alta.</span><span class="sxs-lookup"><span data-stu-id="48265-123">This metric is relevant only in high-safety mode.</span></span> <span data-ttu-id="48265-124">Como o modo de segurança alta é síncrono, a instância do servidor principal espera para confirmar a transação, depois de ter enviado um registro de log para a instância do servidor espelho, até receber a confirmação de que a instância do servidor espelho gravou o registro de log no disco.</span><span class="sxs-lookup"><span data-stu-id="48265-124">Because high-safety mode is synchronous, the principal server instance waits to commit the transaction after it sends a log record to the mirror server instance until it receives confirmation that the mirror server instance has written the log record to disk.</span></span> <span data-ttu-id="48265-125">O registro de log permanece no disco na instância do servidor espelho enquanto ele espera para ser restaurado no banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="48265-125">The log record remains on disk on the mirror server instance while it waits to be restored to the mirror database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="48265-126">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="48265-126">User Action</span></span>  
 <span data-ttu-id="48265-127">Verifique a causa nas cargas das instâncias do servidor principal e espelho, bem como nas respectivas conexões de rede.</span><span class="sxs-lookup"><span data-stu-id="48265-127">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48265-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48265-128">See Also</span></span>  
 <span data-ttu-id="48265-129">[Espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="48265-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="48265-130">Usar os limites de aviso e alertas em métricas de desempenho de espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="48265-130">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
