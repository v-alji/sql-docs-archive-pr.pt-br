---
title: Usar objetos de desempenho | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- SQL Server Agent service, monitoring
- SQL Server Agent service, performance objects
- SQL Server Agent, performance objects
- performance objects [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- performance counters [SQL Server], SQL Server Agent
- counters [SQL Server], SQL Server Agent
ms.assetid: 830b843a-6b2a-4620-a51b-98358e9fc54b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7c1fe3f4a7d9a5fec901f84d8e913e49a4dbd1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575534"
---
# <a name="use-performance-objects"></a><span data-ttu-id="abc54-102">Usar objetos de desempenho</span><span class="sxs-lookup"><span data-stu-id="abc54-102">Use Performance Objects</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="abc54-103">O Agent contém objetos de desempenho e contadores para monitorar o desempenho do serviço.</span><span class="sxs-lookup"><span data-stu-id="abc54-103">Agent includes performance objects and counters to monitor how the service is performing.</span></span> <span data-ttu-id="abc54-104">Esses objetos de desempenho permitem-lhe usar o Monitor de Desempenho — uma ferramenta do Windows — para identificar o que o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent está fazendo em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="abc54-104">These performance objects allow you to use Performance Monitor, a Windows tool, to identify what the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is doing in the background.</span></span> <span data-ttu-id="abc54-105">Por exemplo, é possível identificar quantos trabalhos ativos o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent executa atualmente, para determinar quais deles estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="abc54-105">For example, you can identify how many active jobs the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is currently running to identify those jobs that are blocked.</span></span>  
  
 <span data-ttu-id="abc54-106">Existem objetos de desempenho e contadores do serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para cada instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalada em um computador.</span><span class="sxs-lookup"><span data-stu-id="abc54-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects and counters exist for each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is installed on a computer.</span></span> <span data-ttu-id="abc54-107">Os objetos de desempenho são nomeados de acordo com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que representam.</span><span class="sxs-lookup"><span data-stu-id="abc54-107">Performance objects are named according to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that each object represents.</span></span>  
  
 <span data-ttu-id="abc54-108">A tabela a seguir mostra como os objetos de desempenho do serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent são nomeados:</span><span class="sxs-lookup"><span data-stu-id="abc54-108">The following table shows how the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects are named:</span></span>  
  
|<span data-ttu-id="abc54-109">Tipo de instância</span><span class="sxs-lookup"><span data-stu-id="abc54-109">Instance type</span></span>|<span data-ttu-id="abc54-110">Nome do objeto</span><span class="sxs-lookup"><span data-stu-id="abc54-110">Object name</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="abc54-111">Padrão</span><span class="sxs-lookup"><span data-stu-id="abc54-111">Default</span></span>|<span data-ttu-id="abc54-112">**SQLAgent:** *objeto*:*contador*</span><span class="sxs-lookup"><span data-stu-id="abc54-112">**SQLAgent:** *object*:*counter*</span></span>|  
|<span data-ttu-id="abc54-113">nomeado</span><span class="sxs-lookup"><span data-stu-id="abc54-113">Named</span></span>|<span data-ttu-id="abc54-114">**SQLAgent$**</span><span class="sxs-lookup"><span data-stu-id="abc54-114">**SQLAgent$**</span></span><br /> <span data-ttu-id="abc54-115">***instance_name* :** *objeto*:*contador*</span><span class="sxs-lookup"><span data-stu-id="abc54-115">***instance_name* :** *object*:*counter*</span></span>|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="abc54-116">contém os objetos de desempenho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a seguir.</span><span class="sxs-lookup"><span data-stu-id="abc54-116">includes the following performance objects for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
|<span data-ttu-id="abc54-117">Nome do objeto</span><span class="sxs-lookup"><span data-stu-id="abc54-117">Object name</span></span>|<span data-ttu-id="abc54-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="abc54-118">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="abc54-119">SQLAgent:Jobs</span><span class="sxs-lookup"><span data-stu-id="abc54-119">SQLAgent:Jobs</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobs-object.md)|<span data-ttu-id="abc54-120">Informações sobre o desempenho de trabalhos que foram iniciados, taxas de êxito e status atual</span><span class="sxs-lookup"><span data-stu-id="abc54-120">Performance information about jobs that have been started, success rates, and current status</span></span>|  
|[<span data-ttu-id="abc54-121">SQLAgent:JobSteps</span><span class="sxs-lookup"><span data-stu-id="abc54-121">SQLAgent:JobSteps</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobsteps-object.md)|<span data-ttu-id="abc54-122">Informações sobre o status de etapas de trabalho</span><span class="sxs-lookup"><span data-stu-id="abc54-122">Status information about job steps</span></span>|  
|[<span data-ttu-id="abc54-123">SQLAgent:Alerts</span><span class="sxs-lookup"><span data-stu-id="abc54-123">SQLAgent:Alerts</span></span>](../../relational-databases/performance-monitor/sql-server-agent-alerts-object.md)|<span data-ttu-id="abc54-124">Informações sobre o número de alertas e notificações</span><span class="sxs-lookup"><span data-stu-id="abc54-124">Information about number of alerts and notifications</span></span>|  
|[<span data-ttu-id="abc54-125">SQLAgent:Statistics</span><span class="sxs-lookup"><span data-stu-id="abc54-125">SQLAgent:Statistics</span></span>](../../relational-databases/performance-monitor/sql-server-agent-statistics-object.md)|<span data-ttu-id="abc54-126">Informações gerais do desempenho</span><span class="sxs-lookup"><span data-stu-id="abc54-126">General performance information</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="abc54-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="abc54-127">See Also</span></span>  
 <span data-ttu-id="abc54-128">[Monitorar e ajustar o desempenho](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span><span class="sxs-lookup"><span data-stu-id="abc54-128">[Monitor and Tune for Performance](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span></span>  
 [<span data-ttu-id="abc54-129">Iniciar o Monitor do Sistema &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="abc54-129">Start System Monitor &#40;Windows&#41;</span></span>](../../relational-databases/performance/start-system-monitor-windows.md)  
  
  
