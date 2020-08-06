---
title: Excluir ou desabilitar gatilhos DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, disabling
- removing DML triggers
- disabling DML triggers
- dropping DML triggers
- deleting DML triggers
- DML triggers, removing
ms.assetid: 0f97f953-33c5-4b26-afeb-db2a26ce38b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 39b345ade1258987df06938791ac0024e8612365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582880"
---
# <a name="delete-or-disable-dml-triggers"></a><span data-ttu-id="fdd53-102">Excluir ou desabilitar gatilhos DML</span><span class="sxs-lookup"><span data-stu-id="fdd53-102">Delete or Disable DML Triggers</span></span>
  <span data-ttu-id="fdd53-103">Este tópico descreve como excluir ou desabilitar um gatilho DML no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdd53-103">This topic describes how to delete or disable a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fdd53-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="fdd53-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fdd53-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="fdd53-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fdd53-106">Recomendações</span><span class="sxs-lookup"><span data-stu-id="fdd53-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="fdd53-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="fdd53-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fdd53-108">**Para excluir ou desabilitar um gatilho DML, usando:**</span><span class="sxs-lookup"><span data-stu-id="fdd53-108">**To delete or disable a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="fdd53-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fdd53-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fdd53-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fdd53-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fdd53-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fdd53-111">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="fdd53-112">Recomendações</span><span class="sxs-lookup"><span data-stu-id="fdd53-112">Recommendations</span></span>  
  
-   <span data-ttu-id="fdd53-113">Quando um gatilho é excluído, ele é descartado do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="fdd53-113">When a trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="fdd53-114">A tabela e os dados nos quais está baseada não são afetados.</span><span class="sxs-lookup"><span data-stu-id="fdd53-114">The table and the data upon which it is based are not affected.</span></span> <span data-ttu-id="fdd53-115">Excluir uma tabela exclui automaticamente todos os gatilhos da tabela.</span><span class="sxs-lookup"><span data-stu-id="fdd53-115">Deleting a table automatically deletes any triggers on the table.</span></span>  
  
-   <span data-ttu-id="fdd53-116">Um gatilho é habilitado por padrão quando é criado.</span><span class="sxs-lookup"><span data-stu-id="fdd53-116">A trigger is enabled by default when it is created.</span></span>  
  
-   <span data-ttu-id="fdd53-117">Ao desabilitar um gatilho, você não o descarta.</span><span class="sxs-lookup"><span data-stu-id="fdd53-117">Disabling a trigger does not drop it.</span></span> <span data-ttu-id="fdd53-118">O gatilho ainda existe como um objeto no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="fdd53-118">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="fdd53-119">Porém, o gatilho não será acionado quando qualquer instrução INSERT, UPDATE ou DELETE, em que ele tenha sido programado, for executada.</span><span class="sxs-lookup"><span data-stu-id="fdd53-119">However, the trigger will not fire when any INSERT, UPDATE, or DELETE statement on which it was programmed is executed.</span></span> <span data-ttu-id="fdd53-120">Os gatilhos desabilitados podem ser habilitados novamente.</span><span class="sxs-lookup"><span data-stu-id="fdd53-120">Triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="fdd53-121">A habilitação de um disparador não recria o mesmo.</span><span class="sxs-lookup"><span data-stu-id="fdd53-121">Enabling a trigger does not re-create it.</span></span> <span data-ttu-id="fdd53-122">O gatilho é acionado da mesma forma como foi criado.</span><span class="sxs-lookup"><span data-stu-id="fdd53-122">The trigger fires in the same manner as when it was originally created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fdd53-123">Segurança</span><span class="sxs-lookup"><span data-stu-id="fdd53-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fdd53-124">Permissões</span><span class="sxs-lookup"><span data-stu-id="fdd53-124">Permissions</span></span>  
 <span data-ttu-id="fdd53-125">A exclusão de um gatilho DML requer permissão ALTER na tabela ou exibição na qual o gatilho está definido.</span><span class="sxs-lookup"><span data-stu-id="fdd53-125">To delete a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
 <span data-ttu-id="fdd53-126">Para desabilitar ou habilitar um gatilho DML, no mínimo, um usuário deve ter a permissão ALTER na tabela ou exibição na qual o gatilho foi criado.</span><span class="sxs-lookup"><span data-stu-id="fdd53-126">To disable or enable a DML trigger, at a minimum, a user must have ALTER permission on the table or view on which the trigger was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fdd53-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fdd53-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="fdd53-128">Para excluir um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="fdd53-128">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="fdd53-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fdd53-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fdd53-130">Expanda o banco de dados que você quer, expanda **Tabelas**e expanda a tabela que contém o gatilho que você quer excluir.</span><span class="sxs-lookup"><span data-stu-id="fdd53-130">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to delete.</span></span>  
  
3.  <span data-ttu-id="fdd53-131">Expanda **Gatilhos**, clique com o botão direito do mouse no gatilho para excluí-lo e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="fdd53-131">Expand **Triggers**, right-click the trigger to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="fdd53-132">Na caixa de diálogo **Excluir Objeto** , verifique o gatilho a ser excluído e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdd53-132">In the **Delete Object** dialog box, verify the trigger to delete, and then click **OK**.</span></span>  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="fdd53-133">Para desabilitar e habilitar um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="fdd53-133">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="fdd53-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fdd53-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fdd53-135">Expanda o banco de dados que você quer, expanda **Tabelas**e expanda a tabela que contém o gatilho que você quer desabilitar.</span><span class="sxs-lookup"><span data-stu-id="fdd53-135">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to disable.</span></span>  
  
3.  <span data-ttu-id="fdd53-136">Expanda **Gatilhos**, clique com o botão direito do mouse no gatilho para desabilitá-lo e clique em **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="fdd53-136">Expand **Triggers**, right-click the trigger to disable, and then click **Disable**.</span></span>  
  
4.  <span data-ttu-id="fdd53-137">Para habilitar o gatilho, clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="fdd53-137">To enable the trigger, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fdd53-138">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fdd53-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="fdd53-139">Para excluir um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="fdd53-139">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="fdd53-140">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdd53-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fdd53-141">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fdd53-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fdd53-142">Copie e cole os exemplos a seguir na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="fdd53-142">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="fdd53-143">Execute a instrução [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) para criar o gatilho `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="fdd53-143">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="fdd53-144">Para excluir o gatilho, execute a instrução [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="fdd53-144">To delete the trigger, execute the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) statement.</span></span>  
  
```sql  
--Create the trigger.  
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
--Delete the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ('Sales.bonus_reminder', 'TR') IS NOT NULL  
   DROP TRIGGER Sales.bonus_reminder;  
GO  
  
```  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="fdd53-145">Para desabilitar e habilitar um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="fdd53-145">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="fdd53-146">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdd53-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fdd53-147">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fdd53-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fdd53-148">Copie e cole os exemplos a seguir na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="fdd53-148">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="fdd53-149">Execute a instrução [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) para criar o gatilho `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="fdd53-149">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="fdd53-150">Para desabilitar e habilitar o gatilho, execute as instruções [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) e [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="fdd53-150">To disable and enable the trigger, execute the [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) and [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) statements, respectively.</span></span>  
  
```sql  
--Create the trigger.  
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
--Disable the trigger.  
USE AdventureWorks2012;  
GO  
DISABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
  
```  
  
```sql  
--Enable the trigger.  
USE AdventureWorks2012;  
GO  
ENABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdd53-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fdd53-151">See Also</span></span>  
 <span data-ttu-id="fdd53-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-158">[Obter informações sobre gatilhos DML](dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="fdd53-158">[Get Information About DML Triggers](dml-triggers.md) </span></span>  
 <span data-ttu-id="fdd53-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="fdd53-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdd53-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="fdd53-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fdd53-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
