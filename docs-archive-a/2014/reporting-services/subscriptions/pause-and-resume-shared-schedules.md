---
title: Pausar e retomar agendamentos compartilhados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- report-specific schedules [Reporting Services]
- shared schedules [Reporting Services], resuming
- resuming schedules
- continuing schedules
- schedules [Reporting Services], resuming
- schedules [Reporting Services], pausing
ms.assetid: e416be75-5234-4aa6-a3de-77f60f25169a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f525a15b07b79b5c0d37f9a88ed9483b351af326
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574466"
---
# <a name="pause-and-resume-shared-schedules"></a><span data-ttu-id="c09d4-102">Pause and Resume Shared Schedules</span><span class="sxs-lookup"><span data-stu-id="c09d4-102">Pause and Resume Shared Schedules</span></span>
  <span data-ttu-id="c09d4-103">Você pode pausar e retomar uma agenda compartilhada em uso.</span><span class="sxs-lookup"><span data-stu-id="c09d4-103">You can pause and resume a shared schedule that is in use.</span></span> <span data-ttu-id="c09d4-104">Pausar uma agenda compartilhada é uma maneira de congelar temporariamente uma agenda usada para disparar o processamento de relatórios e assinaturas.</span><span class="sxs-lookup"><span data-stu-id="c09d4-104">Pausing a shared schedule provides a way to temporarily freeze a schedule that is used to trigger report processing and subscriptions.</span></span> <span data-ttu-id="c09d4-105">Somente agendas compartilhadas podem ser pausadas e reiniciadas.</span><span class="sxs-lookup"><span data-stu-id="c09d4-105">Only shared schedules can be paused and resumed.</span></span> <span data-ttu-id="c09d4-106">Não é possível pausar agendas específicas a relatórios.</span><span class="sxs-lookup"><span data-stu-id="c09d4-106">You cannot pause report-specific schedules.</span></span>  
  
 <span data-ttu-id="c09d4-107">Não é possível pausar e retomar o processamento de um relatório em andamento.</span><span class="sxs-lookup"><span data-stu-id="c09d4-107">You cannot pause and resume report processing that is in progress.</span></span> <span data-ttu-id="c09d4-108">Você só pode pausar e retomar agendamentos que estejam na fila de agendamento do serviço SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="c09d4-108">You can only pause and resume schedules that are in the scheduling queue of SQL Server Agent service.</span></span> <span data-ttu-id="c09d4-109">Um trabalho em andamento está fora do escopo do mecanismo de agendamento.</span><span class="sxs-lookup"><span data-stu-id="c09d4-109">A job that is in progress is outside the scope of the scheduling engine.</span></span> <span data-ttu-id="c09d4-110">Para obter mais informações, consulte [Gerenciar um processo em execução](manage-a-running-process.md)</span><span class="sxs-lookup"><span data-stu-id="c09d4-110">For more information, see [Manage a Running Process](manage-a-running-process.md)</span></span>  
  
 <span data-ttu-id="c09d4-111">Enquanto uma agenda compartilhada estiver pausada, todas as operações que teriam ocorrido são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="c09d4-111">While a shared schedule is paused, any operations that would have occurred are allowed to lapse.</span></span> <span data-ttu-id="c09d4-112">Ao permitir que uma agenda compartilhada continue, o processamento de relatórios e assinaturas ocorrerá no próximo horário agendado, usando o horário local do servidor.</span><span class="sxs-lookup"><span data-stu-id="c09d4-112">After you resume a shared schedule, report and subscription processing occurs at the next scheduled time, using the local time of the server.</span></span> <span data-ttu-id="c09d4-113">O servidor de relatórios do modo nativo ou aplicativos de serviço do SharePoint não compensa pelas operações agendadas que teriam ocorrido se o agendamento não tivesse sido pausado.</span><span class="sxs-lookup"><span data-stu-id="c09d4-113">The native mode report server or SharePoint service applications, do not make up scheduled operations that would have occurred had the schedule not been paused.</span></span>  
  
 <span data-ttu-id="c09d4-114">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="c09d4-114">In this Topic:</span></span>  
  
-   [<span data-ttu-id="c09d4-115">Pausar e retomar agendas compartilhadas (modo Nativo)</span><span class="sxs-lookup"><span data-stu-id="c09d4-115">Pause and Resume Shared Schedules (Native Mode)</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="c09d4-116">Pausar e retomar agendas compartilhadas (modo SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c09d4-116">Pause and Resume Shared Schedules (SharePoint mode)</span></span>](#bkmk_sharepoint)  
  
##  <a name="pause-and-resume-shared-schedules-native-mode"></a><a name="bkmk_native"></a> <span data-ttu-id="c09d4-117">Pausar e retomar agendas compartilhadas (modo Nativo)</span><span class="sxs-lookup"><span data-stu-id="c09d4-117">Pause and Resume Shared Schedules (Native Mode)</span></span>  
 <span data-ttu-id="c09d4-118">Para pausar e retomar uma agenda compartilhada, use a página Agendas no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="c09d4-118">To pause and resume a shared schedule, use the Schedules page in Report Manager.</span></span> <span data-ttu-id="c09d4-119">Não é possível usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]; ele não oferece opções para pausar e retomar agendas.</span><span class="sxs-lookup"><span data-stu-id="c09d4-119">You cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]; it does not provide options for pausing and resuming schedules.</span></span> <span data-ttu-id="c09d4-120">Para obter mais informações, consulte [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="c09d4-120">For more information, see [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="c09d4-121">Para pausar ou retomar uma agenda compartilhada</span><span class="sxs-lookup"><span data-stu-id="c09d4-121">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="c09d4-122">No Gerenciador de Relatórios, clique em **Configurações do Site**.</span><span class="sxs-lookup"><span data-stu-id="c09d4-122">From Report Manager Click, **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="c09d4-123">Clique em **Agendas**.</span><span class="sxs-lookup"><span data-stu-id="c09d4-123">Click **Schedules**.</span></span>  
  
3.  <span data-ttu-id="c09d4-124">Selecione a agenda e clique em **Pausar** ou em **Retomar** na faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="c09d4-124">Select the schedule, and click **Pause** or **Resume** in the ribbon.</span></span> <span data-ttu-id="c09d4-125">Se uma Agenda estiver pausada, a coluna **Status** conterá **Pausada**.</span><span class="sxs-lookup"><span data-stu-id="c09d4-125">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
##  <a name="pause-and-resume-shared-schedules-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="c09d4-126">Pausar e retomar agendas compartilhadas (modo SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c09d4-126">Pause and Resume Shared Schedules (SharePoint mode)</span></span>  
 <span data-ttu-id="c09d4-127">Para pausar e retomar uma agenda compartilhada, use a página Configurações do Site ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c09d4-127">To pause and resume a shared schedule, use the Site Settings page or PowerShell.</span></span> <span data-ttu-id="c09d4-128">As agendas são gerenciadas por site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c09d4-128">Schedules are managed per SharePoint site.</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="c09d4-129">Para pausar ou retomar uma agenda compartilhada</span><span class="sxs-lookup"><span data-stu-id="c09d4-129">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="c09d4-130">Clique em **Ações do Site**.</span><span class="sxs-lookup"><span data-stu-id="c09d4-130">Click **Site Actions**.</span></span>  
  
2.  <span data-ttu-id="c09d4-131">Clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="c09d4-131">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="c09d4-132">Na seção Reporting Services, clique em **Gerenciar Agendas Compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="c09d4-132">In the Reporting Services section, click **Manage Shared Schedules**.</span></span>  
  
4.  <span data-ttu-id="c09d4-133">Selecione a agenda e clique em **Pausar Agendas Selecionadas** ou **Executar Agendas Selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="c09d4-133">Select the schedule, and click **Pause Selected Schedules** or **Run Selected Schedules**.</span></span> <span data-ttu-id="c09d4-134">Se uma Agenda estiver pausada, a coluna **Status** conterá **Pausada**.</span><span class="sxs-lookup"><span data-stu-id="c09d4-134">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09d4-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c09d4-135">See Also</span></span>  
 <span data-ttu-id="c09d4-136">[Agendas](schedules.md) </span><span class="sxs-lookup"><span data-stu-id="c09d4-136">[Schedules](schedules.md) </span></span>  
 <span data-ttu-id="c09d4-137">[Criar, modificar e excluir agendas](create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="c09d4-137">[Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="c09d4-138">[Alterar as configurações de fuso horário e relógio em um servidor de relatório](change-time-zones-and-clock-settings-on-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="c09d4-138">[Change Time Zones and Clock Settings on a Report Server](change-time-zones-and-clock-settings-on-a-report-server.md) </span></span>  
 [<span data-ttu-id="c09d4-139">Gerenciar um processo em execução</span><span class="sxs-lookup"><span data-stu-id="c09d4-139">Manage a Running Process</span></span>](manage-a-running-process.md)  
  
  
