---
title: Exibir ou modificar trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- jobs [SQL Server Agent], viewing
- modifying jobs
- viewing jobs
- SQL Server Agent jobs, viewing
- SQL Server Agent jobs, modifying
- displaying jobs
ms.assetid: 57f649b8-190c-4304-abd7-7ca5297deab7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d0d731d25c20597be3ac84adfacd8973e4a51cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680266"
---
# <a name="view-or-modify-jobs"></a><span data-ttu-id="a83fa-102">Exibir ou modificar trabalhos</span><span class="sxs-lookup"><span data-stu-id="a83fa-102">View or Modify Jobs</span></span>
  <span data-ttu-id="a83fa-103">Você pode exibir qualquer trabalho criado.</span><span class="sxs-lookup"><span data-stu-id="a83fa-103">You can view any job you have created.</span></span> <span data-ttu-id="a83fa-104">Após executar um trabalho, você também pode exibir seu histórico.</span><span class="sxs-lookup"><span data-stu-id="a83fa-104">After you have run a job, you can also view its history.</span></span> <span data-ttu-id="a83fa-105">Exibir o histórico de um trabalho permite-lhe observar quando o trabalho foi executado, o status do trabalho como um todo e o status de cada etapa do trabalho.</span><span class="sxs-lookup"><span data-stu-id="a83fa-105">Viewing a job's history allows you to see when the job ran, the status of the job as a whole, and the status of each job step in the job.</span></span> <span data-ttu-id="a83fa-106">É possível saber se o trabalho já falhou no passado, quando foi concluído com êxito pela última vez e que saída o trabalho criou a cada execução.</span><span class="sxs-lookup"><span data-stu-id="a83fa-106">You can see whether the job ever failed in the past, when the job last completed successfully, and what output the job created each time the job ran.</span></span> <span data-ttu-id="a83fa-107">Os membros da função de servidor fixa **sysadmin** podem exibir ou modificar qualquer trabalho, independentemente do proprietário.</span><span class="sxs-lookup"><span data-stu-id="a83fa-107">Members of the **sysadmin** fixed server role can view or modify any job, regardless of the owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a83fa-108">Um trabalho deve ter sido executado pelo menos uma vez para haver um histórico de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="a83fa-108">A job must have been executed at least one time for there to be a job history.</span></span> <span data-ttu-id="a83fa-109">Você pode limitar o tamanho total do log de histórico do trabalho, bem com o tamanho por trabalho.</span><span class="sxs-lookup"><span data-stu-id="a83fa-109">You can limit the total size of the job history log and the size per job.</span></span>  
  
 <span data-ttu-id="a83fa-110">Além disso, você também pode modificar um trabalho para atender a novos requisitos.</span><span class="sxs-lookup"><span data-stu-id="a83fa-110">Finally, you can modify a job to meet new requirements.</span></span> <span data-ttu-id="a83fa-111">É possível modificar:</span><span class="sxs-lookup"><span data-stu-id="a83fa-111">You can modify:</span></span>  
  
-   <span data-ttu-id="a83fa-112">Opções de resposta</span><span class="sxs-lookup"><span data-stu-id="a83fa-112">Response options</span></span>  
  
-   <span data-ttu-id="a83fa-113">Agendas</span><span class="sxs-lookup"><span data-stu-id="a83fa-113">Schedules</span></span>  
  
-   <span data-ttu-id="a83fa-114">Etapas de trabalho</span><span class="sxs-lookup"><span data-stu-id="a83fa-114">Job steps</span></span>  
  
-   <span data-ttu-id="a83fa-115">Propriedade</span><span class="sxs-lookup"><span data-stu-id="a83fa-115">Ownership</span></span>  
  
-   <span data-ttu-id="a83fa-116">Categoria do trabalho</span><span class="sxs-lookup"><span data-stu-id="a83fa-116">Job category</span></span>  
  
-   <span data-ttu-id="a83fa-117">Servidores de destino (somente em trabalhos multisservidor)</span><span class="sxs-lookup"><span data-stu-id="a83fa-117">Target servers (multiserver jobs only)</span></span>  
  
 <span data-ttu-id="a83fa-118">Para assegurar que as alterações em trabalhos multisservidor entrem em vigor, é necessário postá-las na lista de downloads para que os servidores de destino possam baixar o trabalho atualizado.</span><span class="sxs-lookup"><span data-stu-id="a83fa-118">To make sure that changes to multiserver jobs take effect, you must post the changes to the download list so that target servers can download the updated job.</span></span> <span data-ttu-id="a83fa-119">Para garantir que os servidores de destino disponham das definições de trabalho mais atuais, poste uma instrução INSERT após atualizar o trabalho multisservidor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a83fa-119">To ensure that target servers have the most current job definitions, post an INSERT instruction after you update the multiserver job as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="a83fa-120">Para obter mais informações, consulte [sp_purge_jobhistory &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a83fa-120">For more information, see [sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span></span>  
  
 <span data-ttu-id="a83fa-121">Os membros da função de servidor fixa **sysadmin** podem exibir a definição ou o histórico de qualquer trabalho, bem como modificá-los.</span><span class="sxs-lookup"><span data-stu-id="a83fa-121">Members of the **sysadmin** fixed server role can view the definition or history of any job, and can modify any job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a83fa-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a83fa-122">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a83fa-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a83fa-123">**Description**</span></span>|<span data-ttu-id="a83fa-124">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="a83fa-124">**Topic**</span></span>|  
|<span data-ttu-id="a83fa-125">Descreve como exibir trabalhos do [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a83fa-125">Describes how to view [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="a83fa-126">View a Job</span><span class="sxs-lookup"><span data-stu-id="a83fa-126">View a Job</span></span>](view-a-job.md)|  
|<span data-ttu-id="a83fa-127">Descreve como exibir o log de histórico de trabalhos do [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a83fa-127">Describes how to view the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="a83fa-128">View the Job History</span><span class="sxs-lookup"><span data-stu-id="a83fa-128">View the Job History</span></span>](view-the-job-history.md)|  
|<span data-ttu-id="a83fa-129">Descreve como excluir o conteúdo do log de histórico de trabalhos do [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a83fa-129">Describes how to delete the contents of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="a83fa-130">Clear the Job History Log</span><span class="sxs-lookup"><span data-stu-id="a83fa-130">Clear the Job History Log</span></span>](clear-the-job-history-log.md)|  
|<span data-ttu-id="a83fa-131">Descreve como definir limites de tamanho para logs de históricos de trabalhos do [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a83fa-131">Describes how to set size limits for [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history logs.</span></span>|[<span data-ttu-id="a83fa-132">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="a83fa-132">Resize the Job History Log</span></span>](resize-the-job-history-log.md)|  
|<span data-ttu-id="a83fa-133">Descreve como alterar as propriedades de trabalhos do [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a83fa-133">Describes how to change the properties of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="a83fa-134">Modify a Job</span><span class="sxs-lookup"><span data-stu-id="a83fa-134">Modify a Job</span></span>](modify-a-job.md)|  
  
## <a name="see-also"></a><span data-ttu-id="a83fa-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a83fa-135">See Also</span></span>  
 [<span data-ttu-id="a83fa-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a83fa-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobhistory-transact-sql)  
  
  
