---
title: Informações da publicação, avisos (publicação de mesclagem, SQL Server 2005 e posterior) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.merge.f1
ms.assetid: 9bef3565-5f13-42ac-8723-ebe55b0c11e6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75f58a4cd9bd84791acf7fd9d28147ef3bbd6232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574659"
---
# <a name="publication-information-warnings-merge-publication-sql-server-2005-and-later"></a><span data-ttu-id="c18f5-102">Informações da Publicação, Avisos (publicação de mesclagem, SQL Server 2005 e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="c18f5-102">Publication Information, Warnings (Merge Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="c18f5-103"> A guia **Avisos** está disponível para Distribuidores que estão executando o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="c18f5-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="c18f5-104">A guia **Avisos** permite executar as seguintes tarefas para a publicação selecionada:</span><span class="sxs-lookup"><span data-stu-id="c18f5-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="c18f5-105">Habilitar avisos.</span><span class="sxs-lookup"><span data-stu-id="c18f5-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="c18f5-106">Especificar limites associados a avisos.</span><span class="sxs-lookup"><span data-stu-id="c18f5-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="c18f5-107">Definir alertas associados a avisos.</span><span class="sxs-lookup"><span data-stu-id="c18f5-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="c18f5-108">Avisos, limites e alertas</span><span class="sxs-lookup"><span data-stu-id="c18f5-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="c18f5-109">Por padrão, o Replication Monitor exibe avisos para assinaturas não inicializadas: um status **Assinatura não inicializada** é exibido como um aviso na coluna **Status** de páginas que incluem informações de assinatura.</span><span class="sxs-lookup"><span data-stu-id="c18f5-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="c18f5-110">Para publicações de mesclagem, você pode especificar se essas condições adicionais resultarão em avisos:</span><span class="sxs-lookup"><span data-stu-id="c18f5-110">For merge publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="c18f5-111">Expiração de assinatura iminente.</span><span class="sxs-lookup"><span data-stu-id="c18f5-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="c18f5-112">Isso corresponde à opção **Avisar se uma assinatura for expirar dentro do limite**.</span><span class="sxs-lookup"><span data-stu-id="c18f5-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="c18f5-113">Se o limite especificado for alcançado ou ultrapassado, o status da assinatura será exibido como **Expirando em breve/Expirado** (a menos que um problema com prioridade mais alta precise ser exibido).</span><span class="sxs-lookup"><span data-stu-id="c18f5-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="c18f5-114">Excedendo o tempo de sincronização especificado.</span><span class="sxs-lookup"><span data-stu-id="c18f5-114">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="c18f5-115">Isso corresponde às opções **Avisar se o tamanho de mesclagem da conexão discada exceder o limite** e **Avisar se o tamanho de mesclagem das conexões da LAN exceder o limite**.</span><span class="sxs-lookup"><span data-stu-id="c18f5-115">This corresponds to the options **Warn if a merge length for dialup connections exceeds the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="c18f5-116">Esses dois limites podem ser definidos, mas só um é usado durante uma determinada sincronização.</span><span class="sxs-lookup"><span data-stu-id="c18f5-116">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="c18f5-117">O Merge Agent aplica o limite apropriado com base no tipo de conexão.</span><span class="sxs-lookup"><span data-stu-id="c18f5-117">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="c18f5-118">Se o limite especificado for alcançado ou ultrapassado, o status da assinatura será exibido como **Mesclagem de execução longa** (a menos que um problema com prioridade mais alta precise ser exibido).</span><span class="sxs-lookup"><span data-stu-id="c18f5-118">If the specified threshold is met or exceeded, the subscription status is displayed as **Long-running merge** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="c18f5-119">Falha no processamento do número especificado de linhas em um determinado período.</span><span class="sxs-lookup"><span data-stu-id="c18f5-119">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="c18f5-120">Corresponde às opções **Avisar se as filas mescladas por segundo para conexões discadas forem menores que o limite** e **Avisar se o tamanho de mesclagem das conexões da LAN exceder o limite**.</span><span class="sxs-lookup"><span data-stu-id="c18f5-120">This corresponds to the options **Warn if rows merged per second for dialup connections is less than the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="c18f5-121">Esses dois limites podem ser definidos, mas só um é usado durante uma determinada sincronização.</span><span class="sxs-lookup"><span data-stu-id="c18f5-121">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="c18f5-122">O Merge Agent aplica o limite apropriado com base no tipo de conexão.</span><span class="sxs-lookup"><span data-stu-id="c18f5-122">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="c18f5-123">Se o limite especificado for alcançado ou ultrapassado, o status da assinatura será exibido como **Desempenho crítico** (a menos que um problema com prioridade mais alta precise ser exibido).</span><span class="sxs-lookup"><span data-stu-id="c18f5-123">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="c18f5-124">Quando você habilita um aviso, também define um limite.</span><span class="sxs-lookup"><span data-stu-id="c18f5-124">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="c18f5-125">Por exemplo, se você habilitar o aviso **Avisar se o tamanho de mesclagem das conexões da LAN exceder o limite**, defina o período de tempo máximo permitido para uma sincronização de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="c18f5-125">For example, if you enable the warning **Warn if a merge length for LAN connections exceeds the threshold**, set the maximum allowable length of time for a merge synchronization.</span></span>  
  
 <span data-ttu-id="c18f5-126">Além de exibir de um aviso no Replication Monitor, atingir um limite também pode disparar um alerta.</span><span class="sxs-lookup"><span data-stu-id="c18f5-126">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="c18f5-127">Os alertas são definidos clicando em **Configurar Alertas** e fornecendo informações na caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="c18f5-127">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c18f5-128">Opções</span><span class="sxs-lookup"><span data-stu-id="c18f5-128">Options</span></span>  
 <span data-ttu-id="c18f5-129">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="c18f5-129">**Enabled**</span></span>  
 <span data-ttu-id="c18f5-130">Selecione para habilitar um aviso e especificar um limite.</span><span class="sxs-lookup"><span data-stu-id="c18f5-130">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="c18f5-131">**Alerta**</span><span class="sxs-lookup"><span data-stu-id="c18f5-131">**Alert**</span></span>  
 <span data-ttu-id="c18f5-132">Selecione para habilitar a configurações de alerta para um determinado aviso de replicação.</span><span class="sxs-lookup"><span data-stu-id="c18f5-132">Select to enable the alert setting for a given replication warning.</span></span>  
  
 <span data-ttu-id="c18f5-133">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="c18f5-133">**Warning**</span></span>  
 <span data-ttu-id="c18f5-134">Uma descrição do aviso associada a um limite.</span><span class="sxs-lookup"><span data-stu-id="c18f5-134">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="c18f5-135">**Limite**</span><span class="sxs-lookup"><span data-stu-id="c18f5-135">**Threshold**</span></span>  
 <span data-ttu-id="c18f5-136">Especifique um valor para o limite.</span><span class="sxs-lookup"><span data-stu-id="c18f5-136">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="c18f5-137">**Configurar alertas**</span><span class="sxs-lookup"><span data-stu-id="c18f5-137">**Configure Alerts**</span></span>  
 <span data-ttu-id="c18f5-138">Selecione uma linha na grade **Avisos** e clique em **Configurar Alertas** para iniciar a caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="c18f5-138">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="c18f5-139">A caixa de diálogo permite definir um alerta associado ao limite selecionado e ao aviso.</span><span class="sxs-lookup"><span data-stu-id="c18f5-139">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="c18f5-140">**Descartar Alterações**</span><span class="sxs-lookup"><span data-stu-id="c18f5-140">**Discard Changes**</span></span>  
 <span data-ttu-id="c18f5-141">Clique para descartar qualquer alteração em avisos e limites.</span><span class="sxs-lookup"><span data-stu-id="c18f5-141">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c18f5-142">Clicar em **Descartar Alterações** não afeta alertas definidos na caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="c18f5-142">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="c18f5-143">**Salvar alterações**</span><span class="sxs-lookup"><span data-stu-id="c18f5-143">**Save Changes**</span></span>  
 <span data-ttu-id="c18f5-144">Clique para salvar qualquer alteração em avisos e limites.</span><span class="sxs-lookup"><span data-stu-id="c18f5-144">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c18f5-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c18f5-145">See Also</span></span>  
 <span data-ttu-id="c18f5-146">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c18f5-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="c18f5-147">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c18f5-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="c18f5-148">[Monitorar o desempenho com o Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c18f5-148">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="c18f5-149">[Monitorando a Replicação](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="c18f5-149">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="c18f5-150">Definir limites e avisos no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="c18f5-150">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
