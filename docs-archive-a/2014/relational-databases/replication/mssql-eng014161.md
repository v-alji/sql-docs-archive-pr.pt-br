---
title: MSSQL_ENG014161 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014161 error
ms.assetid: 4b983e76-bb77-43c5-b44b-19919d3da619
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8cf85181e444385e1a3908761ba71414b68cf3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568469"
---
# <a name="mssql_eng014161"></a><span data-ttu-id="dc843-102">MSSQL_ENG014161</span><span class="sxs-lookup"><span data-stu-id="dc843-102">MSSQL_ENG014161</span></span>
    
## <a name="message-details"></a><span data-ttu-id="dc843-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="dc843-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc843-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="dc843-104">Product Name</span></span>|<span data-ttu-id="dc843-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc843-105">SQL Server</span></span>|  
|<span data-ttu-id="dc843-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="dc843-106">Event ID</span></span>|<span data-ttu-id="dc843-107">14161</span><span class="sxs-lookup"><span data-stu-id="dc843-107">14161</span></span>|  
|<span data-ttu-id="dc843-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="dc843-108">Event Source</span></span>|<span data-ttu-id="dc843-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dc843-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dc843-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dc843-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="dc843-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="dc843-111">Symbolic Name</span></span>||  
|<span data-ttu-id="dc843-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="dc843-112">Message Text</span></span>|<span data-ttu-id="dc843-113">O limite [%s:%s] da publicação [%s] foi definido.</span><span class="sxs-lookup"><span data-stu-id="dc843-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="dc843-114">Verifique se o leitor de log e os agentes de distribuição estão em execução e atendem ao requisito de latência.</span><span class="sxs-lookup"><span data-stu-id="dc843-114">Make sure that the logreader and distribution agents are running and can match the latency requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc843-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="dc843-115">Explanation</span></span>  
 <span data-ttu-id="dc843-116">A replicação permite habilitar avisos para várias condições.</span><span class="sxs-lookup"><span data-stu-id="dc843-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="dc843-117">Isso inclui exceder uma latência especificada para assinaturas transacionais.</span><span class="sxs-lookup"><span data-stu-id="dc843-117">This includes exceeding a specified latency for transactional subscriptions.</span></span> <span data-ttu-id="dc843-118">Latência é o período entre a confirmação de uma alteração de dados no Publicador e a confirmação da alteração correspondente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="dc843-118">Latency is the period of time that elapses between a data change being committed at the Publisher and the corresponding change being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="dc843-119">Ao habilitar um aviso usando o Replication Monitor ou o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), você especifica um limite que determina quando um aviso é disparado.</span><span class="sxs-lookup"><span data-stu-id="dc843-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="dc843-120">Quando esse limite é atingido ou excedido, um aviso é exibido no Replication Monitor e um evento é gravado no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="dc843-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="dc843-121">Ao atingir um limite, também é possível disparar um alerta do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="dc843-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="dc843-122">Para obter mais informações, consulte [Definir limites e avisos no Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) e [Monitorar a replicação de forma programática](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="dc843-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc843-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="dc843-123">User Action</span></span>  
 <span data-ttu-id="dc843-124">Se uma assinatura exceder um limite de latência, será necessário determinar se há um problema de desempenho no sistema ou se o limite deve ser ajustado.</span><span class="sxs-lookup"><span data-stu-id="dc843-124">If a subscription exceeds a latency threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="dc843-125">Após configurar a replicação, desenvolva uma linha de base de desempenho, a qual permitirá determinar como a replicação se comporta com uma carga de trabalho típica para seus aplicativos e topologia.</span><span class="sxs-lookup"><span data-stu-id="dc843-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="dc843-126">Inclua a latência nessa linha de base de forma que seja possível definir um valor apropriado para o limite.</span><span class="sxs-lookup"><span data-stu-id="dc843-126">Include latency in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="dc843-127">Se o valor do limite for apropriado, mas estiver sendo excedido, será necessário determinar se há algum gargalo no desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="dc843-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="dc843-128">Para obter mais informações sobre como monitorar e solucionar problemas relacionados a desempenho de replicação, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="dc843-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   [<span data-ttu-id="dc843-129">Medir a latência e validar conexões para replicação transacional</span><span class="sxs-lookup"><span data-stu-id="dc843-129">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
-   [<span data-ttu-id="dc843-130">Monitorar o desempenho com o Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="dc843-130">Monitor Performance with Replication Monitor</span></span>](monitor/monitor-performance-with-replication-monitor.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc843-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc843-131">See Also</span></span>  
 [<span data-ttu-id="dc843-132">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="dc843-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
