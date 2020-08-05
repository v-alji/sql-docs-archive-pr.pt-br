---
title: Aplicar backups do log de transações (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], log backups
- transaction log backups [SQL Server], applying backups
- online restores [SQL Server], log backups
- transaction log backups [SQL Server], quantity needed for restore sequence
- backups [SQL Server], log backups
ms.assetid: 9b12be51-5469-46f9-8e86-e938e10aa3a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54c91106f8ca6f15539b4103220860143882c3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573145"
---
# <a name="apply-transaction-log-backups-sql-server"></a><span data-ttu-id="9522b-102">Aplicar backups de log de transações (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9522b-102">Apply Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="9522b-103">O tópico só é relevante para o modelo de recuperação completa ou modelo de recuperação bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="9522b-103">The topic is relevant only for the full recovery model or bulk-logged recovery model.</span></span>  
  
 <span data-ttu-id="9522b-104">Este tópico descreve a aplicação de backups de log de transações como parte da restauração de um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9522b-104">This topic describes applying transaction log backups as part of restoring a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="9522b-105">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="9522b-105">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="9522b-106">Requisitos para restaurar backups de log de transações</span><span class="sxs-lookup"><span data-stu-id="9522b-106">Requirements for Restoring Transaction Log Backups</span></span>](#Requirements)  
  
-   [<span data-ttu-id="9522b-107">Recuperação e logs de transações</span><span class="sxs-lookup"><span data-stu-id="9522b-107">Recovery and Transaction Logs</span></span>](#RecoveryAndTlogs)  
  
-   [<span data-ttu-id="9522b-108">Usando backups de log para restaurar até o ponto de falha</span><span class="sxs-lookup"><span data-stu-id="9522b-108">Using Log Backups to Restore to the Point of Failure</span></span>](#PITrestore)  
  
-   [<span data-ttu-id="9522b-109">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9522b-109">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="requirements-for-restoring-transaction-log-backups"></a><a name="Requirements"></a><span data-ttu-id="9522b-110">Requisitos para restaurar backups de log de transações</span><span class="sxs-lookup"><span data-stu-id="9522b-110">Requirements for Restoring Transaction Log Backups</span></span>  
 <span data-ttu-id="9522b-111">Para aplicar um backup de log de transações, devem ser atendidos os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="9522b-111">To apply a transaction log backup, the following requirements must be met:</span></span>  
  
-   <span data-ttu-id="9522b-112">**backups de log suficientes para uma sequência de restauração:** Você deve ter backups de registros de log suficientes para concluir uma sequência de restauração.</span><span class="sxs-lookup"><span data-stu-id="9522b-112">**Enough Log Backups for a Restore Sequence :** You must have enough log records backed up to complete a restore sequence.</span></span> <span data-ttu-id="9522b-113">Os backups de log necessários, incluindo o [backup da parte final do log](tail-log-backups-sql-server.md) , quando necessário, devem estar disponíveis antes do início da sequência de restauração.</span><span class="sxs-lookup"><span data-stu-id="9522b-113">The necessary log backups, including the [tail-log backup](tail-log-backups-sql-server.md) where required, must be available before the start of the restore sequence.</span></span>  
  
-   <span data-ttu-id="9522b-114">**Ordem de restauração correta:**  O backup de banco de dados completo imediatamente anterior ou backup de banco de dados diferencial deve ser restaurado primeiro.</span><span class="sxs-lookup"><span data-stu-id="9522b-114">**Correct restore order:**  The immediately previous full database backup or differential database backup must be restored first.</span></span> <span data-ttu-id="9522b-115">Em seguida, todos os logs de transações criados após o backup de banco de dados completo ou diferencial devem ser restaurados em ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="9522b-115">Then, all transaction logs that are created after that full or differential database backup must be restored in chronological order.</span></span> <span data-ttu-id="9522b-116">Se um backup de log de transações nessa cadeia de logs for perdido ou danificado, você poderá restaurar apenas os logs de transações anteriores ao log ausente.</span><span class="sxs-lookup"><span data-stu-id="9522b-116">If a transaction log backup in this log chain is lost or damaged, you can restore only transaction logs before the missing transaction log.</span></span>  
  
-   <span data-ttu-id="9522b-117">**Banco de dados ainda não recuperado:**  O banco de dados não poderá ser recuperado até que o log de transações final seja aplicado.</span><span class="sxs-lookup"><span data-stu-id="9522b-117">**Database not yet recovered:**  The database cannot be recovered until after the final transaction log has been applied.</span></span> <span data-ttu-id="9522b-118">Se você recuperar o banco de dados depois de restaurar um dos backups de log de transações intermediários antes do final da cadeia de logs, não poderá restaurar o banco de dados além desse ponto sem restaurar a sequência completa, começando com o backup de banco de dados completo.</span><span class="sxs-lookup"><span data-stu-id="9522b-118">If you recover the database after restoring one of the intermediate transaction log backups, that before the end of the log chain, you cannot restore the database past that point without restarting the complete restore sequence, starting with the full database backup.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="9522b-119">Uma prática recomendada é restaurar todos os backups de log (RESTORE LOG *database_name* WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="9522b-119">A best practice is to restore all the log backups (RESTORE LOG *database_name* WITH NORECOVERY).</span></span> <span data-ttu-id="9522b-120">Em seguida, depois de restaurar o último backup de log, recupere o banco de dados em uma operação separada (RESTORE DATABASE *database_name* WITH RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="9522b-120">Then, after restoring the last log backup, recover the database in a separate operation (RESTORE DATABASE *database_name* WITH RECOVERY).</span></span>  
  
##  <a name="recovery-and-transaction-logs"></a><a name="RecoveryAndTlogs"></a><span data-ttu-id="9522b-121">Recuperação e logs de transações</span><span class="sxs-lookup"><span data-stu-id="9522b-121">Recovery and Transaction Logs</span></span>  
 <span data-ttu-id="9522b-122">Ao concluir a operação de restauração e recuperar o banco de dados, a recuperação reverte todas as transações incompletas.</span><span class="sxs-lookup"><span data-stu-id="9522b-122">When you finish the restore operation and recover the database, recovery rolls back all incomplete transactions.</span></span> <span data-ttu-id="9522b-123">Isso é conhecido como o *fase Desfazer*.</span><span class="sxs-lookup"><span data-stu-id="9522b-123">This is known as the *undo phase*.</span></span> <span data-ttu-id="9522b-124">A reversão é necessária para restaurar a integridade do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9522b-124">Rolling back is required to restore the integrity of the database.</span></span> <span data-ttu-id="9522b-125">Depois da reversão, o banco de dados fica online e mais nenhum backup de log de transações pode ser aplicado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9522b-125">After rollback, the database goes online, and no more transaction log backups can be applied to the database.</span></span>  
  
 <span data-ttu-id="9522b-126">Por exemplo, uma série de backups de log de transações contém uma transação de execução longa.</span><span class="sxs-lookup"><span data-stu-id="9522b-126">For example, a series of transaction log backups contain a long-running transaction.</span></span> <span data-ttu-id="9522b-127">O início da transação é registrado no primeiro backup de log de transações, mas o término da transação é registrado no segundo backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="9522b-127">The start of the transaction is recorded in the first transaction log backup, but the end of the transaction is recorded in the second transaction log backup.</span></span> <span data-ttu-id="9522b-128">Não há registro de uma operação de confirmação ou reversão no primeiro backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="9522b-128">There is no record of a commit or rollback operation in the first transaction log backup.</span></span> <span data-ttu-id="9522b-129">Se uma operação de recuperação for executada quando o primeiro backup de log de transações for aplicado, a transação de longa execução será tratada como incompleta e as modificações de dados registradas no primeiro backup de log de transações serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="9522b-129">If a recovery operation runs when the first transaction log backup is applied, the long-running transaction is treated as incomplete, and data modifications recorded in the first transaction log backup for the transaction are rolled back.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9522b-130">não permite que o segundo backup de log de transação seja aplicado depois deste ponto.</span><span class="sxs-lookup"><span data-stu-id="9522b-130">does not allow for the second transaction log backup to be applied after this point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9522b-131">Em algumas circunstâncias, você pode adicionar um arquivo explicitamente durante a restauração do log.</span><span class="sxs-lookup"><span data-stu-id="9522b-131">In some circumstances, you can explicitly add a file during log restore.</span></span>  
  
##  <a name="using-log-backups-to-restore-to-the-point-of-failure"></a><a name="PITrestore"></a><span data-ttu-id="9522b-132">Usando backups de log para restaurar até o ponto de falha</span><span class="sxs-lookup"><span data-stu-id="9522b-132">Using Log Backups to Restore to the Point of Failure</span></span>  
 <span data-ttu-id="9522b-133">Considere a seguinte sequência de eventos.</span><span class="sxs-lookup"><span data-stu-id="9522b-133">Assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="9522b-134">Hora</span><span class="sxs-lookup"><span data-stu-id="9522b-134">Time</span></span>|<span data-ttu-id="9522b-135">Evento</span><span class="sxs-lookup"><span data-stu-id="9522b-135">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="9522b-136">8:00h</span><span class="sxs-lookup"><span data-stu-id="9522b-136">8:00 A.M.</span></span>|<span data-ttu-id="9522b-137">Faça um backup do banco de dados para criar um backup completo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9522b-137">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="9522b-138">Meio-dia</span><span class="sxs-lookup"><span data-stu-id="9522b-138">Noon</span></span>|<span data-ttu-id="9522b-139">Backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="9522b-139">Back up transaction log.</span></span>|  
|<span data-ttu-id="9522b-140">16:00h</span><span class="sxs-lookup"><span data-stu-id="9522b-140">4:00 P.M.</span></span>|<span data-ttu-id="9522b-141">Backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="9522b-141">Back up transaction log.</span></span>|  
|<span data-ttu-id="9522b-142">18:00h</span><span class="sxs-lookup"><span data-stu-id="9522b-142">6:00 P.M.</span></span>|<span data-ttu-id="9522b-143">Faça um backup do banco de dados para criar um backup completo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9522b-143">Back up database to create a full database backup.</span></span>|  
|<span data-ttu-id="9522b-144">20:00h</span><span class="sxs-lookup"><span data-stu-id="9522b-144">8:00 P.M.</span></span>|<span data-ttu-id="9522b-145">Backup de log de transações.</span><span class="sxs-lookup"><span data-stu-id="9522b-145">Back up transaction log.</span></span>|  
|<span data-ttu-id="9522b-146">21h45</span><span class="sxs-lookup"><span data-stu-id="9522b-146">9:45 P.M.</span></span>|<span data-ttu-id="9522b-147">Ocorre falha.</span><span class="sxs-lookup"><span data-stu-id="9522b-147">Failure occurs.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="9522b-148">Para obter uma explicação dessa sequência de exemplo de backups, veja [Backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9522b-148">For an explanation of this example sequence of backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="9522b-149">Para restaurar o banco de dados a seu estado às 21h45</span><span class="sxs-lookup"><span data-stu-id="9522b-149">To restore the database to its state at 9:45 P.M.</span></span> <span data-ttu-id="9522b-150">(o ponto de falha), um dos seguintes procedimentos alternativos pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="9522b-150">(the point of failure), either of the following alternative procedures can be used:</span></span>  
  
 <span data-ttu-id="9522b-151">**Alternativa 1: restaurar o banco de dados usando o backup de banco de dados completo mais recente**</span><span class="sxs-lookup"><span data-stu-id="9522b-151">**Alternative 1: Restore the database by using the most recent full database backup**</span></span>  
  
1.  <span data-ttu-id="9522b-152">Crie um backup do final do log de transações atualmente ativo a partir do ponto de falha.</span><span class="sxs-lookup"><span data-stu-id="9522b-152">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="9522b-153">Não restaure o backup de banco de dados completo das 8h</span><span class="sxs-lookup"><span data-stu-id="9522b-153">Do not restore the 8:00 A.M.</span></span> <span data-ttu-id="9522b-154">18h.</span><span class="sxs-lookup"><span data-stu-id="9522b-154">full database backup.</span></span> <span data-ttu-id="9522b-155">Restaure o backup de banco de dados completo mais recente das</span><span class="sxs-lookup"><span data-stu-id="9522b-155">Instead, restore the more recent 6:00 P.M.</span></span> <span data-ttu-id="9522b-156">18h e aplique o backup de log das</span><span class="sxs-lookup"><span data-stu-id="9522b-156">full database backup, and then apply the 8:00 P.M.</span></span> <span data-ttu-id="9522b-157">20h e o backup da parte final do log.</span><span class="sxs-lookup"><span data-stu-id="9522b-157">log backup and the tail-log backup.</span></span>  
  
 <span data-ttu-id="9522b-158">**Alternativa 2: restaurar o banco de dados usando o backup de banco de dados completo mais antigo**</span><span class="sxs-lookup"><span data-stu-id="9522b-158">**Alternative 2: Restore the database by using an earlier full database backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9522b-159">Esse processo alternativo será útil se um problema impedir o uso do backup de banco de dados completo</span><span class="sxs-lookup"><span data-stu-id="9522b-159">This alternative process is useful if a problem prevents you from using the 6:00 P.M.</span></span> <span data-ttu-id="9522b-160">18h.</span><span class="sxs-lookup"><span data-stu-id="9522b-160">full database backup.</span></span> <span data-ttu-id="9522b-161">Esse processo leva mais muito tempo do que restaurar o backup de banco de dados completo das</span><span class="sxs-lookup"><span data-stu-id="9522b-161">This process takes longer than restoring from the 6:00 P.M.</span></span> <span data-ttu-id="9522b-162">18h.</span><span class="sxs-lookup"><span data-stu-id="9522b-162">full database backup.</span></span>  
  
1.  <span data-ttu-id="9522b-163">Crie um backup do final do log de transações atualmente ativo a partir do ponto de falha.</span><span class="sxs-lookup"><span data-stu-id="9522b-163">Create a tail-log backup of the currently active transaction log as of the point of failure.</span></span>  
  
2.  <span data-ttu-id="9522b-164">Restaure o backup de banco de dados completo das 8h</span><span class="sxs-lookup"><span data-stu-id="9522b-164">Restore the 8:00 A.M.</span></span> <span data-ttu-id="9522b-165">e, depois, restaure todos os quatro backups de log de transações em sequência.</span><span class="sxs-lookup"><span data-stu-id="9522b-165">full database backup, and then restore all four transaction log backups in sequence.</span></span> <span data-ttu-id="9522b-166">Isso efetua roll forward de todas as transações completas até 21h45.</span><span class="sxs-lookup"><span data-stu-id="9522b-166">This rolls forward all completed transactions up to 9:45 P.M.</span></span>  
  
     <span data-ttu-id="9522b-167">Essa alternativa mostra a segurança redundante oferecida pela manutenção de uma cadeia de backups de log de transações em uma série de backups de banco de dados completos.</span><span class="sxs-lookup"><span data-stu-id="9522b-167">This alternative points out the redundant security offered by maintaining a chain of transaction log backups across a series of full database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9522b-168">Em alguns casos, você pode usar também logs de transações para restaurar um banco de dados até um point-in-time específico.</span><span class="sxs-lookup"><span data-stu-id="9522b-168">In some cases, you can also use transaction logs to restore a database to a specific point in time.</span></span> <span data-ttu-id="9522b-169">Para obter mais informações, veja [Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="9522b-169">For more information, [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9522b-170">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9522b-170">Related Tasks</span></span>  
 <span data-ttu-id="9522b-171">**Para aplicar um backup de log de transações**</span><span class="sxs-lookup"><span data-stu-id="9522b-171">**To apply a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="9522b-172">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9522b-172">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
 <span data-ttu-id="9522b-173">**Para restaurar até seu ponto de recuperação**</span><span class="sxs-lookup"><span data-stu-id="9522b-173">**To restore to your recovery point**</span></span>  
  
-   [<span data-ttu-id="9522b-174">Restaurar um banco de dados até o ponto de falha no modelo de recuperação completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9522b-174">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="9522b-175">Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="9522b-175">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   <span data-ttu-id="9522b-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="9522b-176"><xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A> (SMO)</span></span>  
  
-   [<span data-ttu-id="9522b-177">Recuperação de bancos de dados relacionados que contêm transação marcada</span><span class="sxs-lookup"><span data-stu-id="9522b-177">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
-   [<span data-ttu-id="9522b-178">Recuperar para um número de sequência de log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9522b-178">Recover to a Log Sequence Number &#40;SQL Server&#41;</span></span>](recover-to-a-log-sequence-number-sql-server.md)  
  
 <span data-ttu-id="9522b-179">**Para recuperar um banco de dados depois de restaurar backups usando WITH NORECOVERY**</span><span class="sxs-lookup"><span data-stu-id="9522b-179">**To recover a database after restoring backups using WITH NORECOVERY**</span></span>  
  
-   [<span data-ttu-id="9522b-180">Recuperar um banco de dados sem restaurar dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9522b-180">Recover a Database Without Restoring Data &#40;Transact-SQL&#41;</span></span>](recover-a-database-without-restoring-data-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="9522b-181">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9522b-181">See Also</span></span>  
 [<span data-ttu-id="9522b-182">O log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9522b-182">The Transaction Log &#40;SQL Server&#41;</span></span>](../logs/the-transaction-log-sql-server.md)  
  
  
