---
title: Criar um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- new stored procedures
- stored procedures [SQL Server], creating
- creating stored procedures
ms.assetid: 76e8a6ba-1381-4620-b356-4311e1331ca7
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6781840e6a6c84773f40a6cd0557ccb79b676eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582346"
---
# <a name="create-a-stored-procedure"></a><span data-ttu-id="daa9f-102">Criar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="daa9f-102">Create a Stored Procedure</span></span>
  <span data-ttu-id="daa9f-103">Este tópico descreve como criar um procedimento armazenado [!INCLUDE[tsql](../../includes/tsql-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e a declaração [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="daa9f-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE statement.</span></span>  
  
##  <a name="Top"></a>   
-   <span data-ttu-id="daa9f-104">**Antes de começar:**  [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="daa9f-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="daa9f-105">**Para criar um procedimento usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="daa9f-105">**To create a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="daa9f-106">Permissões</span><span class="sxs-lookup"><span data-stu-id="daa9f-106">Permissions</span></span>  
 <span data-ttu-id="daa9f-107">Requer a permissão CREATE PROCEDURE no banco de dados e a permissão ALTER no esquema no qual o procedimento está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="daa9f-107">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
##  <a name="how-to-create-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="daa9f-108">Como criar um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="daa9f-108">How to Create a Stored Procedure</span></span>  
 <span data-ttu-id="daa9f-109">Você pode usar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="daa9f-109">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="daa9f-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daa9f-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="daa9f-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daa9f-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="daa9f-112">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daa9f-112">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="daa9f-113">**Para criar um procedimento no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="daa9f-113">**To create a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="daa9f-114">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="daa9f-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="daa9f-115">Expanda **Bancos de Dados**, expanda o banco de dados do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] e, em seguida, expanda **Programação**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="daa9f-116">Clique com o botão direito do mouse em **Procedimentos Armazenados**e clique em **Novo Procedimento Armazenado**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-116">Right-click **Stored Procedures**, and then click **New Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="daa9f-117">No menu **Consulta** , clique em **Especificar Valores para Parâmetros de Modelo**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="daa9f-118">Na caixa de diálogo **Especificar Valores para Parâmetros de Modelo** , digite os seguintes valores para os parâmetros mostrados.</span><span class="sxs-lookup"><span data-stu-id="daa9f-118">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="daa9f-119">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="daa9f-119">Parameter</span></span>|<span data-ttu-id="daa9f-120">Valor</span><span class="sxs-lookup"><span data-stu-id="daa9f-120">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="daa9f-121">Autor</span><span class="sxs-lookup"><span data-stu-id="daa9f-121">Author</span></span>|<span data-ttu-id="daa9f-122">*Seu nome*</span><span class="sxs-lookup"><span data-stu-id="daa9f-122">*Your name*</span></span>|  
    |<span data-ttu-id="daa9f-123">Data de criação</span><span class="sxs-lookup"><span data-stu-id="daa9f-123">Create Date</span></span>|<span data-ttu-id="daa9f-124">*A data de hoje*</span><span class="sxs-lookup"><span data-stu-id="daa9f-124">*Today's date*</span></span>|  
    |<span data-ttu-id="daa9f-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="daa9f-125">Description</span></span>|<span data-ttu-id="daa9f-126">Retorna dados de funcionário.</span><span class="sxs-lookup"><span data-stu-id="daa9f-126">Returns employee data.</span></span>|  
    |<span data-ttu-id="daa9f-127">Procedure_name</span><span class="sxs-lookup"><span data-stu-id="daa9f-127">Procedure_name</span></span>|<span data-ttu-id="daa9f-128">HumanResources.uspGetEmployeesTest</span><span class="sxs-lookup"><span data-stu-id="daa9f-128">HumanResources.uspGetEmployeesTest</span></span>|  
    |@Param1|@LastName|  
    |@Datatype_For_Param1|<span data-ttu-id="daa9f-129">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="daa9f-129">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="daa9f-130">Default_Value_For_Param1</span><span class="sxs-lookup"><span data-stu-id="daa9f-130">Default_Value_For_Param1</span></span>|<span data-ttu-id="daa9f-131">NULO</span><span class="sxs-lookup"><span data-stu-id="daa9f-131">NULL</span></span>|  
    |@Param2|@FirstName|  
    |@Datatype_For_Param2|<span data-ttu-id="daa9f-132">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="daa9f-132">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="daa9f-133">Default_Value_For_Param2</span><span class="sxs-lookup"><span data-stu-id="daa9f-133">Default_Value_For_Param2</span></span>|<span data-ttu-id="daa9f-134">NULO</span><span class="sxs-lookup"><span data-stu-id="daa9f-134">NULL</span></span>|  
  
6.  <span data-ttu-id="daa9f-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-135">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="daa9f-136">No **Editor de Consultas**, substitua a instrução SELECT pela seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="daa9f-136">In the **Query Editor**, replace the SELECT statement with the following statement:</span></span>  
  
    ```sql  
    SELECT FirstName, LastName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory  
    WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    ```  
  
8.  <span data-ttu-id="daa9f-137">Para testar a sintaxe, no menu **Consulta** , clique em **Analisar**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-137">To test the syntax, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="daa9f-138">Se uma mensagem de erro for retornada, compare as instruções com as informações acima e corrija conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="daa9f-138">If an error message is returned, compare the statements with the information above and correct as needed.</span></span>  
  
9. <span data-ttu-id="daa9f-139">Para criar o procedimento, no menu **Consulta** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-139">To create the procedure, from  the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="daa9f-140">O procedimento é criado como um objeto no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="daa9f-140">The procedure is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="daa9f-141">Para ver o procedimento listado no Pesquisador de Objetos, clique com o botão direito do mouse em **Procedimentos Armazenados** e selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-141">To see the procedure listed in Object Explorer, right-click **Stored Procedures** and select **Refresh**.</span></span>  
  
11. <span data-ttu-id="daa9f-142">Para executar o procedimento, no Pesquisador de Objetos, clique com o botão direito do mouse no nome do procedimento armazenado **HumanResources.uspGetEmployeesTest** e selecione **Executar Procedimento Armazenado**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-142">To run the procedure, in Object Explorer, right-click the stored procedure name **HumanResources.uspGetEmployeesTest** and select **Execute Stored Procedure**.</span></span>  
  
12. <span data-ttu-id="daa9f-143">Na janela **Executar Procedimento**, insira Margheim como o valor para o parâmetro @LastName e insira o valor Diane como o valor para o parâmetro @FirstName.</span><span class="sxs-lookup"><span data-stu-id="daa9f-143">In the **Execute Procedure** window, enter Margheim as the value for the parameter @LastName and enter the value Diane as the value for the parameter @FirstName.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="daa9f-144">Valide todas as entradas de usuário.</span><span class="sxs-lookup"><span data-stu-id="daa9f-144">Validate all user input.</span></span> <span data-ttu-id="daa9f-145">Não concatene a entrada de usuário antes de validá-la.</span><span class="sxs-lookup"><span data-stu-id="daa9f-145">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="daa9f-146">Nunca execute um comando construído por uma entrada de usuário inválida.</span><span class="sxs-lookup"><span data-stu-id="daa9f-146">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="daa9f-147">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daa9f-147">Using Transact-SQL</span></span>  
 <span data-ttu-id="daa9f-148">**Para criar um procedimento no Editor de Consultas**</span><span class="sxs-lookup"><span data-stu-id="daa9f-148">**To create a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="daa9f-149">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daa9f-149">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="daa9f-150">No menu **Arquivo** , clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-150">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="daa9f-151">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="daa9f-152">Este exemplo cria o mesmo procedimento armazenado descrito acima usando um nome de procedimento diferente.</span><span class="sxs-lookup"><span data-stu-id="daa9f-152">This example creates the same stored procedure as above using a different procedure name.</span></span>  
  
    ```sql
    USE AdventureWorks2012;  
    GO  
    CREATE PROCEDURE HumanResources.uspGetEmployeesTest2   
        @LastName nvarchar(50),   
        @FirstName nvarchar(50)   
    AS
  
        SET NOCOUNT ON;  
        SELECT FirstName, LastName, Department  
        FROM HumanResources.vEmployeeDepartmentHistory  
        WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    GO
    ```  
  
4.  <span data-ttu-id="daa9f-153">Para executar o procedimento, copie e cole o exemplo a seguir em uma nova janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="daa9f-153">To run the procedure, copy and paste the following example into a new query window and click **Execute**.</span></span> <span data-ttu-id="daa9f-154">Observe que métodos diferentes de especificar os valores de parâmetros são mostrados.</span><span class="sxs-lookup"><span data-stu-id="daa9f-154">Notice that different methods of specifying the parameter values are shown.</span></span>  
  
    ```sql
    EXECUTE HumanResources.uspGetEmployeesTest2 N'Ackerman', N'Pilar';  
    -- Or  
    EXEC HumanResources.uspGetEmployeesTest2 @LastName = N'Ackerman', @FirstName = N'Pilar';  
    GO  
    -- Or  
    EXECUTE HumanResources.uspGetEmployeesTest2 @FirstName = N'Pilar', @LastName = N'Ackerman';  
    GO
    ```  
  
## <a name="see-also"></a><span data-ttu-id="daa9f-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="daa9f-155">See Also</span></span>  
 [<span data-ttu-id="daa9f-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="daa9f-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  