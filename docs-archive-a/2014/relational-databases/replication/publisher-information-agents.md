---
title: Informações sobre o Publicador, agentes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.commonjobs.f1
ms.assetid: 2346c00d-c269-45a1-af14-68e7fd7ebd7e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bdd2055ed022257524bc4d2784bdc333537be855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569336"
---
# <a name="publisher-information-agents"></a><span data-ttu-id="f94e2-102">Informações do Publicador, Agentes</span><span class="sxs-lookup"><span data-stu-id="f94e2-102">Publisher Information, Agents</span></span>
  <span data-ttu-id="f94e2-103">A guia **Agentes** exibe informações sobre os agentes e trabalhos de manutenção associados ao Publicador:</span><span class="sxs-lookup"><span data-stu-id="f94e2-103">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher:</span></span>  
  
-   <span data-ttu-id="f94e2-104">Snapshot Agent que é exibido para todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="f94e2-104">Snapshot Agent, which is displayed for all publications.</span></span>  
  
-   <span data-ttu-id="f94e2-105">Log Reader Agent que é exibido para todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="f94e2-105">Log Reader Agent, which is displayed for all transactional publications.</span></span>  
  
-   <span data-ttu-id="f94e2-106">Queue Reader Agent que é exibido para publicações transacionais habilitadas para assinaturas de atualização enfileiradas.</span><span class="sxs-lookup"><span data-stu-id="f94e2-106">Queue Reader Agent, which is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="f94e2-107">Trabalhos de manutenção exibidos para todas as publicações:</span><span class="sxs-lookup"><span data-stu-id="f94e2-107">Maintenance jobs, displayed for all publications:</span></span>  
  
    -   <span data-ttu-id="f94e2-108">Assinaturas de reinicialização, com falhas de validação de dados</span><span class="sxs-lookup"><span data-stu-id="f94e2-108">Reinitialize subscriptions that have data validation failures</span></span>  
  
    -   <span data-ttu-id="f94e2-109">Limpeza do histórico de agente: distribuição</span><span class="sxs-lookup"><span data-stu-id="f94e2-109">Agent history cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="f94e2-110">Atualizador de monitoração de replicação para distribuição</span><span class="sxs-lookup"><span data-stu-id="f94e2-110">Replication monitoring refresher for distribution</span></span>  
  
    -   <span data-ttu-id="f94e2-111">Verificação de agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="f94e2-111">Replication agents checkup</span></span>  
  
    -   <span data-ttu-id="f94e2-112">Limpeza de distribuição: distribuição</span><span class="sxs-lookup"><span data-stu-id="f94e2-112">Distribution cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="f94e2-113">Limpeza de assinatura expirada</span><span class="sxs-lookup"><span data-stu-id="f94e2-113">Expired subscription cleanup</span></span>  
  
 <span data-ttu-id="f94e2-114">Para obter mais informações sobre esses trabalhos, consulte [Administração do agente de replicação](agents/replication-agent-administration.md).</span><span class="sxs-lookup"><span data-stu-id="f94e2-114">For more information about these jobs, see [Replication Agent Administration](agents/replication-agent-administration.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f94e2-115">Opções</span><span class="sxs-lookup"><span data-stu-id="f94e2-115">Options</span></span>  
 <span data-ttu-id="f94e2-116">Para exibir informações sobre um agente ou trabalho, selecione no menu suspenso **Tipos de Agente e Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="f94e2-116">To display information about an agent or job, select from the **Agent and Job Types** drop-down menu.</span></span> <span data-ttu-id="f94e2-117">Para obter informações mais detalhadas e tarefas relacionadas a um agente ou trabalho, clique com o botão direito na linha do agente ou trabalho e clique em uma opção no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="f94e2-117">For more detailed information and tasks that are related to an agent or job, right-click the row for that agent or job, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="f94e2-118">Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="f94e2-118">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="f94e2-119">**Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="f94e2-119">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f94e2-120">**Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="f94e2-120">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f94e2-121">**Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="f94e2-121">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="f94e2-122">**Limpar Filtro**: limpe as configurações de filtro da grade.</span><span class="sxs-lookup"><span data-stu-id="f94e2-122">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="f94e2-123">As configurações de filtro são específicas de cada grade.</span><span class="sxs-lookup"><span data-stu-id="f94e2-123">Filter settings are specific to each grid.</span></span> <span data-ttu-id="f94e2-124">A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="f94e2-124">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="f94e2-125">As seções a seguir descrevem os dados exibidos nesta guia para cada agente ou trabalho.</span><span class="sxs-lookup"><span data-stu-id="f94e2-125">The following sections describe the data that is displayed on this tab for each agent or job.</span></span>  
  
### <a name="snapshot-agent"></a><span data-ttu-id="f94e2-126">Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="f94e2-126">Snapshot Agent</span></span>  
 <span data-ttu-id="f94e2-127">**Status**</span><span class="sxs-lookup"><span data-stu-id="f94e2-127">**Status**</span></span>  
 <span data-ttu-id="f94e2-128">O status do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-128">The status of the agent.</span></span> <span data-ttu-id="f94e2-129">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="f94e2-129">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="f94e2-130">Erro</span><span class="sxs-lookup"><span data-stu-id="f94e2-130">Error</span></span>  
  
-   <span data-ttu-id="f94e2-131">Repetir</span><span class="sxs-lookup"><span data-stu-id="f94e2-131">Retry</span></span>  
  
-   <span data-ttu-id="f94e2-132">Executando</span><span class="sxs-lookup"><span data-stu-id="f94e2-132">Running</span></span>  
  
-   <span data-ttu-id="f94e2-133">Concluído</span><span class="sxs-lookup"><span data-stu-id="f94e2-133">Completed</span></span>  
  
 <span data-ttu-id="f94e2-134">**Publicação**</span><span class="sxs-lookup"><span data-stu-id="f94e2-134">**Publication**</span></span>  
 <span data-ttu-id="f94e2-135">O nome da publicação com a qual o agente está associado.</span><span class="sxs-lookup"><span data-stu-id="f94e2-135">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="f94e2-136">**Última Hora de Início**</span><span class="sxs-lookup"><span data-stu-id="f94e2-136">**Last Start Time**</span></span>  
 <span data-ttu-id="f94e2-137">A última hora de início do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-137">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="f94e2-138">**Duration**</span><span class="sxs-lookup"><span data-stu-id="f94e2-138">**Duration**</span></span>  
 <span data-ttu-id="f94e2-139">O tempo de execução do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-139">The length of time the agent has run.</span></span> <span data-ttu-id="f94e2-140">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total, se o agente foi executado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-140">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="f94e2-141">**Última Ação**</span><span class="sxs-lookup"><span data-stu-id="f94e2-141">**Last Action**</span></span>  
 <span data-ttu-id="f94e2-142">A última ação executada durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-142">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="f94e2-143">**Taxa de Entrega**</span><span class="sxs-lookup"><span data-stu-id="f94e2-143">**Delivery Rate**</span></span>  
 <span data-ttu-id="f94e2-144">A taxa, em comandos por segundo, com a qual os comandos de inicialização são confirmados no banco de dados de distribuição durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-144">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="f94e2-145">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="f94e2-145">**#Trans**</span></span>  
 <span data-ttu-id="f94e2-146">O número de transações confirmado no banco de dados de distribuição durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-146">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="f94e2-147">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="f94e2-147">**#Cmds**</span></span>  
 <span data-ttu-id="f94e2-148">O número de comandos confirmado no banco de dados de distribuição durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-148">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="f94e2-149">Um comando é equivalente a uma alteração de dados, como uma atualização.</span><span class="sxs-lookup"><span data-stu-id="f94e2-149">A command is equivalent to a data change, such as an update.</span></span>  
  
### <a name="log-reader-agent"></a><span data-ttu-id="f94e2-150">Agente de Leitor de Log</span><span class="sxs-lookup"><span data-stu-id="f94e2-150">Log Reader Agent</span></span>  
 <span data-ttu-id="f94e2-151">**Status**</span><span class="sxs-lookup"><span data-stu-id="f94e2-151">**Status**</span></span>  
 <span data-ttu-id="f94e2-152">O status do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-152">The status of the agent.</span></span> <span data-ttu-id="f94e2-153">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="f94e2-153">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="f94e2-154">Erro</span><span class="sxs-lookup"><span data-stu-id="f94e2-154">Error</span></span>  
  
-   <span data-ttu-id="f94e2-155">Repetir</span><span class="sxs-lookup"><span data-stu-id="f94e2-155">Retry</span></span>  
  
-   <span data-ttu-id="f94e2-156">Executando</span><span class="sxs-lookup"><span data-stu-id="f94e2-156">Running</span></span>  
  
-   <span data-ttu-id="f94e2-157">Não está sendo executado</span><span class="sxs-lookup"><span data-stu-id="f94e2-157">Not running</span></span>  
  
 <span data-ttu-id="f94e2-158">**Banco de dados de publicação**</span><span class="sxs-lookup"><span data-stu-id="f94e2-158">**Publication Database**</span></span>  
 <span data-ttu-id="f94e2-159">O nome da publicação com a qual o agente está associado.</span><span class="sxs-lookup"><span data-stu-id="f94e2-159">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="f94e2-160">**Última Hora de Início**</span><span class="sxs-lookup"><span data-stu-id="f94e2-160">**Last Start Time**</span></span>  
 <span data-ttu-id="f94e2-161">A última hora de início do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-161">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="f94e2-162">**Duration**</span><span class="sxs-lookup"><span data-stu-id="f94e2-162">**Duration**</span></span>  
 <span data-ttu-id="f94e2-163">O tempo de execução do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-163">The length of time the agent has run.</span></span> <span data-ttu-id="f94e2-164">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total, se o agente foi executado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-164">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="f94e2-165">**Última Ação**</span><span class="sxs-lookup"><span data-stu-id="f94e2-165">**Last Action**</span></span>  
 <span data-ttu-id="f94e2-166">A última ação executada durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-166">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="f94e2-167">**Taxa de Entrega**</span><span class="sxs-lookup"><span data-stu-id="f94e2-167">**Delivery Rate**</span></span>  
 <span data-ttu-id="f94e2-168">A taxa, em comandos por segundo, com a qual as alterações são confirmadas no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f94e2-168">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="f94e2-169">**Latência**</span><span class="sxs-lookup"><span data-stu-id="f94e2-169">**Latency**</span></span>  
 <span data-ttu-id="f94e2-170">É o período de tempo, em segundos, decorrido entre a confirmação da alteração mais recente no banco de dados de publicação e a confirmação do comando correspondente no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f94e2-170">The amount of time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="f94e2-171">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="f94e2-171">**#Trans**</span></span>  
 <span data-ttu-id="f94e2-172">O número de transações confirmado no banco de dados de distribuição durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-172">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="f94e2-173">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="f94e2-173">**#Cmds**</span></span>  
 <span data-ttu-id="f94e2-174">O número de comandos confirmado no banco de dados de distribuição durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-174">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="f94e2-175">Um comando é equivalente a uma alteração de dados, como uma atualização.</span><span class="sxs-lookup"><span data-stu-id="f94e2-175">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="f94e2-176">**Avg. #Cmds**</span><span class="sxs-lookup"><span data-stu-id="f94e2-176">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="f94e2-177">O número médio de comandos por transação durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-177">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="queue-reader-agent"></a><span data-ttu-id="f94e2-178">Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="f94e2-178">Queue Reader Agent</span></span>  
 <span data-ttu-id="f94e2-179">**Status**</span><span class="sxs-lookup"><span data-stu-id="f94e2-179">**Status**</span></span>  
 <span data-ttu-id="f94e2-180">O status do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-180">The status of the agent.</span></span> <span data-ttu-id="f94e2-181">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="f94e2-181">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="f94e2-182">Erro</span><span class="sxs-lookup"><span data-stu-id="f94e2-182">Error</span></span>  
  
-   <span data-ttu-id="f94e2-183">Repetir</span><span class="sxs-lookup"><span data-stu-id="f94e2-183">Retry</span></span>  
  
-   <span data-ttu-id="f94e2-184">Executando</span><span class="sxs-lookup"><span data-stu-id="f94e2-184">Running</span></span>  
  
-   <span data-ttu-id="f94e2-185">Não está sendo executado</span><span class="sxs-lookup"><span data-stu-id="f94e2-185">Not running</span></span>  
  
 <span data-ttu-id="f94e2-186">**Banco de dados de distribuição**</span><span class="sxs-lookup"><span data-stu-id="f94e2-186">**Distribution Database**</span></span>  
 <span data-ttu-id="f94e2-187">O nome do banco de dados de distribuição ao qual o agente está associado.</span><span class="sxs-lookup"><span data-stu-id="f94e2-187">The name of the distribution database with which the agent is associated.</span></span>  
  
 <span data-ttu-id="f94e2-188">**Última Hora de Início**</span><span class="sxs-lookup"><span data-stu-id="f94e2-188">**Last Start Time**</span></span>  
 <span data-ttu-id="f94e2-189">A última hora de início do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-189">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="f94e2-190">**Duration**</span><span class="sxs-lookup"><span data-stu-id="f94e2-190">**Duration**</span></span>  
 <span data-ttu-id="f94e2-191">O tempo de execução do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-191">The length of time the agent has run.</span></span> <span data-ttu-id="f94e2-192">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total, se o agente foi executado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-192">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="f94e2-193">**Última Ação**</span><span class="sxs-lookup"><span data-stu-id="f94e2-193">**Last Action**</span></span>  
 <span data-ttu-id="f94e2-194">A última ação executada durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-194">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="f94e2-195">**Taxa de Entrega**</span><span class="sxs-lookup"><span data-stu-id="f94e2-195">**Delivery Rate**</span></span>  
 <span data-ttu-id="f94e2-196">A taxa, em comandos por segundo, com a qual as alterações são confirmadas no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f94e2-196">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="f94e2-197">**Latência**</span><span class="sxs-lookup"><span data-stu-id="f94e2-197">**Latency**</span></span>  
 <span data-ttu-id="f94e2-198">É o período de tempo, em segundos, decorrido entre confirmação da alteração mais recente no banco de dados de assinatura e a confirmação do comando correspondente no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="f94e2-198">The amount of time, in seconds, that has elapsed between the most recent change being committed in a subscription database, and the corresponding command being committed in the publication database.</span></span>  
  
 <span data-ttu-id="f94e2-199">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="f94e2-199">**#Trans**</span></span>  
 <span data-ttu-id="f94e2-200">O número de transações confirmado no banco de dados de publicação durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-200">The number of transactions committed in the publication database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="f94e2-201">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="f94e2-201">**#Cmds**</span></span>  
 <span data-ttu-id="f94e2-202">O número de comandos confirmados no banco de dados de publicação durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-202">The number of commands committed in the publication database during the most recent run of the agent.</span></span> <span data-ttu-id="f94e2-203">Um comando é equivalente a uma alteração de dados, como uma atualização.</span><span class="sxs-lookup"><span data-stu-id="f94e2-203">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="f94e2-204">**Avg. #Cmds**</span><span class="sxs-lookup"><span data-stu-id="f94e2-204">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="f94e2-205">O número médio de comandos por transação durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-205">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="maintenance-jobs"></a><span data-ttu-id="f94e2-206">Trabalhos de manutenção</span><span class="sxs-lookup"><span data-stu-id="f94e2-206">Maintenance Jobs</span></span>  
 <span data-ttu-id="f94e2-207">**Status**</span><span class="sxs-lookup"><span data-stu-id="f94e2-207">**Status**</span></span>  
 <span data-ttu-id="f94e2-208">O status de cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="f94e2-208">The status of each job.</span></span> <span data-ttu-id="f94e2-209">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="f94e2-209">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="f94e2-210">Erro</span><span class="sxs-lookup"><span data-stu-id="f94e2-210">Error</span></span>  
  
-   <span data-ttu-id="f94e2-211">Repetir</span><span class="sxs-lookup"><span data-stu-id="f94e2-211">Retry</span></span>  
  
-   <span data-ttu-id="f94e2-212">Executando</span><span class="sxs-lookup"><span data-stu-id="f94e2-212">Running</span></span>  
  
-   <span data-ttu-id="f94e2-213">Não está sendo executado</span><span class="sxs-lookup"><span data-stu-id="f94e2-213">Not running</span></span>  
  
 <span data-ttu-id="f94e2-214">**Trabalho**</span><span class="sxs-lookup"><span data-stu-id="f94e2-214">**Job**</span></span>  
 <span data-ttu-id="f94e2-215">O nome do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f94e2-215">The name of the job.</span></span>  
  
 <span data-ttu-id="f94e2-216">**Última Hora de Início**</span><span class="sxs-lookup"><span data-stu-id="f94e2-216">**Last Start Time**</span></span>  
 <span data-ttu-id="f94e2-217">A última hora de início do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f94e2-217">The last time at which the job started.</span></span>  
  
 <span data-ttu-id="f94e2-218">**Duration**</span><span class="sxs-lookup"><span data-stu-id="f94e2-218">**Duration**</span></span>  
 <span data-ttu-id="f94e2-219">O tempo de execução do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f94e2-219">The length of time the job has run.</span></span> <span data-ttu-id="f94e2-220">O tempo representa o tempo decorrido, se o trabalho estiver sendo executado no momento, e o tempo total, se o trabalho foi executado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f94e2-220">The time represents elapsed time if the job is currently running, and total time if the job has run previously.</span></span>  
  
 <span data-ttu-id="f94e2-221">**Última Ação**</span><span class="sxs-lookup"><span data-stu-id="f94e2-221">**Last Action**</span></span>  
 <span data-ttu-id="f94e2-222">A última ação executada durante a execução mais recente do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f94e2-222">The last action performed during the most recent run of the job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94e2-223">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f94e2-223">See Also</span></span>  
 <span data-ttu-id="f94e2-224">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f94e2-224">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f94e2-225">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f94e2-225">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="f94e2-226">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="f94e2-226">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
