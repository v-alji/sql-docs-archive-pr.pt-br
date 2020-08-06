---
title: 'Exemplo: restauração por etapas de banco de dados (modelo de recuperação simples) | Microsoft Docs'
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
ms.assetid: 9834b14a-4e56-4654-b190-c2a38624b6b4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69de84fa2ff3a853eb9926549ad4859d2f1ae38e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682302"
---
# <a name="example-piecemeal-restore-of-database-simple-recovery-model"></a><span data-ttu-id="89a8e-102">Exemplo: Restauração de banco de dados por etapas (modelo de recuperação simples)</span><span class="sxs-lookup"><span data-stu-id="89a8e-102">Example: Piecemeal Restore of Database (Simple Recovery Model)</span></span>
  <span data-ttu-id="89a8e-103">Uma sequência de restauração por etapas restaura e recupera um banco de dados em etapas no nível do grupo de arquivos, começando pelo grupo de arquivos primários e todos os grupos de arquivos secundários de leitura e gravação.</span><span class="sxs-lookup"><span data-stu-id="89a8e-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="89a8e-104">Nesse exemplo, o banco de dados `adb` é restaurado em um computador novo depois de um desastre.</span><span class="sxs-lookup"><span data-stu-id="89a8e-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="89a8e-105">O banco de dados está usando o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="89a8e-105">The database is using the simple recovery model.</span></span> <span data-ttu-id="89a8e-106">Antes do desastre, todos os grupos de arquivos estão online.</span><span class="sxs-lookup"><span data-stu-id="89a8e-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="89a8e-107">Os grupos de arquivos `A` e `C` são de leitura/gravação e o grupo de arquivos `B` é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="89a8e-107">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="89a8e-108">O grupo de arquivos `B` se tornou somente leitura antes do mais recente backup parcial, que contém o grupo de arquivos primários e os grupos de arquivos secundários de leitura/gravação, `A` e `C`.</span><span class="sxs-lookup"><span data-stu-id="89a8e-108">Filegroup `B` became read-only before the most recent partial backup, which contains the primary filegroup and the read/write secondary filegroups, `A` and `C`.</span></span> <span data-ttu-id="89a8e-109">Depois que o grupo de arquivos `B` tornou-se somente leitura, foi feito um backup de arquivo separado do grupo de arquivos `B` .</span><span class="sxs-lookup"><span data-stu-id="89a8e-109">After filegroup `B` became read-only, a separate file backup of filegroup `B` was taken.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="89a8e-110">Sequências da restauração</span><span class="sxs-lookup"><span data-stu-id="89a8e-110">Restore Sequences</span></span>  
  
1.  <span data-ttu-id="89a8e-111">Restauração parcial do grupo de arquivos primários e grupos de arquivos `A` e `C`.</span><span class="sxs-lookup"><span data-stu-id="89a8e-111">Partial restore of the primary and filegroups `A` and `C`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A',FILEGROUP='C'   
       FROM partial_backup   
       WITH PARTIAL, RECOVERY;  
  
    ```  
  
     <span data-ttu-id="89a8e-112">Neste momento, o grupo de arquivos primários e os grupos de arquivos `A` e `C` estão online.</span><span class="sxs-lookup"><span data-stu-id="89a8e-112">At this point, the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="89a8e-113">Todos os arquivos no grupo de arquivos `B` estão com recuperação pendente e o grupo de arquivos está offline.</span><span class="sxs-lookup"><span data-stu-id="89a8e-113">All files in filegroup `B` are recovery pending, and the filegroup is offline.</span></span>  
  
2.  <span data-ttu-id="89a8e-114">Restauração online do grupo de arquivos `B`.</span><span class="sxs-lookup"><span data-stu-id="89a8e-114">Online restore of filegroup `B`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY;  
  
    ```  
  
     <span data-ttu-id="89a8e-115">Todos os grupos de arquivos agora estão online.</span><span class="sxs-lookup"><span data-stu-id="89a8e-115">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="89a8e-116">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="89a8e-116">Additional Examples</span></span>  
  
-   [<span data-ttu-id="89a8e-117">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="89a8e-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="89a8e-118">Exemplo: restauração online de um arquivo somente leitura &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="89a8e-118">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="89a8e-119">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="89a8e-119">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="89a8e-120">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="89a8e-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="89a8e-121">Exemplo: restauração online de um arquivo de leitura/gravação #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="89a8e-121">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="89a8e-122">Exemplo: restauração online de um arquivo somente leitura #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="89a8e-122">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="89a8e-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89a8e-123">See Also</span></span>  
 <span data-ttu-id="89a8e-124">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="89a8e-124">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="89a8e-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89a8e-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="89a8e-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89a8e-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="89a8e-127">Restaurações por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89a8e-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
