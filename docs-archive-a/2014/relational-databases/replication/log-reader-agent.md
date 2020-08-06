---
title: Agente de Leitor de Log | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.logreaderagent.f1
helpviewer_keywords:
- Log Reader Agent dialog box
ms.assetid: 300a3c46-0e48-4334-99c0-9ee690d2ef4f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2b908e43cf97350fee2913e8cc6bab30a1bcd0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684648"
---
# <a name="log-reader-agent"></a><span data-ttu-id="29fe0-102">Agente de Leitor de Log</span><span class="sxs-lookup"><span data-stu-id="29fe0-102">Log Reader Agent</span></span>
  <span data-ttu-id="29fe0-103">A caixa de diálogo **Log Reader Agent** exibe informações detalhadas sobre o Log Reader Agent, incluindo status, histórico, mensagens informativas e qualquer mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="29fe0-103">The **Log Reader Agent** dialog box displays detailed information on the Log Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29fe0-104">Opções</span><span class="sxs-lookup"><span data-stu-id="29fe0-104">Options</span></span>  
 <span data-ttu-id="29fe0-105">Selecione as sessões do Log Reader Agent a serem exibidas no menu **Exibir** e depois selecione uma sessão específica na grade rotulada **Sessões do Log Reader Agent**.</span><span class="sxs-lookup"><span data-stu-id="29fe0-105">Select which Log Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Log Reader Agent**.</span></span> <span data-ttu-id="29fe0-106">Informações detalhadas sobre essa sessão são exibidas na grade rotulada **Ações na sessão selecionada**.</span><span class="sxs-lookup"><span data-stu-id="29fe0-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="29fe0-107">Se a sessão selecionada terminou em erro, a área de texto rotulada **Detalhes ou mensagem de erro da sessão selecionada** também será exibida.</span><span class="sxs-lookup"><span data-stu-id="29fe0-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="29fe0-108">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="29fe0-108">**View**</span></span>  
 <span data-ttu-id="29fe0-109">Selecione as sessões do Log Reader Agent a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="29fe0-109">Select which Log Reader Agent sessions to view.</span></span> <span data-ttu-id="29fe0-110">O Log Reader Agent normalmente é executado continuamente, portanto pode haver somente uma sessão para exibir.</span><span class="sxs-lookup"><span data-stu-id="29fe0-110">The Log Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="29fe0-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="29fe0-111">**Status**</span></span>  
 <span data-ttu-id="29fe0-112">O status do Log Reader Agent.</span><span class="sxs-lookup"><span data-stu-id="29fe0-112">The status of the Log Reader Agent.</span></span> <span data-ttu-id="29fe0-113">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="29fe0-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="29fe0-114">Erro</span><span class="sxs-lookup"><span data-stu-id="29fe0-114">Error</span></span>  
  
-   <span data-ttu-id="29fe0-115">Tentando novamente comandos com falha</span><span class="sxs-lookup"><span data-stu-id="29fe0-115">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="29fe0-116">Não está sendo executado</span><span class="sxs-lookup"><span data-stu-id="29fe0-116">Not running</span></span>  
  
-   <span data-ttu-id="29fe0-117">Executando</span><span class="sxs-lookup"><span data-stu-id="29fe0-117">Running</span></span>  
  
 <span data-ttu-id="29fe0-118">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="29fe0-118">**Start Time**</span></span>  
 <span data-ttu-id="29fe0-119">A hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="29fe0-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="29fe0-120">**Hora de término**</span><span class="sxs-lookup"><span data-stu-id="29fe0-120">**End Time**</span></span>  
 <span data-ttu-id="29fe0-121">A hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="29fe0-121">The end time of the session.</span></span> <span data-ttu-id="29fe0-122">Se o agente não parou, esse campo estará vazio.</span><span class="sxs-lookup"><span data-stu-id="29fe0-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="29fe0-123">**Duration**</span><span class="sxs-lookup"><span data-stu-id="29fe0-123">**Duration**</span></span>  
 <span data-ttu-id="29fe0-124">A quantidade de tempo que o Log Reader Agent está em execução nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="29fe0-124">The amount of time the Log Reader Agent has run in this session.</span></span> <span data-ttu-id="29fe0-125">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total da sessão, se a sessão do agente tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="29fe0-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="29fe0-126">**Mensagem de erro**</span><span class="sxs-lookup"><span data-stu-id="29fe0-126">**Error Message**</span></span>  
 <span data-ttu-id="29fe0-127">Se uma sessão terminou em um erro, esse campo exibirá a última mensagem de erro registrada pelo Log Reader Agent.</span><span class="sxs-lookup"><span data-stu-id="29fe0-127">If a session ended in an error, this field displays the last error message logged by the Log Reader Agent.</span></span> <span data-ttu-id="29fe0-128">Se uma sessão não terminou em erro, esse campo ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="29fe0-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="29fe0-129">**Mensagem de Ação**</span><span class="sxs-lookup"><span data-stu-id="29fe0-129">**Action Message**</span></span>  
 <span data-ttu-id="29fe0-130">Todas as mensagens informativas e de erro que o Log Reader Agent registrou durante a sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="29fe0-130">All informational messages and error messages that the Log Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="29fe0-131">**Tempo da Ação**</span><span class="sxs-lookup"><span data-stu-id="29fe0-131">**Action Time**</span></span>  
 <span data-ttu-id="29fe0-132">O tempo no qual a ação descrita na coluna **Mensagem de Ação** foi executada.</span><span class="sxs-lookup"><span data-stu-id="29fe0-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="29fe0-133">**Detalhes ou mensagem de erro da sessão selecionada**</span><span class="sxs-lookup"><span data-stu-id="29fe0-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="29fe0-134">Exibido somente se a sessão selecionada exibir um valor de **Erro** na coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="29fe0-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="29fe0-135">Essa área de texto exibe informações de erro detalhadas e o comando tentado no momento do erro.</span><span class="sxs-lookup"><span data-stu-id="29fe0-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="29fe0-136">Também inclui links para conteúdo adicional relacionado ao erro.</span><span class="sxs-lookup"><span data-stu-id="29fe0-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29fe0-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29fe0-137">See Also</span></span>  
 <span data-ttu-id="29fe0-138">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="29fe0-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="29fe0-139">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="29fe0-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="29fe0-140">[Monitorando a Replicação](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="29fe0-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="29fe0-141">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="29fe0-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
