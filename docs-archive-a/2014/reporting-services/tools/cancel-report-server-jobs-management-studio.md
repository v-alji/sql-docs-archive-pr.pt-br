---
title: Cancelar Trabalhos do Servidor de Relatório (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.cancelreportserverjobs.f1
ms.assetid: 1c5b4975-49e9-4d0b-b298-2638e81edbfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0ef8ada32aab4ac368871da711d0fe63fff7620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684057"
---
# <a name="cancel-report-server-jobs-management-studio"></a><span data-ttu-id="c6e11-102">Cancelar Trabalhos do Servidor de Relatório (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c6e11-102">Cancel Report Server Jobs (Management Studio)</span></span>
  <span data-ttu-id="c6e11-103">Use a caixa de diálogo **Cancelar Trabalhos do Servidor de Relatório** para exibir ou cancelar relatórios em andamento.</span><span class="sxs-lookup"><span data-stu-id="c6e11-103">Use the **Cancel Report Server Jobs** dialog box to view or cancel in-progress reports.</span></span> <span data-ttu-id="c6e11-104">Essa caixa de diálogo mostra todos os trabalhos em execução atualmente no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c6e11-104">This dialog box shows all jobs that are currently running on the report server.</span></span> <span data-ttu-id="c6e11-105">Embora você não possa pausar ou reiniciar trabalhos atualmente em processo, pode cancelar todos os trabalhos ou trabalhos individuais se estiverem demorando muito para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="c6e11-105">Although you cannot pause or restart jobs that are currently processing, you can cancel all jobs or individual jobs if they are taking too long to complete.</span></span>  
  
 <span data-ttu-id="c6e11-106">Você pode cancelar trabalhos de usuário e trabalhos do sistema.</span><span class="sxs-lookup"><span data-stu-id="c6e11-106">You can cancel user jobs and system jobs.</span></span>  
  
-   <span data-ttu-id="c6e11-107">Um trabalho de usuário é qualquer trabalho iniciado por um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="c6e11-107">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="c6e11-108">Isso inclui a execução de um relatório sob demanda, a criação manual de um instantâneo de histórico de relatório ou de um instantâneo de execução de relatório.</span><span class="sxs-lookup"><span data-stu-id="c6e11-108">This includes running a report on-demand, manually creating a report history snapshot, or manually creating report execution snapshot.</span></span> <span data-ttu-id="c6e11-109">Uma assinatura padrão em andamento é também um trabalho de usuário.</span><span class="sxs-lookup"><span data-stu-id="c6e11-109">An in-progress standard subscription is also a user job.</span></span>  
  
-   <span data-ttu-id="c6e11-110">Um trabalho do sistema é um trabalho iniciado pelo servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c6e11-110">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="c6e11-111">Trabalhos do sistema incluem processamento de relatório agendado.</span><span class="sxs-lookup"><span data-stu-id="c6e11-111">System jobs include scheduled report processing.</span></span>  
  
 <span data-ttu-id="c6e11-112">Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a um servidor de relatório, clique com o botão direito do mouse em **Trabalhos**e clique em **Cancelar Todos os Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="c6e11-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Jobs**, and then click **Cancel All Jobs**.</span></span> <span data-ttu-id="c6e11-113">Você pode abrir também **Trabalhos**, clicar com o botão direito do mouse em um trabalho em execução no servidor de relatório e selecionar **Cancelar Trabalho(s)** .</span><span class="sxs-lookup"><span data-stu-id="c6e11-113">You can also open **Jobs**, right-click a job that is running on the report server, and select **Cancel Job(s)**.</span></span>  
  
 <span data-ttu-id="c6e11-114">Antes de cancelar um trabalho, você pode exibir suas propriedades para determinar quando o trabalho foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="c6e11-114">Before cancelling a job, you can view its properties to determine when the job started.</span></span> <span data-ttu-id="c6e11-115">Para obter mais informações, consulte [Propriedades do Trabalho &#40;Management Studio&#41;](job-properties-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="c6e11-115">For more information, see [Job Properties &#40;Management Studio&#41;](job-properties-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6e11-116">Esse recurso não tem suporte no [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] com Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="c6e11-116">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="c6e11-117">A página não será exibida enquanto você estiver executando o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6e11-117">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="c6e11-118">Opções</span><span class="sxs-lookup"><span data-stu-id="c6e11-118">Options</span></span>  
 <span data-ttu-id="c6e11-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c6e11-119">**Name**</span></span>  
 <span data-ttu-id="c6e11-120">Exibe o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="c6e11-120">Shows the name of the report.</span></span> <span data-ttu-id="c6e11-121">As assinaturas são identificadas por suas descrições.</span><span class="sxs-lookup"><span data-stu-id="c6e11-121">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="c6e11-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6e11-122">**Type**</span></span>  
 <span data-ttu-id="c6e11-123">Os valores válidos são **User** e **System**.</span><span class="sxs-lookup"><span data-stu-id="c6e11-123">Valid values are **User** and **System**.</span></span>  
  
 <span data-ttu-id="c6e11-124">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="c6e11-124">**Start Time**</span></span>  
 <span data-ttu-id="c6e11-125">Exibe quando o trabalho foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="c6e11-125">Shows when the job started.</span></span>  
  
 <span data-ttu-id="c6e11-126">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="c6e11-126">**User Name**</span></span>  
 <span data-ttu-id="c6e11-127">Para trabalhos iniciados por um usuário, essa coluna exibe o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="c6e11-127">For jobs that are initiated by a user, this column shows the name of the user.</span></span>  
  
 <span data-ttu-id="c6e11-128">**Status**</span><span class="sxs-lookup"><span data-stu-id="c6e11-128">**Status**</span></span>  
 <span data-ttu-id="c6e11-129">Mostra o status atual do trabalho.</span><span class="sxs-lookup"><span data-stu-id="c6e11-129">Shows the status of the job.</span></span> <span data-ttu-id="c6e11-130">Os valores válidos são **Novo** e **Executando**.</span><span class="sxs-lookup"><span data-stu-id="c6e11-130">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="c6e11-131">O status é sempre **Novo** quando o trabalho começa.</span><span class="sxs-lookup"><span data-stu-id="c6e11-131">Status is always **New** when the job begins.</span></span> <span data-ttu-id="c6e11-132">Depois de 60 segundos, o status é alterado para **Executando**.</span><span class="sxs-lookup"><span data-stu-id="c6e11-132">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="c6e11-133">É necessário atualizar a página para que a alteração tenha efeito.</span><span class="sxs-lookup"><span data-stu-id="c6e11-133">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="c6e11-134">**OK**</span><span class="sxs-lookup"><span data-stu-id="c6e11-134">**OK**</span></span>  
 <span data-ttu-id="c6e11-135">Cancele um único trabalho ou vários trabalhos.</span><span class="sxs-lookup"><span data-stu-id="c6e11-135">Cancel a single job or multiple jobs.</span></span> <span data-ttu-id="c6e11-136">Os trabalhos são imediatamente cancelados e não podem ser retomados.</span><span class="sxs-lookup"><span data-stu-id="c6e11-136">The jobs are cancelled immediately and cannot be resumed.</span></span> <span data-ttu-id="c6e11-137">Se você cancelar um trabalho por engano, deverá solicitar o relatório ou a assinatura novamente para iniciar um novo trabalho.</span><span class="sxs-lookup"><span data-stu-id="c6e11-137">If you mistakenly cancel a job, you must request the report or subscription again to start a new job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e11-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6e11-138">See Also</span></span>  
 <span data-ttu-id="c6e11-139">[Servidor de Relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="c6e11-139">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="c6e11-140">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="c6e11-140">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="c6e11-141">Gerenciar um processo em execução</span><span class="sxs-lookup"><span data-stu-id="c6e11-141">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
