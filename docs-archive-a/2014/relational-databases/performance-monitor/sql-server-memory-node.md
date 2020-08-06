---
title: SQL Server, nó de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 55b28ba9-b6d5-4ea9-8103-db8a72f42982
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5bbc3f581ea9ececeb7d55a614ef27c3c72de7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582988"
---
# <a name="sql-server-memory-node"></a><span data-ttu-id="7c03c-102">SQL Server, Nó de Memória</span><span class="sxs-lookup"><span data-stu-id="7c03c-102">SQL Server, Memory Node</span></span>
  <span data-ttu-id="7c03c-103">O objeto **Memory Node** do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece contadores para monitorar o uso de memória de servidor em nós NUMA.</span><span class="sxs-lookup"><span data-stu-id="7c03c-103">The **Memory Node** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor server memory usage on NUMA nodes.</span></span>  
  
## <a name="memory-node-counters"></a><span data-ttu-id="7c03c-104">Contadores de nós de memória</span><span class="sxs-lookup"><span data-stu-id="7c03c-104">Memory Node Counters</span></span>  
 <span data-ttu-id="7c03c-105">Essa tabela descreve os contadores **Memória de Nó** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c03c-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Memory Node** counters.</span></span>  
  
|<span data-ttu-id="7c03c-106">Contadores do Gerenciador de Memória do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c03c-106">SQL Server Memory Manager counters</span></span>|<span data-ttu-id="7c03c-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="7c03c-107">Description</span></span>|  
|----------------------------------------|-----------------|  
|<span data-ttu-id="7c03c-108">**Memória do Nó do Banco de Dados (KB)**</span><span class="sxs-lookup"><span data-stu-id="7c03c-108">**Database Node Memory (KB)**</span></span>|<span data-ttu-id="7c03c-109">Especifica a quantidade de memória que o servidor está usando atualmente nesse nó para páginas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7c03c-109">Specifies the amount of memory the server is currently using on this node for database pages.</span></span>|  
|<span data-ttu-id="7c03c-110">**Memória do Nó Livre (KB)**</span><span class="sxs-lookup"><span data-stu-id="7c03c-110">**Free Node Memory (KB)**</span></span>|<span data-ttu-id="7c03c-111">Especifica a quantidade de memória que o servidor não está usando atualmente nesse nó.</span><span class="sxs-lookup"><span data-stu-id="7c03c-111">Specifies the amount of memory the server is not using on this node.</span></span>|  
|<span data-ttu-id="7c03c-112">**Memória do Nó do Estrangeiro (KB)**</span><span class="sxs-lookup"><span data-stu-id="7c03c-112">**Foreign Node Memory (KB)**</span></span>|<span data-ttu-id="7c03c-113">Especifica a quantidade de memória local não NUMA nesse nó.</span><span class="sxs-lookup"><span data-stu-id="7c03c-113">Specifies the amount of non NUMA-local memory on this node.</span></span>|  
|<span data-ttu-id="7c03c-114">**Memória do Nó Roubada (KB)**</span><span class="sxs-lookup"><span data-stu-id="7c03c-114">**Stolen Memory Node (KB)**</span></span>|<span data-ttu-id="7c03c-115">Especifica a quantidade de memória que o servidor está usando atualmente nesse nó para outras finalidades, sem ser páginas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7c03c-115">Specifies the amount of memory the server is using on this node for purposes other than database pages.</span></span>|  
|<span data-ttu-id="7c03c-116">**Memória do Nó de Destino**</span><span class="sxs-lookup"><span data-stu-id="7c03c-116">**Target Node Memory**</span></span>|<span data-ttu-id="7c03c-117">Especifica a quantidade ideal de memória para esse nó.</span><span class="sxs-lookup"><span data-stu-id="7c03c-117">Specifies the ideal amount of memory for this node.</span></span>|  
|<span data-ttu-id="7c03c-118">**Memória do Nó Total**</span><span class="sxs-lookup"><span data-stu-id="7c03c-118">**Total Node Memory**</span></span>|<span data-ttu-id="7c03c-119">Indica a quantidade total de memória que o servidor comprometeu nesse nó.</span><span class="sxs-lookup"><span data-stu-id="7c03c-119">Indicates the total amount of memory the server has committed on this node.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c03c-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7c03c-120">See Also</span></span>  
 <span data-ttu-id="7c03c-121">[Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="7c03c-121">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="7c03c-122">[SQL Server, objeto Buffer Manager](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="7c03c-122">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="7c03c-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7c03c-123">sys.dm_os_performance_counters &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  
