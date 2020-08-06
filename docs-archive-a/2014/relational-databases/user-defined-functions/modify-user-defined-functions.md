---
title: Modificar funções definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 891c37b3-cb72-411f-9937-ee87e6d95f34
author: rothja
ms.author: jroth
ms.openlocfilehash: 1cf25fef91834e237f5cbaac26350220840830bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582845"
---
# <a name="modify-user-defined-functions"></a><span data-ttu-id="454fe-102">Modificar funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="454fe-102">Modify User-defined Functions</span></span>
  <span data-ttu-id="454fe-103">Você pode modificar funções definidas pelo usuário no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="454fe-103">You can modify user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="454fe-104">A modificação das funções definidas pelo usuário, como descrito abaixo, não alterará as permissões das funções, nem afetará as funções dependentes, os procedimentos armazenados ou os gatilhos.</span><span class="sxs-lookup"><span data-stu-id="454fe-104">Modifying user-defined functions as described below will not change the functions' permissions, nor will it affect any dependent functions, stored procedures, or triggers.</span></span>  
  
 <span data-ttu-id="454fe-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="454fe-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="454fe-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="454fe-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="454fe-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="454fe-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="454fe-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="454fe-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="454fe-109">**Para modificar uma função definida pelo usuário, usando:**</span><span class="sxs-lookup"><span data-stu-id="454fe-109">**To modify a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="454fe-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="454fe-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="454fe-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="454fe-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="454fe-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="454fe-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="454fe-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="454fe-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="454fe-114">ALTER FUNCTION não pode ser usado para executar nenhuma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="454fe-114">ALTER FUNCTION cannot be used to perform any of the following actions:</span></span>  
  
-   <span data-ttu-id="454fe-115">Alterar uma função de valor escalar para uma função com valor de tabela ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="454fe-115">Change a scalar-valued function to a table-valued function, or vice versa.</span></span>  
  
-   <span data-ttu-id="454fe-116">Alterar uma função embutida para uma função com várias instruções, ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="454fe-116">Change an inline function to a multistatement function, or vice versa.</span></span>  
  
-   <span data-ttu-id="454fe-117">Alterar uma função de Transact-SQL para uma função CLR função, ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="454fe-117">Change a Transact-SQL function to a CLR function, or vice-versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="454fe-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="454fe-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="454fe-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="454fe-119">Permissions</span></span>  
 <span data-ttu-id="454fe-120">Requer permissão ALTER na função ou no esquema.</span><span class="sxs-lookup"><span data-stu-id="454fe-120">Requires ALTER permission on the function or on the schema.</span></span> <span data-ttu-id="454fe-121">Se a função especificar um tipo definido pelo usuário, a permissão EXECUTE será exigida no tipo.</span><span class="sxs-lookup"><span data-stu-id="454fe-121">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="454fe-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="454fe-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="454fe-123">Para modificar uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="454fe-123">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="454fe-124">Clique no sinal de mais ao lado do banco de dados que contém a função que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="454fe-124">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="454fe-125">Clique no sinal de mais ao lado da pasta **Programação** .</span><span class="sxs-lookup"><span data-stu-id="454fe-125">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="454fe-126">Clique no sinal de mais ao lado da pasta que contém a função que você deseja modificar:</span><span class="sxs-lookup"><span data-stu-id="454fe-126">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="454fe-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="454fe-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="454fe-128">Função de valor escalar</span><span class="sxs-lookup"><span data-stu-id="454fe-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="454fe-129">Função de agregação</span><span class="sxs-lookup"><span data-stu-id="454fe-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="454fe-130">Clique com o botão direito do mouse na função a ser modificada e selecione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="454fe-130">Right-click the function you want to modify and select **Modify**.</span></span>  
  
5.  <span data-ttu-id="454fe-131">Na Janela de Consulta, faça as alterações necessárias à instrução ALTER FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="454fe-131">In the Query Window, make the necessary changes to the ALTER FUNCTION statement.</span></span>  
  
6.  <span data-ttu-id="454fe-132">No menu **Arquivo** , clique em **Salvar**_function_name_.</span><span class="sxs-lookup"><span data-stu-id="454fe-132">On the **File** menu, click **Save**_function_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="454fe-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="454fe-133">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="454fe-134">Para modificar uma função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="454fe-134">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="454fe-135">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="454fe-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="454fe-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="454fe-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="454fe-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="454fe-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Scalar-Valued Function  
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetAccountingEndDate]()  
    RETURNS [datetime]   
    AS   
    BEGIN  
        RETURN DATEADD(millisecond, -2, CONVERT(datetime, '20040701', 112));  
    END;  
    ```  
  
    ```  
    -- Table-Valued Function   
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetContactInformation](@PersonID int)  
    RETURNS @retContactInformation TABLE   
    (  
        -- Columns returned by the function  
        [PersonID] int NOT NULL,   
        [FirstName] [nvarchar](50) NULL,   
        [LastName] [nvarchar](50) NULL,   
        [JobTitle] [nvarchar](50) NULL,  
        [BusinessEntityType] [nvarchar](50) NULL  
    )  
    AS   
    -- Returns the first name, last name, job title and business entity type for the specified contact.  
    -- Since a contact can serve multiple roles, more than one row may be returned.  
    BEGIN  
    IF @PersonID IS NOT NULL   
    BEGIN  
         IF EXISTS(SELECT * FROM [HumanResources].[Employee] e   
         WHERE e.[BusinessEntityID] = @PersonID)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, e.[JobTitle], 'Employee'  
              FROM [HumanResources].[Employee] AS e  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = e.[BusinessEntityID]  
              WHERE e.[BusinessEntityID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Purchasing].[Vendor] AS v  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Vendor Contact'   
              FROM [Purchasing].[Vendor] AS v  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Sales].[Store] AS s  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Store Contact'   
              FROM [Sales].[Store] AS s  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Person].[Person] AS p  
         INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
         WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, NULL, 'Consumer'   
              FROM [Person].[Person] AS p  
              INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
              WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL;   
         END  
    RETURN;  
    END;  
    ```  
  
 <span data-ttu-id="454fe-138">Para obter mais informações, veja [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="454fe-138">For more information, see [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span></span>  
  
  
