---
title: Informações da publicação, agentes (publicação transacional) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.downlevelagents.tran.f1
ms.assetid: 38ef2f54-53bb-4053-876d-86f8f06a4519
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1a3d50da15ea653a7911e65ad888d5997f47a3f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569346"
---
# <a name="publication-information-agents-transactional-publication"></a><span data-ttu-id="f53d2-102">Informações da Publicação, Agentes (publicação transacional)</span><span class="sxs-lookup"><span data-stu-id="f53d2-102">Publication Information, Agents (Transactional Publication)</span></span>
  <span data-ttu-id="f53d2-103">A guia **Agentes** exibe informações resumidas sobre os agentes para a publicação selecionada.</span><span class="sxs-lookup"><span data-stu-id="f53d2-103">The **Agents** tab displays summary information on the agents for the selected publication.</span></span> <span data-ttu-id="f53d2-104">Informações sobre o Snapshot Agent e Log Reader Agent são exibida para todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="f53d2-104">Information on the Snapshot Agent and Log Reader Agent is displayed for all transactional publications.</span></span> <span data-ttu-id="f53d2-105">Informações sobre o Queue Reader Agent são exibidas para essas publicações transacionais que estão habilitadas para assinaturas de atualização enfileirada.</span><span class="sxs-lookup"><span data-stu-id="f53d2-105">Information on the Queue Reader Agent is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f53d2-106">Opções</span><span class="sxs-lookup"><span data-stu-id="f53d2-106">Options</span></span>  
 <span data-ttu-id="f53d2-107">Para obter informações mais detalhadas e tarefas relacionadas a um agente, clique com o botão direito do mouse na linha desse agente e clique em uma opção no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="f53d2-107">For more detailed information and tasks related to an agent, right-click the row for that agent, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="f53d2-108">Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="f53d2-108">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="f53d2-109">**Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="f53d2-109">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f53d2-110">**Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="f53d2-110">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f53d2-111">**Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="f53d2-111">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="f53d2-112">**Limpar Filtro**: limpe as configurações de filtro da grade.</span><span class="sxs-lookup"><span data-stu-id="f53d2-112">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="f53d2-113">As configurações de filtro são específicas de cada grade.</span><span class="sxs-lookup"><span data-stu-id="f53d2-113">Filter settings are specific to each grid.</span></span> <span data-ttu-id="f53d2-114">A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="f53d2-114">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="f53d2-115">**Status**</span><span class="sxs-lookup"><span data-stu-id="f53d2-115">**Status**</span></span>  
 <span data-ttu-id="f53d2-116">O status de cada agente de replicação associado à publicação.</span><span class="sxs-lookup"><span data-stu-id="f53d2-116">The status of each replication agent associated with the publication.</span></span> <span data-ttu-id="f53d2-117">A seguinte lista mostra os possíveis valores de status:</span><span class="sxs-lookup"><span data-stu-id="f53d2-117">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="f53d2-118">Erro</span><span class="sxs-lookup"><span data-stu-id="f53d2-118">Error</span></span>  
  
-   <span data-ttu-id="f53d2-119">Tentando novamente comandos com falha</span><span class="sxs-lookup"><span data-stu-id="f53d2-119">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="f53d2-120">Não está sendo executado</span><span class="sxs-lookup"><span data-stu-id="f53d2-120">Not running</span></span>  
  
-   <span data-ttu-id="f53d2-121">Executando</span><span class="sxs-lookup"><span data-stu-id="f53d2-121">Running</span></span>  
  
-   <span data-ttu-id="f53d2-122">Concluído</span><span class="sxs-lookup"><span data-stu-id="f53d2-122">Completed</span></span>  
  
 <span data-ttu-id="f53d2-123">**Agente**</span><span class="sxs-lookup"><span data-stu-id="f53d2-123">**Agent**</span></span>  
 <span data-ttu-id="f53d2-124">O nome de cada agente de replicação associado à publicação.</span><span class="sxs-lookup"><span data-stu-id="f53d2-124">The name of each replication agent associated with the publication.</span></span> <span data-ttu-id="f53d2-125">O Distribution Agent é associado com assinaturas para essa publicação.</span><span class="sxs-lookup"><span data-stu-id="f53d2-125">The Distribution Agent is associated with subscriptions to this publication.</span></span> <span data-ttu-id="f53d2-126">Para obter mais informações, confira [Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="f53d2-126">For more information, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="f53d2-127">**Hora da última inicialização**</span><span class="sxs-lookup"><span data-stu-id="f53d2-127">**Last Start Time**</span></span>  
 <span data-ttu-id="f53d2-128">A última vez que o agente foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="f53d2-128">The last time the agent started.</span></span>  
  
 <span data-ttu-id="f53d2-129">**Duration**</span><span class="sxs-lookup"><span data-stu-id="f53d2-129">**Duration**</span></span>  
 <span data-ttu-id="f53d2-130">O tempo durante o qual o agente foi executado.</span><span class="sxs-lookup"><span data-stu-id="f53d2-130">The amount of time the agent has run.</span></span> <span data-ttu-id="f53d2-131">O tempo representa o tempo decorrido, se o agente estiver sendo executado no momento, e o tempo total, se o agente foi executado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f53d2-131">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="f53d2-132">**Última Ação**</span><span class="sxs-lookup"><span data-stu-id="f53d2-132">**Last Action**</span></span>  
 <span data-ttu-id="f53d2-133">A última ação executada durante a execução mais recente do agente.</span><span class="sxs-lookup"><span data-stu-id="f53d2-133">The last action performed during the most recent run of the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53d2-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f53d2-134">See Also</span></span>  
 <span data-ttu-id="f53d2-135">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f53d2-135">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f53d2-136">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f53d2-136">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="f53d2-137">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="f53d2-137">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
