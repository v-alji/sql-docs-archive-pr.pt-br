---
title: Monitorar a Atividade de Trabalho | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- jobs [SQL Server Agent], monitoring
- monitoring [SQL Server], jobs
- activity monitoring [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- SQL Server Agent Job Activity Monitor
- SQL Server Agent jobs, monitoring
- performance [SQL Server], jobs
- current activity
ms.assetid: 71cb432b-631d-4b8b-9965-e731b3d8266d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5088e029e90b4556c1559f8c948e8a8734762749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572338"
---
# <a name="monitor-job-activity"></a><span data-ttu-id="95ce9-102">Monitorar Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="95ce9-102">Monitor Job Activity</span></span>
  <span data-ttu-id="95ce9-103">É possível monitorar a atividade atual de todos os trabalhos definidos em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Monitor de Atividade do Trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="95ce9-103">You can monitor the current activity of all defined jobs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job Activity Monitor.</span></span>  
  
## <a name="sql-server-agent-sessions"></a><span data-ttu-id="95ce9-104">Sessões do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="95ce9-104">SQL Server Agent Sessions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="95ce9-105">O Agent cria uma nova sessão toda vez que o serviço é iniciado.</span><span class="sxs-lookup"><span data-stu-id="95ce9-105">Agent creates a new session each time the service starts.</span></span> <span data-ttu-id="95ce9-106">Quando uma nova sessão é criada, a tabela **sysjobactivity** do banco de dados **msdb** é preenchida com todos os trabalhos definidos existentes.</span><span class="sxs-lookup"><span data-stu-id="95ce9-106">When a new session is created, the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="95ce9-107">Essa tabela preserva a última atividade dos trabalhos quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é reiniciado.</span><span class="sxs-lookup"><span data-stu-id="95ce9-107">This table preserves the last activity for jobs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is restarted.</span></span> <span data-ttu-id="95ce9-108">Cada sessão registra a atividade normal de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent do começo ao fim do trabalho.</span><span class="sxs-lookup"><span data-stu-id="95ce9-108">Each session records [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent normal job activity from the start of the job to its finish.</span></span> <span data-ttu-id="95ce9-109">Informações sobre essas sessões são armazenadas na tabela **syssessions** do banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="95ce9-109">Information about these sessions is stored in the **syssessions** table of the **msdb** database.</span></span>  
  
## <a name="job-activity-monitor"></a><span data-ttu-id="95ce9-110">Monitor de Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="95ce9-110">Job Activity Monitor</span></span>  
 <span data-ttu-id="95ce9-111">O Monitor de Atividade do Trabalho permite exibir a tabela **sysjobactivity** usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95ce9-111">The Job Activity Monitor allows you to view the **sysjobactivity** table by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="95ce9-112">É possível visualizar todos os trabalhos no servidor ou definir filtros para limitar o número de trabalhos exibidos.</span><span class="sxs-lookup"><span data-stu-id="95ce9-112">You can view all jobs on the server, or you can define filters to limit the number of jobs displayed.</span></span> <span data-ttu-id="95ce9-113">Você também pode classificar as informações do trabalho, clicando no título de uma coluna na grade do **Atividade de Trabalho do Agente** .</span><span class="sxs-lookup"><span data-stu-id="95ce9-113">You can also sort the job information by clicking on a column heading in the **Agent Job Activity** grid.</span></span> <span data-ttu-id="95ce9-114">Por exemplo, selecionando o título de coluna **Última Execução** , é possível exibir os trabalhos na ordem em que foram executados pela última vez.</span><span class="sxs-lookup"><span data-stu-id="95ce9-114">For example, when you select the **Last Run** column heading, you can view the jobs in the order that they were last run.</span></span> <span data-ttu-id="95ce9-115">Clicando novamente no cabeçalho da coluna, os trabalhos são classificados em ordem crescente ou decrescente segundo as datas de suas últimas execuções.</span><span class="sxs-lookup"><span data-stu-id="95ce9-115">Clicking the column heading again toggles the jobs in ascending and descending order based on their last run date.</span></span>  
  
 <span data-ttu-id="95ce9-116">Usando o Monitor de Atividade do Trabalho, você pode executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="95ce9-116">Using the Job Activity Monitor you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="95ce9-117">Iniciar e interromper trabalhos.</span><span class="sxs-lookup"><span data-stu-id="95ce9-117">Start and stop jobs.</span></span>  
  
-   <span data-ttu-id="95ce9-118">Exibir propriedades do trabalho.</span><span class="sxs-lookup"><span data-stu-id="95ce9-118">View job properties.</span></span>  
  
-   <span data-ttu-id="95ce9-119">Exibir o histórico de um trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="95ce9-119">View the history for a specific job.</span></span>  
  
-   <span data-ttu-id="95ce9-120">Atualizar as informações na grade de **Atividade do Trabalho do Agente** manualmente ou definir um intervalo de atualização automática, clicando em **Exibir configurações de atualização**.</span><span class="sxs-lookup"><span data-stu-id="95ce9-120">Refresh the information in the **Agent Job Activity** grid manually or set an automatic refresh interval by clicking **View refresh settings**.</span></span>  
  
 <span data-ttu-id="95ce9-121">Use o Monitor de Atividade do Trabalho quando quiser descobrir quais trabalhos estão agendados para execução, o último resultado de trabalhos executados durante a sessão atual e quais trabalhos estão em execução ou ociosos atualmente.</span><span class="sxs-lookup"><span data-stu-id="95ce9-121">Use the Job Activity Monitor when you want to find out what jobs are scheduled to run, the last outcome of jobs that have run during the current session, and to find out which jobs are currently running or idle.</span></span> <span data-ttu-id="95ce9-122">Se o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent falhar de forma inesperada, você poderá determinar quais trabalhos estavam no meio de sua execução, examinando a sessão anterior no Monitor de Atividade do Trabalho.</span><span class="sxs-lookup"><span data-stu-id="95ce9-122">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service fails unexpectedly, you can determine which jobs were in the middle of being executed by looking at the previous session in the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="95ce9-123">Para abrir o Monitor de Atividade do Trabalho, expanda **SQL Server Agent** no Pesquisador de Objetos do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , clique com o botão direito do mouse em **Monitor de Atividade do Trabalho**e clique em **Exibir Atividade do Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="95ce9-123">To open the Job Activity Monitor, expand **SQL Server Agent** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Object Explorer, right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
 <span data-ttu-id="95ce9-124">Você também pode exibir a atividade de trabalhos da sessão atual, usando o procedimento armazenado **sp_help_jobactivity**.</span><span class="sxs-lookup"><span data-stu-id="95ce9-124">You can also view job activity for the current session by using the stored procedure **sp_help_jobactivity**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="95ce9-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="95ce9-125">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95ce9-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="95ce9-126">**Description**</span></span>|<span data-ttu-id="95ce9-127">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="95ce9-127">**Topic**</span></span>|  
|<span data-ttu-id="95ce9-128">Descreve como exibir o estado de runtime de trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="95ce9-128">Describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="95ce9-129">Exibir Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="95ce9-129">View Job Activity</span></span>](view-job-activity.md)|  
  
## <a name="see-also"></a><span data-ttu-id="95ce9-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95ce9-130">See Also</span></span>  
 <span data-ttu-id="95ce9-131">[Exibir atividade do trabalho](view-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="95ce9-131">[View Job Activity](view-job-activity.md) </span></span>  
 <span data-ttu-id="95ce9-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="95ce9-132">[dbo.sysjobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-sysjobactivity-transact-sql) </span></span>  
 <span data-ttu-id="95ce9-133">[dbo.syssessões &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="95ce9-133">[dbo.syssessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/dbo-syssessions-transact-sql) </span></span>  
 [<span data-ttu-id="95ce9-134">&#41;&#40;Transact-SQL de sp_help_jobactivity</span><span class="sxs-lookup"><span data-stu-id="95ce9-134">sp_help_jobactivity &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql)  
  
  
