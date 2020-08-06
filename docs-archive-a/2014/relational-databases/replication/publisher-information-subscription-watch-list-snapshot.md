---
title: Informações do Publicador, lista de inspeção da assinatura (publicação de instantâneo, SQL Server 2005 e posterior) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.snapshot.f1
ms.assetid: 2ebeee62-7f54-4c77-9d37-15708bc5cc23
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ea44958c81465570c036ab7dd83247fb55652f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680903"
---
# <a name="publisher-information-subscription-watch-list-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="0d66c-102">Informações do Publicador, Lista de Observação da Assinatura (publicação de instantâneo, SQL Server 2005 e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="0d66c-102">Publisher Information, Subscription Watch List (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="0d66c-103"> A guia **Lista de Observação da Assinatura** está disponível para os Distribuidores que executam o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores; seu propósito é exibir informações sobre assinaturas de todas as publicações disponíveis no Publicador selecionado.</span><span class="sxs-lookup"><span data-stu-id="0d66c-103">The **Subscription Watch List** tab is available for Distributors running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="0d66c-104">Você pode filtrar a lista de assinaturas para ver erros, avisos e qualquer assinatura de desempenho insatisfatório.</span><span class="sxs-lookup"><span data-stu-id="0d66c-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="0d66c-105">Essa guia fornece um único local para o administrador monitorar todas as atividades de replicação em um Publicador: o Replication Monitor exibe todas as assinaturas que exigem atenção, com base no tipo de replicação selecionado e na opção escolhida na caixa de listagem suspensa **Mostrar** .</span><span class="sxs-lookup"><span data-stu-id="0d66c-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="0d66c-106">Como os itens mostrados nessa guia são baseados no status atual e no desempenho, as assinaturas serão exibidas nessa página somente se corresponderem à opção da caixa de listagem **Mostrar** naquele momento.</span><span class="sxs-lookup"><span data-stu-id="0d66c-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0d66c-107">Opções</span><span class="sxs-lookup"><span data-stu-id="0d66c-107">Options</span></span>  
 <span data-ttu-id="0d66c-108">Para obter informações mais detalhadas e tarefas relacionadas a uma assinatura, clique com o botão direito do mouse na linha dessa assinatura e clique em uma opção no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="0d66c-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="0d66c-109">Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="0d66c-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="0d66c-110">**Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="0d66c-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="0d66c-111">**Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="0d66c-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="0d66c-112">**Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="0d66c-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="0d66c-113">**Limpar Filtro**: limpe as configurações de filtro da grade.</span><span class="sxs-lookup"><span data-stu-id="0d66c-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="0d66c-114">As configurações de filtro são específicas de cada grade.</span><span class="sxs-lookup"><span data-stu-id="0d66c-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="0d66c-115">A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="0d66c-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="0d66c-116">**Mostrar Assinaturas de Instantâneo**</span><span class="sxs-lookup"><span data-stu-id="0d66c-116">**Show Snapshot Subscriptions**</span></span>  
 <span data-ttu-id="0d66c-117">Selecione o tipo de assinatura (transacional, instantâneo ou mesclagem) a ser exibida para o Publicador selecionado.</span><span class="sxs-lookup"><span data-stu-id="0d66c-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="0d66c-118">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="0d66c-118">**Show**</span></span>  
 <span data-ttu-id="0d66c-119">Selecione os estados de assinatura a serem exibidos para o tipo de assinatura selecionado.</span><span class="sxs-lookup"><span data-stu-id="0d66c-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="0d66c-120">Por exemplo, você pode optar por exibir somente as assinaturas que tiverem um erro.</span><span class="sxs-lookup"><span data-stu-id="0d66c-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="0d66c-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="0d66c-121">**Status**</span></span>  
 <span data-ttu-id="0d66c-122">O status de cada assinatura, que é determinado pelo status do Snapshot Agent ou do Distribution Agent (o status com prioridade mais alta é exibido).</span><span class="sxs-lookup"><span data-stu-id="0d66c-122">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="0d66c-123">Por padrão, a grade que contém informações de assinatura é classificada pela coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="0d66c-123">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="0d66c-124">A lista a seguir mostra os valores de status possíveis e a ordem de classificação dos valores (por exemplo, os erros são sempre mostrados na parte superior da grade).</span><span class="sxs-lookup"><span data-stu-id="0d66c-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="0d66c-125">Erro</span><span class="sxs-lookup"><span data-stu-id="0d66c-125">Error</span></span>  
  
-   <span data-ttu-id="0d66c-126">Expirando em breve/Expirado</span><span class="sxs-lookup"><span data-stu-id="0d66c-126">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="0d66c-127">Assinatura não inicializada</span><span class="sxs-lookup"><span data-stu-id="0d66c-127">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="0d66c-128">Tentando novamente comando com falha</span><span class="sxs-lookup"><span data-stu-id="0d66c-128">Retrying failed command</span></span>  
  
-   <span data-ttu-id="0d66c-129">Sincronizando</span><span class="sxs-lookup"><span data-stu-id="0d66c-129">Synchronizing</span></span>  
  
-   <span data-ttu-id="0d66c-130">Não sincronizando</span><span class="sxs-lookup"><span data-stu-id="0d66c-130">Not synchronizing</span></span>  
  
 <span data-ttu-id="0d66c-131">A ordem de classificação também determina qual valor será exibido se uma determinada assinatura estiver em mais de um estado.</span><span class="sxs-lookup"><span data-stu-id="0d66c-131">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="0d66c-132">Por exemplo, se uma assinatura tiver um erro e expirar em breve, a coluna **Status** exibirá **Erro**.</span><span class="sxs-lookup"><span data-stu-id="0d66c-132">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="0d66c-133">Os valores de status **Expirando em breve/Expirado** e **Assinatura não inicializada** são avisos.</span><span class="sxs-lookup"><span data-stu-id="0d66c-133">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="0d66c-134">Quando um aviso é exibido, a coluna **Status** também exibe se um agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="0d66c-134">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="0d66c-135">Por exemplo, o status pode ser **Executando, Expirando em breve/Expirado**.</span><span class="sxs-lookup"><span data-stu-id="0d66c-135">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="0d66c-136">O valor de status **Expirando em breve/Expirado** só será exibido se for definido um limite.</span><span class="sxs-lookup"><span data-stu-id="0d66c-136">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="0d66c-137">Para obter informações sobre como definir limites, consulte [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) (Definir limites e avisos no Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="0d66c-137">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="0d66c-138">**Assinatura**</span><span class="sxs-lookup"><span data-stu-id="0d66c-138">**Subscription**</span></span>  
 <span data-ttu-id="0d66c-139">O nome de cada assinatura no formato: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="0d66c-139">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="0d66c-140">**Publicação**</span><span class="sxs-lookup"><span data-stu-id="0d66c-140">**Publication**</span></span>  
 <span data-ttu-id="0d66c-141">O nome da publicação com a qual uma assinatura é sincronizada, no formato: *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="0d66c-141">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="0d66c-142">**Última Sincronização**</span><span class="sxs-lookup"><span data-stu-id="0d66c-142">**Last Synchronization**</span></span>  
 <span data-ttu-id="0d66c-143">A hora da última execução do Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="0d66c-143">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="0d66c-144">Se a sincronização estiver em andamento, **Em andamento** será exibido.</span><span class="sxs-lookup"><span data-stu-id="0d66c-144">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d66c-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d66c-145">See Also</span></span>  
 <span data-ttu-id="0d66c-146">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0d66c-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="0d66c-147">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0d66c-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="0d66c-148">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="0d66c-148">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
