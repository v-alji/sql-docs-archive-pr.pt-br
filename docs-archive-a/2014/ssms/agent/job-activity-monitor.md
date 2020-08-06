---
title: Monitor de Atividade do Trabalho | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.ACTIVITYMON.F1
- sql12.ag.jobactivitymonitor.alljobs.f1
ms.assetid: 11f2182c-5f71-46f8-8d2b-74f0fc48f2d6
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6f89d5448f0885c85229c2808ee6f85bf6fa071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680293"
---
# <a name="job-activity-monitor"></a><span data-ttu-id="84513-102">Monitor de Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="84513-102">Job Activity Monitor</span></span>
  <span data-ttu-id="84513-103">Use esta página para exibir a atividade atual de trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="84513-103">Use this page to view the current activity of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> <span data-ttu-id="84513-104">Clique em **Filtrar** para limitar os trabalhos exibidos.</span><span class="sxs-lookup"><span data-stu-id="84513-104">Click **Filter** to limit the jobs displayed.</span></span> <span data-ttu-id="84513-105">A grade **Atividade do Trabalho do Agent** é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="84513-105">The **Agent Job Activity** grid is read-only.</span></span> <span data-ttu-id="84513-106">Clique nos cabeçalhos das coluna para classificar a grade.</span><span class="sxs-lookup"><span data-stu-id="84513-106">Click on the column headers to sort the grid.</span></span> <span data-ttu-id="84513-107">Para modificar um trabalho, clique duas vezes no trabalho para abrir a caixa de diálogo **Propriedades do Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="84513-107">To modify a job, double-click the job to open the **Job Properties** dialog box.</span></span> <span data-ttu-id="84513-108">Clique com o botão direito do mouse em um trabalho na grade para que ele inicie a execução de todas as etapas do trabalho, inicie em uma etapa de trabalho específica, desabilite ou habilite o trabalho, atualize o trabalho, exclua o trabalho, exiba o histórico do trabalho ou exiba suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="84513-108">Right-click a job in the grid to start it running all job steps, start at a particular job step, disable or enable the job, refresh the job, delete the job, view the history of the job, or view the properties of the job.</span></span> <span data-ttu-id="84513-109">Clique em **Atualizar** , para atualizar a grade com informações atuais.</span><span class="sxs-lookup"><span data-stu-id="84513-109">Click **Refresh** to update the grid with current information.</span></span>  
  
## <a name="options"></a><span data-ttu-id="84513-110">Opções</span><span class="sxs-lookup"><span data-stu-id="84513-110">Options</span></span>  
 <span data-ttu-id="84513-111">**Nome**</span><span class="sxs-lookup"><span data-stu-id="84513-111">**Name**</span></span>  
 <span data-ttu-id="84513-112">Nome do trabalho.</span><span class="sxs-lookup"><span data-stu-id="84513-112">Name of the job.</span></span>  
  
 <span data-ttu-id="84513-113">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="84513-113">**Enabled**</span></span>  
 <span data-ttu-id="84513-114">Se o trabalho está habilitado (**sim**) ou desabilitado (**não**).</span><span class="sxs-lookup"><span data-stu-id="84513-114">Whether the job is enabled (**yes**) or not enabled (**no**).</span></span>  
  
 <span data-ttu-id="84513-115">**Status** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="84513-115">**Status** <sup>1</sup></span></span>  
 <span data-ttu-id="84513-116">Status atual do trabalho.</span><span class="sxs-lookup"><span data-stu-id="84513-116">Current status of the job.</span></span>  
  
 <span data-ttu-id="84513-117">**Resultado da Última Execução**</span><span class="sxs-lookup"><span data-stu-id="84513-117">**Last Run Outcome**</span></span>  
 <span data-ttu-id="84513-118">Status do trabalho quando executado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="84513-118">Job status when last run.</span></span>  
  
 <span data-ttu-id="84513-119">**Última Execução**</span><span class="sxs-lookup"><span data-stu-id="84513-119">**Last Run**</span></span>  
 <span data-ttu-id="84513-120">Data e hora em que o trabalho foi executado pela última vez, usando a data e hora locais do servidor.</span><span class="sxs-lookup"><span data-stu-id="84513-120">Date and time job was last run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="84513-121">**Próxima execução** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="84513-121">**Next Run** <sup>1</sup></span></span>  
 <span data-ttu-id="84513-122">Date e hora em que o trabalho está agendado para ser executado usando a data local e hora locais do servidor.</span><span class="sxs-lookup"><span data-stu-id="84513-122">Date and time the job is next scheduled to run using the local date and time of the server.</span></span>  
  
 <span data-ttu-id="84513-123">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="84513-123">**Category**</span></span>  
 <span data-ttu-id="84513-124">A categoria de trabalho atribuída ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="84513-124">The job category assigned to the job.</span></span>  
  
 <span data-ttu-id="84513-125">**Xterm**</span><span class="sxs-lookup"><span data-stu-id="84513-125">**Runnable**</span></span>  
 <span data-ttu-id="84513-126">**Sim** se o trabalho puder ser executado; **Não** se o trabalho não puder ser executado.</span><span class="sxs-lookup"><span data-stu-id="84513-126">**Yes** if the job can be run; **No** if the job cannot be run.</span></span> <span data-ttu-id="84513-127">Um trabalho não é executável se não tiver nenhuma etapa ou se não tiver nenhum servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="84513-127">A job is not runnable if it has no steps or if it has no target server.</span></span>  
  
 <span data-ttu-id="84513-128">**Agendado**</span><span class="sxs-lookup"><span data-stu-id="84513-128">**Scheduled**</span></span>  
 <span data-ttu-id="84513-129">**Sim** se o trabalho estiver atribuído a uma agenda de trabalho; **Não** se o trabalho não tiver nenhuma agenda.</span><span class="sxs-lookup"><span data-stu-id="84513-129">**Yes** if the job is assigned to a job schedule; **No** if the job has no schedule.</span></span>  
  
 <span data-ttu-id="84513-130"><sup>1</sup> Somente os membros da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] função de servidor fixa sysadmin e do grupo de administradores de servidor podem ver os valores nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="84513-130"><sup>1</sup>Only members of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sysadmin fixed server role and the server administrators group can see values in this column.</span></span> <span data-ttu-id="84513-131">Os membros da função SQLAgentOperatorRole não podem ver os valores dessa coluna.</span><span class="sxs-lookup"><span data-stu-id="84513-131">Members of the SQLAgentOperatorRole role cannot see values in this column.</span></span>  
  
#### <a name="to-open-the-job-activity-monitor"></a><span data-ttu-id="84513-132">Para abrir o Monitor de Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="84513-132">To open the Job Activity Monitor</span></span>  
  
-   <span data-ttu-id="84513-133">No **Pesquisador de Objetos**, expanda seu servidor, expanda **SQL Server Agent**, clique com o botão direito do mouse em **Monitor de Atividade do Trabalho**e clique em **Exibir Atividade do Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="84513-133">In **Object Explorer**, expand your server, expand **SQL Server Agent**, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84513-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84513-134">See Also</span></span>  
 [<span data-ttu-id="84513-135">Monitorar Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="84513-135">Monitor Job Activity</span></span>](monitor-job-activity.md)  
  
  
