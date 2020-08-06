---
title: Visão geral da interface do Replication Monitor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor
- Replication Monitor, about Replication Monitor
ms.assetid: 078f0e34-7153-45c4-8725-778b5bef88da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d9b7edbd76153f23168ec9bcf4a286d5f7cbe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571936"
---
# <a name="overview-of-the-replication-monitor-interface"></a><span data-ttu-id="6a373-102">Visão geral da interface do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="6a373-102">Overview of the Replication Monitor Interface</span></span>
  <span data-ttu-id="6a373-103">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor apresenta uma exibição voltada para o Publicador ou para o Distribuidor de todas as atividades de replicação em um formato de dois painéis.</span><span class="sxs-lookup"><span data-stu-id="6a373-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor presents a Publisher-focused view or Distributor-focused view of all replication activity in a two pane format.</span></span> <span data-ttu-id="6a373-104">Você adiciona um Publicador ao monitor no painel esquerdo e, no painel direito, o monitor exibe informações sobre o Publicador, suas publicações, as assinaturas para essas publicações e os diversos agentes de replicação.</span><span class="sxs-lookup"><span data-stu-id="6a373-104">You add a Publisher to the monitor in the left pane, and in the right pane the monitor displays information on the Publisher, its publications, the subscriptions to those publications, and the various replication agents.</span></span> <span data-ttu-id="6a373-105">Além de apresentar informações sobre a topologia de replicação, o Replication Monitor permite que você execute várias tarefas, como iniciar e interromper agentes e validar dados.</span><span class="sxs-lookup"><span data-stu-id="6a373-105">In addition to presenting information for the replication topology, Replication Monitor allows you to perform a number of tasks, such as starting and stopping agents, and validating data.</span></span>  
  
## <a name="viewing-information-for-the-entire-topology"></a><span data-ttu-id="6a373-106">Exibindo informações para toda a topologia</span><span class="sxs-lookup"><span data-stu-id="6a373-106">Viewing Information for the Entire Topology</span></span>  
 <span data-ttu-id="6a373-107">O painel esquerdo da exibição do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="6a373-107">The left pane of Replication Monitor displays</span></span>  
  
-   <span data-ttu-id="6a373-108">Grupos do publicador, publicadores e publicações.</span><span class="sxs-lookup"><span data-stu-id="6a373-108">Publisher groups, Publishers, and publications.</span></span>  
  
-   <span data-ttu-id="6a373-109">Distribuidores, publicadores e publicações.</span><span class="sxs-lookup"><span data-stu-id="6a373-109">Distributors, Publishers, and publications.</span></span>  
  
 <span data-ttu-id="6a373-110">Você deve adicionar um Publicador antes de exibir quaisquer informações no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="6a373-110">To view any information in Replication Monitor, you must first add a Publisher.</span></span> <span data-ttu-id="6a373-111">Para obter mais informações, veja [Adicionar e remover Publicadores do Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6a373-111">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="6a373-112">O painel esquerdo ajuda a responder as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="6a373-112">The left pane helps answer the following questions:</span></span>  
  
-   <span data-ttu-id="6a373-113">Meu sistema de replicação está íntegro?</span><span class="sxs-lookup"><span data-stu-id="6a373-113">Is my replication system healthy?</span></span>  
  
     <span data-ttu-id="6a373-114">O sistema de replicação estará relativamente íntegro se não houver nenhum ícones de erro em nós no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="6a373-114">The replication system is relatively healthy if there are no error icons on nodes in the left pane.</span></span> <span data-ttu-id="6a373-115">Para obter uma exibição mais completa da integridade do sistema, você também deve verificar a guia **Lista de Observação da Assinatura** que exibe informações sobre as assinaturas que talvez exijam atenção.</span><span class="sxs-lookup"><span data-stu-id="6a373-115">To get a more complete view of system health, you should also check the **Subscription Watch List** tab, which displays information on subscriptions that might require attention.</span></span>  
  
-   <span data-ttu-id="6a373-116">Por que um agente não está executando?</span><span class="sxs-lookup"><span data-stu-id="6a373-116">Why is an agent not running?</span></span>  
  
     <span data-ttu-id="6a373-117">Um agente não está em execução em um momento específico porque não está agendado para execução ou porque ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="6a373-117">An agent is not running at a particular time either because it is not scheduled to run or because an error has occurred.</span></span> <span data-ttu-id="6a373-118">Se tiver ocorrido um erro, será exibido um ícone de erro nos nós apropriados no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="6a373-118">If an error has occurred, an error icon is displayed on the appropriate nodes in the left pane.</span></span> <span data-ttu-id="6a373-119">Por exemplo, se o Agente de Instantâneo de uma publicação foi interrompido devido a um erro, um ícone de erro será exibido no Grupo do publicador, no Publicador e nos nós de publicação.</span><span class="sxs-lookup"><span data-stu-id="6a373-119">For example, if the Snapshot Agent for a publication stopped because of an error, an error icon is displayed on the Publisher group, Publisher, and publication nodes.</span></span> <span data-ttu-id="6a373-120">A guia **Agentes** exibe informações resumidas sobre o Agente de Instantâneo para a publicação. Clique duas vezes no Agente de Instantâneo nessa guia para obter informações detalhadas sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="6a373-120">Summary information for the Snapshot Agent is displayed on the **Agents** tab for the publication; double click the Snapshot Agent on this tab for detailed error information.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-distributors"></a><span data-ttu-id="6a373-121">Exibindo informações e executando tarefas relacionadas à distribuidores</span><span class="sxs-lookup"><span data-stu-id="6a373-121">Viewing Information and Performing Tasks Related to Distributors</span></span>  
 <span data-ttu-id="6a373-122">O Replication Monitor exibe informações sobre Distribuidores em três guias:</span><span class="sxs-lookup"><span data-stu-id="6a373-122">Replication Monitor displays information about Distributors on three tabs:</span></span>  
  
-   <span data-ttu-id="6a373-123">Guia**Publicações**</span><span class="sxs-lookup"><span data-stu-id="6a373-123">**Publications** tab</span></span>  
  
     <span data-ttu-id="6a373-124">Essa guia fornece informações resumidas de todas as publicações de um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6a373-124">This tab provides summary information for all publications of a Distributor.</span></span>  
  
-   <span data-ttu-id="6a373-125">Guia**Lista de Observação da Assinatura**</span><span class="sxs-lookup"><span data-stu-id="6a373-125">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="6a373-126">Essa guia fornece informações sobre assinaturas do Distribuidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="6a373-126">This tab provides information about subscriptions for the selected Distributor.</span></span> <span data-ttu-id="6a373-127">Você pode filtrar a lista de assinaturas para ver erros, avisos e qualquer assinatura de desempenho insatisfatório.</span><span class="sxs-lookup"><span data-stu-id="6a373-127">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="6a373-128">A guia também permite executar as seguintes tarefas: acessar propriedades da assinatura, acessar informações detalhadas sobre o agente ou agentes associados à assinatura; reiniciar assinaturas e validar assinaturas.</span><span class="sxs-lookup"><span data-stu-id="6a373-128">The tab also lets you to perform the following tasks: access subscription properties, access detailed information about the agent or agents associated with a subscription, reinitialize subscriptions, and validate subscriptions.</span></span>  
  
     <span data-ttu-id="6a373-129">A guia **Lista de Observação da Assinatura** ajuda a responder as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="6a373-129">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="6a373-130">Quais assinaturas estão lentas?</span><span class="sxs-lookup"><span data-stu-id="6a373-130">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="6a373-131">Defina as opções nessa guia de forma que a grade exiba as assinaturas em ordem de desempenho relativo.</span><span class="sxs-lookup"><span data-stu-id="6a373-131">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="6a373-132">Meu sistema de replicação está íntegro?</span><span class="sxs-lookup"><span data-stu-id="6a373-132">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="6a373-133">A grade nessa guia exibe ícones de erro e advertência de qualquer assinatura que exija sua atenção.</span><span class="sxs-lookup"><span data-stu-id="6a373-133">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="6a373-134">Essa guia não está disponível para Distribuidores que estão executando versões do [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] ou anteriores.</span><span class="sxs-lookup"><span data-stu-id="6a373-134">This tab is not available for Distributors that are running versions of [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span>  
  
-   <span data-ttu-id="6a373-135">Guia**Agentes**</span><span class="sxs-lookup"><span data-stu-id="6a373-135">**Agents** tab</span></span>  
  
     <span data-ttu-id="6a373-136">Essa guia exibe informações detalhadas sobre os agentes e trabalhos usados por todos os tipos de replicação.</span><span class="sxs-lookup"><span data-stu-id="6a373-136">This tab displays detailed information about the agents and jobs that are used by all types of replication.</span></span> <span data-ttu-id="6a373-137">A guia também permite iniciar e interromper cada agente e trabalho.</span><span class="sxs-lookup"><span data-stu-id="6a373-137">The tab also let you start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="6a373-138">O Replication Monitor também fornece um menu de contexto para o nó Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6a373-138">Replication Monitor also provides a context menu for the Distributor node.</span></span> <span data-ttu-id="6a373-139">Clique com o botão direito do mouse em um Distribuidor no painel esquerdo para executar as tarefas a seguir:</span><span class="sxs-lookup"><span data-stu-id="6a373-139">Right-click a Distributor in the left pane to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="6a373-140">Adicionar um Publicador ao Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="6a373-140">Add a Publisher to Replication Monitor.</span></span>  
  
-   <span data-ttu-id="6a373-141">Editar as configurações do Replication Monitor para o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6a373-141">Edit Replication Monitor settings for the Distributor.</span></span>  
  
-   <span data-ttu-id="6a373-142">Alternar para a exibição Grupo do Publicador.</span><span class="sxs-lookup"><span data-stu-id="6a373-142">Switch to the Publisher Group view.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publishers"></a><span data-ttu-id="6a373-143">Exibindo informações e executando tarefas relacionadas a Publicadores</span><span class="sxs-lookup"><span data-stu-id="6a373-143">Viewing Information and Performing Tasks Related to Publishers</span></span>  
 <span data-ttu-id="6a373-144">O Replication Monitor exibe informações sobre Publicadores em três guias:</span><span class="sxs-lookup"><span data-stu-id="6a373-144">Replication Monitor displays information about Publishers on three tabs:</span></span>  
  
-   <span data-ttu-id="6a373-145">Guia**Publicações**</span><span class="sxs-lookup"><span data-stu-id="6a373-145">**Publications** tab</span></span>  
  
     <span data-ttu-id="6a373-146">Essa guia fornece informações resumidas de todas as publicações em um Publicador.</span><span class="sxs-lookup"><span data-stu-id="6a373-146">This tab provides summary information for all publications at a Publisher.</span></span>  
  
-   <span data-ttu-id="6a373-147">Guia**Lista de Observação da Assinatura**</span><span class="sxs-lookup"><span data-stu-id="6a373-147">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="6a373-148">O objetivo dessa guia é exibir informações sobre assinaturas de todas as publicações disponíveis no Publicador selecionado.</span><span class="sxs-lookup"><span data-stu-id="6a373-148">This tab is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="6a373-149">Você pode filtrar a lista de assinaturas para ver erros, avisos e qualquer assinatura de desempenho insatisfatório.</span><span class="sxs-lookup"><span data-stu-id="6a373-149">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="6a373-150">A guia também permite: acessar as propriedades da assinatura; acessar informações detalhadas sobre o agente ou agentes associados com uma assinatura; reiniciar assinaturas e validar assinaturas.</span><span class="sxs-lookup"><span data-stu-id="6a373-150">The tab also allows you to: access subscription properties; access detailed information about the agent or agents associated with a subscription; reinitialize subscriptions; and validate subscriptions.</span></span>  
  
     <span data-ttu-id="6a373-151">A guia **Lista de Observação da Assinatura** ajuda a responder as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="6a373-151">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="6a373-152">Quais assinaturas estão lentas?</span><span class="sxs-lookup"><span data-stu-id="6a373-152">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="6a373-153">Defina as opções nessa guia de forma que a grade exiba as assinaturas em ordem de desempenho relativo.</span><span class="sxs-lookup"><span data-stu-id="6a373-153">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="6a373-154">Meu sistema de replicação está íntegro?</span><span class="sxs-lookup"><span data-stu-id="6a373-154">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="6a373-155">A grade nessa guia exibe ícones de erro e advertência de qualquer assinatura que exija sua atenção.</span><span class="sxs-lookup"><span data-stu-id="6a373-155">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="6a373-156">Essa guia não é exibida para Distribuidores que executam versões anteriores ao [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a373-156">This tab is not displayed for Distributors running versions prior to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="6a373-157">Guia**Agentes**</span><span class="sxs-lookup"><span data-stu-id="6a373-157">**Agents** tab</span></span>  
  
     <span data-ttu-id="6a373-158">Essa guia exibe informações detalhadas sobre os agentes e trabalhos usados por todos os tipos de replicação.</span><span class="sxs-lookup"><span data-stu-id="6a373-158">This tab displays detailed information about the agents and jobs used by all types of replication.</span></span> <span data-ttu-id="6a373-159">A guia também permite que você inicie e interrompa cada agente e trabalho.</span><span class="sxs-lookup"><span data-stu-id="6a373-159">The tab also allows you to start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="6a373-160">Para obter mais informações, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6a373-160">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="6a373-161">O Replication Monitor também fornece um menu de contexto para o nó Publicador.</span><span class="sxs-lookup"><span data-stu-id="6a373-161">Replication Monitor also provides a context menu for the Publisher node.</span></span> <span data-ttu-id="6a373-162">Clique com o botão direito do mouse em um Publicador no painel esquerdo para:</span><span class="sxs-lookup"><span data-stu-id="6a373-162">Right-click a Publisher in the left pane to:</span></span>  
  
-   <span data-ttu-id="6a373-163">Editar as configurações do Replication Monitor para o Publicador</span><span class="sxs-lookup"><span data-stu-id="6a373-163">Edit Replication Monitor settings for the Publisher</span></span>  
  
-   <span data-ttu-id="6a373-164">Remover o Publicador do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="6a373-164">Remove the Publisher from Replication Monitor</span></span>  
  
-   <span data-ttu-id="6a373-165">Exibir e editar perfis de agente</span><span class="sxs-lookup"><span data-stu-id="6a373-165">View and edit agent profiles</span></span>  
  
-   <span data-ttu-id="6a373-166">Conectar-se ou desconectar-se do Distribuidor que armazena informações sobre o Publicador</span><span class="sxs-lookup"><span data-stu-id="6a373-166">Connect to or disconnect from the Distributor that stores information about the Publisher</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publications"></a><span data-ttu-id="6a373-167">Exibindo informações e executando tarefas relacionadas a publicações</span><span class="sxs-lookup"><span data-stu-id="6a373-167">Viewing Information and Performing Tasks Related to Publications</span></span>  
 <span data-ttu-id="6a373-168">O Replication Monitor exibe informações sobre publicações em três guias e várias janelas de detalhes:</span><span class="sxs-lookup"><span data-stu-id="6a373-168">Replication Monitor displays information about publications on three tabs and a number of detail windows:</span></span>  
  
-   <span data-ttu-id="6a373-169">Guia**Todas as Assinaturas**</span><span class="sxs-lookup"><span data-stu-id="6a373-169">**All Subscriptions** tab</span></span>  
  
     <span data-ttu-id="6a373-170">Essa guia exibe informações sobre todas as assinaturas para a publicação selecionada.</span><span class="sxs-lookup"><span data-stu-id="6a373-170">This tab displays information about all subscriptions to the selected publication.</span></span> <span data-ttu-id="6a373-171">Por padrão, essa guia é classificada por ordem de prioridade: erros, avisos e, em seguida, em ordem crescente de desempenho, com qualquer assinatura de baixo desempenho na parte superior.</span><span class="sxs-lookup"><span data-stu-id="6a373-171">By default, this tab is sorted in priority order: errors, then warnings, then in increasing order of performance, with any poorly performing subscriptions at the top.</span></span>  
  
     <span data-ttu-id="6a373-172">A guia **Todas as Assinaturas** ajuda a responder as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="6a373-172">The **All Subscriptions** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="6a373-173">Quais assinaturas estão lentas?</span><span class="sxs-lookup"><span data-stu-id="6a373-173">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="6a373-174">Defina as opções nessa guia de forma que a grade exiba as assinaturas em ordem de desempenho relativo.</span><span class="sxs-lookup"><span data-stu-id="6a373-174">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="6a373-175">Meu sistema de replicação está íntegro?</span><span class="sxs-lookup"><span data-stu-id="6a373-175">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="6a373-176">A grade nessa guia exibe ícones de erro e advertência de qualquer assinatura que exija sua atenção.</span><span class="sxs-lookup"><span data-stu-id="6a373-176">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
-   <span data-ttu-id="6a373-177">Guia**Agentes**</span><span class="sxs-lookup"><span data-stu-id="6a373-177">**Agents** tab</span></span>  
  
     <span data-ttu-id="6a373-178">Essa guia exibe informações sobre os agentes que são usados pela replicação.</span><span class="sxs-lookup"><span data-stu-id="6a373-178">This tab displays information about the agents that are used by replication.</span></span> <span data-ttu-id="6a373-179">Essa guia exibe informações sobre os seguintes agentes:</span><span class="sxs-lookup"><span data-stu-id="6a373-179">This tab displays information about the following agents:</span></span>  
  
    -   <span data-ttu-id="6a373-180">O Agente de Instantâneo, que é usado por todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="6a373-180">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="6a373-181">O Agente de Leitor de Log, que é usado por todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="6a373-181">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="6a373-182">O Agente de Leitor de Fila, que é usado pelas publicações transacionais habilitadas para atualização de assinaturas em fila.</span><span class="sxs-lookup"><span data-stu-id="6a373-182">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="6a373-183">A guia também permite que você execute as seguintes tarefas: acessar informações detalhadas sobre cada agente e iniciar e interromper cada agente.</span><span class="sxs-lookup"><span data-stu-id="6a373-183">The tab also allows for you to perform the following tasks: access detailed information about each agent, and start and stop each agent.</span></span> <span data-ttu-id="6a373-184">Para obter mais informações sobre os agentes associados a assinaturas (Agente de Distribuição e Agente de Mesclagem), consulte a seção “Exibindo informações e tarefas de desempenho relacionadas a assinaturas”, neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6a373-184">For information about agents that are associated with subscriptions (the Distribution Agent and Merge Agent), see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
-   <span data-ttu-id="6a373-185">Guia**Avisos**</span><span class="sxs-lookup"><span data-stu-id="6a373-185">**Warnings** tab</span></span>  
  
     <span data-ttu-id="6a373-186">Esta guia permite especificar avisos e alertas para agentes.</span><span class="sxs-lookup"><span data-stu-id="6a373-186">This tab enables you to specify warnings and alerts for agents.</span></span> <span data-ttu-id="6a373-187">Para obter mais informações, consulte [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6a373-187">For more information, see [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="6a373-188">Guia**Tokens de Rastreamento** (somente para replicação transacional)</span><span class="sxs-lookup"><span data-stu-id="6a373-188">**Tracer Tokens** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="6a373-189">Essa guia permite medir a latência, o período decorrido entre a confirmação de uma transação no Publicador e a confirmação da transação correspondente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="6a373-189">This tab allows you to measure latency, the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="6a373-190">Essa guia ajuda a responder a seguinte pergunta:</span><span class="sxs-lookup"><span data-stu-id="6a373-190">This tab helps answers the following question:</span></span>  
  
    -   <span data-ttu-id="6a373-191">Quanto tempo uma transação confirmada agora, levará para alcançar um Assinante em replicação transacional?</span><span class="sxs-lookup"><span data-stu-id="6a373-191">How long will it take a transaction committed now to reach a Subscriber in transactional replication?</span></span>  
  
         <span data-ttu-id="6a373-192">Exiba o período total para uma transação viajar pelo sistema e também o compare com os intervalos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6a373-192">View the total time for a transaction to travel through the system and also compare it to previous times.</span></span>  
  
     <span data-ttu-id="6a373-193">Essa guia não é exibida para Distribuidores que executam o [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] ou versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="6a373-193">This tab is not displayed for Distributors running [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span> <span data-ttu-id="6a373-194">Para obter mais informações sobre tokens de rastreamento, consulte [Medir a latência e validar as conexões para a replicação transacional](measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="6a373-194">For more information on tracer tokens, see [Measure Latency and Validate Connections for Transactional Replication](measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="6a373-195">Janelas de detalhes para agentes associados a uma publicação.</span><span class="sxs-lookup"><span data-stu-id="6a373-195">Detail windows for the agents associated with a publication.</span></span> <span data-ttu-id="6a373-196">Os seguintes agentes são associados a publicações:</span><span class="sxs-lookup"><span data-stu-id="6a373-196">The following agents are associated with publications:</span></span>  
  
    -   <span data-ttu-id="6a373-197">O Agente de Instantâneo, que é usado por todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="6a373-197">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="6a373-198">O Agente de Leitor de Log, que é usado por todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="6a373-198">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="6a373-199">O Agente de Leitor de Fila, que é usado pelas publicações transacionais habilitadas para atualização de assinaturas em fila.</span><span class="sxs-lookup"><span data-stu-id="6a373-199">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="6a373-200">Clique duas vezes em um agente no Replication Monitor para acessar informações em uma janela de detalhes.</span><span class="sxs-lookup"><span data-stu-id="6a373-200">Double-click an agent in Replication Monitor to access information in a detail window.</span></span> <span data-ttu-id="6a373-201">Além dos agentes listados acima, existem agentes associados a assinaturas: o Agente de Distribuição para assinaturas em instantâneos e publicações transacionais; e o Agente de Mesclagem para assinaturas em publicações de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="6a373-201">In addition to the agents listed above, there are agents associated with subscriptions: the Distribution Agent for subscriptions to snapshot and transactional publications; and the Merge Agent for subscriptions to merge publications.</span></span> <span data-ttu-id="6a373-202">Para obter mais informações, consulte a seção “Exibindo informações e desempenhando tarefas relacionadas a assinaturas” neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6a373-202">For more information, see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
     <span data-ttu-id="6a373-203">As janelas de detalhes do agente fornecem informações sobre sessões dos agentes, inclusive hora de início, hora de término, duração e ações executadas em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6a373-203">The agent detail windows provide information about agent sessions, including start time, end time, duration, and the actions performed in a session.</span></span> <span data-ttu-id="6a373-204">Elas ajudam a responder a seguinte pergunta:</span><span class="sxs-lookup"><span data-stu-id="6a373-204">They help to answer the following question:</span></span>  
  
    -   <span data-ttu-id="6a373-205">Por que um agente não está executando?</span><span class="sxs-lookup"><span data-stu-id="6a373-205">Why is an agent not running?</span></span>  
  
         <span data-ttu-id="6a373-206">As mensagens de erro disponíveis fornecem informações detalhadas sobre o motivo de o agente não estar em execução e fornece o ponto inicial para solução de problemas com agentes associados a uma publicação.</span><span class="sxs-lookup"><span data-stu-id="6a373-206">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a publication.</span></span>  
  
 <span data-ttu-id="6a373-207">Para obter mais informações, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6a373-207">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="6a373-208">O Replication Monitor também fornece um menu de contexto para o nó de publicações.</span><span class="sxs-lookup"><span data-stu-id="6a373-208">Replication Monitor also provides a context menu for the publications node.</span></span> <span data-ttu-id="6a373-209">Clique com o botão direito do mouse em uma publicação no painel esquerdo para:</span><span class="sxs-lookup"><span data-stu-id="6a373-209">Right-click a publication in the left pane to:</span></span>  
  
-   <span data-ttu-id="6a373-210">Reiniciar todas as assinaturas em uma publicação</span><span class="sxs-lookup"><span data-stu-id="6a373-210">Reinitialize all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="6a373-211">Validar todas as assinaturas em uma publicação</span><span class="sxs-lookup"><span data-stu-id="6a373-211">Validate all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="6a373-212">Gerar um instantâneo para uma publicação</span><span class="sxs-lookup"><span data-stu-id="6a373-212">Generate a snapshot for a publication</span></span>  
  
-   <span data-ttu-id="6a373-213">Exibir e editar as propriedades da publicação</span><span class="sxs-lookup"><span data-stu-id="6a373-213">View and edit publication properties</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-subscriptions"></a><span data-ttu-id="6a373-214">Exibindo informações e executando tarefas relacionadas a assinaturas</span><span class="sxs-lookup"><span data-stu-id="6a373-214">Viewing Information and Performing Tasks Related to Subscriptions</span></span>  
 <span data-ttu-id="6a373-215">O Replication Monitor exibe informações sobre assinaturas em várias guias diferentes.</span><span class="sxs-lookup"><span data-stu-id="6a373-215">Replication Monitor displays information about subscriptions on a number of different tabs.</span></span> <span data-ttu-id="6a373-216">Clique duas vezes em uma assinatura no Replication Monitor para acessar essas guias em uma janela de detalhes.</span><span class="sxs-lookup"><span data-stu-id="6a373-216">Double-click a subscription in Replication Monitor to access these tabs in a detail window.</span></span> <span data-ttu-id="6a373-217">Todas as guias são úteis para responder a pergunta "Por que um agente não está em execução?"</span><span class="sxs-lookup"><span data-stu-id="6a373-217">All of the tabs are useful in answering the question "Why is an agent not running?"</span></span> <span data-ttu-id="6a373-218">As mensagens de erro disponíveis fornecem informações detalhadas sobre o motivo de o agente não estar em execução e fornece um ponto inicial para solução de problemas com agentes associados a uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="6a373-218">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a subscription.</span></span>  
  
-   <span data-ttu-id="6a373-219">**Guia Todas as Assinaturas** e **guia Lista de Observação da Assinatura**</span><span class="sxs-lookup"><span data-stu-id="6a373-219">**All Subscriptions tab** and **Subscription Watch List tab.**</span></span>  
  
     <span data-ttu-id="6a373-220">Essas guias foram descritas anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6a373-220">These tabs are described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="6a373-221">Guia**Histórico do Publicador para o Distribuidor** (somente replicação transacional)</span><span class="sxs-lookup"><span data-stu-id="6a373-221">**Publisher to Distributor History** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="6a373-222">Essa guia exibe informações sobre o Agente de Leitor de Log para uma publicação (a guia é idêntica à janela de detalhes do Agente de Leitor de Log).</span><span class="sxs-lookup"><span data-stu-id="6a373-222">This tab displays information on the Log Reader Agent for a publication (the tab is identical to the Log Reader Agent details window).</span></span>  
  
-   <span data-ttu-id="6a373-223">Guia**Histórico do Distribuidor para o Assinante** (replicação de instantâneo e replicação transacional)</span><span class="sxs-lookup"><span data-stu-id="6a373-223">**Distributor to Subscriber History** tab (snapshot replication and transactional replication)</span></span>  
  
     <span data-ttu-id="6a373-224">Essa guia exibe informações sobre o Agente de Distribuição de uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="6a373-224">This tab displays information on the Distribution Agent for a subscription.</span></span>  
  
-   <span data-ttu-id="6a373-225">Guia**Comandos Não Distribuídos** (somente replicação transacional)</span><span class="sxs-lookup"><span data-stu-id="6a373-225">**Undistributed Commands** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="6a373-226">Essa guia exibe informações sobre o número de comandos no banco de dados de distribuição que não foram entregues ao Assinante selecionado e o tempo estimado para entrega desses comandos.</span><span class="sxs-lookup"><span data-stu-id="6a373-226">This tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="6a373-227">A guia ajuda a responder a pergunta "Quanto minha assinatura está atrasada?"</span><span class="sxs-lookup"><span data-stu-id="6a373-227">The tab helps answer the question, "How far behind is my subscription?"</span></span> <span data-ttu-id="6a373-228">Essa guia não é exibida para Distribuidores que executam versões anteriores ao SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="6a373-228">This tab is not displayed for Distributors running versions prior to SQL Server 2005.</span></span>  
  
-   <span data-ttu-id="6a373-229">Guia**Histórico de Sincronização** (somente replicação de mesclagem)</span><span class="sxs-lookup"><span data-stu-id="6a373-229">**Synchronization History** tab (merge replication only)</span></span>  
  
     <span data-ttu-id="6a373-230">Essa guia exibe informações sobre o Agente de Mesclagem para uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="6a373-230">This tab displays information on the Merge Agent for a subscription.</span></span> <span data-ttu-id="6a373-231">Essa guia ajuda a responder a seguinte pergunta:</span><span class="sxs-lookup"><span data-stu-id="6a373-231">This tab helps answer the following question:</span></span>  
  
    -   <span data-ttu-id="6a373-232">Por que minha assinatura de mesclagem está lenta?</span><span class="sxs-lookup"><span data-stu-id="6a373-232">Why is my merge subscription slow?</span></span>  
  
         <span data-ttu-id="6a373-233">Essa guia fornece estatísticas detalhadas para cada artigo processado durante a sincronização, inclusive o tempo gasto em cada fase de processamento (carregar alterações, baixar alterações e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="6a373-233">This tab provides detailed statistics for each article processed during synchronization, including the amount of time spent in each processing phase (uploading changes, downloading changes, and so on).</span></span> <span data-ttu-id="6a373-234">Ela pode ajudar a definir tabelas específicas que estão provocando lentidão e é o melhor local para a solução de problemas de desempenho com assinaturas de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="6a373-234">It can help pinpoint specific tables that are causing slowdowns and is the best place to troubleshoot performance issues with merge subscriptions.</span></span>  
  
 <span data-ttu-id="6a373-235">Para obter mais informações, confira [Exibir informações e executar tarefas usando o Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6a373-235">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>
  
## <a name="viewing-information-and-performing-tasks-related-to-agent-profiles"></a><span data-ttu-id="6a373-236">Exibindo informações e executando tarefas relacionadas a perfis de agente</span><span class="sxs-lookup"><span data-stu-id="6a373-236">Viewing Information and Performing Tasks Related to Agent Profiles</span></span>  
 <span data-ttu-id="6a373-237">O Replication Monitor inclui várias caixas de diálogo para gerenciar os perfis de agente.</span><span class="sxs-lookup"><span data-stu-id="6a373-237">Replication Monitor includes a number of dialog boxes for managing agent profiles.</span></span> <span data-ttu-id="6a373-238">Os perfis de agente são conjuntos de parâmetros para um agente que determinam seu comportamento.</span><span class="sxs-lookup"><span data-stu-id="6a373-238">Agent profiles are sets of parameters for an agent that determine agent behavior.</span></span> <span data-ttu-id="6a373-239">Para saber mais, confira [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6a373-239">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span> <span data-ttu-id="6a373-240">As caixas de diálogo são:</span><span class="sxs-lookup"><span data-stu-id="6a373-240">The dialog boxes are:</span></span>  
  
-   <span data-ttu-id="6a373-241">**Perfis de Agente**</span><span class="sxs-lookup"><span data-stu-id="6a373-241">**Agent Profiles**</span></span>  
  
     <span data-ttu-id="6a373-242">Essa caixa de diálogo permite: alterar as propriedades dos perfis, criar e excluir perfis, especificar um perfil padrão e especificar que todos os agentes de um tipo específico (como os Agente de Instantâneos) devem usar um determinado perfil.</span><span class="sxs-lookup"><span data-stu-id="6a373-242">This dialog box allows you to: change the properties of profiles; create and delete profiles; specify a default profile; and specify that all agents of a specific type (such as Snapshot Agents) should use a given profile.</span></span>  
  
-   <span data-ttu-id="6a373-243">**\<AgentProfileName> Propriedades**</span><span class="sxs-lookup"><span data-stu-id="6a373-243">**\<AgentProfileName> Properties**</span></span>  
  
     <span data-ttu-id="6a373-244">Essa caixa de diálogo permite exibir e editar os parâmetros de configuração em um perfil.</span><span class="sxs-lookup"><span data-stu-id="6a373-244">This dialog box allows you to view and edit the parameter settings in a profile.</span></span>  
  
-   <span data-ttu-id="6a373-245">**Novo Perfil de Agente**</span><span class="sxs-lookup"><span data-stu-id="6a373-245">**New Agent Profile**</span></span>  
  
     <span data-ttu-id="6a373-246">Essa caixa de diálogo permite criar um novo perfil, com a inclusão opcional dos valores de um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="6a373-246">This dialog box allows you to create a new profile, optionally including the values from an existing profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a373-247">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a373-247">See Also</span></span>  
 [<span data-ttu-id="6a373-248">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="6a373-248">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
