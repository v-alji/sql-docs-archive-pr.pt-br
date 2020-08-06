---
title: Recuperação de bancos de dados relacionados que contêm uma transação marcada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction logs [SQL Server], marks
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- transactions [SQL Server], recovering to a mark
- database recovery [SQL Server]
- marked transactions [SQL Server], restoring
- database restores [SQL Server], point in time
ms.assetid: 77a0d9c0-978a-4891-8b0d-a4256c81c3f8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b968322f92c7a135adb5fd0733b5774e7562bc39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683566"
---
# <a name="recovery-of-related--databases-that-contain-marked-transaction"></a><span data-ttu-id="61d30-102">Recuperação de bancos de dados relacionados que contêm transação marcada</span><span class="sxs-lookup"><span data-stu-id="61d30-102">Recovery of Related  Databases That Contain Marked Transaction</span></span>
  <span data-ttu-id="61d30-103">Este tópico é relevante apenas para os bancos de dados que contêm transações marcadas e que usam modelos de recuperação bulk-logged ou completos.</span><span class="sxs-lookup"><span data-stu-id="61d30-103">This topic is relevant only for databases that contain marked transactions and that use the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="61d30-104">Para obter informações sobre os requisitos de restauração para um ponto de recuperação específico, veja [Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="61d30-104">For information about the requirements for restoring to a specific recovery point, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="61d30-105">dá suporte à inserção de marcas nomeadas no log de transações, permitindo a recuperação nessa marca específica.</span><span class="sxs-lookup"><span data-stu-id="61d30-105">supports inserting named marks into the transaction log to allow recovery to that specific mark.</span></span> <span data-ttu-id="61d30-106">As marcas de log são transações específicas e são inseridas apenas se as suas transações associadas forem confirmadas.</span><span class="sxs-lookup"><span data-stu-id="61d30-106">Log marks are transaction specific and are inserted only if their associated transaction commits.</span></span> <span data-ttu-id="61d30-107">Desse modo, as marcas podem ser ligadas ao trabalho específico e você pode recuperá-las em um ponto que inclua ou exclua esse trabalho.</span><span class="sxs-lookup"><span data-stu-id="61d30-107">As a result, marks can be tied to specific work, and you can recover to a point that includes or excludes this work.</span></span>  
  
 <span data-ttu-id="61d30-108">Antes de você inserir marcas nomeadas no log de transações, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="61d30-108">Before you insert named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="61d30-109">Como as marcas de transação consomem espaço de log, só as use para transações que têm um papel significativo na estratégia de recuperação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="61d30-109">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="61d30-110">Depois que a transação marcada é confirmada, uma linha é inserida na tabela [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) no **msdb**.</span><span class="sxs-lookup"><span data-stu-id="61d30-110">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="61d30-111">Se uma transação marcada abrange vários bancos de dados no mesmo servidor de banco de dados ou em servidores diferentes, as marcas devem ser registradas nos logs de todos os bancos de dados afetados.</span><span class="sxs-lookup"><span data-stu-id="61d30-111">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span> <span data-ttu-id="61d30-112">Para obter mais informações, veja [Usar transações marcadas para recuperar bancos de dados relacionados de forma consistente &#40;Modelo de recuperação completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="61d30-112">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61d30-113">Para obter informações sobre como marcar transações, veja [Usar transações marcadas para recuperar bancos de dados relacionados de forma consistente &#40;Modelo de recuperação completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="61d30-113">For information about how to mark transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-inserting-named-marks-into-a-transaction-log"></a><span data-ttu-id="61d30-114">Sintaxe Transact-SQL para inserir marcas nomeadas em um log de transações</span><span class="sxs-lookup"><span data-stu-id="61d30-114">Transact-SQL Syntax for Inserting Named Marks into a Transaction Log</span></span>  
 <span data-ttu-id="61d30-115">Para inserir marcas nos logs de transações, use a instrução [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) e a cláusula WITH MARK [*descrição*].</span><span class="sxs-lookup"><span data-stu-id="61d30-115">To insert marks into the transaction logs, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="61d30-116">A marca é nomeada igual à transação.</span><span class="sxs-lookup"><span data-stu-id="61d30-116">The mark is named the same as the transaction.</span></span> <span data-ttu-id="61d30-117">A *descrição* opcional é uma descrição textual da marca, não o nome da marca.</span><span class="sxs-lookup"><span data-stu-id="61d30-117">The optional *description* is a textual description of the mark, not the mark name.</span></span> <span data-ttu-id="61d30-118">Por exemplo, o nome da transação e da marca criado na seguinte instrução `BEGIN TRANSACTION` é `Tx1`:</span><span class="sxs-lookup"><span data-stu-id="61d30-118">For example, the name of both the transaction and the mark that is created in the following `BEGIN TRANSACTION` statement is `Tx1`:</span></span>  
  
```wmimof  
BEGIN TRANSACTION Tx1 WITH MARK 'not the mark name, just a description'    
```  
  
 <span data-ttu-id="61d30-119">O log de transações registra o nome da marca (nome da transação), descrição, banco de dados, usuário, informações `datetime` e o LSN (Log Sequence Number).</span><span class="sxs-lookup"><span data-stu-id="61d30-119">The transaction log records the mark name (transaction name), description, database, user, `datetime` information, and the log sequence number (LSN).</span></span> <span data-ttu-id="61d30-120">As informações `datetime` são usadas com o nome da marca exclusivamente para identificar a marca.</span><span class="sxs-lookup"><span data-stu-id="61d30-120">The `datetime` information is used with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="61d30-121">Para obter informações sobre como inserir uma marca em uma transação que abrange vários bancos de dados, veja [Usar transações marcadas para recuperar bancos de dados relacionados de forma consistente &#40;Modelo de recuperação completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="61d30-121">For information about how to insert a mark into a transaction that spans multiple databases, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-recovering-to-a-mark"></a><span data-ttu-id="61d30-122">Sintaxe Transact-SQL para recuperar a uma marca</span><span class="sxs-lookup"><span data-stu-id="61d30-122">Transact-SQL Syntax for Recovering to a Mark</span></span>  
 <span data-ttu-id="61d30-123">Quando você assinala uma transação marcada usando uma instrução[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql), é possível usar uma das seguintes cláusulas para parar na marca ou imediatamente antes dela:</span><span class="sxs-lookup"><span data-stu-id="61d30-123">When you target a marked transaction by using a[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql)statement, you can use one the following clauses to stop at or immediately before the mark:</span></span>  
  
-   <span data-ttu-id="61d30-124">Use a cláusula WITH STOPATMARK = **' *`<mark_name>`* '** para especificar que a transação marcada é o ponto de recuperação.</span><span class="sxs-lookup"><span data-stu-id="61d30-124">Use the WITH STOPATMARK = **'*`<mark_name>`*'** clause to specify that the marked transaction is the recovery point.</span></span>  
  
     <span data-ttu-id="61d30-125">O STOPATMARK roll-forward até a marca e inclui a transação marcada no roll-forward.</span><span class="sxs-lookup"><span data-stu-id="61d30-125">STOPATMARK rolls forward to the mark and includes the marked transaction in the roll forward.</span></span>  
  
-   <span data-ttu-id="61d30-126">Use a cláusula WITH STOPBEFOREMARK = **' *`<mark_name>`* '** para especificar que o registro de log que está imediatamente antes da marca é o ponto de recuperação.</span><span class="sxs-lookup"><span data-stu-id="61d30-126">Use the WITH STOPBEFOREMARK = **'*`<mark_name>`*'** clause to specify that the log record that is immediately before the mark is the recovery point.</span></span>  
  
     <span data-ttu-id="61d30-127">O STOPATMARK roll-forward até a marca e exclui a transação marcada do roll-forward.</span><span class="sxs-lookup"><span data-stu-id="61d30-127">STOPBEFOREMARK rolls forward to the mark and excludes marked the transaction from the roll forward.</span></span>  
  
 <span data-ttu-id="61d30-128">Ambas as opções STOPATMARK e STOPBEFOREMARK dão suporte a uma cláusula opcional AFTER *datetime* .</span><span class="sxs-lookup"><span data-stu-id="61d30-128">The STOPATMARK and STOPBEFOREMARK options both support an optional AFTER *datetime* clause.</span></span> <span data-ttu-id="61d30-129">Quando *datetime* é usado, os nomes da marca não precisam ser exclusivos.</span><span class="sxs-lookup"><span data-stu-id="61d30-129">When *datetime* is used, mark names do not have to be unique.</span></span>  
  
 <span data-ttu-id="61d30-130">Se AFTER *datetime* for omitido, o roll forward será interrompido na primeira marca que tem o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="61d30-130">If AFTER *datetime* is omitted, roll forward stops at the first mark that has the specified name.</span></span> <span data-ttu-id="61d30-131">Se AFTER *datetime* for especificado, o roll forward será interrompido na primeira marca que tem o nome especificado, exatamente em *datetime*ou após ele.</span><span class="sxs-lookup"><span data-stu-id="61d30-131">If AFTER *datetime* is specified, roll forward stops at the first mark that has the specified name, exactly at or after *datetime*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61d30-132">Como em todas as operações de restauração point-in-time, não é permitido recuperar a uma marca quando o banco de dados estiver passando por operações com log de operações em massa.</span><span class="sxs-lookup"><span data-stu-id="61d30-132">As in all point-in-time restore operations, recovering to a mark is disallowed when the database is undergoing operations that are bulk-logged.</span></span>  
  
 <span data-ttu-id="61d30-133">**Para restaurar a uma transação marcada**</span><span class="sxs-lookup"><span data-stu-id="61d30-133">**To restore to a marked transaction**</span></span>  
  
 [<span data-ttu-id="61d30-134">Restaurar um banco de dados para uma transação marcada &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="61d30-134">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
 [<span data-ttu-id="61d30-135">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61d30-135">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
### <a name="preparing-the-log-backups"></a><span data-ttu-id="61d30-136">Preparando os backups de log</span><span class="sxs-lookup"><span data-stu-id="61d30-136">Preparing the Log Backups</span></span>  
 <span data-ttu-id="61d30-137">Para este exemplo, uma estratégia de backup apropriada para estes bancos de dados relacionados seria a seguinte:</span><span class="sxs-lookup"><span data-stu-id="61d30-137">For this example, an appropriate backup strategy for these related databases would be the following:</span></span>  
  
1.  <span data-ttu-id="61d30-138">Use o modelo de recuperação completa para ambos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="61d30-138">Use the full recovery model for both databases.</span></span>  
  
2.  <span data-ttu-id="61d30-139">Crie um backup completo de cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="61d30-139">Create a full backup of each database.</span></span>  
  
     <span data-ttu-id="61d30-140">Os backups dos bancos de dados podem ser feitos consecutivamente ou simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="61d30-140">The databases can be backed up sequentially or simultaneously.</span></span>  
  
3.  <span data-ttu-id="61d30-141">Antes de fazer o backup do log de transações, marque uma transação que execute em todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="61d30-141">Before backing up the transaction log, mark a transaction that executes in all databases.</span></span> <span data-ttu-id="61d30-142">Para obter informações sobre como criar as transações marcadas, veja [Usar transações marcadas para recuperar bancos de dados relacionados de forma consistente &#40;Modelo de recuperação completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="61d30-142">For information about how to create the marked transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
4.  <span data-ttu-id="61d30-143">Faça o backup do log de transações em cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="61d30-143">Back up the transaction log on each database.</span></span>  
  
### <a name="recovering-the-database-to-a-marked-transaction"></a><span data-ttu-id="61d30-144">Recuperando um banco de dados a uma transação marcada</span><span class="sxs-lookup"><span data-stu-id="61d30-144">Recovering the Database to a Marked Transaction</span></span>  
 <span data-ttu-id="61d30-145">**Para restaurar o backup**</span><span class="sxs-lookup"><span data-stu-id="61d30-145">**To restore the backup**</span></span>  
  
1.  <span data-ttu-id="61d30-146">Crie [backups da parte final do log](tail-log-backups-sql-server.md) dos bancos de dados não danificados, se possível.</span><span class="sxs-lookup"><span data-stu-id="61d30-146">Create [tail-log backups](tail-log-backups-sql-server.md) of the undamaged databases, if possible.</span></span>  
  
2.  <span data-ttu-id="61d30-147">Restaure o backup completo mais recente do banco de dados de cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="61d30-147">Restore the most recent full database backup of each database.</span></span>  
  
3.  <span data-ttu-id="61d30-148">Identifique a transação marcada mais recente disponível em todos os backups de log de transações.</span><span class="sxs-lookup"><span data-stu-id="61d30-148">Identify the most recent marked transaction that is available in all of the transaction log backups.</span></span> <span data-ttu-id="61d30-149">Essa informação é armazenada na tabela **logmarkhistory** no banco de dados **msdb** em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="61d30-149">This information is stored in the **logmarkhistory** table in the **msdb** database on each server.</span></span>  
  
4.  <span data-ttu-id="61d30-150">Identifique os backups de log para todos os bancos de dados relacionados que contêm essa marca.</span><span class="sxs-lookup"><span data-stu-id="61d30-150">Identify the log backups for all related databases that contain this mark.</span></span>  
  
5.  <span data-ttu-id="61d30-151">Restaure cada backup de log, parando na transação marcada.</span><span class="sxs-lookup"><span data-stu-id="61d30-151">Restore each log backup, stopping at the marked transaction.</span></span>  
  
6.  <span data-ttu-id="61d30-152">Recupere cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="61d30-152">Recover each database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d30-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61d30-153">See Also</span></span>  
 <span data-ttu-id="61d30-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="61d30-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="61d30-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="61d30-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="61d30-156">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="61d30-156">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="61d30-157">[Usar transações marcadas para recuperar bancos de dados relacionados de forma consistente &#40;Modelo de recuperação completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span><span class="sxs-lookup"><span data-stu-id="61d30-157">[Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span></span>  
 <span data-ttu-id="61d30-158">[Visão geral de restauração e recuperação &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="61d30-158">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="61d30-159">[Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="61d30-159">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="61d30-160">Planejar e executar sequências de restauração &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="61d30-160">Plan and Perform Restore Sequences &#40;Full Recovery Model&#41;</span></span>](plan-and-perform-restore-sequences-full-recovery-model.md)  
  
  
