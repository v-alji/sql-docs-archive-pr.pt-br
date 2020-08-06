---
title: MSSQLSERVER_4186 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4186 (Database Engine error)
ms.assetid: 1ae88554-f291-45bc-a186-6f41d9cd0fca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 525c1c3bd6e631044b8bc7f17b2c2a01aeb1ef8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569526"
---
# <a name="mssqlserver_4186"></a><span data-ttu-id="5040a-102">MSSQLSERVER_4186</span><span class="sxs-lookup"><span data-stu-id="5040a-102">MSSQLSERVER_4186</span></span>
    
## <a name="details"></a><span data-ttu-id="5040a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5040a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5040a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="5040a-104">Product Name</span></span>|<span data-ttu-id="5040a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5040a-105">SQL Server</span></span>|  
|<span data-ttu-id="5040a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="5040a-106">Event ID</span></span>|<span data-ttu-id="5040a-107">4186</span><span class="sxs-lookup"><span data-stu-id="5040a-107">4186</span></span>|  
|<span data-ttu-id="5040a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="5040a-108">Event Source</span></span>|<span data-ttu-id="5040a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5040a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5040a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5040a-110">Component</span></span>|<span data-ttu-id="5040a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5040a-111">SQLEngine</span></span>|  
|<span data-ttu-id="5040a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="5040a-112">Symbolic Name</span></span>||  
|<span data-ttu-id="5040a-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="5040a-113">Message Text</span></span>|<span data-ttu-id="5040a-114">A coluna '%ls.%.\*ls' não pode ser referenciada na cláusula OUTPUT porque a definição da coluna contém uma subconsulta ou faz referência a uma função que executa acesso a dados de sistema ou de usuário.</span><span class="sxs-lookup"><span data-stu-id="5040a-114">Column '%ls.%.\*ls' cannot be referenced in the OUTPUT clause because the column definition contains a subquery or references a function that performs user or system data access.</span></span> <span data-ttu-id="5040a-115">Por padrão, se uma função não estabelece associação com o esquema, supõe-se que ela execute acesso a dados.</span><span class="sxs-lookup"><span data-stu-id="5040a-115">A function is assumed by default to perform data access if it is not schemabound.</span></span> <span data-ttu-id="5040a-116">Considere remover a subconsulta ou a função da definição de coluna ou remover a coluna da cláusula OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="5040a-116">Consider removing the subquery or function from the column definition or removing the column from the OUTPUT clause.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5040a-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="5040a-117">Explanation</span></span>  
 <span data-ttu-id="5040a-118">Para evitar comportamento não determinístico, a cláusula OUTPUT não pode fazer referência a uma coluna de uma exibição ou função com valor de tabela embutida quando essa coluna é definida por um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="5040a-118">To prevent nondeterministic behavior, the OUTPUT clause cannot reference a column from a view or inline table-valued function when that column is defined by one of the following methods:</span></span>  
  
-   <span data-ttu-id="5040a-119">Uma subconsulta.</span><span class="sxs-lookup"><span data-stu-id="5040a-119">A subquery.</span></span>  
  
-   <span data-ttu-id="5040a-120">Uma função definida pelo usuário que executa acesso a dados de usuário ou de sistema ou que supostamente executa tal acesso.</span><span class="sxs-lookup"><span data-stu-id="5040a-120">A user-defined function that performs user or system data access, or is assumed to perform such access.</span></span>  
  
-   <span data-ttu-id="5040a-121">Uma coluna computada que contém uma função definida pelo usuário e que executa acesso a dados de usuário ou de sistema em sua definição.</span><span class="sxs-lookup"><span data-stu-id="5040a-121">A computed column that contains a user-defined function that performs user or system data access in its definition.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="5040a-122">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5040a-122">Examples</span></span>  
 <span data-ttu-id="5040a-123">**Coluna de exibição definida por uma subconsulta**</span><span class="sxs-lookup"><span data-stu-id="5040a-123">**View Column Defined by a Subquery**</span></span>  
  
 <span data-ttu-id="5040a-124">O exemplo a seguir cria uma exibição que usa uma subconsulta da lista de seleção para definir a coluna `State`.</span><span class="sxs-lookup"><span data-stu-id="5040a-124">The following example creates a view that uses a subquery in the select list to define the column `State`.</span></span> <span data-ttu-id="5040a-125">Uma instrução UPDATE referencia a coluna `State` na cláusula OUTPUT e falha devido à subconsulta na lista de seleção.</span><span class="sxs-lookup"><span data-stu-id="5040a-125">An UPDATE statement then references the `State` column in the OUTPUT clause and fails because ob the subquery in the select list.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW dbo.V1  
AS  
    SELECT City,  
-- subquery to return the State name  
           (SELECT Name FROM Person.StateProvince AS sp   
            WHERE sp.StateProvinceID = a.StateProvinceID) AS State  
    FROM Person.Address AS a;  
GO  
--Reference the State column in the OUTPUT clause of an UPDATE statement  
UPDATE dbo.V1   
SET City = City + 'Test'   
OUTPUT deleted.City, deleted.State, inserted.City, inserted.State  
WHERE State = 'Texas';  
GO  
```  
  
 <span data-ttu-id="5040a-126">**Coluna de exibição definida por uma função**</span><span class="sxs-lookup"><span data-stu-id="5040a-126">**View Column Defined by a Function**</span></span>  
  
 <span data-ttu-id="5040a-127">O exemplo a seguir cria uma exibição que usa a função escalar de acesso a dados `dbo.ufnGetStock` na lista de seleção para definir a coluna `CurrentInventory`.</span><span class="sxs-lookup"><span data-stu-id="5040a-127">The following example creates a view that uses the data accessing, scalar function `dbo.ufnGetStock` in the select list to define the column `CurrentInventory`.</span></span> <span data-ttu-id="5040a-128">Em seguida, uma instrução UPDATE referencia a coluna `CurrentInventory` na cláusula OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="5040a-128">An UPDATE statement then references the `CurrentInventory` column in the OUTPUT clause .</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW Production.ReorderLevels  
AS  
    SELECT ProductID, ProductModelID, ReorderPoint,  
           dbo.ufnGetStock(ProductID) AS CurrentInventory  
    FROM Production.Product;  
GO  
  
UPDATE Production.ReorderLevels  
SET ReorderPoint += CurrentInventory  
OUTPUT deleted.ReorderPoint, deleted.CurrentInventory,  
       inserted.ReorderPoint, inserted.CurrentInventory  
WHERE ProductModelID BETWEEN 75 and 80;  
```  
  
## <a name="user-action"></a><span data-ttu-id="5040a-129">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5040a-129">User Action</span></span>  
 <span data-ttu-id="5040a-130">O erro 4186 pode ser corrigido de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="5040a-130">Error 4186 can be corrected in one of the following ways:</span></span>  
  
-   <span data-ttu-id="5040a-131">Use junções em vez de subconsultas para definir a coluna na exibição ou função.</span><span class="sxs-lookup"><span data-stu-id="5040a-131">Use joins instead of subqueries to define the column in the view or function.</span></span> <span data-ttu-id="5040a-132">Por exemplo, você pode reescrever a exibição `dbo.V1` da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="5040a-132">For example, you can rewrite the view `dbo.V1` as follows.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE VIEW dbo.V1  
    AS  
        SELECT City, sp.Name AS State  
        FROM Person.Address AS a   
        JOIN Person.StateProvince AS sp   
        ON sp.StateProvinceID = a.StateProvinceID;  
    ```  
  
-   <span data-ttu-id="5040a-133">Examine a definição da outra função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="5040a-133">Examine the definition of the user-defined function.</span></span> <span data-ttu-id="5040a-134">Se a função não executar acesso a dados de usuário ou de sistema, altere-a para incluir a cláusula WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="5040a-134">If the function does not perform user or system data access, alter the function to include the WITH SCHEMABINDING clause.</span></span>  
  
-   <span data-ttu-id="5040a-135">Remova a coluna de cláusula OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="5040a-135">Remove the column from the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5040a-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5040a-136">See Also</span></span>  
 [<span data-ttu-id="5040a-137">Cláusula OUTPUT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5040a-137">OUTPUT Clause &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/output-clause-transact-sql)  
  
  
