---
title: Obter informações sobre gatilhos DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- viewing DML triggers
- DML triggers, metadata
- displaying DML triggers
- status information [SQL Server], triggers
- DML triggers, viewing
ms.assetid: 37574aac-181d-4aca-a2cc-8abff64237dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 2f65976d2f517137e23bd9e5e1c98cc76324bc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582876"
---
# <a name="get-information-about-dml-triggers"></a><span data-ttu-id="4ef88-102">Obter informações sobre gatilhos DML</span><span class="sxs-lookup"><span data-stu-id="4ef88-102">Get Information About DML Triggers</span></span>
  <span data-ttu-id="4ef88-103">Este tópico descreve como obter informações sobre os gatilhos DML no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef88-103">This topic describes how to get information about DML triggers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4ef88-104">Essas informações podem incluir os tipos de gatilhos em uma tabela, o nome de um gatilho, seu proprietário e a data em que foi criado ou modificado.</span><span class="sxs-lookup"><span data-stu-id="4ef88-104">This information can include the types of triggers on a table, the name of a trigger, its owner and the date it was created or modified.</span></span> <span data-ttu-id="4ef88-105">Se o gatilho não tiver sido criptografado quando foi criado, você obterá a definição do gatilho.</span><span class="sxs-lookup"><span data-stu-id="4ef88-105">If the trigger was not encrypted when it was created, you obtain the definition of the trigger.</span></span> <span data-ttu-id="4ef88-106">A definição ajudará a entender como um gatilho afeta a tabela na qual está definido.</span><span class="sxs-lookup"><span data-stu-id="4ef88-106">You can use the definition to help you understand how a trigger affects the table up on which it is defined.</span></span> <span data-ttu-id="4ef88-107">Além disso, você pode descobrir os objetos que um gatilho específico usa.</span><span class="sxs-lookup"><span data-stu-id="4ef88-107">Also, you can find out the objects that a specific trigger uses.</span></span> <span data-ttu-id="4ef88-108">Com essas informações, você pode identificar os objetos que afetam o gatilho se eles são alterados ou excluídos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ef88-108">With this information, you can identify the objects that affect the trigger if they are changed or deleted in the database.</span></span>  
  
 <span data-ttu-id="4ef88-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="4ef88-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4ef88-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="4ef88-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4ef88-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="4ef88-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4ef88-112">**Para obter informações os gatilhos DML, usando:**</span><span class="sxs-lookup"><span data-stu-id="4ef88-112">**To get information about DML triggers, using:**</span></span>  
  
     [<span data-ttu-id="4ef88-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4ef88-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4ef88-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4ef88-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4ef88-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4ef88-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4ef88-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="4ef88-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4ef88-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="4ef88-117">Permissions</span></span>  
 <span data-ttu-id="4ef88-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span><span class="sxs-lookup"><span data-stu-id="4ef88-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="4ef88-119">Para obter mais informações, consulte [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="4ef88-119">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
 <span data-ttu-id="4ef88-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span><span class="sxs-lookup"><span data-stu-id="4ef88-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span></span>  
 <span data-ttu-id="4ef88-121">Requer associação à função **pública** .</span><span class="sxs-lookup"><span data-stu-id="4ef88-121">Requires membership in the **public** role.</span></span> <span data-ttu-id="4ef88-122">A definição de objetos de usuário é visível ao proprietário do objeto e às entidades autorizadas que têm uma das seguintes permissões: ALTER, CONTROL, TAKE OWNERSHIP ou VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="4ef88-122">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="4ef88-123">Estas permissões são mantidas implicitamente por membros das funções fixas de banco de dados **db_owner**, **db_ddladmin**e **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="4ef88-123">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="4ef88-124">**sys.sql_expression_dependencies**</span><span class="sxs-lookup"><span data-stu-id="4ef88-124">**sys.sql_expression_dependencies**</span></span>  
 <span data-ttu-id="4ef88-125">Requer permissão VIEW DEFINITION no banco de dados e permissão SELECT em **sys.sql_expression_dependencies** para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ef88-125">Requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="4ef88-126">Por padrão, a permissão SELECT é concedida somente a membros da função de banco de dados fixa **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="4ef88-126">By default, SELECT permission is granted only to members of the **db_owner** fixed database role.</span></span> <span data-ttu-id="4ef88-127">Quando são concedidas permissões SELECT e VIEW DEFINITION a outro usuário, o usuário autorizado pode exibir todas as dependências no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ef88-127">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4ef88-128">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4ef88-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="4ef88-129">Para exibir a definição de um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="4ef88-129">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="4ef88-130">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="4ef88-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4ef88-131">Expanda o banco de dados desejado, expanda **Tabelas**e expanda a tabela que contém o gatilho para o qual você quer exibir a definição.</span><span class="sxs-lookup"><span data-stu-id="4ef88-131">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger for which you want to view the definition.</span></span>  
  
3.  <span data-ttu-id="4ef88-132">Expanda **Gatilhos**, clique com o botão direito do mouse no gatilho desejado e clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-132">Expand **Triggers**, right-click the trigger you want, and then click **Modify**.</span></span> <span data-ttu-id="4ef88-133">A definição do gatilho DML aparece na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="4ef88-133">The definition of the DML trigger appears in the query window.</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="4ef88-134">Para exibir as dependências de um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="4ef88-134">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="4ef88-135">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="4ef88-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4ef88-136">Expanda o banco de dados desejado, expanda **Tabelas**e expanda a tabela que contém o gatilho e suas dependências que você quer exibir.</span><span class="sxs-lookup"><span data-stu-id="4ef88-136">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger and its dependencies that you want to view.</span></span>  
  
3.  <span data-ttu-id="4ef88-137">Expanda **Gatilhos**, clique com o botão direito do mouse no gatilho desejado e clique em **Exibir Dependências**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-137">Expand **Triggers**, right-click the trigger you want, and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="4ef88-138">Na janela **Dependências de Objeto**, para exibir os objetos que dependem do gatilho DML, selecione **Objetos que dependem de \<DML trigger name>** .</span><span class="sxs-lookup"><span data-stu-id="4ef88-138">In the **Object Dependencies** window, to view the objects that depend on the DML trigger, select **Objects that depend on \<DML trigger name>**.</span></span> <span data-ttu-id="4ef88-139">Os objetos aparecem na área **Dependências** .</span><span class="sxs-lookup"><span data-stu-id="4ef88-139">The objects appear in the **Dependencies** area.</span></span>  
  
     <span data-ttu-id="4ef88-140">Para ver os objetos dos quais o DML depende, selecione **Objetos dos quais \<DML trigger name> depende**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-140">To view the objects on which the DML depends, select **Objects on which \<DML trigger name> depends**.</span></span> <span data-ttu-id="4ef88-141">Os objetos aparecem na área **Dependências** .</span><span class="sxs-lookup"><span data-stu-id="4ef88-141">The objects appear in the **Dependencies** area.</span></span> <span data-ttu-id="4ef88-142">Expanda cada nó para ver todos os objetos.</span><span class="sxs-lookup"><span data-stu-id="4ef88-142">Expand each node to see all the objects.</span></span>  
  
5.  <span data-ttu-id="4ef88-143">Para obter informações sobre um objeto que aparece na área **Dependências** , clique no objeto.</span><span class="sxs-lookup"><span data-stu-id="4ef88-143">To obtain information about an object that appears in the **Dependencies** area, click the object.</span></span> <span data-ttu-id="4ef88-144">No campo **Objeto selecionado** , as informações são fornecidas nas caixas **Nome**, **Tipo**e **Tipo de dependência** .</span><span class="sxs-lookup"><span data-stu-id="4ef88-144">In the **Selected object** field, information is provided in the **Name**, **Type**, and **Dependency type** boxes.</span></span>  
  
6.  <span data-ttu-id="4ef88-145">Para fechar a janela **Dependências do Objeto** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-145">To close the **Object Dependencies** window, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4ef88-146">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4ef88-146">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="4ef88-147">Para exibir a definição de um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="4ef88-147">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="4ef88-148">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef88-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4ef88-149">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4ef88-150">Copie e cole um dos exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-150">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="4ef88-151">Cada exemplo mostra como você pode exibir a definição do gatilho `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="4ef88-151">Each example shows how you can view the definition of the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT definition   
FROM sys.sql_modules  
WHERE object_id = OBJECT_ID(N'Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_DEFINITION (OBJECT_ID(N'Person.iuPerson')) AS ObjectDefinition;   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
EXEC sp_helptext 'Person.iuPerson'  
GO  
  
```  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="4ef88-152">Para exibir as dependências de um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="4ef88-152">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="4ef88-153">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef88-153">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4ef88-154">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-154">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4ef88-155">Copie e cole um dos exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-155">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="4ef88-156">Cada exemplo mostra como você pode exibir as dependências do gatilho `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="4ef88-156">Each example shows how you can view the dependencies of `iuPerson` trigger.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
    o.type_desc AS referencing_desciption,   
    COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
    referencing_class_desc, referenced_class_desc,   
    referenced_server_name, referenced_database_name, referenced_schema_name,   
    referenced_entity_name,   
    COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,   
    is_caller_dependent, is_ambiguous  
FROM sys.sql_expression_dependencies AS sed  
INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
WHERE referencing_id = OBJECT_ID(N'Person.iuPerson');   
GO  
  
```  
  
#### <a name="to-view-information-about-dml-triggers-in-the-database"></a><span data-ttu-id="4ef88-157">Para exibir informações sobre os gatilhos DML no banco de dados</span><span class="sxs-lookup"><span data-stu-id="4ef88-157">To view information about DML triggers in the database</span></span>  
  
1.  <span data-ttu-id="4ef88-158">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef88-158">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4ef88-159">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-159">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4ef88-160">Copie e cole um dos exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-160">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="4ef88-161">Cada exemplo mostra como você pode exibir informações sobre os gatilhos DML (`TR`) no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ef88-161">Each example shows how you can view information about DML triggers (`TR`) in the database.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT  name, parent_id, create_date, modify_date, is_instead_of_trigger  
FROM sys.triggers  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT  name, object_id, schema_id, parent_object_id, type_desc, create_date, modify_date, is_published  
FROM sys.objects  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECTPROPERTY(OBJECT_ID(N'Person.iuPerson'), 'ExecIsInsteadOfTrigger');   
GO  
  
```  
  
#### <a name="to-view-information-about-events-that-fire-a-dml-trigger"></a><span data-ttu-id="4ef88-162">Para exibir informações sobre os eventos que acionam um gatilho DML</span><span class="sxs-lookup"><span data-stu-id="4ef88-162">To view information about events that fire a DML trigger</span></span>  
  
1.  <span data-ttu-id="4ef88-163">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ef88-163">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4ef88-164">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-164">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4ef88-165">Copie e cole um dos exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4ef88-165">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="4ef88-166">Cada exemplo mostra como você pode exibir os eventos que disparam o gatilho `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="4ef88-166">Each example shows how you can view the events that fire the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT object_id, type, type_desc, is_trigger_event, event_group_type, event_group_type_desc   
FROM sys.events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO   
SELECT object_id, type,is_first, is_last  
FROM sys.trigger_events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ef88-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4ef88-167">See Also</span></span>  
 <span data-ttu-id="4ef88-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="4ef88-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ef88-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="4ef88-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4ef88-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
  
