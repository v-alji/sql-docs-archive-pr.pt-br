---
title: Definir limites e avisos no Replication Monitor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- Merge Agent, thresholds and warnings
- Distribution Agent, thresholds and warnings
- thresholds [SQL Server replication]
- Replication Monitor, thresholds and warnings
- monitoring performance [SQL Server replication], thresholds and warnings
ms.assetid: 3a409c2c-b77e-4001-b81a-1dcd918618ec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f34878a6398df34e55e6dd3783f2da736bee0959
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685560"
---
# <a name="set-thresholds-and-warnings-in-replication-monitor"></a><span data-ttu-id="aca01-102">Definir os limites e avisos no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="aca01-102">Set Thresholds and Warnings in Replication Monitor</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="aca01-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor exibe informações de status para publicações e assinaturas.</span><span class="sxs-lookup"><span data-stu-id="aca01-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor displays status information for publications and subscriptions.</span></span> <span data-ttu-id="aca01-104">Por padrão, o Replication Monitor só exibe avisos para assinaturas não inicializadas, mas você pode habilitar os avisos para outras condições.</span><span class="sxs-lookup"><span data-stu-id="aca01-104">By default, Replication Monitor displays warnings only for uninitialized subscriptions, but you can enable warnings for other conditions.</span></span> <span data-ttu-id="aca01-105">Recomendamos habilitar os avisos para a sua topologia, para que esteja informado sobre o status e o desempenho de maneira oportuna.</span><span class="sxs-lookup"><span data-stu-id="aca01-105">It is recommended that you enable warnings for your topology, so that you are informed about status and performance in a timely manner.</span></span>  
  
 <span data-ttu-id="aca01-106">Ao habilitar um aviso, você especifica um limite.</span><span class="sxs-lookup"><span data-stu-id="aca01-106">When you enable a warning, you specify a threshold.</span></span> <span data-ttu-id="aca01-107">Quando o limite é atingido ou excedido, um aviso é exibido (a menos que um problema com prioridade superior deva ser exibido).</span><span class="sxs-lookup"><span data-stu-id="aca01-107">When that threshold is met or exceeded, a warning is displayed (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="aca01-108">Além de exibir de um aviso no Replication Monitor, atingir um limite também pode disparar um alerta.</span><span class="sxs-lookup"><span data-stu-id="aca01-108">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="aca01-109">Você pode habilitar avisos para as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="aca01-109">You can enable warnings for the following conditions:</span></span>  
  
-   <span data-ttu-id="aca01-110">Expiração iminente de assinatura</span><span class="sxs-lookup"><span data-stu-id="aca01-110">Imminent subscription expiration</span></span>  
  
     <span data-ttu-id="aca01-111">Isso se aplica a todos os tipos de replicação.</span><span class="sxs-lookup"><span data-stu-id="aca01-111">This applies to all types of replication.</span></span> <span data-ttu-id="aca01-112">Se o limite especificado for atingido ou excedido, o status da assinatura será exibido como **Expirando em breve/Expirado**.</span><span class="sxs-lookup"><span data-stu-id="aca01-112">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired**.</span></span>  
  
-   <span data-ttu-id="aca01-113">Exceder a latência especificada (o período decorrido entre a confirmação de uma transação no Publicador e a confirmação da transação correspondente no Assinante).</span><span class="sxs-lookup"><span data-stu-id="aca01-113">Exceeding the specified latency (the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber).</span></span>  
  
     <span data-ttu-id="aca01-114">Isso se aplica à replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="aca01-114">This applies to transactional replication.</span></span> <span data-ttu-id="aca01-115">Se o limite especificado for atingido ou excedido, o status da assinatura será exibido como **Desempenho crítico**.</span><span class="sxs-lookup"><span data-stu-id="aca01-115">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical**.</span></span>  
  
-   <span data-ttu-id="aca01-116">Excedendo o tempo de sincronização especificado.</span><span class="sxs-lookup"><span data-stu-id="aca01-116">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="aca01-117">Isso se aplica à replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="aca01-117">This applies to merge replication.</span></span> <span data-ttu-id="aca01-118">Se o limite especificado for atingido ou excedido, o status será exibido como **Mesclagem de execução longa**.</span><span class="sxs-lookup"><span data-stu-id="aca01-118">If the specified threshold is met or exceeded, the status is displayed as **Long-running merge**.</span></span> <span data-ttu-id="aca01-119">Você pode especificar limites diferentes para conexões discadas e Rede local (LAN).</span><span class="sxs-lookup"><span data-stu-id="aca01-119">You can specify different thresholds for dialup and Local Area Network (LAN) connections.</span></span>  
  
-   <span data-ttu-id="aca01-120">Falha no processamento do número especificado de linhas em um determinado período.</span><span class="sxs-lookup"><span data-stu-id="aca01-120">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="aca01-121">Isso se aplica à replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="aca01-121">This applies to merge replication.</span></span> <span data-ttu-id="aca01-122">Se o limite especificado for atingido ou excedido, o status será exibido como **Desempenho crítico**.</span><span class="sxs-lookup"><span data-stu-id="aca01-122">If the specified threshold is met or exceeded, the status is displayed as **Performance critical**.</span></span> <span data-ttu-id="aca01-123">Você pode especificar limites diferentes para conexões discadas e LAN.</span><span class="sxs-lookup"><span data-stu-id="aca01-123">You can specify different thresholds for dialup and LAN connections.</span></span>  
  
 <span data-ttu-id="aca01-124">Para obter mais informações sobre os avisos **Desempenho crítico** e **Mesclagem de execução longa**, consulte [Monitorar o desempenho com o Replication Monitor](monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="aca01-124">For more information on the warnings **Performance critical** and **Long-running merge**, see [Monitor Performance with Replication Monitor](monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="aca01-125">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="aca01-125">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="aca01-126">Definir limites e avisos para uma publicação transacional</span><span class="sxs-lookup"><span data-stu-id="aca01-126">Set thresholds and warnings for a transactional publication</span></span>](#Transactional)  
  
-   [<span data-ttu-id="aca01-127">Definir limites e avisos para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="aca01-127">Set thresholds and warnings for a merge publication</span></span>](#Merge)  
  
-   [<span data-ttu-id="aca01-128">Definir limites e avisos para uma publicação de instantâneo</span><span class="sxs-lookup"><span data-stu-id="aca01-128">Set thresholds and warnings for a snapshot publication</span></span>](#Snapshot)  
  
##  <a name="to-set-thresholds-and-warnings-for-a-transactional-publication"></a><a name="Transactional"></a> <span data-ttu-id="aca01-129">Para definir limites e avisos para uma publicação transacional</span><span class="sxs-lookup"><span data-stu-id="aca01-129">To set thresholds and warnings for a transactional publication</span></span>  
  
1.  <span data-ttu-id="aca01-130">Expanda um Grupo do publicador no painel esquerdo, expanda um Publicador e clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="aca01-130">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="aca01-131">Clique na guia **avisos** . Para exibir mais informações sobre as opções nessa guia, clique em **ajuda** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="aca01-131">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="aca01-132">Habilite um aviso selecionando a caixa de seleção apropriada: **Avise se uma assinatura for expirar dentro do limite** ou **Avise se a latência exceder o limite**.</span><span class="sxs-lookup"><span data-stu-id="aca01-132">Enable a warning by selecting the appropriate check box: **Warn if a subscription will expire within the threshold** or **Warn if latency exceeds the threshold**.</span></span>  
  
4.  <span data-ttu-id="aca01-133">Defina um limite para os avisos na coluna **Limite** .</span><span class="sxs-lookup"><span data-stu-id="aca01-133">Set a threshold for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="aca01-134">Por exemplo, ao selecionar **Avise se a latência exceder o limite** na etapa 3, é possível selecionar uma latência de **60 segundos** na coluna **Limite** .</span><span class="sxs-lookup"><span data-stu-id="aca01-134">For example, if you selected **Warn if latency exceeds the threshold** in step 3, you could select a latency of **60 seconds** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="aca01-135">Clique em **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="aca01-135">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="aca01-136">Para configurar um alerta para um limite</span><span class="sxs-lookup"><span data-stu-id="aca01-136">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="aca01-137">Clique em **Configurar Alertas**.</span><span class="sxs-lookup"><span data-stu-id="aca01-137">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="aca01-138">Na caixa de diálogo **Configurar Alertas de Replicação** , selecione um alerta e então clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="aca01-138">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="aca01-139">Essa caixa de diálogo exibe os alertas para todos os tipos de publicação, inclusive alertas que não estão relacionados com o monitoramento de limites.</span><span class="sxs-lookup"><span data-stu-id="aca01-139">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="aca01-140">Para obter mais informações, consulte [Usar alertas para eventos do agente de replicação](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="aca01-140">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="aca01-141">Defina as opções na caixa de diálogo **Propriedades do alerta \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="aca01-141">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="aca01-142">Na página **Geral** , clique em **Habilitar**; especifique em qual banco de dados deverá ser aplicado o alerta.</span><span class="sxs-lookup"><span data-stu-id="aca01-142">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="aca01-143">Na página **Resposta** , especifique se deve ser enviado um e-mail e/ou se deverá ser executado um trabalho.</span><span class="sxs-lookup"><span data-stu-id="aca01-143">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="aca01-144">Na página **Opções** , personalize o texto da resposta.</span><span class="sxs-lookup"><span data-stu-id="aca01-144">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="aca01-145">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="aca01-145">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-merge-publication"></a><a name="Merge"></a><span data-ttu-id="aca01-146">Definir limites e avisos para uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="aca01-146">Set thresholds and warnings for a merge publication</span></span>  
  
1.  <span data-ttu-id="aca01-147">Expanda um Grupo do publicador no painel esquerdo, expanda um Publicador e clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="aca01-147">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="aca01-148">Clique na guia **avisos** . Para exibir mais informações sobre as opções nessa guia, clique em **ajuda** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="aca01-148">Click the **Warnings** tab. To view more information about the options on this tab, click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="aca01-149">Habilite um aviso selecionando a caixa de seleção apropriada:</span><span class="sxs-lookup"><span data-stu-id="aca01-149">Enable a warning by selecting the appropriate check box:</span></span>  
  
    -   <span data-ttu-id="aca01-150">**Avise se uma assinatura for expirar dentro do limite**</span><span class="sxs-lookup"><span data-stu-id="aca01-150">**Warn if a subscription will expire within the threshold**</span></span>  
  
    -   <span data-ttu-id="aca01-151">**Avisar se o tamanho de mesclagem da conexão discada exceder o limite**</span><span class="sxs-lookup"><span data-stu-id="aca01-151">**Warn if a merge length for dialup connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="aca01-152">**Avisar se o tamanho de mesclagem das conexões da LAN exceder o limite**</span><span class="sxs-lookup"><span data-stu-id="aca01-152">**Warn if a merge length for LAN connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="aca01-153">**Avisar se as filas mescladas por segundo para conexões de LAN forem menores que o limite**</span><span class="sxs-lookup"><span data-stu-id="aca01-153">**Warn if rows merged per second for LAN connections is less than the threshold**</span></span>  
  
    -   <span data-ttu-id="aca01-154">**Avisar se as filas mescladas por segundo para conexões discadas forem menores que o limite**</span><span class="sxs-lookup"><span data-stu-id="aca01-154">**Warn if rows merged per second for dialup connections is less than the threshold**</span></span>  
  
4.  <span data-ttu-id="aca01-155">Defina limites para os avisos na coluna **Limite** .</span><span class="sxs-lookup"><span data-stu-id="aca01-155">Set thresholds for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="aca01-156">Por exemplo, caso tenha selecionado **Avisar se o tamanho de mesclagem para conexões discadas exceder o limite** na etapa 3, você poderá selecionar um intervalo de **10 minutos** na coluna **Limite** .</span><span class="sxs-lookup"><span data-stu-id="aca01-156">For example, if you selected **Warn if a merge length for dialup connections exceeds the threshold** in step 3, you could select a time of **10 minutes** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="aca01-157">Clique em **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="aca01-157">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="aca01-158">Para configurar um alerta para um limite</span><span class="sxs-lookup"><span data-stu-id="aca01-158">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="aca01-159">Clique em **Configurar Alertas**.</span><span class="sxs-lookup"><span data-stu-id="aca01-159">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="aca01-160">Na caixa de diálogo **Configurar Alertas de Replicação** , selecione um alerta e então clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="aca01-160">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="aca01-161">Essa caixa de diálogo exibe os alertas para todos os tipos de publicação, inclusive alertas que não estão relacionados com o monitoramento de limites.</span><span class="sxs-lookup"><span data-stu-id="aca01-161">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span>  
  
3.  <span data-ttu-id="aca01-162">Defina as opções na caixa de diálogo **Propriedades do alerta \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="aca01-162">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="aca01-163">Na página **Geral** , clique em **Habilitar**; especifique em qual banco de dados deverá ser aplicado o alerta.</span><span class="sxs-lookup"><span data-stu-id="aca01-163">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="aca01-164">Na página **Resposta** , especifique se deve ser enviado um e-mail e/ou se deverá ser executado um trabalho.</span><span class="sxs-lookup"><span data-stu-id="aca01-164">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="aca01-165">Na página **Opções** , personalize o texto da resposta.</span><span class="sxs-lookup"><span data-stu-id="aca01-165">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="aca01-166">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="aca01-166">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-snapshot-publication"></a><a name="Snapshot"></a><span data-ttu-id="aca01-167">Definir limites e avisos para uma publicação de instantâneo</span><span class="sxs-lookup"><span data-stu-id="aca01-167">Set thresholds and warnings for a snapshot publication</span></span>  
  
1.  <span data-ttu-id="aca01-168">Expanda um Grupo do publicador no painel esquerdo, expanda um Publicador e clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="aca01-168">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="aca01-169">Clique na guia **avisos** . Para exibir mais informações sobre as opções nessa guia, clique em **ajuda** no menu superior.</span><span class="sxs-lookup"><span data-stu-id="aca01-169">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the top menu.</span></span>  
  
3.  <span data-ttu-id="aca01-170">Ative uma aviso selecionando a caixa de seleção **Avisar se uma assinatura for expirar dentro do limite**.</span><span class="sxs-lookup"><span data-stu-id="aca01-170">Enable a warning by selecting the check box **Warn if a subscription will expire within the threshold**.</span></span>  
  
4.  <span data-ttu-id="aca01-171">Defina um limite para o aviso na coluna **Limite** .</span><span class="sxs-lookup"><span data-stu-id="aca01-171">Set a threshold for the warning in the **Threshold** column.</span></span> <span data-ttu-id="aca01-172">Por exemplo, você pode selecionar um valor de **70%** na coluna **Limite** .</span><span class="sxs-lookup"><span data-stu-id="aca01-172">For example, you could select a value of **70%** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="aca01-173">Clique em **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="aca01-173">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="aca01-174">Para configurar um alerta para um limite</span><span class="sxs-lookup"><span data-stu-id="aca01-174">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="aca01-175">Clique em **Configurar Alertas**.</span><span class="sxs-lookup"><span data-stu-id="aca01-175">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="aca01-176">Na caixa de diálogo **Configurar Alertas de Replicação** , selecione um alerta e então clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="aca01-176">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="aca01-177">Essa caixa de diálogo exibe os alertas para todos os tipos de publicação, inclusive alertas que não estão relacionados com o monitoramento de limites.</span><span class="sxs-lookup"><span data-stu-id="aca01-177">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="aca01-178">Para obter mais informações, consulte [Usar alertas para eventos do agente de replicação](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="aca01-178">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="aca01-179">Defina as opções na caixa de diálogo **Propriedades do alerta \<AlertName>** :</span><span class="sxs-lookup"><span data-stu-id="aca01-179">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="aca01-180">Na página **Geral** , clique em **Habilitar**; especifique em qual banco de dados deverá ser aplicado o alerta.</span><span class="sxs-lookup"><span data-stu-id="aca01-180">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="aca01-181">Na página **Resposta** , especifique se deve ser enviado um e-mail e/ou se deverá ser executado um trabalho.</span><span class="sxs-lookup"><span data-stu-id="aca01-181">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="aca01-182">Na página **Opções** , personalize o texto da resposta.</span><span class="sxs-lookup"><span data-stu-id="aca01-182">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="aca01-183">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="aca01-183">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca01-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aca01-184">See Also</span></span>  
 [<span data-ttu-id="aca01-185">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="aca01-185">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
