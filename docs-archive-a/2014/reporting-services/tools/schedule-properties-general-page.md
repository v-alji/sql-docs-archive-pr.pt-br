---
title: Propriedades de agendamento (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.general.f1
ms.assetid: 20e43966-6caf-4972-a2e2-0d9131ac8f51
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a61837cd977526021be948d8c74a93eba6506e67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572370"
---
# <a name="schedule-properties-general-page"></a><span data-ttu-id="08923-102">Propriedades da Agenda (página Geral)</span><span class="sxs-lookup"><span data-stu-id="08923-102">Schedule Properties (General Page)</span></span>
  <span data-ttu-id="08923-103">Use essa página para exibir ou modificar uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="08923-103">Use this page to view or modify a shared schedule.</span></span> <span data-ttu-id="08923-104">As agendas compartilhadas podem ser usadas no lugar de agendas específicas de relatório ou de assinaturas.</span><span class="sxs-lookup"><span data-stu-id="08923-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="08923-105">Alterações à agenda são aplicadas depois que você salva a agenda.</span><span class="sxs-lookup"><span data-stu-id="08923-105">Changes to the schedule are applied after you save the schedule.</span></span> <span data-ttu-id="08923-106">A edição de uma agenda não tem nenhum efeito em trabalhos atualmente em andamento.</span><span class="sxs-lookup"><span data-stu-id="08923-106">Editing a schedule has no effect on jobs that are currently in progress.</span></span> <span data-ttu-id="08923-107">Se você editar uma agenda enquanto ela estiver sendo usada, todos os relatórios e assinaturas atualmente em processamento disparados daquela agenda terão permissão para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="08923-107">If you edit a schedule while it is being used, all currently processing reports and subscriptions triggered from that schedule will be allowed to finish.</span></span>  
  
 <span data-ttu-id="08923-108">Nem todas as combinações de frequência têm suporte em uma única agenda.</span><span class="sxs-lookup"><span data-stu-id="08923-108">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="08923-109">Por exemplo, se você desejar executar um relatório às 12h00</span><span class="sxs-lookup"><span data-stu-id="08923-109">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="08923-110">e às 16h00</span><span class="sxs-lookup"><span data-stu-id="08923-110">and 4:00 P.M.</span></span> <span data-ttu-id="08923-111">todas as sextas-feiras, você deverá criar duas agendas diárias que especifiquem uma data de execução na sexta-feira, uma com horário de início às 12h00</span><span class="sxs-lookup"><span data-stu-id="08923-111">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="08923-112">e outra com horário de início às 16h00.</span><span class="sxs-lookup"><span data-stu-id="08923-112">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="08923-113">O processamento da agenda se baseia no horário local do servidor de relatório que hospeda e processa a agenda.</span><span class="sxs-lookup"><span data-stu-id="08923-113">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="08923-114">Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte a um servidor de relatório, abra a pasta **Agendas Compartilhadas** clique com o botão direito do mouse em uma agenda compartilhada e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="08923-114">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08923-115">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e essa página não aparece quando você está executando uma edição que não tem esse recurso.</span><span class="sxs-lookup"><span data-stu-id="08923-115">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and this page does not appear when you are running an edition which does not have this feature.</span></span> <span data-ttu-id="08923-116">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [recursos com suporte nas edições do SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="08923-116">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="08923-117">Opções</span><span class="sxs-lookup"><span data-stu-id="08923-117">Options</span></span>  
 <span data-ttu-id="08923-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="08923-118">**Name**</span></span>  
 <span data-ttu-id="08923-119">Especifica o nome para a agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="08923-119">Specifies the name for the shared schedule.</span></span>  
  
 <span data-ttu-id="08923-120">**Iniciar a execução desta agenda em**</span><span class="sxs-lookup"><span data-stu-id="08923-120">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="08923-121">Especifica uma data de início para essa agenda.</span><span class="sxs-lookup"><span data-stu-id="08923-121">Specifies a start date for this schedule.</span></span>  
  
 <span data-ttu-id="08923-122">**Parar esta agenda em**</span><span class="sxs-lookup"><span data-stu-id="08923-122">**Stop this schedule on**</span></span>  
 <span data-ttu-id="08923-123">Especifica uma data de validade para essa agenda.</span><span class="sxs-lookup"><span data-stu-id="08923-123">Specifies an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="08923-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="08923-124">**Type**</span></span>  
 <span data-ttu-id="08923-125">Especifica se o padrão de recorrência é baseado principalmente em horas, dias, semanas, meses ou só é executado uma vez.</span><span class="sxs-lookup"><span data-stu-id="08923-125">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, months, or only runs once.</span></span>  
  
 <span data-ttu-id="08923-126">**Hora (Padrão de Recorrência)**</span><span class="sxs-lookup"><span data-stu-id="08923-126">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="08923-127">Especifica opções para execução de uma operação agendada em intervalos de uma hora (por exemplo, para executar um relatório a cada 6 horas).</span><span class="sxs-lookup"><span data-stu-id="08923-127">Specifies options for running a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="08923-128">Você pode especificar o intervalo em horas e minutos.</span><span class="sxs-lookup"><span data-stu-id="08923-128">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="08923-129">**Dia (Padrão de Recorrência)**</span><span class="sxs-lookup"><span data-stu-id="08923-129">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="08923-130">Especifica opções para execução de uma operação agendada em intervalos de dias (por exemplo, para executar um relatório a cada 2 dias).</span><span class="sxs-lookup"><span data-stu-id="08923-130">Specifies options for running a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="08923-131">Você pode especificar o intervalo em dias e na hora e minutos que desejar que a agenda seja executada.</span><span class="sxs-lookup"><span data-stu-id="08923-131">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="08923-132">**Semana (Padrão de Recorrência)**</span><span class="sxs-lookup"><span data-stu-id="08923-132">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="08923-133">Especifica opções para execução de uma operação agendada em intervalos de uma semana ou quando o padrão que você quer repetir é baseado em semanas (por exemplo, para executar um relatório a cada 2 semanas).</span><span class="sxs-lookup"><span data-stu-id="08923-133">Specifies options for running a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="08923-134">Você pode especificar uma agenda semanal para o dia, hora e minuto que você quer a agenda seja executada.</span><span class="sxs-lookup"><span data-stu-id="08923-134">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="08923-135">**Mês (Padrão de Recorrência)**</span><span class="sxs-lookup"><span data-stu-id="08923-135">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="08923-136">Especifica opções para execução de uma operação agendada em intervalos de um mês ou quando o padrão que você quer repetir é baseado em meses.</span><span class="sxs-lookup"><span data-stu-id="08923-136">Specifies options for running a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="08923-137">Você pode especificar uma agenda mensal para o dia, hora e minuto que você quer a agenda seja executada.</span><span class="sxs-lookup"><span data-stu-id="08923-137">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="08923-138">Você pode omitir meses específicos da agenda.</span><span class="sxs-lookup"><span data-stu-id="08923-138">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="08923-139">**Uma vez**</span><span class="sxs-lookup"><span data-stu-id="08923-139">**Once**</span></span>  
 <span data-ttu-id="08923-140">Especifica uma agenda que só é executada uma vez, em uma data e hora específica.</span><span class="sxs-lookup"><span data-stu-id="08923-140">Specifies a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08923-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08923-141">See Also</span></span>  
 <span data-ttu-id="08923-142">[Servidor de relatório na ajuda Management Studio F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="08923-142">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="08923-143">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="08923-143">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="08923-144">[Criar, modificar e excluir agendas](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="08923-144">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="08923-145">Agendas</span><span class="sxs-lookup"><span data-stu-id="08923-145">Schedules</span></span>](../subscriptions/schedules.md)  
  
  
