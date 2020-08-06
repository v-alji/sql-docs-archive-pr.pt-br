---
title: Renomear um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], renaming
- renaming stored procedures
ms.assetid: 5d2e4c68-7e0b-4405-8919-f5b203e46770
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02e1acb528a32ef242e160e0ce5dd0267237c876
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584100"
---
# <a name="rename-a-stored-procedure"></a><span data-ttu-id="c918e-102">Renomear um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="c918e-102">Rename a Stored Procedure</span></span>
  <span data-ttu-id="c918e-103">Este tópico descreve como renomear um procedimento armazenado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c918e-103">This topic describes how to rename a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c918e-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c918e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c918e-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c918e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c918e-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c918e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c918e-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="c918e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c918e-108">**Para renomear um procedimento armazenado, usando:**</span><span class="sxs-lookup"><span data-stu-id="c918e-108">**To rename a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="c918e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c918e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c918e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c918e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c918e-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c918e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c918e-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c918e-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c918e-113">Os nomes de procedimento devem estar de acordo com as regras para [identificadores](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="c918e-113">Procedure names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="c918e-114">Renomear uma procedimento armazenado não alterará o nome do objeto correspondente na coluna de definição da exibição de catálogo **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="c918e-114">Renaming a stored procedure will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="c918e-115">Assim, é recomendável não renomear esse tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="c918e-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="c918e-116">Em vez disso, remova-o e recrie o procedimento armazenado com seu nome novo.</span><span class="sxs-lookup"><span data-stu-id="c918e-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="c918e-117">A alteração do nome ou definição de um procedimento pode causar falha em objetos dependentes que não são atualizados para refletir as alterações que tenham sido feitas no procedimento.</span><span class="sxs-lookup"><span data-stu-id="c918e-117">Changing the name or definition of a procedure can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the procedure.</span></span> <span data-ttu-id="c918e-118">Para obter mais informações, veja [Exibir as dependências de um procedimento armazenado](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="c918e-118">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c918e-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="c918e-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c918e-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="c918e-120">Permissions</span></span>  
 <span data-ttu-id="c918e-121">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="c918e-121">CREATE PROCEDURE</span></span>  
 <span data-ttu-id="c918e-122">Exige a permissão CREATE PROCEDURE no banco de dados e a permissão ALTER no esquema em que o procedimento está sendo criado, ou exige a associação na função de banco de dados fixa **db_ddladmin**.</span><span class="sxs-lookup"><span data-stu-id="c918e-122">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created, or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
 <span data-ttu-id="c918e-123">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="c918e-123">ALTER PROCEDURE</span></span>  
 <span data-ttu-id="c918e-124">Exige a permissão ALTER no procedimento, ou exige a associação na função de banco de dados fixa **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="c918e-124">Requires ALTER permission on the procedure or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c918e-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c918e-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="c918e-126">Para renomear um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="c918e-126">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="c918e-127">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="c918e-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c918e-128">Expanda **Bancos de Dados**, expanda o banco de dados ao qual pertence o procedimento e expanda **Programação**.</span><span class="sxs-lookup"><span data-stu-id="c918e-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="c918e-129">[Determinar as dependências do procedimento armazenado](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="c918e-129">[Determine the dependencies of the stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
4.  <span data-ttu-id="c918e-130">Expanda **Procedimentos Armazenados**, clique com o botão direito do mouse no procedimento a ser renomeado e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="c918e-130">Expand **Stored Procedures**, right-click the procedure to rename, and then click **Rename**.</span></span>  
  
5.  <span data-ttu-id="c918e-131">Modifique o nome do procedimento.</span><span class="sxs-lookup"><span data-stu-id="c918e-131">Modify the procedure name.</span></span>  
  
6.  <span data-ttu-id="c918e-132">Modifique o nome do procedimento referenciado em qualquer objeto dependente ou script.</span><span class="sxs-lookup"><span data-stu-id="c918e-132">Modify the procedure name referenced in any dependent objects or scripts.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c918e-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c918e-133">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="c918e-134">Para renomear um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="c918e-134">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="c918e-135">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c918e-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c918e-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c918e-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c918e-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c918e-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c918e-138">Este exemplo mostra como renomear um procedimento removendo-o e recriando-o com um novo nome.</span><span class="sxs-lookup"><span data-stu-id="c918e-138">This example shows how to rename a procedure by dropping the procedure and re-creating the procedure with a new name.</span></span> <span data-ttu-id="c918e-139">O primeiro exemplo cria o procedimento armazenado `'HumanResources.uspGetAllEmployeesTest`.</span><span class="sxs-lookup"><span data-stu-id="c918e-139">The first example creates the stored procedure `'HumanResources.uspGetAllEmployeesTest`.</span></span> <span data-ttu-id="c918e-140">O segundo exemplo renomeia o procedimento armazenado para `HumanResources.uspEveryEmployeeTest`.</span><span class="sxs-lookup"><span data-stu-id="c918e-140">The second example renames the stored procedure to `HumanResources.uspEveryEmployeeTest`.</span></span>  
  
```sql  
--Create the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspGetAllEmployeesTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
  
--Rename the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspEveryEmployeeTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c918e-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c918e-141">See Also</span></span>  
 <span data-ttu-id="c918e-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c918e-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span></span>  
 <span data-ttu-id="c918e-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c918e-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="c918e-144">[Criar um procedimento armazenado](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c918e-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="c918e-145">[Modificar um procedimento armazenado](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c918e-145">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="c918e-146">[Excluir um procedimento armazenado](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c918e-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="c918e-147">[Exibir a definição de um procedimento armazenado](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c918e-147">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="c918e-148">Exibir as dependências de um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="c918e-148">View the Dependencies of a Stored Procedure</span></span>](view-the-dependencies-of-a-stored-procedure.md)  
  
  
