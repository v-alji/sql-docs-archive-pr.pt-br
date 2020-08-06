---
title: Backups de bancos de dados completos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- backups [SQL Server], database
- backing up databases [SQL Server], full backups
- estimating database backup size
- backing up [SQL Server], size of backup
- database backups [SQL Server], full backups
- size [SQL Server], backups
- database backups [SQL Server], about backing up databases
ms.assetid: 4d933d19-8d21-4aa1-8153-d230cb3a3f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ee871b6cabbe6c2b2cb4f444fd1e2d42d711dfbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680495"
---
# <a name="full-database-backups-sql-server"></a><span data-ttu-id="40d18-102">Backups de bancos de dados completos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="40d18-102">Full Database Backups (SQL Server)</span></span>
  <span data-ttu-id="40d18-103">Um backup completo de banco de dados faz o backup de todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="40d18-103">A full database backup backs up the whole database.</span></span> <span data-ttu-id="40d18-104">Isso inclui parte do log de transações de modo que o banco de dados completo possa ser recuperado depois que um backup completo de banco de dados for restaurado.</span><span class="sxs-lookup"><span data-stu-id="40d18-104">This includes part of the transaction log so that the full database can be recovered after a full database backup is restored.</span></span> <span data-ttu-id="40d18-105">Backups completos de banco de dados representam o banco de dados no momento em que o backup foi concluído.</span><span class="sxs-lookup"><span data-stu-id="40d18-105">Full database backups represent the database at the time the backup finished.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="40d18-106">À medida que um banco de dados aumenta, os backups completos de banco de dados levam mais tempo para serem concluídos e exigem mais espaço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="40d18-106">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="40d18-107">Portanto, para um banco de dados grande, convém complementar um backup de banco de dados completo com uma série de *backups de bancos de dados diferenciais*.</span><span class="sxs-lookup"><span data-stu-id="40d18-107">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="40d18-108">Para obter mais informações, veja [Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="40d18-108">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="40d18-109">TRUSTWORTHY é definido como OFF em um backup de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="40d18-109">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="40d18-110">Para obter informações sobre como definir TRUSTWORTHY como ON, veja [Opções do ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="40d18-110">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="40d18-111">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="40d18-111">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="40d18-112">Backups de banco de dados no modelo de recuperação simples</span><span class="sxs-lookup"><span data-stu-id="40d18-112">Database Backups Under the Simple Recovery Model</span></span>](#DbBuRMs)  
  
-   [<span data-ttu-id="40d18-113">Backups de banco de dados no modelo de recuperação completa</span><span class="sxs-lookup"><span data-stu-id="40d18-113">Database Backups Under the Full Recovery Model</span></span>](#DbBuRMf)  
  
-   [<span data-ttu-id="40d18-114">Usar um backup de banco de dados completo para restaurar o banco de dados</span><span class="sxs-lookup"><span data-stu-id="40d18-114">Use a Full Database Backup to Restore the Database</span></span>](#RestoreDbBu)  
  
-   [<span data-ttu-id="40d18-115">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="40d18-115">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="database-backups-under-the-simple-recovery-model"></a><a name="DbBuRMs"></a> <span data-ttu-id="40d18-116">Backups de banco de dados no modelo de recuperação simples</span><span class="sxs-lookup"><span data-stu-id="40d18-116">Database Backups Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="40d18-117">No modelo de recuperação simples, depois de cada backup, o banco de dados fica sujeito à possível perda de trabalho na eventualidade de um desastre.</span><span class="sxs-lookup"><span data-stu-id="40d18-117">Under the simple recovery model, after each backup, the database is exposed to potential work loss if a disaster were to occur.</span></span> <span data-ttu-id="40d18-118">A possibilidade de perda de trabalho aumenta a cada atualização até que o próximo backup seja feito, quando a possibilidade de perda de trabalho retorna a zero, tendo início um novo ciclo de exposição à perda de trabalho.</span><span class="sxs-lookup"><span data-stu-id="40d18-118">The work-loss exposure increases with each update until the next backup, when the work-loss exposure returns to zero and a new cycle of work-loss exposure starts.</span></span> <span data-ttu-id="40d18-119">A possibilidade de perda de trabalho aumenta com o passar do tempo entre os backups.</span><span class="sxs-lookup"><span data-stu-id="40d18-119">Work-loss exposure increases over time between backups.</span></span> <span data-ttu-id="40d18-120">A ilustração a seguir mostra a exposição à perda de trabalho de uma estratégia de backup que usa apenas backups de banco de dados completos.</span><span class="sxs-lookup"><span data-stu-id="40d18-120">The following illustration shows the work-loss exposure for a backup strategy that uses only full database backups.</span></span>  
  
 <span data-ttu-id="40d18-121">![Mostra a exposição da perda de trabalho entre backups de banco de dados](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Mostra a exposição da perda de trabalho entre backups de banco de dados")</span><span class="sxs-lookup"><span data-stu-id="40d18-121">![Shows work-loss exposure between database backups](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Shows work-loss exposure between database backups")</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="40d18-122">Exemplo ([!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="40d18-122">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="40d18-123">O exemplo a seguir mostra como criar um backup de banco de dados completo usando WITH FORMAT para substituir qualquer backup existente e criar um novo conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="40d18-123">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span>  
  
```  
-- Back up the AdventureWorks2012 database to new media set.  
BACKUP DATABASE AdventureWorks2012  
    TO DISK = 'Z:\SQLServerBackups\AdventureWorksSimpleRM.bak'   
    WITH FORMAT;  
GO  
```  
  
##  <a name="database-backups-under-the-full-recovery-model"></a><a name="DbBuRMf"></a> <span data-ttu-id="40d18-124">Backups de banco de dados no modelo de recuperação completa</span><span class="sxs-lookup"><span data-stu-id="40d18-124">Database Backups Under the Full Recovery Model</span></span>  
 <span data-ttu-id="40d18-125">Para bancos de dados que usam recuperação completa e recuperação bulk-logged, os backups de banco de dados são necessários, mas não são suficientes.</span><span class="sxs-lookup"><span data-stu-id="40d18-125">For databases that use full and bulk-logged recovery, database backups are necessary but not sufficient.</span></span> <span data-ttu-id="40d18-126">Os backups de log de transações também são necessários.</span><span class="sxs-lookup"><span data-stu-id="40d18-126">Transaction log backups are also required.</span></span> <span data-ttu-id="40d18-127">A ilustração a seguir mostra a estratégia de backup menos complexa possível no modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="40d18-127">The following illustration shows the least complex backup strategy that is possible under the full recovery model.</span></span>  
  
 <span data-ttu-id="40d18-128">![Séries de backups de bancos de dados e backups de log completos](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Séries de backups de bancos de dados e backups de log completos")</span><span class="sxs-lookup"><span data-stu-id="40d18-128">![Series of full database backups and log backups](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Series of full database backups and log backups")</span></span>  
  
 <span data-ttu-id="40d18-129">Para obter informações sobre como criar backups de logs, veja [Backups do log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="40d18-129">For information about how to create log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="40d18-130">Exemplo ([!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="40d18-130">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="40d18-131">O exemplo a seguir mostra como criar um backup de banco de dados completo usando WITH FORMAT para substituir qualquer backup existente e criar um novo conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="40d18-131">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span> <span data-ttu-id="40d18-132">Assim, o exemplo faz o backup do log de transações.</span><span class="sxs-lookup"><span data-stu-id="40d18-132">Then, the example backs up the transaction log.</span></span> <span data-ttu-id="40d18-133">Em uma situação da vida real, você teria de executar uma série de backups regulares de log.</span><span class="sxs-lookup"><span data-stu-id="40d18-133">In a real-life situation, you would have to perform a series of regular log backups.</span></span> <span data-ttu-id="40d18-134">Para esse exemplo, o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] deve ser definido para usar o modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="40d18-134">For this example, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database is set to use the full recovery model.</span></span>  
  
```  
USE master;  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
GO  
-- Back up the AdventureWorks2012 database to new media set (backup set 1).  
BACKUP DATABASE AdventureWorks2012  
  TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak'   
  WITH FORMAT;  
GO  
--Create a routine log backup (backup set 2).  
BACKUP LOG AdventureWorks2012 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak';  
GO  
```  
  
##  <a name="use-a-full-database-backup-to-restore-the-database"></a><a name="RestoreDbBu"></a> <span data-ttu-id="40d18-135">Usar um backup de banco de dados completo para restaurar o banco de dados</span><span class="sxs-lookup"><span data-stu-id="40d18-135">Use a Full Database Backup to Restore the Database</span></span>  
 <span data-ttu-id="40d18-136">É possível recriar todo o banco de dados de uma só vez, restaurando o banco de dados a partir de um backup completo de banco de dados para qualquer local.</span><span class="sxs-lookup"><span data-stu-id="40d18-136">You can re-create a whole database in one step by restoring the database from a full database backup to any location.</span></span> <span data-ttu-id="40d18-137">Uma parte suficiente do log de transações é incluída no backup para permitir que você recupere o banco de dados até o momento em que o backup foi concluído.</span><span class="sxs-lookup"><span data-stu-id="40d18-137">Enough of the transaction log is included in the backup to let you recover the database to the time when the backup finished.</span></span> <span data-ttu-id="40d18-138">O banco de dados restaurado equivale ao estado do banco de dados original quando o backup de banco de dados é concluído, desconsiderando transações não confirmadas.</span><span class="sxs-lookup"><span data-stu-id="40d18-138">The restored database matches the state of the original database when the database backup finished, minus any uncommitted transactions.</span></span> <span data-ttu-id="40d18-139">No modelo de recuperação completa, você deve restaurar todos os backups de log de transações subsequentes.</span><span class="sxs-lookup"><span data-stu-id="40d18-139">Under the full recovery model, you should then restore all subsequent transaction log backups.</span></span> <span data-ttu-id="40d18-140">Quando o banco de dados é recuperado, as transações não confirmadas são revertidas.</span><span class="sxs-lookup"><span data-stu-id="40d18-140">When the database is recovered, uncommitted transactions are rolled back.</span></span>  
  
 <span data-ttu-id="40d18-141">Para obter mais informações, veja [Restaurações completas de banco de dados &#40;Modelo de recuperação simples#41;](complete-database-restores-simple-recovery-model.md) ou [Restaurações completas de banco de dados &#40;Modelo de recuperação completa#41;](complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="40d18-141">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="40d18-142">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="40d18-142">Related Tasks</span></span>  
 <span data-ttu-id="40d18-143">**Para criar um backup de banco de dados completo**</span><span class="sxs-lookup"><span data-stu-id="40d18-143">**To create a full database backup**</span></span>  
  
-   [<span data-ttu-id="40d18-144">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40d18-144">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   <span data-ttu-id="40d18-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="40d18-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="40d18-146">**Para agendar trabalhos de backup**</span><span class="sxs-lookup"><span data-stu-id="40d18-146">**To schedule backup jobs**</span></span>  
  
 [<span data-ttu-id="40d18-147">Usar o Assistente de Plano de Manutenção</span><span class="sxs-lookup"><span data-stu-id="40d18-147">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="40d18-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="40d18-148">See Also</span></span>  
 <span data-ttu-id="40d18-149">[Fazer backup e restaurar bancos de dados do SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="40d18-149">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="40d18-150">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="40d18-150">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="40d18-151">Backup e restauração de bancos de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="40d18-151">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
  
