---
title: Propriedades de Trabalho (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.jobproperties.f1
ms.assetid: 807ffd0e-9363-4f8f-9c36-c5d746ad19fd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4d309ba78a21114cf51c48f0a5c5b3b2f7c2500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680789"
---
# <a name="job-properties-management-studio"></a><span data-ttu-id="06548-102">Propriedades do Trabalho (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="06548-102">Job Properties (Management Studio)</span></span>
  <span data-ttu-id="06548-103">Use a página **Propriedades do Trabalho** para exibir informações sobre um relatório ou uma assinatura em andamento antes de serem cancelados.</span><span class="sxs-lookup"><span data-stu-id="06548-103">Use the **Job Properties** page to view information about an in-progress report or subscription before you cancel it.</span></span>  
  
 <span data-ttu-id="06548-104">Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a um servidor de relatórios e abra a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="06548-104">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, and open the **Jobs** folder.</span></span> <span data-ttu-id="06548-105">Clique com o botão direito do mouse em um trabalho em execução e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="06548-105">Right-click a job that is running, and then click **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="06548-106">Esse recurso não tem suporte no [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] com Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="06548-106">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="06548-107">A página não será exibida enquanto você estiver executando o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06548-107">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="06548-108">Tarefas</span><span class="sxs-lookup"><span data-stu-id="06548-108">Tasks</span></span>  
 <span data-ttu-id="06548-109">Antes de exibir informações sobre um trabalho, atualize a página para recuperar informações sobre trabalhos atualmente em execução no servidor de relatórios:</span><span class="sxs-lookup"><span data-stu-id="06548-109">Before you can view information about a job, refresh the page to retrieve information about jobs that are currently running on the report server:</span></span>  
  
1.  <span data-ttu-id="06548-110">Abra a pasta do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="06548-110">Open the report server folder.</span></span>  
  
2.  <span data-ttu-id="06548-111">Clique com o botão direito do mouse em **Trabalhos**e clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="06548-111">Right-click **Jobs**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="06548-112">Se um trabalho estiver listado, clique com o botão direito do mouse no trabalho e depois clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="06548-112">If a job is listed, right-click the job, and then click **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="06548-113">Opções</span><span class="sxs-lookup"><span data-stu-id="06548-113">Options</span></span>  
 <span data-ttu-id="06548-114">**ID do Trabalho**</span><span class="sxs-lookup"><span data-stu-id="06548-114">**Job ID**</span></span>  
 <span data-ttu-id="06548-115">Um GUID atribuído a um trabalho durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="06548-115">A GUID that is assigned to a job while it is processing.</span></span> <span data-ttu-id="06548-116">O valor é gerado aleatoriamente cada vez que um relatório ou uma assinatura é executado.</span><span class="sxs-lookup"><span data-stu-id="06548-116">The value is randomly generated each time a report or subscription runs.</span></span>  
  
 <span data-ttu-id="06548-117">**Status do Trabalho**</span><span class="sxs-lookup"><span data-stu-id="06548-117">**Job Status**</span></span>  
 <span data-ttu-id="06548-118">Os valores válidos são **Novo** e **Executando**.</span><span class="sxs-lookup"><span data-stu-id="06548-118">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="06548-119">O status é sempre **Novo** quando o trabalho começa.</span><span class="sxs-lookup"><span data-stu-id="06548-119">Status is always **New** when the job begins.</span></span> <span data-ttu-id="06548-120">Depois de 60 segundos, o status é alterado para **Executando**.</span><span class="sxs-lookup"><span data-stu-id="06548-120">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="06548-121">É necessário atualizar a página para que a alteração tenha efeito.</span><span class="sxs-lookup"><span data-stu-id="06548-121">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="06548-122">**Tipo de Trabalho**</span><span class="sxs-lookup"><span data-stu-id="06548-122">**Job Type**</span></span>  
 <span data-ttu-id="06548-123">Os valores válidos são **User** e **System**.</span><span class="sxs-lookup"><span data-stu-id="06548-123">Valid values are **User** and **System**.</span></span> <span data-ttu-id="06548-124">Um trabalho de usuário é qualquer trabalho iniciado por um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="06548-124">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="06548-125">Isso inclui a execução de um relatório sob demanda, a geração manual de um instantâneo de histórico de relatório ou de um instantâneo de execução de relatório.</span><span class="sxs-lookup"><span data-stu-id="06548-125">This includes running a report on-demand, manually generating a report history snapshot, or manually creating a report execution snapshot.</span></span> <span data-ttu-id="06548-126">Uma assinatura padrão em andamento é também um trabalho de usuário.</span><span class="sxs-lookup"><span data-stu-id="06548-126">An in-progress standard subscription is also a user job.</span></span> <span data-ttu-id="06548-127">Um trabalho do sistema é um trabalho iniciado pelo servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="06548-127">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="06548-128">Trabalhos do Sistema incluem processamento de relatório que é disparado por uma agenda.</span><span class="sxs-lookup"><span data-stu-id="06548-128">System jobs include report processing that is triggered by a schedule.</span></span>  
  
 <span data-ttu-id="06548-129">**Ação do Trabalho**</span><span class="sxs-lookup"><span data-stu-id="06548-129">**Job Action**</span></span>  
 <span data-ttu-id="06548-130">Para relatórios, esta coluna mostra quais processos de execução de relatório estão a caminho.</span><span class="sxs-lookup"><span data-stu-id="06548-130">For reports, this column shows which report execution processes are underway.</span></span> <span data-ttu-id="06548-131">Esse valor sempre é **Renderizar**.</span><span class="sxs-lookup"><span data-stu-id="06548-131">This value is always **Render**.</span></span>  
  
 <span data-ttu-id="06548-132">**Descrição do Trabalho**</span><span class="sxs-lookup"><span data-stu-id="06548-132">**Job Description**</span></span>  
 <span data-ttu-id="06548-133">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não fornece descrições de trabalho por padrão.</span><span class="sxs-lookup"><span data-stu-id="06548-133">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide job descriptions by default.</span></span>  
  
 <span data-ttu-id="06548-134">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="06548-134">**Server Name**</span></span>  
 <span data-ttu-id="06548-135">Exibe o nome do servidor de relatórios que está processando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="06548-135">Shows the name of the report server that is processing the job.</span></span> <span data-ttu-id="06548-136">Se você configurou uma implantação em expansão, esse valor mostrará qual servidor está processando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="06548-136">If you configured a scale-out deployment, this value will show which server is processing the job.</span></span>  
  
 <span data-ttu-id="06548-137">**Nome do Relatório**</span><span class="sxs-lookup"><span data-stu-id="06548-137">**Report Name**</span></span>  
 <span data-ttu-id="06548-138">Exibe o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="06548-138">Shows the name of the report.</span></span> <span data-ttu-id="06548-139">As assinaturas são identificadas por suas descrições.</span><span class="sxs-lookup"><span data-stu-id="06548-139">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="06548-140">**Caminho do Relatório**</span><span class="sxs-lookup"><span data-stu-id="06548-140">**Report Path**</span></span>  
 <span data-ttu-id="06548-141">Exibe o caminho do relatório na hierarquia de pastas do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="06548-141">Shows the path of the report in the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="06548-142">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="06548-142">**Start Time**</span></span>  
 <span data-ttu-id="06548-143">Exibe quando o processo foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="06548-143">Shows when the process started.</span></span>  
  
 <span data-ttu-id="06548-144">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="06548-144">**User Name**</span></span>  
 <span data-ttu-id="06548-145">Para processos iniciados por um usuário, essa coluna mostra o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="06548-145">For processes initiated by a user, this column shows the name of the user.</span></span> <span data-ttu-id="06548-146">Para trabalhos do sistema, este é o nome do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="06548-146">For system jobs, this is the name of the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06548-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="06548-147">See Also</span></span>  
 <span data-ttu-id="06548-148">[Servidor de Relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="06548-148">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="06548-149">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="06548-149">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="06548-150">Gerenciar um processo em execução</span><span class="sxs-lookup"><span data-stu-id="06548-150">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
