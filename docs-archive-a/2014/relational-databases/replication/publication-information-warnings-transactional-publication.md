---
title: Informações da publicação, avisos (publicação transacional, SQL Server 2005 e posterior) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.tran.f1
ms.assetid: 4d4baf1d-d0a1-4d09-bec7-137811f43f09
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac7ab0f712fe69d3736985921d70b0ce200d474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681551"
---
# <a name="publication-information-warnings-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="f5a19-102">Informações da Publicação, Avisos (publicação transacional, SQL Server 2005 e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="f5a19-102">Publication Information, Warnings (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="f5a19-103"> A guia **Avisos** está disponível para Distribuidores que estão executando o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="f5a19-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="f5a19-104">A guia **Avisos** permite executar as seguintes tarefas para a publicação selecionada:</span><span class="sxs-lookup"><span data-stu-id="f5a19-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="f5a19-105">Ativar advertências a serem exibidas no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="f5a19-105">Enable warnings to be displayed in Replication Monitor.</span></span>  
  
-   <span data-ttu-id="f5a19-106">Especificar limites associados a avisos.</span><span class="sxs-lookup"><span data-stu-id="f5a19-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="f5a19-107">Definir alertas associados a avisos.</span><span class="sxs-lookup"><span data-stu-id="f5a19-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="f5a19-108">Avisos, limites e alertas</span><span class="sxs-lookup"><span data-stu-id="f5a19-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="f5a19-109">Por padrão, o Replication Monitor exibe avisos para assinaturas não inicializadas: um status **Assinatura não inicializada** é exibido como um aviso na coluna **Status** de páginas que incluem informações de assinatura.</span><span class="sxs-lookup"><span data-stu-id="f5a19-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="f5a19-110">Para publicações transacionais, você pode especificar se essas condições adicionais resultarão em avisos:</span><span class="sxs-lookup"><span data-stu-id="f5a19-110">For transactional publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="f5a19-111">Expiração de assinatura iminente.</span><span class="sxs-lookup"><span data-stu-id="f5a19-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="f5a19-112">Isso corresponde à opção **Avisar se uma assinatura for expirar dentro do limite**.</span><span class="sxs-lookup"><span data-stu-id="f5a19-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="f5a19-113">Se o limite especificado for alcançado ou ultrapassado, o status da assinatura será exibido como **Expirando em breve/Expirado** (a menos que um problema com prioridade mais alta precise ser exibido).</span><span class="sxs-lookup"><span data-stu-id="f5a19-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="f5a19-114">Excedendo a latência especificada.</span><span class="sxs-lookup"><span data-stu-id="f5a19-114">Exceeding the specified latency.</span></span> <span data-ttu-id="f5a19-115">É o período de tempo que decorre entre a confirmação de uma transação no Publicador e a confirmação da transação correspondente no Assinante.</span><span class="sxs-lookup"><span data-stu-id="f5a19-115">This is the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="f5a19-116">Isso corresponde à opção **Avisar se a latência exceder o limite**.</span><span class="sxs-lookup"><span data-stu-id="f5a19-116">This corresponds to the option **Warn if latency exceeds the threshold**.</span></span> <span data-ttu-id="f5a19-117">Se o limite especificado for alcançado ou ultrapassado, o status da assinatura será exibido como **Desempenho crítico** (a menos que um problema com prioridade mais alta precise ser exibido).</span><span class="sxs-lookup"><span data-stu-id="f5a19-117">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="f5a19-118">O limite também é usado para fornecer classificação de desempenho, que é exibida na coluna **Desempenho** de páginas que incluem informações de assinatura.</span><span class="sxs-lookup"><span data-stu-id="f5a19-118">The threshold is also used to provide a performance rating, which is displayed in the **Performance** column of pages that include subscription information.</span></span> <span data-ttu-id="f5a19-119">A classificação de desempenho é um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f5a19-119">The performance rating is one of the following values:</span></span>  
  
    -   <span data-ttu-id="f5a19-120">Excelente</span><span class="sxs-lookup"><span data-stu-id="f5a19-120">Excellent</span></span>  
  
    -   <span data-ttu-id="f5a19-121">Satisfatório</span><span class="sxs-lookup"><span data-stu-id="f5a19-121">Good</span></span>  
  
    -   <span data-ttu-id="f5a19-122">Razoável</span><span class="sxs-lookup"><span data-stu-id="f5a19-122">Fair</span></span>  
  
    -   <span data-ttu-id="f5a19-123">Ruim</span><span class="sxs-lookup"><span data-stu-id="f5a19-123">Poor</span></span>  
  
    -   <span data-ttu-id="f5a19-124">Crítico</span><span class="sxs-lookup"><span data-stu-id="f5a19-124">Critical</span></span>  
  
 <span data-ttu-id="f5a19-125">Quando você habilita um aviso, também define um limite.</span><span class="sxs-lookup"><span data-stu-id="f5a19-125">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="f5a19-126">Por exemplo, se você habilitar o aviso **Avisar se a latência exceder o limite**, selecione o período de tempo permitido entre a confirmação de uma transação no Publicador e a confirmação de uma transação no Assinante.</span><span class="sxs-lookup"><span data-stu-id="f5a19-126">For example, if you enable the warning **Warn if latency exceeds the threshold**, select the amount of time allowable between a transaction being committed at the Publisher and the transaction being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="f5a19-127">Além de exibir de um aviso no Replication Monitor, atingir um limite também pode disparar um alerta.</span><span class="sxs-lookup"><span data-stu-id="f5a19-127">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="f5a19-128">Os alertas são definidos clicando em **Configurar Alertas** e fornecendo informações na caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="f5a19-128">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f5a19-129">Opções</span><span class="sxs-lookup"><span data-stu-id="f5a19-129">Options</span></span>  
 <span data-ttu-id="f5a19-130">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="f5a19-130">**Enabled**</span></span>  
 <span data-ttu-id="f5a19-131">Selecione para habilitar um aviso e especificar um limite.</span><span class="sxs-lookup"><span data-stu-id="f5a19-131">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="f5a19-132">**Aviso**</span><span class="sxs-lookup"><span data-stu-id="f5a19-132">**Warning**</span></span>  
 <span data-ttu-id="f5a19-133">Uma descrição do aviso associada a um limite.</span><span class="sxs-lookup"><span data-stu-id="f5a19-133">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="f5a19-134">**Limite**</span><span class="sxs-lookup"><span data-stu-id="f5a19-134">**Threshold**</span></span>  
 <span data-ttu-id="f5a19-135">Especifique um valor para o limite.</span><span class="sxs-lookup"><span data-stu-id="f5a19-135">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="f5a19-136">**Configurar alertas**</span><span class="sxs-lookup"><span data-stu-id="f5a19-136">**Configure Alerts**</span></span>  
 <span data-ttu-id="f5a19-137">Selecione uma linha na grade **Avisos** e clique em **Configurar Alertas** para iniciar a caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="f5a19-137">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="f5a19-138">A caixa de diálogo permite definir um alerta associado ao limite selecionado e ao aviso.</span><span class="sxs-lookup"><span data-stu-id="f5a19-138">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="f5a19-139">**Descartar Alterações**</span><span class="sxs-lookup"><span data-stu-id="f5a19-139">**Discard Changes**</span></span>  
 <span data-ttu-id="f5a19-140">Clique para descartar qualquer alteração em avisos e limites.</span><span class="sxs-lookup"><span data-stu-id="f5a19-140">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5a19-141">Clicar em **Descartar Alterações** não afeta alertas definidos na caixa de diálogo **Configurar Alertas de Replicação** .</span><span class="sxs-lookup"><span data-stu-id="f5a19-141">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="f5a19-142">**Salvar alterações**</span><span class="sxs-lookup"><span data-stu-id="f5a19-142">**Save Changes**</span></span>  
 <span data-ttu-id="f5a19-143">Clique para salvar qualquer alteração em avisos e limites.</span><span class="sxs-lookup"><span data-stu-id="f5a19-143">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a19-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5a19-144">See Also</span></span>  
 <span data-ttu-id="f5a19-145">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f5a19-145">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f5a19-146">[Exibir informações e executar tarefas usando o Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f5a19-146">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="f5a19-147">[Monitorar o desempenho com o Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f5a19-147">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="f5a19-148">[Monitorando a Replicação](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="f5a19-148">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="f5a19-149">Definir limites e avisos no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="f5a19-149">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
