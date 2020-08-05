---
title: MSSQLSERVER_32040 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32040 (Database Engine error)
ms.assetid: 709219b1-f8b2-4696-8923-dd2e91492eb8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05692e2f20b0719c1ca8f48282c3b7aaed8e2341
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573079"
---
# <a name="mssqlserver_32040"></a><span data-ttu-id="18ddf-102">MSSQLSERVER_32040</span><span class="sxs-lookup"><span data-stu-id="18ddf-102">MSSQLSERVER_32040</span></span>
    
## <a name="details"></a><span data-ttu-id="18ddf-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="18ddf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="18ddf-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="18ddf-104">Product Name</span></span>|<span data-ttu-id="18ddf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="18ddf-105">SQL Server</span></span>|  
|<span data-ttu-id="18ddf-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="18ddf-106">Event ID</span></span>|<span data-ttu-id="18ddf-107">32040</span><span class="sxs-lookup"><span data-stu-id="18ddf-107">32040</span></span>|  
|<span data-ttu-id="18ddf-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="18ddf-108">Event Source</span></span>|<span data-ttu-id="18ddf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="18ddf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="18ddf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="18ddf-110">Component</span></span>|<span data-ttu-id="18ddf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="18ddf-111">SQLEngine</span></span>|  
|<span data-ttu-id="18ddf-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="18ddf-112">Symbolic Name</span></span>|<span data-ttu-id="18ddf-113">SQLErrorNum32040</span><span class="sxs-lookup"><span data-stu-id="18ddf-113">SQLErrorNum32040</span></span>|  
|<span data-ttu-id="18ddf-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="18ddf-114">Message Text</span></span>|<span data-ttu-id="18ddf-115">O alerta de 'transação não enviada mais antiga' foi ativado.</span><span class="sxs-lookup"><span data-stu-id="18ddf-115">The alert for 'oldest unsent transaction' has been raised.</span></span> <span data-ttu-id="18ddf-116">O valor atual '%d' ultrapassa o limite '%d'.</span><span class="sxs-lookup"><span data-stu-id="18ddf-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="18ddf-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="18ddf-117">Explanation</span></span>  
 <span data-ttu-id="18ddf-118">Esse evento de espelhamento de banco de dados é emitido na instância do servidor principal para indicar que a duração da transação mais antiga não enviada alcançou um valor de limite especificado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="18ddf-118">This database mirroring event is issued on the principal server instance to indicate that the age of the oldest unsent transaction has reached a user-specified threshold value.</span></span> <span data-ttu-id="18ddf-119">Normalmente, esse evento acontece porque o desempenho do sistema foi alterado.</span><span class="sxs-lookup"><span data-stu-id="18ddf-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="18ddf-120">A largura da banda entre os dois sistemas diminuiu ou a carga aumentou.</span><span class="sxs-lookup"><span data-stu-id="18ddf-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="18ddf-121">A duração da transação mais antiga não enviada é uma métrica de desempenho que pode ajudar a avaliar o potencial de perda de dados mensurado pelo número de minutos das transações não enviadas.</span><span class="sxs-lookup"><span data-stu-id="18ddf-121">The age of the oldest unsent transaction is a performance metric that can help you evaluate the potential for data loss as measured by the number of minutes of unsent transactions.</span></span> <span data-ttu-id="18ddf-122">Essa métrica é especialmente relevante para sessões em modo de alto desempenho.</span><span class="sxs-lookup"><span data-stu-id="18ddf-122">This metric is especially relevant for high-performance mode sessions.</span></span> <span data-ttu-id="18ddf-123">No entanto, essa métrica também é relevante para uma sessão em modo de alta segurança, quando o espelhamento é pausado ou suspenso devido à desconexão dos parceiros.</span><span class="sxs-lookup"><span data-stu-id="18ddf-123">However, this metric is also relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="18ddf-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="18ddf-124">User Action</span></span>  
 <span data-ttu-id="18ddf-125">Verifique a causa nas cargas das instâncias do servidor principal e espelho, bem como nas respectivas conexões de rede.</span><span class="sxs-lookup"><span data-stu-id="18ddf-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ddf-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18ddf-126">See Also</span></span>  
 <span data-ttu-id="18ddf-127">[Espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="18ddf-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="18ddf-128">Usar os limites de aviso e alertas em métricas de desempenho de espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="18ddf-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
