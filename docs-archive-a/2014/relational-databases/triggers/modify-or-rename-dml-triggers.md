---
title: Modificar ou renomear gatilhos DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- renaming triggers
- modifying triggers
- DML triggers, modifying
ms.assetid: c7317eec-c0e9-479e-a4a7-83b6b6c58d59
author: rothja
ms.author: jroth
ms.openlocfilehash: 65bb13552b552d54b5547eadedc412977e423a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582863"
---
# <a name="modify-or-rename-dml-triggers"></a><span data-ttu-id="baa29-102">Modificar ou renomear gatilhos DML</span><span class="sxs-lookup"><span data-stu-id="baa29-102">Modify or Rename DML Triggers</span></span>
  <span data-ttu-id="baa29-103">Este tópico descreve como modificar um gatilho DML no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa29-103">This topic describes how to modify or rename a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="baa29-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="baa29-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="baa29-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="baa29-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="baa29-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="baa29-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="baa29-107">Recomendações</span><span class="sxs-lookup"><span data-stu-id="baa29-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="baa29-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="baa29-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="baa29-109">**Para modificar ou renomear um gatilho DML usando:**</span><span class="sxs-lookup"><span data-stu-id="baa29-109">**To modify or rename a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="baa29-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="baa29-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="baa29-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="baa29-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="baa29-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="baa29-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="baa29-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="baa29-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="baa29-114">Quando você renomeia um gatilho, o gatilho deve estar no banco de dados atual e o novo nome deve seguir as regras para [identificadores](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="baa29-114">When you rename a trigger, the trigger must be in the current database, and the new name must follow the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="baa29-115">Recomendações</span><span class="sxs-lookup"><span data-stu-id="baa29-115">Recommendations</span></span>  
  
-   <span data-ttu-id="baa29-116">Recomendamos que você não use o procedimento armazenado [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) para renomear um gatilho.</span><span class="sxs-lookup"><span data-stu-id="baa29-116">We recommend you do not use the [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) stored procedure to rename a trigger.</span></span> <span data-ttu-id="baa29-117">A alteração de qualquer parte de um nome de objeto pode quebrar scripts e procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="baa29-117">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="baa29-118">Renomear um gatilho não altera o nome do objeto correspondente na coluna de definição da exibição de catálogo [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="baa29-118">Renaming a trigger does not change the name of the corresponding object name in the definition column of the [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) catalog view.</span></span> <span data-ttu-id="baa29-119">Nós recomendamos que você remova e recrie o gatilho.</span><span class="sxs-lookup"><span data-stu-id="baa29-119">We recommend that you drop and re-create the trigger instead.</span></span>  
  
-   <span data-ttu-id="baa29-120">Se você alterar o nome de um objeto referenciado por um gatilho DML, é preciso modificar o gatilho para que seu texto reflita o novo nome.</span><span class="sxs-lookup"><span data-stu-id="baa29-120">If you change the name of an object referenced by a DML trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="baa29-121">Portanto, antes de renomear um objeto, exiba primeiramente as dependências do objeto para determinar se algum gatilho foi afetado pela mudança proposta.</span><span class="sxs-lookup"><span data-stu-id="baa29-121">Therefore, before you rename an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
-   <span data-ttu-id="baa29-122">Um gatilho DML também pode ser modificado para criptografar sua definição.</span><span class="sxs-lookup"><span data-stu-id="baa29-122">A DML trigger can also be modified to encrypt its definition.</span></span>  
  
-   <span data-ttu-id="baa29-123">Para exibir as dependências de um gatilho, você pode usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou a função e as exibições de catálogo a seguir:</span><span class="sxs-lookup"><span data-stu-id="baa29-123">To view the dependencies of a trigger, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the following function and catalog views:</span></span>  
  
    -   [<span data-ttu-id="baa29-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="baa29-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
    -   [<span data-ttu-id="baa29-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="baa29-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
    -   [<span data-ttu-id="baa29-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="baa29-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="baa29-127">Segurança</span><span class="sxs-lookup"><span data-stu-id="baa29-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="baa29-128">Permissões</span><span class="sxs-lookup"><span data-stu-id="baa29-128">Permissions</span></span>  
 <span data-ttu-id="baa29-129">A alteração de um gatilho DML exige permissão ALTER na tabela ou exibição na qual o gatilho está definido.</span><span class="sxs-lookup"><span data-stu-id="baa29-129">To alter a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="baa29-130">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="baa29-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-dml-trigger"></a><span data-ttu-id="baa29-131">Para modificar um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="baa29-131">To modify a DML trigger</span></span>  
  
1.  <span data-ttu-id="baa29-132">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="baa29-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="baa29-133">Expanda o banco de dados que você quer, expanda **Tabelas**e expanda a tabela que contém o gatilho que você quer modificar.</span><span class="sxs-lookup"><span data-stu-id="baa29-133">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to modify.</span></span>  
  
3.  <span data-ttu-id="baa29-134">Expanda **Gatilhos**, clique com o botão direito do mouse no gatilho a ser modificado e clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="baa29-134">Expand **Triggers**, right-click the trigger to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="baa29-135">Modifique o gatilho e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="baa29-135">Modify the trigger, and then click **Execute**.</span></span>  
  
#### <a name="to-rename-a-dml-trigger"></a><span data-ttu-id="baa29-136">Para renomear um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="baa29-136">To rename a DML trigger</span></span>  
  
1.  <span data-ttu-id="baa29-137">[Exclua o gatilho](../triggers/dml-triggers.md) que você deseja renomear.</span><span class="sxs-lookup"><span data-stu-id="baa29-137">[Delete the trigger](../triggers/dml-triggers.md) that you want to rename.</span></span>  
  
2.  <span data-ttu-id="baa29-138">[Recrie o gatilho](../triggers/create-dml-triggers.md), especificando o novo nome.</span><span class="sxs-lookup"><span data-stu-id="baa29-138">[Re-create the trigger](../triggers/create-dml-triggers.md), specifying the new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="baa29-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="baa29-139">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-trigger-using-alter-trigger"></a><span data-ttu-id="baa29-140">Para modificar um gatilho usando ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="baa29-140">To modify a trigger using ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="baa29-141">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa29-141">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="baa29-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="baa29-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="baa29-143">Copie e cole os seguintes exemplos na consulta.</span><span class="sxs-lookup"><span data-stu-id="baa29-143">Copy and paste the following examples into the query.</span></span> <span data-ttu-id="baa29-144">Execute o primeiro exemplo para criar um gatilho DML que imprime uma mensagem definida pelo usuário para o cliente quando um usuário tenta adicionar ou alterar dados na tabela `SalesPersonQuotaHistory` .</span><span class="sxs-lookup"><span data-stu-id="baa29-144">Execute the first example to create a DML trigger that prints a user-defined message to the client when a user tries to add or change data in the `SalesPersonQuotaHistory` table.</span></span> <span data-ttu-id="baa29-145">Execute a instrução [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) para modificar o gatilho a ser disparado apenas nas atividades `INSERT` .</span><span class="sxs-lookup"><span data-stu-id="baa29-145">Execute the [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statement to modify the trigger to fire only on `INSERT` activities.</span></span> <span data-ttu-id="baa29-146">Esse gatilho é útil porque lembra ao usuário que atualiza ou insere linhas nessa tabela que também notifique o departamento `Compensation` .</span><span class="sxs-lookup"><span data-stu-id="baa29-146">This trigger is helpful because it reminds the user that updates or inserts rows into this table to also notify the `Compensation` department.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
USE AdventureWorks2012;  
GO  
ALTER TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
AFTER INSERT  
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
#### <a name="to-rename-a-trigger-using-drop-trigger-and-alter-trigger"></a><span data-ttu-id="baa29-147">Para renomear um gatilho usando DROP TRIGGER e ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="baa29-147">To rename a trigger using DROP TRIGGER and ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="baa29-148">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa29-148">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="baa29-149">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="baa29-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="baa29-150">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="baa29-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="baa29-151">Este exemplo usa as instruções [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) e [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) para renomear o gatilho `Sales.bonus_reminder` como `Sales.bonus_reminder_2`.</span><span class="sxs-lookup"><span data-stu-id="baa29-151">This example use the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) and [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statements to rename the `Sales.bonus_reminder` trigger to `Sales.bonus_reminder_2`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder_2  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="baa29-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="baa29-152">See Also</span></span>  
 <span data-ttu-id="baa29-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="baa29-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="baa29-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="baa29-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="baa29-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="baa29-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="baa29-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="baa29-160">[Obter informações sobre gatilhos DML](../triggers/get-information-about-dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="baa29-160">[Get Information About DML Triggers](../triggers/get-information-about-dml-triggers.md) </span></span>  
 <span data-ttu-id="baa29-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="baa29-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="baa29-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="baa29-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="baa29-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="baa29-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="baa29-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="baa29-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="baa29-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa29-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="baa29-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="baa29-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
