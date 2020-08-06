---
title: Gerenciar a segurança dos gatilhos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], security
ms.assetid: e94720a8-a3a2-4364-b0a3-bbe86e3ce4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: fdc176dcad50c3bf28f058c3724a01267975bfc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582864"
---
# <a name="manage-trigger-security"></a><span data-ttu-id="bf3ed-102">Gerenciar a segurança dos gatilhos</span><span class="sxs-lookup"><span data-stu-id="bf3ed-102">Manage Trigger Security</span></span>
  <span data-ttu-id="bf3ed-103">Por padrão, os gatilhos DML e DDL executam sob o contexto do usuário que aciona o gatilho.</span><span class="sxs-lookup"><span data-stu-id="bf3ed-103">By default, both DML and DDL triggers execute under the context of the user that calls the trigger.</span></span> <span data-ttu-id="bf3ed-104">O chamador do gatilho é o usuário que executa a instrução que faz com que o gatilho execute.</span><span class="sxs-lookup"><span data-stu-id="bf3ed-104">The caller of a trigger is the user that executes the statement that causes the trigger to run.</span></span> <span data-ttu-id="bf3ed-105">Por exemplo, se o usuário **Marina** executar uma instrução DELETE que faz com que o gatilho DML **DML_trigMarina** seja executado, o código dentro do **DML_trigMarina** executará no contexto dos privilégios do usuário para **Marina**.</span><span class="sxs-lookup"><span data-stu-id="bf3ed-105">For example, if user **Mary** executes a DELETE statement that causes DML trigger **DML_trigMary** to run, the code inside **DML_trigMary** executes in the context of the user privileges for **Mary**.</span></span> <span data-ttu-id="bf3ed-106">Esse comportamento padrão pode ser explorado pelos usuários que desejam apresentar um código mal-intencionado no banco de dados ou na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="bf3ed-106">This default behavior can be exploited by users who want to introduce malicious code in the database or server instance.</span></span> <span data-ttu-id="bf3ed-107">Por exemplo, o gatilho DDL a seguir é criado pelo usuário `JohnDoe`:</span><span class="sxs-lookup"><span data-stu-id="bf3ed-107">For example, the following DDL trigger is created by user `JohnDoe`:</span></span>  
  
 `CREATE TRIGGER DDL_trigJohnDoe`  
  
 `ON DATABASE`  
  
 `FOR ALTER_TABLE`  
  
 `AS`  
  
 `GRANT CONTROL SERVER TO JohnDoe ;`  
  
 `GO`  
  
 <span data-ttu-id="bf3ed-108">O que esse gatilho significa é que assim que um usuário tiver a permissão para executar uma instrução `GRANT CONTROL SERVER` , como um membro da função de servidor fixa **sysadmin** , ele executa uma instrução `ALTER TABLE` , `JohnDoe` recebe permissão `CONTROL SERVER` .</span><span class="sxs-lookup"><span data-stu-id="bf3ed-108">What this trigger means is that as soon as a user that has permission to execute a `GRANT CONTROL SERVER` statement, such as a member of the **sysadmin** fixed server role, executes an `ALTER TABLE` statement, `JohnDoe` is granted `CONTROL SERVER` permission.</span></span> <span data-ttu-id="bf3ed-109">Em outras palavras, embora `JohnDoe` não possa conceder permissão `CONTROL SERVER` para ele mesmo, ele habilita o código do gatilho que lhe concede essa permissão para executar sob privilégios escalados.</span><span class="sxs-lookup"><span data-stu-id="bf3ed-109">In other words, although `JohnDoe` cannot grant `CONTROL SERVER` permission to himself, he enabled the trigger code that grants him this permission to execute under escalated privileges.</span></span> <span data-ttu-id="bf3ed-110">Os gatilhos DML e DDL estão abertos para este tipo de ameaça à segurança.</span><span class="sxs-lookup"><span data-stu-id="bf3ed-110">Both DML and DDL triggers are open to this kind of security threat.</span></span>  
  
## <a name="trigger-security-best-practices"></a><span data-ttu-id="bf3ed-111">Práticas recomendadas para a segurança dos gatilhos</span><span class="sxs-lookup"><span data-stu-id="bf3ed-111">Trigger Security Best Practices</span></span>  
 <span data-ttu-id="bf3ed-112">Você pode tomar as medidas a seguir para impedir que o código do gatilho execute sob privilégios escalados:</span><span class="sxs-lookup"><span data-stu-id="bf3ed-112">You can take the following measures to prevent trigger code from executing under escalated privileges:</span></span>  
  
-   <span data-ttu-id="bf3ed-113">Lembre-se dos gatilhos DML e DDL que existem no banco de dados e na instância do servidor consultando as exibições de catálogo [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) e [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="bf3ed-113">Be aware of the DML and DDL triggers that exist in the database and on the server instance by querying the [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) and [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) catalog views.</span></span> <span data-ttu-id="bf3ed-114">A consulta a seguir retorna todos os gatilhos DML e DDL no nível de banco de dados no banco de dados atual e todos os gatilhos DDL no nível de servidor na instância do servidor:</span><span class="sxs-lookup"><span data-stu-id="bf3ed-114">The following query returns all DML and database-level DDL triggers in the current database, and all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    SELECT type, name, parent_class_desc FROM sys.triggers  
    UNION  
    SELECT type, name, parent_class_desc FROM sys.server_triggers ;  
    ```  
  
-   <span data-ttu-id="bf3ed-115">Use [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) para desabilitar os gatilhos que podem prejudicar a integridade do banco de dados ou do servidor caso sejam executados sob privilégios escalonados.</span><span class="sxs-lookup"><span data-stu-id="bf3ed-115">Use [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) to disable triggers that can harm the integrity of the database or server if the triggers execute under escalated privileges.</span></span> <span data-ttu-id="bf3ed-116">A instrução a seguir desabilita todos os gatilhos DDL no nível do banco de dados no banco de dados atual:</span><span class="sxs-lookup"><span data-stu-id="bf3ed-116">The following statement disables all database-level DDL triggers in the current database:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON DATABASE  
    ```  
  
     <span data-ttu-id="bf3ed-117">Essa instrução desabilita todos os gatilhos DDL no nível de servidor na instância do servidor:</span><span class="sxs-lookup"><span data-stu-id="bf3ed-117">This statement disables all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON ALL SERVER  
    ```  
  
     <span data-ttu-id="bf3ed-118">Essa instrução desabilita todos os gatilhos DML no banco de dados atual:</span><span class="sxs-lookup"><span data-stu-id="bf3ed-118">This statement disables all DML triggers in the current database:</span></span>  
  
    ```  
    DECLARE @schema_name sysname, @trigger_name sysname, @object_name sysname ;  
    DECLARE @sql nvarchar(max) ;  
    DECLARE trig_cur CURSOR FORWARD_ONLY READ_ONLY FOR  
        SELECT SCHEMA_NAME(schema_id) AS schema_name,  
            name AS trigger_name,  
            OBJECT_NAME(parent_object_id) as object_name  
        FROM sys.objects WHERE type in ('TR', 'TA') ;  
  
    OPEN trig_cur ;  
    FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        SELECT @sql = 'DISABLE TRIGGER ' + QUOTENAME(@schema_name) + '.'  
            + QUOTENAME(@trigger_name) +  
            ' ON ' + QUOTENAME(@schema_name) + '.'   
            + QUOTENAME(@object_name) + ' ; ' ;  
        EXEC (@sql) ;  
        FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
    END  
    GO  
  
    -- Verify triggers are disabled. Should return an empty result set.  
    SELECT * FROM sys.triggers WHERE is_disabled = 0 ;  
    GO  
  
    CLOSE trig_cur ;  
    DEALLOCATE trig_cur;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bf3ed-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf3ed-119">See Also</span></span>  
 <span data-ttu-id="bf3ed-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bf3ed-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="bf3ed-121">[Gatilhos DML](../triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="bf3ed-121">[DML Triggers](../triggers/dml-triggers.md) </span></span>  
 [<span data-ttu-id="bf3ed-122">Gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="bf3ed-122">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
