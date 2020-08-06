---
title: 'Exemplo: restauração online de um arquivo leitura-gravação (modelo de recuperação completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- online restores [SQL Server], full recovery model
- restore sequences [SQL Server], online
ms.assetid: 0dbeda81-1464-44ba-9011-914900096368
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5b99a3d97644c2a5f104173457f30fc5b3fd7188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570075"
---
# <a name="example-online-restore-of-a-read-write-file-full-recovery-model"></a><span data-ttu-id="0185d-102">Exemplo: Restauração online de um arquivo de leitura/gravação (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="0185d-102">Example: Online Restore of a Read-Write File (Full Recovery Model)</span></span>
  <span data-ttu-id="0185d-103">Este tópico é relevante para bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sob o modelo de recuperação completa que contém vários arquivos ou grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0185d-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="0185d-104">Neste exemplo, um banco de dados nomeado `adb`, que usa o modelo de recuperação completa, contém três grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0185d-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="0185d-105">O grupo de arquivos `A` é de leitura/gravação e os grupos de arquivos `B` e `C` são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="0185d-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="0185d-106">Inicialmente, todos os grupos de arquivos estão online.</span><span class="sxs-lookup"><span data-stu-id="0185d-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="0185d-107">O arquivo `a1` no grupo de arquivos `A` parece estar danificado e o administrador de banco de dados decide restaurá-lo enquanto o banco de dados permanece online.</span><span class="sxs-lookup"><span data-stu-id="0185d-107">File `a1` in filegroup `A` appears to be damaged, and the database administrator decides to restore it while the database remains online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0185d-108">Segundo o modelo de recuperação simples, a restauração online de dados leitura/gravação não é permitida.</span><span class="sxs-lookup"><span data-stu-id="0185d-108">Under the simple recovery model, online restore of read/write data is not allowed.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="0185d-109">Sequências da restauração</span><span class="sxs-lookup"><span data-stu-id="0185d-109">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0185d-110">A sintaxe para uma sequência de restauração online é igual à de uma sequência de restauração offline.</span><span class="sxs-lookup"><span data-stu-id="0185d-110">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="0185d-111">Restauração online do arquivo `a1`.</span><span class="sxs-lookup"><span data-stu-id="0185d-111">Online restore of file `a1`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILE='a1' FROM backup   
    WITH NORECOVERY;  
    ```  
  
     <span data-ttu-id="0185d-112">Neste momento, o arquivo a1 está no estado de RESTORING e o grupo de arquivos A está offline.</span><span class="sxs-lookup"><span data-stu-id="0185d-112">At this point, file a1 is in the RESTORING state, and filegroup A is offline.</span></span>  
  
2.  <span data-ttu-id="0185d-113">Depois de restaurar o arquivo, o administrador do banco de dados faz um novo backup do log para verificar se o ponto em que o arquivo ficou offline é capturado.</span><span class="sxs-lookup"><span data-stu-id="0185d-113">After restoring the file, the database administrator takes a new log backup to make sure that the point at which the file went offline is captured.</span></span>  
  
    ```  
    BACKUP LOG adb TO log_backup3;   
    ```  
  
3.  <span data-ttu-id="0185d-114">Restauração online de backups de log.</span><span class="sxs-lookup"><span data-stu-id="0185d-114">Online restore of log backups.</span></span>  
  
     <span data-ttu-id="0185d-115">O administrador restaura todos os backups de log feitos desde o backup do arquivo restaurado, terminando com o backup de log mais recente (*log_backup3*, feito na etapa 2).</span><span class="sxs-lookup"><span data-stu-id="0185d-115">The administrator restores all the log backups taken since the restored file backup, ending with the latest log backup (*log_backup3*, taken in step 2).</span></span> <span data-ttu-id="0185d-116">Depois que o último backup é restaurado, o banco de dados é recuperado.</span><span class="sxs-lookup"><span data-stu-id="0185d-116">After the last backup is restored, the database is recovered.</span></span>  
  
    ```  
    RESTORE LOG adb FROM log_backup1 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup2 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup3 WITH NORECOVERY;  
    RESTORE LOG adb WITH RECOVERY;  
    ```  
  
     <span data-ttu-id="0185d-117">O arquivo `a1` agora está online.</span><span class="sxs-lookup"><span data-stu-id="0185d-117">File `a1` is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="0185d-118">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="0185d-118">Additional Examples</span></span>  
  
-   [<span data-ttu-id="0185d-119">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="0185d-119">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="0185d-120">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="0185d-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="0185d-121">Exemplo: restauração online de um arquivo somente leitura &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="0185d-121">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="0185d-122">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="0185d-122">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="0185d-123">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="0185d-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="0185d-124">Exemplo: restauração online de um arquivo somente leitura #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="0185d-124">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="0185d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0185d-125">See Also</span></span>  
 <span data-ttu-id="0185d-126">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0185d-126">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="0185d-127">[Restaurações por etapas &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0185d-127">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="0185d-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0185d-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="0185d-129">[Visão geral de restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0185d-129">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="0185d-130">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0185d-130">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="0185d-131">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0185d-131">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
