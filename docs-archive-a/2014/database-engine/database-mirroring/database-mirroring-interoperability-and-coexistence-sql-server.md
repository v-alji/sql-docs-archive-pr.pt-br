---
title: 'Espelhamento de Banco de Dados: interoperabilidade e coexistência (SQL Server) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- high availability [SQL Server], interoperability and coexistence
- Database Engine [SQL Server], high availability
ms.assetid: 89fef397-e0cf-4e08-b598-25b8d4170523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 057392842974c3342fc57d0ec113f8b1bb58b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572692"
---
# <a name="database-mirroring-interoperability-and-coexistence-sql-server"></a><span data-ttu-id="c3a1b-102">Espelhamento de banco de dados: Interoperabilidade e coexistência (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c3a1b-102">Database Mirroring: Interoperability and Coexistence (SQL Server)</span></span>
  <span data-ttu-id="c3a1b-103">O espelhamento de banco de dados pode ser usado com os seguintes recursos ou componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c3a1b-103">Database mirroring can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="c3a1b-104">Instâncias de cluster de failover AlwaysOn (clustering de failover do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c3a1b-104">AlwaysOn Failover Cluster Instances (SQL Server Failover Clustering)</span></span>](database-mirroring-and-sql-server-failover-cluster-instances.md)  
  
-   [<span data-ttu-id="c3a1b-105">Change data capture (e controle de alterações)</span><span class="sxs-lookup"><span data-stu-id="c3a1b-105">Change data capture (and change tracking)</span></span>](../../relational-databases/track-changes/change-data-capture-and-other-sql-server-features.md)  
  
-   [<span data-ttu-id="c3a1b-106">Instantâneos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c3a1b-106">Database snapshots</span></span>](../../relational-databases/databases/database-snapshots-sql-server.md)  
  
-   [<span data-ttu-id="c3a1b-107">Catálogos de texto completo</span><span class="sxs-lookup"><span data-stu-id="c3a1b-107">Full-text catalogs</span></span>](database-mirroring-and-full-text-catalogs-sql-server.md)  
  
-   [<span data-ttu-id="c3a1b-108">Envio de logs</span><span class="sxs-lookup"><span data-stu-id="c3a1b-108">Log shipping</span></span>](database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="c3a1b-109">Replicação</span><span class="sxs-lookup"><span data-stu-id="c3a1b-109">Replication</span></span>](database-mirroring-and-replication-sql-server.md)  
  
 <span data-ttu-id="c3a1b-110">O espelhamento de banco de dados não interopera com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c3a1b-110">Database mirroring does not interoperate with the following:</span></span>  
  
-   <span data-ttu-id="c3a1b-111">Transações envolvendo todos os bancos de dados/transações distribuídas</span><span class="sxs-lookup"><span data-stu-id="c3a1b-111">Cross-database transactions/distributed transactions</span></span>  
  
     <span data-ttu-id="c3a1b-112">Para obter informações sobre por que não há suporte para essas transações, consulte [Transações envolvendo todos os bancos de dados sem suporte para espelhamento de banco de dados ou Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="c3a1b-112">For information about why such transactions are not supported, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
-   [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c3a1b-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3a1b-113">See Also</span></span>  
 [<span data-ttu-id="c3a1b-114">Espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3a1b-114">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
