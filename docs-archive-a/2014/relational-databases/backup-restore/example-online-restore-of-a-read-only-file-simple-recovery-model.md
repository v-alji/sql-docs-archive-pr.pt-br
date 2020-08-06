---
title: 'Exemplo: restauração online de um arquivo somente leitura (modelo de recuperação simples) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restore sequences [SQL Server], online
- online restores [SQL Server], simple recovery model
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: 0c691fc6-9865-46a7-b055-8097424492d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d84c920a2cb40866ba106b4d30d8e24c4caea611
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685808"
---
# <a name="example-online-restore-of-a-read-only-file-simple-recovery-model"></a><span data-ttu-id="9c398-102">Exemplo: Restauração online de um arquivo somente leitura (modelo de recuperação simples)</span><span class="sxs-lookup"><span data-stu-id="9c398-102">Example: Online Restore of a Read-Only File (Simple Recovery Model)</span></span>
  <span data-ttu-id="9c398-103">Este tópico é pertinente para bancos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sob o modelo de recuperação simples que contenham um grupo de arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9c398-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span> <span data-ttu-id="9c398-104">No modelo de recuperação simples, um arquivo somente leitura pode ser restaurado online se existir um backup do arquivo que tenha sido feito desde a última vez em que arquivo tornou-se somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9c398-104">Under the simple recovery model, a read-only file can be restored online if a file backup exists that was taken since the file became read-only for the last time.</span></span>  
  
 <span data-ttu-id="9c398-105">Neste exemplo, um banco de dados denominado `adb` contém três grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9c398-105">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="9c398-106">O grupo de arquivos `A` é leitura/gravação, e os grupos de arquivos `B` e `C` são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9c398-106">Filegroup `A` is read/write, and filegroups `B` and `C` are read-only.</span></span> <span data-ttu-id="9c398-107">Inicialmente, todos os grupos de arquivos estão online.</span><span class="sxs-lookup"><span data-stu-id="9c398-107">Initially, all of the filegroups are online.</span></span> <span data-ttu-id="9c398-108">Um arquivo somente leitura no grupo de arquivos `B`, `b1`, tem de ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="9c398-108">A read-only file in filegroup `B`, `b1`, has to be restored.</span></span> <span data-ttu-id="9c398-109">O administrador de banco de dados pode restaurá-lo usando um backup que foi feito depois de o arquivo tornar-se somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9c398-109">The database administrator can restore it by using a backup that was taken after the file became read-only.</span></span> <span data-ttu-id="9c398-110">Durante a restauração, o grupo de arquivos `B` estará offline, mas o resto do banco de dados permanecerá online.</span><span class="sxs-lookup"><span data-stu-id="9c398-110">For the duration of the restore, filegroup `B` will be offline, but the remainder of the database will remain online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="9c398-111">Sequência de restauração</span><span class="sxs-lookup"><span data-stu-id="9c398-111">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c398-112">A sintaxe para uma sequência de restauração online é igual à de uma sequência de restauração offline.</span><span class="sxs-lookup"><span data-stu-id="9c398-112">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="9c398-113">Para restaurar o arquivo, o administrador do banco de dados usa a seguinte sequência de restauração:</span><span class="sxs-lookup"><span data-stu-id="9c398-113">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup   
WITH RECOVERY  
```  
  
 <span data-ttu-id="9c398-114">O arquivo agora está online.</span><span class="sxs-lookup"><span data-stu-id="9c398-114">The file is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="9c398-115">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="9c398-115">Additional Examples</span></span>  
  
-   [<span data-ttu-id="9c398-116">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="9c398-116">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="9c398-117">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="9c398-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="9c398-118">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9c398-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="9c398-119">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9c398-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="9c398-120">Exemplo: restauração online de um arquivo de leitura/gravação #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9c398-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="9c398-121">Exemplo: restauração online de um arquivo somente leitura #40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9c398-121">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c398-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c398-122">See Also</span></span>  
 <span data-ttu-id="9c398-123">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c398-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="9c398-124">[Restaurações por etapas &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c398-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="9c398-125">[Restaurações de arquivos &#40;Modelo de recuperação simples&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="9c398-125">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="9c398-126">[Visão geral de restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9c398-126">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="9c398-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9c398-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
