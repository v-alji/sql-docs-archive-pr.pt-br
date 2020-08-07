---
title: Visão geral de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], backing up data
- backups [SQL Server]
- database backups [SQL Server]
- backup types [SQL Server]
- data backups [SQL Server]
- backing up tables [SQL Server]
- database restores [SQL Server], backups
- backing up [SQL Server], about backing up
- restoring [SQL Server], backup types
- backups [SQL Server], about
- backups [SQL Server], table-level backups unsupported
ms.assetid: 09a6e0c2-d8fd-453f-9aac-4ff24a97dc1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60fbd0341c4e29c6f98cc4d5fe5a2cfabc9b703f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583675"
---
# <a name="backup-overview-sql-server"></a><span data-ttu-id="dae07-102">Backup Overview (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dae07-102">Backup Overview (SQL Server)</span></span>
  <span data-ttu-id="dae07-103">Este tópico apresenta o componente de backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae07-103">This topic introduces the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup component.</span></span> <span data-ttu-id="dae07-104">O backup do banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é essencial para proteger seus dados.</span><span class="sxs-lookup"><span data-stu-id="dae07-104">Backing up your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is essential for protecting your data.</span></span> <span data-ttu-id="dae07-105">Esta discussão abrange tipos de backup e restrições de backup.</span><span class="sxs-lookup"><span data-stu-id="dae07-105">This discussion covers backup types, and backup restrictions.</span></span> <span data-ttu-id="dae07-106">O tópico também apresenta dispositivos de backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e mídia de backup.</span><span class="sxs-lookup"><span data-stu-id="dae07-106">The topic also introduces [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices and backup media.</span></span>  
  
 <span data-ttu-id="dae07-107">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="dae07-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="dae07-108">Componentes e conceitos</span><span class="sxs-lookup"><span data-stu-id="dae07-108">Components and Concepts</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="dae07-109">Compactação de backup</span><span class="sxs-lookup"><span data-stu-id="dae07-109">Backup Compression</span></span>](#BackupCompression)  
  
-   [<span data-ttu-id="dae07-110">Restrições das operações de backup no SQL Server</span><span class="sxs-lookup"><span data-stu-id="dae07-110">Restrictions on Backup Operations in SQL Server</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="dae07-111">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="dae07-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="components-and-concepts"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="dae07-112">Componentes e conceitos</span><span class="sxs-lookup"><span data-stu-id="dae07-112">Components and Concepts</span></span>  
 <span data-ttu-id="dae07-113">fazer backup [verbo]</span><span class="sxs-lookup"><span data-stu-id="dae07-113">back up [verb]</span></span>  
 <span data-ttu-id="dae07-114">Copia os dados ou registros de log de um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou de seu log de transações para um dispositivo de backup, como um disco, a fim de criar um backup de dados ou backup de log.</span><span class="sxs-lookup"><span data-stu-id="dae07-114">Copies the data or log records from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or its transaction log to a backup device, such as a disk, to create a data backup or log backup.</span></span>  
  
 <span data-ttu-id="dae07-115">backup [substantivo]</span><span class="sxs-lookup"><span data-stu-id="dae07-115">backup [noun]</span></span>  
 <span data-ttu-id="dae07-116">Uma cópia dos dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que pode ser usada para restaurar e recuperar os dados após uma falha.</span><span class="sxs-lookup"><span data-stu-id="dae07-116">A copy of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data that can be used to restore and recover the data after a failure.</span></span> <span data-ttu-id="dae07-117">Um backup dos dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é criado no nível de um banco de dados ou de um ou mais de seus arquivos ou grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="dae07-117">A backup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data is created at the level of a database or one or more of its files or filegroups.</span></span> <span data-ttu-id="dae07-118">Não é possível criar backups no nível da tabela.</span><span class="sxs-lookup"><span data-stu-id="dae07-118">Table-level backups cannot be created.</span></span> <span data-ttu-id="dae07-119">Além dos backups de dados, o modelo de recuperação completa requer a criação de backups do log de transações.</span><span class="sxs-lookup"><span data-stu-id="dae07-119">In addition to data backups, the full recovery model requires creating backups of the transaction log.</span></span>  
  
 [<span data-ttu-id="dae07-120">modelo de recuperação</span><span class="sxs-lookup"><span data-stu-id="dae07-120">recovery model</span></span>](recovery-models-sql-server.md)  
 <span data-ttu-id="dae07-121">Uma propriedade de banco de dados que controla a manutenção do log de transações em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dae07-121">A database property that controls transaction log maintenance on a database.</span></span> <span data-ttu-id="dae07-122">Existem três modelos de recuperação: simples, completo e bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="dae07-122">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="dae07-123">O modelo de recuperação de banco de dados determina seus requisitos de backup e de restauração.</span><span class="sxs-lookup"><span data-stu-id="dae07-123">The recovery model of database determines its backup and restore requirements.</span></span>  
  
 [<span data-ttu-id="dae07-124">restaurar</span><span class="sxs-lookup"><span data-stu-id="dae07-124">restore</span></span>](restore-and-recovery-overview-sql-server.md)  
 <span data-ttu-id="dae07-125">Um processo multifase que copia todos os dados e páginas de log de um backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um banco de dados especificado e, em seguida, efetua roll forward de todas as transações registradas no backup, aplicando as alterações registradas para avançar os dados no tempo.</span><span class="sxs-lookup"><span data-stu-id="dae07-125">A multi-phase process that copies all the data and log pages from a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to a specified database, and then rolls forward all the transactions that are logged in the backup by applying logged changes to bring the data forward in time.</span></span>  
  
 <span data-ttu-id="dae07-126">**Tipos de backups**</span><span class="sxs-lookup"><span data-stu-id="dae07-126">**Types of Backups**</span></span>  
  
 [<span data-ttu-id="dae07-127">backup somente cópia</span><span class="sxs-lookup"><span data-stu-id="dae07-127">copy-only backup</span></span>](copy-only-backups-sql-server.md)  
 <span data-ttu-id="dae07-128">Um backup de uso especial que é independente da sequência regular dos backups do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae07-128">A special-use backup that is independent of the regular sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
 <span data-ttu-id="dae07-129">backup de dados</span><span class="sxs-lookup"><span data-stu-id="dae07-129">data backup</span></span>  
 <span data-ttu-id="dae07-130">Um backup de dados em um banco de dados completo (um backup de banco de dados), um banco de dados parcial (um backup parcial) ou um conjunto de arquivos de dados ou grupos de arquivos (um backup de arquivo).</span><span class="sxs-lookup"><span data-stu-id="dae07-130">A backup of data in a complete database (a database backup), a partial database (a partial backup), or a set of data files or filegroups (a file backup).</span></span>  
  
 [<span data-ttu-id="dae07-131">backup de banco de dados</span><span class="sxs-lookup"><span data-stu-id="dae07-131">database backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="dae07-132">Um backup de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dae07-132">A backup of a database.</span></span> <span data-ttu-id="dae07-133">Os backups completos de banco de dados representam todo o banco de dados no momento em que o backup é concluído.</span><span class="sxs-lookup"><span data-stu-id="dae07-133">Full database backups represent the whole database at the time the backup finished.</span></span> <span data-ttu-id="dae07-134">Os backups de banco de dados diferenciais contêm somente alterações feitas no banco de dados desde seu backup completo de banco de dados mais recente.</span><span class="sxs-lookup"><span data-stu-id="dae07-134">Differential database backups contain only changes made to the database since its most recent full database backup.</span></span>  
  
 [<span data-ttu-id="dae07-135">backup diferencial</span><span class="sxs-lookup"><span data-stu-id="dae07-135">differential backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="dae07-136">Um backup de dados que se baseia no backup completo mais recente de um banco de dados completo ou parcial ou um conjunto de arquivos de dados ou grupos de arquivos (a *base diferencial*) que contém somente as extensões de dados alterados desde a base diferencial.</span><span class="sxs-lookup"><span data-stu-id="dae07-136">A data backup that is based on the latest full backup of a complete or partial database or a set of data files or filegroups (the *differential base*) and that contains only the data extents that have changed since the differential base.</span></span>  
  
 <span data-ttu-id="dae07-137">Um backup diferencial parcial registra apenas as extensões de dados que foram alteradas nos grupos de arquivos desde o backup parcial anterior, conhecido como a base para o diferencial.</span><span class="sxs-lookup"><span data-stu-id="dae07-137">A differential partial backup records only the data extents that have changed in the filegroups since the previous partial backup, known as the base for the differential.</span></span>  
  
 <span data-ttu-id="dae07-138">backup completo</span><span class="sxs-lookup"><span data-stu-id="dae07-138">full backup</span></span>  
 <span data-ttu-id="dae07-139">Um backup de dados que contém todos os dados em um banco de dados ou em um conjunto de grupos de arquivos ou arquivos, além de log suficiente para permitir a recuperação desses dados.</span><span class="sxs-lookup"><span data-stu-id="dae07-139">A data backup that contains all the data in a specific database or set of filegroups or files, and also enough log to allow for recovering that data.</span></span>  
  
 [<span data-ttu-id="dae07-140">backup de log</span><span class="sxs-lookup"><span data-stu-id="dae07-140">log backup</span></span>](transaction-log-backups-sql-server.md)  
 <span data-ttu-id="dae07-141">Um backup de logs de transações que inclui todos os registros de log dos quais não foi feito backup em um backup de log anterior.</span><span class="sxs-lookup"><span data-stu-id="dae07-141">A backup of transaction logs that includes all log records that were not backed up in a previous log backup.</span></span> <span data-ttu-id="dae07-142">(modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="dae07-142">(full recovery model)</span></span>  
  
 [<span data-ttu-id="dae07-143">backup de arquivo</span><span class="sxs-lookup"><span data-stu-id="dae07-143">file backup</span></span>](full-file-backups-sql-server.md)  
 <span data-ttu-id="dae07-144">Um backup de um ou mais arquivos ou grupos de arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dae07-144">A backup of one or more database files or filegroups.</span></span>  
  
 [<span data-ttu-id="dae07-145">backup parcial</span><span class="sxs-lookup"><span data-stu-id="dae07-145">partial backup</span></span>](partial-backups-sql-server.md)  
 <span data-ttu-id="dae07-146">Contém dados apenas de alguns grupos de arquivos em um banco de dados, incluindo os dados no grupo de arquivos primário, em cada grupo de arquivos de leitura/gravação e em qualquer arquivo somente leitura especificado opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="dae07-146">Contains data from only some of the filegroups in a database, including the data in the primary filegroup, every read/write filegroup, and any optionally-specified read-only files.</span></span>  
  
 <span data-ttu-id="dae07-147">**Termos e definições de mídia de backup**</span><span class="sxs-lookup"><span data-stu-id="dae07-147">**Backup Media Terms and Definitions**</span></span>  
  
 [<span data-ttu-id="dae07-148">dispositivo de backup</span><span class="sxs-lookup"><span data-stu-id="dae07-148">backup device</span></span>](backup-devices-sql-server.md)  
 <span data-ttu-id="dae07-149">Um disco ou dispositivo de fita no qual são gravados backups do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e nos quais eles podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="dae07-149">A disk or tape device to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups are written and from which they can be restored.</span></span> <span data-ttu-id="dae07-150">Os backups do SQL Server também podem ser gravados em um serviço de Armazenamento de Blobs do Azure. O formato de **URL** é usado para especificar o destino e o nome do arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="dae07-150">SQL Server backups can also be written to an Azure Blob storage service, and **URL** format is used to specify the destination and the name of the backup file..</span></span> <span data-ttu-id="dae07-151">Para obter mais informações, veja [Backup e restauração do SQL Server com o Serviço de Armazenamento de Blob do Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="dae07-151">For more information, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 [<span data-ttu-id="dae07-152">mídia de backup</span><span class="sxs-lookup"><span data-stu-id="dae07-152">backup media</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="dae07-153">Uma ou mais fitas ou arquivos de disco nos quais um ou mais backups foram gravados.</span><span class="sxs-lookup"><span data-stu-id="dae07-153">One or more tapes or disk files to which one or more backup have been written.</span></span>  
  
 [<span data-ttu-id="dae07-154">conjunto de backup</span><span class="sxs-lookup"><span data-stu-id="dae07-154">backup set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="dae07-155">O conteúdo de backup adicionado a um conjunto de mídias por uma operação de backup bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="dae07-155">The backup content that is added to a media set by a successful backup operation.</span></span>  
  
 [<span data-ttu-id="dae07-156">família de mídia</span><span class="sxs-lookup"><span data-stu-id="dae07-156">media family</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="dae07-157">Os backups criados em um único dispositivo não espelhado ou um conjunto de dispositivos espelhados em um conjunto de mídias</span><span class="sxs-lookup"><span data-stu-id="dae07-157">Backups created on a single nonmirrored device or a set of mirrored devices in a media set</span></span>  
  
 [<span data-ttu-id="dae07-158">conjunto de mídias</span><span class="sxs-lookup"><span data-stu-id="dae07-158">media set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="dae07-159">Uma coleção ordenada de mídias de backup, fitas ou arquivos de disco, em que uma ou mais operações de backup foram gravadas, usando um número e um tipo fixo de dispositivos de backup.</span><span class="sxs-lookup"><span data-stu-id="dae07-159">An ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span>  
  
 [<span data-ttu-id="dae07-160">conjunto de mídias espelhado</span><span class="sxs-lookup"><span data-stu-id="dae07-160">mirrored media set</span></span>](mirrored-backup-media-sets-sql-server.md)  
 <span data-ttu-id="dae07-161">Várias cópias (espelhos) de um conjunto de mídias.</span><span class="sxs-lookup"><span data-stu-id="dae07-161">Multiple copies (mirrors) of a media set.</span></span>  
  
##  <a name="backup-compression"></a><a name="BackupCompression"></a><span data-ttu-id="dae07-162">Compactação de backup</span><span class="sxs-lookup"><span data-stu-id="dae07-162">Backup Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="dae07-163">e versões posteriores dão suporte à compactação de backups, e o [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versões posteriores podem restaurar um backup compactado.</span><span class="sxs-lookup"><span data-stu-id="dae07-163">and later versions support compressing backups, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions can restore a compressed backup.</span></span> <span data-ttu-id="dae07-164">Para obter mais informações, veja [Compactação de backup &#40;SQL Server&#41;](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dae07-164">For more information, see [Backup Compression &#40;SQL Server&#41;](backup-compression-sql-server.md).</span></span>  
  
##  <a name="restrictions-on-backup-operations-in-sql-server"></a><a name="Restrictions"></a><span data-ttu-id="dae07-165">Restrições de operações de backup no SQL Server</span><span class="sxs-lookup"><span data-stu-id="dae07-165">Restrictions on Backup Operations in SQL Server</span></span>  
 <span data-ttu-id="dae07-166">O backup pode ser realizado com o banco de dados online e em uso.</span><span class="sxs-lookup"><span data-stu-id="dae07-166">Backup can occur while the database is online and being used.</span></span> <span data-ttu-id="dae07-167">No entanto, existem as seguintes restrições.</span><span class="sxs-lookup"><span data-stu-id="dae07-167">However, the following restrictions exist.</span></span>  
  
### <a name="offline-data-cannot-be-backed-up"></a><span data-ttu-id="dae07-168">Não é possível fazer backup de dados offline</span><span class="sxs-lookup"><span data-stu-id="dae07-168">Offline Data Cannot Be Backed Up</span></span>  
 <span data-ttu-id="dae07-169">Operações de backup que implícita ou explicitamente fizerem referência a dados offline falharão.</span><span class="sxs-lookup"><span data-stu-id="dae07-169">Any backup operation that implicitly or explicitly references data that is offline fails.</span></span> <span data-ttu-id="dae07-170">Alguns exemplos comuns incluem:</span><span class="sxs-lookup"><span data-stu-id="dae07-170">Some typical examples include the following:</span></span>  
  
-   <span data-ttu-id="dae07-171">Você solicita um backup de banco de dados completo, mas um grupo de arquivos do banco de dados está offline.</span><span class="sxs-lookup"><span data-stu-id="dae07-171">You request a full database backup, but one filegroup of the database is offline.</span></span> <span data-ttu-id="dae07-172">Como todos os grupos de arquivos são implicitamente incluídos em um backup de banco de dados completo, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="dae07-172">Because all filegroups are implicitly included in a full database backup, this operation fails.</span></span>  
  
     <span data-ttu-id="dae07-173">Para fazer backup desse banco de dados, você pode usar um backup de arquivo e especificar apenas os grupos de arquivos que estão online.</span><span class="sxs-lookup"><span data-stu-id="dae07-173">To back up this database, you can use a file backup and specify only the filegroups that are online.</span></span>  
  
-   <span data-ttu-id="dae07-174">Você solicita um backup parcial, mas um grupo de arquivos de leitura/gravação está offline.</span><span class="sxs-lookup"><span data-stu-id="dae07-174">You request a partial backup, but a read/write filegroup is offline.</span></span> <span data-ttu-id="dae07-175">Como todos os grupos de arquivos de leitura/gravação são requeridos para um backup parcial, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="dae07-175">Because all read/write filegroups are required for a partial backup, the operation fails.</span></span>  
  
-   <span data-ttu-id="dae07-176">Você solicita um backup de arquivo de arquivos específicos, mas um dos arquivos não está online.</span><span class="sxs-lookup"><span data-stu-id="dae07-176">You request a file backup of specific files, but one of the files is not online.</span></span> <span data-ttu-id="dae07-177">A operação falhará.</span><span class="sxs-lookup"><span data-stu-id="dae07-177">The operation fails.</span></span> <span data-ttu-id="dae07-178">Para fazer backup dos arquivos online, você pode omitir o arquivo offline da lista de arquivos e repetir a operação.</span><span class="sxs-lookup"><span data-stu-id="dae07-178">To back up the online files, you can omit the offline file from the file list and repeat the operation.</span></span>  
  
 <span data-ttu-id="dae07-179">Normalmente, um backup de log será realizado com êxito mesmo se um ou mais arquivos de dados estiverem indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="dae07-179">Typically, a log backup succeeds even if one or more data files are unavailable.</span></span> <span data-ttu-id="dae07-180">Entretanto, se algum arquivo contiver alterações bulk-logged feitas sob o modelo de recuperação bulk-logged, todos os arquivos devem estar online para a realização do backup.</span><span class="sxs-lookup"><span data-stu-id="dae07-180">However, if any file contains bulk-logged changes made under the bulk-logged recovery model, all the files must be online for the backup to succeed.</span></span>  
  
### <a name="concurrency-restrictions-during-backup"></a><span data-ttu-id="dae07-181">Restrições de simultaneidade durante o backup</span><span class="sxs-lookup"><span data-stu-id="dae07-181">Concurrency Restrictions During Backup</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dae07-182">usa um processo de backup online para permitir que um backup de banco de dados seja feito com o banco de dados em uso.</span><span class="sxs-lookup"><span data-stu-id="dae07-182">uses an online backup process to allow for a database backup while the database is still being used.</span></span> <span data-ttu-id="dae07-183">Durante um backup, a maior parte das operações é possível. Por exemplo, instruções INSERT, UPDATE ou DELETE são permitidas durante uma operação de backup</span><span class="sxs-lookup"><span data-stu-id="dae07-183">During a backup, most operations are possible; for example, INSERT, UPDATE, or DELETE statements are allowed during a backup operation.</span></span> <span data-ttu-id="dae07-184">Contudo, se você tentar iniciar uma operação de backup enquanto um arquivo do banco de dados estiver sendo criado ou excluído, a operação de backup aguardará até a conclusão dessa operação ou até o tempo limite do backup.</span><span class="sxs-lookup"><span data-stu-id="dae07-184">However, if you try to start a backup operation while a database file is being created or deleted, the backup operation waits until the create or delete operation is finished or the backup times out.</span></span>  
  
 <span data-ttu-id="dae07-185">Operações que não podem ser executadas durante um backup de banco de dados ou de log de transações incluem:</span><span class="sxs-lookup"><span data-stu-id="dae07-185">Operations that cannot run during a database backup or transaction log backup include the following:</span></span>  
  
-   <span data-ttu-id="dae07-186">Operações de gerenciamento de arquivos, como a instrução ALTER DATABASE com as opções ADD FILE ou REMOVE FILE.</span><span class="sxs-lookup"><span data-stu-id="dae07-186">File-management operations such as the ALTER DATABASE statement with either the ADD FILE or REMOVE FILE options.</span></span>  
  
-   <span data-ttu-id="dae07-187">Operações de redução do banco de dados ou de arquivos.</span><span class="sxs-lookup"><span data-stu-id="dae07-187">Shrink database or shrink file operations.</span></span> <span data-ttu-id="dae07-188">Isso inclui operações de redução automática.</span><span class="sxs-lookup"><span data-stu-id="dae07-188">This includes auto-shrink operations.</span></span>  
  
-   <span data-ttu-id="dae07-189">Se você tentar criar ou excluir um arquivo de banco de dados enquanto houver uma operação de backup em andamento, a operação de criação ou exclusão falhará.</span><span class="sxs-lookup"><span data-stu-id="dae07-189">If you try to create or delete a database file while a backup operation is in progress, the create or delete operation fails.</span></span>  
  
 <span data-ttu-id="dae07-190">Se uma operação de backup for sobreposta por uma operação de gerenciamento de arquivos ou de redução, ocorrerá um conflito.</span><span class="sxs-lookup"><span data-stu-id="dae07-190">If a backup operation overlaps with a file-management operation or shrink operation, a conflict occurs.</span></span> <span data-ttu-id="dae07-191">Independentemente de qual operação conflitante começou primeiro, a segunda operação aguardará até que o bloqueio definido para a primeira operação seja esgotado. (O tempo limite é controlado por uma configuração de tempo limite da sessão.) Se o bloqueio for liberado durante o período de tempo limite, a segunda operação continuará.</span><span class="sxs-lookup"><span data-stu-id="dae07-191">Regardless of which of the conflicting operation began first, the second operation waits for the lock set by the first operation to time out. (The time-out period is controlled by a session time-out setting.) If the lock is released during the time-out period, the second operation continues.</span></span> <span data-ttu-id="dae07-192">Se o tempo limite do bloqueio for esgotado, a segunda operação falhará.</span><span class="sxs-lookup"><span data-stu-id="dae07-192">If the lock times out, the second operation fails.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="dae07-193">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="dae07-193">Related Tasks</span></span>  
 <span data-ttu-id="dae07-194">**Para trabalhar com dispositivos de backup e mídias de backup**</span><span class="sxs-lookup"><span data-stu-id="dae07-194">**To work with backup devices and backup media**</span></span>  
  
-   [<span data-ttu-id="dae07-195">Definir um dispositivo de backup lógico para um arquivo de disco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-195">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="dae07-196">Definir um dispositivo de backup lógico para uma unidade de fita &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-196">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="dae07-197">Especificar um disco ou fita como destino de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-197">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="dae07-198">Excluir um dispositivo de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-198">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="dae07-199">Definir a data de validade em um backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-199">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="dae07-200">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-200">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="dae07-201">Exibir os dados e arquivos de log em um conjunto de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-201">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="dae07-202">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-202">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="dae07-203">Restaurar um backup de um dispositivo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-203">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
-   [<span data-ttu-id="dae07-204">Tutorial: Backup e restauração do SQL Server no serviço de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="dae07-204">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
 <span data-ttu-id="dae07-205">**Para criar um backup**</span><span class="sxs-lookup"><span data-stu-id="dae07-205">**To create a backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dae07-206">Para backups parciais ou somente cópia, use a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) com a opção PARTIAL ou COPY_ONLY, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="dae07-206">For partial or copy-only backups, you must use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement with the PARTIAL or COPY_ONLY option, respectively.</span></span>  
  
-   [<span data-ttu-id="dae07-207">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-207">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="dae07-208">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-208">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="dae07-209">Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-209">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="dae07-210">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-210">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="dae07-211">Fazer backup do log de transações quando o banco de dados está danificado &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-211">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
-   [<span data-ttu-id="dae07-212">Habilitar ou desabilitar as somas de verificação de backup durante backup ou restauração &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-212">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
-   [<span data-ttu-id="dae07-213">Especificar se uma operação de backup ou restauração continua ou é interrompida após um erro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-213">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
-   [<span data-ttu-id="dae07-214">Usar o Resource Governor para limitar o uso de CPU por meio de compactação de backup &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-214">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="dae07-215">Tutorial: Backup e restauração do SQL Server no serviço de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="dae07-215">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="dae07-216">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dae07-216">See Also</span></span>  
 <span data-ttu-id="dae07-217">[Fazer backup e restaurar bancos de dados do SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="dae07-217">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="dae07-218">[Visão geral de restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dae07-218">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="dae07-219">[Planos de manutenção](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="dae07-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 <span data-ttu-id="dae07-220">[O log de transações &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dae07-220">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="dae07-221">Modelos de recuperação &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dae07-221">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
