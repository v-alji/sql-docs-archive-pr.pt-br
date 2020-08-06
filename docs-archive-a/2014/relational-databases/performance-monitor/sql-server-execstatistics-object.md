---
title: SQL Server, objeto ExecStatistics | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:ExecStatistics
- ExecStatistics object
ms.assetid: 4f8557a8-345f-4622-a8a5-763a0388ad94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d1a50c97add4708a58b9edc45fd49982b97a51ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570639"
---
# <a name="sql-server-execstatistics-object"></a><span data-ttu-id="d7719-102">SQL Server, objeto ExecStatistics</span><span class="sxs-lookup"><span data-stu-id="d7719-102">SQL Server, ExecStatistics Object</span></span>
  <span data-ttu-id="d7719-103">O objeto **SQLServer:ExecStatistics** do Microsoft SQL Server oferece contadores para o monitoramento de diversas execuções.</span><span class="sxs-lookup"><span data-stu-id="d7719-103">The **SQLServer:ExecStatistics** object in Microsoft SQL Server provides counters to monitor various executions.</span></span>  
  
 <span data-ttu-id="d7719-104">Esta tabela descreve os contadores **Exec Statistics** do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d7719-104">This table describes the SQL Server **Exec Statistics** counters.</span></span>  
  
|<span data-ttu-id="d7719-105">Contadores Exec Statistics do SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7719-105">SQL Server Exec Statistics counters</span></span>|<span data-ttu-id="d7719-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7719-106">Description</span></span>|  
|-----------------------------------------|-----------------|  
|<span data-ttu-id="d7719-107">**Consulta Distribuída**</span><span class="sxs-lookup"><span data-stu-id="d7719-107">**Distributed Query**</span></span>|<span data-ttu-id="d7719-108">Estatísticas referentes à execução de consultas distribuídas.</span><span class="sxs-lookup"><span data-stu-id="d7719-108">Statistics relevant to execution of distributed queries.</span></span>|  
|<span data-ttu-id="d7719-109">**Chamadas DTC**</span><span class="sxs-lookup"><span data-stu-id="d7719-109">**DTC calls**</span></span>|<span data-ttu-id="d7719-110">Estatísticas referentes à execução de chamadas DTC.</span><span class="sxs-lookup"><span data-stu-id="d7719-110">Statistics relevant to execution of DTC calls.</span></span>|  
|<span data-ttu-id="d7719-111">**Procedimentos Estendidos**</span><span class="sxs-lookup"><span data-stu-id="d7719-111">**Extended Procedures**</span></span>|<span data-ttu-id="d7719-112">Estatísticas referentes à execução de procedimentos estendidos.</span><span class="sxs-lookup"><span data-stu-id="d7719-112">Statistics relevant to execution of extended procedures.</span></span>|  
|<span data-ttu-id="d7719-113">**Chamadas OLEDB**</span><span class="sxs-lookup"><span data-stu-id="d7719-113">**OLEDB calls**</span></span>|<span data-ttu-id="d7719-114">Estatísticas referentes à execução de chamadas OLEDB.</span><span class="sxs-lookup"><span data-stu-id="d7719-114">Statistics relevant to execution of OLEDB calls.</span></span>|  
  
 <span data-ttu-id="d7719-115">Cada contador no objeto contém as seguintes instâncias:</span><span class="sxs-lookup"><span data-stu-id="d7719-115">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="d7719-116">Item</span><span class="sxs-lookup"><span data-stu-id="d7719-116">Item</span></span>|<span data-ttu-id="d7719-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7719-117">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d7719-118">**Tempo médio de execução (ms)**</span><span class="sxs-lookup"><span data-stu-id="d7719-118">**Average execution time (ms)**</span></span>|<span data-ttu-id="d7719-119">Tempo médio de execução do tipo de execução selecionado.</span><span class="sxs-lookup"><span data-stu-id="d7719-119">Average execution time of the selected type of execution.</span></span>|  
|<span data-ttu-id="d7719-120">**Tempo de execução cumulativo (ms) por segundo**</span><span class="sxs-lookup"><span data-stu-id="d7719-120">**Cumulative execution time (ms) per second**</span></span>|<span data-ttu-id="d7719-121">Tempo de execução agregado, por segundo, do tipo de execução selecionado.</span><span class="sxs-lookup"><span data-stu-id="d7719-121">Aggregated execution time per second, of the selected type of execution.</span></span>|  
|<span data-ttu-id="d7719-122">**Execuções em andamento**</span><span class="sxs-lookup"><span data-stu-id="d7719-122">**Execs in progress**</span></span>|<span data-ttu-id="d7719-123">Número de execuções em andamento do tipo de execução selecionado.</span><span class="sxs-lookup"><span data-stu-id="d7719-123">Number of execs in progress of the selected type of execution.</span></span>|  
|<span data-ttu-id="d7719-124">**Execuções iniciadas por segundo**</span><span class="sxs-lookup"><span data-stu-id="d7719-124">**Exec started per second**</span></span>|<span data-ttu-id="d7719-125">Número de execuções iniciadas por segundo, do tipo de execução selecionado.</span><span class="sxs-lookup"><span data-stu-id="d7719-125">Number of exes started per second of the selected type of execution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7719-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7719-126">See Also</span></span>  
 [<span data-ttu-id="d7719-127">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="d7719-127">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
