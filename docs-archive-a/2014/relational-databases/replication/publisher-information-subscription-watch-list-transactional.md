---
title: Informações do Publicador, lista de inspeção da assinatura (publicação transacional, SQL Server 2005 e posterior) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.tran.f1
ms.assetid: 6bc64ddb-5c86-4681-a391-77fc1d3c4e6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bf6d151b75bca1dbfd2e5ad8f7601fb1002e84be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568444"
---
# <a name="publisher-information-subscription-watch-list-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="4bd8b-102">Informações do Publicador, Lista de Observação da Assinatura (publicação transacional, SQL Server 2005 e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="4bd8b-102">Publisher Information, Subscription Watch List (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="4bd8b-103">A guia **Lista de Observação da Assinatura** está disponível para os Distribuidores que executam o SQL Server 2005 e versões posteriores; seu propósito é exibir informações sobre assinaturas de todas as publicações disponíveis no Publicador selecionado.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-103">The **Subscription Watch List** tab is available for Distributors running SQL Server 2005 and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="4bd8b-104">Você pode filtrar a lista de assinaturas para ver erros, avisos e qualquer assinatura de desempenho insatisfatório.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="4bd8b-105">Essa guia fornece um único local para o administrador monitorar todas as atividades de replicação em um Publicador: o Replication Monitor exibe todas as assinaturas que exigem atenção, com base no tipo de replicação selecionado e na opção escolhida na caixa de listagem suspensa **Mostrar** .</span><span class="sxs-lookup"><span data-stu-id="4bd8b-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="4bd8b-106">Como os itens mostrados nessa guia são baseados no status atual e no desempenho, as assinaturas serão exibidas nessa página somente se corresponderem à opção da caixa de listagem **Mostrar** naquele momento.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4bd8b-107">Opções</span><span class="sxs-lookup"><span data-stu-id="4bd8b-107">Options</span></span>  
 <span data-ttu-id="4bd8b-108">Para obter informações mais detalhadas e tarefas relacionadas a uma assinatura, clique com o botão direito do mouse na linha dessa assinatura e clique em uma opção no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="4bd8b-109">Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="4bd8b-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="4bd8b-110">**Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="4bd8b-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="4bd8b-111">**Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="4bd8b-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="4bd8b-112">**Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="4bd8b-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="4bd8b-113">**Limpar Filtro**: limpe as configurações de filtro da grade.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="4bd8b-114">As configurações de filtro são específicas de cada grade.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="4bd8b-115">A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="4bd8b-116">**Mostrar Assinaturas Transacionais**</span><span class="sxs-lookup"><span data-stu-id="4bd8b-116">**Show Transactional Subscriptions**</span></span>  
 <span data-ttu-id="4bd8b-117">Selecione o tipo de assinatura (transacional, instantâneo ou mesclagem) a ser exibida para o Publicador selecionado.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="4bd8b-118">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="4bd8b-118">**Show**</span></span>  
 <span data-ttu-id="4bd8b-119">Selecione os estados de assinatura a serem exibidos para o tipo de assinatura selecionado.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="4bd8b-120">Por exemplo, você pode optar por exibir somente as assinaturas que tiverem um erro.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="4bd8b-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="4bd8b-121">**Status**</span></span>  
 <span data-ttu-id="4bd8b-122">O status de cada assinatura, determinado pelo status do Distribution Agent ou do Log Reader Agent (o status com prioridade mais alta é exibido; o status também pode ser determinado pelo Queue Reader Agent, se assinaturas de atualização enfileiradas forem usadas).</span><span class="sxs-lookup"><span data-stu-id="4bd8b-122">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="4bd8b-123">Por padrão, a grade que contém informações de assinatura é classificada pela coluna **Status** (e depois pela coluna **Desempenho** para assinaturas com o mesmo status).</span><span class="sxs-lookup"><span data-stu-id="4bd8b-123">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="4bd8b-124">A lista a seguir mostra os valores de status possíveis e a ordem de classificação dos valores (por exemplo, os erros são sempre mostrados na parte superior da grade).</span><span class="sxs-lookup"><span data-stu-id="4bd8b-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="4bd8b-125">Erro</span><span class="sxs-lookup"><span data-stu-id="4bd8b-125">Error</span></span>  
  
-   <span data-ttu-id="4bd8b-126">Desempenho crítico</span><span class="sxs-lookup"><span data-stu-id="4bd8b-126">Performance critical</span></span>  
  
-   <span data-ttu-id="4bd8b-127">Expirando em breve/Expirado</span><span class="sxs-lookup"><span data-stu-id="4bd8b-127">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="4bd8b-128">Assinatura não inicializada</span><span class="sxs-lookup"><span data-stu-id="4bd8b-128">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="4bd8b-129">Tentando novamente comando com falha</span><span class="sxs-lookup"><span data-stu-id="4bd8b-129">Retrying failed command</span></span>  
  
-   <span data-ttu-id="4bd8b-130">Não está em execução</span><span class="sxs-lookup"><span data-stu-id="4bd8b-130">Not Running</span></span>  
  
-   <span data-ttu-id="4bd8b-131">Executando</span><span class="sxs-lookup"><span data-stu-id="4bd8b-131">Running</span></span>  
  
 <span data-ttu-id="4bd8b-132">A ordem de classificação também determina qual valor será exibido se uma determinada assinatura estiver em mais de um estado.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-132">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="4bd8b-133">Por exemplo, se uma assinatura tiver um erro e expirar em breve, a coluna **Status** exibirá **Erro**.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-133">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="4bd8b-134">Os valores de status **Desempenho crítico**, **Expirando em breve/Expirado**e **Assinatura não inicializada** são avisos.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-134">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="4bd8b-135">Quando um aviso é exibido, a coluna **Status** também exibe se um agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-135">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="4bd8b-136">Por exemplo, o status poderia ser **Executando, Desempenho crítico**.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-136">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="4bd8b-137">Os valores de status **Desempenho crítico** e **Expirando em breve/Expirado** só serão exibidos se os limites forem definidos.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-137">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="4bd8b-138">Para obter informações sobre medidas de desempenho e definir limites, consulte [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (Monitorar o desempenho com o Replication Monitor) e [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) (Definir limites e avisos no Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="4bd8b-138">For information about performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="4bd8b-139">**Assinatura**</span><span class="sxs-lookup"><span data-stu-id="4bd8b-139">**Subscription**</span></span>  
 <span data-ttu-id="4bd8b-140">O nome de cada assinatura no formato: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-140">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="4bd8b-141">**Publicação**</span><span class="sxs-lookup"><span data-stu-id="4bd8b-141">**Publication**</span></span>  
 <span data-ttu-id="4bd8b-142">O nome da publicação com a qual uma assinatura é sincronizada, no formato: *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-142">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="4bd8b-143">**Desempenho**</span><span class="sxs-lookup"><span data-stu-id="4bd8b-143">**Performance**</span></span>  
 <span data-ttu-id="4bd8b-144">A classificação de desempenho de cada assinatura é baseada nas medidas mais atuais, calculadas pelo Replication Monitor, e, não reflete desempenho histórico.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-144">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="4bd8b-145">O desempenho é avaliado para assinaturas de publicações que têm limites de desempenho definidos; se os limites de desempenho não forem definidos para uma publicação, essa coluna exibirá **Não habilitado**.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-145">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="4bd8b-146">A classificação de desempenho é um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="4bd8b-146">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="4bd8b-147">Excelente</span><span class="sxs-lookup"><span data-stu-id="4bd8b-147">Excellent</span></span>  
  
-   <span data-ttu-id="4bd8b-148">Bom</span><span class="sxs-lookup"><span data-stu-id="4bd8b-148">Good</span></span>  
  
-   <span data-ttu-id="4bd8b-149">Razoável</span><span class="sxs-lookup"><span data-stu-id="4bd8b-149">Fair</span></span>  
  
-   <span data-ttu-id="4bd8b-150">Fraco</span><span class="sxs-lookup"><span data-stu-id="4bd8b-150">Poor</span></span>  
  
-   <span data-ttu-id="4bd8b-151">Crítico</span><span class="sxs-lookup"><span data-stu-id="4bd8b-151">Critical</span></span>  
  
 <span data-ttu-id="4bd8b-152">Se o desempenho for crítico, **Desempenho Crítico** será exibido na coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="4bd8b-152">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="4bd8b-153">Para obter mais informações sobre como as classificações de desempenho são definidas e como os limites de desempenho são configurados, consulte [Monitorar o desempenho com o Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="4bd8b-153">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="4bd8b-154">**Latência**</span><span class="sxs-lookup"><span data-stu-id="4bd8b-154">**Latency**</span></span>  
 <span data-ttu-id="4bd8b-155">É o período médio de tempo que decorre entre a confirmação de uma transação no Publicador e a confirmação da transação correspondente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-155">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="4bd8b-156">A latência exibida é baseada nas medidas mais recentes calculadas pelo Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-156">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="4bd8b-157">Para obter mais informações sobre como medir a latência, consulte [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) (Medir a latência e validar as conexões da replicação transacional).</span><span class="sxs-lookup"><span data-stu-id="4bd8b-157">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="4bd8b-158">**Última Sincronização**</span><span class="sxs-lookup"><span data-stu-id="4bd8b-158">**Last Synchronization**</span></span>  
 <span data-ttu-id="4bd8b-159">A hora da última execução do Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-159">The time when the Distribution Agent last ran.</span></span> <span data-ttu-id="4bd8b-160">Se a sincronização estiver em andamento, **Em andamento** será exibido.</span><span class="sxs-lookup"><span data-stu-id="4bd8b-160">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd8b-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4bd8b-161">See Also</span></span>  
 <span data-ttu-id="4bd8b-162">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4bd8b-162">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="4bd8b-163">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4bd8b-163">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="4bd8b-164">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="4bd8b-164">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
