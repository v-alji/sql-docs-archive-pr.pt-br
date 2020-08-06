---
title: Implementar Trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent]
- SQL Server Agent jobs
- SQL Server Agent jobs, about jobs
- jobs [SQL Server Agent], about jobs
ms.assetid: 69e06724-25c7-4fb3-8a5b-3d4596f21756
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1925b3113db8d7c57ac4344958c0247763cfd1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569009"
---
# <a name="implement-jobs"></a><span data-ttu-id="276e0-102">Implementar trabalhos</span><span class="sxs-lookup"><span data-stu-id="276e0-102">Implement Jobs</span></span>
  <span data-ttu-id="276e0-103">É possível usar trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para automatizar tarefas administrativas de rotina e executá-las recorrentemente, tornando a administração mais eficaz.</span><span class="sxs-lookup"><span data-stu-id="276e0-103">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to automate routine administrative tasks and run them on a recurring basis, making administration more efficient.</span></span>  
  
 <span data-ttu-id="276e0-104">Um trabalho é uma série especificada de operações executadas sequencialmente pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="276e0-104">A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="276e0-105">Um trabalho pode realizar uma ampla gama de atividades, tais como a execução de scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , aplicativos de linha de comando, scripts Microsoft ActiveX, pacotes do Integration Services, comandos e consultas do Analysis Services ou tarefas de replicação.</span><span class="sxs-lookup"><span data-stu-id="276e0-105">A job can perform a wide range of activities, including running [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, command-line applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks.</span></span> <span data-ttu-id="276e0-106">Os trabalhos podem executar tarefas repetitivas ou agendáveis, bem como notificar usuários automaticamente sobre o status do trabalho por meio de alertas, desse modo simplificando bastante a administração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="276e0-106">Jobs can run repetitive tasks or those that can be scheduled, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administration.</span></span>  
  
 <span data-ttu-id="276e0-107">É possível executar um trabalho manualmente ou configurá-lo para executar de acordo com uma agenda ou em resposta a alertas.</span><span class="sxs-lookup"><span data-stu-id="276e0-107">You can run a job manually, or you can configure it to run according to a schedule or in response to alerts.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="276e0-108">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="276e0-108">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="276e0-109">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="276e0-109">**Description**</span></span>|<span data-ttu-id="276e0-110">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="276e0-110">**Topic**</span></span>|  
|<span data-ttu-id="276e0-111">Contém informações sobre como criar trabalhos e atribuir propriedade.</span><span class="sxs-lookup"><span data-stu-id="276e0-111">Contains information about creating jobs and assigning ownership.</span></span>|[<span data-ttu-id="276e0-112">Criar trabalhos</span><span class="sxs-lookup"><span data-stu-id="276e0-112">Create Jobs</span></span>](create-jobs.md)|  
|<span data-ttu-id="276e0-113">Contém informações sobre como organizar trabalhos em categorias.</span><span class="sxs-lookup"><span data-stu-id="276e0-113">Contains information about organizing jobs into categories.</span></span>|[<span data-ttu-id="276e0-114">organizar trabalhos</span><span class="sxs-lookup"><span data-stu-id="276e0-114">Organize Jobs</span></span>](organize-jobs.md)|  
|<span data-ttu-id="276e0-115">Contém informações sobre os diferentes tipos de etapas de trabalho que podem ser criadas e como gerenciá-las.</span><span class="sxs-lookup"><span data-stu-id="276e0-115">Contains information about the different kinds of job steps you can create and how to manage them.</span></span>|[<span data-ttu-id="276e0-116">Gerenciar etapas de trabalho</span><span class="sxs-lookup"><span data-stu-id="276e0-116">Manage Job Steps</span></span>](manage-job-steps.md)|  
|<span data-ttu-id="276e0-117">Contém informações sobre como definir o início e a frequência da execução de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="276e0-117">Contains information about how to define when jobs start running and how often they should run.</span></span>|[<span data-ttu-id="276e0-118">Criar e anexar agendas para trabalhos</span><span class="sxs-lookup"><span data-stu-id="276e0-118">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)|  
|<span data-ttu-id="276e0-119">Contém informações sobre como executar trabalhos manualmente (sem uma agenda).</span><span class="sxs-lookup"><span data-stu-id="276e0-119">Contains information about manually running jobs (without a schedule).</span></span>|[<span data-ttu-id="276e0-120">Executar Trabalhos</span><span class="sxs-lookup"><span data-stu-id="276e0-120">Run Jobs</span></span>](run-jobs.md)|  
|<span data-ttu-id="276e0-121">Contém informações sobre como configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para responder a trabalhos.</span><span class="sxs-lookup"><span data-stu-id="276e0-121">Contains information about how you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to jobs.</span></span> <span data-ttu-id="276e0-122">Por exemplo, você pode configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para notificar administradores quando os trabalhos forem concluídos.</span><span class="sxs-lookup"><span data-stu-id="276e0-122">For example, you can configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to notify administrators when jobs are finished.</span></span>|[<span data-ttu-id="276e0-123">Especificar respostas de trabalho</span><span class="sxs-lookup"><span data-stu-id="276e0-123">Specify Job Responses</span></span>](specify-job-responses.md)|  
|<span data-ttu-id="276e0-124">Contém informações sobre como exibir trabalhos existentes, seu histórico quando executado, e como modificá-los.</span><span class="sxs-lookup"><span data-stu-id="276e0-124">Contains information about how to view existing jobs, their history once executes, and how to modify them.</span></span>|[<span data-ttu-id="276e0-125">Exibir ou modificar trabalhos</span><span class="sxs-lookup"><span data-stu-id="276e0-125">View or Modify Jobs</span></span>](view-or-modify-jobs.md)|  
|<span data-ttu-id="276e0-126">Contém informações sobre como excluir trabalhos.</span><span class="sxs-lookup"><span data-stu-id="276e0-126">Contains information about how to delete jobs.</span></span>|[<span data-ttu-id="276e0-127">excluir trabalhos</span><span class="sxs-lookup"><span data-stu-id="276e0-127">Delete Jobs</span></span>](delete-jobs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="276e0-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="276e0-128">See Also</span></span>  
 [<span data-ttu-id="276e0-129">Implementar a segurança do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="276e0-129">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
