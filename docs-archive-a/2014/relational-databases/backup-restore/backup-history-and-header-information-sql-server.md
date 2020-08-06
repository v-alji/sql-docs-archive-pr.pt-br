---
title: Informações de histórico e cabeçalho de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup headers [SQL Server]
- history tables [SQL Server]
- file restores [SQL Server], status information
- backup sets [SQL Server], status information
- listing backed up databases
- status information [SQL Server], backups
- backing up [SQL Server], viewing backup sets
- restoring [SQL Server], history tables
- restoring databases [SQL Server], status information
- backups [SQL Server], status information
- headers [SQL Server]
- media headers [SQL Server]
- backup history tables [SQL Server]
- viewing backup information
- restoring files [SQL Server], viewing backup information
- restoring databases [SQL Server], history tables
- displaying backup information
- restoring files [SQL Server], status information
- historical information [SQL Server], backups
- database restores [SQL Server], history tables
- restore history tables [SQL Server]
- listing backed up files
ms.assetid: 799b9934-0ec2-4f43-960b-5c9653f18374
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ff1e75cc88e51de75af32bcd9d48860be52d5861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686307"
---
# <a name="backup-history-and-header-information-sql-server"></a><span data-ttu-id="3dde0-102">Informações de histórico e cabeçalho de backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3dde0-102">Backup History and Header Information (SQL Server)</span></span>
  <span data-ttu-id="3dde0-103">Um histórico completo de todas as operações de backup e restauração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em uma instância do servidor é armazenado no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="3dde0-103">A complete history of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore operations on a server instance is stored in the **msdb** database.</span></span> <span data-ttu-id="3dde0-104">Este tópico apresenta as tabelas de histórico de backup e restauração e também as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] usadas para acessar o histórico de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-104">This topic introduces the backup and restore history tables and also the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are used to access backup history.</span></span> <span data-ttu-id="3dde0-105">O tópico também discute quando a listagem de banco de dados e de arquivos de log de transação é útil e quando usar informações do cabeçalho de mídia comparado a quando usar informações do cabeçalho de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-105">The topic also discusses when listing database and transaction log files is useful and when to use media-header information compared to when to use backup-header information.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3dde0-106">Para gerenciar o risco de perder alterações recentes no seu histórico de backup e restauração, faça backup do **msdb** com frequência.</span><span class="sxs-lookup"><span data-stu-id="3dde0-106">To manage the risk of losing recent changes to your backup and restore history, back up **msdb** frequently.</span></span> <span data-ttu-id="3dde0-107">Para obter informações sobre de quais bancos de dados do sistema você deve fazer backup, veja [Fazer backup e restaurar bancos de dados do sistema &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3dde0-107">For information about which of the system databases you must back up, see [Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md).</span></span>  
  
 <span data-ttu-id="3dde0-108">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="3dde0-108">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="3dde0-109">Tabelas de histórico de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="3dde0-109">Backup and Restore History Tables</span></span>](#BnRHistoryTables)  
  
-   [<span data-ttu-id="3dde0-110">Instruções Transact-SQL por acessar histórico de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-110">Transact-SQL Statements for Accessing Backup History</span></span>](#TsqlStatementsForBackupHistory)  
  
-   [<span data-ttu-id="3dde0-111">Arquivos de log de transações e de banco de dados</span><span class="sxs-lookup"><span data-stu-id="3dde0-111">Database and Transaction Log Files</span></span>](#ListDbTlogFiles)  
  
-   [<span data-ttu-id="3dde0-112">Informações de cabeçalho de mídia</span><span class="sxs-lookup"><span data-stu-id="3dde0-112">Media-Header Information</span></span>](#MediaHeader)  
  
-   [<span data-ttu-id="3dde0-113">Informações de cabeçalho de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-113">Backup-Header Information</span></span>](#BackupHeader)  
  
-   [<span data-ttu-id="3dde0-114">Comparação de informações do cabeçalho de mídia e do cabeçalho de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-114">Comparison of Media-Header and Backup-Header Information</span></span>](#CompareMediaHeaderBackupHeader)  
  
-   [<span data-ttu-id="3dde0-115">Verificação de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-115">Backup Verification</span></span>](#Verification)  
  
-   [<span data-ttu-id="3dde0-116">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3dde0-116">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="backup-and-restore-history-tables"></a><a name="BnRHistoryTables"></a> <span data-ttu-id="3dde0-117">Tabelas de histórico de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="3dde0-117">Backup and Restore History Tables</span></span>  
 <span data-ttu-id="3dde0-118">Esta seção apresenta as tabelas de histórico que armazenam backup e restauram metadados no banco de dados do sistema **msdb** .</span><span class="sxs-lookup"><span data-stu-id="3dde0-118">This section introduces the history tables that store backup and restore metadata in the **msdb** system database.</span></span>  
  
|<span data-ttu-id="3dde0-119">Tabela de histórico</span><span class="sxs-lookup"><span data-stu-id="3dde0-119">History table</span></span>|<span data-ttu-id="3dde0-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="3dde0-120">Description</span></span>|  
|-------------------|-----------------|  
|[<span data-ttu-id="3dde0-121">backupfile</span><span class="sxs-lookup"><span data-stu-id="3dde0-121">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)|<span data-ttu-id="3dde0-122">Contém uma linha para cada arquivo de dados ou arquivo de log para o qual é feito o backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-122">Contains one row for each data or log file that is backed up.</span></span>|  
|[<span data-ttu-id="3dde0-123">backupfilegroup</span><span class="sxs-lookup"><span data-stu-id="3dde0-123">backupfilegroup</span></span>](/sql/relational-databases/system-tables/backupfilegroup-transact-sql)|<span data-ttu-id="3dde0-124">Contém uma linha para cada grupo de arquivos em um conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-124">Contains a row for each filegroup in a backup set.</span></span>|  
|[<span data-ttu-id="3dde0-125">backupmediafamily</span><span class="sxs-lookup"><span data-stu-id="3dde0-125">backupmediafamily</span></span>](/sql/relational-databases/system-tables/backupmediafamily-transact-sql)|<span data-ttu-id="3dde0-126">Contém uma linha para cada família de mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-126">Contains one row for each media family.</span></span> <span data-ttu-id="3dde0-127">Se uma família de mídia residir em um conjunto de mídias espelhado, a família terá uma linha separada para cada espelho no conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="3dde0-127">If a media family resides in a mirrored media set, the family has a separate row for each mirror in the media set.</span></span>|  
|[<span data-ttu-id="3dde0-128">backupmediaset</span><span class="sxs-lookup"><span data-stu-id="3dde0-128">backupmediaset</span></span>](/sql/relational-databases/system-tables/backupmediaset-transact-sql)|<span data-ttu-id="3dde0-129">Contém uma linha para cada conjunto de mídias de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-129">Contains one row for each backup media set.</span></span>|  
|[<span data-ttu-id="3dde0-130">backupset</span><span class="sxs-lookup"><span data-stu-id="3dde0-130">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)|<span data-ttu-id="3dde0-131">Contém uma linha para cada conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-131">Contains a row for each backup set.</span></span>|  
|[<span data-ttu-id="3dde0-132">restorefile</span><span class="sxs-lookup"><span data-stu-id="3dde0-132">restorefile</span></span>](/sql/relational-databases/system-tables/restorefile-transact-sql)|<span data-ttu-id="3dde0-133">Contém uma linha para cada arquivo restaurado.</span><span class="sxs-lookup"><span data-stu-id="3dde0-133">Contains one row for each restored file.</span></span> <span data-ttu-id="3dde0-134">Isso inclui arquivos restaurados indiretamente por nome de grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3dde0-134">This includes files restored indirectly by filegroup name.</span></span>|  
|[<span data-ttu-id="3dde0-135">restorefilegroup</span><span class="sxs-lookup"><span data-stu-id="3dde0-135">restorefilegroup</span></span>](/sql/relational-databases/system-tables/restorefilegroup-transact-sql)|<span data-ttu-id="3dde0-136">Contém uma linha para cada grupo de arquivos restaurado.</span><span class="sxs-lookup"><span data-stu-id="3dde0-136">Contains one row for each restored filegroup.</span></span>|  
|[<span data-ttu-id="3dde0-137">restorehistory</span><span class="sxs-lookup"><span data-stu-id="3dde0-137">restorehistory</span></span>](/sql/relational-databases/system-tables/restorehistory-transact-sql)|<span data-ttu-id="3dde0-138">Contém uma linha para cada operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="3dde0-138">Contains one row for each restore operation.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="3dde0-139">Quando uma restauração é executada, as tabelas de histórico de backup e restauração são modificadas.</span><span class="sxs-lookup"><span data-stu-id="3dde0-139">When a restore is performed, backup history tables and restore history tables are modified.</span></span>  
  
##  <a name="transact-sql-statements-for-accessing-backup-history"></a><a name="TsqlStatementsForBackupHistory"></a> <span data-ttu-id="3dde0-140">Instruções Transact-SQL por acessar histórico de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-140">Transact-SQL Statements for Accessing Backup History</span></span>  
 <span data-ttu-id="3dde0-141">As instruções de informações de restauração correspondem a informações armazenadas em certas tabelas de histórico de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-141">The restore information statements correspond with information stored in certain backup history tables.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3dde0-142">As instruções Transact-SQL RESTORE FILELISTONLY, RESTORE HEADERONLY, RESTORE LABELONLY e RESTORE VERIFYONLY exigem a permissão CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3dde0-142">The RESTORE FILELISTONLY, RESTORE HEADERONLY, RESTORE LABELONLY, and RESTORE VERIFYONLY Transact-SQL statements require CREATE DATABASE permission.</span></span> <span data-ttu-id="3dde0-143">Com essa exigência, seus arquivos e suas informações de backup estão mais protegidos do que nas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="3dde0-143">This requirement secures your backup files and protects your backup information more fully than in previous versions.</span></span> <span data-ttu-id="3dde0-144">Para obter informações sobre essa permissão, veja [Permissões de banco de dados GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3dde0-144">For information about this permission, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
|<span data-ttu-id="3dde0-145">Instrução de informações</span><span class="sxs-lookup"><span data-stu-id="3dde0-145">Information statement</span></span>|<span data-ttu-id="3dde0-146">Tabela de histórico de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-146">Backup history table</span></span>|<span data-ttu-id="3dde0-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="3dde0-147">Description</span></span>|  
|---------------------------|--------------------------|-----------------|  
|[<span data-ttu-id="3dde0-148">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="3dde0-148">RESTORE FILELISTONLY</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)|[<span data-ttu-id="3dde0-149">backupfile</span><span class="sxs-lookup"><span data-stu-id="3dde0-149">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)|<span data-ttu-id="3dde0-150">Retorna um conjunto de resultados que tem uma lista dos arquivos de log e de banco de dados contidos no backup especificado.</span><span class="sxs-lookup"><span data-stu-id="3dde0-150">Returns a result set that has a list of the database and log files that are contained in the specified backup set.</span></span><br /><br /> <span data-ttu-id="3dde0-151">Para obter mais informações, consulte "Listando arquivos de log de transações e de banco de dados", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3dde0-151">For more information, see "Listing Database and Transaction Log Files," later in this topic.</span></span>|  
|[<span data-ttu-id="3dde0-152">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="3dde0-152">RESTORE HEADERONLY</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)|[<span data-ttu-id="3dde0-153">backupset</span><span class="sxs-lookup"><span data-stu-id="3dde0-153">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)|<span data-ttu-id="3dde0-154">Recupera todas as informações do cabeçalho de backup de todos os conjuntos de backup em um dispositivo de backup particular.</span><span class="sxs-lookup"><span data-stu-id="3dde0-154">Retrieves all the backup header information for all backup sets on a particular backup device.</span></span> <span data-ttu-id="3dde0-155">O resultado de executar RESTORE HEADERONLY é um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="3dde0-155">The result from executing RESTORE HEADERONLY is a result set.</span></span><br /><br /> <span data-ttu-id="3dde0-156">Para obter mais informações, consulte "Exibindo informações do cabeçalho de backup" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3dde0-156">For more information, see "Viewing the Backup-Header Information," later in this topic.</span></span>|  
|[<span data-ttu-id="3dde0-157">RESTORE LABELONLY</span><span class="sxs-lookup"><span data-stu-id="3dde0-157">RESTORE LABELONLY</span></span>](/sql/t-sql/statements/restore-statements-labelonly-transact-sql)|[<span data-ttu-id="3dde0-158">backupmediaset</span><span class="sxs-lookup"><span data-stu-id="3dde0-158">backupmediaset</span></span>](/sql/relational-databases/system-tables/backupmediaset-transact-sql)|<span data-ttu-id="3dde0-159">Retorna um conjunto de resultados que contém informações sobre a mídia de backup em um dispositivo de backup especificado.</span><span class="sxs-lookup"><span data-stu-id="3dde0-159">Returns a result set that contains information about the backup media on a specified backup device.</span></span><br /><br /> <span data-ttu-id="3dde0-160">Para obter mais informações, consulte "Exibindo informações do cabeçalho de mídia" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3dde0-160">For more information, see "Viewing the Media-Header Information," later in this topic.</span></span>|  
  
##  <a name="database-and-transaction-log-files"></a><a name="ListDbTlogFiles"></a> <span data-ttu-id="3dde0-161">Arquivos de log de transações e de banco de dados</span><span class="sxs-lookup"><span data-stu-id="3dde0-161">Database and Transaction Log Files</span></span>  
 <span data-ttu-id="3dde0-162">Informações que são exibidas quando os arquivos de log de transações e de banco de dados são listados em um backup incluem o nome lógico, nome físico, tipo de arquivo (banco de dados ou log), associação de grupo de arquivos, tamanho de arquivo (em bytes), tamanho máximo de arquivo permitido e o tamanho de crescimento de arquivo predefinido (em bytes).</span><span class="sxs-lookup"><span data-stu-id="3dde0-162">Information that is displayed when the database and transaction log files are listed in a backup includes the logical name, physical name, file type (database or log), filegroup membership, file size (in bytes), the maximum allowed file size, and the predefined file growth size (in bytes).</span></span> <span data-ttu-id="3dde0-163">Essas informações são úteis nas seguintes situações, para determinar os nomes dos arquivos em um backup de banco de dados antes de restaurar o backup de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="3dde0-163">This information is useful, in the following situations, to determine the names of the files in a database backup before you restore the database backup:</span></span>  
  
-   <span data-ttu-id="3dde0-164">Você perdeu uma unidade de disco que contém um ou mais dos arquivos de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3dde0-164">You have lost a disk drive that contains one or more of the files for a database.</span></span>  
  
     <span data-ttu-id="3dde0-165">Você pode listar os arquivos no backup de banco de dados para determinar quais arquivos foram afetados, e depois restaurar esses arquivos em uma unidade diferente quando restaurar todo o banco de dados; ou restaurar apenas esses arquivos e aplicar qualquer backup de log de transações criado desde o backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3dde0-165">You can list the files in the database backup to determine which files were affected, and then restore those files onto a different drive when you restore the whole database; or restore just those files and apply any transaction log backups created since the database was backed up.</span></span>  
  
-   <span data-ttu-id="3dde0-166">Você está restaurando um banco de dados de um servidor em outro servidor, mas a estrutura de diretório e o mapeamento de unidade não existe no servidor.</span><span class="sxs-lookup"><span data-stu-id="3dde0-166">You are restoring a database from one server onto another server, but the directory structure and drive mapping does not exist on the server.</span></span>  
  
     <span data-ttu-id="3dde0-167">Listar os arquivos no backup permite que você determine quais arquivos são afetados.</span><span class="sxs-lookup"><span data-stu-id="3dde0-167">Listing the files in the backup let you determine which files are affected.</span></span> <span data-ttu-id="3dde0-168">Por exemplo, o backup contém um arquivo que tem deve ser restaurado na unidade E, mas o servidor de destino não tem uma unidade E. O arquivo deve ser realocado em outro local, por exemplo, na unidade Z, quando o arquivo for restaurado.</span><span class="sxs-lookup"><span data-stu-id="3dde0-168">For example, the backup contains a file that it has to restore to drive E, but the destination server does not have a drive E. The file must be relocated to another location, such as drive Z, when the file is restored.</span></span>  
  
##  <a name="media-header-information"></a><a name="MediaHeader"></a> <span data-ttu-id="3dde0-169">Informações de cabeçalho de mídia</span><span class="sxs-lookup"><span data-stu-id="3dde0-169">Media-Header Information</span></span>  
 <span data-ttu-id="3dde0-170">A exibição do cabeçalho de mídia exibe informações sobre a própria mídia, em vez de informações sobre os backups na mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-170">Viewing the media header displays information about the media itself, instead of about the backups on the media.</span></span> <span data-ttu-id="3dde0-171">As informações do cabeçalho de mídia exibidas incluem nome da mídia, descrição, nome do software que criou o cabeçalho e a data em que o cabeçalho de mídia foi escrito.</span><span class="sxs-lookup"><span data-stu-id="3dde0-171">Media header information that is displayed includes the media name, description, name of the software that created the media header, and the date the media header was written.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3dde0-172">É rápido exibir informações do cabeçalho de mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-172">Viewing the media header is quick.</span></span>  
  
 <span data-ttu-id="3dde0-173">Para obter mais informações, veja [Comparação de informações do cabeçalho de mídia e do cabeçalho de backup](#CompareMediaHeaderBackupHeader), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3dde0-173">For more information, see [Comparison of Media-Header and Backup-Header Information](#CompareMediaHeaderBackupHeader), later in this topic.</span></span>  
  
##  <a name="backup-header-information"></a><a name="BackupHeader"></a> <span data-ttu-id="3dde0-174">Informações de cabeçalho de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-174">Backup-Header Information</span></span>  
 <span data-ttu-id="3dde0-175">A exibição do cabeçalho de backup exibe informações sobre todos os conjuntos de backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e não[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-175">Viewing the backup header displays information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup sets on the media.</span></span> <span data-ttu-id="3dde0-176">As informações exibidas incluem os tipos de dispositivos de backup usados, os tipos de backup (por exemplo, banco de dados, transação, arquivo ou banco de dados diferencial) e informações de data/hora de início e término do backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-176">Information that is displayed includes the types of backup devices that are used, the types of backup (for example, database, transaction, file, or differential database), and backup start and stop date/time information.</span></span> <span data-ttu-id="3dde0-177">Essas informações são úteis quando é necessário determinar qual conjunto de backup deve ser restaurado na fita, ou os backups contidos na mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-177">This information is useful when you have to determine which backup set on the tape to restore, or the backups that are contained on the media.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3dde0-178">A exibição de informações do cabeçalho de backup pode demorar muito tempo para fitas de alta capacidade, porque a mídia toda deve ser percorrida para exibir informações sobre cada backup na mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-178">Viewing backup header information can take a long time for high-capacity tapes, because the whole media must be scanned to display information about each backup on the media.</span></span>  
  
 <span data-ttu-id="3dde0-179">Para obter mais informações, veja [Comparação de informações do cabeçalho de mídia e do cabeçalho de backup](#CompareMediaHeaderBackupHeader), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3dde0-179">For more information, see [Comparison of Media-Header and Backup-Header Information](#CompareMediaHeaderBackupHeader), later in this topic.</span></span>  
  
### <a name="which-backup-set-to-restore"></a><span data-ttu-id="3dde0-180">Conjunto de backup a ser restaurado</span><span class="sxs-lookup"><span data-stu-id="3dde0-180">Which Backup Set to Restore</span></span>  
 <span data-ttu-id="3dde0-181">Você pode usar informações do cabeçalho de backup para identificar qual conjunto de backup deve ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="3dde0-181">You can use information in the backup header to identify which backup set to restore.</span></span> <span data-ttu-id="3dde0-182">O Mecanismo de Banco de Dados numera cada conjunto de backup na mídia de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-182">The Database Engine numbers each backup set on the backup media.</span></span> <span data-ttu-id="3dde0-183">Isso permite a identificação do conjunto de backup que você deve restaurar usando sua posição na mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-183">This lets you identify the backup set you want to restore by using its position on the media.</span></span> <span data-ttu-id="3dde0-184">Por exemplo, a mídia a seguir contêm três conjuntos de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-184">For example, the following media contains three backup sets.</span></span>  
  
 <span data-ttu-id="3dde0-185">![Mídia de backup que contém conjuntos de backup do SQL Server](../../database-engine/media/bnr-media-backup-sets.gif "Mídia de backup que contém conjuntos de backup do SQL Server")</span><span class="sxs-lookup"><span data-stu-id="3dde0-185">![Backup media containing SQL Server backup sets](../../database-engine/media/bnr-media-backup-sets.gif "Backup media containing SQL Server backup sets")</span></span>  
  
 <span data-ttu-id="3dde0-186">Para restaurar um conjunto de backup específico, determine o número da posição do conjunto de backup a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="3dde0-186">To restore a specific backup set, specify the position number of the backup set you want to restore.</span></span> <span data-ttu-id="3dde0-187">Por exemplo, para restaurar o segundo conjunto de backup, especifique 2 como o conjunto de backup a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="3dde0-187">For example, to restore the second backup set, specify 2 as the backup set to restore.</span></span>  
  
##  <a name="comparison-of-media-header-and-backup-header-information"></a><a name="CompareMediaHeaderBackupHeader"></a> <span data-ttu-id="3dde0-188">Comparação de informações do cabeçalho de mídia e do cabeçalho de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-188">Comparison of Media-Header and Backup-Header Information</span></span>  
 <span data-ttu-id="3dde0-189">A ilustração a seguir exemplifica as diferenças entre exibir informações do cabeçalho de backup e do cabeçalho de mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-189">The following illustration provides an example of the differences between viewing backup-header and media-header information.</span></span> <span data-ttu-id="3dde0-190">A obtenção do cabeçalho de mídia requer a recuperação de informações somente do início da fita.</span><span class="sxs-lookup"><span data-stu-id="3dde0-190">Obtaining the media header requires retrieving information from only the start of the tape.</span></span> <span data-ttu-id="3dde0-191">A obtenção do cabeçalho de backup requer a varredura da fita toda para verificar o cabeçalho de todos os conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-191">Obtaining the backup header requires scanning the whole tape to look at the header of every backup set.</span></span>  
  
 <span data-ttu-id="3dde0-192">![Conjunto de mídias que contém três conjuntos de backup do SQL Server](../../database-engine/media/bnr-media-label.gif "Conjunto de mídias que contém três conjuntos de backup do SQL Server")</span><span class="sxs-lookup"><span data-stu-id="3dde0-192">![Media set containing three SQL Server backup sets](../../database-engine/media/bnr-media-label.gif "Media set containing three SQL Server backup sets")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3dde0-193">Quando você usa conjuntos de mídia de várias famílias de mídia, o cabeçalho de mídia e conjunto de backup são registrados em todas as famílias de mídia.</span><span class="sxs-lookup"><span data-stu-id="3dde0-193">When you use media sets that have multiple media families, the media header and backup set are written to all media families.</span></span> <span data-ttu-id="3dde0-194">Portanto, você só precisa fornecer uma única família de mídia para essas operações de relatório.</span><span class="sxs-lookup"><span data-stu-id="3dde0-194">Therefore, you only have to provide a single media family for these reporting operations.</span></span>  
  
 <span data-ttu-id="3dde0-195">Para obter informações sobre como exibir o cabeçalho de mídia, consulte "Exibindo informações do cabeçalho de mídia", anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3dde0-195">For information about how to view the media-header, see "Viewing the Media-Header Information," earlier in this topic.</span></span>  
  
 <span data-ttu-id="3dde0-196">Para obter informações sobre como exibir informações do cabeçalho de backup para todos os conjuntos de backup em um dispositivo de backup, consulte "Exibindo informações do cabeçalho de backup", anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3dde0-196">For information about how to view the backup header information for all backup sets on a backup device, see "Viewing the Backup-Header Information," earlier in this topic.</span></span>  
  
##  <a name="backup-verification"></a><a name="Verification"></a> <span data-ttu-id="3dde0-197">Verificação de backup</span><span class="sxs-lookup"><span data-stu-id="3dde0-197">Backup Verification</span></span>  
 <span data-ttu-id="3dde0-198">Embora não exigido, verificar um backup é uma prática útil.</span><span class="sxs-lookup"><span data-stu-id="3dde0-198">Although not required, verifying a backup is a useful practice.</span></span> <span data-ttu-id="3dde0-199">A verificação de um backup constata se o backup está fisicamente intacto, para assegurar que todos os arquivos no backup estão legíveis e podem ser restaurados, e que você pode restaurar seu backup se precisar dele.</span><span class="sxs-lookup"><span data-stu-id="3dde0-199">Verifying a backup checks that the backup is intact physically, to ensure that all the files in the backup are readable and can be restored, and that you can restore your backup in the event you need to use it.</span></span> <span data-ttu-id="3dde0-200">É importante entender que verificando um backup a estrutura dos dados no backup não é verificada.</span><span class="sxs-lookup"><span data-stu-id="3dde0-200">It is important to understand that verifying a backup does not verify the structure of the data on the backup.</span></span> <span data-ttu-id="3dde0-201">Porém, se o backup foi criado usando WITH CHECKSUMS, verificar o backup usando WITH CHECKSUMS pode fornecer uma boa indicação da confiabilidade dos dados no backup.</span><span class="sxs-lookup"><span data-stu-id="3dde0-201">However, if the backup was created using WITH CHECKSUMS, verifying the backup using WITH CHECKSUMS can provide a good indication of the reliability of the data on the backup.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3dde0-202">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3dde0-202">Related Tasks</span></span>  
 <span data-ttu-id="3dde0-203">**Para excluir linhas antigas das tabelas de histórico de backup e restauração**</span><span class="sxs-lookup"><span data-stu-id="3dde0-203">**To delete old rows from backup and restore history tables**</span></span>  
  
-   [<span data-ttu-id="3dde0-204">sp_delete_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-204">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
 <span data-ttu-id="3dde0-205">**Para excluir todas as linhas de um banco de dados específico das tabelas de histórico de backup e restauração**</span><span class="sxs-lookup"><span data-stu-id="3dde0-205">**To delete all rows for a specific database from backup and restore history tables**</span></span>  
  
-   [<span data-ttu-id="3dde0-206">sp_delete_database_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-206">sp_delete_database_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-database-backuphistory-transact-sql)  
  
 <span data-ttu-id="3dde0-207">**Para exibir os dados e arquivos de log em um conjunto de backup**</span><span class="sxs-lookup"><span data-stu-id="3dde0-207">**To view the data and log files in a backup set**</span></span>  
  
-   [<span data-ttu-id="3dde0-208">RESTORE FILELISTONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-208">RESTORE FILELISTONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)  
  
-   <span data-ttu-id="3dde0-209"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadFileList%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="3dde0-209"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadFileList%2A> (SMO)</span></span>  
  
 <span data-ttu-id="3dde0-210">**Para exibir informações do cabeçalho de mídia**</span><span class="sxs-lookup"><span data-stu-id="3dde0-210">**To view media header information**</span></span>  
  
-   [<span data-ttu-id="3dde0-211">RESTORE LABELONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-211">RESTORE LABELONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-labelonly-transact-sql)  
  
-   [<span data-ttu-id="3dde0-212">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-212">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="3dde0-213">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-213">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   <span data-ttu-id="3dde0-214"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadMediaHeader%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="3dde0-214"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadMediaHeader%2A> (SMO)</span></span>  
  
 <span data-ttu-id="3dde0-215">**Para exibir informações do cabeçalho de backup**</span><span class="sxs-lookup"><span data-stu-id="3dde0-215">**To view backup header information**</span></span>  
  
-   [<span data-ttu-id="3dde0-216">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-216">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="3dde0-217">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-217">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="3dde0-218">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-218">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   <span data-ttu-id="3dde0-219"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadBackupHeader%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="3dde0-219"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadBackupHeader%2A> (SMO)</span></span>  
  
 <span data-ttu-id="3dde0-220">**Para excluir linhas antigas das tabelas de histórico de backup e restauração**</span><span class="sxs-lookup"><span data-stu-id="3dde0-220">**To delete old rows from backup and restore history tables**</span></span>  
  
-   [<span data-ttu-id="3dde0-221">sp_delete_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-221">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
 <span data-ttu-id="3dde0-222">**Para excluir todas as linhas de um banco de dados específico das tabelas de histórico de backup e restauração**</span><span class="sxs-lookup"><span data-stu-id="3dde0-222">**To delete all rows for a specific database from backup and restore history tables**</span></span>  
  
-   [<span data-ttu-id="3dde0-223">sp_delete_database_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-223">sp_delete_database_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-database-backuphistory-transact-sql)  
  
 <span data-ttu-id="3dde0-224">**Para exibir informações do cabeçalho de mídia**</span><span class="sxs-lookup"><span data-stu-id="3dde0-224">**To view media header information**</span></span>  
  
-   [<span data-ttu-id="3dde0-225">RESTORE LABELONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-225">RESTORE LABELONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-labelonly-transact-sql)  
  
-   [<span data-ttu-id="3dde0-226">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-226">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="3dde0-227">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-227">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   <span data-ttu-id="3dde0-228"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadMediaHeader%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="3dde0-228"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadMediaHeader%2A> (SMO)</span></span>  
  
 <span data-ttu-id="3dde0-229">**Para exibir informações do cabeçalho de backup**</span><span class="sxs-lookup"><span data-stu-id="3dde0-229">**To view backup header information**</span></span>  
  
-   [<span data-ttu-id="3dde0-230">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-230">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="3dde0-231">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-231">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="3dde0-232">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-232">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   <span data-ttu-id="3dde0-233"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadBackupHeader%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="3dde0-233"><xref:Microsoft.SqlServer.Management.Smo.Restore.ReadBackupHeader%2A> (SMO)</span></span>  
  
 <span data-ttu-id="3dde0-234">**Para exibir os arquivos em um conjunto de backup**</span><span class="sxs-lookup"><span data-stu-id="3dde0-234">**To view the files in a backup set**</span></span>  
  
-   [<span data-ttu-id="3dde0-235">Exibir os dados e arquivos de log em um conjunto de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-235">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="3dde0-236">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-236">RESTORE HEADERONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
 <span data-ttu-id="3dde0-237">**Para verificar um backup**</span><span class="sxs-lookup"><span data-stu-id="3dde0-237">**To verify a backup**</span></span>  
  
-   [<span data-ttu-id="3dde0-238">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-238">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql)  
  
-   <span data-ttu-id="3dde0-239"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlVerify%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="3dde0-239"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlVerify%2A> (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dde0-240">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3dde0-240">See Also</span></span>  
 <span data-ttu-id="3dde0-241">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3dde0-241">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="3dde0-242">[Conjuntos de mídias, famílias de mídia e conjuntos de backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3dde0-242">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="3dde0-243">[Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3dde0-243">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="3dde0-244">[Conjuntos de mídias de backup espelhadas &#40;SQL Server&#41;](mirrored-backup-media-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3dde0-244">[Mirrored Backup Media Sets &#40;SQL Server&#41;](mirrored-backup-media-sets-sql-server.md) </span></span>  
 [<span data-ttu-id="3dde0-245">Erros de mídia possíveis durante backup e restauração &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3dde0-245">Possible Media Errors During Backup and Restore &#40;SQL Server&#41;</span></span>](possible-media-errors-during-backup-and-restore-sql-server.md)  
  
  
