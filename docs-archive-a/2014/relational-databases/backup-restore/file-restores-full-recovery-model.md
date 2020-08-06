---
title: Restaurações de arquivos (modelo de recuperação completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- full recovery model [SQL Server], performing restores
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- file restores [SQL Server], full recovery model
- restoring files [SQL Server], full recovery model
- Transact-SQL restore sequence
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: d2236a2a-4cf1-4c3f-b542-f73f6096e15c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 488515ec900867f13d33580402e36a3f98747bb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680497"
---
# <a name="file-restores-full-recovery-model"></a><span data-ttu-id="f5ed9-102">Restaurações de arquivo (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="f5ed9-102">File Restores (Full Recovery Model)</span></span>
  <span data-ttu-id="f5ed9-103">Este tópico é relevante apenas para bancos de dados que contêm vários arquivos ou grupos de arquivos sob o modelo de recuperação completa ou de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-103">This topic is relevant only for databases that contain multiple files or filegroups under the full or bulk-load recovery model.</span></span>  
  
 <span data-ttu-id="f5ed9-104">Em uma restauração de arquivo, a meta é restaurar um ou mais arquivos danificados sem restaurar todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="f5ed9-105">Um cenário de restauração de arquivo consiste em uma única sequência de restauração que copia, efetua roll forward e recupera os dados apropriados</span><span class="sxs-lookup"><span data-stu-id="f5ed9-105">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data</span></span>  
  
 <span data-ttu-id="f5ed9-106">Se o grupo de arquivos que é restaurado for de leitura/gravação, uma cadeia ininterrupta de backups de log deve ser aplicada após o último backup de dados ou diferencial ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-106">If the filegroup that is being restored is read/write, an unbroken chain of log backups must be applied after the last data or differential backup is restored.</span></span> <span data-ttu-id="f5ed9-107">Isso faz com que o grupo de arquivos avance para os registros de log nos registros de log ativos atuais no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-107">This brings the filegroup forward to the log records in the current active log records in the log file.</span></span> <span data-ttu-id="f5ed9-108">O ponto de recuperação está normalmente próximo o término do log, mas não necessariamente.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-108">The recovery point is typically near the end of log, but not necessarily.</span></span>  
  
 <span data-ttu-id="f5ed9-109">Se o grupo de arquivos que está sendo restaurado for somente leitura, normalmente aplicar backups de log será desnecessário e ignorado.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-109">If the filegroup that is being restored is read-only, usually applying log backups is unnecessary and is skipped.</span></span> <span data-ttu-id="f5ed9-110">Se o backup for realizado depois que o arquivo se torne somente leitura, ele será o último backup a restaurar.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-110">If the backup was taken after the file became read-only, that is the last backup to restore.</span></span> <span data-ttu-id="f5ed9-111">Roll-forward para no ponto de destino.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-111">Roll forward stops at the target point.</span></span>  
  
 <span data-ttu-id="f5ed9-112">Os cenários de restauração de arquivo são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f5ed9-112">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="f5ed9-113">Restauração de arquivo offline</span><span class="sxs-lookup"><span data-stu-id="f5ed9-113">Offline file restore</span></span>  
  
     <span data-ttu-id="f5ed9-114">Em uma *restauração de arquivo offline*, o banco de dados fica offline enquanto os arquivos ou grupos de arquivos danificados são restaurados.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-114">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="f5ed9-115">Ao término da sequência de restauração, o banco de dados fica online.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-115">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="f5ed9-116">Todas as edições do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oferecem suporte à restauração de arquivos offline.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-116">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="f5ed9-117">Restauração de arquivo online</span><span class="sxs-lookup"><span data-stu-id="f5ed9-117">Online file restore</span></span>  
  
     <span data-ttu-id="f5ed9-118">Em uma *restauração de arquivo online*, se o banco de dados estiver online no momento da restauração, ele permanecerá online durante a restauração do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-118">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="f5ed9-119">Porém, cada grupo de arquivos no qual um arquivo está sendo restaurado fica offline durante a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-119">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="f5ed9-120">Depois que todos os arquivos de um grupo de arquivos offline são recuperados, o grupo de arquivos é automaticamente colocado online.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-120">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="f5ed9-121">Para obter informações sobre o suporte para restauração de arquivo e de página online, consulte [Recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-121">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="f5ed9-122">Para obter mais informações sobre restaurações online, veja [Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-122">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="f5ed9-123">Se você deseja que o banco de dados esteja offline para uma restauração arquivo, coloque o banco de dados offline antes de iniciar a sequência de restauração executando a seguinte instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options): ALTER DATABASE *database_name* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-123">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  
  
  
##  <a name="restoring-damaged-files-from-file-backups"></a><a name="Overview"></a> <span data-ttu-id="f5ed9-124">Restaurando arquivos danificados de backups de arquivo</span><span class="sxs-lookup"><span data-stu-id="f5ed9-124">Restoring Damaged Files from File Backups</span></span>  
  
1.  <span data-ttu-id="f5ed9-125">Antes de restaurar um ou mais arquivos danificados, tente criar um [backup da parte final do log](tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-125">Before restoring one or more damaged files, attempt to create a [tail-log backup](tail-log-backups-sql-server.md).</span></span>  
  
     <span data-ttu-id="f5ed9-126">Se o log tiver sido danificado e não for possível criar um backup da parte final do log, você deverá restaurar todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-126">If the log has been damaged, a tail-log backup cannot be created, and you must restore the whole database.</span></span>  
  
     <span data-ttu-id="f5ed9-127">Para obter informações sobre como fazer backup de um log de transações, veja [Backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-127">For information about how to back up a transaction log, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f5ed9-128">Para uma restauração de arquivo offline, você deve sempre fazer um backup do final do log antes da restauração do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-128">For an offline file restore, you must always take a tail-log backup before the file restore.</span></span> <span data-ttu-id="f5ed9-129">Para uma restauração de arquivo online, você deve sempre fazer o backup do log após a restauração do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-129">For an online file restore, you must always take the log backup after the file restore.</span></span> <span data-ttu-id="f5ed9-130">Este backup de log é necessário para permitir que o arquivo seja recuperado a um estado consistente com o restante do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-130">This log backup is necessary to allow for the file to be recovered to a state consistent with the rest of the database.</span></span>  
  
2.  <span data-ttu-id="f5ed9-131">Restaure cada arquivo danificado do backup de arquivos mais recente desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-131">Restore each damaged file from the most recent file backup of that file.</span></span>  
  
3.  <span data-ttu-id="f5ed9-132">Restaure o backup de arquivo diferencial mais recente, se houver, para cada arquivo restaurado.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-132">Restore the most recent differential file backup, if any, for each restored file.</span></span>  
  
4.  <span data-ttu-id="f5ed9-133">Restaure backups de log de transações em sequência, iniciando com o backup que inclui o mais antigo dos arquivos restaurados e terminando com o backup do final do log criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-133">Restore transaction log backups in sequence, starting with the backup that covers the oldest of the restored files and ending with the tail-log backup created in step 1.</span></span>  
  
     <span data-ttu-id="f5ed9-134">Você deve restaurar os backups de log de transações que foram criados após os backups de arquivo para trazer o banco de dados a um estado consistente.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-134">You must restore the transaction log backups that were created after the file backups to bring the database to a consistent state.</span></span> <span data-ttu-id="f5ed9-135">Os backups de log de transações podem ser rolados para frente rapidamente, porque somente são aplicadas as mudanças que se aplicam aos arquivos restaurados.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-135">The transaction log backups can be rolled forward quickly, because only the changes that apply to the restored files are applied.</span></span> <span data-ttu-id="f5ed9-136">Restaurar arquivos individuais pode ser melhor que restaurar todo o banco de dados, porque não são copiados arquivos não danificados e rolados para frente.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-136">Restoring individual files can be better than restoring the whole database, because undamaged files are not copied and then rolled forward.</span></span> <span data-ttu-id="f5ed9-137">Porém, a cadeia inteira de backups de log ainda tem que ser lida.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-137">However, the whole chain of log backups still has to be read.</span></span>  
  
5.  <span data-ttu-id="f5ed9-138">Recuperar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-138">Recover the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5ed9-139">Podem ser usados backups de arquivo para restaurar o banco de dados a um ponto anterior no tempo.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-139">File backups can be used to restore the database to an earlier point in time.</span></span> <span data-ttu-id="f5ed9-140">Para fazê-lo, você deve restaurar um conjunto completo de backups de arquivo e então restaurar backups de log de transações em sequência para alcançar um ponto de destino que busca o término do backup de arquivo restaurado mais recente.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-140">To do this, you must restore a complete set of file backups, and then restore transaction log backups in sequence to reach a target point that is after the end of the most recent restored file backup.</span></span> <span data-ttu-id="f5ed9-141">Para obter mais informações sobre a recuperação pontual, veja [Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed9-141">For more information about point-in-time recovery, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
## <a name="transact-sql-restore-sequence-for-an-offline-file-restore-full-recovery-model"></a><span data-ttu-id="f5ed9-142">Sequência de restauração Transact-SQL para uma restauração de arquivo offline (modelo de recuperação completo)</span><span class="sxs-lookup"><span data-stu-id="f5ed9-142">Transact-SQL Restore Sequence for an Offline File Restore (Full Recovery Model)</span></span>  
 <span data-ttu-id="f5ed9-143">Um cenário de restauração de arquivo consiste em uma única sequência de restauração que copia, rola para frente e recupera os dados apropriados.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-143">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data.</span></span>  
  
 <span data-ttu-id="f5ed9-144">Esta seção mostra as opções básicas de [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) para uma sequência de restauração de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-144">This section shows the essential [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a file-restore sequence.</span></span> <span data-ttu-id="f5ed9-145">Sintaxe e detalhes que não sejam relevantes para esse propósito são omitidos.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-145">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="f5ed9-146">A sequência de restauração de exemplo a seguir mostra uma restauração offline de dois arquivos secundários, `A` e `B`, usando WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-146">The following sample restore sequence shows an offline restore of two secondary files, `A` and `B`, using WITH NORECOVERY.</span></span> <span data-ttu-id="f5ed9-147">Em seguida, dois backups de log são aplicados com NORECOVERY, seguido pelo backup do final do log que é restaurado com WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-147">Next, two log backups are applied with NORECOVERY, followed with the tail-log backup, and this is restored using WITH RECOVERY.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5ed9-148">A sequência de restauração de exemplo a seguir começa colocando o arquivo offline e cria um backup do final do log.</span><span class="sxs-lookup"><span data-stu-id="f5ed9-148">The following sample restore sequence starts by taking the file offline and then creates a tail-log backup.</span></span>  
  
```  
--Take the file offline.  
ALTER DATABASE database_name MODIFY FILE SET OFFLINE;  
-- Back up the currently active transaction log.  
BACKUP LOG database_name  
   TO <tail_log_backup>  
   WITH NORECOVERY;  
GO   
-- Restore the files.  
RESTORE DATABASE database_name FILE=name   
   FROM <file_backup_of_file_A>   
   WITH NORECOVERY;  
RESTORE DATABASE database_name FILE=<name> ......  
   FROM <file_backup_of_file_B>   
   WITH NORECOVERY;  
-- Restore the log backups.  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <log_backup>   
   WITH NORECOVERY;  
RESTORE LOG database_name FROM <tail_log_backup>   
   WITH RECOVERY;  
```  
  
## <a name="examples"></a><span data-ttu-id="f5ed9-149">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f5ed9-149">Examples</span></span>  
  
-   [<span data-ttu-id="f5ed9-150">Exemplo: restauração online de um arquivo de leitura/gravação #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="f5ed9-150">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="f5ed9-151">Exemplo: restauração online de um arquivo somente leitura #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="f5ed9-151">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="f5ed9-152">Exemplo: restauração offline do grupo de arquivos primário e mais um &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="f5ed9-152">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f5ed9-153">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="f5ed9-153">Related Tasks</span></span>  
 <span data-ttu-id="f5ed9-154">**Para restaurar arquivos e grupos de arquivos**</span><span class="sxs-lookup"><span data-stu-id="f5ed9-154">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="f5ed9-155">Restaurar arquivos em um novo local &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f5ed9-155">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="f5ed9-156">Restaurar arquivos e grupos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f5ed9-156">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="f5ed9-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="f5ed9-157"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="f5ed9-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f5ed9-158">See Also</span></span>  
 <span data-ttu-id="f5ed9-159">[Backup e Restauração: Interoperabilidade e Coexistência &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5ed9-159">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="f5ed9-160">[Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5ed9-160">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="f5ed9-161">[Backups completos de arquivos &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5ed9-161">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="f5ed9-162">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5ed9-162">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="f5ed9-163">[Visão geral de restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5ed9-163">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="f5ed9-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5ed9-164">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="f5ed9-165">[Restaurações completas de banco de dados &#40;Modelo de recuperação simples#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="f5ed9-165">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="f5ed9-166">Restaurações por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f5ed9-166">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
