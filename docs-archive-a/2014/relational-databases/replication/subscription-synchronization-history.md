---
title: Assinatura, histórico de sincronização (assinatura de mesclagem, SQL Server 2005 e posterior) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.synchhistory.f1
- sql12.rep.monitor.subscription.downlevelsynchhistory.f1
ms.assetid: 85f666f6-14ee-4f19-b385-e5cc508aabe4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49fe19f22976116813ac2454b2d08fc1fe47d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581760"
---
# <a name="subscription-synchronization-history-merge-subscription-sql-server-2005-and-later"></a><span data-ttu-id="d66a1-102">Assinatura, Histórico de Sincronização (assinatura de mesclagem, SQL Server 2005 e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="d66a1-102">Subscription, Synchronization History (Merge Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="d66a1-103">A guia **Histórico de Sincronização** exibe informações detalhadas do Merge Agent, incluindo status, estatísticas de artigo, histórico, mensagens informativas e qualquer mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="d66a1-103">The **Synchronization History** tab displays detailed information on the Merge Agent, including status, article statistics, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d66a1-104">Opções</span><span class="sxs-lookup"><span data-stu-id="d66a1-104">Options</span></span>  
 <span data-ttu-id="d66a1-105">Selecione as sessões do Merge Agent a serem exibidas no menu **Exibir** e, depois, selecione uma sessão específica na grade rotulada **Sessões do Merge Agent**.</span><span class="sxs-lookup"><span data-stu-id="d66a1-105">Select which Merge Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Merge Agent**.</span></span> <span data-ttu-id="d66a1-106">As informações detalhadas sobre essa sessão são exibidas na grade rotulada **Artigos processados na sessão selecionada**.</span><span class="sxs-lookup"><span data-stu-id="d66a1-106">Detailed information on this session is displayed in the grid labeled **Articles processed in the selected session**.</span></span>  
  
 <span data-ttu-id="d66a1-107">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="d66a1-107">**View**</span></span>  
 <span data-ttu-id="d66a1-108">Selecione as sessões do Merge Agent a serem exibidas.</span><span class="sxs-lookup"><span data-stu-id="d66a1-108">Select which Merge Agent sessions to view.</span></span>  
  
 <span data-ttu-id="d66a1-109">**Status**</span><span class="sxs-lookup"><span data-stu-id="d66a1-109">**Status**</span></span>  
 <span data-ttu-id="d66a1-110">A ID do status do Merge Agent no fim da sessão.</span><span class="sxs-lookup"><span data-stu-id="d66a1-110">The status of the Merge Agent at the end of the session.</span></span> <span data-ttu-id="d66a1-111">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="d66a1-111">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="d66a1-112">Erro</span><span class="sxs-lookup"><span data-stu-id="d66a1-112">Error</span></span>  
  
-   <span data-ttu-id="d66a1-113">Concluído</span><span class="sxs-lookup"><span data-stu-id="d66a1-113">Completed</span></span>  
  
-   <span data-ttu-id="d66a1-114">Tentando novamente</span><span class="sxs-lookup"><span data-stu-id="d66a1-114">Retrying</span></span>  
  
-   <span data-ttu-id="d66a1-115">Executando</span><span class="sxs-lookup"><span data-stu-id="d66a1-115">Running</span></span>  
  
 <span data-ttu-id="d66a1-116">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="d66a1-116">**Start Time**</span></span>  
 <span data-ttu-id="d66a1-117">A hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="d66a1-117">The start time of the session.</span></span>  
  
 <span data-ttu-id="d66a1-118">**Hora de término**</span><span class="sxs-lookup"><span data-stu-id="d66a1-118">**End Time**</span></span>  
 <span data-ttu-id="d66a1-119">A hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="d66a1-119">The end time of the session.</span></span> <span data-ttu-id="d66a1-120">Se o agente não parou, esse campo estará vazio.</span><span class="sxs-lookup"><span data-stu-id="d66a1-120">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="d66a1-121">**Duration**</span><span class="sxs-lookup"><span data-stu-id="d66a1-121">**Duration**</span></span>  
 <span data-ttu-id="d66a1-122">A quantidade de tempo que o Merge Agent foi executado em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d66a1-122">The amount of time the Merge Agent has run in a session.</span></span> <span data-ttu-id="d66a1-123">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total, se o agente foi executado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d66a1-123">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="d66a1-124">**Comandos Carregados**</span><span class="sxs-lookup"><span data-stu-id="d66a1-124">**Uploaded Commands**</span></span>  
 <span data-ttu-id="d66a1-125">O número de linhas carregado durante a sessão do Merge Agent.</span><span class="sxs-lookup"><span data-stu-id="d66a1-125">The number of rows uploaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="d66a1-126">**Comandos Baixados**</span><span class="sxs-lookup"><span data-stu-id="d66a1-126">**Downloaded Commands**</span></span>  
 <span data-ttu-id="d66a1-127">O número de linhas baixado durante a sessão do Merge Agent.</span><span class="sxs-lookup"><span data-stu-id="d66a1-127">The number of rows downloaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="d66a1-128">**Mensagem de erro**</span><span class="sxs-lookup"><span data-stu-id="d66a1-128">**Error Message**</span></span>  
 <span data-ttu-id="d66a1-129">Se uma sessão tiver terminado em um erro, esse campo exibirá a última mensagem de erro registrada pelo Merge Agent.</span><span class="sxs-lookup"><span data-stu-id="d66a1-129">If a session ended in an error, this field displays the last error message logged by the Merge Agent.</span></span> <span data-ttu-id="d66a1-130">Se uma sessão não terminou em erro, esse campo ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="d66a1-130">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="d66a1-131">**Artigo**</span><span class="sxs-lookup"><span data-stu-id="d66a1-131">**Article**</span></span>  
 <span data-ttu-id="d66a1-132">O nome de cada artigo na publicação e as fases de processamento posteriores para toda a publicação:</span><span class="sxs-lookup"><span data-stu-id="d66a1-132">The name of each article in the publication, and the following processing phases for the entire publication:</span></span>  
  
-   <span data-ttu-id="d66a1-133">**Inicialização**.</span><span class="sxs-lookup"><span data-stu-id="d66a1-133">**Initialization**.</span></span> <span data-ttu-id="d66a1-134">Refere-se à inicialização do Merge Agent; não é o mesmo que iniciar uma assinatura, que envolve a aplicação de um instantâneo.</span><span class="sxs-lookup"><span data-stu-id="d66a1-134">This refers to starting the Merge Agent; this is not synonymous with initializing a subscription, which involves applying a snapshot.</span></span>  
  
-   <span data-ttu-id="d66a1-135">**Alterações de esquema e inserções em massa**.</span><span class="sxs-lookup"><span data-stu-id="d66a1-135">**Schema changes and bulk inserts**.</span></span>  
  
-   <span data-ttu-id="d66a1-136">**Carregar alterações do Publicador**.</span><span class="sxs-lookup"><span data-stu-id="d66a1-136">**Upload changes to Publisher**.</span></span>  
  
-   <span data-ttu-id="d66a1-137">**Baixar alterações para o Assinante**.</span><span class="sxs-lookup"><span data-stu-id="d66a1-137">**Download changes to Subscriber**.</span></span>  
  
 <span data-ttu-id="d66a1-138">As fases são incluídas para que a grade possa exibir a quantidade de tempo e a porcentagem do tempo total de cada fase na sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66a1-138">The phases are included so that the grid can display the amount of time and percentage of total time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="d66a1-139">**% do total**</span><span class="sxs-lookup"><span data-stu-id="d66a1-139">**% of total**</span></span>  
 <span data-ttu-id="d66a1-140">A porcentagem do tempo de processamento total de cada fase na sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66a1-140">The percentage of total processing time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="d66a1-141">**Duration**</span><span class="sxs-lookup"><span data-stu-id="d66a1-141">**Duration**</span></span>  
 <span data-ttu-id="d66a1-142">O tempo gasto em cada fase de processamento.</span><span class="sxs-lookup"><span data-stu-id="d66a1-142">The amount of time spent in each processing phase.</span></span> <span data-ttu-id="d66a1-143">O tempo representa o tempo decorrido, se o Merge Agent estiver sendo executado na sessão no momento, e o tempo total, se o Merge Agent foi executado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d66a1-143">The time represents elapsed time if the Merge Agent is currently running for the session and total time if the Merge Agent has run previously.</span></span>  
  
 <span data-ttu-id="d66a1-144">**Insere**</span><span class="sxs-lookup"><span data-stu-id="d66a1-144">**Inserts**</span></span>  
 <span data-ttu-id="d66a1-145">O número de linhas inserido nesta fase da sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66a1-145">The number of rows inserted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="d66a1-146">**Atualizações**</span><span class="sxs-lookup"><span data-stu-id="d66a1-146">**Updates**</span></span>  
 <span data-ttu-id="d66a1-147">O número de linhas atualizado nesta fase da sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66a1-147">The number of rows updated in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="d66a1-148">**Deletes**</span><span class="sxs-lookup"><span data-stu-id="d66a1-148">**Deletes**</span></span>  
 <span data-ttu-id="d66a1-149">O número de linhas excluído nesta fase da sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66a1-149">The number of rows deleted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="d66a1-150">**Conflicts**</span><span class="sxs-lookup"><span data-stu-id="d66a1-150">**Conflicts**</span></span>  
 <span data-ttu-id="d66a1-151">O número de conflitos na sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66a1-151">The number of conflicts in the selected session.</span></span>  
  
 <span data-ttu-id="d66a1-152">**Schema Changes**</span><span class="sxs-lookup"><span data-stu-id="d66a1-152">**Schema Changes**</span></span>  
 <span data-ttu-id="d66a1-153">O número de alterações de esquema na sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66a1-153">The number of schema changes in the selected session.</span></span> <span data-ttu-id="d66a1-154">As alterações de esquema podem resultar de: alterações sendo replicadas no banco de dados de publicação; adição ou descarte de artigos; e alterações em propriedades de artigo ou publicação.</span><span class="sxs-lookup"><span data-stu-id="d66a1-154">Schema changes can result from: schema changes being replicated from the publication database; adding or dropping articles; and changes to article or publication properties.</span></span>  
  
 <span data-ttu-id="d66a1-155">**Última mensagem da sessão selecionada**</span><span class="sxs-lookup"><span data-stu-id="d66a1-155">**Last message of the selected session**</span></span>  
 <span data-ttu-id="d66a1-156">Essa área de texto exibe a última mensagem na sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="d66a1-156">This text area displays the last message in the selected session.</span></span> <span data-ttu-id="d66a1-157">Se tiver ocorrido um erro, exibirá informações de erro detalhadas e o comando tentado no momento do erro.</span><span class="sxs-lookup"><span data-stu-id="d66a1-157">If an error has occurred, it displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="d66a1-158">Também inclui links para conteúdo adicional relacionado ao erro.</span><span class="sxs-lookup"><span data-stu-id="d66a1-158">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d66a1-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d66a1-159">See Also</span></span>  
 <span data-ttu-id="d66a1-160">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d66a1-160">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="d66a1-161">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d66a1-161">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="d66a1-162">[Monitorando a Replicação](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d66a1-162">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="d66a1-163">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="d66a1-163">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
