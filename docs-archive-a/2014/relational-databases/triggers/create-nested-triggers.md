---
title: Criar gatilhos aninhados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- recursive DML triggers [SQL Server]
- DML triggers, nested
- triggers [SQL Server], nested
- direct recursion [SQL Server]
- triggers [SQL Server], recursive
- DML triggers, recursive
- RECURSIVE_TRIGGERS option
- indirect recursion [SQL Server]
- nested DML triggers
ms.assetid: cd522dda-b4ab-41b8-82b0-02445bdba7af
author: rothja
ms.author: jroth
ms.openlocfilehash: c0016fc3cdd93ea78ceed56efa076a01bd85be50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582885"
---
# <a name="create-nested-triggers"></a><span data-ttu-id="04af9-102">Criar gatilhos aninhados</span><span class="sxs-lookup"><span data-stu-id="04af9-102">Create Nested Triggers</span></span>
  <span data-ttu-id="04af9-103">Os gatilhos DML e DDL são aninhados quando um gatilho executa uma ação que inicia outro gatilho.</span><span class="sxs-lookup"><span data-stu-id="04af9-103">Both DML and DDL triggers are nested when a trigger performs an action that initiates another trigger.</span></span> <span data-ttu-id="04af9-104">Essas ações podem iniciar outros gatilhos, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="04af9-104">These actions can initiate other triggers, and so on.</span></span> <span data-ttu-id="04af9-105">Os gatilhos DML e DDL podem ser aninhados em até 32 níveis.</span><span class="sxs-lookup"><span data-stu-id="04af9-105">DML and DDL triggers can be nested up to 32 levels.</span></span> <span data-ttu-id="04af9-106">Você pode controlar se os gatilhos AFTER podem ser aninhados pela opção de configuração do servidor **nested triggers** .</span><span class="sxs-lookup"><span data-stu-id="04af9-106">You can control whether AFTER triggers can be nested through the **nested triggers** server configuration option.</span></span> <span data-ttu-id="04af9-107">Os gatilhos INSTEAD OF (apenas gatilhos DML podem ser gatilhos INSTEAD OF) podem ser aninhados, independentemente dessa configuração.</span><span class="sxs-lookup"><span data-stu-id="04af9-107">INSTEAD OF triggers (only DML triggers can be INSTEAD OF triggers) can be nested regardless of this setting.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04af9-108">Qualquer referência a um código gerenciado de um gatilho [!INCLUDE[tsql](../../includes/tsql-md.md)] conta como um nível em relação ao limite de 32 níveis de aninhamento.</span><span class="sxs-lookup"><span data-stu-id="04af9-108">Any reference to managed code from a [!INCLUDE[tsql](../../includes/tsql-md.md)] trigger counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="04af9-109">Os métodos invocados a partir do código gerenciado não são contados em relação a esse limite.</span><span class="sxs-lookup"><span data-stu-id="04af9-109">Methods invoked from within managed code do not count against this limit.</span></span>  
  
 <span data-ttu-id="04af9-110">Se gatilhos aninhados forem permitidos e um gatilho na cadeia iniciar um loop infinito, o nível de aninhamento será excedido e o gatilho será encerrado.</span><span class="sxs-lookup"><span data-stu-id="04af9-110">If nested triggers are allowed and a trigger in the chain starts an infinite loop, the nesting level is exceeded and the trigger terminates.</span></span>  
  
 <span data-ttu-id="04af9-111">Você pode usar gatilhos aninhados para executar funções de manutenção úteis, como armazenar uma cópia de backup de linhas afetadas por um gatilho anterior.</span><span class="sxs-lookup"><span data-stu-id="04af9-111">You can use nested triggers to perform useful housekeeping functions such as storing a backup copy of rows affected by a previous trigger.</span></span> <span data-ttu-id="04af9-112">Por exemplo, você pode criar um gatilho em `PurchaseOrderDetail` que salva uma cópia de backup das linhas de `PurchaseOrderDetail` que o gatilho `delcascadetrig` excluiu.</span><span class="sxs-lookup"><span data-stu-id="04af9-112">For example, you can create a trigger on `PurchaseOrderDetail` that saves a backup copy of the `PurchaseOrderDetail` rows that the `delcascadetrig` trigger deleted.</span></span> <span data-ttu-id="04af9-113">Com o gatilho `delcascadetrig` em vigor, excluir `PurchaseOrderID` 1965 de `PurchaseOrderHeader` exclui a linha correspondente de `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="04af9-113">With the `delcascadetrig` trigger in effect, deleting `PurchaseOrderID` 1965 from `PurchaseOrderHeader` deletes the corresponding row or rows from `PurchaseOrderDetail`.</span></span> <span data-ttu-id="04af9-114">Para salvar os dados, você pode criar um gatilho DELETE em `PurchaseOrderDetail` que salva os dados excluídos em outra tabela criada separadamente, `del_save`.</span><span class="sxs-lookup"><span data-stu-id="04af9-114">To save the data, you can create a DELETE trigger on `PurchaseOrderDetail` that saves the deleted data into another separately created table, `del_save`.</span></span> <span data-ttu-id="04af9-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="04af9-115">For example:</span></span>  
  
```  
CREATE TRIGGER Purchasing.savedel  
   ON Purchasing.PurchaseOrderDetail  
FOR DELETE  
AS  
   INSERT del_save;  
   SELECT * FROM deleted;  
```  
  
 <span data-ttu-id="04af9-116">Nós não recomendamos usar gatilhos aninhados em uma sequência dependente de ordem.</span><span class="sxs-lookup"><span data-stu-id="04af9-116">We do not recommend using nested triggers in an order-dependent sequence.</span></span> <span data-ttu-id="04af9-117">Use gatilhos separados para colocar modificações de dados em cascata.</span><span class="sxs-lookup"><span data-stu-id="04af9-117">Use separate triggers to cascade data modifications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04af9-118">Como os gatilhos são executados em uma transação, uma falha em qualquer nível de um conjunto de gatilhos aninhados cancela toda a transação e todas as modificações de dados são revertidas.</span><span class="sxs-lookup"><span data-stu-id="04af9-118">Because triggers execute within a transaction, a failure at any level of a set of nested triggers cancels the entire transaction, and all data modifications are rolled back.</span></span> <span data-ttu-id="04af9-119">Inclua instruções PRINT em seus gatilhos de modo que você possa determinar onde a falha ocorreu.</span><span class="sxs-lookup"><span data-stu-id="04af9-119">Include PRINT statements in your triggers so that you can determine where the failure has occurred.</span></span>  
  
## <a name="recursive-triggers"></a><span data-ttu-id="04af9-120">Gatilhos recursivos</span><span class="sxs-lookup"><span data-stu-id="04af9-120">Recursive Triggers</span></span>  
 <span data-ttu-id="04af9-121">Um gatilho AFTER não pode ser chamado recursivamente a menos que a opção do banco de dados RECURSIVE_TRIGGERS seja definida.</span><span class="sxs-lookup"><span data-stu-id="04af9-121">An AFTER trigger does not call itself recursively unless the RECURSIVE_TRIGGERS database option is set.</span></span>  
  
 <span data-ttu-id="04af9-122">Existem dois tipos de grupos de recursão:</span><span class="sxs-lookup"><span data-stu-id="04af9-122">There are two types of recursion:</span></span>  
  
-   <span data-ttu-id="04af9-123">Recursão direta</span><span class="sxs-lookup"><span data-stu-id="04af9-123">Direct recursion</span></span>  
  
     <span data-ttu-id="04af9-124">Essa recursão ocorre quando um gatilho é acionado e executa uma ação que faz com que o mesmo gatilho seja acionado novamente.</span><span class="sxs-lookup"><span data-stu-id="04af9-124">This recursion occurs when a trigger fires and performs an action that causes the same trigger to fire again.</span></span> <span data-ttu-id="04af9-125">Por exemplo, um aplicativo atualiza a tabela **T3**; isso faz com que o gatilho **Trig3** seja acionado.</span><span class="sxs-lookup"><span data-stu-id="04af9-125">For example, an application updates table **T3**; this causes trigger **Trig3** to fire.</span></span> <span data-ttu-id="04af9-126">**Trig3** atualiza a tabela **T3** novamente; isso faz com que o gatilho **Trig3** seja acionado novamente.</span><span class="sxs-lookup"><span data-stu-id="04af9-126">**Trig3** updates table **T3** again; this causes trigger **Trig3** to fire again.</span></span>  
  
     <span data-ttu-id="04af9-127">A recursão direta também pode ocorrer quando o mesmo gatilho é chamado novamente, mas após um gatilho de um tipo diferente (AFTER ou INSTEAD OF) ter sido chamado.</span><span class="sxs-lookup"><span data-stu-id="04af9-127">Direct recursion can also occur when the same trigger is called again, but after a trigger of a different type (AFTER or INSTEAD OF) is called.</span></span> <span data-ttu-id="04af9-128">Em outras palavras, a recursão direta de um gatilho INSTEAD OF pode ocorrer quando o mesmo gatilho INSTEAD OF é chamado pela segunda vez, mesmo se um ou mais gatilhos AFTER forem chamados no meio disso.</span><span class="sxs-lookup"><span data-stu-id="04af9-128">In other words, direct recursion of an INSTEAD OF trigger can occur when the same INSTEAD OF trigger is called for a second time, even if one or more AFTER triggers are called in between.</span></span> <span data-ttu-id="04af9-129">Da mesma maneira, a recursão direta de um gatilho AFTER pode ocorrer quando o mesmo gatilho AFTER é chamado pela segunda vez, mesmo se um ou mais gatilhos INSTEAD OF forem chamados no meio disso.</span><span class="sxs-lookup"><span data-stu-id="04af9-129">Likewise, direct recursion of an AFTER trigger can occur when the same AFTER trigger is called for a second time, even if one or more INSTEAD OF triggers are called in between.</span></span> <span data-ttu-id="04af9-130">Por exemplo, um aplicativo atualiza a tabela **T4**.</span><span class="sxs-lookup"><span data-stu-id="04af9-130">For example, an application updates table **T4**.</span></span> <span data-ttu-id="04af9-131">Essa atualização faz com que o gatilho INSTEAD OF **Trig4** seja acionado.</span><span class="sxs-lookup"><span data-stu-id="04af9-131">This update causes INSTEAD OF trigger **Trig4** to fire.</span></span> <span data-ttu-id="04af9-132">**Trig4** atualiza a tabela **T5**.</span><span class="sxs-lookup"><span data-stu-id="04af9-132">**Trig4** updates table **T5**.</span></span> <span data-ttu-id="04af9-133">Essa atualização faz com que o gatilho AFTER **Trig5** seja acionado.</span><span class="sxs-lookup"><span data-stu-id="04af9-133">This update causes AFTER trigger **Trig5** to fire.</span></span> <span data-ttu-id="04af9-134">**Trig5** atualiza a tabela **T4**e essa atualização faz com que o gatilho INSTEAD OF **Trig4** seja acionado novamente.</span><span class="sxs-lookup"><span data-stu-id="04af9-134">**Trig5** updates table **T4**, and this update causes INSTEAD OF trigger **Trig4** to fire again.</span></span> <span data-ttu-id="04af9-135">Essa cadeia de eventos é considerada uma recursão direta para **Trig4**.</span><span class="sxs-lookup"><span data-stu-id="04af9-135">This chain of events is considered direct recursion for **Trig4**.</span></span>  
  
-   <span data-ttu-id="04af9-136">Recursão indireta</span><span class="sxs-lookup"><span data-stu-id="04af9-136">Indirect recursion</span></span>  
  
     <span data-ttu-id="04af9-137">Essa recursão ocorre quando um gatilho é acionado e executa uma ação que faz com que outro gatilho do mesmo tipo (AFTER ou INSTEAD OF) seja acionado.</span><span class="sxs-lookup"><span data-stu-id="04af9-137">This recursion occurs when a trigger fires and performs an action that causes another trigger of the same type (AFTER or INSTEAD OF) to fire.</span></span> <span data-ttu-id="04af9-138">Esse segundo gatilho executa uma ação que faz com que o gatilho original seja acionado novamente.</span><span class="sxs-lookup"><span data-stu-id="04af9-138">This second trigger performs an action that causes the original trigger to fire again.</span></span> <span data-ttu-id="04af9-139">Em outras palavras, a recursão indireta pode ocorrer quando um gatilho INSTEAD OF for chamado pela segunda vez, mas não até que outro gatilho INSTEAD OF seja chamado no meio disso.</span><span class="sxs-lookup"><span data-stu-id="04af9-139">In other words, indirect recursion can occur when an INSTEAD OF trigger is called for a second time, but not until another INSTEAD OF trigger is called in between.</span></span> <span data-ttu-id="04af9-140">Da mesma maneira, a recursão indireta pode ocorrer quando um gatilho AFTER for chamado pela segunda vez, mas não até que outro gatilho AFTER seja chamado no meio disso.</span><span class="sxs-lookup"><span data-stu-id="04af9-140">Likewise, indirect recursion can occur when an AFTER trigger is called for a second time, but not until another AFTER trigger is called in between.</span></span> <span data-ttu-id="04af9-141">Por exemplo, um aplicativo atualiza a tabela **T1**.</span><span class="sxs-lookup"><span data-stu-id="04af9-141">For example, an application updates table **T1**.</span></span> <span data-ttu-id="04af9-142">Essa atualização faz com que o gatilho AFTER **Trig1** seja acionado.</span><span class="sxs-lookup"><span data-stu-id="04af9-142">This update causes AFTER trigger **Trig1** to fire.</span></span> <span data-ttu-id="04af9-143">**Trig1** atualiza a tabela **T2**e essa atualização faz com que o gatilho AFTER **Trig2** seja acionado.</span><span class="sxs-lookup"><span data-stu-id="04af9-143">**Trig1** updates table **T2**, and this update causes AFTER trigger **Trig2** to fire.</span></span> <span data-ttu-id="04af9-144">**Trig2** , por sua vez, atualiza a tabela **T1** , o que faz com que o gatilho AFTER **Trig1** seja acionado novamente.</span><span class="sxs-lookup"><span data-stu-id="04af9-144">**Trig2** in turn updates table **T1** that causes AFTER trigger **Trig1** to fire again.</span></span>  
  
 <span data-ttu-id="04af9-145">Somente a recursão direta de gatilhos AFTER é impedida quando a opção do banco de dados RECURSIVE_TRIGGERS estiver definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="04af9-145">Only direct recursion of AFTER triggers is prevented when the RECURSIVE_TRIGGERS database option is set to OFF.</span></span> <span data-ttu-id="04af9-146">Para desabilitar a recursão indireta de gatilhos AFTER, defina também a opção do servidor **nested triggers** como **0**.</span><span class="sxs-lookup"><span data-stu-id="04af9-146">To disable indirect recursion of AFTER triggers, also set the **nested triggers** server option to **0**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="04af9-147">Exemplos</span><span class="sxs-lookup"><span data-stu-id="04af9-147">Examples</span></span>  
 <span data-ttu-id="04af9-148">O exemplo a seguir mostra o uso de gatilhos recursivos para resolver uma relação de autorreferência (também conhecida como fechamento transitivo).</span><span class="sxs-lookup"><span data-stu-id="04af9-148">The following example shows using recursive triggers to solve a self-referencing relationship (also known as transitive closure).</span></span> <span data-ttu-id="04af9-149">Por exemplo, a tabela `emp_mgr` define o seguinte:</span><span class="sxs-lookup"><span data-stu-id="04af9-149">For example, the table `emp_mgr` defines the following:</span></span>  
  
-   <span data-ttu-id="04af9-150">Um funcionário (`emp`) em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="04af9-150">An employee (`emp`) in a company.</span></span>  
  
-   <span data-ttu-id="04af9-151">O gerente de cada funcionário (`mgr`).</span><span class="sxs-lookup"><span data-stu-id="04af9-151">The manager for each employee (`mgr`).</span></span>  
  
-   <span data-ttu-id="04af9-152">O número total de funcionários na árvore organizacional reportando-se a cada funcionário (`NoOfReports`).</span><span class="sxs-lookup"><span data-stu-id="04af9-152">The total number of employees in the organizational tree reporting to each employee (`NoOfReports`).</span></span>  
  
 <span data-ttu-id="04af9-153">Um gatilho recursivo UPDATE pode ser usado para manter a coluna `NoOfReports` atualizada à medida que novos registros de funcionário forem sendo inseridos.</span><span class="sxs-lookup"><span data-stu-id="04af9-153">A recursive UPDATE trigger can be used to keep the `NoOfReports` column up-to-date as new employee records are inserted.</span></span> <span data-ttu-id="04af9-154">O gatilho INSERT atualiza a coluna `NoOfReports` do registro do gerente, o que atualiza recursivamente a coluna `NoOfReports` de outros registros acima da hierarquia de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="04af9-154">The INSERT trigger updates the `NoOfReports` column of the manager record, which recursively updates the `NoOfReports` column of other records up the management hierarchy.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Turn recursive triggers ON in the database.  
ALTER DATABASE AdventureWorks2012  
   SET RECURSIVE_TRIGGERS ON;  
GO  
CREATE TABLE dbo.emp_mgr (  
   emp char(30) PRIMARY KEY,  
    mgr char(30) NULL FOREIGN KEY REFERENCES emp_mgr(emp),  
    NoOfReports int DEFAULT 0  
);  
GO  
CREATE TRIGGER dbo.emp_mgrins ON dbo.emp_mgr  
FOR INSERT  
AS  
DECLARE @e char(30), @m char(30);  
DECLARE c1 CURSOR FOR  
   SELECT emp_mgr.emp  
   FROM   emp_mgr, inserted  
   WHERE emp_mgr.emp = inserted.mgr;  
  
OPEN c1;  
FETCH NEXT FROM c1 INTO @e;  
WHILE @@fetch_status = 0  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Add 1 for newly  
   WHERE emp_mgr.emp = @e ;                           -- added employee.  
  
   FETCH NEXT FROM c1 INTO @e;  
END  
CLOSE c1;  
DEALLOCATE c1;  
GO  
-- This recursive UPDATE trigger works assuming:  
--   1. Only singleton updates on emp_mgr.  
--   2. No inserts in the middle of the org tree.  
CREATE TRIGGER dbo.emp_mgrupd ON dbo.emp_mgr FOR UPDATE  
AS  
IF UPDATE (mgr)  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Increment mgr's  
   FROM inserted                            -- (no. of reports) by  
   WHERE emp_mgr.emp = inserted.mgr;         -- 1 for the new report.  
  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports - 1 -- Decrement mgr's  
   FROM deleted                             -- (no. of reports) by 1  
   WHERE emp_mgr.emp = deleted.mgr;          -- for the new report.  
END  
GO  
-- Insert some test data rows.  
INSERT dbo.emp_mgr(emp, mgr) VALUES  
    ('Harry', NULL)  
    ,('Alice', 'Harry')  
    ,('Paul', 'Alice')  
    ,('Joe', 'Alice')  
    ,('Dave', 'Joe');  
GO  
SELECT emp,mgr,NoOfReports  
FROM dbo.emp_mgr;  
GO  
-- Change Dave's manager from Joe to Harry  
UPDATE dbo.emp_mgr SET mgr = 'Harry'  
WHERE emp = 'Dave';  
GO  
SELECT emp,mgr,NoOfReports FROM emp_mgr;  
  
GO  
```  
  
 <span data-ttu-id="04af9-155">Eis os resultados antes da atualização.</span><span class="sxs-lookup"><span data-stu-id="04af9-155">Here are the results before the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Joe                            0  
Harry                          NULL                           1  
Joe                            Alice                          1  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="04af9-156">Eis os resultados após a atualização.</span><span class="sxs-lookup"><span data-stu-id="04af9-156">Here are the results after the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Harry                          0  
Harry                          NULL                           2  
Joe                            Alice                          0  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="04af9-157">**Para definir a opção de gatilhos aninhados**</span><span class="sxs-lookup"><span data-stu-id="04af9-157">**To set the nested triggers option**</span></span>  
  
-   [<span data-ttu-id="04af9-158">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04af9-158">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
 <span data-ttu-id="04af9-159">**Para definir a opção do banco de dados RECURSIVE_TRIGGERS**</span><span class="sxs-lookup"><span data-stu-id="04af9-159">**To set the RECURSIVE_TRIGGERS database option**</span></span>  
  
-   [<span data-ttu-id="04af9-160">Opções ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04af9-160">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="04af9-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="04af9-161">See Also</span></span>  
 <span data-ttu-id="04af9-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04af9-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="04af9-163">Configurar a opção de configuração de servidor nested triggers</span><span class="sxs-lookup"><span data-stu-id="04af9-163">Configure the nested triggers Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-nested-triggers-server-configuration-option.md)  
  
  
