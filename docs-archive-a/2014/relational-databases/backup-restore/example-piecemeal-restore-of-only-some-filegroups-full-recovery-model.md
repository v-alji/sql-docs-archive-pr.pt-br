---
title: 'Exemplo: restauração por etapas de apenas alguns grupos de arquivos (modelo de recuperação completa) | Microsoft Docs'
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
ms.assetid: bced4b54-e819-472b-b784-c72e14e72a0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b3cb1a5ea33a5016c99fdf1f5a7f4e892c045b59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685805"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-full-recovery-model"></a><span data-ttu-id="55d48-102">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="55d48-102">Example: Piecemeal Restore of Only Some Filegroups (Full Recovery Model)</span></span>
  <span data-ttu-id="55d48-103">Este tópico é relevante para bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sob o modelo de recuperação completa que contém vários arquivos ou grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="55d48-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="55d48-104">Uma sequência de restauração por etapas restaura e recupera um banco de dados em etapas no nível do grupo de arquivos, começando pelo grupo de arquivos primários e todos os grupos de arquivos secundários de leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="55d48-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="55d48-105">Neste exemplo, um banco de dados nomeado `adb`, que usa o modelo de recuperação completa, contém três grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="55d48-105">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="55d48-106">O grupo de arquivos `A` é de leitura/gravação e os grupos de arquivos `B` e `C` são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="55d48-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="55d48-107">Inicialmente, todos os grupos de arquivos estão online.</span><span class="sxs-lookup"><span data-stu-id="55d48-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="55d48-108">O primário e grupo de arquivos `B` do banco de dados `adb` parecem estar danificados.</span><span class="sxs-lookup"><span data-stu-id="55d48-108">The primary and filegroup `B` of database `adb` appear to be damaged.</span></span> <span data-ttu-id="55d48-109">O grupo de arquivos primário é bastante pequeno e pode ser restaurado rapidamente.</span><span class="sxs-lookup"><span data-stu-id="55d48-109">The primary filegroup is fairly small and can be restored quickly.</span></span> <span data-ttu-id="55d48-110">O administrador do banco de dados decide restaurá-los usando a seguinte sequência de restauração por etapas:</span><span class="sxs-lookup"><span data-stu-id="55d48-110">The database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="55d48-111">Primeiro, o grupo de arquivos primário e os logs de transações subsequentes são restaurados e o banco de dados é recuperado.</span><span class="sxs-lookup"><span data-stu-id="55d48-111">First, the primary filegroup and the subsequent transaction logs are restored the database is recovered.</span></span>  
  
 <span data-ttu-id="55d48-112">Os grupos de arquivos intactos `A` e `C` contêm dados críticos.</span><span class="sxs-lookup"><span data-stu-id="55d48-112">The intact filegroups `A` and `C` contain critical data.</span></span> <span data-ttu-id="55d48-113">Portanto, eles serão recuperados a seguir para colocá-los online o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="55d48-113">Therefore, they will be recovered next to bring them online as quickly as possible.</span></span> <span data-ttu-id="55d48-114">Finalmente, o grupo de arquivos secundário danificado, `B`, é restaurado e recuperado.</span><span class="sxs-lookup"><span data-stu-id="55d48-114">Finally, the damaged secondary filegroup, `B`, is restored and recovered.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="55d48-115">Sequências de restauração:</span><span class="sxs-lookup"><span data-stu-id="55d48-115">Restore Sequences:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55d48-116">A sintaxe para uma sequência de restauração online é igual à de uma sequência de restauração offline.</span><span class="sxs-lookup"><span data-stu-id="55d48-116">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="55d48-117">Crie um backup do final do log do banco de dados `adb`.</span><span class="sxs-lookup"><span data-stu-id="55d48-117">Create a tail log backup of database `adb`.</span></span> <span data-ttu-id="55d48-118">Essa etapa é essencial para deixar os grupos de arquivos intactos `A` e `C` em dia com o ponto de recuperação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55d48-118">This step is essential to make the intact filegroups `A` and `C` current with the recovery point of the database.</span></span>  
  
    ```  
    BACKUP LOG adb TO tailLogBackup WITH NORECOVERY  
    ```  
  
2.  <span data-ttu-id="55d48-119">Restauração parcial do grupo de arquivos primários.</span><span class="sxs-lookup"><span data-stu-id="55d48-119">Partial restore of the primary filegroup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup   
    WITH PARTIAL, NORECOVERY  
    RESTORE LOG adb FROM backup1 WITH NORECOVERY  
    RESTORE LOG adb FROM backup2 WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="55d48-120">Neste momento o primário está online.</span><span class="sxs-lookup"><span data-stu-id="55d48-120">At this point the primary is online.</span></span> <span data-ttu-id="55d48-121">Os arquivos nos grupos de arquivos `A`, `B`e `C` estão com sua recuperação pendente e os grupos de arquivos estão offline.</span><span class="sxs-lookup"><span data-stu-id="55d48-121">Files in filegroups `A`, `B`, and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
3.  <span data-ttu-id="55d48-122">Restauração online dos grupos de arquivos `A` e `C`.</span><span class="sxs-lookup"><span data-stu-id="55d48-122">Online restore of filegroups `A` and `C`.</span></span>  
  
     <span data-ttu-id="55d48-123">Como seus dados não estão danificados, esses grupos de arquivos não têm de ser restaurados de um backup, mas eles têm de ser recuperados para serem colocados online.</span><span class="sxs-lookup"><span data-stu-id="55d48-123">Because their data is undamaged, these filegroups do not have to be restored from a backup, but they do have to be recovered to bring them online.</span></span>  
  
     <span data-ttu-id="55d48-124">O administrador do banco de dados recupera `A` e `C` imediatamente.</span><span class="sxs-lookup"><span data-stu-id="55d48-124">The database administrator recovers `A` and `C` immediately.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A', FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="55d48-125">Neste momento, o grupo de arquivos primário e os grupos de arquivos `A` e `C` estão online.</span><span class="sxs-lookup"><span data-stu-id="55d48-125">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="55d48-126">Os arquivos no grupo de arquivos `B` permanecem em recuperação pendente, com o grupo de arquivos offline.</span><span class="sxs-lookup"><span data-stu-id="55d48-126">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span>  
  
4.  <span data-ttu-id="55d48-127">Restauração online do grupo de arquivos `B`.</span><span class="sxs-lookup"><span data-stu-id="55d48-127">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="55d48-128">Os arquivos no grupo de arquivos `B` são restaurados a partir desse momento.</span><span class="sxs-lookup"><span data-stu-id="55d48-128">Files in filegroup `B` are restored any time thereafter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="55d48-129">O backup do grupo de arquivos `B` foi realizado depois de o grupo de arquivos tornar-se somente leitura; portanto, não há necessidade de efetuar roll-forward nesses arquivos.</span><span class="sxs-lookup"><span data-stu-id="55d48-129">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, these files do not have to be rolled forward.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="55d48-130">Todos os grupos de arquivos agora estão online.</span><span class="sxs-lookup"><span data-stu-id="55d48-130">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="55d48-131">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="55d48-131">Additional Examples</span></span>  
  
-   [<span data-ttu-id="55d48-132">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="55d48-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="55d48-133">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="55d48-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="55d48-134">Exemplo: restauração online de um arquivo somente leitura &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="55d48-134">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="55d48-135">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="55d48-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="55d48-136">Exemplo: restauração online de um arquivo de leitura/gravação #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="55d48-136">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="55d48-137">Exemplo: restauração online de um arquivo somente leitura #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="55d48-137">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="55d48-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55d48-138">See Also</span></span>  
 <span data-ttu-id="55d48-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="55d48-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="55d48-140">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="55d48-140">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="55d48-141">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="55d48-141">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="55d48-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="55d48-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="55d48-143">Restaurações por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="55d48-143">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
