---
title: Restaurar um banco de dados e associá-lo a um pool de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0d20a569-8a27-409c-bcab-0effefb48013
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0b518c93ca9d5e7157ceaa20d9548d7b6061017d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568567"
---
# <a name="restore-a-database-and-bind-it-to-a-resource-pool"></a><span data-ttu-id="ca385-102">Restaurar um banco de dados e associá-lo a um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="ca385-102">Restore a Database and Bind it to a Resource Pool</span></span>
  <span data-ttu-id="ca385-103">Embora você tenha memória suficiente para restaurar um banco de dados com tabelas com otimização memória, siga as práticas recomendadas e associe o banco de dados a um pool de recursos nomeado.</span><span class="sxs-lookup"><span data-stu-id="ca385-103">Even though you have enough memory to restore a database with memory-optimized tables, you want to follow best practices and bind the database to a named resource pool.</span></span> <span data-ttu-id="ca385-104">Como o banco de dados deve existir antes de você poder associá-lo ao pool, restaurar seu banco de dados é um processo de várias etapas.</span><span class="sxs-lookup"><span data-stu-id="ca385-104">Since the database must exist before you can bind it to the pool restoring your database is a multi-step process.</span></span> <span data-ttu-id="ca385-105">Este tópico orienta ao longo desse processo.</span><span class="sxs-lookup"><span data-stu-id="ca385-105">This topic walks you through that process.</span></span>  
  
##  <a name="restore-with-norecovery"></a><span data-ttu-id="ca385-106">Restaurar com NORECOVERY</span><span class="sxs-lookup"><span data-stu-id="ca385-106">Restore with NORECOVERY</span></span>  
 <span data-ttu-id="ca385-107">Quando você restaurar um banco de dados, NORECOVERY faz com que o banco de dados seja criado e a imagem de disco seja restaurada sem consumir memória.</span><span class="sxs-lookup"><span data-stu-id="ca385-107">When you restore a database, NORECOVERY causes the database to be created and the disk image restored without consuming memory.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   FROM DISK = 'C:\IMOLTP_test\IMOLTP_DB.bak'  
   WITH NORECOVERY  
```  
  
##  <a name="create-the-resource-pool"></a><span data-ttu-id="ca385-108">Criar o pool de recursos</span><span class="sxs-lookup"><span data-stu-id="ca385-108">Create the resource pool</span></span>  
 <span data-ttu-id="ca385-109">O [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir cria um pool de recursos chamado Pool_IMOLTP com 50% da memória disponível para seu uso.</span><span class="sxs-lookup"><span data-stu-id="ca385-109">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a resource pool named Pool_IMOLTP with 50% of memory available for its use.</span></span>  <span data-ttu-id="ca385-110">Depois que o pool é criado, o Administrador de Recursos é reconfigurado para incluir o Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="ca385-110">After the pool is created, the Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
CREATE RESOURCE POOL Pool_IMOLTP WITH (MAX_MEMORY_PERCENT = 50);  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
##  <a name="bind-the-database-and-resource-pool"></a><span data-ttu-id="ca385-111">Associar o banco de dados e o pool de recursos</span><span class="sxs-lookup"><span data-stu-id="ca385-111">Bind the database and resource pool</span></span>  
 <span data-ttu-id="ca385-112">Use a função do sistema `sp_xtp_bind_db_resource_pool` para associar o banco de dados ao pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="ca385-112">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="ca385-113">A função usa dois parâmetros: o nome do banco de dados seguido pelo nome do pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="ca385-113">The function takes two parameters: the database name followed by the resource pool name.</span></span>  
  
 <span data-ttu-id="ca385-114">O [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir define uma associação do banco de dados IMOLTP_DB ao pool de recursos Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="ca385-114">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="ca385-115">A associação não entra em vigor até que você conclua a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ca385-115">The binding does not become effective until you complete the next step.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
##  <a name="restore-with-recovery"></a><span data-ttu-id="ca385-116">Restaurar com RECOVERY</span><span class="sxs-lookup"><span data-stu-id="ca385-116">Restore with RECOVERY</span></span>  
 <span data-ttu-id="ca385-117">Quando você restaura o banco de dados com recuperação, o banco de dados é colocado online e todos os dados restaurados.</span><span class="sxs-lookup"><span data-stu-id="ca385-117">When you restore the database with recovery the database is brought online and all the data restored.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   WITH RECOVERY  
```  
  
##  <a name="monitor-the-resource-pool-performance"></a><span data-ttu-id="ca385-118">Monitorar o desempenho do pool de recursos</span><span class="sxs-lookup"><span data-stu-id="ca385-118">Monitor the resource pool performance</span></span>  
 <span data-ttu-id="ca385-119">Quando o banco de dados for associado ao pool de recursos nomeado e restaurado com recuperação, monitore o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o objeto Resource Pool Stats.</span><span class="sxs-lookup"><span data-stu-id="ca385-119">Once the database is bound to the named resource pool and restored with recovery, monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Resource Pool Stats Object.</span></span> <span data-ttu-id="ca385-120">Para obter mais informações, consulte [Objeto SQLServer:Resource Pool Stats](../performance-monitor/sql-server-resource-pool-stats-object.md).</span><span class="sxs-lookup"><span data-stu-id="ca385-120">For more information see [SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca385-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca385-121">See Also</span></span>  
 <span data-ttu-id="ca385-122">[Associar um banco de dados com tabelas com otimização de memória a um pool de recursos](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="ca385-122">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span></span>  
 <span data-ttu-id="ca385-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ca385-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="ca385-124">[SQL Server, objeto de estatísticas do pool de recursos](../performance-monitor/sql-server-resource-pool-stats-object.md) </span><span class="sxs-lookup"><span data-stu-id="ca385-124">[SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md) </span></span>  
 [<span data-ttu-id="ca385-125">sys.dm_resource_governor_resource_pools</span><span class="sxs-lookup"><span data-stu-id="ca385-125">sys.dm_resource_governor_resource_pools</span></span>](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql)  
  
  
