---
title: Criar funções definidas pelo usuário (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- SCHEMABINDING clause
- schema-bound functions [SQL Server]
- user-defined functions [SQL Server], creating
- CREATE FUNCTION statement
- valid statements [SQL Server]
ms.assetid: f0d5dd10-73fd-4e05-9177-07f56552bdf7
author: rothja
ms.author: jroth
ms.openlocfilehash: 790fa1b969f933890e050311173fcde3f12c37ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582856"
---
# <a name="create-user-defined-functions-database-engine"></a><span data-ttu-id="c3bdd-102">Criar funções definidas pelo usuário (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="c3bdd-102">Create User-defined Functions (Database Engine)</span></span>
  <span data-ttu-id="c3bdd-103">Este tópico descreve como criar uma função definida pelo usuário [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3bdd-103">This topic describes how to create a user-defined function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c3bdd-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c3bdd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c3bdd-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c3bdd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c3bdd-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c3bdd-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c3bdd-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="c3bdd-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c3bdd-108">**Para criar uma função definida pelo usuário:**</span><span class="sxs-lookup"><span data-stu-id="c3bdd-108">**To create a user-defined function:**</span></span>  
  
     [<span data-ttu-id="c3bdd-109">Criar uma função escalar</span><span class="sxs-lookup"><span data-stu-id="c3bdd-109">Create a Scalar Function</span></span>](#Scalar)  
  
     [<span data-ttu-id="c3bdd-110">Criar uma função com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="c3bdd-110">Create a Table-valued Function</span></span>](#TVF)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c3bdd-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c3bdd-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c3bdd-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c3bdd-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c3bdd-113">Funções definidas pelo usuário não podem ser usadas para executar ações que modificam o estado do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-113">User-defined functions cannot be used to perform actions that modify the database state.</span></span>  
  
-   <span data-ttu-id="c3bdd-114">As funções definidas pelo usuário não podem conter uma cláusula OUTPUT INTO que tenha uma tabela como seu destino.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-114">User-defined functions cannot contain an OUTPUT INTO clause that has a table as its target.</span></span>  
  
-   <span data-ttu-id="c3bdd-115">As funções definidas pelo usuário não podem retornar vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-115">User-defined functions can not return multiple result sets.</span></span> <span data-ttu-id="c3bdd-116">Use um procedimento armazenado se precisar retornar vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-116">Use a stored procedure if you need to return multiple result sets.</span></span>  
  
-   <span data-ttu-id="c3bdd-117">O tratamento de erros é restringido em uma função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-117">Error handling is restricted in a user-defined function.</span></span> <span data-ttu-id="c3bdd-118">Um UDF não dá suporte A TRY... CATCH @ERROR ou RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-118">A UDF does not support TRY...CATCH, @ERROR or RAISERROR.</span></span>  
  
-   <span data-ttu-id="c3bdd-119">As funções definidas pelo usuário não podem chamar um procedimento armazenado, mas podem chamar um procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-119">User-defined functions cannot call a stored procedure, but can call an extended stored procedure.</span></span>  
  
-   <span data-ttu-id="c3bdd-120">As funções definidas pelo usuário não podem fazer uso de SQL dinâmico ou tabelas temporárias.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-120">User-defined functions cannot make use of dynamic SQL or temp tables.</span></span> <span data-ttu-id="c3bdd-121">Variáveis de tabela são permitidas.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-121">Table variables are allowed.</span></span>  
  
-   <span data-ttu-id="c3bdd-122">A instruções SET não são permitidas em uma função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-122">SET statements are not allowed in a user-defined function.</span></span>  
  
-   <span data-ttu-id="c3bdd-123">A cláusula FOR XML não é permitida.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-123">The FOR XML clause is not allowed</span></span>  
  
-   <span data-ttu-id="c3bdd-124">Funções definidas pelo usuário podem ser aninhadas, isto é, uma função definida pelo usuário pode chamar outra.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-124">User-defined functions can be nested; that is, one user-defined function can call another.</span></span> <span data-ttu-id="c3bdd-125">O nível de aninhamento é incrementado quando a execução da função é iniciada, e reduzido quando a execução da função chamada é concluída.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-125">The nesting level is incremented when the called function starts execution, and decremented when the called function finishes execution.</span></span> <span data-ttu-id="c3bdd-126">Até 32 níveis de funções definidas pelo usuário podem ser aninhados.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-126">User-defined functions can be nested up to 32 levels.</span></span> <span data-ttu-id="c3bdd-127">Se o máximo de níveis de aninhamento for excedido haverá falha em toda a cadeia de funções da chamada de aninhamento.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-127">Exceeding the maximum levels of nesting causes the whole calling function chain to fail.</span></span> <span data-ttu-id="c3bdd-128">Qualquer referência a um código gerenciado de uma função definida pelo usuário do Transact-SQL é contada como um nível em relação ao limite de 32 níveis de aninhamento.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-128">Any reference to managed code from a Transact-SQL user-defined function counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="c3bdd-129">Os métodos invocados a partir do código gerenciado não são contados em relação a esse limite.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-129">Methods invoked from within managed code do not count against this limit.</span></span>  
  
-   <span data-ttu-id="c3bdd-130">As seguintes instruções do Service Broker não podem ser incluídas na definição de uma função Transact-SQL definida pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="c3bdd-130">The following Service Broker statements cannot be included in the definition of a Transact-SQL user-defined function:</span></span>  
  
    -   <span data-ttu-id="c3bdd-131">BEGIN DIALOG CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="c3bdd-131">BEGIN DIALOG CONVERSATION</span></span>  
  
    -   <span data-ttu-id="c3bdd-132">END CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="c3bdd-132">END CONVERSATION</span></span>  
  
    -   <span data-ttu-id="c3bdd-133">GET CONVERSATION GROUP</span><span class="sxs-lookup"><span data-stu-id="c3bdd-133">GET CONVERSATION GROUP</span></span>  
  
    -   <span data-ttu-id="c3bdd-134">MOVE CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="c3bdd-134">MOVE CONVERSATION</span></span>  
  
    -   <span data-ttu-id="c3bdd-135">RECEIVE</span><span class="sxs-lookup"><span data-stu-id="c3bdd-135">RECEIVE</span></span>  
  
    -   <span data-ttu-id="c3bdd-136">SEND</span><span class="sxs-lookup"><span data-stu-id="c3bdd-136">SEND</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c3bdd-137">Segurança</span><span class="sxs-lookup"><span data-stu-id="c3bdd-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c3bdd-138">Permissões</span><span class="sxs-lookup"><span data-stu-id="c3bdd-138">Permissions</span></span>  
 <span data-ttu-id="c3bdd-139">Requer a permissão CREATE FUNCTION no banco de dados e a permissão ALTER no esquema no qual a função está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-139">Requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span> <span data-ttu-id="c3bdd-140">Se a função especificar um tipo definido pelo usuário, a permissão EXECUTE será exigida no tipo.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-140">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="scalar-functions"></a><a name="Scalar"></a><span data-ttu-id="c3bdd-141">Funções escalares</span><span class="sxs-lookup"><span data-stu-id="c3bdd-141">Scalar Functions</span></span>  
 <span data-ttu-id="c3bdd-142">O exemplo a seguir cria uma função escalar de várias instruções no banco de dados [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3bdd-142">The following example creates a multistatement scalar function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="c3bdd-143">A função pega um valor de entrada, um `ProductID`, e retorna um único valor de dados, a quantidade agregada do produto especificado no estoque.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-143">The function takes one input value, a `ProductID`, and returns a single data value, the aggregated quantity of the specified product in inventory.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufnGetInventoryStock', N'FN') IS NOT NULL  
    DROP FUNCTION ufnGetInventoryStock;  
GO  
CREATE FUNCTION dbo.ufnGetInventoryStock(@ProductID int)  
RETURNS int   
AS   
-- Returns the stock level for the product.  
BEGIN  
    DECLARE @ret int;  
    SELECT @ret = SUM(p.Quantity)   
    FROM Production.ProductInventory p   
    WHERE p.ProductID = @ProductID   
        AND p.LocationID = '6';  
     IF (@ret IS NULL)   
        SET @ret = 0;  
    RETURN @ret;  
END;  
GO  
  
```  
  
 <span data-ttu-id="c3bdd-144">O exemplo a seguir usa a função `ufnGetInventoryStock` , para retornar a quantidade atual do estoque dos produtos que têm um `ProductModelID` entre 75 e 80.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-144">The following example uses the `ufnGetInventoryStock` function to return the current inventory quantity for products that have a `ProductModelID` between 75 and 80.</span></span>  
  
```  
SELECT ProductModelID, Name, dbo.ufnGetInventoryStock(ProductID)AS CurrentSupply  
FROM Production.Product  
WHERE ProductModelID BETWEEN 75 and 80;  
  
```  
  
##  <a name="table-valued-functions"></a><a name="TVF"></a><span data-ttu-id="c3bdd-145">Funções com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="c3bdd-145">Table-Valued Functions</span></span>  
 <span data-ttu-id="c3bdd-146">O exemplo a seguir cria uma função com valor de tabela embutida no banco de dados [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3bdd-146">The following example creates an inline table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="c3bdd-147">A função pega um parâmetro de entrada, um ID cliente (loja), e retorna as colunas `ProductID`, `Name`e a agregação das vendas do ano, até a data atual, como `YTD Total` para cada produto vendido para a loja.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-147">The function takes one input parameter, a customer (store) ID, and returns the columns `ProductID`, `Name`, and the aggregate of year-to-date sales as `YTD Total` for each product sold to the store.</span></span>  
  
```  
IF OBJECT_ID (N'Sales.ufn_SalesByStore', N'IF') IS NOT NULL  
    DROP FUNCTION Sales.ufn_SalesByStore;  
GO  
CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
    FROM Production.Product AS P   
    JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
    JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
    JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
    WHERE C.StoreID = @storeid  
    GROUP BY P.ProductID, P.Name  
);  
  
```  
  
 <span data-ttu-id="c3bdd-148">O exemplo a seguir invoca a função e especifica a ID do cliente 602.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-148">The following example invokes the function and specifies customer ID 602.</span></span>  
  
```  
SELECT * FROM Sales.ufn_SalesByStore (602);  
  
```  
  
 <span data-ttu-id="c3bdd-149">O exemplo a seguir cria uma função com valor de tabela no banco de dados [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3bdd-149">The following example creates a table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="c3bdd-150">A função usa um único parâmetro de entrada, um `EmployeeID` , e retorna uma lista de todos os funcionários que reportam direta ou indiretamente ao funcionário especificado.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-150">The function takes a single input parameter, an `EmployeeID` and returns a list of all the employees who report to the specified employee directly or indirectly.</span></span> <span data-ttu-id="c3bdd-151">A função que especifica a ID do funcionário 109 é invocada em seguida.</span><span class="sxs-lookup"><span data-stu-id="c3bdd-151">The function is then invoked specifying employee ID 109.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufn_FindReports', N'TF') IS NOT NULL  
    DROP FUNCTION dbo.ufn_FindReports;  
GO  
CREATE FUNCTION dbo.ufn_FindReports (@InEmpID INTEGER)  
RETURNS @retFindReports TABLE   
(  
    EmployeeID int primary key NOT NULL,  
    FirstName nvarchar(255) NOT NULL,  
    LastName nvarchar(255) NOT NULL,  
    JobTitle nvarchar(50) NOT NULL,  
    RecursionLevel int NOT NULL  
)  
--Returns a result set that lists all the employees who report to the   
--specific employee directly or indirectly.*/  
AS  
BEGIN  
WITH EMP_cte(EmployeeID, OrganizationNode, FirstName, LastName, JobTitle, RecursionLevel) -- CTE name and columns  
    AS (  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, 0 -- Get the initial list of Employees for Manager n  
        FROM HumanResources.Employee e   
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        WHERE e.BusinessEntityID = @InEmpID  
        UNION ALL  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, RecursionLevel + 1 -- Join recursive member to anchor  
        FROM HumanResources.Employee e   
            INNER JOIN EMP_cte  
            ON e.OrganizationNode.GetAncestor(1) = EMP_cte.OrganizationNode  
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        )  
-- copy the required columns to the result of the function   
   INSERT @retFindReports  
   SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
   FROM EMP_cte   
   RETURN  
END;  
GO  
-- Example invocation  
SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
FROM dbo.ufn_FindReports(1);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3bdd-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3bdd-152">See Also</span></span>  
 <span data-ttu-id="c3bdd-153">[Funções definidas pelo usuário](user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="c3bdd-153">[User-Defined Functions](user-defined-functions.md) </span></span>  
 [<span data-ttu-id="c3bdd-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3bdd-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
