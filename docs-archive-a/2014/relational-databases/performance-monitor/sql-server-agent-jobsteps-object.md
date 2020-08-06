---
title: SQL Server Agent, objeto JobSteps | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- JobSteps object
- SQLAgent:JobSteps
ms.assetid: 44f9983c-1753-4fe0-8475-973aa2460b3a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3759303807714e2bb7f71f59e644bc485d36cfcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571344"
---
# <a name="sql-server-agent-jobsteps-object"></a><span data-ttu-id="9c3e2-102">SQL Server Agent, objeto JobSteps</span><span class="sxs-lookup"><span data-stu-id="9c3e2-102">SQL Server Agent, JobSteps Object</span></span>
  <span data-ttu-id="9c3e2-103">O objeto de desempenho [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] JobSteps **do** Agent contém contadores de desempenho que relatam informações sobre etapas de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="9c3e2-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **JobSteps** performance object contains performance counters that report information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="9c3e2-104">A tabela a seguir lista os contadores contidos nesse objeto.</span><span class="sxs-lookup"><span data-stu-id="9c3e2-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="9c3e2-105">A tabela abaixo contém os contadores de **SQLAgent:JobSteps** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-105">The table below contains the **SQLAgent:JobSteps** counters.</span></span>  
  
|<span data-ttu-id="9c3e2-106">Nome</span><span class="sxs-lookup"><span data-stu-id="9c3e2-106">Name</span></span>|<span data-ttu-id="9c3e2-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="9c3e2-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="9c3e2-108">**Etapas ativas**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-108">**Active steps**</span></span>|<span data-ttu-id="9c3e2-109">Este contador informa o número de etapas de trabalho atualmente em execução.</span><span class="sxs-lookup"><span data-stu-id="9c3e2-109">This counter reports the number of job steps currently running.</span></span>|  
|<span data-ttu-id="9c3e2-110">**Etapas em fila**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-110">**Queued steps**</span></span>|<span data-ttu-id="9c3e2-111">Este contador informa o número de etapas de trabalho que estão prontas para execução pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, mas que ainda não foram iniciadas.</span><span class="sxs-lookup"><span data-stu-id="9c3e2-111">This counter reports the number of job steps that are ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="9c3e2-112">**Total de repetições de etapas**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-112">**Total step retries**</span></span>|<span data-ttu-id="9c3e2-113">Esse contador informa o número total de vezes que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] repetiu uma etapa de trabalho desde a última reinicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="9c3e2-113">This counter reports the total number of times that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has retried a job step since the last server restart.</span></span>|  
  
 <span data-ttu-id="9c3e2-114">Cada contador no objeto contém as seguintes instâncias:</span><span class="sxs-lookup"><span data-stu-id="9c3e2-114">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="9c3e2-115">Instância</span><span class="sxs-lookup"><span data-stu-id="9c3e2-115">Instance</span></span>|<span data-ttu-id="9c3e2-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="9c3e2-116">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="9c3e2-117">**_Total**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-117">**_Total**</span></span>|<span data-ttu-id="9c3e2-118">Informações de todas as etapas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c3e2-118">Information for all job steps.</span></span>|  
|<span data-ttu-id="9c3e2-119">**ActiveScripting**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-119">**ActiveScripting**</span></span>|<span data-ttu-id="9c3e2-120">Informações de etapas de trabalho que usam o subsistema **ActiveScripting** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-120">Information for job steps that use the **ActiveScripting** subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-121">**ANALYSISCOMMAND**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-121">**ANALYSISCOMMAND**</span></span>|<span data-ttu-id="9c3e2-122">Informações de etapas de trabalho que usam o subsistema ANALYSISCOMMAND.</span><span class="sxs-lookup"><span data-stu-id="9c3e2-122">Information for job steps that use the ANALYSISCOMMAND subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-123">**ANALYSISQUERY**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-123">**ANALYSISQUERY**</span></span>|<span data-ttu-id="9c3e2-124">Informações de etapas de trabalho que usam o subsistema ANALYSISQUERY.</span><span class="sxs-lookup"><span data-stu-id="9c3e2-124">Information for job steps that use the ANALYSISQUERY subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-125">**CmdExec**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-125">**CmdExec**</span></span>|<span data-ttu-id="9c3e2-126">Informações de etapas de trabalho que usam o subsistema **CmdExec** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-126">Information for job steps that use the **CmdExec** subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-127">**Distribuição**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-127">**Distribution**</span></span>|<span data-ttu-id="9c3e2-128">Informações de etapas de trabalho que usam o subsistema **Distribution** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-128">Information for job steps that use the **Distribution** subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-129">**Dts**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-129">**Dts**</span></span>|<span data-ttu-id="9c3e2-130">Informações de etapas de trabalho que usam o subsistema [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-130">Information for job steps that use the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-131">**LogReader**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-131">**LogReader**</span></span>|<span data-ttu-id="9c3e2-132">Informações de etapas de trabalho que usam o subsistema **LogReader** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-132">Information for job steps that use the **LogReader** subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-133">**Mesclagem**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-133">**Merge**</span></span>|<span data-ttu-id="9c3e2-134">Informações de etapas de trabalho que usam o subsistema **Merge** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-134">Information for job steps that use the **Merge** subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-135">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-135">**PowerShell**</span></span>|<span data-ttu-id="9c3e2-136">Informações de etapas de trabalho que usam o subsistema **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-136">Information for job steps that use the **PowerShell** subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-137">**QueueReader**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-137">**QueueReader**</span></span>|<span data-ttu-id="9c3e2-138">Informações de etapas de trabalho que usam o subsistema **QueueReader** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-138">Information for job steps that use the **QueueReader** subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-139">**Instantâneo**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-139">**Snapshot**</span></span>|<span data-ttu-id="9c3e2-140">Informações de etapas de trabalho que usam o subsistema **Snapshot** .</span><span class="sxs-lookup"><span data-stu-id="9c3e2-140">Information for job steps that use the **Snapshot** subsystem.</span></span>|  
|<span data-ttu-id="9c3e2-141">**TSQL**</span><span class="sxs-lookup"><span data-stu-id="9c3e2-141">**TSQL**</span></span>|<span data-ttu-id="9c3e2-142">Informações de etapas de trabalho que executam [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c3e2-142">Information for job steps that execute [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c3e2-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c3e2-143">See Also</span></span>  
 <span data-ttu-id="9c3e2-144">[Gerenciar etapas de trabalho](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="9c3e2-144">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 <span data-ttu-id="9c3e2-145">[Usar objetos de desempenho](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="9c3e2-145">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="9c3e2-146">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="9c3e2-146">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
