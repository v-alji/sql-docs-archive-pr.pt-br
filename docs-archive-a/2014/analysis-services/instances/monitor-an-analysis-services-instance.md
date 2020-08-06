---
title: Monitorar uma instância de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- monitoring [Analysis Services - multidimensional data]
- multidimensional data [Analysis Services], monitoring
- monitoring performance [SQL Server], SQL Server Profiler
- performance [SQL Server], monitoring tools
ms.assetid: 2f0ab717-05f3-427e-b8cd-a8bdca374add
author: minewiskan
ms.author: owend
ms.openlocfilehash: b98037ea9f26c339cdf7aba22c37e2cfb3dfbb97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576042"
---
# <a name="monitor-an-analysis-services-instance"></a><span data-ttu-id="0037a-102">Monitorar uma instância do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0037a-102">Monitor an Analysis Services Instance</span></span>
  <span data-ttu-id="0037a-103">Você pode monitorar o desempenho do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ou Monitor de Desempenho, um aplicativo às vezes chamado de **PerfMon**.</span><span class="sxs-lookup"><span data-stu-id="0037a-103">You can monitor the performance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor, an application sometimes referred to as **PerfMon**.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="0037a-104">permite criar e gerenciar rastreamentos e analisar e repetir resultados de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="0037a-104">lets you create and manage traces and analyze and replay trace results.</span></span> <span data-ttu-id="0037a-105">O Monitor de Desempenho reporta em um status de servidor, como indexado por certos contadores, que são discutidos na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="0037a-105">Performance Monitor reports on server status, as indexed through certain counters, which are discussed in the next section.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0037a-106">Para obter mais informações sobre monitoramento, consulte o [Guia de operações do SQL Server 2008 R2](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="0037a-106">For more information about monitoring, see the [SQL Server 2008 R2 Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0037a-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0037a-107">In This Section</span></span>  
 <span data-ttu-id="0037a-108">Siga estes links para saber mais sobre como monitorar.</span><span class="sxs-lookup"><span data-stu-id="0037a-108">Follow these links to learn more about monitoring.</span></span>  
  
 [<span data-ttu-id="0037a-109">Eventos de rastreamento do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0037a-109">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)  
  
 [<span data-ttu-id="0037a-110">Use SQL Server Profiler to Monitor Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0037a-110">Use SQL Server Profiler to Monitor Analysis Services</span></span>](use-sql-server-profiler-to-monitor-analysis-services.md)  
  
 [<span data-ttu-id="0037a-111">Usar SQL Server eventos estendidos &#40;&#41; de XEvents para monitorar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0037a-111">Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services</span></span>](../instances/monitor-analysis-services-with-sql-server-extended-events.md)  
  
 [<span data-ttu-id="0037a-112">Usar DMVs &#40;Exibições de Gerenciamento Dinâmico&#41; para monitorar o Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0037a-112">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
 [<span data-ttu-id="0037a-113">Contadores de desempenho &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="0037a-113">Performance Counters &#40;SSAS&#41;</span></span>](performance-counters-ssas.md)  
  
  
