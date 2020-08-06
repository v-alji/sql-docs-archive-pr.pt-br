---
title: Criar e anexar agendas a trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server]
- scheduling jobs [SQL Server]
- jobs [SQL Server], scheduling
- CPU [SQL Server], idle conditions
- automatic job processing
- SQL Server Agent jobs, scheduling
- idle time [SQL Server]
ms.assetid: 079c2984-0052-4a37-a2b8-4ece56e6b6b5
author: stevestein
ms.author: sstein
ms.openlocfilehash: ced47013b6552725e6350b113a3722b066016a6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680306"
---
# <a name="create-and-attach-schedules-to-jobs"></a><span data-ttu-id="58ea1-102">Criar e anexar agendas para trabalhos</span><span class="sxs-lookup"><span data-stu-id="58ea1-102">Create and Attach Schedules to Jobs</span></span>
  <span data-ttu-id="58ea1-103">Agendar trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent significa definir as condições que fazem com que o trabalho comece a ser executado sem interação com o usuário.</span><span class="sxs-lookup"><span data-stu-id="58ea1-103">Scheduling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs means defining the condition or conditions that cause the job to begin running without user interaction.</span></span> <span data-ttu-id="58ea1-104">Você pode agendar um trabalho para execução automática criando uma nova agenda para ele ou anexando uma agenda existente para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="58ea1-104">You can schedule a job to run automatically by creating a new schedule for the job, or by attaching an existing schedule to the job.</span></span>  
  
 <span data-ttu-id="58ea1-105">Há dois modos de criar um agenda:</span><span class="sxs-lookup"><span data-stu-id="58ea1-105">There are two ways to create a schedule:</span></span>  
  
-   <span data-ttu-id="58ea1-106">Crie a agenda enquanto estiver criando um trabalho.</span><span class="sxs-lookup"><span data-stu-id="58ea1-106">Create the schedule while you are creating a job.</span></span>  
  
-   <span data-ttu-id="58ea1-107">Crie a agenda no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="58ea1-107">Create the schedule in Object Explorer.</span></span>  
  
 <span data-ttu-id="58ea1-108">Após a criação de uma agenda, você pode anexá-la a vários objetos, mesmo que tenha sido criada para um determinado trabalho.</span><span class="sxs-lookup"><span data-stu-id="58ea1-108">After a schedule has been created, you can attach that schedule to multiple jobs, even if the schedule was created for a specific job.</span></span> <span data-ttu-id="58ea1-109">Você também pode desanexar agendas de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="58ea1-109">You can also detach schedules from jobs.</span></span>  
  
 <span data-ttu-id="58ea1-110">Uma agenda pode se basear na hora ou em um evento.</span><span class="sxs-lookup"><span data-stu-id="58ea1-110">A schedule can be based upon time or an event.</span></span> <span data-ttu-id="58ea1-111">Por exemplo, você pode agendar um trabalho para execução nos seguintes horários:</span><span class="sxs-lookup"><span data-stu-id="58ea1-111">For example, you can schedule a job to run at the following times:</span></span>  
  
-   <span data-ttu-id="58ea1-112">Sempre que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent for iniciado.</span><span class="sxs-lookup"><span data-stu-id="58ea1-112">Whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts.</span></span>  
  
-   <span data-ttu-id="58ea1-113">Sempre que a utilização de CPU do computador estiver em um nível definido como ocioso.</span><span class="sxs-lookup"><span data-stu-id="58ea1-113">Whenever CPU utilization of the computer is at a level you have defined as idle.</span></span>  
  
-   <span data-ttu-id="58ea1-114">Apenas uma vez, em data e horário específicos.</span><span class="sxs-lookup"><span data-stu-id="58ea1-114">One time, at a specific date and time.</span></span>  
  
-   <span data-ttu-id="58ea1-115">Em uma agenda recorrente.</span><span class="sxs-lookup"><span data-stu-id="58ea1-115">On a recurring schedule.</span></span>  
  
 <span data-ttu-id="58ea1-116">Como alternativa às agendas de trabalho, também é possível criar um alerta que responda a um evento executando um trabalho.</span><span class="sxs-lookup"><span data-stu-id="58ea1-116">As an alternative to job schedules, you can also create an alert that responds to an event by running a job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58ea1-117">Só uma instância do trabalho pode ser executada de cada vez.</span><span class="sxs-lookup"><span data-stu-id="58ea1-117">Only one instance of the job can be run at a time.</span></span> <span data-ttu-id="58ea1-118">Se você tentar executar um trabalho manualmente enquanto ele estiver sendo executado como agendado, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent recusará a solicitação.</span><span class="sxs-lookup"><span data-stu-id="58ea1-118">If you try to run a job manually while it is running as scheduled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refuses the request.</span></span>  
  
 <span data-ttu-id="58ea1-119">Para impedir a execução de um trabalho agendado, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="58ea1-119">To prevent a scheduled job from running, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="58ea1-120">Desabilite a agenda.</span><span class="sxs-lookup"><span data-stu-id="58ea1-120">Disable the schedule.</span></span>  
  
-   <span data-ttu-id="58ea1-121">Desabilite o trabalho.</span><span class="sxs-lookup"><span data-stu-id="58ea1-121">Disable the job.</span></span>  
  
-   <span data-ttu-id="58ea1-122">Desanexe a agenda do trabalho.</span><span class="sxs-lookup"><span data-stu-id="58ea1-122">Detach the schedule from the job.</span></span>  
  
-   <span data-ttu-id="58ea1-123">Pare o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="58ea1-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
-   <span data-ttu-id="58ea1-124">Exclua a agenda.</span><span class="sxs-lookup"><span data-stu-id="58ea1-124">Delete the schedule.</span></span>  
  
 <span data-ttu-id="58ea1-125">Se a agenda não estiver habilitada, o trabalho poderá ser executado em resposta a um alerta ou manualmente, por um usuário.</span><span class="sxs-lookup"><span data-stu-id="58ea1-125">If the schedule is not enabled, the job can still run in response to an alert or when a user runs the job manually.</span></span> <span data-ttu-id="58ea1-126">Quando uma agenda de trabalho não é habilitada, todos os trabalhos agendados também ficam desabilitados.</span><span class="sxs-lookup"><span data-stu-id="58ea1-126">When a job schedule is not enabled, the schedule is not enabled for any job that uses the schedule.</span></span>  
  
 <span data-ttu-id="58ea1-127">É necessário habilitar novamente explicitamente uma agenda que tenha sido desabilitada.</span><span class="sxs-lookup"><span data-stu-id="58ea1-127">You must explicitly re-enable a schedule that has been disabled.</span></span> <span data-ttu-id="58ea1-128">Editar a agenda não a habilita novamente automaticamente.</span><span class="sxs-lookup"><span data-stu-id="58ea1-128">Editing the schedule does not automatically re-enable the schedule.</span></span>  
  
## <a name="scheduling-start-dates"></a><span data-ttu-id="58ea1-129">Agendando datas de início</span><span class="sxs-lookup"><span data-stu-id="58ea1-129">Scheduling Start Dates</span></span>  
 <span data-ttu-id="58ea1-130">A data de início de uma agenda deve ser maior ou igual a 19900101.</span><span class="sxs-lookup"><span data-stu-id="58ea1-130">The start date of a schedule must be greater than or equal to 19900101.</span></span>  
  
 <span data-ttu-id="58ea1-131">Quando você está anexando uma agenda a um trabalho, deve examinar a data de início que a agenda usa para executar o trabalho pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="58ea1-131">When you are attaching a schedule to a job, you should review the start date that the schedule uses to run the job for the first time.</span></span> <span data-ttu-id="58ea1-132">A data de início depende do dia e da hora em que você anexa a agenda ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="58ea1-132">The start date depends upon the day and time when you attach the schedule to the job.</span></span> <span data-ttu-id="58ea1-133">Por exemplo, você cria uma agenda executada de 15 em 15 dias, às segundas-feiras às 8:00.</span><span class="sxs-lookup"><span data-stu-id="58ea1-133">For example, you create a schedule that runs every other Monday at 8:00 A.M.</span></span> <span data-ttu-id="58ea1-134">Se você criar um trabalho às 10h</span><span class="sxs-lookup"><span data-stu-id="58ea1-134">If you create a job at 10:00 A.M.</span></span> <span data-ttu-id="58ea1-135">na segunda-feira, 3 de março de 2008, a data de início da agenda será Segunda-feira, 17 de março de 2008.</span><span class="sxs-lookup"><span data-stu-id="58ea1-135">on Monday, March 3, 2008, the schedule start date is Monday, March 17, 2008.</span></span> <span data-ttu-id="58ea1-136">Se você criar outro trabalho na terça-feira, 4 de março de 2008, a data de início da agenda será segunda-feira,10 de março de 2008.</span><span class="sxs-lookup"><span data-stu-id="58ea1-136">If you create another job on Tuesday, March 4, 2008, the schedule start date is Monday, March 10, 2008.</span></span>  
  
 <span data-ttu-id="58ea1-137">Você pode alterar a data de início de agenda após anexá-la a um trabalho.</span><span class="sxs-lookup"><span data-stu-id="58ea1-137">You can change the schedule start date after you attach the schedule to a job.</span></span>  
  
## <a name="cpu-idle-schedules"></a><span data-ttu-id="58ea1-138">Agendas de ociosidade de CPU</span><span class="sxs-lookup"><span data-stu-id="58ea1-138">CPU Idle Schedules</span></span>  
 <span data-ttu-id="58ea1-139">Para maximizar os recursos da CPU, você pode definir uma condição de ociosidade de CPU para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="58ea1-139">To maximize CPU resources, you can define a CPU idle condition for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="58ea1-140">O Agent usa a configuração de condição de ociosidade de CPU para determinar o melhor momento para executar trabalhos.</span><span class="sxs-lookup"><span data-stu-id="58ea1-140">Agent uses the CPU idle condition setting to determine the best time to run jobs.</span></span> <span data-ttu-id="58ea1-141">Por exemplo, você pode agendar um trabalho para recriar índices durante o tempo ocioso de CPU e períodos de produção lentos.</span><span class="sxs-lookup"><span data-stu-id="58ea1-141">For example, you can schedule a job to rebuild indexes during CPU idle time and slow production periods.</span></span>  
  
 <span data-ttu-id="58ea1-142">Antes de definir trabalhos para execução durante o tempo ocioso de CPU, determine a carga na CPU durante o processamento normal.</span><span class="sxs-lookup"><span data-stu-id="58ea1-142">Before you define jobs to run during CPU idle time, determine the load on the CPU during normal processing.</span></span> <span data-ttu-id="58ea1-143">Para tanto, use o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou o Monitor de Desempenho para monitorar o tráfego de servidor e coletar estatísticas.</span><span class="sxs-lookup"><span data-stu-id="58ea1-143">To do this, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor server traffic and collect statistics.</span></span> <span data-ttu-id="58ea1-144">Assim, você poderá usar as informações recolhidas para definir a porcentagem e a duração do tempo ocioso de CPU.</span><span class="sxs-lookup"><span data-stu-id="58ea1-144">You can then use the information you gather to set the CPU idle time percentage and duration.</span></span>  
  
 <span data-ttu-id="58ea1-145">Defina a condição de ociosidade de CPU na forma de uma porcentagem abaixo da qual deve permanecer o uso de CPU por um tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="58ea1-145">Define the CPU idle condition as a percentage below which CPU usage must remain for a specified time.</span></span> <span data-ttu-id="58ea1-146">Em seguida, defina o intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="58ea1-146">Next, set the amount of time.</span></span> <span data-ttu-id="58ea1-147">Quando o uso de CPU se encontrar abaixo da porcentagem especificada pelo intervalo de tempo especificado, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent iniciará todos os trabalhos que têm uma agenda de tempo ocioso de CPU.</span><span class="sxs-lookup"><span data-stu-id="58ea1-147">When the CPU usage is below the specified percentage for the specified amount of time, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent starts all jobs that have a CPU idle time schedule.</span></span> <span data-ttu-id="58ea1-148">Para obter mais informações sobre como usar o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou o monitor de desempenho para monitorar o uso da CPU, consulte [monitorar o uso da CPU](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span><span class="sxs-lookup"><span data-stu-id="58ea1-148">For more information on using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor to monitor CPU usage, see [Monitor CPU Usage](../../relational-databases/performance-monitor/monitor-cpu-usage.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="58ea1-149">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="58ea1-149">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58ea1-150">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="58ea1-150">**Description**</span></span>|<span data-ttu-id="58ea1-151">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="58ea1-151">**Topic**</span></span>|  
|<span data-ttu-id="58ea1-152">Descreve como criar uma agenda para um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="58ea1-152">Describes how to create a schedule for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="58ea1-153">Criar uma agenda</span><span class="sxs-lookup"><span data-stu-id="58ea1-153">Create a Schedule</span></span>](create-a-schedule.md)|  
|<span data-ttu-id="58ea1-154">Descreve como agendar um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="58ea1-154">Describes how to schedule a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="58ea1-155">Agendar um trabalho</span><span class="sxs-lookup"><span data-stu-id="58ea1-155">Schedule a Job</span></span>](schedule-a-job.md)|  
|<span data-ttu-id="58ea1-156">Explica como definir a condição de ociosidade de CPU para seu servidor.</span><span class="sxs-lookup"><span data-stu-id="58ea1-156">Explains how to define the CPU idle condition for your server.</span></span>|[<span data-ttu-id="58ea1-157">Definir o momento e a duração de ociosidade da CPU &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="58ea1-157">Set CPU Idle Time and Duration &#40;SQL Server Management Studio&#41;</span></span>](set-cpu-idle-time-and-duration-sql-server-management-studio.md)|  
  
## <a name="see-also"></a><span data-ttu-id="58ea1-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58ea1-158">See Also</span></span>  
 <span data-ttu-id="58ea1-159">[&#41;&#40;Transact-SQL de sp_help_jobschedule](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="58ea1-159">[sp_help_jobschedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobschedule-transact-sql) </span></span>  
 [<span data-ttu-id="58ea1-160">dbo.sysJobSchedules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58ea1-160">dbo.sysjobschedules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobschedules-transact-sql)  
  
  
