---
title: Informações da publicação, todas as assinaturas (publicação de instantâneo) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.snapshot.f1
ms.assetid: 7ce656c2-6e60-4625-8955-1daff641070c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75eb85adae46481ddd4360f095c00060af5677fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574658"
---
# <a name="publication-information-all-subscriptions-snapshot-publication"></a><span data-ttu-id="4abad-102">Informações da Publicação, Todas as Assinaturas (publicação de instantâneo)</span><span class="sxs-lookup"><span data-stu-id="4abad-102">Publication Information, All Subscriptions (Snapshot Publication)</span></span>
  <span data-ttu-id="4abad-103">A guia **Todas as Assinaturas** exibe informações sobre todas as assinaturas na publicação de instantâneo selecionada.</span><span class="sxs-lookup"><span data-stu-id="4abad-103">The **All Subscriptions** tab displays information on all subscriptions to the selected snapshot publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4abad-104">Opções</span><span class="sxs-lookup"><span data-stu-id="4abad-104">Options</span></span>  
 <span data-ttu-id="4abad-105">Para obter informações mais detalhadas e tarefas relacionadas a uma assinatura, clique com o botão direito do mouse na linha dessa assinatura e clique em uma opção no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="4abad-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="4abad-106">Para alterar a forma como a grade exibe os dados, clique com o botão direito do mouse na grade e clique em uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="4abad-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="4abad-107">**Classificar**: classifique uma ou mais colunas na caixa de diálogo **Classificar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="4abad-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="4abad-108">**Selecionar Colunas para Mostrar**: selecione quais colunas devem ser exibidas e a ordem em que devem ser exibidas, na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="4abad-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="4abad-109">**Filtrar**: filtre linhas na grade com base em valores de colunas da caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="4abad-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="4abad-110">**Limpar Filtro**: limpe as configurações de filtro da grade.</span><span class="sxs-lookup"><span data-stu-id="4abad-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="4abad-111">As configurações de filtro são específicas de cada grade.</span><span class="sxs-lookup"><span data-stu-id="4abad-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="4abad-112">A seleção e a classificação da coluna são aplicadas a todas as grades do mesmo tipo, como a grade de publicações de cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="4abad-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="4abad-113">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="4abad-113">**Show**</span></span>  
 <span data-ttu-id="4abad-114">Somente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="4abad-114">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="4abad-115">Selecione os estados de assinatura a serem exibidos para o tipo de assinatura selecionado.</span><span class="sxs-lookup"><span data-stu-id="4abad-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="4abad-116">Por exemplo, você pode optar por exibir somente as assinaturas que tiverem um erro.</span><span class="sxs-lookup"><span data-stu-id="4abad-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="4abad-117">**Status**</span><span class="sxs-lookup"><span data-stu-id="4abad-117">**Status**</span></span>  
 <span data-ttu-id="4abad-118">O status de cada assinatura, que é determinado pelo status do Snapshot Agent ou do Distribution Agent (o status com prioridade mais alta é exibido).</span><span class="sxs-lookup"><span data-stu-id="4abad-118">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="4abad-119">Por padrão, a grade que contém informações de assinatura é classificada pela coluna **Status** .</span><span class="sxs-lookup"><span data-stu-id="4abad-119">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="4abad-120">A lista a seguir mostra os valores de status possíveis e a ordem de classificação dos valores (por exemplo, os erros são sempre mostrados na parte superior da grade).</span><span class="sxs-lookup"><span data-stu-id="4abad-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="4abad-121">Erro</span><span class="sxs-lookup"><span data-stu-id="4abad-121">Error</span></span>  
  
-   <span data-ttu-id="4abad-122">Expirando em breve/Expirado (somente[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="4abad-122">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="4abad-123">Assinatura não inicializada (somente[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="4abad-123">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="4abad-124">Tentando novamente comando com falha</span><span class="sxs-lookup"><span data-stu-id="4abad-124">Retrying failed command</span></span>  
  
-   <span data-ttu-id="4abad-125">Sincronizando</span><span class="sxs-lookup"><span data-stu-id="4abad-125">Synchronizing</span></span>  
  
-   <span data-ttu-id="4abad-126">Não sincronizando</span><span class="sxs-lookup"><span data-stu-id="4abad-126">Not synchronizing</span></span>  
  
 <span data-ttu-id="4abad-127">A ordem de classificação também determina qual valor será exibido se uma determinada assinatura estiver em mais de um estado.</span><span class="sxs-lookup"><span data-stu-id="4abad-127">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="4abad-128">Por exemplo, se uma assinatura tiver um erro e expirar em breve, a coluna **Status** exibirá **Erro**.</span><span class="sxs-lookup"><span data-stu-id="4abad-128">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="4abad-129">Os valores de status **Expirando em breve/Expirado** e **Assinatura não inicializada** são avisos.</span><span class="sxs-lookup"><span data-stu-id="4abad-129">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="4abad-130">Quando um aviso é exibido, a coluna **Status** também exibe se um agente está em execução.</span><span class="sxs-lookup"><span data-stu-id="4abad-130">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="4abad-131">Por exemplo, o status pode ser **Executando, Expirando em breve/Expirado**.</span><span class="sxs-lookup"><span data-stu-id="4abad-131">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="4abad-132">O valor de status **Expirando em breve/Expirado** só será exibido se for definido um limite.</span><span class="sxs-lookup"><span data-stu-id="4abad-132">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="4abad-133">Para obter informações sobre como definir limites, consulte [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) (Definir limites e avisos no Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="4abad-133">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="4abad-134">**Assinatura**</span><span class="sxs-lookup"><span data-stu-id="4abad-134">**Subscription**</span></span>  
 <span data-ttu-id="4abad-135">O nome de cada assinatura no formato: *SubscriberName: SubscriptionDatabaseName*.</span><span class="sxs-lookup"><span data-stu-id="4abad-135">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="4abad-136">**Última Sincronização**</span><span class="sxs-lookup"><span data-stu-id="4abad-136">**Last Synchronization**</span></span>  
 <span data-ttu-id="4abad-137">A hora da última execução do Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="4abad-137">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="4abad-138">Se a sincronização estiver em andamento, **Em andamento** será exibido.</span><span class="sxs-lookup"><span data-stu-id="4abad-138">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4abad-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4abad-139">See Also</span></span>  
 <span data-ttu-id="4abad-140">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4abad-140">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="4abad-141">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4abad-141">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="4abad-142">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="4abad-142">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
