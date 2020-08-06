---
title: Monitorar e solucionar problemas de uso de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 7a458b9c-3423-4e24-823d-99573544c877
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5805ed06ad78040dbdf6c8557e5f548ad57f618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685685"
---
# <a name="monitor-and-troubleshoot-memory-usage"></a><span data-ttu-id="b303f-102">Monitorar e solucionar problemas de uso da memória</span><span class="sxs-lookup"><span data-stu-id="b303f-102">Monitor and Troubleshoot Memory Usage</span></span>
  [!INCLUDE[hek_1](../../includes/hek-1-md.md)] <span data-ttu-id="b303f-103">consome memória em padrões diferentes comparado a tabelas baseadas em disco.</span><span class="sxs-lookup"><span data-stu-id="b303f-103">consumes memory in different patterns than disk-based tables.</span></span> <span data-ttu-id="b303f-104">Você pode monitorar a quantidade de memória alocada e usada pelas tabelas e índices com otimização de memória em seu banco de dados, usando as DMVs ou os contadores de desempenho fornecidos para a memória e o subsistema de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="b303f-104">You can monitor the amount of memory allocated and used by memory-optimized tables and indexes in your database using the DMVs or performance counters provided for memory and the garbage collection subsystem.</span></span>  <span data-ttu-id="b303f-105">Isso oferece visibilidade em nível de sistema e banco de dados, e permite que você evite problemas devido ao esgotamento de memória.</span><span class="sxs-lookup"><span data-stu-id="b303f-105">This gives you visibility at both the system and database level and lets you prevent problems due to memory exhaustion.</span></span>

 <span data-ttu-id="b303f-106">Este tópico abrange o monitoramento do uso de memória de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b303f-106">This topic covers monitoring your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] memory usage.</span></span>


##  <a name="create-a-sample-database-with-memory-optimized-tables"></a><a name="bkmk_CreateDB"></a> <span data-ttu-id="b303f-107">Criar um banco de dados de exemplo com tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="b303f-107">Create a sample database with memory-optimized tables</span></span>
 <span data-ttu-id="b303f-108">Você poderá ignorar esta seção se já tiver um banco de dados com tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="b303f-108">You can skip this section if you already have a database with memory-optimized tables.</span></span>

 <span data-ttu-id="b303f-109">As etapas a seguir criam um banco de dados com três tabelas com otimização de memória que você pode usar no restante deste tópico.</span><span class="sxs-lookup"><span data-stu-id="b303f-109">The following steps create a database with three memory-optimized tables that you can use in the remainder of this topic.</span></span> <span data-ttu-id="b303f-110">No exemplo, mapeamos o banco de dados para um pool de recursos a fim de controlar a quantidade de memória que pode ser usada por tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="b303f-110">In the example, we mapped the database to a resource pool so that we can control how much memory can be taken by memory-optimized tables.</span></span>

1.  <span data-ttu-id="b303f-111">Inicie o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b303f-111">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>

2.  <span data-ttu-id="b303f-112">Clicar em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b303f-112">Click **New Query**.</span></span>

3.  <span data-ttu-id="b303f-113">Colar este código na nova janela de consulta e executar cada seção.</span><span class="sxs-lookup"><span data-stu-id="b303f-113">Paste this code into the new query window and execute each section.</span></span>

    ```
    -- create a database to be used
    CREATE DATABASE IMOLTP_DB
    GO

    ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_xtp_fg CONTAINS MEMORY_OPTIMIZED_DATA
    ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_xtp' , FILENAME = 'C:\Data\IMOLTP_DB_xtp') TO FILEGROUP IMOLTP_DB_xtp_fg;
    GO

    USE IMOLTP_DB
    GO

    -- create the resoure pool
    CREATE RESOURCE POOL PoolIMOLTP WITH (MAX_MEMORY_PERCENT = 60);
    ALTER RESOURCE GOVERNOR RECONFIGURE;
    GO

    -- bind the database to a resource pool
    EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'PoolIMOLTP'

    -- you can query the binding using the catalog view as described here
    SELECT d.database_id
         , d.name
         , d.resource_pool_id
    FROM sys.databases d
    GO

    -- take database offline/online to finalize the binding to the resource pool
    USE master
    GO

    ALTER DATABASE IMOLTP_DB SET OFFLINE
    GO
    ALTER DATABASE IMOLTP_DB SET ONLINE
    GO

    -- create some tables
    USE IMOLTP_DB
    GO

    -- create table t1
    CREATE TABLE dbo.t1 (
           c1 int NOT NULL CONSTRAINT [pk_t1_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- load t1 150K rows
    DECLARE @i int = 0
    BEGIN TRAN
    WHILE (@i <= 150000)
       BEGIN
          INSERT t1 VALUES (@i, 'a', replicate ('b', 8000))
          SET @i += 1;
       END
    Commit
    GO

    -- Create another table, t2
    CREATE TABLE dbo.t2 (
           c1 int NOT NULL CONSTRAINT [pk_t2_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- Create another table, t3 
    CREATE TABLE dbo.t3 (
           c1 int NOT NULL CONSTRAINT [pk_t3_c1] PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 1000000)
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO
    ```

##  <a name="monitoring-memory-usage"></a><span data-ttu-id="b303f-114">Monitorando o uso da memória</span><span class="sxs-lookup"><span data-stu-id="b303f-114">Monitoring Memory Usage</span></span>

###  <a name="using-ssmanstudiofull"></a><span data-ttu-id="b303f-115">Usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b303f-115">Using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>
 [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="b303f-116">é fornecido com relatórios internos padrão para monitorar a memória consumida por tabelas na memória.</span><span class="sxs-lookup"><span data-stu-id="b303f-116">ships with built-in standard reports to monitor the memory consumed by in-memory tables.</span></span> <span data-ttu-id="b303f-117">Você pode acessar esses relatórios usando o Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="b303f-117">You can access these reports using Object Explorer.</span></span> <span data-ttu-id="b303f-118">Você também pode usar o Pesquisador de Objetos para monitorar a memória consumida por tabelas individuais com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="b303f-118">You can also use the object explorer to monitor memory consumed by individual memory-optimized tables.</span></span>

#### <a name="consumption-at-the-database-level"></a><span data-ttu-id="b303f-119">Consumo em nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b303f-119">Consumption at the database level</span></span>
 <span data-ttu-id="b303f-120">Você pode monitorar o uso da memória em nível de banco de dados da forma a seguir.</span><span class="sxs-lookup"><span data-stu-id="b303f-120">You can monitor memory use at the database level as follows.</span></span>

1.  <span data-ttu-id="b303f-121">Inicie o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] e conecte-se a um servidor.</span><span class="sxs-lookup"><span data-stu-id="b303f-121">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and connect to a server.</span></span>

2.  <span data-ttu-id="b303f-122">No Pesquisador de Objetos, clique com o botão direito do mouse no banco de dados sobre o qual você deseja obter relatórios.</span><span class="sxs-lookup"><span data-stu-id="b303f-122">In Object Explorer, right-click the database you want reports on.</span></span>

3.  <span data-ttu-id="b303f-123">No menu de contexto, selecione **Relatórios** -> **Relatórios Padrão** -> **Uso de Memória por Objetos com Otimização de Memória**</span><span class="sxs-lookup"><span data-stu-id="b303f-123">In the context menu select, **Reports** -> **Standard Reports** -> **Memory Usage By Memory Optimized Objects**</span></span>

 <span data-ttu-id="b303f-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="b303f-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span></span>

 <span data-ttu-id="b303f-125">Esse relatório mostra o consumo de memória pelo banco de dados criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b303f-125">This report shows memory consumption by the database we created above.</span></span>

 <span data-ttu-id="b303f-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="b303f-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span></span>

###  <a name="using-dmvs"></a><span data-ttu-id="b303f-127">Usando DMVs</span><span class="sxs-lookup"><span data-stu-id="b303f-127">Using DMVs</span></span>
 <span data-ttu-id="b303f-128">Há várias DMVs disponíveis para monitorar a memória consumida por tabelas com otimização de memória, índices, objetos de sistema e estruturas de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b303f-128">There are a number of DMVs available to monitor memory consumed by memory-optimized tables, indexes, system objects, and by run-time structures.</span></span>

#### <a name="memory-consumption-by-memory-optimized-tables-and-indexes"></a><span data-ttu-id="b303f-129">Consumo de memória por tabelas com otimização de memória e índices</span><span class="sxs-lookup"><span data-stu-id="b303f-129">Memory consumption by memory-optimized tables and indexes</span></span>
 <span data-ttu-id="b303f-130">Você pode localizar o consumo de memória para todas as tabelas de usuário, índices e objetos do sistema consultando `sys.dm_db_xtp_table_memory_stats` , conforme mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="b303f-130">You can find memory consumption for all user tables, indexes, and system objects by querying `sys.dm_db_xtp_table_memory_stats` as shown here.</span></span>

```sql
SELECT object_name(object_id) AS Name
     , *
   FROM sys.dm_db_xtp_table_memory_stats
```

 <span data-ttu-id="b303f-131">**Saída de exemplo**</span><span class="sxs-lookup"><span data-stu-id="b303f-131">**Sample Output**</span></span>

```
Name       object_id   memory_allocated_for_table_kb memory_used_by_table_kb memory_allocated_for_indexes_kb memory_used_by_indexes_kb
---------- ----------- ----------------------------- ----------------------- ------------------------------- -------------------------
t3         629577281   0                             0                       128                             0
t1         565577053   1372928                       1200008                 7872                            1942
t2         597577167   0                             0                       128                             0
NULL       -6          0                             0                       2                               2
NULL       -5          0                             0                       24                              24
NULL       -4          0                             0                       2                               2
NULL       -3          0                             0                       2                               2
NULL       -2          192                           25                      16                              16
```

 <span data-ttu-id="b303f-132">Para obter mais informações, consulte [Sys. dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span><span class="sxs-lookup"><span data-stu-id="b303f-132">For more information, see [sys.dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span></span>

#### <a name="memory-consumption-by-internal-system-structures"></a><span data-ttu-id="b303f-133">Consumo de memória por estruturas internas do sistema</span><span class="sxs-lookup"><span data-stu-id="b303f-133">Memory consumption by internal system structures</span></span>
 <span data-ttu-id="b303f-134">A memória também é consumida por objetos do sistema, tais como estruturas transacionais, buffers para arquivos de dados e delta, estruturas de coleta de lixo, entre outros.</span><span class="sxs-lookup"><span data-stu-id="b303f-134">Memory is also consumed by system objects, such as, transactional structures, buffers for data and delta files, garbage collection structures, and more.</span></span> <span data-ttu-id="b303f-135">Você pode localizar a memória usada para esses objetos de sistema consultando `sys.dm_xtp_system_memory_consumers` , conforme mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="b303f-135">You can find the memory used for these system objects by querying `sys.dm_xtp_system_memory_consumers` as shown here.</span></span>

```sql
SELECT memory_consumer_desc
     , allocated_bytes/1024 AS allocated_bytes_kb
     , used_bytes/1024 AS used_bytes_kb
     , allocation_count
   FROM sys.dm_xtp_system_memory_consumers
```

 <span data-ttu-id="b303f-136">**Saída de exemplo**</span><span class="sxs-lookup"><span data-stu-id="b303f-136">**Sample Output**</span></span>

```
memory_consumer_ desc allocated_bytes_kb   used_bytes_kb        allocation_count
------------------------- -------------------- -------------------- ----------------
VARHEAP                   0                    0                    0
VARHEAP                   384                  0                    0
DBG_GC_OUTSTANDING_T      64                   64                   910
ACTIVE_TX_MAP_LOOKAS      0                    0                    0
RECOVERY_TABLE_CACHE      0                    0                    0
RECENTLY_USED_ROWS_L      192                  192                  261
RANGE_CURSOR_LOOKSID      0                    0                    0
HASH_CURSOR_LOOKASID      128                  128                  455
SAVEPOINT_LOOKASIDE       0                    0                    0
PARTIAL_INSERT_SET_L      192                  192                  351
CONSTRAINT_SET_LOOKA      192                  192                  646
SAVEPOINT_SET_LOOKAS      0                    0                    0
WRITE_SET_LOOKASIDE       192                  192                  183
SCAN_SET_LOOKASIDE        64                   64                   31
READ_SET_LOOKASIDE        0                    0                    0
TRANSACTION_LOOKASID      448                  448                  156
PGPOOL:256K               768                  768                  3
PGPOOL: 64K               0                    0                    0
PGPOOL:  4K               0                    0                    0
```

 <span data-ttu-id="b303f-137">Para obter mais informações, veja [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b303f-137">For more information see [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span></span>


#### <a name="memory-consumption-at-run-time-when-accessing-memory-optimized-tables"></a><span data-ttu-id="b303f-138">Consumo de memória em tempo de execução ao acessar tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="b303f-138">Memory consumption at run-time when accessing memory-optimized tables</span></span>
 <span data-ttu-id="b303f-139">Você pode determinar a memória consumida por estruturas em tempo de execução; por exemplo, o cache de procedimento com a seguinte consulta: execute esta consulta para obter a memória usada por estruturas em tempo de execução, como o cache de procedimento.</span><span class="sxs-lookup"><span data-stu-id="b303f-139">You can determine the memory consumed by run time structures, such as the procedure cache with the following query: run this query to get the memory used by run-time structures such as for the procedure cache.</span></span> <span data-ttu-id="b303f-140">Todas as estruturas em tempo de execução são marcadas com XTP.</span><span class="sxs-lookup"><span data-stu-id="b303f-140">All run-time structures are tagged with XTP.</span></span>

```sql
SELECT memory_object_address
     , pages_in_bytes
     , bytes_used
     , type
   FROM sys.dm_os_memory_objects WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="b303f-141">**Saída de exemplo**</span><span class="sxs-lookup"><span data-stu-id="b303f-141">**Sample Output**</span></span>

```
memory_object_address pages_ in_bytes bytes_used type
--------------------- ------------------- ---------- ----
0x00000001F1EA8040    507904              NULL       MEMOBJ_XTPDB
0x00000001F1EAA040    68337664            NULL       MEMOBJ_XTPDB
0x00000001FD67A040    16384               NULL       MEMOBJ_XTPPROCCACHE
0x00000001FD68C040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD284040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD302040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD382040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD402040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD482040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD502040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD67E040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001F813C040    8192                NULL       MEMOBJ_XTPBLOCKALLOC
0x00000001F813E040    16842752            NULL       MEMOBJ_XTPBLOCKALLOC
```

 <span data-ttu-id="b303f-142">Para obter mais informações, consulte [Sys. dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b303f-142">For more information, see [sys.dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span></span>

#### <a name="memory-consumed-by-hek_2-engine-across-the-instance"></a><span data-ttu-id="b303f-143">Memória consumida pelo mecanismo [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] na instância</span><span class="sxs-lookup"><span data-stu-id="b303f-143">Memory consumed by [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine across the instance</span></span>
 <span data-ttu-id="b303f-144">A memória alocada para o mecanismo [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] e os objetos com otimização de memória são gerenciados da mesma maneira que qualquer outro consumidor de memória em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b303f-144">Memory allocated to the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine and the memory-optimized objects is managed the same way as any other memory consumer within a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b303f-145">Os administradores do tipo MEMORYCLERK_XTP respondem por toda a memória alocada para o mecanismo [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b303f-145">The clerks of type MEMORYCLERK_XTP accounts for all the memory allocated to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span> <span data-ttu-id="b303f-146">Use a consulta a seguir para localizar toda a memória usada pelo mecanismo [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b303f-146">Use the following query to find all the memory used by the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span>

```sql
-- this DMV accounts for all memory used by the hek_2 engine
SELECT type
     , name
     , memory_node_id
     , pages_kb/1024 AS pages_MB 
   FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="b303f-147">A saída de exemplo mostra que a memória total alocada equivale a 18MB de consumo de memória em nível de sistema e a 1358MB alocados para a ID de banco de dados de valor 5.</span><span class="sxs-lookup"><span data-stu-id="b303f-147">The sample output shows that the total memory allocated is 18 MB system-level memory consumption and 1358MB allocated to database id of 5.</span></span> <span data-ttu-id="b303f-148">Como esse banco de dados é mapeado para um pool de recursos dedicados, essa memória é contabilizada nesse pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="b303f-148">Since this database is mapped to a dedicated resource pool, this memory is accounted for in that resource pool.</span></span>

 <span data-ttu-id="b303f-149">**Saída de exemplo**</span><span class="sxs-lookup"><span data-stu-id="b303f-149">**Sample Output**</span></span>

```
type                 name       memory_node_id pages_MB
-------------------- ---------- -------------- --------------------
MEMORYCLERK_XTP      Default    0              18
MEMORYCLERK_XTP      DB_ID_5    0              1358
MEMORYCLERK_XTP      Default    64             0
```

 <span data-ttu-id="b303f-150">Para obter mais informações, consulte [Sys. dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b303f-150">For more information, see [sys.dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span></span>

##   <a name="managing-memory-consumed-by-memory-optimized-objects"></a><span data-ttu-id="b303f-151">Gerenciando a memória consumida por objetos com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="b303f-151">Managing memory consumed by memory-optimized objects</span></span>
 <span data-ttu-id="b303f-152">É possível controlar a memória total consumida por tabelas com otimização de memória, associando-a a um grupo de recursos nomeado, conforme descrito no tópico [Associar um banco de dados com tabelas com otimização de memória a um pool de recursos](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b303f-152">You can control the total memory consumed by memory-optimized tables by binding it to a named resource pool as described in the topic [Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span></span>

##  <a name="troubleshooting-memory-issues"></a><span data-ttu-id="b303f-153">Solucionando problemas de memória</span><span class="sxs-lookup"><span data-stu-id="b303f-153">Troubleshooting Memory Issues</span></span>
 <span data-ttu-id="b303f-154">A solução de problemas de memória é um processo de três etapas:</span><span class="sxs-lookup"><span data-stu-id="b303f-154">Troubleshooting memory issues is a three step process:</span></span>

1.  <span data-ttu-id="b303f-155">Identificar a quantidade de memória que está sendo consumido pelos objetos no banco de dados ou instância.</span><span class="sxs-lookup"><span data-stu-id="b303f-155">Identify how much memory is being consumed by the objects in your database or instance.</span></span> <span data-ttu-id="b303f-156">Você pode usar um excelente conjunto de ferramentas de monitoramento disponíveis para tabelas com otimização de memória, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b303f-156">You can use a rich set of monitoring tools available for memory-optimized tables as described earlier.</span></span>  <span data-ttu-id="b303f-157">Por exemplo, os DMVs `sys.dm_db_xtp_table_memory_stats` ou `sys.dm_os_memory_clerks`.</span><span class="sxs-lookup"><span data-stu-id="b303f-157">For example the DMVs `sys.dm_db_xtp_table_memory_stats` or `sys.dm_os_memory_clerks`.</span></span>

2.  <span data-ttu-id="b303f-158">Determine como o consumo de memória aumenta e o espaço disponível para você.</span><span class="sxs-lookup"><span data-stu-id="b303f-158">Determine how memory consumption is growing and how much head room you have left.</span></span> <span data-ttu-id="b303f-159">Ao monitorar o consumo de memória periodicamente, você pode saber como o uso da memória está aumentando.</span><span class="sxs-lookup"><span data-stu-id="b303f-159">By monitoring the memory consumption periodically, you can know how the memory use is growing.</span></span> <span data-ttu-id="b303f-160">Por exemplo, se você mapeou o banco de dados para um pool de recursos nomeado, poderá monitorar o contador de desempenho Memória Usada (KB) para ver o aumento no uso de memória.</span><span class="sxs-lookup"><span data-stu-id="b303f-160">For example, if you have mapped the database to a named resource pool, you can monitor the performance counter Used Memory (KB) to see how memory usage is growing.</span></span>

3.  <span data-ttu-id="b303f-161">Execute uma ação para reduzir os problemas potenciais de memória.</span><span class="sxs-lookup"><span data-stu-id="b303f-161">Take action to mitigate the potential memory issues.</span></span> <span data-ttu-id="b303f-162">Para obter mais informações, consulte [resolver problemas de memória insuficiente](resolve-out-of-memory-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b303f-162">For more information, see [Resolve Out Of Memory Issues](resolve-out-of-memory-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b303f-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b303f-163">See Also</span></span>
 <span data-ttu-id="b303f-164">[Associar um banco de dados com tabelas com otimização de memória a um pool de recursos](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [alterar MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT em um pool existente](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span><span class="sxs-lookup"><span data-stu-id="b303f-164">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [Change MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on an existing pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span></span>


