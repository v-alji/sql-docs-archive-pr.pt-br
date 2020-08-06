---
title: Restauração por etapas de bancos de dados com tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 732c9721-8dd4-481d-8ff9-1feaaa63f84f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ed23f08d40e23b1d43c1b642f4089fe77646b675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684212"
---
# <a name="piecemeal-restore-of-databases-with-memory-optimized-tables"></a><span data-ttu-id="05b94-102">Restauração por etapas de bancos de dados com tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="05b94-102">Piecemeal Restore of Databases With Memory-Optimized Tables</span></span>
  <span data-ttu-id="05b94-103">A restauração por etapas tem suporte em bancos de dados com tabelas com otimização de memória, exceto para uma restrição descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="05b94-103">Piecemeal restore is supported on databases with memory-optimized tables except for one restriction described below.</span></span> <span data-ttu-id="05b94-104">Para obter mais informações sobre backup e restauração por etapas, veja [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) e [Restaurações por etapas &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="05b94-104">For more information about piecemeal backup and restore, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [Piecemeal Restores &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span></span>  
  
 <span data-ttu-id="05b94-105">Um grupo de arquivos com otimização de memória deve ser submetido a backup e restaurado junto com um grupo de arquivos primário:</span><span class="sxs-lookup"><span data-stu-id="05b94-105">A memory-optimized filegroup must be backed up and restored together with the primary filegroup:</span></span>  
  
-   <span data-ttu-id="05b94-106">Se você submeter a backup (ou restaurar) o grupo de arquivos primário, especifique o grupo de arquivos com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="05b94-106">If you back up (or restore) the primary filegroup you must specify the memory-optimized filegroup.</span></span>  
  
-   <span data-ttu-id="05b94-107">Se você submeter a backup (ou restaurar) o grupo de arquivos com otimização de memória, especifique o grupo de arquivos primário.</span><span class="sxs-lookup"><span data-stu-id="05b94-107">If you backup (or restore) the memory-optimized filegroup you must specify the primary filegroup.</span></span>  
  
 <span data-ttu-id="05b94-108">Os principais cenários para backup e restauração por etapas são:</span><span class="sxs-lookup"><span data-stu-id="05b94-108">Key scenarios for piecemeal backup and restore are,</span></span>  
  
-   <span data-ttu-id="05b94-109">O backup por etapas permite reduzir o tamanho do backup.</span><span class="sxs-lookup"><span data-stu-id="05b94-109">Piecemeal backup allows you to reduce the size of backup.</span></span> <span data-ttu-id="05b94-110">Alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="05b94-110">Some examples:</span></span>  
  
    -   <span data-ttu-id="05b94-111">Configurar o backup de banco de dados para ocorrer em horas ou dias diferentes para minimizar o impacto sobre a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="05b94-111">Configure the database backup to occur at different times or days to minimize the impact on the workload.</span></span> <span data-ttu-id="05b94-112">Um exemplo é um banco de dados muito grande (maior que 1 TB) em que um backup completo de banco de dados não pode ser concluído no tempo alocado para a manutenção do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05b94-112">One example is a very large database (greater than 1 TB) where a full database backup cannot complete in the time allocated for database maintenance.</span></span> <span data-ttu-id="05b94-113">Nessa situação, você pode usar o backup por etapas para fazer backup do banco de dados inteiro em vários backup por etapas.</span><span class="sxs-lookup"><span data-stu-id="05b94-113">In that situation, you can use piecemeal backup to backup the full database in multiple piecemeal backups.</span></span>  
  
    -   <span data-ttu-id="05b94-114">Se um grupo de arquivos for marcado como somente leitura, ele não exigirá um backup de log de transações após ser marcado como somente leitura.</span><span class="sxs-lookup"><span data-stu-id="05b94-114">If a filegroup is marked read-only, it does not require a transaction log backup after it was marked read-only.</span></span> <span data-ttu-id="05b94-115">Você pode optar por fazer backup do grupo de arquivos apenas uma vez depois de marcá-lo como somente leitura.</span><span class="sxs-lookup"><span data-stu-id="05b94-115">You can choose to back up the filegroup only once after marking it read-only.</span></span>  
  
-   <span data-ttu-id="05b94-116">Restauração por etapas.</span><span class="sxs-lookup"><span data-stu-id="05b94-116">Piecemeal restore.</span></span>  
  
    -   <span data-ttu-id="05b94-117">A meta de uma restauração por etapas é colocar as partes importantes do banco de dados online, sem esperar por todos os dados.</span><span class="sxs-lookup"><span data-stu-id="05b94-117">The goal of a piecemeal restore is to bring the critical parts of database online without waiting for all the data.</span></span> <span data-ttu-id="05b94-118">Por exemplo, se um banco de dados tiver dados particionados, as partições mais antigas serão usadas apenas raramente.</span><span class="sxs-lookup"><span data-stu-id="05b94-118">One example is if a database has partitioned data, such that older partitions are only used rarely.</span></span> <span data-ttu-id="05b94-119">É possível restaurá-los somente conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="05b94-119">You can restore them only on an as-needed basis.</span></span> <span data-ttu-id="05b94-120">O mesmo ocorre com grupos de arquivos que contêm, por exemplo, dados históricos.</span><span class="sxs-lookup"><span data-stu-id="05b94-120">Similar for filegroups that contain, for example, historical data.</span></span>  
  
    -   <span data-ttu-id="05b94-121">Usando o reparo de página, você pode corrigir danos de página, especificamente restaurando a página.</span><span class="sxs-lookup"><span data-stu-id="05b94-121">Using page repair, you can fix page corruption by specifically restoring the page.</span></span> <span data-ttu-id="05b94-122">Para obter mais informações, veja [Restaurar páginas &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="05b94-122">For more information, see [Restore Pages &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span></span>  
  
## <a name="samples"></a><span data-ttu-id="05b94-123">Exemplos</span><span class="sxs-lookup"><span data-stu-id="05b94-123">Samples</span></span>  
 <span data-ttu-id="05b94-124">Os exemplos usam o seguinte esquema:</span><span class="sxs-lookup"><span data-stu-id="05b94-124">The examples use the following schema:</span></span>  
  
```  
CREATE DATABASE imoltp  
ON PRIMARY (name = imoltp_primary1, filename = 'c:\data\imoltp_data1.mdf')  
LOG ON (name = imoltp_log, filename = 'c:\data\imoltp_log.ldf')  
GO  
  
ALTER DATABASE imoltp ADD FILE (name = imoltp_primary2, filename = 'c:\data\imoltp_data2.ndf')  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_secondary  
ALTER DATABASE imoltp ADD FILE (name = imoltp_secondary, filename = 'c:\data\imoltp_secondary.ndf') TO FILEGROUP imoltp_secondary  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_mod CONTAINS MEMORY_OPTIMIZED_DATA   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod1', filename='c:\data\imoltp_mod1') TO FILEGROUP imoltp_mod   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod2', filename='c:\data\imoltp_mod2') TO FILEGROUP imoltp_mod   
GO  
```  
  
### <a name="backup"></a><span data-ttu-id="05b94-125">Backup</span><span class="sxs-lookup"><span data-stu-id="05b94-125">Backup</span></span>  
 <span data-ttu-id="05b94-126">Este exemplo mostra como fazer backup do grupo de arquivos primário e do grupo de arquivos com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="05b94-126">This sample shows how to backup the primary filegroup and the memory-optimized filegroup.</span></span> <span data-ttu-id="05b94-127">Você deve especificar o grupo de arquivos primário e com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="05b94-127">You must specify both primary and memory-optimized filegroup together.</span></span>  
  
```  
backup database imoltp filegroup='primary', filegroup='imoltp_mod' to disk='c:\data\imoltp.dmp' with init  
```  
  
 <span data-ttu-id="05b94-128">O exemplo a seguir mostra que o backup de grupos de arquivos, que não sejam o grupo de arquivos primário e com otimização de memória, funciona de maneira semelhante para os bancos de dados sem tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="05b94-128">The following sample shows that a back up of filegroup(s) other than primary and memory-optimized filegroup works similar to the databases without memory-optimized tables.</span></span> <span data-ttu-id="05b94-129">O comando a seguir faz backup do grupo de arquivos secundário</span><span class="sxs-lookup"><span data-stu-id="05b94-129">The following command backups up the secondary filegroup</span></span>  
  
```  
backup database imoltp filegroup='imoltp_secondary' to disk='c:\data\imoltp_secondary.dmp' with init  
```  
  
### <a name="restore"></a><span data-ttu-id="05b94-130">Restaurar</span><span class="sxs-lookup"><span data-stu-id="05b94-130">Restore</span></span>  
 <span data-ttu-id="05b94-131">O exemplo a seguir mostra como restaurar o grupo de arquivos primário e o grupo de arquivos com otimização de memória juntos.</span><span class="sxs-lookup"><span data-stu-id="05b94-131">The following sample shows how to restore the primary filegroup and memory-optimized filegroup together.</span></span>  
  
```  
restore database imoltp filegroup = 'primary', filegroup = 'imoltp_mod'   
from disk='c:\data\imoltp.dmp' with partial, norecovery  
  
--restore the transaction log  
 RESTORE LOG [imoltp] FROM DISK = N'c:\data\imoltp_log.dmp' WITH  FILE = 1,  NOUNLOAD,  STATS = 10  
GO  
```  
  
 <span data-ttu-id="05b94-132">O próximo exemplo mostra que a restauração de grupos de arquivos, que não sejam o grupo de arquivos primário e com otimização de memória, funciona de maneira semelhante para os bancos de dados sem tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="05b94-132">The next sample shows that restoring filegroup(s) other than the primary and memory-optimized filegroup works similar to the databases without memory-optimized tables</span></span>  
  
```  
RESTORE DATABASE [imoltp] FILE = N'imoltp_secondary'   
FROM  DISK = N'c:\data\imoltp_secondary.dmp' WITH  FILE = 1,  RECOVERY,  NOUNLOAD,  STATS = 10  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="05b94-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05b94-133">See Also</span></span>  
 [<span data-ttu-id="05b94-134">Backup, restauração e recuperação de tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="05b94-134">Backup, Restore, and Recovery of Memory-Optimized Tables</span></span>](../../database-engine/backup-restore-and-recovery-of-memory-optimized-tables.md)  
  
  
