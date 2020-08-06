---
title: Restaurações completas de banco de dados (modelo de recuperação completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- complete database restores
- database restores [SQL Server], complete database
- restoring databases [SQL Server], complete database
- restoring [SQL Server], database
- full recovery model [SQL Server], performing restores
- log backups [SQL Server[
ms.assetid: 5b4c471c-b972-498e-aba9-92cf7a0ea881
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea6ec9f196acd0a64a0b785024bd6426cd6a5381
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583671"
---
# <a name="complete-database-restores-full-recovery-model"></a><span data-ttu-id="ec1a0-102">Restaurações completas de banco de dados (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="ec1a0-102">Complete Database Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="ec1a0-103">Em uma restauração completa de banco de dados, a meta é restaurar todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="ec1a0-104">O banco de dados inteiro fica offline durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="ec1a0-105">Antes que qualquer parte do banco de dados possa ficar online, todos os dados são recuperados a um ponto consistente, no qual todas as partes do banco de dados estejam no mesmo momento determinado e não exista nenhuma transação não confirmada.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="ec1a0-106">No modelo de recuperação completa, depois de restaurar seu backup ou backups de dados, você deve restaurar todos os backups de log de transações subsequentes e recuperar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-106">Under the full recovery model, after you restore your data backup or backups, you must restore all subsequent transaction log backups and then recover the database.</span></span> <span data-ttu-id="ec1a0-107">Você pode restaurar um banco de dados a um *ponto de recuperação* específico dentro de um destes backups de log.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-107">You can restore a database to a specific *recovery point* within one of these log backups.</span></span> <span data-ttu-id="ec1a0-108">O ponto de recuperação pode ser uma data e hora específica, uma transação marcada ou um LSN (número de sequência de log).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-108">The recovery point can be a specific date and time, a marked transaction, or a log sequence number (LSN).</span></span>  
  
 <span data-ttu-id="ec1a0-109">Ao restaurar um banco de dados, particularmente com o modelo de recuperação completa ou o modelo de recuperação bulk-logged, você deve usar uma única sequência de restauração.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-109">When restoring a database, particularly under the full recovery model or bulk-logged recovery model, you should use a single restore sequence.</span></span> <span data-ttu-id="ec1a0-110">Uma *sequência de restauração* consiste em uma ou mais operações de restauração que movem dados por uma ou mais etapas da restauração.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-110">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ec1a0-111">Não é recomendável anexar ou restaurar bancos de dados de origem desconhecida ou não confiável.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-111">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="ec1a0-112">Esses bancos de dados podem conter códigos mal-intencionados que podem executar códigos [!INCLUDE[tsql](../../includes/tsql-md.md)] inesperados ou causar erros que modifiquem o esquema ou a estrutura física do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-112">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="ec1a0-113">Antes de usar um banco de dados de origem desconhecida ou não confiável, execute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no banco de dados, em um servidor que não seja de produção. Além disso, examine o código, como procedimentos armazenados ou outro código definido pelo usuário, no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-113">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
 <span data-ttu-id="ec1a0-114">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-114">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="ec1a0-115">Restaurando um banco de dados até o ponto de falha</span><span class="sxs-lookup"><span data-stu-id="ec1a0-115">Restoring a Database to the Point of Failure</span></span>](#PointOfFailure)  
  
-   [<span data-ttu-id="ec1a0-116">Restaurando um banco de dados para um ponto dentro de um backup de log</span><span class="sxs-lookup"><span data-stu-id="ec1a0-116">Restoring a Database to a Point Within a Log Backup</span></span>](#PointWithinBackup)  
  
-   [<span data-ttu-id="ec1a0-117">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ec1a0-117">Related Tasks</span></span>](#RelatedTasks)  
  
> [!NOTE]  
>  <span data-ttu-id="ec1a0-118">Para obter informações sobre suporte para backups de versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], veja a seção “Suporte de compatibilidade” de [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-118">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="restoring-a-database-to-the-point-of-failure"></a><a name="PointOfFailure"></a> <span data-ttu-id="ec1a0-119">Restaurando um banco de dados até o ponto de falha</span><span class="sxs-lookup"><span data-stu-id="ec1a0-119">Restoring a Database to the Point of Failure</span></span>  
 <span data-ttu-id="ec1a0-120">Normalmente, a recuperação de um banco de dados até o ponto da falha envolve as seguintes etapas básicas:</span><span class="sxs-lookup"><span data-stu-id="ec1a0-120">Typically, recovering a database to the point of failure involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="ec1a0-121">Faça um backup do log de transações ativas (conhecido como a parte final do log).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-121">Back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="ec1a0-122">Isso cria um backup do final do log.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-122">This creates a tail-log backup.</span></span> <span data-ttu-id="ec1a0-123">Se o log de transações ativas não estiver disponível, todas as transações naquela parte do log serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-123">If the active transaction log is unavailable, all transactions in that part of the log are lost.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ec1a0-124">No modelo de recuperação bulk-logged, o backup de qualquer log que contenha operações em massa requer acesso a todos os arquivos de dados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-124">Under the bulk-logged recovery model, backing up any log that contains bulk-logged operations requires access to all data files in the database.</span></span> <span data-ttu-id="ec1a0-125">Se os arquivos de dados não puderem ser acessados, não será possível fazer um backup do log de transações.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-125">If the data files cannot be accessed, the transaction log cannot be backed up.</span></span> <span data-ttu-id="ec1a0-126">Nesse caso, você tem de refazer manualmente todas as alterações feitas desde o backup de log mais recente.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-126">In that case, you have to manually redo all changes that were made since the most recent log backup.</span></span>  
  
     <span data-ttu-id="ec1a0-127">Para obter mais informações, veja [Backups da parte final do log &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-127">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="ec1a0-128">Restaure o backup de banco de dados completo mais recente sem recuperar o banco de dados (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-128">Restore the most recent full database backup without recovering the database (RESTORE DATABASE *database_name* FROM *backup_device* WITH NORECOVERY).</span></span>  
  
3.  <span data-ttu-id="ec1a0-129">Se houver backups diferenciais, restaure o mais recente sem recuperar o banco de dados (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-129">If differential backups exist, restore the most recent one without recovering the database (RESTORE DATABASE *database_name* FROM *differential_backup_device* WITH NORECOVERY).</span></span>  
  
     <span data-ttu-id="ec1a0-130">A restauração do backup mais recente diferencial reduz o número de backups de log que devem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-130">Restoring the most recent differential backup reduces the number of log backups that must be restored.</span></span>  
  
4.  <span data-ttu-id="ec1a0-131">Iniciando com o primeiro backup de log de transações criado depois do backup que você acaba de restaurar, restaure os logs em sequência com NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-131">Starting with the first transaction log backup that was created after the backup you just restored, restore the logs in sequence with NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="ec1a0-132">Recupere o banco de dados (RESTORE DATABASE *database_name* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-132">Recover the database (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span> <span data-ttu-id="ec1a0-133">Alternativamente, essa etapa pode ser combinada com a restauração do último backup de log.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-133">Alternatively, this step can be combined with restoring the last log backup.</span></span>  
  
 <span data-ttu-id="ec1a0-134">A ilustração a seguir mostra esta sequência de restauração.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-134">The following illustration shows this restore sequence.</span></span> <span data-ttu-id="ec1a0-135">Depois de uma falha (1), um backup do final do log de final é criado (2).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-135">After a failure occurs (1), a tail-log backup is created (2).</span></span> <span data-ttu-id="ec1a0-136">Em seguida, o banco de dados é restaurado ao ponto da falha.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-136">Next, the database is restored to the point of the failure.</span></span> <span data-ttu-id="ec1a0-137">Isso envolve a restauração de um backup de banco de dados, de um backup diferencial subsequente e de todos os backups de log feitos depois do backup diferencial, inclusive o do backup do final do log.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-137">This involves restoring a database backup, a subsequent differential backup, and every log backup taken after the differential backup, including the tail-log backup.</span></span>  
  
 <span data-ttu-id="ec1a0-138">![Restauração de banco de dados completa no momento da falha](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Restauração de banco de dados completa no momento da falha")</span><span class="sxs-lookup"><span data-stu-id="ec1a0-138">![Complete database restore to the time of a failure](../../database-engine/media/bnrr-rmfull1-db-failure-pt.gif "Complete database restore to the time of a failure")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec1a0-139">Ao restaurar um backup de banco de dados em uma instância de servidor diferente, veja [Copiar bancos de dados com Backup e Restauração](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-139">When you restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="ec1a0-140">Sintaxe básica de RESTORE do Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ec1a0-140">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="ec1a0-141">A sintaxe básica de [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] para a sequência de restauração na ilustração anterior é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="ec1a0-141">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] syntax for the restore sequence in the preceding illustration is as follows:</span></span>  
  
1.  <span data-ttu-id="ec1a0-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-142">RESTORE DATABASE *database* FROM *full database backup* WITH NORECOVERY;</span></span>  
  
2.  <span data-ttu-id="ec1a0-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-143">RESTORE DATABASE *database* FROM *full_differential_backup* WITH NORECOVERY;</span></span>  
  
3.  <span data-ttu-id="ec1a0-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-144">RESTORE LOG *database* FROM *log_backup* WITH NORECOVERY;</span></span>  
  
     <span data-ttu-id="ec1a0-145">Repita essa etapa de log de restauração para cada backup de log adicional.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-145">Repeat this restore-log step for each additional log backup.</span></span>  
  
4.  <span data-ttu-id="ec1a0-146">RESTORE DATABASE *database* WITH RECOVERY;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-146">RESTORE DATABASE *database* WITH RECOVERY;</span></span>  
  
###  <a name="example-recovering-to-the-point-of-failure-transact-sql"></a><a name="ExampleToPoFTsql"></a> <span data-ttu-id="ec1a0-147">Exemplo: Recuperando até o ponto de falha (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ec1a0-147">Example: Recovering to the Point of Failure (Transact-SQL)</span></span>  
 <span data-ttu-id="ec1a0-148">O exemplo a seguir de [!INCLUDE[tsql](../../includes/tsql-md.md)] mostra as opções essenciais em uma sequência de restauração que restaura o banco de dados até o ponto de falha.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-148">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] example shows the essential options in a restore sequence that restores the database to the point of failure.</span></span> <span data-ttu-id="ec1a0-149">O exemplo cria um backup do final do log do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-149">The example creates a tail-log backup of the database.</span></span> <span data-ttu-id="ec1a0-150">Em seguida, o exemplo restaura um backup de banco de dados completo e, depois, restaura o backup do final do log.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-150">Next, the example restores a full database backup and log backup and then restores the tail-log backup.</span></span> <span data-ttu-id="ec1a0-151">O exemplo recupera o banco de dados em uma etapa final, separada.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-151">The example recovers the database in a separate, final step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec1a0-152">Esse exemplo usa um backup de banco de dados e um backup de log criados na seção “Usando backups de bancos de dados no modelo de recuperação completa” em [Backups de bancos de dados completos &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-152">This example uses a database backup and log backup that is created in the "Using Database Backups Under the Full Recovery Model" section in [Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md).</span></span> <span data-ttu-id="ec1a0-153">Antes do backup do banco de dados, o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] foi definido para usar o modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-153">Before the database backup, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database was set to use the full recovery model.</span></span>  
  
```  
USE master;  
--Create tail-log backup.  
BACKUP LOG AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'    
   WITH NORECOVERY;   
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=1,   
    NORECOVERY;  
  
--Restore the regular log backup (from backup set 2).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'   
  WITH FILE=2,   
    NORECOVERY;  
  
--Restore the tail-log backup (from backup set 3).  
RESTORE LOG AdventureWorks2012   
  FROM DISK = 'Z:\SQLServerBackups\AdventureWorksFullRM.bak'  
  WITH FILE=3,   
    NORECOVERY;  
GO  
--recover the database:  
RESTORE DATABASE AdventureWorks2012 WITH RECOVERY;  
GO  
```  
  
##  <a name="restoring-a-database-to-a-point-within-a-log-backup"></a><a name="PointWithinBackup"></a> <span data-ttu-id="ec1a0-154">Restaurando um banco de dados em um ponto em um backup de log</span><span class="sxs-lookup"><span data-stu-id="ec1a0-154">Restoring a Database to a Point Within a Log Backup</span></span>  
 <span data-ttu-id="ec1a0-155">No modelo de recuperação completa, uma restauração de banco de dados completa pode ser recuperada normalmente até um ponto de hora, uma transação marcada ou um LSN dentro de um backup de log.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-155">Under the full recovery model, a complete database restore can usually be recovered to a point of time, a marked transaction, or an LSN within a log backup.</span></span> <span data-ttu-id="ec1a0-156">Porém, no modelo de recuperação bulk-logged, se o backup de log contiver alterações registradas em massa, a recuperação pontual não será possível.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-156">However, under the bulk-logged recovery model, if the log backup contains bulk-logged changes, point-in-time recovery is not possible.</span></span>  
  
### <a name="sample-point-in-time-restore-scenarios"></a><span data-ttu-id="ec1a0-157">Exemplos de cenários de restauração point-in-time</span><span class="sxs-lookup"><span data-stu-id="ec1a0-157">Sample Point-in-Time Restore Scenarios</span></span>  
 <span data-ttu-id="ec1a0-158">O exemplo a seguir pressupõe um sistema de banco de dados crucial para o qual um backup de banco de dados completo é criado diariamente à meia-noite, um backup de banco de dados diferencial é criado a cada hora, de segunda-feira a sábado, e os backups de log de transações são criados a cada 10 minutos ao longo do dia.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-158">The following example assumes a mission-critical database system for which a full database backup is created daily at midnight, a differential database backup is created on the hour, Monday through Saturday, and transaction log backups are created every 10 minutes throughout the day.</span></span> <span data-ttu-id="ec1a0-159">Para restaurar o banco de dados ao estado em que estava às 5h19 da</span><span class="sxs-lookup"><span data-stu-id="ec1a0-159">To restore the database to the state is was in at 5:19 A.M.</span></span> <span data-ttu-id="ec1a0-160">quarta-feira, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ec1a0-160">Wednesday, do the following:</span></span>  
  
1.  <span data-ttu-id="ec1a0-161">Restaure o backup de banco de dados completo criado na terça-feira à meia-noite.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-161">Restore the full database backup that was created Tuesday at midnight.</span></span>  
  
2.  <span data-ttu-id="ec1a0-162">Restaure o backup de banco de dados diferencial criado às 5h</span><span class="sxs-lookup"><span data-stu-id="ec1a0-162">Restore the differential database backup that was created at 5:00 A.M.</span></span> <span data-ttu-id="ec1a0-163">na quarta-feira.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-163">on Wednesday.</span></span>  
  
3.  <span data-ttu-id="ec1a0-164">Aplique o backup de log de transações criado às 5h10</span><span class="sxs-lookup"><span data-stu-id="ec1a0-164">Apply the transaction log backup that was created at 5:10 A.M.</span></span> <span data-ttu-id="ec1a0-165">na quarta-feira.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-165">on Wednesday.</span></span>  
  
4.  <span data-ttu-id="ec1a0-166">Aplique o backup de log de transações criado às 5h20</span><span class="sxs-lookup"><span data-stu-id="ec1a0-166">Apply the transaction log backup that was created 5:20 A.M.</span></span> <span data-ttu-id="ec1a0-167">na quarta-feira, especificando que o processo de recuperação só se aplica a transações que ocorreram antes das 5h19.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-167">on Wednesday, specifying that the recovery process applies only to transactions that occurred before 5:19 A.M.</span></span>  
  
 <span data-ttu-id="ec1a0-168">Ou então, se o banco de dados precisar ser restaurado ao estado em que estava às 3h04 da</span><span class="sxs-lookup"><span data-stu-id="ec1a0-168">Alternatively, if the database needs to be restored to its state at 3:04 A.M.</span></span> <span data-ttu-id="ec1a0-169">quinta-feira, mas o backup de banco de dados diferencial criado às 3h da</span><span class="sxs-lookup"><span data-stu-id="ec1a0-169">Thursday, but the differential database backup that was created at 3:00 A.M.</span></span> <span data-ttu-id="ec1a0-170">quinta-feira não estiver disponível, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ec1a0-170">Thursday is unavailable, do the following:</span></span>  
  
1.  <span data-ttu-id="ec1a0-171">Restaure o backup de banco de dados criado na quarta-feira à meia-noite.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-171">Restore the database backup that was created Wednesday at midnight.</span></span>  
  
2.  <span data-ttu-id="ec1a0-172">Restaure o backup de banco de dados diferencial criado às 2h</span><span class="sxs-lookup"><span data-stu-id="ec1a0-172">Restore the differential database backup that was created at 2:00 A.M.</span></span> <span data-ttu-id="ec1a0-173">na quinta-feira.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-173">on Thursday.</span></span>  
  
3.  <span data-ttu-id="ec1a0-174">Aplique todos os backups de log de transações criados das 2h10</span><span class="sxs-lookup"><span data-stu-id="ec1a0-174">Apply all the transaction log backups created from 2:10 A.M.</span></span> <span data-ttu-id="ec1a0-175">às 3h</span><span class="sxs-lookup"><span data-stu-id="ec1a0-175">to 3:00 A.M.</span></span> <span data-ttu-id="ec1a0-176">na quinta-feira.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-176">on Thursday.</span></span>  
  
4.  <span data-ttu-id="ec1a0-177">Aplique o backup de log de transações criado às 3h10</span><span class="sxs-lookup"><span data-stu-id="ec1a0-177">Apply the transaction log backup that was created at 3:10 A.M.</span></span> <span data-ttu-id="ec1a0-178">na quinta-feira, parando o processo de recuperação às 3h04.</span><span class="sxs-lookup"><span data-stu-id="ec1a0-178">on Thursday, stopping the recovery process at 3:04 A.M.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec1a0-179">Para obter um exemplo de uma restauração pontual, veja [Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="ec1a0-179">For an example of a point-in-time restore, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ec1a0-180">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ec1a0-180">Related Tasks</span></span>  
 <span data-ttu-id="ec1a0-181">**Para restaurar um backup de banco de dados completo**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-181">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="ec1a0-182">Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-182">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="ec1a0-183">Restaurar um banco de dados em um novo local &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-183">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="ec1a0-184">**Para restaurar um backup de banco de dados diferencial**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-184">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="ec1a0-185">Restaurar um backup de banco de dados diferencial &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-185">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="ec1a0-186">**Para restaurar um backup de log de transações**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-186">**To restore a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="ec1a0-187">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-187">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="ec1a0-188">**Para restaurar um backup usando o SQL Server Management Objects (SMO)**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-188">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
 <span data-ttu-id="ec1a0-189">**Para restaurar um banco de dados para um ponto em um backup de log**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-189">**To restore a database to a point within a log backup**</span></span>  
  
-   [<span data-ttu-id="ec1a0-190">Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-190">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="ec1a0-191">Recuperação de bancos de dados relacionados que contêm transação marcada</span><span class="sxs-lookup"><span data-stu-id="ec1a0-191">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="ec1a0-192">Recuperar para um número de sequência de log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-192">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec1a0-193">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec1a0-193">See Also</span></span>  
 <span data-ttu-id="ec1a0-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec1a0-194">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="ec1a0-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec1a0-195">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ec1a0-196">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec1a0-196">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ec1a0-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec1a0-197">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="ec1a0-198">[Backups de bancos de dados completos &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec1a0-198">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ec1a0-199">[Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec1a0-199">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="ec1a0-200">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec1a0-200">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="ec1a0-201">Visão geral de restauração e recuperação &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec1a0-201">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
