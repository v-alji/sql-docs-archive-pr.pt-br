---
title: Isolar problemas de desempenho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- isolating performance problems [SQL Server]
- monitoring performance [SQL Server], isolating problems
- database monitoring [SQL Server], isolating problems
- tuning databases [SQL Server], isolating problems
- monitoring server performance [SQL Server], isolating problems
- database performance [SQL Server], isolating problems
- server performance [SQL Server], isolating problems
ms.assetid: 2eb425cb-9166-4027-ae08-c8fc2d236f44
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b42d780a8174ab57d00de72e8b00ef7af0abc17e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680920"
---
# <a name="isolate-performance-problems"></a><span data-ttu-id="9b499-102">Isolar problemas de desempenho</span><span class="sxs-lookup"><span data-stu-id="9b499-102">Isolate Performance Problems</span></span>
  <span data-ttu-id="9b499-103">Muitas vezes, é mais eficaz usar várias ferramentas do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou do Microsoft Windows juntas para isolar problemas de desempenho de banco de dados do que usar uma ferramenta de cada vez.</span><span class="sxs-lookup"><span data-stu-id="9b499-103">It is often more effective to use several [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Microsoft Windows tools together to isolate database performance problems than to use one tool at a time.</span></span> <span data-ttu-id="9b499-104">Por exemplo, o recurso gráfico Plano de Execução ajuda a reconhecer deadlocks rapidamente em uma única consulta.</span><span class="sxs-lookup"><span data-stu-id="9b499-104">For example, the graphical Execution Plan feature, also called Showplan, helps you quickly recognize deadlocks in a single query.</span></span> <span data-ttu-id="9b499-105">No entanto, você poderá reconhecer alguns outros problemas de desempenho mais facilmente se usar os recursos de monitoramento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do Windows juntos.</span><span class="sxs-lookup"><span data-stu-id="9b499-105">However, you can recognize some other performance problems more easily if you use the monitoring features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows together.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="9b499-106">pode ser usado para monitorar e solucionar problemas relacionados a Transact-SQL e a aplicativos.</span><span class="sxs-lookup"><span data-stu-id="9b499-106">can be used to monitor and troubleshoot Transact-SQL and application-related problems.</span></span> <span data-ttu-id="9b499-107">O Monitor do Sistema pode ser usado para monitorar hardware e outros problemas relacionados a sistema.</span><span class="sxs-lookup"><span data-stu-id="9b499-107">System Monitor can be used to monitor hardware and other system-related problems.</span></span>  
  
 <span data-ttu-id="9b499-108">Você pode monitorar as seguintes áreas para solucionar problemas:</span><span class="sxs-lookup"><span data-stu-id="9b499-108">You can monitor the following areas to troubleshoot problems:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9b499-109">procedimentos armazenados ou lotes de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] enviados por aplicativos de usuário.</span><span class="sxs-lookup"><span data-stu-id="9b499-109">stored procedures or batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements submitted by user applications.</span></span>  
  
-   <span data-ttu-id="9b499-110">Atividade de usuário, tal como bloqueios ou deadlocks.</span><span class="sxs-lookup"><span data-stu-id="9b499-110">User activity, such as blocking locks or deadlocks.</span></span>  
  
-   <span data-ttu-id="9b499-111">Atividade de hardware, tal como uso de disco.</span><span class="sxs-lookup"><span data-stu-id="9b499-111">Hardware activity, such as disk usage.</span></span>  
  
 <span data-ttu-id="9b499-112">Os problemas podem incluir:</span><span class="sxs-lookup"><span data-stu-id="9b499-112">Problems can include:</span></span>  
  
-   <span data-ttu-id="9b499-113">Erros de desenvolvimento de aplicativo que envolvam instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] incorretamente escritas.</span><span class="sxs-lookup"><span data-stu-id="9b499-113">Application development errors involving incorrectly written [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
-   <span data-ttu-id="9b499-114">Erros de hardware, tais como erros relacionados a disco ou a rede.</span><span class="sxs-lookup"><span data-stu-id="9b499-114">Hardware errors, such as disk- or network-related errors.</span></span>  
  
-   <span data-ttu-id="9b499-115">Bloqueio excessivo devido a um banco de dados incorretamente projetado.</span><span class="sxs-lookup"><span data-stu-id="9b499-115">Excessive blocking due to an incorrectly designed database.</span></span>  
  
## <a name="tools-for-common-performance-problems"></a><span data-ttu-id="9b499-116">Ferramentas para problemas de desempenho comuns</span><span class="sxs-lookup"><span data-stu-id="9b499-116">Tools for Common Performance Problems</span></span>  
 <span data-ttu-id="9b499-117">Igualmente importante é a seleção criteriosa do problema de desempenho que você deseja que cada ferramenta monitore ou ajuste.</span><span class="sxs-lookup"><span data-stu-id="9b499-117">Equally important is careful selection of the performance problem that you want each tool to monitor or tune.</span></span> <span data-ttu-id="9b499-118">A ferramenta e o utilitário dependem do tipo de problema de desempenho que você queira resolver.</span><span class="sxs-lookup"><span data-stu-id="9b499-118">The tool and the utility depend on the type of performance problem you want to resolve.</span></span>  
  
 <span data-ttu-id="9b499-119">Os tópicos a seguir descrevem uma série de ferramentas de monitoramento e de ajuste e os problemas de que dão conta.</span><span class="sxs-lookup"><span data-stu-id="9b499-119">The following topics describe a variety of monitoring and tuning tools and the problems they uncover.</span></span>  
  
 [<span data-ttu-id="9b499-120">Identificar afunilamentos</span><span class="sxs-lookup"><span data-stu-id="9b499-120">Identify Bottlenecks</span></span>](identify-bottlenecks.md)  
  
 [<span data-ttu-id="9b499-121">Monitorar o uso de memória</span><span class="sxs-lookup"><span data-stu-id="9b499-121">Monitor Memory Usage</span></span>](../performance-monitor/monitor-memory-usage.md)  
  
  
