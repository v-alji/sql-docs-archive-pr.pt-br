---
title: Caixa de diálogo Replicação do SQL Server ' informações do editor ' | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.publications.f1
ms.assetid: 0b2e3d4e-03b7-4c31-8f96-48648d750010
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3797ae4f9fe8f42b4abec715c63bc627c2a62cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679849"
---
# <a name="sql-server-replication-publisher-information-dialog-box"></a><span data-ttu-id="ac218-102">Caixa de diálogo Replicação do SQL Server ' informações do editor '</span><span class="sxs-lookup"><span data-stu-id="ac218-102">SQL Server Replication 'Publisher Information' dialog box</span></span>
  <span data-ttu-id="ac218-103">A guia **Publicações** fornece informações resumidas sobre todas as publicações no Publicador selecionado no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="ac218-103">The **Publications** tab provides summary information for all publications at the Publisher selected in the left pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac218-104">Opções</span><span class="sxs-lookup"><span data-stu-id="ac218-104">Options</span></span>  
 <span data-ttu-id="ac218-105">Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="ac218-105">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="ac218-106">**Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="ac218-106">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="ac218-107">**Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="ac218-107">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="ac218-108">**Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="ac218-108">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="ac218-109">**Limpar Filtro**: limpe as configurações de filtro da grade.</span><span class="sxs-lookup"><span data-stu-id="ac218-109">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="ac218-110">As configurações de filtro são específicas de cada grade.</span><span class="sxs-lookup"><span data-stu-id="ac218-110">Filter settings are specific to each grid.</span></span> <span data-ttu-id="ac218-111">A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="ac218-111">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="ac218-112">**Status**</span><span class="sxs-lookup"><span data-stu-id="ac218-112">**Status**</span></span>  
 <span data-ttu-id="ac218-113">O estado de cada publicação que é determinado pelo status de prioridade mais alta de suas assinaturas.</span><span class="sxs-lookup"><span data-stu-id="ac218-113">The status of each publication, which is determined by the highest priority status of its subscriptions.</span></span> <span data-ttu-id="ac218-114">Por padrão, a grade que contém informações de publicação é classificada pela coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="ac218-114">By default, the grid containing publication information is sorted by the **Status** column.</span></span> <span data-ttu-id="ac218-115">A lista a seguir mostra os valores de status possíveis e a ordem de classificação dos valores (por exemplo, erros são sempre mostrados na parte superior da grade):</span><span class="sxs-lookup"><span data-stu-id="ac218-115">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid):</span></span>  
  
-   <span data-ttu-id="ac218-116">Erro</span><span class="sxs-lookup"><span data-stu-id="ac218-116">Error</span></span>  
  
-   <span data-ttu-id="ac218-117">Desempenho crítico</span><span class="sxs-lookup"><span data-stu-id="ac218-117">Performance critical</span></span>  
  
-   <span data-ttu-id="ac218-118">Tentando novamente comando com falha</span><span class="sxs-lookup"><span data-stu-id="ac218-118">Retrying failed command</span></span>  
  
-   <span data-ttu-id="ac218-119">OK</span><span class="sxs-lookup"><span data-stu-id="ac218-119">OK</span></span>  
  
 <span data-ttu-id="ac218-120">O valor de status **Desempenho Crítico** é relevante para assinaturas transacionais e assinaturas de mesclagem; em assinaturas transacionais, ele só poderá ser exibido se for definido um limite.</span><span class="sxs-lookup"><span data-stu-id="ac218-120">The status value **Performance critical** is relevant for transactional subscriptions and merge subscriptions; for transactional subscriptions, it can be displayed only if a threshold is set.</span></span> <span data-ttu-id="ac218-121">Para obter informações sobre medidas de desempenho e definir limites, consulte [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (Monitorar o desempenho com o Replication Monitor) e [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) (Definir limites e avisos no Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="ac218-121">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="ac218-122">**Publicação**</span><span class="sxs-lookup"><span data-stu-id="ac218-122">**Publication**</span></span>  
 <span data-ttu-id="ac218-123">O nome de cada publicação, no formato *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="ac218-123">The name of each publication, in the form *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="ac218-124">**Assinaturas**</span><span class="sxs-lookup"><span data-stu-id="ac218-124">**Subscriptions**</span></span>  
 <span data-ttu-id="ac218-125">O número de assinaturas para cada publicação.</span><span class="sxs-lookup"><span data-stu-id="ac218-125">The number of subscriptions for each publication.</span></span>  
  
 <span data-ttu-id="ac218-126">**Sincronizando**</span><span class="sxs-lookup"><span data-stu-id="ac218-126">**Synchronizing**</span></span>  
 <span data-ttu-id="ac218-127">O número de assinaturas que está sendo sincronizado no momento para cada publicação:</span><span class="sxs-lookup"><span data-stu-id="ac218-127">The number of subscriptions for each publication that are currently synchronizing:</span></span>  
  
-   <span data-ttu-id="ac218-128">Na replicação transacional, "sincronizando" significa que o Distribution Agent está sendo executado, mas os dados não estão sendo necessariamente replicados.</span><span class="sxs-lookup"><span data-stu-id="ac218-128">For transactional replication, "synchronizing" means that the Distribution Agent is running, but data is not necessarily being replicated.</span></span>  
  
-   <span data-ttu-id="ac218-129">Na replicação de mesclagem, "sincronizando" significa que o Merge Agent está sendo executado e que os dados estão sendo replicados no momento.</span><span class="sxs-lookup"><span data-stu-id="ac218-129">For merge replication, "synchronizing" means that the Merge Agent is running and that data is currently being replicated.</span></span>  
  
-   <span data-ttu-id="ac218-130">Na replicação de instantâneo, "sincronizando" significa que o Distribution Agent está sendo executado e que os dados estão sendo replicados no momento.</span><span class="sxs-lookup"><span data-stu-id="ac218-130">For snapshot replication, "synchronizing" means that the Distribution Agent is running and that data is currently being replicated.</span></span>  
  
 <span data-ttu-id="ac218-131">**Desempenho Médio Atual** e **Pior Desempenho Atual**</span><span class="sxs-lookup"><span data-stu-id="ac218-131">**Current Average Performance** and **Current Worst Performance**</span></span>  
 <span data-ttu-id="ac218-132">Somente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="ac218-132">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="ac218-133">A classificação de desempenho médio e do pior desempenho atual, respectivamente, para todas as assinaturas em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="ac218-133">The average performance rating and the worst performance rating, respectively, for all subscriptions to a publication.</span></span> <span data-ttu-id="ac218-134">As classificações têm base nas medidas mais atuais calculadas pelo Replication Monitor e não refletem o desempenho de uma assinatura ao longo de tempo.</span><span class="sxs-lookup"><span data-stu-id="ac218-134">Ratings are based on the most recent measurements taken by Replication Monitor and do not reflect the performance of a subscription over time.</span></span>  
  
 <span data-ttu-id="ac218-135">Para replicação transacional, o Replication Monitor exibe só um valor para publicações com limites de desempenho definidos.</span><span class="sxs-lookup"><span data-stu-id="ac218-135">For transactional replication, Replication Monitor displays a value only for publications that have performance thresholds defined.</span></span> <span data-ttu-id="ac218-136">Se os limites de desempenho não estiverem definidos para uma publicação, essa coluna exibirá **Não Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="ac218-136">If performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="ac218-137">Para replicação de mesclagem, o Replication Monitor exibe um valor após a ocorrência de cinco sincronizações com 50 ou mais alterações cada no mesmo tipo de conexão (discada ou LAN).</span><span class="sxs-lookup"><span data-stu-id="ac218-137">For merge replication, Replication Monitor displays a value after five synchronizations have occurred with 50 or more changes each over the same type of connection (dial-up or LAN).</span></span> <span data-ttu-id="ac218-138">Se houver menos de cinco sincronizações com 50 ou mais alterações ou se a sincronização mais recente tiver menos de 50 alterações, essa coluna ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="ac218-138">If there have been less than five synchronizations with 50 or more changes or the most recent synchronization has less than 50 changes, this column is blank.</span></span>  
  
 <span data-ttu-id="ac218-139">A classificação de desempenho é um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ac218-139">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="ac218-140">Excelente</span><span class="sxs-lookup"><span data-stu-id="ac218-140">Excellent</span></span>  
  
-   <span data-ttu-id="ac218-141">Bom</span><span class="sxs-lookup"><span data-stu-id="ac218-141">Good</span></span>  
  
-   <span data-ttu-id="ac218-142">Razoável</span><span class="sxs-lookup"><span data-stu-id="ac218-142">Fair</span></span>  
  
-   <span data-ttu-id="ac218-143">Fraco</span><span class="sxs-lookup"><span data-stu-id="ac218-143">Poor</span></span>  
  
-   <span data-ttu-id="ac218-144">Crítico</span><span class="sxs-lookup"><span data-stu-id="ac218-144">Critical</span></span>  
  
 <span data-ttu-id="ac218-145">Para obter mais informações sobre como as classificações de desempenho são definidas e como os limites de desempenho são configurados, consulte [Monitorar o desempenho com o Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ac218-145">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac218-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ac218-146">See Also</span></span>  
 <span data-ttu-id="ac218-147">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="ac218-147">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="ac218-148">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="ac218-148">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="ac218-149">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="ac218-149">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
