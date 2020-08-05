---
title: Exibir a definição de um procedimento armazenado| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], viewing
- definition of stored procedure
- viewing stored procedures
- displaying stored procedures
ms.assetid: 93318587-a0c5-4788-946f-3b5dc8372ea9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4da455d38f984b08ee1f396f26cd4cc85411be92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573882"
---
# <a name="view-the-definition-of-a-stored-procedure"></a><span data-ttu-id="2a867-102">Exibir a definição de um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="2a867-102">View the Definition of a Stored Procedure</span></span>
    
##  <a name="you-can-view-the-definition-of-a-stored-procedure-in-ssmanstudiofull-using-object-explorer-menu-options-or-in-the-query-editor-using-tsql-this-topic-describes-how-to-view-the-definition-of-procedure-in-object-explorer-and-by-using-a-system-stored-procedure-system-function-and-object-catalog-view-in-the-query-editor"></a><a name="Top"></a> <span data-ttu-id="2a867-103">Você pode exibir a definição de um procedimento armazenamento no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando as opções de menu do Pesquisador de Objetos ou no Editor de Consultas usando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a867-103">You can view the definition of a stored procedure in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or in the Query Editor using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2a867-104">Este tópico descreve como exibir a definição de procedimento no Pesquisador de Objetos e usando um procedimento armazenado do sistema, uma função de sistema e a exibição do catálogo de objetos no Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="2a867-104">This topic describes how to view the definition of procedure in Object Explorer and by using a system stored procedure, system function, and object catalog view in the Query Editor.</span></span>  
  
-   <span data-ttu-id="2a867-105">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="2a867-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="2a867-106">**Para exibir a definição de um procedimento, usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="2a867-106">**To view the definition of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2a867-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2a867-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2a867-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="2a867-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2a867-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="2a867-109">Permissions</span></span>  
 <span data-ttu-id="2a867-110">Procedimento armazenado do sistema: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="2a867-110">System Stored Procedure: `sp_helptext`</span></span>  
 <span data-ttu-id="2a867-111">Requer associação à função **pública** .</span><span class="sxs-lookup"><span data-stu-id="2a867-111">Requires membership in the **public** role.</span></span> <span data-ttu-id="2a867-112">Definições de objeto de sistema são publicamente visíveis.</span><span class="sxs-lookup"><span data-stu-id="2a867-112">System object definitions are publicly visible.</span></span> <span data-ttu-id="2a867-113">A definição de objetos de usuário é visível ao proprietário do objeto e às entidades autorizadas que têm uma das seguintes permissões: ALTER, CONTROL, TAKE OWNERSHIP ou VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="2a867-113">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span>  
  
 <span data-ttu-id="2a867-114">Função do sistema: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="2a867-114">System Function: `OBJECT_DEFINITION`</span></span>  
 <span data-ttu-id="2a867-115">Definições de objeto de sistema são publicamente visíveis.</span><span class="sxs-lookup"><span data-stu-id="2a867-115">System object definitions are publicly visible.</span></span> <span data-ttu-id="2a867-116">A definição de objetos de usuário é visível ao proprietário do objeto e às entidades autorizadas que têm uma das seguintes permissões: ALTER, CONTROL, TAKE OWNERSHIP ou VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="2a867-116">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="2a867-117">Estas permissões são mantidas implicitamente por membros das funções fixas de banco de dados **db_owner**, **db_ddladmin**e **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="2a867-117">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="2a867-118">Exibição do catálogo de objetos: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="2a867-118">Object Catalog View: `sys.sql_modules`</span></span>  
 <span data-ttu-id="2a867-119">A visibilidade dos metadados em exibições do catálogo está limitada aos protegíveis que pertencem a um usuário ou para os quais o usuário recebeu permissão.</span><span class="sxs-lookup"><span data-stu-id="2a867-119">The visibility of the metadata in catalog views is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="2a867-120">Para obter mais informações, consulte [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="2a867-120">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="how-to-view-the-definition-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="2a867-121">Como exibir as definições de um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="2a867-121">How to View the Definition of a Stored Procedure</span></span>  
 <span data-ttu-id="2a867-122">Você pode usar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="2a867-122">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="2a867-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a867-123">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="2a867-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a867-124">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2a867-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a867-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2a867-126">**Para exibir a definição de um procedimento armazenado no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="2a867-126">**To view the definition a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="2a867-127">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="2a867-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2a867-128">Expanda **Bancos de Dados**, expanda o banco de dados ao qual pertence o procedimento e expanda **Programação**.</span><span class="sxs-lookup"><span data-stu-id="2a867-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="2a867-129">Expanda **Procedimentos armazenados**, clique com o botão direito do mouse no procedimento, clique em **Gerar script de procedimento armazenado como** e clique em um dos itens a seguir: **Criar para**, **Alterar para** ou **Descartar e criar para**.</span><span class="sxs-lookup"><span data-stu-id="2a867-129">Expand **Stored Procedures**, right-click the procedure and then click **Script Stored Procedure as**, and then click one of the following: **Create To**, **Alter To**, or **Drop and Create To**.</span></span>  
  
4.  <span data-ttu-id="2a867-130">Selecione **Janela do Editor de Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2a867-130">Select **New Query Editor Window**.</span></span> <span data-ttu-id="2a867-131">Isso exibirá a definição de procedimento.</span><span class="sxs-lookup"><span data-stu-id="2a867-131">This will display the procedure definition.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2a867-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a867-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="2a867-133">**Para exibir a definição de um procedimento no Editor de Consultas**</span><span class="sxs-lookup"><span data-stu-id="2a867-133">**To view the definition of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="2a867-134">Procedimento armazenado do sistema: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="2a867-134">System Stored Procedure: `sp_helptext`</span></span>  
 1.  <span data-ttu-id="2a867-135">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a867-135">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a867-136">Na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2a867-136">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2a867-137">Na janela de consulta, insira a instrução a seguir que usa o procedimento armazenado do sistema `sp_helptext`.</span><span class="sxs-lookup"><span data-stu-id="2a867-137">In the query window, enter the following statement that uses the `sp_helptext` system stored procedure.</span></span> <span data-ttu-id="2a867-138">Altere os nomes do banco de dados e do procedimento armazenado para fazer referência ao banco de dados e ao procedimento armazenado que você quer.</span><span class="sxs-lookup"><span data-stu-id="2a867-138">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_helptext N'AdventureWorks2012.dbo.uspLogError';  
    ```  
  
 <span data-ttu-id="2a867-139">Função do sistema: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="2a867-139">System Function: `OBJECT_DEFINITION`</span></span>  
 1.  <span data-ttu-id="2a867-140">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a867-140">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a867-141">Na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2a867-141">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2a867-142">Na janela de consulta, insira as instruções a seguir que usam a função de sistema `OBJECT_DEFINITION`.</span><span class="sxs-lookup"><span data-stu-id="2a867-142">In the query window, enter the following statements that use the `OBJECT_DEFINITION` system function.</span></span> <span data-ttu-id="2a867-143">Altere os nomes do banco de dados e do procedimento armazenado para fazer referência ao banco de dados e ao procedimento armazenado que você quer.</span><span class="sxs-lookup"><span data-stu-id="2a867-143">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
 <span data-ttu-id="2a867-144">Exibição do catálogo de objetos: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="2a867-144">Object Catalog View: `sys.sql_modules`</span></span>  
 1.  <span data-ttu-id="2a867-145">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a867-145">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a867-146">Na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2a867-146">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2a867-147">Na janela de consulta, insira as instruções a seguir que usam a exibição de catálogo `sys.sql_modules`.</span><span class="sxs-lookup"><span data-stu-id="2a867-147">In the query window, enter the following statements that use the `sys.sql_modules` catalog view.</span></span> <span data-ttu-id="2a867-148">Altere os nomes do banco de dados e do procedimento armazenado para fazer referência ao banco de dados e ao procedimento armazenado que você quer.</span><span class="sxs-lookup"><span data-stu-id="2a867-148">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition  
    FROM sys.sql_modules  
    WHERE object_id = (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2a867-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2a867-149">See Also</span></span>  
 <span data-ttu-id="2a867-150">[Criar um procedimento armazenado](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="2a867-150">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="2a867-151">[Modificar um procedimento armazenado](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="2a867-151">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="2a867-152">[Excluir um procedimento armazenado](delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="2a867-152">[Delete a Stored Procedure](delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="2a867-153">[Renomear um procedimento armazenado](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="2a867-153">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="2a867-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a867-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span></span>  
 <span data-ttu-id="2a867-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a867-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="2a867-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a867-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span></span>  
 [<span data-ttu-id="2a867-157">OBJECT_ID &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2a867-157">OBJECT_ID &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-id-transact-sql)  
  
  
