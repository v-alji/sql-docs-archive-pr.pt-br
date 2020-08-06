---
title: Assinatura, Histórico do Distribuidor para o Assinante (assinatura transacional) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.disttosub.f1
ms.assetid: 1aad5b82-592e-4907-92f7-b90794175be5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5cb9d708b75a9414725907530c7454cdba26d135
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685045"
---
# <a name="subscription-distributor-to-subscriber-history-transactional-subscription"></a><span data-ttu-id="d939f-102">Assinatura , Histórico do Distribuidor para o Assinante (assinatura transacional)</span><span class="sxs-lookup"><span data-stu-id="d939f-102">Subscription, Distributor to Subscriber History (Transactional Subscription)</span></span>
  <span data-ttu-id="d939f-103">A guia **Histórico do Distribuidor para o Assinante** exibe informações detalhadas sobre o Distribution Agent, incluindo status, histórico, mensagens informativas e qualquer mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="d939f-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d939f-104">Opções</span><span class="sxs-lookup"><span data-stu-id="d939f-104">Options</span></span>  
 <span data-ttu-id="d939f-105">Selecione as sessões do Distribution Agent a serem exibidas no menu **Exibir** e depois selecione uma sessão específica na grade rotulada **Sessões do Distribution Agent**.</span><span class="sxs-lookup"><span data-stu-id="d939f-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="d939f-106">Informações detalhadas sobre essa sessão são exibidas na grade rotulada **Ações na sessão selecionada**.</span><span class="sxs-lookup"><span data-stu-id="d939f-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="d939f-107">Se a sessão selecionada terminou em erro, a área de texto rotulada **Detalhes ou mensagem de erro da sessão selecionada** também será exibida.</span><span class="sxs-lookup"><span data-stu-id="d939f-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="d939f-108">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="d939f-108">**View**</span></span>  
 <span data-ttu-id="d939f-109">Selecione as sessões do Distribution Agent a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="d939f-109">Select which Distribution Agent sessions to view.</span></span> <span data-ttu-id="d939f-110">O Distribution Agent normalmente é executado continuamente, portanto pode haver somente uma sessão para exibir.</span><span class="sxs-lookup"><span data-stu-id="d939f-110">The Distribution Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="d939f-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="d939f-111">**Status**</span></span>  
 <span data-ttu-id="d939f-112">O status do Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="d939f-112">The status of the Distribution Agent.</span></span> <span data-ttu-id="d939f-113">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="d939f-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="d939f-114">Erro</span><span class="sxs-lookup"><span data-stu-id="d939f-114">Error</span></span>  
  
-   <span data-ttu-id="d939f-115">Concluído</span><span class="sxs-lookup"><span data-stu-id="d939f-115">Completed</span></span>  
  
-   <span data-ttu-id="d939f-116">Tentando novamente</span><span class="sxs-lookup"><span data-stu-id="d939f-116">Retrying</span></span>  
  
-   <span data-ttu-id="d939f-117">Executando</span><span class="sxs-lookup"><span data-stu-id="d939f-117">Running</span></span>  
  
 <span data-ttu-id="d939f-118">**Hora de início**</span><span class="sxs-lookup"><span data-stu-id="d939f-118">**Start Time**</span></span>  
 <span data-ttu-id="d939f-119">A hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="d939f-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="d939f-120">**Hora de término**</span><span class="sxs-lookup"><span data-stu-id="d939f-120">**End Time**</span></span>  
 <span data-ttu-id="d939f-121">A hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="d939f-121">The end time of the session.</span></span> <span data-ttu-id="d939f-122">Se o agente não parou, esse campo estará vazio.</span><span class="sxs-lookup"><span data-stu-id="d939f-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="d939f-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="d939f-123">**Duration**</span></span>  
 <span data-ttu-id="d939f-124">A quantidade de tempo que o Distribution Agent está em execução nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="d939f-124">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="d939f-125">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total da sessão, se a sessão do agente tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="d939f-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="d939f-126">**Mensagem de erro**</span><span class="sxs-lookup"><span data-stu-id="d939f-126">**Error Message**</span></span>  
 <span data-ttu-id="d939f-127">Se uma sessão terminou em um erro, esse campo exibirá a última mensagem de erro registrada pelo Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="d939f-127">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="d939f-128">Se uma sessão não terminou em erro, esse campo ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="d939f-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="d939f-129">**Mensagem de Ação**</span><span class="sxs-lookup"><span data-stu-id="d939f-129">**Action Message**</span></span>  
 <span data-ttu-id="d939f-130">Todas as mensagens informativas e de erro que o Distribution Agent registrou durante a sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d939f-130">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="d939f-131">**Tempo da Ação**</span><span class="sxs-lookup"><span data-stu-id="d939f-131">**Action Time**</span></span>  
 <span data-ttu-id="d939f-132">O tempo no qual a ação descrita na coluna **Mensagem de Ação** foi executada.</span><span class="sxs-lookup"><span data-stu-id="d939f-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="d939f-133">**Detalhes ou mensagem de erro da sessão selecionada**</span><span class="sxs-lookup"><span data-stu-id="d939f-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="d939f-134">Exibido somente se a sessão selecionada exibir um valor de **Erro** na coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="d939f-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="d939f-135">Essa área de texto exibe informações de erro detalhadas e o comando tentado no momento do erro.</span><span class="sxs-lookup"><span data-stu-id="d939f-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="d939f-136">Também inclui links para conteúdo adicional relacionado ao erro.</span><span class="sxs-lookup"><span data-stu-id="d939f-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d939f-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d939f-137">See Also</span></span>  
 <span data-ttu-id="d939f-138">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d939f-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="d939f-139">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d939f-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="d939f-140">[Monitorando a Replicação](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d939f-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="d939f-141">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="d939f-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
