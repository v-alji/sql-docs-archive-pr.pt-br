---
title: 'Exemplo: restauração por etapas de banco de dados (modelo de recuperação completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- piecemeal restores [SQL Server], full recovery model
- restore sequences [SQL Server], piecemeal
ms.assetid: 0a84892d-2f7a-4e77-b2d0-d68b95595210
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfccccdbdc0c4fb3b189ee0a9fa3aeaf426578b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682303"
---
# <a name="example-piecemeal-restore-of-database-full-recovery-model"></a><span data-ttu-id="24ca8-102">Exemplo: Restauração de banco de dados por etapas (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="24ca8-102">Example: Piecemeal Restore of Database (Full Recovery Model)</span></span>
  <span data-ttu-id="24ca8-103">Uma sequência de restauração por etapas restaura e recupera um banco de dados em etapas no nível do grupo de arquivos, começando pelo grupo de arquivos primário e todos os grupos de arquivo secundários de leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="24ca8-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read-write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="24ca8-104">Nesse exemplo, o banco de dados `adb` é restaurado em um computador novo depois de um desastre.</span><span class="sxs-lookup"><span data-stu-id="24ca8-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="24ca8-105">O banco de dados está usando o modelo de recuperação completa; portanto, antes do início da restauração, um backup do final do log deve ser extraído do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="24ca8-105">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="24ca8-106">Antes do desastre, todos os grupos de arquivos estão online.</span><span class="sxs-lookup"><span data-stu-id="24ca8-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="24ca8-107">O grupo de arquivos `B` é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="24ca8-107">Filegroup `B` is read-only.</span></span> <span data-ttu-id="24ca8-108">Todos os grupos de arquivos secundários precisam ser restaurados, mas são restaurados em ordem de importância: `A` (mais alto), `C`, e por fim `B`.</span><span class="sxs-lookup"><span data-stu-id="24ca8-108">All of the secondary filegroups must be restored, but they are restored in order of importance: `A` (highest), `C`, and lastly `B`.</span></span> <span data-ttu-id="24ca8-109">Nesse exemplo, há quatro backups de log, inclusive o backup do final do log.</span><span class="sxs-lookup"><span data-stu-id="24ca8-109">In this example, there are four log backups, including the tail-log backup.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="24ca8-110">Backup do final do log</span><span class="sxs-lookup"><span data-stu-id="24ca8-110">Tail-Log Backup</span></span>  
 <span data-ttu-id="24ca8-111">Antes de restaurar o banco de dados, o administrador do banco de dados deve fazer backup do final do log.</span><span class="sxs-lookup"><span data-stu-id="24ca8-111">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="24ca8-112">Como o banco de dados está danificado, é preciso usar a opção NO_TRUNCATE para criar o backup do final do log:</span><span class="sxs-lookup"><span data-stu-id="24ca8-112">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="24ca8-113">O backup do final do log é o último backup aplicado nas sequências de restauração a seguir.</span><span class="sxs-lookup"><span data-stu-id="24ca8-113">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="24ca8-114">Sequências da restauração</span><span class="sxs-lookup"><span data-stu-id="24ca8-114">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24ca8-115">A sintaxe para uma sequência de restauração online é igual à de uma sequência de restauração offline.</span><span class="sxs-lookup"><span data-stu-id="24ca8-115">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="24ca8-116">Restauração parcial do grupo de arquivos primário e secundário `A`.</span><span class="sxs-lookup"><span data-stu-id="24ca8-116">Partial restore of the primary and secondary filegroup `A`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
       WITH PARTIAL, NORECOVERY  
    RESTORE DATABASE adb FILEGROUP='A' FROM backup2   
       WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
2.  <span data-ttu-id="24ca8-117">Restauração online do grupo de arquivos `C`.</span><span class="sxs-lookup"><span data-stu-id="24ca8-117">Online restore of filegroup `C`.</span></span>  
  
     <span data-ttu-id="24ca8-118">Neste momento, o grupo de arquivos primário e o grupo de arquivos secundário `A` estão online.</span><span class="sxs-lookup"><span data-stu-id="24ca8-118">At this point, the primary filegroup and secondary filegroup `A` are online.</span></span> <span data-ttu-id="24ca8-119">Todos os arquivos nos grupos de arquivos `B` e `C` estão em recuperação pendente e os grupos de arquivos estão offline.</span><span class="sxs-lookup"><span data-stu-id="24ca8-119">All the files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
     <span data-ttu-id="24ca8-120">Mensagens da última instrução `RESTORE LOG` na etapa 1 indicam que a reversão das transações que envolvem o grupo de arquivos `C` foi adiada, porque o grupo de arquivos não está disponível.</span><span class="sxs-lookup"><span data-stu-id="24ca8-120">Messages from the last `RESTORE LOG` statement in step 1 indicate that rollback of transactions that involve filegroup `C` was deferred, because this filegroup is not available.</span></span> <span data-ttu-id="24ca8-121">As operações regulares podem continuar, mas bloqueios são mantidos por essas transações e o truncamento de log não acontecerá até que a reversão esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="24ca8-121">Regular operations can continue, but locks are held by these transactions and log truncation will not occur until the rollback can complete.</span></span>  
  
     <span data-ttu-id="24ca8-122">Na segunda sequência de restauração, o administrador de banco de dados restaura o grupo de arquivos `C`:</span><span class="sxs-lookup"><span data-stu-id="24ca8-122">In the second restore sequence, the database administrator restores filegroup `C`:</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' FROM backup2a WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="24ca8-123">Neste momento, o grupo de arquivos primário e os grupos de arquivos `A` e `C` estão online.</span><span class="sxs-lookup"><span data-stu-id="24ca8-123">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="24ca8-124">Os arquivos no grupo de arquivos `B` permanecem em recuperação pendente, com o grupo de arquivos offline.</span><span class="sxs-lookup"><span data-stu-id="24ca8-124">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span> <span data-ttu-id="24ca8-125">As transações adiadas foram resolvidas e o truncamento de log acontece.</span><span class="sxs-lookup"><span data-stu-id="24ca8-125">Deferred transactions have been resolved, and log truncation occurs.</span></span>  
  
3.  <span data-ttu-id="24ca8-126">Restauração online do grupo de arquivos `B`.</span><span class="sxs-lookup"><span data-stu-id="24ca8-126">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="24ca8-127">Na terceira sequência de restauração, o administrador de banco de dados restaura o grupo de arquivos `B`.</span><span class="sxs-lookup"><span data-stu-id="24ca8-127">In the third restore sequence, the database administrator restores filegroup `B`.</span></span> <span data-ttu-id="24ca8-128">O backup do grupo de arquivos `B` foi realizado depois de o grupo de arquivos tornar-se somente leitura; portanto, não tem de efetuar roll forward durante a recuperação.</span><span class="sxs-lookup"><span data-stu-id="24ca8-128">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, it does not have to be rolled forward during recovery.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup2b WITH RECOVERY  
    ```  
  
     <span data-ttu-id="24ca8-129">Todos os grupos de arquivos agora estão online.</span><span class="sxs-lookup"><span data-stu-id="24ca8-129">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="24ca8-130">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="24ca8-130">Additional Examples</span></span>  
  
-   [<span data-ttu-id="24ca8-131">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="24ca8-131">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="24ca8-132">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="24ca8-132">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="24ca8-133">Exemplo: restauração online de um arquivo somente leitura &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="24ca8-133">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="24ca8-134">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="24ca8-134">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="24ca8-135">Exemplo: restauração online de um arquivo de leitura/gravação #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="24ca8-135">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="24ca8-136">Exemplo: restauração online de um arquivo somente leitura #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="24ca8-136">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="24ca8-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24ca8-137">See Also</span></span>  
 <span data-ttu-id="24ca8-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="24ca8-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="24ca8-139">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="24ca8-139">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="24ca8-140">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="24ca8-140">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="24ca8-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="24ca8-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="24ca8-142">Restaurações por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="24ca8-142">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
