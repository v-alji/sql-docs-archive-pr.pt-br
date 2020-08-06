---
title: 'Exemplo: restauração online de um arquivo somente leitura (modelo de recuperação completa) | Microsoft Docs'
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
ms.assetid: 7ea2d2af-086f-48dc-9636-38dc194c7090
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f493c88d64e6ed22e44f33f1442ae581daa8ed4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685809"
---
# <a name="example-online-restore-of-a-read-only-file-full-recovery-model"></a><span data-ttu-id="a0ef5-102">Exemplo: Restauração online de um arquivo somente leitura (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="a0ef5-102">Example: Online Restore of a Read-Only File (Full Recovery Model)</span></span>
  <span data-ttu-id="a0ef5-103">Este tópico é relevante para bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sob o modelo de recuperação completa que contém vários arquivos ou grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="a0ef5-104">Neste exemplo, um banco de dados nomeado `adb`, que usa o modelo de recuperação completa, contém três grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="a0ef5-105">O grupo de arquivos `A` é de leitura/gravação e os grupos de arquivos `B` e `C` são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="a0ef5-106">Inicialmente, todos os grupos de arquivos estão online.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="a0ef5-107">Um arquivo somente leitura, `b1`, no grupo de arquivos `B` do banco de dados `adb` precisa ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-107">A read-only file, `b1`, in filegroup `B` of database `adb` has to be restored.</span></span> <span data-ttu-id="a0ef5-108">Foi feito um backup quando o arquivo se tornou somente leitura; portanto, backups de log não são necessários.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-108">A backup was taken since the file became read-only; therefore, log backups are not required.</span></span> <span data-ttu-id="a0ef5-109">O grupo de arquivos `B` está offline durante a restauração, mas o restante do banco de dados permanece online.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-109">Filegroup `B` is offline for the duration of the restore, but the remainder of the database remains online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="a0ef5-110">Sequência de restauração</span><span class="sxs-lookup"><span data-stu-id="a0ef5-110">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0ef5-111">A sintaxe para uma sequência de restauração online é igual à de uma sequência de restauração offline.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-111">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="a0ef5-112">Para restaurar o arquivo, o administrador do banco de dados usa a seguinte sequência de restauração:</span><span class="sxs-lookup"><span data-stu-id="a0ef5-112">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup  
WITH RECOVERY   
```  
  
 <span data-ttu-id="a0ef5-113">O grupo de arquivos B agora está online.</span><span class="sxs-lookup"><span data-stu-id="a0ef5-113">Filegroup B is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="a0ef5-114">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="a0ef5-114">Additional Examples</span></span>  
  
-   [<span data-ttu-id="a0ef5-115">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef5-115">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="a0ef5-116">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef5-116">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="a0ef5-117">Exemplo: restauração online de um arquivo somente leitura &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef5-117">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="a0ef5-118">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef5-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="a0ef5-119">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef5-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="a0ef5-120">Exemplo: restauração online de um arquivo de leitura/gravação #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef5-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0ef5-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0ef5-121">See Also</span></span>  
 <span data-ttu-id="a0ef5-122">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0ef5-122">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="a0ef5-123">[Visão geral de restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a0ef5-123">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="a0ef5-124">[Restaurações de arquivo &#40;Modelo de recuperação completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="a0ef5-124">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="a0ef5-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef5-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
