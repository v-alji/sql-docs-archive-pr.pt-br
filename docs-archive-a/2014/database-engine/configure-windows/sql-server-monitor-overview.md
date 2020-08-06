---
title: Visão geral do SQL Server Monitor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlservermonitor.main.f1
helpviewer_keywords:
- SQL Server Monitor [SQL Server]
ms.assetid: 048ae16d-31c3-489a-9f1e-1400a3bacd39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab90186ed493e616e672cfacf881fd61be166f88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569637"
---
# <a name="sql-server-monitor-overview"></a><span data-ttu-id="750a4-102">Visão geral do SQL Server Monitor</span><span class="sxs-lookup"><span data-stu-id="750a4-102">SQL Server Monitor Overview</span></span>
  <span data-ttu-id="750a4-103">O SQL Server Monitor não realiza funções de monitoramento, mas hospeda módulos que as realizam.</span><span class="sxs-lookup"><span data-stu-id="750a4-103">SQL Server Monitor does not perform monitoring functions, but it hosts modules that do.</span></span> <span data-ttu-id="750a4-104">Os módulos do SQL Server Monitor incluem o Replication Monitor e o Monitor de Espelhamento de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="750a4-104">The SQL Server Monitor modules include Replication Monitor and Database Mirroring Monitor.</span></span>  
  
 <span data-ttu-id="750a4-105">Para usar um desses módulos, selecione o módulo no menu **Ir** .</span><span class="sxs-lookup"><span data-stu-id="750a4-105">To use one of these modules, select that module on the **Go** menu.</span></span> <span data-ttu-id="750a4-106">O módulo presentemente selecionado possui o conteúdo de navegação e os painéis de detalhes, interação de usuário nos painéis de detalhes e as consultas de conteúdo e status.</span><span class="sxs-lookup"><span data-stu-id="750a4-106">The currently selected module owns the content of the navigation and detail panes, user interaction in the detail panes, and the queries for content and status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="750a4-107">Para obter mais informações sobre esses monitores, consulte [Replicação de monitoramento](../../relational-databases/replication/monitoring-replication.md) e [Monitorando o espelhamento de banco de dados &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="750a4-107">For more information about these monitors, see [Monitoring Replication](../../relational-databases/replication/monitoring-replication.md) and [Monitoring Database Mirroring &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="750a4-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="750a4-108">Permissions</span></span>  
  
-   <span data-ttu-id="750a4-109">Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="750a4-109">Replication Monitor</span></span>  
  
     <span data-ttu-id="750a4-110">Para monitorar a replicação é preciso ser membro da função de servidor fixa **sysadmin** no Distribuido ou membro da função de banco de dados fixa **replmonitor** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="750a4-110">To monitor replication, you must be a member of the **sysadmin** fixed server role at the Distributor or a member of the **replmonitor** fixed database role in the distribution database.</span></span> <span data-ttu-id="750a4-111">Um administrador de sistema pode adicionar qualquer usuário à função **replmonitor** , o que permite que o usuário exiba a atividade de replicação no Replication Monitor. No entanto, o usuário não pode administrar a replicação.</span><span class="sxs-lookup"><span data-stu-id="750a4-111">A system administrator can add any user to the **replmonitor** role, which allows that user to view replication activity in Replication Monitor; however, the user cannot administer replication.</span></span>  
  
-   <span data-ttu-id="750a4-112">Monitor de Espelhamento de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="750a4-112">Database Mirroring Monitor</span></span>  
  
     <span data-ttu-id="750a4-113">Para monitorar um espelhamento de banco de dados, é preciso ser membro da função de servidor fixa **sysadmin** ou da função de banco de dados fixa **dbm_monitor** na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="750a4-113">To monitor database mirroring, you must be a member of either the **sysadmin** fixed server role or the **dbm_monitor** fixed database role on the server instance.</span></span> <span data-ttu-id="750a4-114">Se você for um membro do **sysadmin** ou do **dbm_monitor** em apenas uma das instâncias do servidor parceiro, o monitor poderá se conectar apenas àquele parceiro e não poderá recuperar as informações do outro parceiro.</span><span class="sxs-lookup"><span data-stu-id="750a4-114">If you are a member of **sysadmin** or **dbm_monitor** on only one of the partner server instances, the monitor can connect only to that partner; the monitor cannot retrieve information from the other partner.</span></span> <span data-ttu-id="750a4-115">Para obter mais informações, consulte [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="750a4-115">For more information, see [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="menu-options"></a><span data-ttu-id="750a4-116">Menu Opções</span><span class="sxs-lookup"><span data-stu-id="750a4-116">Menu Options</span></span>  
 <span data-ttu-id="750a4-117">O SQL Server Monitor possui um menu que contém comandos que pertencem ao SQL Server Monitor.</span><span class="sxs-lookup"><span data-stu-id="750a4-117">SQL Server Monitor has a menu that contains commands that pertain to SQL Server Monitor.</span></span> <span data-ttu-id="750a4-118">Esse menu pode igualmente conter comandos do módulo selecionado.</span><span class="sxs-lookup"><span data-stu-id="750a4-118">This menu may also contain commands from the selected module.</span></span>  
  
 <span data-ttu-id="750a4-119">As opções de menu a seguir pertencem ao SQL Server Monitor.</span><span class="sxs-lookup"><span data-stu-id="750a4-119">The following menu options pertain to SQL Server Monitor.</span></span>  
  
 <span data-ttu-id="750a4-120">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="750a4-120">**File**</span></span>  
 <span data-ttu-id="750a4-121">Esse menu contém o comando **Sair** .</span><span class="sxs-lookup"><span data-stu-id="750a4-121">This menu contains the **Exit** command.</span></span>  
  
 <span data-ttu-id="750a4-122">**Ação**</span><span class="sxs-lookup"><span data-stu-id="750a4-122">**Action**</span></span>  
 <span data-ttu-id="750a4-123">Contém o menu de contexto do nó selecionado na árvore de navegação.</span><span class="sxs-lookup"><span data-stu-id="750a4-123">Contains the context menu of the node selected in the navigation tree.</span></span>  
  
 <span data-ttu-id="750a4-124">**Go**</span><span class="sxs-lookup"><span data-stu-id="750a4-124">**Go**</span></span>  
 <span data-ttu-id="750a4-125">Contém uma lista de componentes de monitoramento:</span><span class="sxs-lookup"><span data-stu-id="750a4-125">Contains a list of monitoring components:</span></span>  
  
-   <span data-ttu-id="750a4-126">Espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="750a4-126">Database Mirroring</span></span>  
  
-   <span data-ttu-id="750a4-127">Replicação</span><span class="sxs-lookup"><span data-stu-id="750a4-127">Replication</span></span>  
  
 <span data-ttu-id="750a4-128">**Para usar o SQL Server Management Studio para monitorar o espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="750a4-128">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="750a4-129">Iniciar o Monitor de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="750a4-129">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="750a4-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="750a4-130">See Also</span></span>  
 [<span data-ttu-id="750a4-131">Monitorando o espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="750a4-131">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-sql-server.md)  
  
  
