---
title: 'Exemplo: restauração por etapas de apenas alguns grupos de arquivos (modelo de recuperação simples) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], simple recovery model
- restore sequences [SQL Server], piecemeal
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: d7ad026c-5355-4308-9560-0dc843940d4f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8254ac96a269b6fb433759e5a649bf9df1b7feac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685804"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model"></a><span data-ttu-id="c4bb4-102">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos (modelo de recuperação simples)</span><span class="sxs-lookup"><span data-stu-id="c4bb4-102">Example: Piecemeal Restore of Only Some Filegroups (Simple Recovery Model)</span></span>
  <span data-ttu-id="c4bb4-103">Este tópico é pertinente para bancos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sob o modelo de recuperação simples que contenham um grupo de arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span>  
  
 <span data-ttu-id="c4bb4-104">Uma sequência de restauração por etapas restaura e recupera um banco de dados em etapas no nível do grupo de arquivos, começando pelo grupo de arquivos primário e todos os grupos de arquivos secundários de leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="c4bb4-105">Nesse exemplo, um banco de dados nomeado `adb`, que usa o modelo de recuperação simples, contém três grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-105">In this example, a database named `adb`, which uses the simple recovery model, contains three filegroups.</span></span> <span data-ttu-id="c4bb4-106">O grupo de arquivos `A` é de leitura/gravação e os grupos de arquivos `B` e `C` são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="c4bb4-107">Inicialmente, todos os grupos de arquivos estão online.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="c4bb4-108">O grupo de arquivos primário e `B` do banco de dados `adb` parecem estar danificados; então, o administrador de banco de dados decide restaurá-los usando uma sequência de restauração por etapas.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-108">The primary and filegroup `B` of database `adb` appear to be damaged; therefore, the database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="c4bb4-109">Sob o modelo de recuperação simples, todos os grupos de arquivos de leitura/gravação devem ser restaurados do mesmo backup parcial.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-109">Under the simple recovery model, all read/write filegroups must be restored from the same partial backup.</span></span> <span data-ttu-id="c4bb4-110">Embora o grupo de arquivos `A` esteja intacto, deve ser restaurado com o grupo de arquivos primário para ter certeza que eles são consistentes (o banco de dados será restaurado a tempo ao ponto definido ao final do último backup parcial).</span><span class="sxs-lookup"><span data-stu-id="c4bb4-110">Although filegroup `A` is intact, it must be restored with the primary filegroup to make sure that they are consistent (the database will be restored to the point in time defined by the end of the last partial backup).</span></span> <span data-ttu-id="c4bb4-111">Grupo de arquivos `C` está intacto, mas deve ser recuperado para ser colocado online.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-111">Filegroup `C` is intact, but it must be recovered to bring it online.</span></span> <span data-ttu-id="c4bb4-112">Grupo de arquivos `B`, embora danificado, contém dados menos essenciais que o grupo de arquivos `C`; então, `B` será restaurado por último.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-112">Filegroup `B`, although damaged, contains less critical data than Filegroup `C`; therefore, `B` will be restored last.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="c4bb4-113">Sequências da restauração</span><span class="sxs-lookup"><span data-stu-id="c4bb4-113">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4bb4-114">A sintaxe para uma sequência de restauração online é igual à de uma sequência de restauração offline.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-114">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="c4bb4-115">Restauração parcial do grupo de arquivos primário e `A` de um backup parcial.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-115">Partial restore of the primary and filegroup `A` from a partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb READ_WRITE_FILEGROUPS FROM partial_backup   
    WITH PARTIAL, RECOVERY  
    ```  
  
     <span data-ttu-id="c4bb4-116">Neste momento, o grupo de arquivos primário e o grupo de arquivos `A` estão online.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-116">At this point the primary filegroup and filegroup `A` are online.</span></span> <span data-ttu-id="c4bb4-117">Os arquivos nos grupos de arquivos `B` e `C` estão com sua recuperação pendente e os grupos de arquivos estão offline.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-117">Files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
2.  <span data-ttu-id="c4bb4-118">Recuperação online do grupo de arquivos `C`.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-118">Online recovery of filegroup `C`.</span></span>  
  
     <span data-ttu-id="c4bb4-119">Grupo de arquivos `C` é consistente porque o backup parcial que foi restaurado acima foi realizado depois que grupo de arquivos `C` tornou-se somente leitura, embora o banco de dados tenha sido recuperado a tempo pela restauração.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-119">Filegroup `C` is consistent because the partial backup that was restored above was taken after filegroup `C` became read-only, although the database was taken back in time by the restore.</span></span> <span data-ttu-id="c4bb4-120">O administrador de banco de dados recupera o grupo de arquivos `C`, sem restaurá-lo, colocá-lo online.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-120">The database administrator recovers the filegroup `C`, without restoring it, to bring it online.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="c4bb4-121">Neste momento, o grupo de arquivos primário e os grupos de arquivos `A` e `C` estão online.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-121">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="c4bb4-122">Os arquivos no grupo de arquivosB permanecem em recuperação pendente, com o grupo de arquivos offline.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-122">Files in filegroupB remain recovery pending, with the filegroup offline.</span></span>  
  
3.  <span data-ttu-id="c4bb4-123">Restauração online do grupo de arquivos `B.`</span><span class="sxs-lookup"><span data-stu-id="c4bb4-123">Online restore of filegroup `B.`</span></span>  
  
     <span data-ttu-id="c4bb4-124">Arquivos em grupo de arquivos `B` devem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-124">Files in filegroup `B` must be restored.</span></span> <span data-ttu-id="c4bb4-125">O administrador de banco de dados restaura o backup do grupo de arquivos `B` realizado após o grupo de arquivos `B` tornar-se somente leitura e antes do backup parcial.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-125">The database administrator restores the backup of filegroup `B` taken after filegroup `B` became read-only and before the partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup   
    WITH RECOVERY  
    ```  
  
     <span data-ttu-id="c4bb4-126">Todos os grupos de arquivos agora estão online.</span><span class="sxs-lookup"><span data-stu-id="c4bb4-126">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="c4bb4-127">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="c4bb4-127">Additional Examples</span></span>  
  
-   [<span data-ttu-id="c4bb4-128">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="c4bb4-128">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="c4bb4-129">Exemplo: restauração online de um arquivo somente leitura &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="c4bb4-129">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="c4bb4-130">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="c4bb4-130">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="c4bb4-131">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="c4bb4-131">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="c4bb4-132">Exemplo: restauração online de um arquivo de leitura/gravação #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="c4bb4-132">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="c4bb4-133">Exemplo: restauração online de um arquivo somente leitura #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="c4bb4-133">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="c4bb4-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c4bb4-134">See Also</span></span>  
 <span data-ttu-id="c4bb4-135">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c4bb4-135">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="c4bb4-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4bb4-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c4bb4-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4bb4-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="c4bb4-138">Restaurações por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4bb4-138">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
