---
title: Cache, atualização e desempenho do Replication Monitor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], Replication Monitor
- cache [SQL Server], replication
- Replication Monitor, caching
- refreshing data
- Replication Monitor, refreshing
ms.assetid: a2d8b666-ed41-4f86-b2b8-c8e118416ab7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b04a91e971e65d19c66cc36f142d8c4764b1b05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571942"
---
# <a name="caching-refresh-and-replication-monitor-performance"></a><span data-ttu-id="b3fdf-102">Cache, atualização e desempenho do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="b3fdf-102">Caching, Refresh, and Replication Monitor Performance</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="b3fdf-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]O Replication Monitor foi projetado para monitorar com eficiência um grande número de computadores em um sistema de produção.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor is designed to efficiently monitor a large number of computers in a production system.</span></span> <span data-ttu-id="b3fdf-104">As consultas que o Replication Monitor usa para executar cálculos e reunir dados são armazenadas em cache e atualizadas periodicamente.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-104">The queries that Replication Monitor uses to perform calculations and gather data are cached and refreshed on a periodic basis.</span></span> <span data-ttu-id="b3fdf-105">O armazenamento em cache reduz o número de consultas e cálculos necessários conforme diferentes páginas são exibidas no Replication Monitor, e permite que a monitoração seja bem-escalonada para usuários múltiplos.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-105">Caching reduces the number of queries and calculations required as you view different pages in Replication Monitor and allows monitoring to scale well for multiple users.</span></span>  
  
 <span data-ttu-id="b3fdf-106">A atualização do cache é controlada por um trabalho do Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , o **Atualizador de monitoração de replicação para distribuição**.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-106">Cache refresh is handled by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job, the **Replication monitoring refresher for distribution**.</span></span> <span data-ttu-id="b3fdf-107">O trabalho é executado continuamente, mas a agenda para a atualização de cache é baseada na espera de certo tempo após a atualização anterior:</span><span class="sxs-lookup"><span data-stu-id="b3fdf-107">The job runs continuously, but the cache refresh schedule is based on waiting a certain amount time after the previous refresh:</span></span>  
  
-   <span data-ttu-id="b3fdf-108">Se houver alterações de histórico de agente desde que o cache foi criado por último, o tempo de espera será no mínimo de 4 segundos ou o tempo levado para criar o cache anterior.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-108">If there were agent history changes since the cache was last created, the wait time is the minimum of: 4 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
-   <span data-ttu-id="b3fdf-109">Se não houver alterações de histórico de agente desde a última criação do cache (podem ter havido outras alterações), o tempo de espera será no máximo de 30 segundos ou o tempo levado para criar o cache anterior.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-109">If there were no agent history changes since the cache was last created (there could have been other changes), the wait time is the maximum of: 30 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
## <a name="refreshing-the-replication-monitor-user-interface"></a><span data-ttu-id="b3fdf-110">Atualizando a interface de usuário do Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="b3fdf-110">Refreshing the Replication Monitor User Interface</span></span>  
 <span data-ttu-id="b3fdf-111">A interface de usuário do Replication Monitor pode ser atualizada das formas a seguir:</span><span class="sxs-lookup"><span data-stu-id="b3fdf-111">The Replication Monitor user interface can be refreshed in the following ways:</span></span>  
  
-   <span data-ttu-id="b3fdf-112">A janela principal do Replication Monitor (incluindo todas as guias), é atualizada automaticamente a cada cinco segundos por padrão.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-112">The main Replication Monitor window (including all tabs), automatically refreshes by default every five seconds.</span></span> <span data-ttu-id="b3fdf-113">Atualizações automáticas não forçam a atualização do cache; a interface do usuário mostra a versão mais recente dos dados do cache.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-113">Automatic refreshes do not force a refresh of the cache; the user interface displays the most recent version of the data from the cache.</span></span> <span data-ttu-id="b3fdf-114">Para personalizar a taxa de atualização usada para todas as janelas associadas com um Publicador, edite as configurações do Publicador.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-114">You can customize the refresh rate used for all windows associated with a Publisher by editing the Publisher settings.</span></span> <span data-ttu-id="b3fdf-115">Também é possível desabilitar as atualizações automáticas para um Publicador.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-115">You can also disable automatic refreshes for a Publisher.</span></span>  
  
-   <span data-ttu-id="b3fdf-116">As janelas de detalhe que são executadas a partir do Replication Monitor não são automaticamente atualizadas por padrão, com exceção das janelas relacionadas a assinaturas de mesclagem que estão sendo sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-116">The detail windows that are launched from Replication Monitor are not automatically refreshed by default, with the exception of windows related to merge subscriptions that are synchronizing.</span></span> <span data-ttu-id="b3fdf-117">Se você especificar que as janelas de detalhes devem ser atualizadas automaticamente, elas serão atualizadas na mesma agenda que a janela principal do Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-117">If you specify that detail windows should automatically refresh, they refresh on the same schedule as the main Replication Monitor window.</span></span>  
  
-   <span data-ttu-id="b3fdf-118">Todas as janelas podem ser atualizadas manualmente pressionando F5 ou clicando com o botão direito em um nó na árvore do Replication Monitor e, em seguida, clicando em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-118">All windows can be manually refreshed by pressing F5 or by right-clicking a node in the Replication Monitor tree and clicking **Refresh**.</span></span> <span data-ttu-id="b3fdf-119">Atualizações manuais forçam uma atualização do cache.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-119">Manual refreshes force a refresh of the cache.</span></span>  
  
 <span data-ttu-id="b3fdf-120">Para obter mais informações, consulte [Atualizar dados no Replication Monitor](refresh-data-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b3fdf-120">For more information, see [Refresh Data in Replication Monitor](refresh-data-in-replication-monitor.md).</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="b3fdf-121">Considerações sobre desempenho</span><span class="sxs-lookup"><span data-stu-id="b3fdf-121">Performance Considerations</span></span>  
 <span data-ttu-id="b3fdf-122">Embora o Replication Monitor seja projetado para executar de forma eficaz, esteja atento ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="b3fdf-122">Although Replication Monitor is designed to run efficiently, be aware of the following:</span></span>  
  
-   <span data-ttu-id="b3fdf-123">Se tiver um grande número de publicações e assinaturas, considere definir uma agenda de atualização automática menos frequente para a interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-123">If you have a large number of publications or subscriptions, consider setting a less frequent automatic refresh schedule for the user interface.</span></span>  
  
-   <span data-ttu-id="b3fdf-124">Evite executar várias instâncias do Replication Monitor simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-124">Avoid concurrently running multiple instances of Replication Monitor.</span></span>  
  
-   <span data-ttu-id="b3fdf-125">Evite registrar um número grande de Distribuidores e configurar o Replication Monitor para conectar-se automaticamente a todos eles.</span><span class="sxs-lookup"><span data-stu-id="b3fdf-125">Avoid registering a large number of Distributors and setting Replication Monitor to automatically connect to all of them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3fdf-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b3fdf-126">See Also</span></span>  
 <span data-ttu-id="b3fdf-127">[Executar trabalhos de manutenção de replicação &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="b3fdf-127">[Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="b3fdf-128">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="b3fdf-128">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
