---
title: Criar trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], creating
- SQL Server Agent jobs, creating
ms.assetid: 465fb7fc-7622-4252-a178-ea51691c935b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 706b9348eed5b190f99543a74e7019dc1bde5978
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680300"
---
# <a name="create-jobs"></a><span data-ttu-id="32a8f-102">Criar trabalhos</span><span class="sxs-lookup"><span data-stu-id="32a8f-102">Create Jobs</span></span>
  <span data-ttu-id="32a8f-103">Um trabalho é uma série especificada de operações executadas sequencialmente pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="32a8f-103">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="32a8f-104">Um trabalho pode realizar uma ampla gama de atividades, tais como a execução de scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , aplicativos de prompt de comando, scripts Microsoft ActiveX, pacotes do Integration Services, comandos e consultas do Analysis Services ou tarefas de replicação.</span><span class="sxs-lookup"><span data-stu-id="32a8f-104">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command prompt applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="32a8f-105">Os trabalhos podem executar tarefas repetitivas ou agendáveis, bem como notificar usuários automaticamente sobre o status do trabalho, desse modo simplificando bastante a administração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32a8f-105">Jobs can run repetitive or schedulable tasks, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="32a8f-106">Para criar um trabalho, o usuário deve ser membro de uma das funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ou da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="32a8f-106">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="32a8f-107">Um trabalho só pode ser editado por seu proprietário ou por membros da função **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="32a8f-107">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="32a8f-108">Os membros da função **sysadmin** podem atribuir a propriedade do trabalho a outros usuários, bem como executar qualquer trabalho, independentemente de seu proprietário.</span><span class="sxs-lookup"><span data-stu-id="32a8f-108">Members of the **sysadmin** role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span> <span data-ttu-id="32a8f-109">Para obter mais informações sobre as funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consulte [Funções de banco de dados fixas do SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="32a8f-109">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="32a8f-110">Podem ser criados trabalhos para execução na instância local do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou em várias instâncias em toda a empresa.</span><span class="sxs-lookup"><span data-stu-id="32a8f-110">Jobs can be written to run on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or on multiple instances across an enterprise.</span></span> <span data-ttu-id="32a8f-111">Para executar trabalhos em vários servidores, é necessário configurar pelo menos um servidor mestre e um ou mais servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="32a8f-111">To run jobs on multiple servers, you must set up at least one master server and one or more target servers.</span></span> <span data-ttu-id="32a8f-112">Para obter mais informações sobre servidores mestre e de destino, consulte [Administração automatizada em toda a empresa](automated-administration-across-an-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="32a8f-112">For more information about master and target servers, see [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="32a8f-113">O Agent registra as informações do trabalho e suas etapas no histórico de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="32a8f-113">Agent records job and job step information in the job history.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="32a8f-114">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="32a8f-114">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32a8f-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="32a8f-115">**Description**</span></span>|<span data-ttu-id="32a8f-116">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="32a8f-116">**Topic**</span></span>|  
|<span data-ttu-id="32a8f-117">Descreve como criar um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="32a8f-117">Describes how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="32a8f-118">Criar um trabalho</span><span class="sxs-lookup"><span data-stu-id="32a8f-118">Create a Job</span></span>](create-a-job.md)|  
|<span data-ttu-id="32a8f-119">Descreve como reatribuir a propriedade de trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="32a8f-119">Describes how to reassign ownership of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>|[<span data-ttu-id="32a8f-120">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="32a8f-120">Give Others Ownership of a Job</span></span>](give-others-ownership-of-a-job.md)|  
|<span data-ttu-id="32a8f-121">Descreve como configurar o log de histórico de trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="32a8f-121">Describes how to set up the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="32a8f-122">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="32a8f-122">Set Up the Job History Log</span></span>](set-up-the-job-history-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="32a8f-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32a8f-123">See Also</span></span>  
 <span data-ttu-id="32a8f-124">[Gerenciar etapas de trabalho](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="32a8f-124">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="32a8f-125">[Administração automatizada em toda a empresa](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="32a8f-125">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 <span data-ttu-id="32a8f-126">[Criar e anexar agendas a trabalhos](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="32a8f-126">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 <span data-ttu-id="32a8f-127">[Executar trabalhos](run-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="32a8f-127">[Run Jobs](run-jobs.md) </span></span>  
 [<span data-ttu-id="32a8f-128">Exibir ou modificar trabalhos</span><span class="sxs-lookup"><span data-stu-id="32a8f-128">View or Modify Jobs</span></span>](view-or-modify-jobs.md)  
  
  
