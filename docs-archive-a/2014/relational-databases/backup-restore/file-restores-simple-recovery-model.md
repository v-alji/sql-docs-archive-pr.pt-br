---
title: Restaurações de arquivos (modelo de recuperação simples) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- file restores [SQL Server]
- simple recovery model [SQL Server]
- restoring files [SQL Server], Transact-SQL restore sequence
- restoring files [SQL Server]
- Transact-SQL restore sequence
- restoring files [SQL Server], simple recovery model
- file restores [SQL Server], simple recovery model
- file restores [SQL Server], Transact-SQL restore sequence
ms.assetid: b6d07386-7c6f-4cc6-be32-93289adbd3d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ed48f48f531e727de5d6e1403ef47f5399f874d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680496"
---
# <a name="file-restores-simple-recovery-model"></a><span data-ttu-id="1beaf-102">Restaurações de arquivos (modelo de recuperação simples)</span><span class="sxs-lookup"><span data-stu-id="1beaf-102">File Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="1beaf-103">Este tópico é relevante apenas para bancos de dados modelo simples que contêm pelo menos um grupo de arquivos secundário somente leitura.</span><span class="sxs-lookup"><span data-stu-id="1beaf-103">This topic is relevant only for simple-model databases that contain at least one read-only secondary filegroup.</span></span>  
  
 <span data-ttu-id="1beaf-104">Em uma restauração de arquivo, a meta é restaurar um ou mais arquivos danificados sem restaurar todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1beaf-104">In a file restore, the goal is to restore one or more damaged files without restoring the whole database.</span></span> <span data-ttu-id="1beaf-105">No modelo de recuperação simples, os backups de arquivo possuem suporte apenas para grupos de arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="1beaf-105">Under the simple recovery model, file backups are supported only for read-only files.</span></span> <span data-ttu-id="1beaf-106">O grupo de arquivos primário e os grupos de arquivos secundários leitura/gravação sempre são restaurados juntos, restaurando um banco de dados ou backup parcial.</span><span class="sxs-lookup"><span data-stu-id="1beaf-106">The primary filegroup and read/write secondary filegroups are always restored together, by restoring a database or partial backup.</span></span>  
  
 <span data-ttu-id="1beaf-107">Os cenários de restauração de arquivo são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="1beaf-107">The file-restore scenarios are as follows:</span></span>  
  
-   <span data-ttu-id="1beaf-108">Restauração de arquivo offline</span><span class="sxs-lookup"><span data-stu-id="1beaf-108">Offline file restore</span></span>  
  
     <span data-ttu-id="1beaf-109">Em uma *restauração de arquivo offline*, o banco de dados fica offline enquanto os arquivos ou grupos de arquivos danificados são restaurados.</span><span class="sxs-lookup"><span data-stu-id="1beaf-109">In an *offline file restore*, the database is offline while damaged files or filegroups are restored.</span></span> <span data-ttu-id="1beaf-110">Ao término da sequência de restauração, o banco de dados fica online.</span><span class="sxs-lookup"><span data-stu-id="1beaf-110">At the end of the restore sequence, the database comes online.</span></span>  
  
     <span data-ttu-id="1beaf-111">Todas as edições do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oferecem suporte à restauração de arquivos offline.</span><span class="sxs-lookup"><span data-stu-id="1beaf-111">All editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support offline file restore.</span></span>  
  
-   <span data-ttu-id="1beaf-112">Restauração de arquivo online</span><span class="sxs-lookup"><span data-stu-id="1beaf-112">Online file restore</span></span>  
  
     <span data-ttu-id="1beaf-113">Em uma *restauração de arquivo online*, se o banco de dados estiver online no momento da restauração, ele permanecerá online durante a restauração do arquivo.</span><span class="sxs-lookup"><span data-stu-id="1beaf-113">In an *online file restore*, if database is online at restore time, it remains online during the file restore.</span></span> <span data-ttu-id="1beaf-114">Porém, cada grupo de arquivos no qual um arquivo está sendo restaurado fica offline durante a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="1beaf-114">However, each filegroup in which a file is being restored is offline during the restore operation.</span></span> <span data-ttu-id="1beaf-115">Depois que todos os arquivos de um grupo de arquivos offline são recuperados, o grupo de arquivos é automaticamente colocado online.</span><span class="sxs-lookup"><span data-stu-id="1beaf-115">After all the files in an offline filegroup are recovered, the filegroup is automatically brought online.</span></span>  
  
     <span data-ttu-id="1beaf-116">Para obter informações sobre o suporte para restauração de arquivo e de página online, consulte [Recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="1beaf-116">For information about support for online page and file restore, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="1beaf-117">Para obter mais informações sobre restaurações online, veja [Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1beaf-117">For more information about online restores, see [Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="1beaf-118">Se você deseja que o banco de dados esteja offline para uma restauração arquivo, coloque o banco de dados offline antes de iniciar a sequência de restauração executando a seguinte instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options): ALTER DATABASE *database_name* SET OFFLINE.</span><span class="sxs-lookup"><span data-stu-id="1beaf-118">If you want the database to be offline for a file restore, take the database offline before you start the restore sequence by executing the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement: ALTER DATABASE *database_name* SET OFFLINE.</span></span>  
  

  
##  <a name="overview-of-file-and-filegroup-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="1beaf-119">Visão geral da restauração de arquivos e grupos de arquivos no modelo de recuperação simples</span><span class="sxs-lookup"><span data-stu-id="1beaf-119">Overview of File and Filegroup Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="1beaf-120">Um cenário de restauração de arquivos consiste em uma única sequência de restauração que copia, efetua roll forward e recupera os dados apropriados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1beaf-120">A file restore scenario consists of a single restore sequence that copies, rolls forward, and recovers the appropriate data as follows:</span></span>  
  
1.  <span data-ttu-id="1beaf-121">Restaure cada arquivo danificado de seu mais recente backup de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1beaf-121">Restore each damaged file from its most recent file backup.</span></span>  
  
2.  <span data-ttu-id="1beaf-122">Restaure o backup de arquivo diferencial mais recente para cada arquivo restaurado e recupere o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1beaf-122">Restore the most recent differential file backup for each restored file and recover the database.</span></span>  
  
### <a name="transact-sql-steps-for-file-restore-sequence-simple-recovery-model"></a><span data-ttu-id="1beaf-123">Etapas do Transact-SQL para a sequência de restauração de arquivos (modelo de recuperação simples)</span><span class="sxs-lookup"><span data-stu-id="1beaf-123">Transact-SQL Steps for File Restore Sequence (Simple Recovery Model)</span></span>  
 <span data-ttu-id="1beaf-124">Esta seção mostra as opções básicas de [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) do [!INCLUDE[tsql](../../../includes/tsql-md.md)] para uma sequência de restauração de arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="1beaf-124">This section shows the essential [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) options for a simple file-restore sequence.</span></span> <span data-ttu-id="1beaf-125">Sintaxe e detalhes que não sejam relevantes para esse propósito são omitidos.</span><span class="sxs-lookup"><span data-stu-id="1beaf-125">Syntax and details that are not relevant to this purpose are omitted.</span></span>  
  
 <span data-ttu-id="1beaf-126">A sequência de restauração contém apenas duas instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1beaf-126">The restore sequence contains only two [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="1beaf-127">A primeira instrução restaura um arquivo secundário, o arquivo `A`, que é restaurado usando WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1beaf-127">The first statement restores a secondary file, file `A`, which is restored using WITH NORECOVERY.</span></span> <span data-ttu-id="1beaf-128">A segunda operação restaura dois outros arquivos, `B` e `C` , que são restaurados usando WITH RECOVERY de um dispositivo de backup diferente:</span><span class="sxs-lookup"><span data-stu-id="1beaf-128">The second operation restores two other files, `B` and `C` which are restored using WITH RECOVERY from a different backup device:</span></span>  
  
1.  <span data-ttu-id="1beaf-129">RESTORE DATABASE *database* FILE **=** _name_of_file_A_</span><span class="sxs-lookup"><span data-stu-id="1beaf-129">RESTORE DATABASE *database* FILE **=**_name_of_file_A_</span></span>  
  
     <span data-ttu-id="1beaf-130">FROM *file_backup_of_file_A*</span><span class="sxs-lookup"><span data-stu-id="1beaf-130">FROM *file_backup_of_file_A*</span></span>  
  
     <span data-ttu-id="1beaf-131">WITH NORECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="1beaf-131">WITH NORECOVERY **;**</span></span>  
  
2.  <span data-ttu-id="1beaf-132">RESTORE DATABASE *database* FILE **=** _name_of_file_B_ **,** _name_of_file_C_</span><span class="sxs-lookup"><span data-stu-id="1beaf-132">RESTORE DATABASE *database* FILE **=**_name_of_file_B_**,**_name_of_file_C_</span></span>  
  
     <span data-ttu-id="1beaf-133">FROM *file_backup_of_files_B_and_C*</span><span class="sxs-lookup"><span data-stu-id="1beaf-133">FROM *file_backup_of_files_B_and_C*</span></span>  
  
     <span data-ttu-id="1beaf-134">WITH RECOVERY **;**</span><span class="sxs-lookup"><span data-stu-id="1beaf-134">WITH RECOVERY **;**</span></span>  
  
### <a name="examples"></a><span data-ttu-id="1beaf-135">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1beaf-135">Examples</span></span>  
  
-   [<span data-ttu-id="1beaf-136">Exemplo: restauração online de um arquivo somente leitura &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="1beaf-136">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="1beaf-137">Exemplo: restauração offline do grupo de arquivos primário e mais um &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="1beaf-137">Example: Offline Restore of Primary and One Other Filegroup &#40;Full Recovery Model&#41;</span></span>](example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model.md)  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1beaf-138">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="1beaf-138">Related Tasks</span></span>  
 <span data-ttu-id="1beaf-139">**Para restaurar arquivos e grupos de arquivos**</span><span class="sxs-lookup"><span data-stu-id="1beaf-139">**To restore files and filegroups**</span></span>  
  
-   [<span data-ttu-id="1beaf-140">Restaurar arquivos e grupos de arquivos sobre arquivos existentes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1beaf-140">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="1beaf-141">Restaurar arquivos e grupos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1beaf-141">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="1beaf-142">Restaurar arquivos e grupos de arquivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1beaf-142">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
-   <span data-ttu-id="1beaf-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="1beaf-143"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="1beaf-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1beaf-144">See Also</span></span>  
 <span data-ttu-id="1beaf-145">[Backup e Restauração: Interoperabilidade e Coexistência &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1beaf-145">[Backup and Restore: Interoperability and Coexistence &#40;SQL Server&#41;](backup-and-restore-interoperability-and-coexistence-sql-server.md) </span></span>  
 <span data-ttu-id="1beaf-146">[Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1beaf-146">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="1beaf-147">[Backups completos de arquivos &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1beaf-147">[Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md) </span></span>  
 <span data-ttu-id="1beaf-148">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1beaf-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="1beaf-149">[Visão geral de restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1beaf-149">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="1beaf-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1beaf-150">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="1beaf-151">[Restaurações completas de banco de dados &#40;Modelo de recuperação simples#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="1beaf-151">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="1beaf-152">Restaurações por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1beaf-152">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
