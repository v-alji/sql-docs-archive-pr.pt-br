---
title: Informações da publicação, todas as assinaturas (publicação transacional) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.tran.f1
ms.assetid: 7073350c-f667-4f70-88e9-152c9a1b08dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccc34bbe0933f4558478bd1d8276898219016e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570630"
---
# <a name="publication-information-all-subscriptions-transactional-publication"></a><span data-ttu-id="448aa-102">Informações da Publicação, Todas as Assinaturas (publicação transacional)</span><span class="sxs-lookup"><span data-stu-id="448aa-102">Publication Information, All Subscriptions (Transactional Publication)</span></span>
  <span data-ttu-id="448aa-103">A guia **Todas as Assinaturas** exibe informações sobre todas as assinaturas na publicação transacional selecionada.</span><span class="sxs-lookup"><span data-stu-id="448aa-103">The **All Subscriptions** tab displays information on all subscriptions to the selected transactional publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="448aa-104">Opções</span><span class="sxs-lookup"><span data-stu-id="448aa-104">Options</span></span>  
 <span data-ttu-id="448aa-105">Para obter informações mais detalhadas e tarefas relacionadas a uma assinatura, clique com o botão direito do mouse na linha dessa assinatura e clique em uma opção no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="448aa-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="448aa-106">Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="448aa-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="448aa-107">**Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="448aa-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="448aa-108">**Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="448aa-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="448aa-109">**Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="448aa-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="448aa-110">**Limpar Filtro**: limpe as configurações de filtro da grade.</span><span class="sxs-lookup"><span data-stu-id="448aa-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="448aa-111">As configurações de filtro são específicas de cada grade.</span><span class="sxs-lookup"><span data-stu-id="448aa-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="448aa-112">A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="448aa-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="448aa-113">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="448aa-113">**Show**</span></span>  
 <span data-ttu-id="448aa-114">Somente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="448aa-114">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="448aa-115">Selecione os estados de assinatura a serem exibidos para o tipo de assinatura selecionado.</span><span class="sxs-lookup"><span data-stu-id="448aa-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="448aa-116">Por exemplo, você pode optar por exibir somente as assinaturas que tiverem um erro.</span><span class="sxs-lookup"><span data-stu-id="448aa-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="448aa-117">**Status**</span><span class="sxs-lookup"><span data-stu-id="448aa-117">**Status**</span></span>  
 <span data-ttu-id="448aa-118">O status de cada assinatura, determinado pelo status do Distribution Agent ou do Log Reader Agent (o status com prioridade mais alta é exibido; o status também pode ser determinado pelo Queue Reader Agent, se assinaturas de atualização enfileiradas forem usadas).</span><span class="sxs-lookup"><span data-stu-id="448aa-118">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="448aa-119">Por padrão, a grade que contém informações de assinatura é classificada pela coluna **Status** (e depois pela coluna **Desempenho** para assinaturas com o mesmo status).</span><span class="sxs-lookup"><span data-stu-id="448aa-119">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="448aa-120">A lista a seguir mostra os valores de status possíveis e a ordem de classificação dos valores (por exemplo, os erros são sempre mostrados na parte superior da grade).</span><span class="sxs-lookup"><span data-stu-id="448aa-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="448aa-121">Erro</span><span class="sxs-lookup"><span data-stu-id="448aa-121">Error</span></span>  
  
-   <span data-ttu-id="448aa-122">Desempenho crítico (somente[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="448aa-122">Performance critical ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="448aa-123">Expirando em breve/Expirado (somente[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="448aa-123">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="448aa-124">Assinatura não inicializada (somente[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="448aa-124">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="448aa-125">Tentando novamente comando com falha</span><span class="sxs-lookup"><span data-stu-id="448aa-125">Retrying failed command</span></span>  
  
-   <span data-ttu-id="448aa-126">Não está em execução</span><span class="sxs-lookup"><span data-stu-id="448aa-126">Not Running</span></span>  
  
-   <span data-ttu-id="448aa-127">Executando</span><span class="sxs-lookup"><span data-stu-id="448aa-127">Running</span></span>  
  
 <span data-ttu-id="448aa-128">A ordem de classificação também determina qual valor será exibido se uma determinada assinatura estiver em mais de um estado.</span><span class="sxs-lookup"><span data-stu-id="448aa-128">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="448aa-129">Por exemplo, se uma assinatura tiver um erro e expirar em breve, a coluna **Status** exibirá **Erro**.</span><span class="sxs-lookup"><span data-stu-id="448aa-129">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="448aa-130">Os valores de status **Desempenho crítico**, **Expirando em breve/Expirado**e **Assinatura não inicializada** são avisos.</span><span class="sxs-lookup"><span data-stu-id="448aa-130">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="448aa-131">Quando um aviso é exibido, a coluna **Status** também exibe se um agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="448aa-131">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="448aa-132">Por exemplo, o status poderia ser **Executando, Desempenho crítico**.</span><span class="sxs-lookup"><span data-stu-id="448aa-132">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="448aa-133">Os valores de status **Desempenho crítico** e **Expirando em breve/Expirado** só serão exibidos se os limites forem definidos.</span><span class="sxs-lookup"><span data-stu-id="448aa-133">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="448aa-134">Para obter informações sobre medidas de desempenho e definir limites, consulte [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (Monitorar o desempenho com o Replication Monitor) e [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) (Definir limites e avisos no Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="448aa-134">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="448aa-135">**Assinatura**</span><span class="sxs-lookup"><span data-stu-id="448aa-135">**Subscription**</span></span>  
 <span data-ttu-id="448aa-136">O nome de cada assinatura no formato: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="448aa-136">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="448aa-137">**Desempenho**</span><span class="sxs-lookup"><span data-stu-id="448aa-137">**Performance**</span></span>  
 <span data-ttu-id="448aa-138">Somente o[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="448aa-138">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="448aa-139">A classificação de desempenho de cada assinatura é baseada nas medidas mais atuais, calculadas pelo Replication Monitor, e, não reflete desempenho histórico.</span><span class="sxs-lookup"><span data-stu-id="448aa-139">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="448aa-140">O desempenho é avaliado para assinaturas de publicações que têm limites de desempenho definidos; se os limites de desempenho não forem definidos para uma publicação, essa coluna exibirá **Não habilitado**.</span><span class="sxs-lookup"><span data-stu-id="448aa-140">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="448aa-141">A classificação de desempenho é um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="448aa-141">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="448aa-142">Excelente</span><span class="sxs-lookup"><span data-stu-id="448aa-142">Excellent</span></span>  
  
-   <span data-ttu-id="448aa-143">Satisfatório</span><span class="sxs-lookup"><span data-stu-id="448aa-143">Good</span></span>  
  
-   <span data-ttu-id="448aa-144">Razoável</span><span class="sxs-lookup"><span data-stu-id="448aa-144">Fair</span></span>  
  
-   <span data-ttu-id="448aa-145">Ruim</span><span class="sxs-lookup"><span data-stu-id="448aa-145">Poor</span></span>  
  
-   <span data-ttu-id="448aa-146">Crítico</span><span class="sxs-lookup"><span data-stu-id="448aa-146">Critical</span></span>  
  
 <span data-ttu-id="448aa-147">Se o desempenho for crítico, **Desempenho Crítico** será exibido na coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="448aa-147">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="448aa-148">Para obter mais informações sobre como as classificações de desempenho são definidas e como os limites de desempenho são configurados, consulte [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (Monitorar o desempenho com o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="448aa-148">For more information on how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="448aa-149">**Latência**</span><span class="sxs-lookup"><span data-stu-id="448aa-149">**Latency**</span></span>  
 <span data-ttu-id="448aa-150">Somente o[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="448aa-150">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="448aa-151">É o período médio de tempo que decorre entre a confirmação de uma transação no Publicador e a confirmação da transação correspondente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="448aa-151">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="448aa-152">A latência exibida é baseada nas medidas mais recentes calculadas pelo Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="448aa-152">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="448aa-153">Para obter mais informações sobre como medir a latência, consulte [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) (Medir a latência e validar as conexões da replicação transacional).</span><span class="sxs-lookup"><span data-stu-id="448aa-153">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448aa-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="448aa-154">See Also</span></span>  
 <span data-ttu-id="448aa-155">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="448aa-155">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="448aa-156">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="448aa-156">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="448aa-157">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="448aa-157">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
