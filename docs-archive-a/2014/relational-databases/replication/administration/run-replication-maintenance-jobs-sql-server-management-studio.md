---
title: Executar trabalhos de manutenção de replicação (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server replication]
ms.assetid: 0dc485a0-5a50-41eb-a29d-f2b2fb920174
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9dc27c65e96a9f956ffa6d3edf9c72ed52f721a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683506"
---
# <a name="run-replication-maintenance-jobs-sql-server-management-studio"></a><span data-ttu-id="6e2fd-102">Executar trabalhos de manutenção de replicação (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6e2fd-102">Run Replication Maintenance Jobs (SQL Server Management Studio)</span></span>
  <span data-ttu-id="6e2fd-103">A replicação usa os seguintes trabalhos de manutenção:</span><span class="sxs-lookup"><span data-stu-id="6e2fd-103">Replication uses the following maintenance jobs:</span></span>  
  
-   <span data-ttu-id="6e2fd-104">**Reinicializar assinaturas com falha na validação de dados**</span><span class="sxs-lookup"><span data-stu-id="6e2fd-104">**Reinitialize subscriptions having data validation failures**</span></span>
-   <span data-ttu-id="6e2fd-105">**Limpeza de histórico de agente: distribuição**</span><span class="sxs-lookup"><span data-stu-id="6e2fd-105">**Agent history clean up: distribution**</span></span>
-   <span data-ttu-id="6e2fd-106">**Atualizador de monitoramento de replicação para distribuição.**</span><span class="sxs-lookup"><span data-stu-id="6e2fd-106">**Replication monitoring refresher for distribution.**</span></span>
-   <span data-ttu-id="6e2fd-107">**Verificação de agentes de replicação**</span><span class="sxs-lookup"><span data-stu-id="6e2fd-107">**Replication agents checkup**</span></span>
-   <span data-ttu-id="6e2fd-108">**Limpeza de distribuição: distribuição**</span><span class="sxs-lookup"><span data-stu-id="6e2fd-108">**Distribution clean up: distribution**</span></span>
-   <span data-ttu-id="6e2fd-109">**Limpeza de assinaturas expiradas**</span><span class="sxs-lookup"><span data-stu-id="6e2fd-109">**Expired subscription clean up**</span></span>  
  
 <span data-ttu-id="6e2fd-110">Inicie e pare esses trabalhos na pasta **Trabalhos** do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e na guia **Agentes** do Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-110">Start and stop these jobs from the **Jobs** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="6e2fd-111">Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](../monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).</span><span class="sxs-lookup"><span data-stu-id="6e2fd-111">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span> <span data-ttu-id="6e2fd-112">Exiba e modifique propriedades de cada trabalho na caixa de diálogo **Propriedades do trabalho – \<Job>** , que está disponível na mesma pasta e guia.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-112">View and modify properties for each job in the **Job Properties - \<Job>** dialog box, which is available from the same folder and tab.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="6e2fd-113">Para iniciar ou parar um trabalho de manutenção de replicação no Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e2fd-113">To start or stop a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="6e2fd-114">Conecte-se ao Distribuidor no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e, em seguida, expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-114">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="6e2fd-115">Expanda a pasta **SQL Server Agent** e, em seguida, a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="6e2fd-115">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="6e2fd-116">Clique com o botão direito do mouse em um trabalho e então clique em **Iniciar Trabalho** ou **Parar Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-116">Right-click a job, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="6e2fd-117">Para iniciar ou parar um trabalho de manutenção de replicação no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="6e2fd-117">To start or stop a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="6e2fd-118">Expanda um Grupo do publicador no Replication Monitor e, então, selecione um Publicador.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-118">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="6e2fd-119">Clique na guia **Agentes** .</span><span class="sxs-lookup"><span data-stu-id="6e2fd-119">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="6e2fd-120">Clique com o botão direito do mouse em um trabalho na grade e então clique em **Iniciar Trabalho** ou **Parar Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-120">Right-click a job in the grid, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="6e2fd-121">Para exibir e modificar propriedades de um trabalho de manutenção de replicação no Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e2fd-121">To view and modify properties for a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="6e2fd-122">Conecte-se ao Distribuidor no [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]e, em seguida, expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-122">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="6e2fd-123">Expanda a pasta **SQL Server Agent** e, em seguida, a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="6e2fd-123">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="6e2fd-124">Clique com o botão direito do mouse em um trabalho e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-124">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="6e2fd-125">Na caixa de diálogo **Propriedades do Trabalho – \<Job>** , se necessário, altere qualquer propriedade e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-125">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="6e2fd-126">Para exibir e modificar propriedades de um trabalho de manutenção de replicação no Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="6e2fd-126">To view and modify properties for a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="6e2fd-127">Expanda um Grupo do publicador no Replication Monitor e, então, selecione um Publicador.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-127">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="6e2fd-128">Clique na guia **Agentes** .</span><span class="sxs-lookup"><span data-stu-id="6e2fd-128">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="6e2fd-129">Clique com o botão direito do mouse em um trabalho na grade e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-129">Right-click a job in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="6e2fd-130">Na caixa de diálogo **Propriedades do Trabalho – \<Job>** , se necessário, altere qualquer propriedade e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e2fd-130">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e2fd-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e2fd-131">See Also</span></span>  
 <span data-ttu-id="6e2fd-132">[Iniciar e interromper um agente de replicação &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6e2fd-132">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="6e2fd-133">[Exibir informações e executar tarefas usando o Replication Monitor](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6e2fd-133">[View Information and Perform Tasks using Replication Monitor](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="6e2fd-134">Administração do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="6e2fd-134">Replication Agent Administration</span></span>](../agents/replication-agent-administration.md)  
  
  
