---
title: Recuperar um banco de dados sem restaurar os dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], recovery-only
- recovery-only scenario [SQL Server]
- restoring databases [SQL Server], recovery-only
- recovery [SQL Server], recovery-only
- database recovery [SQL Server]
- database restores [SQL Server], recovery-only
- recovery [SQL Server], without restoring data
ms.assetid: 7e8fa620-315d-4e10-a718-23fa5171c09e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 04e4f78e51adb803bb65530c0b3b903aa7f76419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581423"
---
# <a name="recover-a-database-without-restoring-data-transact-sql"></a><span data-ttu-id="9cae6-102">Recuperar um banco de dados sem restaurar dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9cae6-102">Recover a Database Without Restoring Data (Transact-SQL)</span></span>
  <span data-ttu-id="9cae6-103">Normalmente, todos os dados em um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são restaurados antes de o banco de dados ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="9cae6-103">Usually, all of the data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is restored before the database is recovered.</span></span> <span data-ttu-id="9cae6-104">Porém, uma operação de restauração pode recuperar um banco de dados sem de fato restaurar um backup; por exemplo, ao recuperar um arquivo somente leitura que seja consistente com o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9cae6-104">However, a restore operation can recover a database without actually restoring a backup; for example, when recovering a read-only file that is consistent with the database.</span></span> <span data-ttu-id="9cae6-105">Isso é chamado de uma *restauração somente recuperação*.</span><span class="sxs-lookup"><span data-stu-id="9cae6-105">This is referred to as a *recovery-only restore*.</span></span> <span data-ttu-id="9cae6-106">Quando dados offline já são consistentes com o banco de dados e só precisam ser disponibilizados, uma operação de restauração somente recuperação conclui a recuperação do banco de dados e coloca os dados online.</span><span class="sxs-lookup"><span data-stu-id="9cae6-106">When offline data is already consistent with the database and needs only to be made available, a recovery-only restore operation completes the recovery of the database and bring the data online.</span></span>  
  
 <span data-ttu-id="9cae6-107">Uma restauração somente recuperação pode ocorrer para um banco de dados inteiro ou para um ou mais arquivos ou grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9cae6-107">A recovery-only restore can occur for a whole database or for one or more a files or filegroups.</span></span>  
  
## <a name="recovery-only-database-restore"></a><span data-ttu-id="9cae6-108">Restauração de banco de dados somente recuperação</span><span class="sxs-lookup"><span data-stu-id="9cae6-108">Recovery-Only Database Restore</span></span>  
 <span data-ttu-id="9cae6-109">Uma restauração somente recuperação de banco de dados pode ser útil nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="9cae6-109">A recovery-only database restore can be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="9cae6-110">Você não recuperou o banco de dados ao restaurar o último backup em uma sequência de restauração, e agora quer recuperar o banco de dados para colocá-lo online.</span><span class="sxs-lookup"><span data-stu-id="9cae6-110">You did not recover the database when restoring the last backup in a restore sequence, and you now want to recover the database to bring it online.</span></span>  
  
-   <span data-ttu-id="9cae6-111">O banco de dados está em modo de espera e você quer atualizá-lo sem aplicar outro backup de log.</span><span class="sxs-lookup"><span data-stu-id="9cae6-111">The database is in standby mode, and you want to make the database updatable without applying another log backup.</span></span>  
  
 <span data-ttu-id="9cae6-112">A sintaxe [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) para a restauração de um banco de dados somente recuperação é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="9cae6-112">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only database restore is as follows:</span></span>  
  
 <span data-ttu-id="9cae6-113">RESTORE DATABASE *database_name* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="9cae6-113">RESTORE DATABASE *database_name* WITH RECOVERY</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9cae6-114">A cláusula FROM **=** \<*backup_device>\* não é usada em restaurações somente recuperação porque nenhum backup é necessário.</span><span class="sxs-lookup"><span data-stu-id="9cae6-114">The FROM **=** \<*backup_device>\* clause is not used for recovery-only restores because no backup is necessary.</span></span>  
  
 <span data-ttu-id="9cae6-115">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="9cae6-115">**Example**</span></span>  
  
 <span data-ttu-id="9cae6-116">O exemplo a seguir recupera o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] de amostra em uma operação de restauração sem restaurar dados.</span><span class="sxs-lookup"><span data-stu-id="9cae6-116">The following example recovers the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in a restore operation without restoring data.</span></span>  
  
```  
-- Restore database using WITH RECOVERY.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY  
```  
  
## <a name="recovery-only-file-restore"></a><span data-ttu-id="9cae6-117">Restauração de arquivo somente recuperação</span><span class="sxs-lookup"><span data-stu-id="9cae6-117">Recovery-Only File Restore</span></span>  
 <span data-ttu-id="9cae6-118">Uma restauração somente recuperação pode ser útil na situação seguinte:</span><span class="sxs-lookup"><span data-stu-id="9cae6-118">A recovery-only file restore can be useful in the following situation:</span></span>  
  
 <span data-ttu-id="9cae6-119">Um banco de dados é restaurado por etapas.</span><span class="sxs-lookup"><span data-stu-id="9cae6-119">A database is restored piecemeal.</span></span> <span data-ttu-id="9cae6-120">Depois da conclusão da restauração do grupo de arquivos primário, um ou mais dos arquivos não restaurados estão consistentes com o novo estado do banco de dados, talvez porque tenham sido somente leitura por algum tempo.</span><span class="sxs-lookup"><span data-stu-id="9cae6-120">After restore of the primary filegroup is complete, one or more of the unrestored files are consistent with the new database state, perhaps because it has been read-only for some time.</span></span> <span data-ttu-id="9cae6-121">Esses arquivos só precisam ser recuperados; a cópia de dados é desnecessária.</span><span class="sxs-lookup"><span data-stu-id="9cae6-121">These files only have to be recovered; data copying is unnecessary.</span></span>  
  
 <span data-ttu-id="9cae6-122">Uma operação de restauração somente recuperação coloca os dados do grupo de arquivos offline online; nenhuma fase de cópia de dados, refazer ou desfazer acontece.</span><span class="sxs-lookup"><span data-stu-id="9cae6-122">A recovery-only restore operation brings the data in the offline filegroup online; no data-copy, redo, or undo phase occurs.</span></span> <span data-ttu-id="9cae6-123">Para obter informações sobre as fases de restauração, confira [Visão geral da restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9cae6-123">For information about the phases of restore, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
 <span data-ttu-id="9cae6-124">A sintaxe [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) para a restauração de um arquivo somente recuperação é:</span><span class="sxs-lookup"><span data-stu-id="9cae6-124">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only file restore is:</span></span>  
  
 <span data-ttu-id="9cae6-125">RESTOre DATABASE *database_name* {File **=** _logical_file_name_ | Grupo de arquivos **=** _logical_filegroup_name_ } [ **,**... *n* ] com recuperação</span><span class="sxs-lookup"><span data-stu-id="9cae6-125">RESTORE DATABASE *database_name* { FILE **=**_logical_file_name_ | FILEGROUP **=**_logical_filegroup_name_ }[ **,**...*n* ] WITH RECOVERY</span></span>  
  
 <span data-ttu-id="9cae6-126">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="9cae6-126">**Example**</span></span>  
  
 <span data-ttu-id="9cae6-127">O exemplo a seguir ilustra uma restauração de arquivos somente recuperação de um grupo de arquivos secundário, `SalesGroup2`, no banco de dados `Sales` .</span><span class="sxs-lookup"><span data-stu-id="9cae6-127">The following example illustrates a recovery-only file restore of the files in a secondary filegroup, `SalesGroup2`, in the `Sales` database.</span></span> <span data-ttu-id="9cae6-128">O grupo de arquivos primário já foi restaurado como a etapa inicial de uma restauração por etapas e `SalesGroup2` está consistente com o grupo de arquivos primário restaurado.</span><span class="sxs-lookup"><span data-stu-id="9cae6-128">The primary filegroup has already been restored as the initial step of a piecemeal restore, and `SalesGroup2` is consistent with the restored primary filegroup.</span></span> <span data-ttu-id="9cae6-129">Recuperar esse grupo de arquivos e colocá-lo online requer somente uma única instrução.</span><span class="sxs-lookup"><span data-stu-id="9cae6-129">Recovering this filegroup and bringing it online requires only a single statement.</span></span>  
  
```  
RESTORE DATABASE Sales FILEGROUP=SalesGroup2 WITH RECOVERY;  
```  
  
## <a name="examples-of-completing-a-piecemeal-restore-scenario-with-a-recovery-only-restore"></a><span data-ttu-id="9cae6-130">Exemplos de conclusão de um cenário de restauração por etapas com uma restauração somente recuperação</span><span class="sxs-lookup"><span data-stu-id="9cae6-130">Examples of Completing a Piecemeal Restore Scenario with a Recovery-Only Restore</span></span>  
 <span data-ttu-id="9cae6-131">**Modelo de recuperação simples**</span><span class="sxs-lookup"><span data-stu-id="9cae6-131">**Simple recovery model**</span></span>  
  
-   [<span data-ttu-id="9cae6-132">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="9cae6-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="9cae6-133">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="9cae6-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
 <span data-ttu-id="9cae6-134">**Modelo de recuperação completa**</span><span class="sxs-lookup"><span data-stu-id="9cae6-134">**Full recovery model**</span></span>  
  
-   [<span data-ttu-id="9cae6-135">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9cae6-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="9cae6-136">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9cae6-136">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
## <a name="see-also"></a><span data-ttu-id="9cae6-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9cae6-137">See Also</span></span>  
 <span data-ttu-id="9cae6-138">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9cae6-138">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="9cae6-139">[Restaurações por etapas &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9cae6-139">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="9cae6-140">[Restaurações de arquivos &#40;Modelo de recuperação simples&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="9cae6-140">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="9cae6-141">[Restaurações de arquivo &#40;Modelo de recuperação completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="9cae6-141">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="9cae6-142">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9cae6-142">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
