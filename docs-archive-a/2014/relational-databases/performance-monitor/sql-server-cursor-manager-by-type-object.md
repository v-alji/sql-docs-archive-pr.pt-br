---
title: SQL Server, objeto Gerenciador de cursor por tipo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Cursor Manager by Type object
- SQLServer:Cursor Manager by Type
ms.assetid: d67fbd8a-7554-4a16-96f1-d9ee857a95e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7bee15aa2917f7b8890e6c1d3f26cc0e210208a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570649"
---
# <a name="sql-server-cursor-manager-by-type-object"></a><span data-ttu-id="e9218-102">SQL Server, objeto Cursor Manager by Type</span><span class="sxs-lookup"><span data-stu-id="e9218-102">SQL Server, Cursor Manager by Type Object</span></span>
  <span data-ttu-id="e9218-103">O objeto **SQLServer:Gerenciador de Cursor por Tipo** fornece contadores para monitorar cursores, agrupados por tipo.</span><span class="sxs-lookup"><span data-stu-id="e9218-103">The **SQLServer:Cursor Manager by Type** object provides counters to monitor cursors, grouped by type.</span></span>  
  
 <span data-ttu-id="e9218-104">Esta tabela descreve os contadores do **Gerenciador de Cursor por Tipo** do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9218-104">This table describes the SQL Server **Cursor Manager by Type** counters.</span></span>  
  
|<span data-ttu-id="e9218-105">Contadores do Gerenciador de Cursor por Tipo</span><span class="sxs-lookup"><span data-stu-id="e9218-105">Cursor Manager by Type counters</span></span>|<span data-ttu-id="e9218-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="e9218-106">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="e9218-107">**Cursores ativos**</span><span class="sxs-lookup"><span data-stu-id="e9218-107">**Active cursors**</span></span>|<span data-ttu-id="e9218-108">Número de cursores ativos.</span><span class="sxs-lookup"><span data-stu-id="e9218-108">Number of active cursors.</span></span>|  
|<span data-ttu-id="e9218-109">**Taxa de Acertos do Cache**</span><span class="sxs-lookup"><span data-stu-id="e9218-109">**Cache Hit Ratio**</span></span>|<span data-ttu-id="e9218-110">Taxa entre acertos e pesquisas do cache.</span><span class="sxs-lookup"><span data-stu-id="e9218-110">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="e9218-111">**Contagens de Cursor em Cache**</span><span class="sxs-lookup"><span data-stu-id="e9218-111">**Cached Cursor Counts**</span></span>|<span data-ttu-id="e9218-112">Número de cursores de um determinado tipo no cache.</span><span class="sxs-lookup"><span data-stu-id="e9218-112">Number of cursors of a given type in the cache.</span></span>|  
|<span data-ttu-id="e9218-113">**Contagem de Uso de Cache de Cursor/s**</span><span class="sxs-lookup"><span data-stu-id="e9218-113">**Cursor Cache Use Count/sec**</span></span>|<span data-ttu-id="e9218-114">Número de vezes em que cada tipo de cursor em cache foi usado.</span><span class="sxs-lookup"><span data-stu-id="e9218-114">Times each type of cached cursor has been used.</span></span>|  
|<span data-ttu-id="e9218-115">**Uso de memória do cursor**</span><span class="sxs-lookup"><span data-stu-id="e9218-115">**Cursor memory usage**</span></span>|<span data-ttu-id="e9218-116">Quantidade de memória consumida por cursores, em quilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="e9218-116">Amount of memory consumed by cursors in kilobytes (KB).</span></span>|  
|<span data-ttu-id="e9218-117">**Solicitações de Cursor/s**</span><span class="sxs-lookup"><span data-stu-id="e9218-117">**Cursor Requests/sec**</span></span>|<span data-ttu-id="e9218-118">Número de solicitações de cursor SQL recebidas por servidor.</span><span class="sxs-lookup"><span data-stu-id="e9218-118">Number of SQL cursor requests received by server.</span></span>|  
|<span data-ttu-id="e9218-119">**Uso de tabelas de trabalho do cursor**</span><span class="sxs-lookup"><span data-stu-id="e9218-119">**Cursor worktable usage**</span></span>|<span data-ttu-id="e9218-120">Número de tabelas de trabalho usadas por cursores.</span><span class="sxs-lookup"><span data-stu-id="e9218-120">Number of worktables used by cursors.</span></span>|  
|<span data-ttu-id="e9218-121">**Número de planos de cursor ativos**</span><span class="sxs-lookup"><span data-stu-id="e9218-121">**Number of active cursor plans**</span></span>|<span data-ttu-id="e9218-122">Número de planos de cursor.</span><span class="sxs-lookup"><span data-stu-id="e9218-122">Number of cursor plans.</span></span>|  
  
 <span data-ttu-id="e9218-123">Cada contador no objeto contém as seguintes instâncias:</span><span class="sxs-lookup"><span data-stu-id="e9218-123">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="e9218-124">Instância do Gerenciador de Cursor</span><span class="sxs-lookup"><span data-stu-id="e9218-124">Cursor Manager instance</span></span>|<span data-ttu-id="e9218-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="e9218-125">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="e9218-126">**_Total**</span><span class="sxs-lookup"><span data-stu-id="e9218-126">**_Total**</span></span>|<span data-ttu-id="e9218-127">Informações de todos os cursores.</span><span class="sxs-lookup"><span data-stu-id="e9218-127">Information for all cursors.</span></span>|  
|<span data-ttu-id="e9218-128">**Cursor API**</span><span class="sxs-lookup"><span data-stu-id="e9218-128">**API Cursor**</span></span>|<span data-ttu-id="e9218-129">Apenas informações de cursor de API.</span><span class="sxs-lookup"><span data-stu-id="e9218-129">Only the API cursor information.</span></span>|  
|<span data-ttu-id="e9218-130">**Cursor Global de TSQL**</span><span class="sxs-lookup"><span data-stu-id="e9218-130">**TSQL Global Cursor**</span></span>|<span data-ttu-id="e9218-131">Apenas informações de cursor global de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9218-131">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] global cursor information.</span></span>|  
|<span data-ttu-id="e9218-132">**Cursor Local de TSQL**</span><span class="sxs-lookup"><span data-stu-id="e9218-132">**TSQL Local Cursor**</span></span>|<span data-ttu-id="e9218-133">Apenas informações do cursor local de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9218-133">Only the [!INCLUDE[tsql](../../includes/tsql-md.md)] local cursor information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9218-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9218-134">See Also</span></span>  
 [<span data-ttu-id="e9218-135">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="e9218-135">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
