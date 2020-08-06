---
title: Snapshot Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.snapshotagent.f1
helpviewer_keywords:
- Snapshot Agent dialog box
ms.assetid: b715e621-2cd5-4a15-8f58-a341aa8ef5e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 925f2d3841b5dded6c8504a4a05dc60e61024161
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583487"
---
# <a name="snapshot-agent"></a><span data-ttu-id="13882-102">Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="13882-102">Snapshot Agent</span></span>
  <span data-ttu-id="13882-103">A caixa de diálogo **Snapshot Agent** exibe informações detalhadas sobre o Snapshot Agent, incluindo status, histórico, mensagens informativas e qualquer mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="13882-103">The **Snapshot Agent** dialog box displays detailed information on the Snapshot Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="13882-104">Opções</span><span class="sxs-lookup"><span data-stu-id="13882-104">Options</span></span>  
 <span data-ttu-id="13882-105">Selecione as sessões do Snapshot Agent a serem exibidas no menu **Exibir** e depois selecione uma sessão específica na grade rotulada **Sessões do Snapshot Agent**.</span><span class="sxs-lookup"><span data-stu-id="13882-105">Select which Snapshot Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Snapshot Agent**.</span></span> <span data-ttu-id="13882-106">Informações detalhadas sobre essa sessão são exibidas na grade rotulada **Ações na sessão selecionada**.</span><span class="sxs-lookup"><span data-stu-id="13882-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="13882-107">Se a sessão selecionada terminou em erro, a área de texto rotulada **Detalhes ou mensagem de erro da sessão selecionada** também será exibida.</span><span class="sxs-lookup"><span data-stu-id="13882-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="13882-108">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="13882-108">**View**</span></span>  
 <span data-ttu-id="13882-109">Selecione quais sessões do Snapshot Agent exibir.</span><span class="sxs-lookup"><span data-stu-id="13882-109">Select which Snapshot Agent sessions to view.</span></span>  
  
 <span data-ttu-id="13882-110">**Status**</span><span class="sxs-lookup"><span data-stu-id="13882-110">**Status**</span></span>  
 <span data-ttu-id="13882-111">O status do Snapshot Agent.</span><span class="sxs-lookup"><span data-stu-id="13882-111">The status of the Snapshot Agent.</span></span> <span data-ttu-id="13882-112">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="13882-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="13882-113">Erro</span><span class="sxs-lookup"><span data-stu-id="13882-113">Error</span></span>  
  
-   <span data-ttu-id="13882-114">Tentando novamente comandos com falha</span><span class="sxs-lookup"><span data-stu-id="13882-114">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="13882-115">Não está sendo executado</span><span class="sxs-lookup"><span data-stu-id="13882-115">Not running</span></span>  
  
-   <span data-ttu-id="13882-116">Concluído</span><span class="sxs-lookup"><span data-stu-id="13882-116">Completed</span></span>  
  
 <span data-ttu-id="13882-117">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="13882-117">**Start Time**</span></span>  
 <span data-ttu-id="13882-118">A hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="13882-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="13882-119">**Hora de término**</span><span class="sxs-lookup"><span data-stu-id="13882-119">**End Time**</span></span>  
 <span data-ttu-id="13882-120">A hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="13882-120">The end time of the session.</span></span> <span data-ttu-id="13882-121">Se o agente não parou, esse campo estará vazio.</span><span class="sxs-lookup"><span data-stu-id="13882-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="13882-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="13882-122">**Duration**</span></span>  
 <span data-ttu-id="13882-123">A quantidade de tempo que o Snapshot Agent está em execução nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="13882-123">The amount of time the Snapshot Agent has run in this session.</span></span> <span data-ttu-id="13882-124">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total da sessão, se a sessão do agente tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="13882-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="13882-125">**Mensagem de erro**</span><span class="sxs-lookup"><span data-stu-id="13882-125">**Error Message**</span></span>  
 <span data-ttu-id="13882-126">Se uma sessão terminou em um erro, esse campo exibirá a última mensagem de erro registrada pelo Snapshot Agent.</span><span class="sxs-lookup"><span data-stu-id="13882-126">If a session ended in an error, this field displays the last error message logged by the Snapshot Agent.</span></span> <span data-ttu-id="13882-127">Se uma sessão não terminou em erro, esse campo ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="13882-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="13882-128">**Mensagem de Ação**</span><span class="sxs-lookup"><span data-stu-id="13882-128">**Action Message**</span></span>  
 <span data-ttu-id="13882-129">Todas as mensagens informativas e de erro que o Snapshot Agent registrou durante a sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="13882-129">All informational messages and error messages that the Snapshot Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="13882-130">**Tempo da Ação**</span><span class="sxs-lookup"><span data-stu-id="13882-130">**Action Time**</span></span>  
 <span data-ttu-id="13882-131">O tempo no qual a ação descrita na coluna **Mensagem de Ação** foi executada.</span><span class="sxs-lookup"><span data-stu-id="13882-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="13882-132">**Detalhes ou mensagem de erro da sessão selecionada**</span><span class="sxs-lookup"><span data-stu-id="13882-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="13882-133">Exibido somente se a sessão selecionada exibir um valor de **Erro** na coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="13882-133">Is displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="13882-134">Essa área de texto exibe informações de erro detalhadas e o comando tentado no momento do erro.</span><span class="sxs-lookup"><span data-stu-id="13882-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="13882-135">Também inclui links para conteúdo adicional relacionado ao erro.</span><span class="sxs-lookup"><span data-stu-id="13882-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13882-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="13882-136">See Also</span></span>  
 <span data-ttu-id="13882-137">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="13882-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="13882-138">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="13882-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="13882-139">[Monitorando a Replicação](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="13882-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="13882-140">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="13882-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
