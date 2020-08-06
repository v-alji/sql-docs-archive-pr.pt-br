---
title: Instantâneos do banco de dados com Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 7432da1c-ce2f-4cd9-af41-54c97744166b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1e4307653b5b8150d71019a373ee073d15123f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683685"
---
# <a name="database-snapshots-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="c24c4-102">Instantâneos do banco de dados com grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c24c4-102">Database Snapshots with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="c24c4-103">Você pode criar um instantâneo de banco de dados em um banco de dados primário ou secundário em um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c24c4-103">You can create a database snapshot on an primary or secondary database in an availability group.</span></span> <span data-ttu-id="c24c4-104">A função de réplica deve ser PRIMARY ou SECONDARY, em vez de estar no estado RESOLVING.</span><span class="sxs-lookup"><span data-stu-id="c24c4-104">The replica role must be either PRIMARY or SECONDARY, not in the RESOLVING state.</span></span>  
  
 <span data-ttu-id="c24c4-105">É recomendável que o estado de sincronização de banco de dados seja SYNCHRONIZING ou SYNCHRONIZED quando você criar um instantâneo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c24c4-105">We recommend that the database synchronization state be SYNCHRONIZING or SYNCHRONIZED when you create a database snapshot.</span></span> <span data-ttu-id="c24c4-106">No entanto, os instantâneos de banco de dados poderão ser criados quando o estado de sincronização de banco de dados for NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="c24c4-106">However, database snapshots can be created when the database synchronization state is NOT SYNCHRONIZING.</span></span>  
  
 <span data-ttu-id="c24c4-107">Um instantâneo do banco de dados em uma réplica secundária deverá continuar funcionando se a réplica for desconectada (DISCONNECTED) da réplica primária.</span><span class="sxs-lookup"><span data-stu-id="c24c4-107">A database snapshot on a secondary replica should continue to work if the replica is DISCONNECTED from the primary replica.</span></span>  
  
 <span data-ttu-id="c24c4-108">Algumas condições de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] fazem o banco de dados de origem e seus instantâneos do banco de dados serem reiniciados, desconectando os usuários temporariamente.</span><span class="sxs-lookup"><span data-stu-id="c24c4-108">Some [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] conditions cause both the source database and its database snapshots to be restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="c24c4-109">Estas condições são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="c24c4-109">These conditions are as follows:</span></span>  
  
-   <span data-ttu-id="c24c4-110">A réplica primária altera funções, ou porque a réplica primária atual é desconectada e fica online novamente na mesma instância de servidor ou porque o grupo de disponibilidade realiza o failover.</span><span class="sxs-lookup"><span data-stu-id="c24c4-110">The primary replica changes roles, whether because the current primary replica goes off line and comes back online on the same server instance or because the availability group fails over.</span></span>  
  
-   <span data-ttu-id="c24c4-111">O banco de dados entra na função secundária.</span><span class="sxs-lookup"><span data-stu-id="c24c4-111">The database enters the secondary role.</span></span>  
  
 <span data-ttu-id="c24c4-112">Se a réplica de disponibilidade que hospeda os instantâneos do banco de dados realizar failover, os instantâneos do banco de dados permanecerão na instância de servidor onde foram criados.</span><span class="sxs-lookup"><span data-stu-id="c24c4-112">If the availability replica that hosts database snapshots is failed over, the database snapshots remain on the server instance where they were created.</span></span> <span data-ttu-id="c24c4-113">Os usuários podem continuar usando os instantâneos depois do failover. Se o desempenho for uma preocupação em seu ambiente, nós recomendamos que você crie instantâneos do banco de dados somente em bancos de dados secundários que estão hospedados por uma réplica secundária que está configurada para modo de failover manual.</span><span class="sxs-lookup"><span data-stu-id="c24c4-113">Users can continue to use the snapshots after the failover.If performance is a concern in your environment, we recommend that you create database snapshots only on secondary databases that are hosted by a secondary replica that is configured for manual failover mode.</span></span>  <span data-ttu-id="c24c4-114">Se você já realizou failover manual no grupo de disponibilidade para esta réplica secundária, poderá criar um novo conjunto de instantâneos do banco de dados em outra réplica secundária, redirecionar clientes para os novos instantâneos do banco de dados e remover todos os instantâneos dos bancos de dados agora primários.</span><span class="sxs-lookup"><span data-stu-id="c24c4-114">If you ever manually fail over the availability group to this secondary replica, you can create a new set of database snapshots on another secondary replica, redirect clients to the new database snapshots, and drop all of the database snapshots from the now primary databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24c4-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c24c4-115">See Also</span></span>  
 <span data-ttu-id="c24c4-116">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c24c4-116">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="c24c4-117">Instantâneos de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c24c4-117">Database Snapshots &#40;SQL Server&#41;</span></span>](../../../relational-databases/databases/database-snapshots-sql-server.md)  
  
  
