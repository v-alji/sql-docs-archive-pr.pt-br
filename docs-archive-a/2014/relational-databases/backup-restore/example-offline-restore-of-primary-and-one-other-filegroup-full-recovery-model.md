---
title: 'Exemplo: restauração offline de um grupo de arquivos primário e outro (modelo de recuperação completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- offline restores [SQL Server]
- restore sequences [SQL Server], offline
ms.assetid: 7d6c50eb-dc84-4d66-855a-0b5f1bd89737
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f845927fdd74fba476139fccbf9a5fa112d434e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582467"
---
# <a name="example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model"></a><span data-ttu-id="2f73b-102">Exemplo: Restauração offline do grupo de arquivos primário e mais um (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="2f73b-102">Example: Offline Restore of Primary and One Other Filegroup (Full Recovery Model)</span></span>
  <span data-ttu-id="2f73b-103">Este tópico é relevante apenas para bancos de dados com modelos de recuperação completa e que contêm vários grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2f73b-103">This topic is relevant only for databases under the full recovery model that contain multiple filegroups.</span></span>  
  
 <span data-ttu-id="2f73b-104">Neste exemplo, um banco de dados denominado `adb` contém três grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2f73b-104">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="2f73b-105">Os grupos de arquivos `A` e `C` são de leitura/gravação e o grupo de arquivos `B` é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="2f73b-105">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="2f73b-106">O grupo de arquivos primário e o grupo de arquivos `B` estão danificados, mas os grupos de arquivos `A` e `C` estão intactos.</span><span class="sxs-lookup"><span data-stu-id="2f73b-106">The primary filegroup and filegroup `B` are damaged, but filegroups `A` and `C` are intact.</span></span> <span data-ttu-id="2f73b-107">Antes do desastre, todos os grupos de arquivos estavam online.</span><span class="sxs-lookup"><span data-stu-id="2f73b-107">Before the disaster, all the filegroups were online.</span></span>  
  
 <span data-ttu-id="2f73b-108">O administrador de banco de dados decide restaurar e recuperar o grupo de arquivos primário e grupo de arquivos `B`.</span><span class="sxs-lookup"><span data-stu-id="2f73b-108">The database administrator decides to restore and recover the primary filegroup and filegroup `B`.</span></span> <span data-ttu-id="2f73b-109">O banco de dados está usando o modelo de recuperação completa; portanto, antes do início da restauração, um backup do final do log deve ser extraído do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2f73b-109">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="2f73b-110">Quando o banco de dados estiver online, os grupos de arquivos `A` e `C` ficarão automaticamente online.</span><span class="sxs-lookup"><span data-stu-id="2f73b-110">When the database comes on line, Filegroups `A` and `C` are automatically brought online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f73b-111">A sequência de restauração offline tem menos etapas do que a restauração online de um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="2f73b-111">The offline restore sequence has fewer steps than an online restore of a read-only file.</span></span> <span data-ttu-id="2f73b-112">Para obter um exemplo, confira [Exemplo: restauração online de um arquivo somente leitura #40;Modelo de recuperação completa&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="2f73b-112">For an example, see [Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span></span> <span data-ttu-id="2f73b-113">Porém, todo o banco de dados está offline na duração da sequência.</span><span class="sxs-lookup"><span data-stu-id="2f73b-113">However, the whole database is offline for the duration of the sequence.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="2f73b-114">Backup do final do log</span><span class="sxs-lookup"><span data-stu-id="2f73b-114">Tail-Log Backup</span></span>  
 <span data-ttu-id="2f73b-115">Antes de restaurar o banco de dados, o administrador do banco de dados deve fazer backup do final do log.</span><span class="sxs-lookup"><span data-stu-id="2f73b-115">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="2f73b-116">Como o banco de dados está danificado, é preciso usar a opção NO_TRUNCATE para criar o backup do final do log:</span><span class="sxs-lookup"><span data-stu-id="2f73b-116">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup   
   WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="2f73b-117">O backup do final do log é o último backup aplicado nas sequências de restauração a seguir.</span><span class="sxs-lookup"><span data-stu-id="2f73b-117">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="2f73b-118">Sequência de restauração</span><span class="sxs-lookup"><span data-stu-id="2f73b-118">Restore Sequence</span></span>  
 <span data-ttu-id="2f73b-119">Para restaurar o grupo de arquivos primário e o grupo de arquivos `B`, o administrador do banco de dados usa uma sequência de restauração sem a opção PARTIAL, do seguinte modo:</span><span class="sxs-lookup"><span data-stu-id="2f73b-119">To restore the primary filegroup and filegroup `B`, the database administrator uses a restore sequence without the PARTIAL option, as follows:</span></span>  
  
```  
RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
WITH NORECOVERY  
RESTORE DATABASE adb FILEGROUP='B' FROM backup2   
WITH NORECOVERY  
RESTORE LOG adb FROM backup3 WITH NORECOVERY  
RESTORE LOG adb FROM backup4 WITH NORECOVERY  
RESTORE LOG adb FROM backup5 WITH NORECOVERY  
RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
```  
  
 <span data-ttu-id="2f73b-120">Os arquivos que não estão restaurados ficam automaticamente online.</span><span class="sxs-lookup"><span data-stu-id="2f73b-120">The files that are not restored are automatically brought online.</span></span> <span data-ttu-id="2f73b-121">Todos os grupos de arquivos agora estão online.</span><span class="sxs-lookup"><span data-stu-id="2f73b-121">All the filegroups are now online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f73b-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f73b-122">See Also</span></span>  
 <span data-ttu-id="2f73b-123">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2f73b-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="2f73b-124">[Restaurações por etapas &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2f73b-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="2f73b-125">[Restaurações de arquivo &#40;Modelo de recuperação completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="2f73b-125">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="2f73b-126">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2f73b-126">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="2f73b-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f73b-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
