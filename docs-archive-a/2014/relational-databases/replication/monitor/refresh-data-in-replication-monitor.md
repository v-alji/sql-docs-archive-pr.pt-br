---
title: Atualizar dados no Replication Monitor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- refreshing data
ms.assetid: e9582244-7d00-45f4-be16-020a65c76a5e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f097dea21b06540293e9b60b7de9315323b4168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685561"
---
# <a name="refresh-data-in-replication-monitor"></a><span data-ttu-id="e8638-102">Atualizar dados no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="e8638-102">Refresh Data in Replication Monitor</span></span>
  <span data-ttu-id="e8638-103">No Replication Monitor, a janela principal e a janela de detalhes (as janelas abertas na janela principal) podem ser atualizadas automaticamente e manualmente.</span><span class="sxs-lookup"><span data-stu-id="e8638-103">In Replication Monitor, the main window and detail windows (those windows launched from the main window) can be refreshed automatically or manually.</span></span> <span data-ttu-id="e8638-104">Para atualizar uma janela manualmente, pressione F5.</span><span class="sxs-lookup"><span data-stu-id="e8638-104">To refresh a window manually, press F5.</span></span> <span data-ttu-id="e8638-105">Por padrão, a janela principal é atualizada a cada cinco segundos automaticamente; a taxa pode ser personalizada para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="e8638-105">By default, the main window is refreshed automatically every five seconds; the rate can be customized for each Publisher.</span></span>  
  
 <span data-ttu-id="e8638-106">Os dados exibidos no Replication Monitor são consultados por meio de um cache; para obter informações sobre a relação entre o cache e a atualização do Replication Monitor, consulte [Cache, atualização e desempenho do Replication Monitor](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="e8638-106">The data displayed in Replication Monitor is queried from a cache; for information about the relationship between the cache and refreshing Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span> <span data-ttu-id="e8638-107">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="e8638-107">For information about starting Replication Monitor, see [Start the Replication Monitor](start-the-replication-monitor.md).</span></span>  
  
### <a name="to-set-refresh-options-for-replication-monitor"></a><span data-ttu-id="e8638-108">Para definir as opções de atualização para o Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="e8638-108">To set refresh options for Replication Monitor</span></span>  
  
1.  <span data-ttu-id="e8638-109">Clique com o botão direito do mouse no Publicador do painel esquerdo do Replication Monitor e clique em **Configurações do Publicador**.</span><span class="sxs-lookup"><span data-stu-id="e8638-109">Right-click a Publisher in the left pane of Replication Monitor, and then click **Publisher Settings**.</span></span>  
  
2.  <span data-ttu-id="e8638-110">Na caixa de diálogo **Configurações do Publicador** , defina as opções **Atualização automática** e **Taxa de atualização** .</span><span class="sxs-lookup"><span data-stu-id="e8638-110">In the **Publisher Settings** dialog box, set the **Auto refresh** and **Refresh rate** options.</span></span> <span data-ttu-id="e8638-111">As configurações de **Atualização automática** afetam a janela principal do Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="e8638-111">The **Auto refresh** setting affects the main window in Replication Monitor.</span></span> <span data-ttu-id="e8638-112">As configurações de **Taxa de atualização** também afetam todos os detalhes definidos para atualizarem automaticamente (alterações na configuração afetam apenas as janelas de detalhes abertas depois da alteração).</span><span class="sxs-lookup"><span data-stu-id="e8638-112">The **Refresh rate** setting also affects any detail windows that are set to refresh automatically (changes to the setting only affect the detail windows opened after the change).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-specify-that-a-detail-window-should-automatically-refresh"></a><span data-ttu-id="e8638-113">Para especificar que uma janela de detalhe deverá atualizar automaticamente</span><span class="sxs-lookup"><span data-stu-id="e8638-113">To specify that a detail window should automatically refresh</span></span>  
  
1.  <span data-ttu-id="e8638-114">Abra uma janela de detalhe no Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="e8638-114">Open a detail window in Replication Monitor.</span></span> <span data-ttu-id="e8638-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e8638-115">For example:</span></span>  
  
    1.  <span data-ttu-id="e8638-116">Expanda um Grupo do publicador no painel esquerdo, expanda um Publicador e clique em uma publicação.</span><span class="sxs-lookup"><span data-stu-id="e8638-116">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="e8638-117">Clique na guia **Todas as Assinaturas** .</span><span class="sxs-lookup"><span data-stu-id="e8638-117">Click the **All Subscriptions** tab.</span></span>  
  
    3.  <span data-ttu-id="e8638-118">Clique com o botão direito do mouse em uma assinatura e clique em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e8638-118">Right-click a subscription, and then click **View Details**.</span></span>  
  
2.  <span data-ttu-id="e8638-119">Na janela de detalhe **Assinatura \<SubscriptionName>** , clique em **Ação** e depois em **Atualização automática**.</span><span class="sxs-lookup"><span data-stu-id="e8638-119">In the **Subscription \<SubscriptionName>** detail window, click **Action**, and then click **Auto Refresh**.</span></span> <span data-ttu-id="e8638-120">A taxa de atualização é determinada pela configuração em **Taxa de atualização** , na caixa de diálogo **Configurações do Publicador** .</span><span class="sxs-lookup"><span data-stu-id="e8638-120">The refresh rate is determined by the **Refresh rate** setting in the **Publisher Settings** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8638-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8638-121">See Also</span></span>  
 [<span data-ttu-id="e8638-122">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="e8638-122">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
