---
title: MSSQLSERVER_32042 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32042 (Database Engine error)
ms.assetid: 53a51c7a-dcd4-4c15-b4d2-6aaa9dce76da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd959d84da2c54310dea5156b1a45b73490211a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573078"
---
# <a name="mssqlserver_32042"></a><span data-ttu-id="bfe90-102">MSSQLSERVER_32042</span><span class="sxs-lookup"><span data-stu-id="bfe90-102">MSSQLSERVER_32042</span></span>
    
## <a name="details"></a><span data-ttu-id="bfe90-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bfe90-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bfe90-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="bfe90-104">Product Name</span></span>|<span data-ttu-id="bfe90-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfe90-105">SQL Server</span></span>|  
|<span data-ttu-id="bfe90-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="bfe90-106">Event ID</span></span>|<span data-ttu-id="bfe90-107">32042</span><span class="sxs-lookup"><span data-stu-id="bfe90-107">32042</span></span>|  
|<span data-ttu-id="bfe90-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="bfe90-108">Event Source</span></span>|<span data-ttu-id="bfe90-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bfe90-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bfe90-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bfe90-110">Component</span></span>|<span data-ttu-id="bfe90-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bfe90-111">SQLEngine</span></span>|  
|<span data-ttu-id="bfe90-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="bfe90-112">Symbolic Name</span></span>|<span data-ttu-id="bfe90-113">SQLErrorNum32042</span><span class="sxs-lookup"><span data-stu-id="bfe90-113">SQLErrorNum32042</span></span>|  
|<span data-ttu-id="bfe90-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="bfe90-114">Message Text</span></span>|<span data-ttu-id="bfe90-115">O alerta de 'log não enviado' foi interceptado.</span><span class="sxs-lookup"><span data-stu-id="bfe90-115">The alert for 'unsent log' has been raised.</span></span> <span data-ttu-id="bfe90-116">O valor atual '%d' ultrapassa o limite '%d'.</span><span class="sxs-lookup"><span data-stu-id="bfe90-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bfe90-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="bfe90-117">Explanation</span></span>  
 <span data-ttu-id="bfe90-118">Esse evento de espelhamento de banco de dados é emitido na instância do servidor principal para indicar que a quantidade de logs não enviados alcançou um valor de limite especificado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="bfe90-118">This database mirroring event is issued on the principal server instance to indicate that the amount of unsent log has reached a user-specified threshold value.</span></span> <span data-ttu-id="bfe90-119">Normalmente, esse evento acontece porque o desempenho do sistema foi alterado.</span><span class="sxs-lookup"><span data-stu-id="bfe90-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="bfe90-120">A largura da banda entre os dois sistemas diminuiu ou a carga aumentou.</span><span class="sxs-lookup"><span data-stu-id="bfe90-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="bfe90-121">A quantidade de logs não enviados é uma métrica de desempenho que pode ajudá-lo a avaliar o potencial de perda de dados em termos de número de kilobytes (KB) de logs não enviados.</span><span class="sxs-lookup"><span data-stu-id="bfe90-121">The amount of unsent log is a performance metric that can help you evaluate the potential for data loss in terms of the number of kilobytes (KB) of unsent log.</span></span> <span data-ttu-id="bfe90-122">Essa métrica é particularmente relevante para sessões em modo de alto desempenho.</span><span class="sxs-lookup"><span data-stu-id="bfe90-122">This metric is particularly relevant for high-performance mode sessions.</span></span> <span data-ttu-id="bfe90-123">No entanto, essa métrica também é relevante para uma sessão em modo de segurança alta, quando o espelhamento é pausado ou suspenso devido à desconexão dos parceiros.</span><span class="sxs-lookup"><span data-stu-id="bfe90-123">However, this metric is also a relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bfe90-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="bfe90-124">User Action</span></span>  
 <span data-ttu-id="bfe90-125">Verifique a causa nas cargas das instâncias do servidor principal e espelho, bem como nas respectivas conexões de rede.</span><span class="sxs-lookup"><span data-stu-id="bfe90-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe90-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bfe90-126">See Also</span></span>  
 <span data-ttu-id="bfe90-127">[Espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bfe90-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="bfe90-128">Usar os limites de aviso e alertas em métricas de desempenho de espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bfe90-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
