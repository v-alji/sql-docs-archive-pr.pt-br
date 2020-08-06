---
title: Backups parciais (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- partial backups [SQL Server]
- READ_WRITE_FILEGROUPS option
- database backups [SQL Server], about backing up databases
ms.assetid: fe6b6bb1-38d0-46c4-bab8-31df14e8999c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0c03cf2fb4d3af6fe87459e881e26c48cfacc232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581425"
---
# <a name="partial-backups-sql-server"></a><span data-ttu-id="d3c72-102">Backups parciais (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3c72-102">Partial Backups (SQL Server)</span></span>
  <span data-ttu-id="d3c72-103">Todos os modelos de recuperação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferecem suporte a backups parciais. Então, este tópico é relevante a todos os bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3c72-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recovery models support partial backups, so this topic is relevant for all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="d3c72-104">No entanto, os backups parciais são projetados para uso no modelo de recuperação simples para aprimorar a flexibilidade no backup de bancos de dados muito grandes que contêm um ou mais grupos de arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d3c72-104">However, partial backups are designed for use under the simple recovery model to improve flexibility for backing up very large databases that contain one or more read-only filegroups.</span></span>  
  
 <span data-ttu-id="d3c72-105">Os backups parciais são úteis sempre que você quer excluir grupos de arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d3c72-105">Partial backups are useful whenever you want to exclude read-only filegroups.</span></span> <span data-ttu-id="d3c72-106">Um *backup parcial* se assemelha a um backup de banco de dados completo, mas não contém todos os grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3c72-106">A *partial backup* resembles a full database backup, but a partial backup does not contain all the filegroups.</span></span> <span data-ttu-id="d3c72-107">Em vez disso, para um banco de dados somente leitura, um backup parcial contém todos os dados do grupo de arquivos primário, todos os grupos de arquivos de leitura/gravação e, opcionalmente, um ou mais arquivos de somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d3c72-107">Instead, for a read-write database, a partial backup contains the data in the primary filegroup, every read-write filegroup, and, optionally, one or more read-only files.</span></span> <span data-ttu-id="d3c72-108">Um backup parcial de um banco de dados somente leitura contém apenas o grupo de arquivos primário.</span><span class="sxs-lookup"><span data-stu-id="d3c72-108">A partial backup of a read-only database contains only the primary filegroup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3c72-109">Se o banco de dados somente leitura for alterado para leitura/gravação depois de um backup parcial, será possível haver grupos de arquivos secundários leitura/gravação que não estejam no backup parcial.</span><span class="sxs-lookup"><span data-stu-id="d3c72-109">If a read-only database is changed to read/write after a partial backup, there might be read/write secondary filegroups that are not in the partial backup.</span></span> <span data-ttu-id="d3c72-110">Nesse caso, se você tentar fazer um backup parcial diferencial, o backup falhará.</span><span class="sxs-lookup"><span data-stu-id="d3c72-110">In this case, if you try to take a differential partial backup, the backup fails.</span></span> <span data-ttu-id="d3c72-111">Para fazer um backup diferencial parcial de banco de dados, é necessário fazer outro backup parcial.</span><span class="sxs-lookup"><span data-stu-id="d3c72-111">Before you can take a differential partial backup of the database, you must take another partial backup.</span></span> <span data-ttu-id="d3c72-112">O novo backup parcial contém todos os grupos de arquivos leitura/gravação secundários e pode servir de base para backups diferenciais parciais.</span><span class="sxs-lookup"><span data-stu-id="d3c72-112">The new partial backup contains every read/write secondary filegroup and can serve as the base for differential partial backups.</span></span>  
  
 <span data-ttu-id="d3c72-113">Backups de arquivos de grupos de arquivos do tipo somente leitura podem ser combinados com backups parciais.</span><span class="sxs-lookup"><span data-stu-id="d3c72-113">File backups of read-only filegroups can be combined with partial backups.</span></span> <span data-ttu-id="d3c72-114">Para obter informações sobre backups de arquivos, veja [Backups completos de arquivos &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3c72-114">For information about file backups, see [Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="d3c72-115">Um backup parcial pode servir como *base diferencial* para backups parciais diferenciais.</span><span class="sxs-lookup"><span data-stu-id="d3c72-115">A partial backup can serve as the *differential base* for differential partial backups.</span></span> <span data-ttu-id="d3c72-116">Para obter mais informações, veja [Backups diferenciais &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3c72-116">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d3c72-117">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d3c72-117">Related Tasks</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3c72-118">Não há suporte para backups parciais no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou no Assistente de Plano de Manutenção.</span><span class="sxs-lookup"><span data-stu-id="d3c72-118">Partial backups are not supported by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the Maintenance Plan Wizard.</span></span>  
  
 <span data-ttu-id="d3c72-119">**Para criar um backup parcial**</span><span class="sxs-lookup"><span data-stu-id="d3c72-119">**To create a partial backup**</span></span>  
  
-   <span data-ttu-id="d3c72-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; opção FILEGROUP, se necessário)</span><span class="sxs-lookup"><span data-stu-id="d3c72-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; FILEGROUP option, if needed)</span></span>  
  
 <span data-ttu-id="d3c72-121">**Para usar um backup parcial em uma sequência de restauração**</span><span class="sxs-lookup"><span data-stu-id="d3c72-121">**To use a partial backup in a restore sequence**</span></span>  
  
-   [<span data-ttu-id="d3c72-122">Exemplo: Restauração por etapas de banco de dados &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="d3c72-122">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="d3c72-123">Exemplo: Restauração por etapas de apenas alguns grupos de arquivos &#40;Modelo de recuperação simples&#41;</span><span class="sxs-lookup"><span data-stu-id="d3c72-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3c72-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3c72-124">See Also</span></span>  
 <span data-ttu-id="d3c72-125">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d3c72-125">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="d3c72-126">[Restaurações de arquivos &#40;Modelo de recuperação simples&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="d3c72-126">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="d3c72-127">Restaurações por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d3c72-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
