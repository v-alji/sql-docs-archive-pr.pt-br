---
title: MSSQLSERVER_32043 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32043 (Database Engine error)
ms.assetid: a0c48ae3-4c8c-419c-afb5-579fcefac01d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2febc7173c8144451c7a9b0576f2293d5594c6df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569527"
---
# <a name="mssqlserver_32043"></a><span data-ttu-id="be426-102">MSSQLSERVER_32043</span><span class="sxs-lookup"><span data-stu-id="be426-102">MSSQLSERVER_32043</span></span>
    
## <a name="details"></a><span data-ttu-id="be426-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="be426-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be426-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="be426-104">Product Name</span></span>|<span data-ttu-id="be426-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="be426-105">SQL Server</span></span>|  
|<span data-ttu-id="be426-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="be426-106">Event ID</span></span>|<span data-ttu-id="be426-107">32043</span><span class="sxs-lookup"><span data-stu-id="be426-107">32043</span></span>|  
|<span data-ttu-id="be426-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="be426-108">Event Source</span></span>|<span data-ttu-id="be426-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="be426-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="be426-110">Componente</span><span class="sxs-lookup"><span data-stu-id="be426-110">Component</span></span>|<span data-ttu-id="be426-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="be426-111">SQLEngine</span></span>|  
|<span data-ttu-id="be426-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="be426-112">Symbolic Name</span></span>|<span data-ttu-id="be426-113">SQLErrorNum32043</span><span class="sxs-lookup"><span data-stu-id="be426-113">SQLErrorNum32043</span></span>|  
|<span data-ttu-id="be426-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="be426-114">Message Text</span></span>|<span data-ttu-id="be426-115">O alerta de 'log não restaurado' foi ativado.</span><span class="sxs-lookup"><span data-stu-id="be426-115">The alert for 'unrestored log' has been raised.</span></span> <span data-ttu-id="be426-116">O valor atual '%d' ultrapassa o limite '%d'.</span><span class="sxs-lookup"><span data-stu-id="be426-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be426-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="be426-117">Explanation</span></span>  
 <span data-ttu-id="be426-118">Esse evento de espelhamento de banco de dados é emitido na instância do servidor espelho para indicar que a quantidade de logs não restaurados alcançou um valor do limite especificado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="be426-118">This database mirroring event is issued on the mirror server instance to indicate that the amount of unrestored log reached a user-specified threshold value.</span></span> <span data-ttu-id="be426-119">Normalmente, esse evento acontece porque o desempenho do sistema foi alterado.</span><span class="sxs-lookup"><span data-stu-id="be426-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="be426-120">A largura da banda entre os dois sistemas diminuiu ou a carga aumentou.</span><span class="sxs-lookup"><span data-stu-id="be426-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="be426-121">Um log não restaurado é um log que foi recebido pela instância do servidor espelho e foi gravado no disco, mas está aguardando para ser restaurado no banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="be426-121">An unrestored log is a log that has been received by the mirror server instance and written to disk but is waiting to be restored to the mirror database.</span></span> <span data-ttu-id="be426-122">A quantidade de logs não restaurados em KB (quilobytes) é uma métrica de desempenho que pode ajudar a avaliar o tempo atual de failover.</span><span class="sxs-lookup"><span data-stu-id="be426-122">The amount of unrestored log in kilobytes (KB) is a performance metric that can help you evaluate the current failover time.</span></span> <span data-ttu-id="be426-123">O tempo necessário para aplicar o log não restaurado é o fator principal no tempo de failover, além de um curto período adicional necessário para restaurar o banco de dados e fazer com que ele fique online.</span><span class="sxs-lookup"><span data-stu-id="be426-123">The time that is required to apply the unrestored log is the main factor in failover time, along with a short additional time that is required to recover the database and bring it online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be426-124">Em um failover automático, o tempo necessário para que o sistema perceba a falha é independente do tempo de failover.</span><span class="sxs-lookup"><span data-stu-id="be426-124">For an automatic failover, the time for the system to notice the failure is independent of the failover time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be426-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="be426-125">User Action</span></span>  
 <span data-ttu-id="be426-126">Verifique a causa nas cargas das instâncias do servidor principal e espelho, bem como nas respectivas conexões de rede.</span><span class="sxs-lookup"><span data-stu-id="be426-126">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be426-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="be426-127">See Also</span></span>  
 <span data-ttu-id="be426-128">[Espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="be426-128">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="be426-129">Usar os limites de aviso e alertas em métricas de desempenho de espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="be426-129">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
