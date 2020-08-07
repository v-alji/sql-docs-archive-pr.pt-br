---
title: 'Tutorial: cadeias de propriedade e alternância de contexto | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- context switching [SQL Server], tutorials
- ownership chains [SQL Server]
ms.assetid: db5d4cc3-5fc5-4cf5-afc1-8d4edc1d512b
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e9072a68dd3179e5900fda06d4fea58b484a37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571912"
---
# <a name="tutorial-ownership-chains-and-context-switching"></a><span data-ttu-id="e43bc-102">Tutorial: Ownership Chains and Context Switching</span><span class="sxs-lookup"><span data-stu-id="e43bc-102">Tutorial: Ownership Chains and Context Switching</span></span>
  <span data-ttu-id="e43bc-103">Este tutorial usa um cenário para ilustrar os conceitos de segurança do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] envolvendo cadeias de propriedade e alternância de contexto de usuário.</span><span class="sxs-lookup"><span data-stu-id="e43bc-103">This tutorial uses a scenario to illustrate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security concepts involving ownership chains and user context switching.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e43bc-104">Para executar o código nesse tutorial será necessário ter a segurança do Modo Misto configurada e o banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] instalado.</span><span class="sxs-lookup"><span data-stu-id="e43bc-104">To run the code in this tutorial you must have both Mixed Mode security configured and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database installed.</span></span> <span data-ttu-id="e43bc-105">Para obter mais informações sobre a segurança de Modo Misto, consulte [Escolher um modo de autenticação](security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e43bc-105">For more information about Mixed Mode security, see [Choose an Authentication Mode](security/choose-an-authentication-mode.md).</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="e43bc-106">Cenário</span><span class="sxs-lookup"><span data-stu-id="e43bc-106">Scenario</span></span>  
 <span data-ttu-id="e43bc-107">Neste cenário, dois usuários precisam de contas para acessar dados de ordem de compra armazenados no banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e43bc-107">In this scenario, two users need accounts to access purchase order data stored in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="e43bc-108">Os requisitos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="e43bc-108">The requirements are as follows:</span></span>  
  
-   <span data-ttu-id="e43bc-109">A primeira conta (TestManagerUser) deve estar habilitada para que você veja todos os detalhes em cada ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e43bc-109">The first account (TestManagerUser) must be able to see all details in every purchase order.</span></span>  
  
-   <span data-ttu-id="e43bc-110">A segunda conta (TestEmployeeUser) deve estar habilitada para ver o número da ordem de compra, a data do pedido, a data de envio, os números de ID do produto e os itens solicitados e recebidos por ordem de compra, por número de ordem de compra, para itens cujos envios parciais foram recebidos.</span><span class="sxs-lookup"><span data-stu-id="e43bc-110">The second account (TestEmployeeUser) must be able to see the purchase order number, order date, shipping date, product ID numbers, and the ordered and received items per purchase order, by purchase order number, for items where partial shipments have been received.</span></span>  
  
-   <span data-ttu-id="e43bc-111">Todas as outras contas devem reter suas permissões atuais.</span><span class="sxs-lookup"><span data-stu-id="e43bc-111">All other accounts must retain their current permissions.</span></span>  
  
 <span data-ttu-id="e43bc-112">Para atender aos requisitos deste cenário, o exemplo é dividido em quatro partes que demonstram os conceitos de cadeia de propriedade e alternância de contexto:</span><span class="sxs-lookup"><span data-stu-id="e43bc-112">To fulfill the requirements of this scenario, the example is broken into four parts that demonstrate the concepts of ownership chains and context switching:</span></span>  
  
1.  <span data-ttu-id="e43bc-113">Configurando o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e43bc-113">Configuring the environment.</span></span>  
  
2.  <span data-ttu-id="e43bc-114">Criando um procedimento armazenado para acessar dados por ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e43bc-114">Creating a stored procedure to access data by purchase order.</span></span>  
  
3.  <span data-ttu-id="e43bc-115">Acessando os dados pelo procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="e43bc-115">Accessing the data through the stored procedure.</span></span>  
  
4.  <span data-ttu-id="e43bc-116">Redefinindo o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e43bc-116">Resetting the environment.</span></span>  
  
 <span data-ttu-id="e43bc-117">Cada bloco de código neste exemplo é explicado em linha.</span><span class="sxs-lookup"><span data-stu-id="e43bc-117">Each code block in this example is explained in line.</span></span> <span data-ttu-id="e43bc-118">Para copiar o exemplo completo, consulte [Exemplo completo](#CompleteExample) no fim deste tutorial.</span><span class="sxs-lookup"><span data-stu-id="e43bc-118">To copy the complete example, see [Complete Example](#CompleteExample) at the end of this tutorial.</span></span>  
  
## <a name="1-configure-the-environment"></a><span data-ttu-id="e43bc-119">1. Configure o ambiente</span><span class="sxs-lookup"><span data-stu-id="e43bc-119">1. Configure the Environment</span></span>  
 <span data-ttu-id="e43bc-120">Use o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e o código a seguir para abrir o `AdventureWorks2012` banco de dados e use a `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] instrução para verificar se o usuário dbo é exibido como o contexto.</span><span class="sxs-lookup"><span data-stu-id="e43bc-120">Use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and the following code to open the `AdventureWorks2012` database, and use the `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] statement to check that the dbo user is displayed as the context.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
```  
  
 <span data-ttu-id="e43bc-121">Para obter mais informações sobre a instrução CURRENT_USER, consulte [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e43bc-121">For more information about the CURRENT_USER statement, see [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span></span>  
  
 <span data-ttu-id="e43bc-122">Use esse código como o usuário dbo para criar dois usuários no servidor e no banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e43bc-122">Use this code as the dbo user to create two users on the server and in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
GO  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
```  
  
 <span data-ttu-id="e43bc-123">Para obter mais informações sobre a instrução CREATE USER, consulte [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e43bc-123">For more information about the CREATE USER statement, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="e43bc-124">Para obter mais informações sobre a instrução CREATE LOGIN, consulte [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e43bc-124">For more information about the CREATE LOGIN statement, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
 <span data-ttu-id="e43bc-125">Use o código a seguir para alterar a propriedade do esquema `Purchasing` para a conta `TestManagerUser` .</span><span class="sxs-lookup"><span data-stu-id="e43bc-125">Use the following code to change the ownership of the `Purchasing` schema to the `TestManagerUser` account.</span></span> <span data-ttu-id="e43bc-126">Isso permite que a conta use todos os acessos da instrução DML (Linguagem de Manipulação de Dados) (como as permissões `SELECT` e `INSERT` ) nos objetos que ela contém.</span><span class="sxs-lookup"><span data-stu-id="e43bc-126">This allows that account to use all Data Manipulation Language (DML) statement access (such as `SELECT` and `INSERT` permissions) on the objects it contains.</span></span> <span data-ttu-id="e43bc-127">`TestManagerUser` também tem a capacidade de criar procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="e43bc-127">`TestManagerUser` is also granted the ability to create stored procedures.</span></span>  
  
```  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
```  
  
 <span data-ttu-id="e43bc-128">Para obter mais informações sobre a instrução GRANT, consulte [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e43bc-128">For more information about the GRANT statement, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="e43bc-129">Para obter mais informações sobre procedimentos armazenados, consulte [Procedimentos armazenados &#40;Mecanismo de Banco de Dados&#41;](stored-procedures/stored-procedures-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="e43bc-129">For more information about stored procedures, see [Stored Procedures &#40;Database Engine&#41;](stored-procedures/stored-procedures-database-engine.md).</span></span> <span data-ttu-id="e43bc-130">Para obter um pôster de todas as [!INCLUDE[ssDE](../includes/ssde-md.md)] permissões, consulte [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf) .</span><span class="sxs-lookup"><span data-stu-id="e43bc-130">For a poster of all [!INCLUDE[ssDE](../includes/ssde-md.md)] permissions, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>  
  
## <a name="2-create-a-stored-procedure-to-access-data"></a><span data-ttu-id="e43bc-131">2. Crie um procedimento armazenado para acessar os dados</span><span class="sxs-lookup"><span data-stu-id="e43bc-131">2. Create a Stored Procedure to Access Data</span></span>  
 <span data-ttu-id="e43bc-132">Para alternar o contexto dentro de um banco de dados, use a instrução EXECUTE AS.</span><span class="sxs-lookup"><span data-stu-id="e43bc-132">To switch context within a database, use the EXECUTE AS statement.</span></span> <span data-ttu-id="e43bc-133">EXECUTE AS exige permissões IMPERSONATE.</span><span class="sxs-lookup"><span data-stu-id="e43bc-133">EXECUTE AS requires IMPERSONATE permissions.</span></span>  
  
 <span data-ttu-id="e43bc-134">Use a instrução `EXECUTE AS` no código a seguir para alterar o contexto para `TestManagerUser` e criar um procedimento armazenado exibindo somente os dados requeridos por `TestEmployeeUser`.</span><span class="sxs-lookup"><span data-stu-id="e43bc-134">Use the `EXECUTE AS` statement in the following code to change the context to `TestManagerUser` and create a stored procedure showing only the data required by `TestEmployeeUser`.</span></span> <span data-ttu-id="e43bc-135">Para atender a esses requisitos, o procedimento armazenado aceita uma variável como número da ordem de compra e não exibe informações financeiras, e a cláusula WHERE limita os resultados a envios parciais.</span><span class="sxs-lookup"><span data-stu-id="e43bc-135">To satisfy the requirements, the stored procedure accepts one variable for the purchase order number and does not display financial information, and the WHERE clause limits the results to partial shipments.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestManagerUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader a  
      INNER JOIN Purchasing.PurchaseOrderDetail b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END  
GO  
```  
  
 <span data-ttu-id="e43bc-136">Atualmente `TestEmployeeUser` não tem acesso a qualquer objeto de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e43bc-136">Currently `TestEmployeeUser` does not have access to any database objects.</span></span> <span data-ttu-id="e43bc-137">O código a seguir (ainda no contexto `TestManagerUser` ) concede ao usuário da conta a capacidade de consultar informações na tabela base, pelo procedimento armazenado).</span><span class="sxs-lookup"><span data-stu-id="e43bc-137">The following code (still in the `TestManagerUser` context) grants the user account the ability to query base-table information through the stored procedure.</span></span>  
  
```  
GRANT EXECUTE  
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO  
```  
  
 <span data-ttu-id="e43bc-138">O procedimento armazenado faz parte do esquema `Purchasing` , embora nenhum esquema tenha sido explicitamente especificado devido ao `TestManagerUser` ser atribuído por padrão ao esquema `Purchasing` .</span><span class="sxs-lookup"><span data-stu-id="e43bc-138">The stored procedure is part of the `Purchasing` schema, even though no schema was explicitly specified, because `TestManagerUser` is assigned by default to the `Purchasing` schema.</span></span> <span data-ttu-id="e43bc-139">Você pode usar informações de catálogo de sistema para localizar objetos, como mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="e43bc-139">You can use system catalog information to locate objects, as shown in the following code.</span></span>  
  
```  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas a  
   INNER JOIN sys.objects b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
```  
  
 <span data-ttu-id="e43bc-140">Com essa seção de exemplo concluída, o código muda o contexto de volta ao dbo usando a instrução `REVERT`.</span><span class="sxs-lookup"><span data-stu-id="e43bc-140">With this section of the example completed, the code switches context back to dbo using the `REVERT` statement.</span></span>  
  
```  
REVERT;  
GO  
```  
  
 <span data-ttu-id="e43bc-141">Para obter mais informações sobre a instrução REVERT, consulte [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e43bc-141">For more information about the REVERT statement, see [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span></span>  
  
## <a name="3-access-data-through-the-stored-procedure"></a><span data-ttu-id="e43bc-142">3. Acesse dados pelo procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="e43bc-142">3. Access Data Through the Stored Procedure</span></span>  
 <span data-ttu-id="e43bc-143">`TestEmployeeUser` não tem permissões nos objetos de banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , a não ser um logon e os direitos atribuídos à função de banco de dados pública.</span><span class="sxs-lookup"><span data-stu-id="e43bc-143">`TestEmployeeUser` has no permissions on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database objects other than a login and the rights assigned to the public database role.</span></span> <span data-ttu-id="e43bc-144">O código a seguir retorna um erro quando `TestEmployeeUser` tentar acessar tabelas base.</span><span class="sxs-lookup"><span data-stu-id="e43bc-144">The following code returns an error when `TestEmployeeUser` attempts to access base tables.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestEmployeeUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* This won't work */  
SELECT *  
FROM Purchasing.PurchaseOrderHeader;  
GO  
SELECT *  
FROM Purchasing.PurchaseOrderDetail;  
GO  
```  
  
 <span data-ttu-id="e43bc-145">Como os objetos referenciados pelos procedimentos armazenados criados na última seção são de propriedade do `TestManagerUser` em virtude da propriedade de esquema `Purchasing` , `TestEmployeeUser` pode acessar as tabelas base pelo procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="e43bc-145">Because the objects referenced by the stored procedure created in the last section are owned by `TestManagerUser` by virtue of the `Purchasing` schema ownership, `TestEmployeeUser` can access the base tables through the stored procedure.</span></span> <span data-ttu-id="e43bc-146">O código a seguir, ainda usando o contexto `TestEmployeeUser` , passa a ordem de compra 952 como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e43bc-146">The following code, still using the `TestEmployeeUser` context, passes purchase order 952 as a parameter.</span></span>  
  
```  
EXEC Purchasing.usp_ShowWaitingItems 952  
GO  
```  
  
## <a name="4-reset-the-environment"></a><span data-ttu-id="e43bc-147">4. Redefina o ambiente</span><span class="sxs-lookup"><span data-stu-id="e43bc-147">4. Reset the Environment</span></span>  
 <span data-ttu-id="e43bc-148">O código a seguir usa o comando `REVERT` para retornar o contexto da conta atual ao `dbo`e, em seguida, redefine o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e43bc-148">The following code uses the `REVERT` command to return the context of the current account to `dbo`, and then resets the environment.</span></span>  
  
```  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
##  <a name="complete-example"></a><a name="CompleteExample"></a><span data-ttu-id="e43bc-149">Exemplo completo</span><span class="sxs-lookup"><span data-stu-id="e43bc-149">Complete Example</span></span>  
 <span data-ttu-id="e43bc-150">Esta seção exibe o código de exemplo completo.</span><span class="sxs-lookup"><span data-stu-id="e43bc-150">This section displays the complete example code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e43bc-151">Este código não inclui os dois erros previstos que demonstram a incapacidade de o `TestEmployeeUser` fazer a seleção a partir de tabelas base.</span><span class="sxs-lookup"><span data-stu-id="e43bc-151">This code does not include the two expected errors that demonstrate the inability of `TestEmployeeUser` to select from base tables.</span></span>  
  
```  
/*   
Script:       UserContextTutorial.sql  
Author:       Microsoft  
Last Updated: Books Online  
Conditions:   Execute as DBO or sysadmin in the AdventureWorks database  
Section 1:    Configure the Environment   
*/  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* Create server and database users */  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
  
GO  
  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
  
/*   
Section 2: Switch Context and Create Objects  
*/  
EXECUTE AS LOGIN = 'TestManagerUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader AS a  
      INNER JOIN Purchasing.PurchaseOrderDetail AS b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END;  
GO  
  
/* Give the employee the ability to run the procedure */  
GRANT EXECUTE   
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO   
  
/* Notice that the stored procedure is located in the Purchasing   
schema. This also demonstrates system catalogs */  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas AS a  
   INNER JOIN sys.objects AS b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
  
/* Go back to being the dbo user */  
REVERT;  
GO  
  
/*  
Section 3: Switch Context and Observe Security   
*/  
EXECUTE AS LOGIN = 'TestEmployeeUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
EXEC Purchasing.usp_ShowWaitingItems 952;  
GO  
  
/*   
Section 4: Clean Up Example  
*/  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e43bc-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e43bc-152">See Also</span></span>  
 [<span data-ttu-id="e43bc-153">Central de segurança do Mecanismo de Banco de Dados do SQL Server e Banco de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="e43bc-153">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
