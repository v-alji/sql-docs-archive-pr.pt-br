---
title: Novo agendamento compartilhado (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newschedule.f1
ms.assetid: b2c69586-d98e-4933-827d-f5e6c15c5203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6afd406730f815d3ab61e59cdebd21d564daa74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571800"
---
# <a name="new-shared-schedule-management-studio"></a><span data-ttu-id="f4fcb-102">Nova Agenda Compartilhada (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f4fcb-102">New Shared Schedule (Management Studio)</span></span>
  <span data-ttu-id="f4fcb-103">Use essa página para criar uma agenda compartilhada para executar relatórios publicados e assinaturas.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-103">Use this page to create a shared schedule to run published reports and subscriptions.</span></span> <span data-ttu-id="f4fcb-104">As agendas compartilhadas podem ser usadas no lugar de agendas específicas de relatório ou de assinaturas.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="f4fcb-105">Informações de agenda centralizadas e a capacidade de pausar e retomar operações de agendamento são dois recursos básicos que distinguem as agendas compartilhadas de agendas específicas de item.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-105">Centralized schedule information and the ability to pause and resume scheduled operations are two key features that distinguish shared schedules from item-specific schedules.</span></span>  
  
 <span data-ttu-id="f4fcb-106">Nem todas as combinações de frequência têm suporte em uma única agenda.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-106">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="f4fcb-107">Por exemplo, se você desejar executar um relatório às 12h00</span><span class="sxs-lookup"><span data-stu-id="f4fcb-107">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="f4fcb-108">e às 16h00</span><span class="sxs-lookup"><span data-stu-id="f4fcb-108">and 4:00 P.M.</span></span> <span data-ttu-id="f4fcb-109">todas as sextas-feiras, você deverá criar duas agendas diárias que especifiquem uma data de execução na sexta-feira, uma com horário de início às 12h00</span><span class="sxs-lookup"><span data-stu-id="f4fcb-109">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="f4fcb-110">e outra com horário de início às 16h00.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-110">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="f4fcb-111">O processamento da agenda se baseia no horário local do servidor de relatório que hospeda e processa a agenda.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-111">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="f4fcb-112">Para abrir essa página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte a um servidor de relatório, clique com o botão direito do mouse em **Agenda Compartilhada**e selecione **Nova Agenda**.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Shared Schedule**, and select **New Schedule**.</span></span> <span data-ttu-id="f4fcb-113">Para salvar a agenda, o serviço SQL Server Agent deve estar em execução.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-113">To save the schedule, SQL Server Agent service must be running.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4fcb-114">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4fcb-114">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f4fcb-115">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], veja [Recursos com suporte nas edições do SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span><span class="sxs-lookup"><span data-stu-id="f4fcb-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f4fcb-116">Opções</span><span class="sxs-lookup"><span data-stu-id="f4fcb-116">Options</span></span>  
 <span data-ttu-id="f4fcb-117">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-117">**Name**</span></span>  
 <span data-ttu-id="f4fcb-118">Digite um nome para a agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-118">Type a name for the shared schedule.</span></span> <span data-ttu-id="f4fcb-119">Esse nome aparece em listas suspensas quando os usuários selecionam uma agenda compartilhada para relatórios e assinaturas.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-119">This name appears in drop-down lists when users select a shared schedule for reports and subscriptions.</span></span> <span data-ttu-id="f4fcb-120">Certifique-se de fornecer um nome descritivo que caiba facilmente dentro de uma lista e que diferencie com facilidade uma agenda compartilhada de outra.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-120">Be sure to provide a descriptive name that fits easily within a list and that easily distinguishes one shared schedule from another.</span></span> <span data-ttu-id="f4fcb-121">Um nome deve conter pelo menos um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="f4fcb-122">Também pode conter espaços e alguns símbolos.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="f4fcb-123">Não use os seguintes caracteres ao especificar um nome:</span><span class="sxs-lookup"><span data-stu-id="f4fcb-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="f4fcb-124">; ?</span><span class="sxs-lookup"><span data-stu-id="f4fcb-124">; ?</span></span> <span data-ttu-id="f4fcb-125">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="f4fcb-125">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="f4fcb-126">" /</span><span class="sxs-lookup"><span data-stu-id="f4fcb-126">" /</span></span>  
  
 <span data-ttu-id="f4fcb-127">**Iniciar a execução desta agenda em**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-127">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="f4fcb-128">Especifique uma data de início para essa agenda.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-128">Specify a start date for this schedule.</span></span>  
  
 <span data-ttu-id="f4fcb-129">**Parar esta agenda em**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-129">**Stop this schedule on**</span></span>  
 <span data-ttu-id="f4fcb-130">Especifique uma data de validade para essa agenda.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-130">Specify an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="f4fcb-131">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-131">**Type**</span></span>  
 <span data-ttu-id="f4fcb-132">Especifica se o padrão de recorrência é baseado principalmente em horas, dias, semanas ou meses.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-132">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, or months.</span></span>  
  
 <span data-ttu-id="f4fcb-133">**Hora (Padrão de Recorrência)**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-133">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="f4fcb-134">Selecione opções para execução de uma operação agendada em intervalos de uma hora (por exemplo, para executar um relatório a cada 6 horas).</span><span class="sxs-lookup"><span data-stu-id="f4fcb-134">Select options to run a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="f4fcb-135">Você pode especificar o intervalo em horas e minutos.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-135">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="f4fcb-136">**Dia (Padrão de Recorrência)**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-136">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="f4fcb-137">Selecione opções para execução de uma operação agendada em intervalos de dias (por exemplo, para executar um relatório a cada 2 dias).</span><span class="sxs-lookup"><span data-stu-id="f4fcb-137">Select options to run a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="f4fcb-138">Você pode especificar o intervalo em dias e na hora e minutos que desejar que a agenda seja executada.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-138">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="f4fcb-139">**Semana (Padrão de Recorrência)**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-139">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="f4fcb-140">Selecione opções para execução de uma operação agendada em intervalos de uma semana ou quando o padrão que você quer repetir é baseado em semanas (por exemplo, para executar um relatório a cada 2 semanas).</span><span class="sxs-lookup"><span data-stu-id="f4fcb-140">Select options to run a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="f4fcb-141">Você pode especificar uma agenda semanal para o dia, hora e minuto que você quer a agenda seja executada.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-141">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="f4fcb-142">**Mês (Padrão de Recorrência)**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-142">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="f4fcb-143">Selecione opções para execução de uma operação agendada em intervalos de um mês ou quando o padrão que você quer repetir é baseado em meses.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-143">Select options to run a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="f4fcb-144">Você pode especificar uma agenda mensal para o dia, hora e minuto que você quer a agenda seja executada.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-144">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="f4fcb-145">Você pode omitir meses específicos da agenda.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-145">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="f4fcb-146">**Uma vez**</span><span class="sxs-lookup"><span data-stu-id="f4fcb-146">**Once**</span></span>  
 <span data-ttu-id="f4fcb-147">Selecione esta opção para criar uma agenda que só executa uma vez, em uma data e hora específica.</span><span class="sxs-lookup"><span data-stu-id="f4fcb-147">Select this option to create a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4fcb-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4fcb-148">See Also</span></span>  
 <span data-ttu-id="f4fcb-149">[Servidor de Relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="f4fcb-149">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="f4fcb-150">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="f4fcb-150">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="f4fcb-151">[Criar, modificar e excluir agendas](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="f4fcb-151">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="f4fcb-152">[Agendas](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="f4fcb-152">[Schedules](../subscriptions/schedules.md) </span></span>  
 [<span data-ttu-id="f4fcb-153">Servidor de Relatório na ajuda F1 do Management Studio</span><span class="sxs-lookup"><span data-stu-id="f4fcb-153">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
