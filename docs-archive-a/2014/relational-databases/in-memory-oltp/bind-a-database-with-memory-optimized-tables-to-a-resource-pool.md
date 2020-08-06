---
title: Associar um banco de dados com tabelas com otimização de memória a um pool de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f222b1d5-d2fa-4269-8294-4575a0e78636
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cd163c5d3bc7a2cd9051b8d37b8127a1cc88c30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584134"
---
# <a name="bind-a-database-with-memory-optimized-tables-to-a-resource-pool"></a><span data-ttu-id="226e8-102">Associar um banco de dados com tabelas com otimização de memória a um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="226e8-102">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>
  <span data-ttu-id="226e8-103">Um pool de recursos representa um subconjunto de recursos físicos que podem ser controlados.</span><span class="sxs-lookup"><span data-stu-id="226e8-103">A resource pool represents a subset of physical resources that can be governed.</span></span> <span data-ttu-id="226e8-104">Por padrão, os bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estão associados a e consomem recursos do pool de recursos padrão.</span><span class="sxs-lookup"><span data-stu-id="226e8-104">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases are bound to and consume the resources of the default resource pool.</span></span> <span data-ttu-id="226e8-105">Para proteger o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de ter todos os recursos consumidos por uma ou mais tabelas com otimização de memória, e evitar que outros usuários da memória consumam a memória necessária para as tabelas com otimização de memória, você deve criar um pool de recursos separado para gerenciar o consumo de memória para o banco de dados com tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="226e8-105">To protect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from having its resources consumed by one or more memory-optimized tables, and to prevent other memory users from consuming memory needed by memory-optimized tables, you should create a separate resource pool to manage memory consumption for the database with memory-optimized tables.</span></span>  
  
 <span data-ttu-id="226e8-106">Um banco de dados pode estar associado em apenas um pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="226e8-106">A database can be bound on only one resource pool.</span></span> <span data-ttu-id="226e8-107">No entanto, você pode associar vários bancos de dados ao mesmo pool.</span><span class="sxs-lookup"><span data-stu-id="226e8-107">However, you can bind multiple databases to the same pool.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="226e8-108">permite associar um banco de dados sem tabelas com otimização de memória a um pool de recursos, mas isso não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="226e8-108">allows binding a database without memory-optimized tables to a resource pool but it has no effect.</span></span> <span data-ttu-id="226e8-109">Talvez você queira associar um banco de dados a um pool de recursos denominado se, no futuro, talvez você quiser criar tabelas com otimização de memória no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="226e8-109">You may want to bind a database to a named resource pool if, in future, you may want to create memory-optimized tables in the database.</span></span>  
  
 <span data-ttu-id="226e8-110">Antes de associar um banco de dados a um pool de recursos, o banco de dados e o pool de recursos devem existir.</span><span class="sxs-lookup"><span data-stu-id="226e8-110">Before you can bind a database to a resource pool both the database and the resource pool must exist.</span></span> <span data-ttu-id="226e8-111">A associação entra em vigor da próxima vez que o banco de dados é colocado online.</span><span class="sxs-lookup"><span data-stu-id="226e8-111">The binding takes effect the next time the database is brought online.</span></span> <span data-ttu-id="226e8-112">Veja [Estados de banco de dados](../databases/database-states.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="226e8-112">See [Database States](../databases/database-states.md) for more information.</span></span>  
  
 <span data-ttu-id="226e8-113">Para obter informações sobre pools de recursos, veja [Pool de recursos do Administrador de Recursos](../resource-governor/resource-governor-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="226e8-113">For information about resource pools, see [Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md).</span></span>  
  
  
## <a name="create-the-database-and-resource-pool"></a><span data-ttu-id="226e8-114">Criar o banco de dados e o pool de recursos</span><span class="sxs-lookup"><span data-stu-id="226e8-114">Create the database and resource pool</span></span>  
 <span data-ttu-id="226e8-115">Você pode criar o banco de dados e o pool de recursos em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="226e8-115">You can create the database and resource pool in any order.</span></span> <span data-ttu-id="226e8-116">O que importa é que ambos existam antes de associar o banco de dados ao pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="226e8-116">What matters is that they both exist prior to binding the database to the resource pool.</span></span>  
  
### <a name="create-the-database"></a><span data-ttu-id="226e8-117">Criar o banco de dados</span><span class="sxs-lookup"><span data-stu-id="226e8-117">Create the database</span></span>  
 <span data-ttu-id="226e8-118">O [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir cria um banco de dados chamado IMOLTP_DB que conterá uma ou mais tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="226e8-118">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a database named IMOLTP_DB which will contain one or more memory-optimized tables.</span></span> <span data-ttu-id="226e8-119">O caminho \<driveAndPath> precisa existir antes da execução desse comando.</span><span class="sxs-lookup"><span data-stu-id="226e8-119">The path \<driveAndPath> must exist prior to running this command.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP_DB  
GO  
ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_fg CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_fg' , FILENAME = 'c:\data\IMOLTP_DB_fg') TO FILEGROUP IMOLTP_DB_fg;  
GO  
```  
  
### <a name="determine-the-minimum-value-for-min_memory_percent-and-max_memory_percent"></a><span data-ttu-id="226e8-120">Determine o valor mínimo de MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT</span><span class="sxs-lookup"><span data-stu-id="226e8-120">Determine the minimum value for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT</span></span>  
 <span data-ttu-id="226e8-121">Depois que você determinar as necessidades de memória para tabelas com otimização de memória, será necessário determinar o percentual de memória disponível necessário e definir os percentuais de memória com esse valor ou um valor mais alto.</span><span class="sxs-lookup"><span data-stu-id="226e8-121">Once you determine the memory needs for your memory-optimized tables, you need to determine what percentage of available memory you need, and set the memory percentages to that value or higher.</span></span>  
  
 <span data-ttu-id="226e8-122">**Exemplo:**  </span><span class="sxs-lookup"><span data-stu-id="226e8-122">**Example:** </span></span>  
<span data-ttu-id="226e8-123">Para este exemplo, vamos pressupor que, com base nos cálculos, você determinou que suas tabelas com otimização de memória e índices precisam de 16 GB de memória.</span><span class="sxs-lookup"><span data-stu-id="226e8-123">For this example we will assume that from your calculations you determined that your memory-optimized tables and indexes need 16 GB of memory.</span></span> <span data-ttu-id="226e8-124">Digamos que você tenha 32 GB de memória confirmada para uso.</span><span class="sxs-lookup"><span data-stu-id="226e8-124">Assume that you have 32 GB of memory committed for your use.</span></span>  
  
 <span data-ttu-id="226e8-125">À primeira vista pode parecer que você precisa definir MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT como 50 (16 são de 50% de 32).</span><span class="sxs-lookup"><span data-stu-id="226e8-125">At first glance it could seem that you need to set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to 50 (16 is 50% of 32).</span></span>  <span data-ttu-id="226e8-126">No entanto, isso não daria memória suficiente às tabelas com otimização de memória otimizada.</span><span class="sxs-lookup"><span data-stu-id="226e8-126">However, that would not give your memory-optimized tables sufficient memory.</span></span> <span data-ttu-id="226e8-127">Examinando a tabela abaixo ([Percentual de memória disponível de índices e tabelas com otimização de memória](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)), vemos que, se houver 32 GB de memória confirmada, somente 80% dessa quantidade estará disponível para índices e tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="226e8-127">Looking at the table below ([Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)) we see that if there is 32 GB of committed memory, only 80% of that is available for memory-optimized tables and indexes.</span></span>  <span data-ttu-id="226e8-128">Consequentemente, calculamos percentuais mínimo e máximo com base na memória disponível, não na memória confirmada.</span><span class="sxs-lookup"><span data-stu-id="226e8-128">Therefore, we calculate the min and max percentages based upon the available memory, not the committed memory.</span></span>  
  
 `memoryNeedeed = 16`   
 `memoryCommitted = 32`   
 `availablePercent = 0.8`   
 `memoryAvailable = memoryCommitted * availablePercent`   
 `percentNeeded = memoryNeeded / memoryAvailable`  
  
 <span data-ttu-id="226e8-129">Em números reais:</span><span class="sxs-lookup"><span data-stu-id="226e8-129">Plugging in real numbes:</span></span>   
`percentNeeded = 16 / (32 * 0.8) = 16 / 25.6 = 0.625`  
  
 <span data-ttu-id="226e8-130">Dessa forma, você precisa de pelo menos 62,5% da memória disponível para cumprir o requisito de 16 GB de tabelas com otimização de memória e índices.</span><span class="sxs-lookup"><span data-stu-id="226e8-130">Thus you need at least 62.5% of the available memory to meet the 16 GB requirement of your memory-optimized tables and indexes.</span></span>  <span data-ttu-id="226e8-131">Como os valores de MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT devem ser inteiros, vamos configurá-los como pelo menos 63%.</span><span class="sxs-lookup"><span data-stu-id="226e8-131">Since the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT must be integers, we set them to at least 63%.</span></span>  
  
### <a name="create-a-resource-pool-and-configure-memory"></a><span data-ttu-id="226e8-132">Criar um pool de recursos e configurar a memória</span><span class="sxs-lookup"><span data-stu-id="226e8-132">Create a resource pool and configure memory</span></span>  
 <span data-ttu-id="226e8-133">Ao configurar a memória para tabelas com otimização de memória, o planejamento de capacidade deve ser feito com base em MIN_MEMORY_PERCENT, não MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="226e8-133">When configuring memory for memory-optimized tables, the capacity planning should be done based on MIN_MEMORY_PERCENT, not on MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="226e8-134">Veja [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) para obter informações sobre MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="226e8-134">See [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) for information on MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="226e8-135">Isso fornece uma disponibilidade de memória mais previsível para tabelas com otimização de memória porque o MIN_MEMORY_PERCENT causa uma pressão de memória em outros pools de recursos para garantir que seja cumprida.</span><span class="sxs-lookup"><span data-stu-id="226e8-135">This provides more predictable memory availability for memory-optimized tables as MIN_MEMORY_PERCENT causes memory pressure to other resource pools to make sure it is honored.</span></span> <span data-ttu-id="226e8-136">Para garantir que essa memória esteja disponível e para ajudar a evitar condições de memória insuficiente, os valores de MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT devem ser iguais.</span><span class="sxs-lookup"><span data-stu-id="226e8-136">To ensure that memory is available and help avoid out-of-memory conditions, the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT should be the same.</span></span> <span data-ttu-id="226e8-137">Veja [Percentual de memória disponível de índices e tabelas com otimização de memória](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) abaixo para obter o percentual de memória disponível para tabelas com otimização de memória com base na quantidade de memória confirmada.</span><span class="sxs-lookup"><span data-stu-id="226e8-137">See [Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) below for the percent of memory available for memory-optimized tables based on the amount of committed memory.</span></span>  
  
 <span data-ttu-id="226e8-138">Confira [Melhores práticas: usar OLTP in-memory em um ambiente de VM](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) para obter mais informações ao trabalhar em um ambiente de VM.</span><span class="sxs-lookup"><span data-stu-id="226e8-138">See [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information when working in a VM environment.</span></span>  
  
 <span data-ttu-id="226e8-139">O código [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir cria um pool de recursos chamado Pool_IMOLTP com metade da memória disponível para esse uso.</span><span class="sxs-lookup"><span data-stu-id="226e8-139">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a resource pool named Pool_IMOLTP with half of the memory available for its use.</span></span>  <span data-ttu-id="226e8-140">Depois que o pool é criado, o Administrador de Recursos é reconfigurado para incluir Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="226e8-140">After the pool is created Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
-- set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to the same value  
CREATE RESOURCE POOL Pool_IMOLTP   
  WITH   
    ( MIN_MEMORY_PERCENT = 63,   
    MAX_MEMORY_PERCENT = 63 );  
GO  
  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="bind-the-database-to-the-pool"></a><span data-ttu-id="226e8-141">Associar o banco de dados ao pool</span><span class="sxs-lookup"><span data-stu-id="226e8-141">Bind the database to the pool</span></span>  
 <span data-ttu-id="226e8-142">Use a função do sistema `sp_xtp_bind_db_resource_pool` para associar o banco de dados ao pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="226e8-142">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="226e8-143">A função usa dois parâmetros: o nome do banco de dados e o nome do pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="226e8-143">The function takes two parameters: the database name and the resource pool name.</span></span>  
  
 <span data-ttu-id="226e8-144">O [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir define uma associação do banco de dados IMOLTP_DB ao pool de recursos Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="226e8-144">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="226e8-145">A associação não entra em vigor até que você coloque o banco de dados online.</span><span class="sxs-lookup"><span data-stu-id="226e8-145">The binding does not become effective until you bring the database online.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
 <span data-ttu-id="226e8-146">A função de sistema sp_xtp_bind_db_resourece_pool usa dois parâmetros de cadeia de caracteres: nome_do_banco_de_dados e nome_do_pool.</span><span class="sxs-lookup"><span data-stu-id="226e8-146">The system function sp_xtp_bind_db_resourece_pool takes two string parameters: database_name and pool_name.</span></span>  
  
## <a name="confirm-the-binding"></a><span data-ttu-id="226e8-147">Confirmar a associação</span><span class="sxs-lookup"><span data-stu-id="226e8-147">Confirm the binding</span></span>  
 <span data-ttu-id="226e8-148">Confirme a associação, observando a ID do pool de recursos para IMOLTP_DB.</span><span class="sxs-lookup"><span data-stu-id="226e8-148">Confirm the binding, noting the resource pool id for IMOLTP_DB.</span></span> <span data-ttu-id="226e8-149">Não deve ser NULL.</span><span class="sxs-lookup"><span data-stu-id="226e8-149">It should not be NULL.</span></span>  
  
```sql  
SELECT d.database_id, d.name, d.resource_pool_id  
FROM sys.databases d  
GO  
```  
  
## <a name="make-the-binding-effective"></a><span data-ttu-id="226e8-150">Tornar a associação efetiva</span><span class="sxs-lookup"><span data-stu-id="226e8-150">Make the binding effective</span></span>  
 <span data-ttu-id="226e8-151">Você deve colocar o banco de dados offline e depois online de novo depois de associá-lo ao pool de recursos para que a associação entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="226e8-151">You must take the database offline and back online after binding it to the resource pool for binding to take effect.</span></span> <span data-ttu-id="226e8-152">Se seu banco de dados tiver sido associado a um pool diferente anteriormente, isso removerá a memória alocada do pool de recursos anterior, e as alocações de memória para sua tabela com otimização de memória e os índices agora virão do pool de recursos recém-associado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="226e8-152">If your database was bound to an a different pool earlier, this removes the allocated memory from the previous resource pool and memory allocations for your memory-optimized table and indexes will now come from the resource pool newly bound with the database.</span></span>  
  
```sql  
USE master  
GO  
  
ALTER DATABASE IMOLTP_DB SET OFFLINE  
GO  
ALTER DATABASE IMOLTP_DB SET ONLINE  
GO  
  
USE IMOLTP_DB  
GO  
```  
  
 <span data-ttu-id="226e8-153">Agora o banco de dados está associado ao pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="226e8-153">And now, the database is bound to the resource pool.</span></span>  
  
## <a name="change-min-memory-percent-and-max-memory-percent-on-an-existing-pool"></a><span data-ttu-id="226e8-154">Alterar a porcentagem mínima de memória e a porcentagem máxima de memória em um pool existente</span><span class="sxs-lookup"><span data-stu-id="226e8-154">Change MIN MEMORY PERCENT and MAX MEMORY PERCENT on an existing pool</span></span>  
 <span data-ttu-id="226e8-155">Se você adicionar mais memória ao servidor ou se a quantidade de memória das suas tabelas com otimização de memória for alterada, talvez seja necessário alterar o valor de MIN_MEMORY_PERCENT e de MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="226e8-155">If you add additional memory to the server or the amount of memory needed for your memory-optimized tables changes, you may need to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="226e8-156">As etapas a seguir mostram como alterar o valor de MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT em um pool de recursos.</span><span class="sxs-lookup"><span data-stu-id="226e8-156">The following steps show you how to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on a resource pool.</span></span> <span data-ttu-id="226e8-157">Consulte a seção abaixo, para obter orientação sobre quais valores usar para MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="226e8-157">See the section below, for guidance on what values to use for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="226e8-158">Confira o tópico [Melhores práticas: usar OLTP in-memory em um ambiente de VM](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="226e8-158">See the topic [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information.</span></span>  
  
1.  <span data-ttu-id="226e8-159">Use `ALTER RESOURCE POOL` para alterar o valor de MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="226e8-159">Use `ALTER RESOURCE POOL` to change the value of both MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  
  
2.  <span data-ttu-id="226e8-160">Use `ALTER RESURCE GOVERNOR` para reconfigurar o Administrador de Recursos com os novos valores.</span><span class="sxs-lookup"><span data-stu-id="226e8-160">Use `ALTER RESURCE GOVERNOR` to reconfigure the Resource Governor with the new values.</span></span>  
  
 <span data-ttu-id="226e8-161">**Código de exemplo**</span><span class="sxs-lookup"><span data-stu-id="226e8-161">**Sample Code**</span></span>  
  
```sql  
ALTER RESOURCE POOL Pool_IMOLTP  
WITH  
     ( MIN_MEMORY_PERCENT = 70,  
       MAX_MEMORY_PERCENT = 70 )   
GO  
  
-- reconfigure the Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE  
GO  
```  
  
## <a name="percent-of-memory-available-for-memory-optimized-tables-and-indexes"></a><span data-ttu-id="226e8-162">Porcentagem de memória disponível para tabelas com otimização de memória e índices</span><span class="sxs-lookup"><span data-stu-id="226e8-162">Percent of memory available for memory-optimized tables and indexes</span></span>  
 <span data-ttu-id="226e8-163">Se você mapear um banco de dados com tabelas com otimização de memória e uma carga de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o mesmo pool de recursos, o Administrador de Recursos definirá um limite interno para o [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] usar de modo que os usuários do pool não tenham conflitos sobre o uso do pool.</span><span class="sxs-lookup"><span data-stu-id="226e8-163">If you map a database with memory-optimized tables and a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] workload to the same resource pool, the Resource Governor sets an internal threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use so that the users of the pool do not have conflicts over pool usage.</span></span> <span data-ttu-id="226e8-164">Em linhas gerais, o limite para o uso do [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] é de aproximadamente 80% do pool.</span><span class="sxs-lookup"><span data-stu-id="226e8-164">Generally speaking, the threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use is about 80% of the pool.</span></span> <span data-ttu-id="226e8-165">A tabela a seguir mostra os limites reais para vários tamanhos de memória.</span><span class="sxs-lookup"><span data-stu-id="226e8-165">The following table shows actual thresholds for various memory sizes.</span></span>  
  
 <span data-ttu-id="226e8-166">Quando você cria um pool de recursos dedicado para o banco de dados [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] , precisa estimar a quantidade de memória física necessária para as tabelas na memória, após considerar versões de linhas e o crescimento de dados.</span><span class="sxs-lookup"><span data-stu-id="226e8-166">When you create a dedicated resource pool for the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database, you need to estimate how much physical memory you need for the in-memory tables after accounting for row versions and data growth.</span></span> <span data-ttu-id="226e8-167">Após calcular a memória necessária, crie um pool de recursos com uma porcentagem da memória de destino de confirmação para a Instância SQL, conforme refletido pela coluna ‘committed_target_kb’ no DMV `sys.dm_os_sys_info` (veja [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="226e8-167">Once estimate the memory needed, you create a resource pool with a percent of the commit target memory for SQL Instance as reflected by column 'committed_target_kb' in the DMV `sys.dm_os_sys_info` (see [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span></span> <span data-ttu-id="226e8-168">Por exemplo, você pode criar um pool de recursos P1 com 40% da memória total disponível para a instância.</span><span class="sxs-lookup"><span data-stu-id="226e8-168">For example, you can create a resource pool P1 with 40% of the total memory available to the instance.</span></span> <span data-ttu-id="226e8-169">Além desses 40%, o mecanismo de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] obtém uma porcentagem menor para armazenar dados de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="226e8-169">Out of this 40%, the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine gets a smaller percent to store [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] data.</span></span>  <span data-ttu-id="226e8-170">Isso é feito para garantir que [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] não consuma toda a memória desse pool.</span><span class="sxs-lookup"><span data-stu-id="226e8-170">This is done to make sure [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] does not consume all the memory from this pool.</span></span>  <span data-ttu-id="226e8-171">Esse valor de porcentagem menor depende da Memória confirmada de destino.</span><span class="sxs-lookup"><span data-stu-id="226e8-171">This value of the smaller percent depends upon the Target committed Memory.</span></span> <span data-ttu-id="226e8-172">A tabela a seguir descreve a memória disponível para o banco de dados de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] em um pool de recursos (nomeado ou padrão), antes que um erro de OOM seja gerado.</span><span class="sxs-lookup"><span data-stu-id="226e8-172">The following table describes memory available to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database in a resource pool (named or default) before an OOM error is raised.</span></span>  
  
|<span data-ttu-id="226e8-173">Memória confirmada de destino</span><span class="sxs-lookup"><span data-stu-id="226e8-173">Target Committed Memory</span></span>|<span data-ttu-id="226e8-174">Porcentagem disponível para tabelas na memória</span><span class="sxs-lookup"><span data-stu-id="226e8-174">Percent available for in-memory tables</span></span>|  
|-----------------------------|---------------------------------------------|  
|<span data-ttu-id="226e8-175"><= 8 GB</span><span class="sxs-lookup"><span data-stu-id="226e8-175"><= 8 GB</span></span>|<span data-ttu-id="226e8-176">70%</span><span class="sxs-lookup"><span data-stu-id="226e8-176">70%</span></span>|  
|<span data-ttu-id="226e8-177"><= 16 GB</span><span class="sxs-lookup"><span data-stu-id="226e8-177"><= 16 GB</span></span>|<span data-ttu-id="226e8-178">75%</span><span class="sxs-lookup"><span data-stu-id="226e8-178">75%</span></span>|  
|<span data-ttu-id="226e8-179"><= 32 GB</span><span class="sxs-lookup"><span data-stu-id="226e8-179"><= 32 GB</span></span>|<span data-ttu-id="226e8-180">80%</span><span class="sxs-lookup"><span data-stu-id="226e8-180">80%</span></span>|  
|<span data-ttu-id="226e8-181">\<= 96 GB</span><span class="sxs-lookup"><span data-stu-id="226e8-181">\<= 96 GB</span></span>|<span data-ttu-id="226e8-182">85%</span><span class="sxs-lookup"><span data-stu-id="226e8-182">85%</span></span>|  
|<span data-ttu-id="226e8-183">>96 GB</span><span class="sxs-lookup"><span data-stu-id="226e8-183">>96 GB</span></span>|<span data-ttu-id="226e8-184">90%</span><span class="sxs-lookup"><span data-stu-id="226e8-184">90%</span></span>|  
  
 <span data-ttu-id="226e8-185">Por exemplo, se a 'memória confirmada de destino' for 100 GB e você calcular que as tabelas com otimização de memória e os índices precisam de 60 GB de memória, poderá criar um pool de recursos com MAX_MEMORY_PERCENT = 67 (60 GB necessários / 0,90 = 66,667 GB – arredondar para 67 GB, 67 GB / 100 GB instalados = 67%) para garantir que seus objetos [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] tenham os 60 GB necessários.</span><span class="sxs-lookup"><span data-stu-id="226e8-185">For example, if your 'target committed memory' is 100 GB, and you estimate your memory-optimized tables and indexes need 60GBof memory, then you can create a resource pool with MAX_MEMORY_PERCENT = 67 (60GB needed / 0.90 = 66.667GB - round up to 67GB; 67GB / 100GB installed = 67%) to ensure that your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] objects have the 60GB they need.</span></span>  
  
 <span data-ttu-id="226e8-186">Quando um banco de dados for associado a um pool de recursos nomeado, use a consulta a seguir para ver as alocações de memória em diferentes pools de recursos.</span><span class="sxs-lookup"><span data-stu-id="226e8-186">Once a database has been bound to a named resource pool, use the following query to see memory allocations across different resource pools.</span></span>  
  
```sql  
SELECT pool_id  
     , Name  
     , min_memory_percent  
     , max_memory_percent  
     , max_memory_kb/1024 AS max_memory_mb  
     , used_memory_kb/1024 AS used_memory_mb   
     , target_memory_kb/1024 AS target_memory_mb  
   FROM sys.dm_resource_governor_resource_pools  
```  
  
 <span data-ttu-id="226e8-187">Esta saída de exemplo mostra que a memória usada por objetos com otimização de memória é de 1356 MB no pool de recursos, PoolIMOLTP, com um limite superior de 2307 MB.</span><span class="sxs-lookup"><span data-stu-id="226e8-187">This sample output shows that the memory taken by memory-optimized objects is 1356 MB in resource pool, PoolIMOLTP, with an upper bound of 2307 MB.</span></span> <span data-ttu-id="226e8-188">Esse limite superior controla a memória total que pode ser usada pelo usuário e os objetos com otimização de memória do sistema que são mapeados para esse pool.</span><span class="sxs-lookup"><span data-stu-id="226e8-188">This upper bound controls the total memory that can be taken by user and system memory-optimized objects mapped to this pool.</span></span>  
  
 <span data-ttu-id="226e8-189">**Saída de exemplo** </span><span class="sxs-lookup"><span data-stu-id="226e8-189">**Sample Output** </span></span>  
<span data-ttu-id="226e8-190">Esta saída é do banco de dados e das tabelas criadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="226e8-190">This output is from the database and tables we created above.</span></span>  
  
```  
pool_id     Name        min_memory_percent max_memory_percent max_memory_mb used_memory_mb target_memory_mb  
----------- ----------- ------------------ ------------------ ------------- -------------- ----------------   
1           internal    0                  100                3845          125            3845  
2           default     0                  100                3845          32             3845  
259         PoolIMOLTP 0                  100                3845          1356           2307  
```  
  
 <span data-ttu-id="226e8-191">Para obter mais informações, veja [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="226e8-191">For more information see [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span></span>  
  
 <span data-ttu-id="226e8-192">Se você não associa o banco de dados a um pool de recursos nomeado, ele é associado ao pool ‘padrão‘.</span><span class="sxs-lookup"><span data-stu-id="226e8-192">If you do not bind your database to a named resource pool, it is bound to the 'default' pool.</span></span> <span data-ttu-id="226e8-193">Como o pool de recursos padrão é usado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a maioria das demais alocações, você não poderá monitorar a memória consumida por tabelas com otimização de memória usando o DMV sys.dm_resource_governor_resource_pools de forma precisa para o banco de dados de interesse.</span><span class="sxs-lookup"><span data-stu-id="226e8-193">Since default resource pool is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for most other allocations, you will not be able to monitor memory consumed by memory-optimized tables using the DMV sys.dm_resource_governor_resource_pools accurately for the database of interest.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="226e8-194">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="226e8-194">See Also</span></span>  
 <span data-ttu-id="226e8-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="226e8-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="226e8-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="226e8-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="226e8-197">[Administrador de Recursos](../resource-governor/resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="226e8-197">[Resource Governor](../resource-governor/resource-governor.md) </span></span>  
 <span data-ttu-id="226e8-198">[Pool de recursos do Administrador de Recursos](../resource-governor/resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="226e8-198">[Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="226e8-199">[Criar um pool de recursos](../resource-governor/create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="226e8-199">[Create a Resource Pool](../resource-governor/create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="226e8-200">[Alterar configurações do pool de recursos](../resource-governor/change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="226e8-200">[Change Resource Pool Settings](../resource-governor/change-resource-pool-settings.md) </span></span>  
 [<span data-ttu-id="226e8-201">Excluir um pool de recursos</span><span class="sxs-lookup"><span data-stu-id="226e8-201">Delete a Resource Pool</span></span>](../resource-governor/delete-a-resource-pool.md)  
  
  
