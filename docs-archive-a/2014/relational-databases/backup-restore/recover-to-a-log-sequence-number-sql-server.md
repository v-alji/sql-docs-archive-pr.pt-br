---
title: Recuperar para um número de sequência de log (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log sequence numbers [SQL Server]
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- LSNs
- database recovery [SQL Server]
- database restores [SQL Server], point in time
ms.assetid: f7b3de5b-198d-448d-8c71-1cdd9239676c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4df55c3468fc009d86cffd58a837d6935f5ce14b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581419"
---
# <a name="recover-to-a-log-sequence-number-sql-server"></a><span data-ttu-id="29f7b-102">Recuperar para um número de sequência de log (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="29f7b-102">Recover to a Log Sequence Number (SQL Server)</span></span>
  <span data-ttu-id="29f7b-103">Este tópico é relevante apenas para bancos de dados que estejam usando modelos de recuperação completa ou bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="29f7b-103">This topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="29f7b-104">Você pode usar um LSN (número de sequência de log) para definir o ponto de recuperação para uma operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="29f7b-104">You can use a log sequence number (LSN) to define the recovery point for a restore operation.</span></span> <span data-ttu-id="29f7b-105">No entanto, esse é um recurso especializado destinado a fornecedores de ferramentas e provavelmente não é de uso geral.</span><span class="sxs-lookup"><span data-stu-id="29f7b-105">However, this is a specialized feature that is intended for tools vendors and is unlikely to be generally useful.</span></span>  
  
##  <a name="overview-of-log-sequence-numbers"></a><a name="LSNs"></a> <span data-ttu-id="29f7b-106">Visão geral de números de sequência de log</span><span class="sxs-lookup"><span data-stu-id="29f7b-106">Overview of Log Sequence Numbers</span></span>  
 <span data-ttu-id="29f7b-107">Os LSNs são usados internamente durante uma sequência RESTORE para localizar o point-in-time para o qual os dados foram restaurados.</span><span class="sxs-lookup"><span data-stu-id="29f7b-107">LSNs are used internally during a RESTORE sequence to track the point in time to which data has been restored.</span></span> <span data-ttu-id="29f7b-108">Quando um backup é restaurado, os dados são restaurados ao LSN que corresponde ao point-in-time em que o backup foi realizado.</span><span class="sxs-lookup"><span data-stu-id="29f7b-108">When a backup is restored, the data is restored to the LSN corresponding to the point in time at which the backup was taken.</span></span> <span data-ttu-id="29f7b-109">O backup diferencial e o backup de log avançam o banco de dados restaurado para uma hora posterior que corresponde a um LSN mais alto.</span><span class="sxs-lookup"><span data-stu-id="29f7b-109">Differential and log backups advance the restored database to a later time, which corresponds to a higher LSN.</span></span>  
  
 <span data-ttu-id="29f7b-110">Cada registro do log de transações é identificado de forma exclusiva por um LSN (número da sequência de log).</span><span class="sxs-lookup"><span data-stu-id="29f7b-110">Every record in the transaction log is uniquely identified by a log sequence number (LSN).</span></span> <span data-ttu-id="29f7b-111">Os LSNs são ordenados de tal modo que se LSN2 for maior do que LSN1, a alteração descrita pelo registro de log mencionado por LSN2 ocorreu depois da alteração descrita pelo registro de log LSN.</span><span class="sxs-lookup"><span data-stu-id="29f7b-111">LSNs are ordered such that if LSN2 is greater than LSN1, the change described by the log record referred to by LSN2 occurred after the change described by the log record LSN.</span></span>  
  
 <span data-ttu-id="29f7b-112">O LSN de um registro de log no qual ocorreu um evento significativo pode ser útil para construir sequências de restauração corretas.</span><span class="sxs-lookup"><span data-stu-id="29f7b-112">The LSN of a log record at which a significant event occurred can be useful for constructing correct restore sequences.</span></span> <span data-ttu-id="29f7b-113">Como LSNs são ordenados, eles podem ser comparados por igualdade e desigualdade (ou seja,,, **\<**, **>** **=** **\<=**, **>=** ).</span><span class="sxs-lookup"><span data-stu-id="29f7b-113">Because LSNs are ordered, they can be compared for equality and inequality (that is, **\<**, **>**, **=**, **\<=**, **>=**).</span></span> <span data-ttu-id="29f7b-114">Essas comparações são úteis ao construir sequências de restauração.</span><span class="sxs-lookup"><span data-stu-id="29f7b-114">Such comparisons are useful when constructing restore sequences.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29f7b-115">Os LSNs são valores do tipo de dados `numeric`(25,0).</span><span class="sxs-lookup"><span data-stu-id="29f7b-115">LSNs are values of data type `numeric`(25,0).</span></span> <span data-ttu-id="29f7b-116">Operações aritméticas (por exemplo, adição ou subtração) não são significativas e não devem ser usadas com LSNs.</span><span class="sxs-lookup"><span data-stu-id="29f7b-116">Arithmetic operations (for example, addition or subtraction) are not meaningful and must not be used with LSNs.</span></span>  
  

  
## <a name="viewing-lsns-used-by-backup-and-restore"></a><span data-ttu-id="29f7b-117">Exibindo LSNs usados por Backup e Restauração</span><span class="sxs-lookup"><span data-stu-id="29f7b-117">Viewing LSNs Used by Backup and Restore</span></span>  
 <span data-ttu-id="29f7b-118">O LSN de um registro de log no qual um determinado evento de backup e restauração ocorrido pode ser exibido usando um ou mais do seguinte:</span><span class="sxs-lookup"><span data-stu-id="29f7b-118">The LSN of a log record at which a given backup and restore event occurred is viewable using one or more of the following:</span></span>  
  
-   [<span data-ttu-id="29f7b-119">backupset</span><span class="sxs-lookup"><span data-stu-id="29f7b-119">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
-   [<span data-ttu-id="29f7b-120">backupfile</span><span class="sxs-lookup"><span data-stu-id="29f7b-120">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)  
  
-   <span data-ttu-id="29f7b-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="29f7b-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span></span>  
  
-   [<span data-ttu-id="29f7b-122">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="29f7b-122">RESTORE HEADERONLY</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="29f7b-123">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="29f7b-123">RESTORE FILELISTONLY</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="29f7b-124">Os LSNs também aparecem em alguns textos de mensagem.</span><span class="sxs-lookup"><span data-stu-id="29f7b-124">LSNs also appear in some message texts.</span></span>  
  
## <a name="transact-sql-syntax-for-restoring-to-an-lsn"></a><span data-ttu-id="29f7b-125">Sintaxe de Transact-SQL para restaurar para um LSN</span><span class="sxs-lookup"><span data-stu-id="29f7b-125">Transact-SQL Syntax for Restoring to an LSN</span></span>  
 <span data-ttu-id="29f7b-126">Usando uma instrução [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) é possível parar no LSN ou imediatamente antes, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="29f7b-126">By using a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, you can stop at or immediately before the LSN, as follows:</span></span>  
  
-   <span data-ttu-id="29f7b-127">Use a cláusula WITH STOPATMARK **='** lsn: _<número_de_lsn>_ **'** , em que lsn: *\<lsnNumber>* é uma cadeia de caracteres que especifica que o registro de log que contém o LSN especificado é o ponto de recuperação.</span><span class="sxs-lookup"><span data-stu-id="29f7b-127">Use the WITH STOPATMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record that contains the specified LSN is the recovery point.</span></span>  
  
     <span data-ttu-id="29f7b-128">O STOPATMARK efetua roll forward para o LSN e inclui o registro de log no roll forward.</span><span class="sxs-lookup"><span data-stu-id="29f7b-128">STOPATMARK roll forwards to the LSN and includes that log record in the roll forward.</span></span>  
  
-   <span data-ttu-id="29f7b-129">Use a cláusula WITH STOPBEFOREMARK **='** lsn: _<número_de_lsn>_ **'** , em que lsn: *\<lsnNumber>* é uma cadeia de caracteres que especifica que o registro de log imediatamente anterior ao registro de log que contém o número do LSN especificado é o ponto de recuperação.</span><span class="sxs-lookup"><span data-stu-id="29f7b-129">Use the WITH STOPBEFOREMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record immediately before the log record that contains the specified LSN number is the recovery point.</span></span>  
  
     <span data-ttu-id="29f7b-130">O STOPATMARK efetua roll forward para o LSN e exclui o registro de log do roll forward.</span><span class="sxs-lookup"><span data-stu-id="29f7b-130">STOPBEFOREMARK rolls forward to the LSN and excludes that log record from the roll forward.</span></span>  
  
 <span data-ttu-id="29f7b-131">Normalmente, uma transação específica é selecionada para ser incluída ou excluída.</span><span class="sxs-lookup"><span data-stu-id="29f7b-131">Typically, a specific transaction is selected to be included or excluded.</span></span> <span data-ttu-id="29f7b-132">Embora não seja exigido, na prática, o registro de log especificado é um registro da confirmação de transação.</span><span class="sxs-lookup"><span data-stu-id="29f7b-132">Although not required, in practice, the specified log record is a transaction-commit record.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="29f7b-133">Exemplos</span><span class="sxs-lookup"><span data-stu-id="29f7b-133">Examples</span></span>  
 <span data-ttu-id="29f7b-134">O exemplo a seguir assume que o banco de dados `AdventureWorks` foi alterado para usar o modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="29f7b-134">The following example assumes that the `AdventureWorks` database has been changed to use the full recovery model.</span></span>  
  
```  
RESTORE LOG AdventureWorks FROM DISK = 'c:\adventureworks_log.bak'   
WITH STOPATMARK = 'lsn:15000000040000037'  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="29f7b-135">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="29f7b-135">Related Tasks</span></span>  
  
-   [<span data-ttu-id="29f7b-136">Restaurar um backup de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="29f7b-136">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="29f7b-137">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="29f7b-137">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="29f7b-138">Restaurar um backup de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="29f7b-138">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="29f7b-139">Restaurar um banco de dados até o ponto de falha no modelo de recuperação completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29f7b-139">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="29f7b-140">Restaurar um banco de dados para uma transação marcada &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="29f7b-140">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="29f7b-141">Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;</span><span class="sxs-lookup"><span data-stu-id="29f7b-141">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="29f7b-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29f7b-142">See Also</span></span>  
 <span data-ttu-id="29f7b-143">[Aplicar backups de log de transações &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="29f7b-143">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="29f7b-144">[O log de transações &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="29f7b-144">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="29f7b-145">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29f7b-145">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
