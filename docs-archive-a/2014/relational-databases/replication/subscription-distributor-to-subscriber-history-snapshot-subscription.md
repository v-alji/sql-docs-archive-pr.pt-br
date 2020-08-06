---
title: Assinatura, Histórico do Distribuidor para o Assinante (assinatura de instantâneo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.snapshot.f1
ms.assetid: d3575964-f287-4bcf-8d2e-f81a33141b25
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fe894e23e7ad7fef9c328334740eff73164130a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685044"
---
# <a name="subscription-distributor-to-subscriber-history-snapshot-subscription"></a><span data-ttu-id="2d3ae-102">Assinatura, Histórico do Distribuidor para o Assinante (assinatura de instantâneo)</span><span class="sxs-lookup"><span data-stu-id="2d3ae-102">Subscription, Distributor to Subscriber History (Snapshot Subscription)</span></span>
  <span data-ttu-id="2d3ae-103">A guia **Histórico do Distribuidor para o Assinante** exibe informações detalhadas sobre o Distribution Agent, incluindo status, histórico, mensagens informativas e qualquer mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d3ae-104">Opções</span><span class="sxs-lookup"><span data-stu-id="2d3ae-104">Options</span></span>  
 <span data-ttu-id="2d3ae-105">Selecione as sessões do Distribution Agent a serem exibidas no menu **Exibir** e depois selecione uma sessão específica na grade rotulada **Sessões do Distribution Agent**.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="2d3ae-106">Informações detalhadas sobre essa sessão são exibidas na grade rotulada **Ações na sessão selecionada**.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="2d3ae-107">Se a sessão selecionada terminou em erro, a área de texto rotulada **Detalhes ou mensagem de erro da sessão selecionada** também será exibida.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="2d3ae-108">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-108">**View**</span></span>  
 <span data-ttu-id="2d3ae-109">Selecione as sessões do Distribution Agent a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-109">Select which Distribution Agent sessions to view.</span></span>  
  
 <span data-ttu-id="2d3ae-110">**Status**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-110">**Status**</span></span>  
 <span data-ttu-id="2d3ae-111">O status do Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-111">The status of the Distribution Agent.</span></span> <span data-ttu-id="2d3ae-112">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="2d3ae-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="2d3ae-113">Erro</span><span class="sxs-lookup"><span data-stu-id="2d3ae-113">Error</span></span>  
  
-   <span data-ttu-id="2d3ae-114">Concluído</span><span class="sxs-lookup"><span data-stu-id="2d3ae-114">Completed</span></span>  
  
-   <span data-ttu-id="2d3ae-115">Tentando novamente</span><span class="sxs-lookup"><span data-stu-id="2d3ae-115">Retrying</span></span>  
  
-   <span data-ttu-id="2d3ae-116">Executando</span><span class="sxs-lookup"><span data-stu-id="2d3ae-116">Running</span></span>  
  
 <span data-ttu-id="2d3ae-117">**Hora de início**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-117">**Start Time**</span></span>  
 <span data-ttu-id="2d3ae-118">A hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="2d3ae-119">**Hora de término**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-119">**End Time**</span></span>  
 <span data-ttu-id="2d3ae-120">A hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-120">The end time of the session.</span></span> <span data-ttu-id="2d3ae-121">Se o agente não parou, esse campo estará vazio.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="2d3ae-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-122">**Duration**</span></span>  
 <span data-ttu-id="2d3ae-123">A quantidade de tempo que o Distribution Agent está em execução nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-123">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="2d3ae-124">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total da sessão, se a sessão do agente tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session had ended.</span></span>  
  
 <span data-ttu-id="2d3ae-125">**Mensagem de erro**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-125">**Error Message**</span></span>  
 <span data-ttu-id="2d3ae-126">Se uma sessão terminou em um erro, esse campo exibirá a última mensagem de erro registrada pelo Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-126">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="2d3ae-127">Se uma sessão não terminou em erro, esse campo ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="2d3ae-128">**Mensagem de Ação**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-128">**Action Message**</span></span>  
 <span data-ttu-id="2d3ae-129">Todas as mensagens informativas e de erro que o Distribution Agent registrou durante a sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-129">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="2d3ae-130">**Tempo da Ação**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-130">**Action Time**</span></span>  
 <span data-ttu-id="2d3ae-131">O tempo no qual a ação descrita na coluna **Mensagem de Ação** foi executada.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="2d3ae-132">**Detalhes ou mensagem de erro da sessão selecionada**</span><span class="sxs-lookup"><span data-stu-id="2d3ae-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="2d3ae-133">Exibido somente se a sessão selecionada exibir um valor de **Erro** na coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="2d3ae-133">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="2d3ae-134">Essa área de texto exibe informações de erro detalhadas e o comando tentado no momento do erro.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="2d3ae-135">Também inclui links para conteúdo adicional relacionado ao erro.</span><span class="sxs-lookup"><span data-stu-id="2d3ae-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3ae-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d3ae-136">See Also</span></span>  
 <span data-ttu-id="2d3ae-137">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="2d3ae-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="2d3ae-138">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="2d3ae-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="2d3ae-139">[Monitorando a Replicação](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="2d3ae-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="2d3ae-140">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="2d3ae-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
