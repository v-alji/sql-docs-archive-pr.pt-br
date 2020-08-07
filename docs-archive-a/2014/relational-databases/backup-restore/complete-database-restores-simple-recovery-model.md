---
title: Restaurações completas de banco de dados (modelo de recuperação simples) | Microsoft Docs
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
- simple recovery model [SQL Server]
- restoring [SQL Server], database
ms.assetid: 49828927-1727-4d1d-9ef5-3de43f68c026
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67eee8d7d6f44c9ff83795bf2a8bd612309bf0a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583668"
---
# <a name="complete-database-restores-simple-recovery-model"></a><span data-ttu-id="b5144-102">Restaurações completas de banco de dados (modelo de recuperação simples)</span><span class="sxs-lookup"><span data-stu-id="b5144-102">Complete Database Restores (Simple Recovery Model)</span></span>
  <span data-ttu-id="b5144-103">Em uma restauração completa de banco de dados, a meta é restaurar todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5144-103">In a complete database restore, the goal is to restore the whole database.</span></span> <span data-ttu-id="b5144-104">O banco de dados inteiro fica offline durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="b5144-104">The whole database is offline for the duration of the restore.</span></span> <span data-ttu-id="b5144-105">Antes que qualquer parte do banco de dados possa ficar online, todos os dados são recuperados a um ponto consistente, no qual todas as partes do banco de dados estejam no mesmo momento determinado e não exista nenhuma transação não confirmada.</span><span class="sxs-lookup"><span data-stu-id="b5144-105">Before any part of the database can come online, all data is recovered to a consistent point in which all parts of the database are at the same point in time and no uncommitted transactions exist.</span></span>  
  
 <span data-ttu-id="b5144-106">No modelo de recuperação simples, o banco de dados não poderá ser restaurado para um momento determinado específico durante um backup específico.</span><span class="sxs-lookup"><span data-stu-id="b5144-106">Under the simple recovery model, the database cannot be restored to a specific point in time within a specific backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b5144-107">Não é recomendável anexar ou restaurar bancos de dados de origem desconhecida ou não confiável.</span><span class="sxs-lookup"><span data-stu-id="b5144-107">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="b5144-108">Esses bancos de dados podem conter códigos mal-intencionados que podem executar códigos [!INCLUDE[tsql](../../../includes/tsql-md.md)] inesperados ou causar erros que modifiquem o esquema ou a estrutura física do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5144-108">These databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="b5144-109">Antes de usar um banco de dados de origem desconhecida ou não confiável, execute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no banco de dados, em um servidor que não seja de produção. Além disso, examine o código, como procedimentos armazenados ou outro código definido pelo usuário, no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5144-109">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="b5144-110">Para obter informações sobre suporte para backups de versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], veja a seção “Suporte de compatibilidade” de [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5144-110">For information about support for backups from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the "Compatibility Support" section of [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
##  <a name="overview-of-database-restore-under-the-simple-recovery-model"></a><a name="Overview"></a> <span data-ttu-id="b5144-111">Visão geral da restauração de banco de dados no modelo de recuperação simples</span><span class="sxs-lookup"><span data-stu-id="b5144-111">Overview of Database Restore Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="b5144-112">Uma restauração de banco de dados completa no modelo de recuperação simples envolve uma ou duas instruções [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , dependendo se você deseja restaurar um backup de banco de dados diferencial.</span><span class="sxs-lookup"><span data-stu-id="b5144-112">A full database restore under the simple recovery model involves one or two [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statements, depending on whether you want to restore a differential database backup.</span></span> <span data-ttu-id="b5144-113">Se você estiver usando somente um backup de banco de dados completo, simplesmente restaure o backup mais recente, conforme mostrado na ilustração abaixo.</span><span class="sxs-lookup"><span data-stu-id="b5144-113">If you are using only a full database backup, just restore the most recent backup, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="b5144-114">![Restaurando apenas um backup de banco de dados completo](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restaurando apenas um backup de banco de dados completo")</span><span class="sxs-lookup"><span data-stu-id="b5144-114">![Restoring only a full database backup](../../database-engine/media/bnrr-rmsimple1-fulldbbu.gif "Restoring only a full database backup")</span></span>  
  
 <span data-ttu-id="b5144-115">Se você também estiver usando um backup de banco de dados diferencial, restaure o backup de banco de dados completo mais recente sem recuperar o banco de dados, e em seguida restaure o backup de banco de dados diferencial mais recente e recupere o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b5144-115">If you are also using a differential database backup, restore the most recent full database backup without recovering the database, and then restore the most recent differential database backup and recover the database.</span></span> <span data-ttu-id="b5144-116">A ilustração a seguir mostra este processo.</span><span class="sxs-lookup"><span data-stu-id="b5144-116">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="b5144-117">![Restaurando backups de banco de dados diferenciais e completos](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restaurando backups de banco de dados diferenciais e completos")</span><span class="sxs-lookup"><span data-stu-id="b5144-117">![Restoring full and differential database backups](../../database-engine/media/bnrr-rmsimple2-diffdbbu.gif "Restoring full and differential database backups")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5144-118">Se você pretende restaurar um backup de banco de dados em uma instância de servidor diferente, consulte [Copiar bancos de dados com Backup e Restauração](../databases/copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="b5144-118">If you plan to restore a database backup onto a different server instance, see [Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md).</span></span>  
  
###  <a name="basic-transact-sql-restore-syntax"></a><a name="TsqlSyntax"></a> <span data-ttu-id="b5144-119">Sintaxe básica de RESTORE do Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5144-119">Basic Transact-SQL RESTORE Syntax</span></span>  
 <span data-ttu-id="b5144-120">A sintaxe básica [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) para restaurar um backup de banco de dados completo é:</span><span class="sxs-lookup"><span data-stu-id="b5144-120">The basic [!INCLUDE[tsql](../../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a full database backup is:</span></span>  
  
 <span data-ttu-id="b5144-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span><span class="sxs-lookup"><span data-stu-id="b5144-121">RESTORE DATABASE *database_name* FROM *backup_device* [ WITH NORECOVERY ]</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5144-122">Use WITH NORECOVERY se você também planeja restaurar um backup de banco de dados diferencial.</span><span class="sxs-lookup"><span data-stu-id="b5144-122">Use WITH NORECOVERY if you plan to also restore a differential database backup.</span></span>  
  
 <span data-ttu-id="b5144-123">A sintaxe básica [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) para restaurar um backup de banco de dados é:</span><span class="sxs-lookup"><span data-stu-id="b5144-123">The basic [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for restoring a database backup is:</span></span>  
  
 <span data-ttu-id="b5144-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="b5144-124">RESTORE DATABASE *database_name* FROM *backup_device* WITH RECOVERY</span></span>  
  
###  <a name="example-transact-sql"></a><a name="Example"></a> <span data-ttu-id="b5144-125">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b5144-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="b5144-126">O exemplo a seguir mostra inicialmente como usar a instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql) para criar um backup de banco de dados completo e um backup de banco de dados diferencial do banco de dados do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5144-126">The following example first shows how to use the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to create a full database backup and a differential database backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="b5144-127">O exemplo restaura em seguida estes backups em sequência.</span><span class="sxs-lookup"><span data-stu-id="b5144-127">The example then restores these backups in sequence.</span></span> <span data-ttu-id="b5144-128">O banco de dados é restaurado a seu estado a partir do momento em que o backup de banco de dados diferencial é concluído.</span><span class="sxs-lookup"><span data-stu-id="b5144-128">The database is restored to its state as of the time that the differential database backup finished.</span></span>  
  
 <span data-ttu-id="b5144-129">O exemplo mostra as opções críticas em uma sequência de restauração referentes a um cenário de restauração de banco de dados completa.</span><span class="sxs-lookup"><span data-stu-id="b5144-129">The example shows the critical options in a restore sequence for the complete database restore scenario.</span></span> <span data-ttu-id="b5144-130">Uma *sequência de restauração* consiste em uma ou mais operações de restauração que movem dados por uma ou mais etapas da restauração.</span><span class="sxs-lookup"><span data-stu-id="b5144-130">A *restore sequence* consists of one or more restore operations that move data through one or more of the phases of restore.</span></span> <span data-ttu-id="b5144-131">Sintaxe e detalhes que não sejam relevantes para esse propósito são omitidos.</span><span class="sxs-lookup"><span data-stu-id="b5144-131">Syntax and details that are not relevant to this purpose are omitted.</span></span> <span data-ttu-id="b5144-132">Quando você recupera um banco de dados, nós recomendamos especificar explicitamente a opção RECOVERY para que haja melhor clareza, mesmo que este seja o padrão.</span><span class="sxs-lookup"><span data-stu-id="b5144-132">When you recover a database, we recommend explicitly specifying the RECOVERY option for clarity, even though it is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5144-133">O exemplo inicia com uma instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) que define o modelo de recuperação como `SIMPLE`.</span><span class="sxs-lookup"><span data-stu-id="b5144-133">The example starts with an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement that sets the recovery model to `SIMPLE`.</span></span>  
  
```  
USE master;  
--Make sure the database is using the simple recovery model.  
ALTER DATABASE AdventureWorks2012 SET RECOVERY SIMPLE;  
GO  
-- Back up the full AdventureWorks2012 database.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
  WITH FORMAT;  
GO  
--Create a differential database backup.  
BACKUP DATABASE AdventureWorks2012   
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'  
   WITH DIFFERENTIAL;  
GO  
--Restore the full database backup (from backup set 1).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=1, NORECOVERY;  
--Restore the differential backup (from backup set 2).  
RESTORE DATABASE AdventureWorks2012   
FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak'   
   WITH FILE=2, RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b5144-134">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b5144-134">Related Tasks</span></span>  
 <span data-ttu-id="b5144-135">**Para restaurar um backup de banco de dados completo**</span><span class="sxs-lookup"><span data-stu-id="b5144-135">**To restore a full database backup**</span></span>  
  
-   [<span data-ttu-id="b5144-136">Restaurar um backup de banco de dados no modelo de recuperação simples &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b5144-136">Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md)  
  
-   [<span data-ttu-id="b5144-137">Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b5144-137">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="b5144-138">Restaurar um banco de dados em um novo local &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b5144-138">Restore a Database to a New Location &#40;SQL Server&#41;</span></span>](restore-a-database-to-a-new-location-sql-server.md)  
  
 <span data-ttu-id="b5144-139">**Para restaurar um backup de banco de dados diferencial**</span><span class="sxs-lookup"><span data-stu-id="b5144-139">**To restore a differential database backup**</span></span>  
  
-   [<span data-ttu-id="b5144-140">Restaurar um backup de banco de dados diferencial &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b5144-140">Restore a Differential Database Backup &#40;SQL Server&#41;</span></span>](restore-a-differential-database-backup-sql-server.md)  
  
 <span data-ttu-id="b5144-141">**Para restaurar um backup usando o SQL Server Management Objects (SMO)**</span><span class="sxs-lookup"><span data-stu-id="b5144-141">**To restore a backup by using SQL Server Management Objects (SMO)**</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  

  
## <a name="see-also"></a><span data-ttu-id="b5144-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5144-142">See Also</span></span>  
 <span data-ttu-id="b5144-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b5144-143">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="b5144-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b5144-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="b5144-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b5144-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="b5144-146">[Backups de bancos de dados completos &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5144-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="b5144-147">[Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5144-147">[Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md) </span></span>  
 <span data-ttu-id="b5144-148">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5144-148">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="b5144-149">Visão geral de restauração e recuperação &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b5144-149">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
  
  
