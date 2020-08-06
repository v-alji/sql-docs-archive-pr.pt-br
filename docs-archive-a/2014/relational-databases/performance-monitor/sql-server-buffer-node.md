---
title: SQL Server:Buffer Node | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Buffer Node
- Buffer Node object
ms.assetid: fd3f9f0f-7c38-4cfd-a0c5-ee93dd52d9a5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14659e4c1191e2260bccdbcd612f510770913629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581762"
---
# <a name="sql-serverbuffer-node"></a><span data-ttu-id="a94e1-102">SQL Server:Buffer Node</span><span class="sxs-lookup"><span data-stu-id="a94e1-102">SQL Server:Buffer Node</span></span>
  <span data-ttu-id="a94e1-103">O objeto **Buffer Node** fornece contadores que complementam aqueles fornecidos pelo objeto **Buffer Manager** .</span><span class="sxs-lookup"><span data-stu-id="a94e1-103">The **Buffer Node** object provides counters that complement counters provided by the **Buffer Manager** object.</span></span> <span data-ttu-id="a94e1-104">Ele lhe permite monitorar a distribuição de páginas de pool de buffer do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cada nó NUMA (non-uniform memory access).</span><span class="sxs-lookup"><span data-stu-id="a94e1-104">It allows you to monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] buffer pool page distribution for each non-uniform memory access (NUMA) node.</span></span> <span data-ttu-id="a94e1-105">Há uma instância do objeto **Buffer Node** para cada nó NUMA em uso.</span><span class="sxs-lookup"><span data-stu-id="a94e1-105">There is an instance of the **Buffer Node** object for each NUMA node in use.</span></span> <span data-ttu-id="a94e1-106">Em arquiteturas diferentes de NUMA, haverá uma única instância do objeto **Buffer Node** .</span><span class="sxs-lookup"><span data-stu-id="a94e1-106">On non-NUMA architecture, there will be a single instance of the **Buffer Node** object.</span></span>  
  
## <a name="buffer-node-performance-objects"></a><span data-ttu-id="a94e1-107">Objetos de desempenho do Buffer Node</span><span class="sxs-lookup"><span data-stu-id="a94e1-107">Buffer Node Performance Objects</span></span>  
 <span data-ttu-id="a94e1-108">Esta tabela descreve os objetos de desempenho **Buffer Node** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a94e1-108">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Buffer Node** performance objects.</span></span>  
  
|<span data-ttu-id="a94e1-109">Contadores de Buffer Node do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a94e1-109">SQL Server Buffer Node counters</span></span>|<span data-ttu-id="a94e1-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="a94e1-110">Description</span></span>|  
|-------------------------------------|-----------------|  
|<span data-ttu-id="a94e1-111">**Páginas do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a94e1-111">**Database pages**</span></span>|<span data-ttu-id="a94e1-112">Indica o número de páginas no pool de buffers do nó com conteúdo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a94e1-112">Indicates the number of pages in the buffer pool on this node with database content.</span></span>|  
|<span data-ttu-id="a94e1-113">**Expectativa de vida da página**</span><span class="sxs-lookup"><span data-stu-id="a94e1-113">**Page life expectancy**</span></span>|<span data-ttu-id="a94e1-114">Indica o número mínimo de segundos que uma página ficará no pool de buffers do nó sem referências.</span><span class="sxs-lookup"><span data-stu-id="a94e1-114">Indicates the minimum number of seconds a page will stay in the buffer pool on this node without references.</span></span>|  
|<span data-ttu-id="a94e1-115">**Pesquisas de página de nó local/s**</span><span class="sxs-lookup"><span data-stu-id="a94e1-115">**Local Node page lookups/sec**</span></span>|<span data-ttu-id="a94e1-116">Indica o número de solicitações de pesquisa desse nó que foram atendidas nesse nó.</span><span class="sxs-lookup"><span data-stu-id="a94e1-116">Indicates the number of lookup requests from this node which were satisfied from this node.</span></span>|  
|<span data-ttu-id="a94e1-117">**Pesquisas de página de nó remoto/s**</span><span class="sxs-lookup"><span data-stu-id="a94e1-117">**Remote Note page lookups/sec**</span></span>|<span data-ttu-id="a94e1-118">Indica o número de solicitações de pesquisa desse nó que foram atendidas em outros nós.</span><span class="sxs-lookup"><span data-stu-id="a94e1-118">Indicates the number of lookup requests from this node which were satisfied from other nodes.</span></span>|  
  
 <span data-ttu-id="a94e1-119">Se o SQL Server estiver em execução em um hardware diferente de NUMA, os contadores dos objetos **Buffer Node** e **Buffer Manager** deverão ser correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a94e1-119">If SQL Server is running on non-NUMA hardware, the counters of **Buffer Node** and **Buffer Manager** objects should match.</span></span>  
  
 <span data-ttu-id="a94e1-120">No hardware NUMA, as somas dos respectivos contadores de todos os objetos **Buffer Node** devem corresponder aos seus equivalentes no **Buffer Manager**.</span><span class="sxs-lookup"><span data-stu-id="a94e1-120">On NUMA hardware, sums of respective counters of all **Buffer Nodes** should match their counterparts of **Buffer Manager**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a94e1-121">Os valores e somas dos contadores podem não corresponder exatamente, devido à natureza dinâmica dos contadores e à exatidão da amostragem.</span><span class="sxs-lookup"><span data-stu-id="a94e1-121">The counter values and sums may not match precisely due to the dynamic nature of the counters and the sampling accuracy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94e1-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a94e1-122">See Also</span></span>  
 <span data-ttu-id="a94e1-123">[SQL Server, objeto Buffer Manager](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="a94e1-123">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 <span data-ttu-id="a94e1-124">[Opções Server Memory de configuração do servidor](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="a94e1-124">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="a94e1-125">[Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="a94e1-125">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 [<span data-ttu-id="a94e1-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a94e1-126">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
