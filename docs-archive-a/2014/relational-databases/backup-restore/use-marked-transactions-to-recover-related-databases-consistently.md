---
title: Usar transações marcadas para recuperar bancos de dados relacionados consistentemente (modelo de recuperação completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction marks [SQL Server]
- marked transactions [SQL Server]
- database restores [SQL Server], inserting transaction marks for
- recovery [SQL Server], related databases
- restoring databases [SQL Server], related database recovery
- database restores [SQL Server], related databases
- marked transactions [SQL Server], creating
- BEGIN TRAN...WITH MARK statement
- two-phase commit
ms.assetid: 50a73574-1a69-448e-83dd-9abcc7cb7e1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8dd368ad14f6e521fb8d504bdea774e3088c2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683561"
---
# <a name="use-marked-transactions-to-recover-related-databases-consistently-full-recovery-model"></a><span data-ttu-id="12586-102">Usar transações marcadas para recuperar bancos de dados relacionados consistentemente (modelo de recuperação completa)</span><span class="sxs-lookup"><span data-stu-id="12586-102">Use Marked Transactions to Recover Related Databases Consistently (Full Recovery Model)</span></span>
  <span data-ttu-id="12586-103">Este tópico é relevante apenas para bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que estejam usando modelos de recuperação completa ou bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="12586-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="12586-104">Ao fazer atualizações relacionadas a dois ou mais bancos de dados, *bancos de dados relacionados*, você pode usar marcas de transação para recuperá-los a um ponto logicamente consistente.</span><span class="sxs-lookup"><span data-stu-id="12586-104">When you make related updates to two or more databases, *related databases*, you can use transaction marks to recover them to a logically consistent point.</span></span> <span data-ttu-id="12586-105">Contudo, essa recuperação perde qualquer transação confirmada após a marca usada como ponto de recuperação.</span><span class="sxs-lookup"><span data-stu-id="12586-105">However, this recovery loses any transaction that is committed after the mark that was used as the recovery point.</span></span> <span data-ttu-id="12586-106">A marcação de uma transação é indicada apenas quando se está testando bancos de dados relacionados, ou se está disposto a perder transações confirmadas recentemente.</span><span class="sxs-lookup"><span data-stu-id="12586-106">Marking transactions is suitable only when you are testing related databases or when you are willing to lose recently committed transactions.</span></span>  
  
 <span data-ttu-id="12586-107">A marcação de transações relacionadas rotineiramente em todo banco de dados relacionado estabelece uma série de pontos de recuperação comuns nesses bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="12586-107">Routinely marking related transactions in every related database establishes a series of common recovery points in the databases.</span></span> <span data-ttu-id="12586-108">As marcas de transação são gravadas no log de transações e incluídas em backups de log.</span><span class="sxs-lookup"><span data-stu-id="12586-108">The transaction marks are recorded in the transaction log and included in log backups.</span></span> <span data-ttu-id="12586-109">Em caso de desastre, você pode restaurar cada um dos bancos de dados para a mesma marca de transação para recuperá-los em um ponto consistente.</span><span class="sxs-lookup"><span data-stu-id="12586-109">In the event of a disaster, you can restore each of the databases to the same transaction mark to recover them to a consistent point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12586-110">Backups de log em bancos de dados diferentes podem ser criados independentemente um do outro, e não precisam ser simultâneos.</span><span class="sxs-lookup"><span data-stu-id="12586-110">Log backups on the different databases can be created independently of each other and do not have to be simultaneous.</span></span>  
  
 <span data-ttu-id="12586-111">A recuperação de bancos de dados relacionados nos seguintes cenários exige que você já tenha marcado as transações em todos os bancos de dados relacionados:</span><span class="sxs-lookup"><span data-stu-id="12586-111">Recovering related databases in the following scenarios requires that you have already marked transactions in every related database:</span></span>  
  
-   <span data-ttu-id="12586-112">Um ou mais logs de transações são destruídos.</span><span class="sxs-lookup"><span data-stu-id="12586-112">One or more transaction logs are destroyed.</span></span> <span data-ttu-id="12586-113">Você deve restaurar o conjunto de bancos de dados em um estado consistente no momento do último backup de log.</span><span class="sxs-lookup"><span data-stu-id="12586-113">You have to restore the set of databases to a consistent state at the time of your last log backup.</span></span>  
  
-   <span data-ttu-id="12586-114">Você deve restaurar o conjunto inteiro de bancos de dados a um estado mutuamente consistente em algum point-in-time anterior.</span><span class="sxs-lookup"><span data-stu-id="12586-114">You have to restore the entire set of databases to a mutually consistent state at some earlier point in time.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12586-115">Você pode fazer uma recuperação dos bancos de dados relacionados apenas para uma transação marcada, não uma resturação pontual.</span><span class="sxs-lookup"><span data-stu-id="12586-115">You can recover related databases only to a marked transaction, not to a specific point in time.</span></span>  
  
 <span data-ttu-id="12586-116">Para obter informações sobre como criar transações de marcação, consulte "Criando transações marcadas", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="12586-116">For information about how to create marking transactions, see "Creating the Marked Transactions," later in this topic.</span></span>  
  
## <a name="typical-scenario-for-using-marked-transactions"></a><span data-ttu-id="12586-117">Cenário típico para o uso de transações marcadas</span><span class="sxs-lookup"><span data-stu-id="12586-117">Typical Scenario for Using Marked Transactions</span></span>  
 <span data-ttu-id="12586-118">Um cenário típico para o uso de transações marcadas inclui as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="12586-118">A typical scenario for using marked transactions includes the following steps:</span></span>  
  
1.  <span data-ttu-id="12586-119">Crie um backup de banco de dados completo ou diferencial de cada um dos bancos de dados relacionados.</span><span class="sxs-lookup"><span data-stu-id="12586-119">Create a full or differential database backup of each of the related databases.</span></span>  
  
2.  <span data-ttu-id="12586-120">Marque um bloco de transação em todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="12586-120">Mark a transaction block in all the databases.</span></span>  
  
3.  <span data-ttu-id="12586-121">Faça o backup de log de transações de todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="12586-121">Back up the transaction log for all the databases.</span></span>  
  
4.  <span data-ttu-id="12586-122">Restaure backups de bancos de dados WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="12586-122">Restore database backups WITH NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="12586-123">Restaure logs WITH STOPATMARK.</span><span class="sxs-lookup"><span data-stu-id="12586-123">Restore logs WITH STOPATMARK.</span></span>  
  
## <a name="considerations-for-using-marked-transactions"></a><span data-ttu-id="12586-124">Considerações para usar transações marcadas</span><span class="sxs-lookup"><span data-stu-id="12586-124">Considerations for Using Marked Transactions</span></span>  
 <span data-ttu-id="12586-125">Antes de inserir marcas nomeadas no log de transações, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12586-125">Before inserting named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="12586-126">Como as marcas de transação consomem espaço de log, só as use para transações que têm um papel significativo na estratégia de recuperação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="12586-126">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="12586-127">Depois que a transação marcada é confirmada, uma linha é inserida na tabela [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) no **msdb**.</span><span class="sxs-lookup"><span data-stu-id="12586-127">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="12586-128">Se uma transação marcada abrange vários bancos de dados no mesmo servidor de banco de dados ou em servidores diferentes, as marcas devem ser registradas nos logs de todos os bancos de dados afetados.</span><span class="sxs-lookup"><span data-stu-id="12586-128">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span>  
  
## <a name="creating-the-marked-transactions"></a><span data-ttu-id="12586-129">Criando as transações marcadas</span><span class="sxs-lookup"><span data-stu-id="12586-129">Creating the Marked Transactions</span></span>  
 <span data-ttu-id="12586-130">Para criar uma transação marcada, use a instrução [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) e a cláusula WITH MARK [*descrição*].</span><span class="sxs-lookup"><span data-stu-id="12586-130">To create a marked transaction, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="12586-131">A *descrição* opcional é uma descrição textual da marca.</span><span class="sxs-lookup"><span data-stu-id="12586-131">The optional *description* is a textual description of the mark.</span></span> <span data-ttu-id="12586-132">Um nome de marca da transação é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="12586-132">A mark name for the transaction is required.</span></span> <span data-ttu-id="12586-133">Um nome de marca pode ser usado novamente.</span><span class="sxs-lookup"><span data-stu-id="12586-133">A mark name can be reused.</span></span> <span data-ttu-id="12586-134">O log de transações registra o nome da marca, a descrição, o banco de dados, o usuário, as informações de data e hora e o LSN (número de sequência de log).</span><span class="sxs-lookup"><span data-stu-id="12586-134">The transaction log records the mark name, description, database, user, datetime information, and the log sequence number (LSN).</span></span> <span data-ttu-id="12586-135">As informações de data e hora são usadas junto com o nome da marca para identificar a marca com exclusividade.</span><span class="sxs-lookup"><span data-stu-id="12586-135">The datetime information is used along with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="12586-136">**Para criar transações marcadas em um conjunto de bancos de dados:**</span><span class="sxs-lookup"><span data-stu-id="12586-136">**To create marked transactions in a set of databases:**</span></span>  
  
1.  <span data-ttu-id="12586-137">Nomeie a transação na instrução BEGIN TRAN e use a cláusula WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="12586-137">Name the transaction in the BEGIN TRAN statement and use the WITH MARK clause</span></span>  
  
     <span data-ttu-id="12586-138">Você pode aninhar a instrução BEGIN TRAN *new_mark_name* WITH MARK dentro de uma transação existente.</span><span class="sxs-lookup"><span data-stu-id="12586-138">You can nest the statement BEGIN TRAN *new_mark_name* WITH MARK within an existing transaction.</span></span> <span data-ttu-id="12586-139">O valor de *new_mark_name* é o nome da marca para a transação, mesmo se a transação tiver um nome de transação.</span><span class="sxs-lookup"><span data-stu-id="12586-139">The value of *new_mark_name* is the mark name for the transaction, even if the transaction possesses a transaction name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="12586-140">Se você emitir uma segunda instrução aninhada BEGIN TRAN...WITH MARK, ela será ignorada, mas provocará uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="12586-140">If you issue a second nested BEGIN TRAN...WITH MARK, that statement is skipped but causes a warning message.</span></span>  
  
2.  <span data-ttu-id="12586-141">Execute uma atualização de todos os bancos de dados do conjunto.</span><span class="sxs-lookup"><span data-stu-id="12586-141">Run an update against all of the databases in the set.</span></span>  
  
     <span data-ttu-id="12586-142">A marca para uma transação específica é inserida em logs de transações apenas na instância de servidor na qual a instrução BEGIN TRAN...WITH MARK é executada.</span><span class="sxs-lookup"><span data-stu-id="12586-142">The mark for a specific transaction is inserted into transaction logs only on the server instance where the BEGIN TRAN...WITH MARK statement is executed.</span></span> <span data-ttu-id="12586-143">A marca de transações é colocada no log de transações de todos os bancos de dados atualizados pela transação marcada naquela instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="12586-143">The transaction mark is placed in the transaction log of every database updated by the marked transaction on that server instance.</span></span> <span data-ttu-id="12586-144">Se os bancos de dados residirem em instâncias de servidor diferentes, deverão ser criadas marcas idênticas em cada uma das instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="12586-144">If the databases reside on different server instances, identical marks must be created on each of the server instances.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="12586-145">Exemplos</span><span class="sxs-lookup"><span data-stu-id="12586-145">Examples</span></span>  
 <span data-ttu-id="12586-146">O exemplo a seguir restaura o log de transações até a marca na transação marcada denominada `ListPriceUpdate`.</span><span class="sxs-lookup"><span data-stu-id="12586-146">The following example restores the transaction log to the mark in the marked transaction named `ListPriceUpdate`.</span></span>  
  
```sql  
USE AdventureWorks  
GO  
BEGIN TRANSACTION ListPriceUpdate  
   WITH MARK 'UPDATE Product list prices';  
GO  
  
UPDATE Production.Product  
   SET ListPrice = ListPrice * 1.10  
   WHERE ProductNumber LIKE 'BK-%';  
GO  
  
COMMIT TRANSACTION ListPriceUpdate;  
GO  
  
-- Time passes. Regular database   
-- and log backups are taken.  
-- An error occurs in the database.  
USE master  
GO  
  
RESTORE DATABASE AdventureWorks  
FROM AdventureWorksBackups  
WITH FILE = 3, NORECOVERY;  
GO  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups   
   WITH FILE = 4,  
   RECOVERY,   
   STOPATMARK = 'ListPriceUpdate';  
```  
  
## <a name="forcing-a-mark-to-spread-to-other-servers"></a><span data-ttu-id="12586-147">Forçando uma marca para ser difundida em outros servidores</span><span class="sxs-lookup"><span data-stu-id="12586-147">Forcing a Mark to Spread to Other Servers</span></span>  
 <span data-ttu-id="12586-148">O nome de uma marca de transação não é automaticamente distribuído para outro servidor à medida que a transação é difundida.</span><span class="sxs-lookup"><span data-stu-id="12586-148">A transaction mark name is not automatically distributed to another server as the transaction spreads there.</span></span> <span data-ttu-id="12586-149">Para forçar a difusão da marca em outros servidores, é necessário gravar um procedimento armazenado que contenha uma instrução BEGIN TRAN *name* WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="12586-149">To force the mark to spread to the other servers, a stored procedure must be written that contains a BEGIN TRAN *name* WITH MARK statement.</span></span> <span data-ttu-id="12586-150">Esse procedimento armazenado deve ser executado no servidor remoto dentro do escopo da transação no servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="12586-150">That stored procedure must then be executed on the remote server under the scope of the transaction in the originating server.</span></span>  
  
 <span data-ttu-id="12586-151">Por exemplo, considere um banco de dados particionado que exista em várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12586-151">For example, consider a partitioned database that exists on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="12586-152">Em cada instância é um banco de dados chamado `coyote`.</span><span class="sxs-lookup"><span data-stu-id="12586-152">On each instance is a database named `coyote`.</span></span> <span data-ttu-id="12586-153">Primeiro, em todos os bancos de dados, crie um procedimento armazenado, por exemplo, `sp_SetMark`.</span><span class="sxs-lookup"><span data-stu-id="12586-153">First, in every database, create a stored procedure, for example, `sp_SetMark`.</span></span>  
  
```sql  
CREATE PROCEDURE sp_SetMark  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION @name WITH MARK  
UPDATE coyote.dbo.Marks SET one = 1  
COMMIT TRANSACTION;  
GO  
```  
  
 <span data-ttu-id="12586-154">Em seguida, crie um procedimento armazenado `sp_MarkAll` que contenha uma transação que coloque uma marca em cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="12586-154">Next, create stored procedure `sp_MarkAll` containing a transaction that places a mark in every database.</span></span> <span data-ttu-id="12586-155">`sp_MarkAll` pode ser executado em qualquer instância.</span><span class="sxs-lookup"><span data-stu-id="12586-155">`sp_MarkAll` can be run from any of the instances.</span></span>  
  
```sql  
CREATE PROCEDURE sp_MarkAll  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION  
EXEC instance0.coyote.dbo.sp_SetMark @name  
EXEC instance1.coyote.dbo.sp_SetMark @name  
EXEC instance2.coyote.dbo.sp_SetMark @name  
COMMIT TRANSACTION;  
GO  
```  
  
### <a name="two-phase-commit"></a><span data-ttu-id="12586-156">protocolo 2PC</span><span class="sxs-lookup"><span data-stu-id="12586-156">Two-Phase Commit</span></span>  
 <span data-ttu-id="12586-157">A confirmação de uma transação distribuída ocorre em duas fases: preparar e confirmar.</span><span class="sxs-lookup"><span data-stu-id="12586-157">Committing a distributed transaction occurs in two phases: prepare and commit.</span></span> <span data-ttu-id="12586-158">Quando uma transação marcada é confirmada, o registro de log de confirmação de cada banco de dados na transação marcada é colocado no log em um ponto em que não há nenhuma transação duvidosa em nenhum dos logs.</span><span class="sxs-lookup"><span data-stu-id="12586-158">When a marked transaction is committed, the commit log record for each database in the marked transaction is placed in the log at a point where there are no in-doubt transactions in any of the logs.</span></span> <span data-ttu-id="12586-159">Nesse ponto, há a garantia de que não há nenhuma transação que aparece confirmada em um log, mas não confirmada em outro log.</span><span class="sxs-lookup"><span data-stu-id="12586-159">At this point, it is guaranteed that there are no transactions that appear as committed in one log, but not committed in another log.</span></span>  
  
 <span data-ttu-id="12586-160">As seguintes etapas fazem isso durante a confirmação de uma transação marcada:</span><span class="sxs-lookup"><span data-stu-id="12586-160">The following steps accomplish this during the commit of a marked transaction:</span></span>  
  
1.  <span data-ttu-id="12586-161">A fase de preparação da marcação de transação pausa todas as novas preparações e confirmações.</span><span class="sxs-lookup"><span data-stu-id="12586-161">Prepare phase of a marking transaction stalls all new prepares and commits.</span></span>  
  
2.  <span data-ttu-id="12586-162">Somente as confirmações de transações já preparadas podem continuar.</span><span class="sxs-lookup"><span data-stu-id="12586-162">Only commits of already prepared transactions are allowed to continue.</span></span>  
  
3.  <span data-ttu-id="12586-163">A marcação de transação espera que todas as transações preparadas se esgotem (com tempo limite).</span><span class="sxs-lookup"><span data-stu-id="12586-163">Marking transaction then waits for all prepared transactions to drain (with time-out).</span></span>  
  
4.  <span data-ttu-id="12586-164">A transação marcada é preparada e confirmada.</span><span class="sxs-lookup"><span data-stu-id="12586-164">Marked transaction is prepared and committed.</span></span>  
  
5.  <span data-ttu-id="12586-165">A pausa de novas preparações e confirmações é suspensa.</span><span class="sxs-lookup"><span data-stu-id="12586-165">The stall of new prepares and commits is removed.</span></span>  
  
 <span data-ttu-id="12586-166">As pausas geradas por transações marcadas que são estendidas em vários bancos de dados podem diminuir o desempenho do processamento de transações do servidor.</span><span class="sxs-lookup"><span data-stu-id="12586-166">The stalls generated by marked transactions that span multiple databases can reduce the transaction processing performance of the server.</span></span>  
  
 <span data-ttu-id="12586-167">Não recomendamos a execução de transações marcadas simultâneas.</span><span class="sxs-lookup"><span data-stu-id="12586-167">We recommend that you do not run concurrent marked transactions.</span></span> <span data-ttu-id="12586-168">Apesar de ser raro, é possível que a confirmação de uma transação marcada distribuída faça deadlock em outras transações marcadas distribuídas que estejam sendo confirmadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="12586-168">It is rare but possible for the commit of a distributed marked transaction to deadlock with other distributed marked transactions that are committing at the same time.</span></span> <span data-ttu-id="12586-169">Quando isso acontece, a marcação da transação é escolhida como vítima de deadlock e é revertida.</span><span class="sxs-lookup"><span data-stu-id="12586-169">When this happens, the marking transaction is chosen as the deadlock victim and is rolled back.</span></span> <span data-ttu-id="12586-170">Quando ocorre esse erro, o aplicativo pode repetir a transação marcada.</span><span class="sxs-lookup"><span data-stu-id="12586-170">When this error occurs, the application can retry the marked transaction.</span></span> <span data-ttu-id="12586-171">Quando várias transações marcadas tentam confirmar simultaneamente, a probabilidade de haver deadlock aumenta.</span><span class="sxs-lookup"><span data-stu-id="12586-171">When multiple marked transactions try to commit concurrently, there is a higher probability of deadlock.</span></span>  
  
## <a name="recovering-to-a-marked-transaction"></a><span data-ttu-id="12586-172">Recuperando para uma transação marcada</span><span class="sxs-lookup"><span data-stu-id="12586-172">Recovering to a Marked Transaction</span></span>  
 <span data-ttu-id="12586-173">Para obter informações sobre como recuperar um banco de dados que contém transações marcadas ou um pouco antes de uma determinada marca, consulte [Recuperação de bancos de dados relacionados que contêm transação marcada](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="12586-173">For information about how to recover a database that contains marked transactions to or just before a particular mark, see [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12586-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12586-174">See Also</span></span>  
 <span data-ttu-id="12586-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12586-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span></span>  
 <span data-ttu-id="12586-176">[Fazer backup e restaurar bancos de dados do sistema &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="12586-176">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="12586-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12586-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="12586-178">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="12586-178">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="12586-179">[Backups de bancos de dados completos &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="12586-179">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="12586-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12586-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="12586-181">Recuperação de bancos de dados relacionados que contêm transação marcada</span><span class="sxs-lookup"><span data-stu-id="12586-181">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
  
