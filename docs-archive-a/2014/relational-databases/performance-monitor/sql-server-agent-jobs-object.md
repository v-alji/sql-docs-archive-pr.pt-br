---
title: SQL Server Agent, objeto Trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLAgent:Jobs
- Jobs object
ms.assetid: 225b5e2d-4a78-4178-b2b6-b419df83c4aa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 82ee57eba20d44c08eadc125e9dfd69e73c35751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571345"
---
# <a name="sql-server-agent-jobs-object"></a><span data-ttu-id="65755-102">SQL Server Agent, objeto Jobs</span><span class="sxs-lookup"><span data-stu-id="65755-102">SQL Server Agent, Jobs Object</span></span>
  <span data-ttu-id="65755-103">O objeto de desempenho **Jobs** do SQL Server Agent contém contadores de desempenho que relatam informações sobre trabalhos do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="65755-103">The SQL Server Agent **Jobs** performance object contains performance counters that report information about SQL Server Agent jobs.</span></span> <span data-ttu-id="65755-104">A tabela a seguir lista os contadores contidos nesse objeto.</span><span class="sxs-lookup"><span data-stu-id="65755-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="65755-105">A tabela abaixo contém os contadores **SQLAgent:Jobs** .</span><span class="sxs-lookup"><span data-stu-id="65755-105">The table below contains the **SQLAgent:Jobs** counters.</span></span>  
  
|<span data-ttu-id="65755-106">Nome</span><span class="sxs-lookup"><span data-stu-id="65755-106">Name</span></span>|<span data-ttu-id="65755-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="65755-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="65755-108">**Trabalhos Ativos**</span><span class="sxs-lookup"><span data-stu-id="65755-108">**Active Jobs**</span></span>|<span data-ttu-id="65755-109">Este contador informa o número de trabalhos atualmente em execução.</span><span class="sxs-lookup"><span data-stu-id="65755-109">This counter reports the number of jobs currently running.</span></span>|  
|<span data-ttu-id="65755-110">**Trabalhos com falha**</span><span class="sxs-lookup"><span data-stu-id="65755-110">**Failed jobs**</span></span>|<span data-ttu-id="65755-111">Este contador informa o número de trabalhos que falharam.</span><span class="sxs-lookup"><span data-stu-id="65755-111">This counter reports the number of jobs that exited with failure.</span></span>|  
|<span data-ttu-id="65755-112">**Taxa de êxito de trabalhos**</span><span class="sxs-lookup"><span data-stu-id="65755-112">**Job success rate**</span></span>|<span data-ttu-id="65755-113">Este contador informa a porcentagem de trabalhos executados que foram concluídos com êxito.</span><span class="sxs-lookup"><span data-stu-id="65755-113">This counter reports the percentage of executed jobs that completed successfully.</span></span>|  
|<span data-ttu-id="65755-114">**Trabalhos ativados/minuto**</span><span class="sxs-lookup"><span data-stu-id="65755-114">**Jobs activated/minute**</span></span>|<span data-ttu-id="65755-115">Este contador informa o número de trabalhos iniciados no último minuto.</span><span class="sxs-lookup"><span data-stu-id="65755-115">This counter reports the number of jobs launched within the last minute.</span></span>|  
|<span data-ttu-id="65755-116">**Trabalhos em fila**</span><span class="sxs-lookup"><span data-stu-id="65755-116">**Queued jobs**</span></span>|<span data-ttu-id="65755-117">Este contador informa o número de trabalhos prontos para execução pelo SQL Server Agent, mas que ainda não foram iniciados.</span><span class="sxs-lookup"><span data-stu-id="65755-117">This counter reports the number of jobs that are ready for SQL Server Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="65755-118">**Trabalhos bem-sucedidos**</span><span class="sxs-lookup"><span data-stu-id="65755-118">**Successful jobs**</span></span>|<span data-ttu-id="65755-119">Este contador informa o número de trabalhos que obtiveram êxito.</span><span class="sxs-lookup"><span data-stu-id="65755-119">This counter reports the number of jobs that exited with success.</span></span>|  
  
 <span data-ttu-id="65755-120">Cada contador no objeto contém as seguintes instâncias:</span><span class="sxs-lookup"><span data-stu-id="65755-120">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="65755-121">Instância</span><span class="sxs-lookup"><span data-stu-id="65755-121">Instance</span></span>|<span data-ttu-id="65755-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="65755-122">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="65755-123">**_Total**</span><span class="sxs-lookup"><span data-stu-id="65755-123">**_Total**</span></span>|<span data-ttu-id="65755-124">Informações referentes a todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="65755-124">Information for all jobs.</span></span>|  
|<span data-ttu-id="65755-125">**Alertas**</span><span class="sxs-lookup"><span data-stu-id="65755-125">**Alerts**</span></span>|<span data-ttu-id="65755-126">Informações sobre trabalhos iniciados por alertas.</span><span class="sxs-lookup"><span data-stu-id="65755-126">Information for jobs started by alerts.</span></span>|  
|<span data-ttu-id="65755-127">**Others**</span><span class="sxs-lookup"><span data-stu-id="65755-127">**Others**</span></span>|<span data-ttu-id="65755-128">Informações sobre trabalhos que não foram iniciados nem por alertas, nem por agendas.</span><span class="sxs-lookup"><span data-stu-id="65755-128">Information for jobs that were not started by alerts or schedules.</span></span> <span data-ttu-id="65755-129">Normalmente, trata-se de trabalhos iniciados manualmente usando **sp_start_job**.</span><span class="sxs-lookup"><span data-stu-id="65755-129">Typically these are jobs started manually using **sp_start_job**.</span></span>|  
|<span data-ttu-id="65755-130">**Agendas**</span><span class="sxs-lookup"><span data-stu-id="65755-130">**Schedules**</span></span>|<span data-ttu-id="65755-131">Informações sobre trabalhos iniciados por agendas.</span><span class="sxs-lookup"><span data-stu-id="65755-131">Information for jobs started by schedules.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65755-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65755-132">See Also</span></span>  
 <span data-ttu-id="65755-133">[Implementar trabalhos](../../ssms/agent/implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="65755-133">[Implement Jobs](../../ssms/agent/implement-jobs.md) </span></span>  
 <span data-ttu-id="65755-134">[Usar objetos de desempenho](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="65755-134">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="65755-135">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="65755-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
