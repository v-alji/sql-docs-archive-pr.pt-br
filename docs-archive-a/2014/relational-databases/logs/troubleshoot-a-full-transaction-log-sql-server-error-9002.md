---
title: Solução de problemas em um log de transação completa (SQL Server Erro 9002) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], full
- troubleshooting [SQL Server], full transaction log
- 9002 (Database Engine error)
- transaction logs [SQL Server], truncation
- backing up transaction logs [SQL Server], full logs
- transaction logs [SQL Server], full log
- full transaction logs [SQL Server]
ms.assetid: 0f23aa84-475d-40df-bed3-c923f8c1b520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d03e259bd0aff8fce02558dbe08efb56748493c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569439"
---
# <a name="troubleshoot-a-full-transaction-log-sql-server-error-9002"></a><span data-ttu-id="4ebd5-102">Solução de problemas em um log de transação completa (SQL Server Erro 9002)</span><span class="sxs-lookup"><span data-stu-id="4ebd5-102">Troubleshoot a Full Transaction Log (SQL Server Error 9002)</span></span>
  <span data-ttu-id="4ebd5-103">Este tópico aborda as respostas possíveis a um log de transações completo e sugere como evitar isso no futuro.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-103">This topic discusses possible responses to a full transaction log and suggests how to avoid it in the future.</span></span> <span data-ttu-id="4ebd5-104">Quando o log de transações fica completo, o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] emite um erro 9002.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-104">When the transaction log becomes full, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] issues a 9002 error.</span></span> <span data-ttu-id="4ebd5-105">O log pode ficar completo quando o banco de dados estiver online ou em recuperação.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-105">The log can fill when the database is online or in recovery.</span></span> <span data-ttu-id="4ebd5-106">Se o log ficar cheio enquanto o banco de dados estiver online, o banco de dados permanecerá online, mas só poderá ser lido, não atualizado.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-106">If the log fills while the database is online, the database remains online but can only be read, not updated.</span></span> <span data-ttu-id="4ebd5-107">Se o log ficar completo durante uma recuperação, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] marcará o banco de dados como RESOURCE PENDING.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-107">If the log fills during recovery, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] marks the database as RESOURCE PENDING.</span></span> <span data-ttu-id="4ebd5-108">Em qualquer caso, é necessária a ação do usuário para liberar espaço no log.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-108">In either case, user action is required to make log space available.</span></span>  
  
## <a name="responding-to-a-full-transaction-log"></a><span data-ttu-id="4ebd5-109">Respondendo a um log de transações completo</span><span class="sxs-lookup"><span data-stu-id="4ebd5-109">Responding to a Full Transaction Log</span></span>  
 <span data-ttu-id="4ebd5-110">A resposta apropriada a um log de transações completo depende em parte das condições que o fizeram ficar completo.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-110">The appropriate response to a full transaction log depends partly on what condition or conditions caused the log to fill.</span></span> <span data-ttu-id="4ebd5-111">Para descobrir o que está impedindo o truncamento de log em um determinado caso, use as colunas **log_reuse_wait** e **log_reuse_wait_desc** da exibição de catálogo do **sys.database**.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-111">To discover what is preventing log truncation in a given case, use the **log_reuse_wait** and **log_reuse_wait_desc** columns of the **sys.database** catalog view.</span></span> <span data-ttu-id="4ebd5-112">Para obter mais informações, veja [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ebd5-112">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span> <span data-ttu-id="4ebd5-113">Para descrições de fatores que podem adiar o truncamento de log, consulte [O log de transações &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd5-113">For descriptions of factors that can delay log truncation, see [The Transaction Log &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4ebd5-114">Se o banco de dados estava em recuperação quando o erro 9002 aconteceu, depois de resolver o problema, recupere o banco de dados usando ALTER DATABASE *database_name* SET ONLINE.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-114">If the database was in recovery when the 9002 error occurred, after resolving the problem, recover the database by using ALTER DATABASE *database_name* SET ONLINE.</span></span>  
  
 <span data-ttu-id="4ebd5-115">As alternativas para responder a um log de transações completo incluem:</span><span class="sxs-lookup"><span data-stu-id="4ebd5-115">Alternatives for responding to a full transaction log include:</span></span>  
  
-   <span data-ttu-id="4ebd5-116">Fazer backup do log.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-116">Backing up the log.</span></span>  
  
-   <span data-ttu-id="4ebd5-117">Liberar espaço de disco para que o log possa crescer automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-117">Freeing disk space so that the log can automatically grow.</span></span>  
  
-   <span data-ttu-id="4ebd5-118">Mover o arquivo de log para uma unidade de disco com espaço suficiente.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-118">Moving the log file to a disk drive with sufficient space.</span></span>  
  
-   <span data-ttu-id="4ebd5-119">Aumentar o tamanho de um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-119">Increasing the size of a log file.</span></span>  
  
-   <span data-ttu-id="4ebd5-120">Adicionar um arquivo de log a um disco diferente.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-120">Adding a log file on a different disk.</span></span>  
  
-   <span data-ttu-id="4ebd5-121">Completar ou cancelar uma transação demorada.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-121">Completing or killing a long-running transaction.</span></span>  
  
 <span data-ttu-id="4ebd5-122">Essas alternativas são discutidas nas seções seguintes.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-122">These alternatives are discussed in the following sections.</span></span> <span data-ttu-id="4ebd5-123">Escolha uma resposta que se ajuste melhor a sua situação.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-123">Choose a response that fits your situation best.</span></span>  
  
### <a name="backing-up-the-log"></a><span data-ttu-id="4ebd5-124">Fazendo backup de log</span><span class="sxs-lookup"><span data-stu-id="4ebd5-124">Backing up the Log</span></span>  
 <span data-ttu-id="4ebd5-125">No modelo de recuperação completa ou no modelo de recuperação bulk-logged, se não foi feito backup do log de transações recentemente, pode ser que o backup esteja impedindo o truncamento de log.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-125">Under the full recovery model or bulk-logged recovery model, if the transaction log has not been backed up recently, backup might be what is preventing log truncation.</span></span> <span data-ttu-id="4ebd5-126">Se nunca foi feito backup do log, você deve criar dois backups de log para permitir que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] trunque o log no ponto do último backup.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-126">If the log has never been backed up, you must create two log backups to permit the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to truncate the log to the point of the last backup.</span></span> <span data-ttu-id="4ebd5-127">Truncar o log libera espaço para novos registros de log.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-127">Truncating the log frees space for new log records.</span></span> <span data-ttu-id="4ebd5-128">Para impedir que o log fique completo novamente, faça backups de log frequentes.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-128">To keep the log from filling up again, take log backups frequently.</span></span>  
  
 <span data-ttu-id="4ebd5-129">**Para criar um backup de log de transações**</span><span class="sxs-lookup"><span data-stu-id="4ebd5-129">**To create a transaction log backup**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4ebd5-130">Se o banco de dados estiver danificado, consulte [Backups da parte final do Log &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4ebd5-130">If the database is damaged, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="4ebd5-131">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4ebd5-131">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="4ebd5-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="4ebd5-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
### <a name="freeing-disk-space"></a><span data-ttu-id="4ebd5-133">Liberando espaço no disco</span><span class="sxs-lookup"><span data-stu-id="4ebd5-133">Freeing Disk Space</span></span>  
 <span data-ttu-id="4ebd5-134">Pode ser possível liberar espaço de disco na unidade de disco que contém o arquivo de log de transações do banco de dados excluindo ou movendo outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-134">You might be able to free disk space on the disk drive that contains the transaction log file for the database by deleting or moving other files.</span></span> <span data-ttu-id="4ebd5-135">O espaço de disco liberado permite que o sistema de recuperação aumente o arquivo de log automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-135">The freed disk space allows the recovery system to enlarge the log file automatically.</span></span>  
  
### <a name="moving-the-log-file-to-a-different-disk"></a><span data-ttu-id="4ebd5-136">Movendo o arquivo de log para um disco diferente</span><span class="sxs-lookup"><span data-stu-id="4ebd5-136">Moving the Log File to a Different Disk</span></span>  
 <span data-ttu-id="4ebd5-137">Se você não puder liberar espaço de disco suficiente na unidade que contém o arquivo de log, pense em mover o arquivo para outra unidade com espaço suficiente.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-137">If you cannot free enough disk space on the drive that currently contains the log file, consider moving the file to another drive with sufficient space.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4ebd5-138">Arquivos de log nunca devem ser colocados em sistemas de arquivos compactados.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-138">Log files should never be placed on compressed file systems.</span></span>  
  
 <span data-ttu-id="4ebd5-139">**Para mover um arquivo de log**</span><span class="sxs-lookup"><span data-stu-id="4ebd5-139">**To move a log file**</span></span>  
  
-   [<span data-ttu-id="4ebd5-140">Mover arquivos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="4ebd5-140">Move Database Files</span></span>](../databases/move-database-files.md)  
  
### <a name="increasing-the-size-of-a-log-file"></a><span data-ttu-id="4ebd5-141">Aumentando o tamanho de um arquivo de log</span><span class="sxs-lookup"><span data-stu-id="4ebd5-141">Increasing the Size of a Log File</span></span>  
 <span data-ttu-id="4ebd5-142">Se houver espaço disponível no disco de log, você pode aumentar o tamanho do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-142">If space is available on the log disk, you can increase the size of the log file.</span></span> <span data-ttu-id="4ebd5-143">O tamanho máximo para arquivos de log é de dois terabytes (TB) por arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-143">The maximum size for log files is two terabytes (TB) per log file.</span></span>  
  
 <span data-ttu-id="4ebd5-144">**Para aumentar o tamanho de arquivo**</span><span class="sxs-lookup"><span data-stu-id="4ebd5-144">**To increase the file size**</span></span>  
  
 <span data-ttu-id="4ebd5-145">Se o aumento automático estiver desabilitado, o banco de dados estiver online e houver espaço suficiente disponível no disco, as ações possíveis serão:</span><span class="sxs-lookup"><span data-stu-id="4ebd5-145">If autogrow is disabled, the database is online, and sufficient space is available on the disk, either:</span></span>  
  
-   <span data-ttu-id="4ebd5-146">Aumentar manualmente o tamanho de arquivo para produzir um único incremento de crescimento.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-146">Manually increase the file size to produce a single growth increment.</span></span>  
  
-   <span data-ttu-id="4ebd5-147">Ativar o crescimento automático usando a instrução ALTER DATABASE para definir um incremento de crescimento diferente de zero para a opção FILEGROWTH.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-147">Turn on autogrow by using the ALTER DATABASE statement to set a non-zero growth increment for the FILEGROWTH option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ebd5-148">Em qualquer caso, se o limite de tamanho atual foi alcançado, aumente o valor MAXSIZE.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-148">In either case, if the current size limit has been reached, increase the MAXSIZE value.</span></span>  
  
### <a name="adding-a-log-file-on-a-different-disk"></a><span data-ttu-id="4ebd5-149">Adicionando um arquivo de log a um disco diferente</span><span class="sxs-lookup"><span data-stu-id="4ebd5-149">Adding a Log File on a Different Disk</span></span>  
 <span data-ttu-id="4ebd5-150">Adicione um arquivo de log novo ao banco de dados em um disco diferente que tenha espaço suficiente usando ALTER DATABASE <database_name> ADD LOG FILE.</span><span class="sxs-lookup"><span data-stu-id="4ebd5-150">Add a new log file to the database on a different disk that has sufficient space by using ALTER DATABASE <database_name> ADD LOG FILE.</span></span>  
  
 <span data-ttu-id="4ebd5-151">**Para adicionar um arquivo de log**</span><span class="sxs-lookup"><span data-stu-id="4ebd5-151">**To add a log file**</span></span>  
  
-   [<span data-ttu-id="4ebd5-152">Adicionar arquivos de dados ou de log a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="4ebd5-152">Add Data or Log Files to a Database</span></span>](../databases/add-data-or-log-files-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ebd5-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4ebd5-153">See Also</span></span>  
 <span data-ttu-id="4ebd5-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ebd5-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="4ebd5-155">[Gerenciar o tamanho do arquivo de log de transações](manage-the-size-of-the-transaction-log-file.md) </span><span class="sxs-lookup"><span data-stu-id="4ebd5-155">[Manage the Size of the Transaction Log File](manage-the-size-of-the-transaction-log-file.md) </span></span>  
 <span data-ttu-id="4ebd5-156">[Backups de log de transações &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ebd5-156">[Transaction Log Backups &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="4ebd5-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4ebd5-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-log-file-recover-suspect-db-transact-sql)  
  
  
