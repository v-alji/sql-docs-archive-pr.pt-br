---
title: Desempenho, instantâneos, cache (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- performance [Reporting Services]
- Reporting Services, performance
ms.assetid: 85afd00f-e8d7-4ef7-9174-2ff84d82f960
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f171586e136b36bd694fa40b15272f62e1cb1378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680821"
---
# <a name="performance-snapshots-caching-reporting-services"></a><span data-ttu-id="8e0b6-102">Desempenho, instantâneos, cache (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="8e0b6-102">Performance, Snapshots, Caching (Reporting Services)</span></span>
  <span data-ttu-id="8e0b6-103">O desempenho do servidor de relatório é afetado por uma combinação de fatores que incluem o hardware, o número de usuários simultâneos que acessam relatórios, a quantidade de dados em um relatório e o formato de saída.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-103">Report server performance is affected by a combination of factors that include hardware, number of concurrent users accessing reports, the amount of data in a report, and output format.</span></span> <span data-ttu-id="8e0b6-104">Para entender os fatores de desempenho específicos de sua instalação e quais reparos produzirão os resultados desejados, será necessário obter dados de linha de base e executar testes.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-104">To understand the performance factors that are specific to your installation and which remedies will produce the results you want, you will need to get baseline data and run tests.</span></span> <span data-ttu-id="8e0b6-105">Para obter mais informações sobre ferramentas e diretrizes, consulte as seguintes publicações no MSDN: [Otimização de desempenho do Reporting Services](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) e [Usando o Visual Studio 2005 para executar um teste de carregamento em um servidor de relatório do SQL Server 2005](https://go.microsoft.com/fwlink/?LinkID=77519).</span><span class="sxs-lookup"><span data-stu-id="8e0b6-105">For more information about tools and guidelines, see the following publications on MSDN: [Reporting Services Performance Optimization](https://blogs.msdn.com/b/sqlcat/archive/2013/10/30/reporting-services-performance-and-optimization.aspx) and [Using Visual Studio 2005 to Perform Load Testing on a SQL Server 2005 Reporting Services Report Server](https://go.microsoft.com/fwlink/?LinkID=77519).</span></span>  
  
 <span data-ttu-id="8e0b6-106">Os princípios gerais a serem considerados incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8e0b6-106">General principles to consider include the following:</span></span>  
  
-   <span data-ttu-id="8e0b6-107">O processamento e a renderização de relatórios são operações que consomem muita memória.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-107">Report processing and rendering are memory intensive operations.</span></span> <span data-ttu-id="8e0b6-108">Quando possível, escolha um computador que tenha bastante memória.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-108">When possible, choose a computer that has a lot of memory.</span></span>  
  
-   <span data-ttu-id="8e0b6-109">A hospedagem do servidor de relatório e do banco de dados do servidor de relatório em computadores separados tende a fornecer um melhor desempenho do hospedar ambos em um único computador avançado.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-109">Hosting the report server and the report server database on separate computers tends to provide better performance than hosting both on a single high-end computer.</span></span>  
  
-   <span data-ttu-id="8e0b6-110">Se o processamento de todos os relatórios estiver lento, avalie a possibilidade de uma implantação de expansão na qual várias instâncias do servidor de relatório oferecem suporte a um único banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-110">If all reports are processing slowly, consider a scale-out deployment where multiple report server instances support a single report server database.</span></span> <span data-ttu-id="8e0b6-111">Para obter os melhores resultados, use o software de balanceamento de carga para distribuir solicitações uniformemente pela implantação.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-111">For best results, use load balancing software to distribute requests evenly across the deployment.</span></span>  
  
-   <span data-ttu-id="8e0b6-112">Se um único relatório estiver sendo executado lentamente, ajuste as consultas ao conjunto de dados do relatório se o relatório tiver que ser executado sob demanda.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-112">If a single report is processing slowly, tune report dataset queries if the report must run on demand.</span></span> <span data-ttu-id="8e0b6-113">Também é possível usar conjuntos de dados compartilhados que você pode armazenar em cache enquanto estiver armazenando em cache o relatório ou executando o relatório como um instantâneo.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-113">You might also consider using shared datasets that you can cache, caching the report, or running the report as a snapshot.</span></span>  
  
-   <span data-ttu-id="8e0b6-114">Se o processamento de todos os relatórios for lento em um formato específico (por exemplo, ao renderizar em PDF), tente realizar entrega de compartilhamento de arquivos, adicionar mais memória ou escolher um formato diferente.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-114">If all reports process slowly in a specific format (for example, while rendering to PDF), consider file share delivery, adding more memory, or choosing a different format.</span></span>  
  
-   <span data-ttu-id="8e0b6-115">Para saber quanto demora o processamento de um relatório e obter outras métricas de uso, revise o log de execução do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-115">To find out how long it takes to process a report and other usage metrics, review the report server execution log.</span></span> <span data-ttu-id="8e0b6-116">Para obter mais informações, consulte [log de execução do servidor de relatório e a exibição ExecutionLog3](report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="8e0b6-116">For more information, see [Report Server Execution Log and the ExecutionLog3 View](report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
-   <span data-ttu-id="8e0b6-117">Para obter mais informações sobre como solucionar problemas de desempenho ajustando configurações de gerenciamento de memória, consulte [Configurar memória disponível para aplicativos do Servidor de Relatório](../report-server/configure-available-memory-for-report-server-applications.md).</span><span class="sxs-lookup"><span data-stu-id="8e0b6-117">For more information about how to mitigate performance issues by tuning memory management configuration settings, see [Configure Available Memory for Report Server Applications](../report-server/configure-available-memory-for-report-server-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e0b6-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8e0b6-118">In This Section</span></span>  
 [<span data-ttu-id="8e0b6-119">Monitorar o desempenho do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="8e0b6-119">Monitoring Report Server Performance</span></span>](monitoring-report-server-performance.md)  
 <span data-ttu-id="8e0b6-120">Descreve os objetos de desempenho que podem ser usados para controlar a carga de processamento no servidor.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-120">Describes the performance objects you can use to track the processing load on your server.</span></span>  
  
 [<span data-ttu-id="8e0b6-121">Definir propriedades de processamento de relatórios</span><span class="sxs-lookup"><span data-stu-id="8e0b6-121">Set Report Processing Properties</span></span>](set-report-processing-properties.md)  
 <span data-ttu-id="8e0b6-122">Descreve maneiras de configurar um relatório para ser executado sob demanda, a partir do cache ou em uma agenda como um instantâneo de relatório.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-122">Describes ways of configuring a report to run on demand, from cache, or on a schedule as a report snapshot.</span></span>  
  
 [<span data-ttu-id="8e0b6-123">Configurar a memória disponível para aplicativos do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="8e0b6-123">Configure Available Memory for Report Server Applications</span></span>](../report-server/configure-available-memory-for-report-server-applications.md)  
 <span data-ttu-id="8e0b6-124">Descreve como você pode substituir o comportamento padrão de gerenciamento de memória.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-124">Describes how you can override default memory management behavior.</span></span>  
  
 [<span data-ttu-id="8e0b6-125">Armazenando relatórios em cache &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e0b6-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
 <span data-ttu-id="8e0b6-126">Descreve o comportamento do cache de relatório em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-126">Describes report caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="8e0b6-127">Conjuntos de dados compartilhados em cache &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e0b6-127">Cache Shared Datasets &#40;SSRS&#41;</span></span>](cache-shared-datasets-ssrs.md)  
 <span data-ttu-id="8e0b6-128">Descreve o comportamento do cache de conjunto de dados compartilhados em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-128">Describes shared dataset caching behavior on a report server.</span></span>  
  
 [<span data-ttu-id="8e0b6-129">Processar relatórios grandes</span><span class="sxs-lookup"><span data-stu-id="8e0b6-129">Process Large Reports</span></span>](process-large-reports.md)  
 <span data-ttu-id="8e0b6-130">Fornece recomendações para configurar e distribuir um relatório grande.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-130">Provides recommendations on how to configure and distribute a large report.</span></span>  
  
 [<span data-ttu-id="8e0b6-131">Definindo valores de tempo limite para processamento de relatórios e conjuntos de dados compartilhados &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8e0b6-131">Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;</span></span>](setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md)  
 <span data-ttu-id="8e0b6-132">Explica como definir tempos limite no processamento de consultas e relatórios.</span><span class="sxs-lookup"><span data-stu-id="8e0b6-132">Explains how to set time outs on query and report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e0b6-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e0b6-133">See Also</span></span>  
 <span data-ttu-id="8e0b6-134">[Manage a Running Process](../subscriptions/manage-a-running-process.md) </span><span class="sxs-lookup"><span data-stu-id="8e0b6-134">[Manage a Running Process](../subscriptions/manage-a-running-process.md) </span></span>  
 [<span data-ttu-id="8e0b6-135">Verificar a execução de um relatório</span><span class="sxs-lookup"><span data-stu-id="8e0b6-135">Verifying a Report Run</span></span>](verifying-a-report-run.md)  
  
  
