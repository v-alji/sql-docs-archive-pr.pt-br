---
title: Exibir as dependências de um procedimento armazenado| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], dependencies
- displaying stored procedure dependencies
- viewing stored procedure dependencies
ms.assetid: 6ae0a369-1bc7-4ae4-be89-2b483697cd1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 790684035d2db3b697fb8b718c96182eda8f1186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584095"
---
# <a name="view-the-dependencies-of-a-stored-procedure"></a><span data-ttu-id="fa7e6-102">Exibir as dependências de um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="fa7e6-102">View the Dependencies of a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-view-stored-procedure-dependencies-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="fa7e6-103">Este tópico descreve como exibir dependências de procedimento armazenado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa7e6-103">This topic describes how to view stored procedure dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="fa7e6-104">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="fa7e6-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="fa7e6-105">**Para exibir as dependências de um procedimento, usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="fa7e6-105">**To view the dependencies of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fa7e6-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fa7e6-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fa7e6-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="fa7e6-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fa7e6-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="fa7e6-108">Permissions</span></span>  
 <span data-ttu-id="fa7e6-109">Função do sistema: `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="fa7e6-109">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="fa7e6-110">Requer a permissão CONTROL da entidade referenciada e a permissão SELECT em sys.dm_sql_referencing_entities.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-110">Requires CONTROL permission on the referenced entity and SELECT permission on sys.dm_sql_referencing_entities.</span></span> <span data-ttu-id="fa7e6-111">Quando a entidade referenciada é uma função de partição, a permissão CONTROL é exigida no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-111">When the referenced entity is a partition function, CONTROL permission on the database is required.</span></span> <span data-ttu-id="fa7e6-112">Por padrão, a permissão SELECT é concedida a público.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-112">By default, SELECT permission is granted to public.</span></span>  
  
 <span data-ttu-id="fa7e6-113">Função do sistema: `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="fa7e6-113">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="fa7e6-114">Requer permissão SELECT em sys.dm_sql_referenced_entities e permissão VIEW DEFINITION na entidade de referência.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-114">Requires SELECT permission on sys.dm_sql_referenced_entities and VIEW DEFINITION permission on the referencing entity.</span></span> <span data-ttu-id="fa7e6-115">Por padrão, a permissão SELECT é concedida a público.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-115">By default, SELECT permission is granted to public.</span></span> <span data-ttu-id="fa7e6-116">Requer permissão VIEW DEFINITION no banco de dados ou permissão ALTER DATABASE DDL TRIGGER no banco de dados quando a entidade de referência é um gatilho DDL do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-116">Requires VIEW DEFINITION permission on the database or ALTER DATABASE DDL TRIGGER permission on the database when the referencing entity is a database-level DDL trigger.</span></span> <span data-ttu-id="fa7e6-117">Requer permissão de VIEW ANY DEFINITION no servidor quando a entidade de referência é um gatilho DDL de servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-117">Requires VIEW ANY DEFINITION permission on the server when the referencing entity is a server-level DDL trigger.</span></span>  
  
 <span data-ttu-id="fa7e6-118">Exibição do catálogo de objetos: `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="fa7e6-118">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="fa7e6-119">Requer permissão VIEW DEFINITION no banco de dados e permissão SELECT em sys.sql_expression_dependencies para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-119">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="fa7e6-120">Por padrão, a permissão SELECT é concedida somente a membros da função de banco de dados fixa db_owner.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-120">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="fa7e6-121">Quando são concedidas permissões SELECT e VIEW DEFINITION a outro usuário, o usuário autorizado pode exibir todas as dependências no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-121">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="how-to-view-the-dependencies-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="fa7e6-122">Como exibir as dependências de um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="fa7e6-122">How to View the Dependencies of a Stored Procedure</span></span>  
 <span data-ttu-id="fa7e6-123">Você pode usar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fa7e6-123">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="fa7e6-124">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fa7e6-124">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="fa7e6-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fa7e6-125">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fa7e6-126">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fa7e6-126">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="fa7e6-127">**Para exibir as dependências de um procedimento armazenado no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="fa7e6-127">**To view the dependencies of a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="fa7e6-128">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-128">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fa7e6-129">Expanda **Bancos de Dados**, expanda o banco de dados ao qual pertence o procedimento e expanda **Programação**.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-129">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="fa7e6-130">Expanda **Procedimentos Armazenados**, clique com o botão direito do mouse no procedimento e clique em **Exibir Dependências**.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-130">Expand **Stored Procedures**, right-click the procedure and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="fa7e6-131">Exiba a lista de objetos que dependem do procedimento.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-131">View the list of objects that depend on the procedure.</span></span>  
  
5.  <span data-ttu-id="fa7e6-132">Exiba a lista de objetos dos quais o procedimento depende.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-132">View the list of objects on which the procedure depends.</span></span>  
  
6.  <span data-ttu-id="fa7e6-133">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-133">Click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fa7e6-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fa7e6-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="fa7e6-135">**Para exibir as dependências de um procedimento no Editor de Consultas**</span><span class="sxs-lookup"><span data-stu-id="fa7e6-135">**To view the dependencies of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="fa7e6-136">Função do sistema: `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="fa7e6-136">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="fa7e6-137">Esta função é usada para exibir os objetos que dependem de um procedimento.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-137">This function is used to display the objects that depend on a procedure.</span></span>  
  
1.  <span data-ttu-id="fa7e6-138">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fa7e6-139">Expanda **Bancos de Dados**e o banco de dados ao qual o procedimento pertence.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-139">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="fa7e6-140">Clique em **Nova Consulta** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="fa7e6-140">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="fa7e6-141">Copie e cole os exemplos a seguir no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-141">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="fa7e6-142">O primeiro exemplo cria o procedimento `uspVendorAllInfo` , que retorna os nomes de todos os fornecedores no banco de dados [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , os produtos que eles fornecem, suas classificações de crédito e sua disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-142">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="fa7e6-143">Depois que o procedimento é criado, o segundo exemplo usa a função sys.dm_sql_referencing_entities para exibir os objetos que dependem do procedimento.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-143">After the procedure is created, the second example uses the sys.dm_sql_referencing_entities function to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referencing_schema_name, referencing_entity_name, referencing_id, referencing_class_desc, is_caller_dependent  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');   
    GO  
  
    ```  
  
 <span data-ttu-id="fa7e6-144">Função do sistema: `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="fa7e6-144">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="fa7e6-145">Esta função é usada para exibir os objetos dos quais um procedimento depende.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-145">This function is used to display the objects a procedure depends on.</span></span>  
  
1.  <span data-ttu-id="fa7e6-146">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-146">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fa7e6-147">Expanda **Bancos de Dados**e o banco de dados ao qual o procedimento pertence.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-147">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="fa7e6-148">Clique em **Nova Consulta** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="fa7e6-148">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="fa7e6-149">Copie e cole os exemplos a seguir no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-149">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="fa7e6-150">O primeiro exemplo cria o procedimento `uspVendorAllInfo` , que retorna os nomes de todos os fornecedores no banco de dados [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , os produtos que eles fornecem, suas classificações de crédito e sua disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-150">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="fa7e6-151">Depois que o procedimento é criado, o segundo exemplo usa a função sys.dm_sql_referenced_entities para exibir os objetos dos quais o procedimento depende.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-151">After the procedure is created, the second example uses the sys.dm_sql_referenced_entities function to display the objects that the procedure depends on.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referenced_schema_name, referenced_entity_name,  
    referenced_minor_name,referenced_minor_id, referenced_class_desc,  
    is_caller_dependent, is_ambiguous  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');  
    GO  
    ```  
  
 <span data-ttu-id="fa7e6-152">Exibição do catálogo de objetos: `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="fa7e6-152">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="fa7e6-153">Esta exibição pode ser usada para exibir objetos dos quais um procedimento depende ou que dependem de um procedimento.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-153">This view can be used to display objects that a procedure depends on or that depend on a procedure.</span></span>  
  
 <span data-ttu-id="fa7e6-154">Exibindo os objetos que dependem de um procedimento.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-154">Displaying the objects that depend on a procedure.</span></span>  
 1.  <span data-ttu-id="fa7e6-155">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fa7e6-156">Expanda **Bancos de Dados**e o banco de dados ao qual o procedimento pertence.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-156">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="fa7e6-157">Clique em **Nova Consulta** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="fa7e6-157">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="fa7e6-158">Copie e cole os exemplos a seguir no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-158">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="fa7e6-159">O primeiro exemplo cria o procedimento `uspVendorAllInfo` , que retorna os nomes de todos os fornecedores no banco de dados [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , os produtos que eles fornecem, suas classificações de crédito e sua disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-159">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="fa7e6-160">Depois que o procedimento é criado, o segundo exemplo usa a exibição sys.sql_expression_dependencies para exibir os objetos que dependem do procedimento.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-160">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_SCHEMA_NAME ( referencing_id ) AS referencing_schema_name,  
        OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referenced_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
 <span data-ttu-id="fa7e6-161">Exibindo os objetos dois quais um procedimento depende.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-161">Displaying the objects a procedure depends on.</span></span>  
 1.  <span data-ttu-id="fa7e6-162">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fa7e6-163">Expanda **Bancos de Dados**e o banco de dados ao qual o procedimento pertence.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-163">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="fa7e6-164">Clique em **Nova Consulta** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="fa7e6-164">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="fa7e6-165">Copie e cole os exemplos a seguir no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-165">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="fa7e6-166">O primeiro exemplo cria o procedimento `uspVendorAllInfo` , que retorna os nomes de todos os fornecedores no banco de dados [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , os produtos que eles fornecem, suas classificações de crédito e sua disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-166">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="fa7e6-167">Depois que o procedimento é criado, o segundo exemplo usa a exibição sys.sql_expression_dependencies para exibir os objetos dos quais o procedimento depende.</span><span class="sxs-lookup"><span data-stu-id="fa7e6-167">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects the procedure depends on.</span></span>  
  
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
    WHERE referencing_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fa7e6-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa7e6-168">See Also</span></span>  
 <span data-ttu-id="fa7e6-169">[Renomear um procedimento armazenado](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="fa7e6-169">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="fa7e6-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa7e6-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span></span>  
 <span data-ttu-id="fa7e6-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa7e6-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span></span>  
 [<span data-ttu-id="fa7e6-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fa7e6-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
  
