---
title: Populando uma tabela com os dados hierárquicos existentes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: fd943d84-dbe6-4a05-912b-c88164998d80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 966548b11ad4697abc06de5c5c239a511f80b7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679288"
---
# <a name="populating-a-table-with-existing-hierarchical-data"></a><span data-ttu-id="ade72-102">Populando uma tabela com dados hierárquicos existentes</span><span class="sxs-lookup"><span data-stu-id="ade72-102">Populating a Table with Existing Hierarchical Data</span></span>
  <span data-ttu-id="ade72-103"> Essa tarefa cria uma tabela nova e a popula com os dados da tabela **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="ade72-103">This task creates a new table and populates it with the data in the **EmployeeDemo** table.</span></span> <span data-ttu-id="ade72-104">Essa tarefa tem as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ade72-104">This task has the following steps:</span></span>  
  
-   <span data-ttu-id="ade72-105">Crie uma tabela que contenha uma coluna `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="ade72-105">Create a new table that contains a `hierarchyid` column.</span></span> <span data-ttu-id="ade72-106">Essa coluna pode substituir as colunas **EmployeeID** e **ManagerID** existentes.</span><span class="sxs-lookup"><span data-stu-id="ade72-106">This column could replace the existing **EmployeeID** and **ManagerID** columns.</span></span> <span data-ttu-id="ade72-107">Entretanto, você manterá essas colunas.</span><span class="sxs-lookup"><span data-stu-id="ade72-107">However, you will retain those columns.</span></span> <span data-ttu-id="ade72-108">Isso porque os aplicativos existentes podem se referir a essas colunas e, também, para ajudar a compreender os dados depois da transferência.</span><span class="sxs-lookup"><span data-stu-id="ade72-108">This is because existing applications might refer to those columns, and also to help you understand the data after the transfer.</span></span> <span data-ttu-id="ade72-109">A definição da tabela especifica que **OrgNode** é a chave primária, exigindo que a coluna contenha valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ade72-109">The table definition specifies that **OrgNode** is the primary key, which requires the column to contain unique values.</span></span> <span data-ttu-id="ade72-110">O índice clusterizado da coluna **OrgNode** armazenará a data na sequência **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="ade72-110">The clustered index on the **OrgNode** column will store the date in **OrgNode** sequence.</span></span>  
  
-   <span data-ttu-id="ade72-111">Crie uma tabela temporária que será usada para localizar quantos funcionários se reportam diretamente a cada gerenciador.</span><span class="sxs-lookup"><span data-stu-id="ade72-111">Create a temporary table that is used to track how many employees report directly to each manager.</span></span>  
  
-   <span data-ttu-id="ade72-112">Popule a nova tabela usando dados da tabela **EmployeeDemo** .</span><span class="sxs-lookup"><span data-stu-id="ade72-112">Populate the new table by using data from the **EmployeeDemo** table.</span></span>  
  
### <a name="to-create-a-new-table-named-neworg"></a><span data-ttu-id="ade72-113">Para criar uma tabela chamada NewOrg</span><span class="sxs-lookup"><span data-stu-id="ade72-113">To create a new table named NewOrg</span></span>  
  
-   <span data-ttu-id="ade72-114">Em uma janela do Editor de Consultas, execute o seguinte código para criar uma tabela chamada **HumanResources.NewOrg**:</span><span class="sxs-lookup"><span data-stu-id="ade72-114">In a Query Editor window, run the following code to create a new table named **HumanResources.NewOrg**:</span></span>  
  
    ```  
    CREATE TABLE NewOrg  
    (  
      OrgNode hierarchyid,  
      EmployeeID int,  
      LoginID nvarchar(50),  
      ManagerID int  
    CONSTRAINT PK_NewOrg_OrgNode  
      PRIMARY KEY CLUSTERED (OrgNode)  
    );  
    GO  
    ```  
  
### <a name="to-create-a-temporary-table-named-children"></a><span data-ttu-id="ade72-115">Para criar uma tabela temporária chamada #Children</span><span class="sxs-lookup"><span data-stu-id="ade72-115">To create a temporary table named #Children</span></span>  
  
1.  <span data-ttu-id="ade72-116">Crie uma tabela temporária chamada **#Children** com uma coluna chamada **Num** que conterá o número de filhos de cada nó:</span><span class="sxs-lookup"><span data-stu-id="ade72-116">Create a temporary table named **#Children** with a column named **Num** that will contain the number of children for each node:</span></span>  
  
    ```  
    CREATE TABLE #Children   
       (  
        EmployeeID int,  
        ManagerID int,  
        Num int  
    );  
    GO  
    ```  
  
2.  <span data-ttu-id="ade72-117">Adicione um índice que acelerará consideravelmente a consulta que popula a tabela **NewOrg** :</span><span class="sxs-lookup"><span data-stu-id="ade72-117">Add an index that will significantly speed up the query that populates the **NewOrg** table:</span></span>  
  
    ```  
    CREATE CLUSTERED INDEX tmpind ON #Children(ManagerID, EmployeeID);  
    GO  
    ```  
  
### <a name="to-populate-the-neworg-table"></a><span data-ttu-id="ade72-118">Para popular a tabela NewOrg</span><span class="sxs-lookup"><span data-stu-id="ade72-118">To populate the NewOrg table</span></span>  
  
1.  <span data-ttu-id="ade72-119">Consultas recursivas proíbem subconsultas com agregações.</span><span class="sxs-lookup"><span data-stu-id="ade72-119">Recursive queries forbid subqueries with aggregates.</span></span> <span data-ttu-id="ade72-120">Em vez disso, popule a tabela **#Children** com o seguinte código, que usa o método [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) para popular a coluna **Num** :</span><span class="sxs-lookup"><span data-stu-id="ade72-120">Instead, populate the **#Children** table with the following code, which uses the [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) method to populate the **Num** column:</span></span>  
  
    ```  
    INSERT #Children (EmployeeID, ManagerID, Num)  
    SELECT EmployeeID, ManagerID,  
      ROW_NUMBER() OVER (PARTITION BY ManagerID ORDER BY ManagerID)   
    FROM EmployeeDemo  
    GO  
  
    ```  
  
2.  <span data-ttu-id="ade72-121">Examine a tabela **#Children** .</span><span class="sxs-lookup"><span data-stu-id="ade72-121">Review the **#Children** table.</span></span> <span data-ttu-id="ade72-122">Observe como a coluna **Num** contém números sequenciais para cada gerenciador.</span><span class="sxs-lookup"><span data-stu-id="ade72-122">Note how the **Num** column contains sequential numbers for each manager.</span></span>  
  
    ```  
    SELECT * FROM #Children ORDER BY ManagerID, Num  
    GO  
  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     `EmployeeID ManagerID Num`  
  
     `---------- --------- ---`  
  
     `1        NULL       1`  
  
     `2         1         1`  
  
     `3         1         2`  
  
     `4         2         1`  
  
     `5         2         2`  
  
     `6         2         3`  
  
     `7         3         1`  
  
     `8         3         2`  
  
     `9         4         1`  
  
     `10        4         2`  
  
3.  <span data-ttu-id="ade72-123">Preencha a tabela **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="ade72-123">Populate the **NewOrg** table.</span></span> <span data-ttu-id="ade72-124">Use os métodos GetRoot e ToString para concatenar os valores **num** no `hierarchyid` formato e, em seguida, atualize a coluna **OrgNode** com os valores hierárquicos resultantes:</span><span class="sxs-lookup"><span data-stu-id="ade72-124">Use the GetRoot and ToString methods to concatenate the **Num** values into the `hierarchyid` format, and then update the **OrgNode** column with the resultant hierarchical values:</span></span>  
  
    ```  
    WITH paths(path, EmployeeID)   
    AS (  
    -- This section provides the value for the root of the hierarchy  
    SELECT hierarchyid::GetRoot() AS OrgNode, EmployeeID   
    FROM #Children AS C   
    WHERE ManagerID IS NULL   
  
    UNION ALL   
    -- This section provides values for all nodes except the root  
    SELECT   
    CAST(p.path.ToString() + CAST(C.Num AS varchar(30)) + '/' AS hierarchyid),   
    C.EmployeeID  
    FROM #Children AS C   
    JOIN paths AS p   
       ON C.ManagerID = P.EmployeeID   
    )  
    INSERT NewOrg (OrgNode, O.EmployeeID, O.LoginID, O.ManagerID)  
    SELECT P.path, O.EmployeeID, O.LoginID, O.ManagerID  
    FROM EmployeeDemo AS O   
    JOIN Paths AS P   
       ON O.EmployeeID = P.EmployeeID  
    GO  
  
    ```  
  
4.  <span data-ttu-id="ade72-125">Uma coluna `hierarchyid` é mais compreensível quando você a converte no formato de caractere.</span><span class="sxs-lookup"><span data-stu-id="ade72-125">A `hierarchyid` column is more understandable when you convert it to character format.</span></span> <span data-ttu-id="ade72-126">Examine os dados da tabela **NewOrg** executando o seguinte código, que contém duas representações da coluna **OrgNode** :</span><span class="sxs-lookup"><span data-stu-id="ade72-126">Review the data in the **NewOrg** table by executing the following code, which contains two representations of the **OrgNode** column:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode, *   
    FROM NewOrg   
    ORDER BY LogicalNode;  
    GO  
  
    ```  
  
     <span data-ttu-id="ade72-127">A coluna **LogicalNode** converte a `hierarchyid` coluna em um formulário de texto mais legível que representa a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="ade72-127">The **LogicalNode** column converts the `hierarchyid` column into a more readable text form that represents the hierarchy.</span></span> <span data-ttu-id="ade72-128">Nas tarefas restantes, você usará o método `ToString()` para mostrar o formato lógico das colunas `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="ade72-128">In the remaining tasks, you will use the `ToString()` method to show the logical format of the `hierarchyid` columns.</span></span>  
  
5.  <span data-ttu-id="ade72-129">Descarte a tabela temporária, que não será mais necessária:</span><span class="sxs-lookup"><span data-stu-id="ade72-129">Drop the temporary table, which is no longer needed:</span></span>  
  
    ```  
    DROP TABLE #Children  
    GO  
    ```  
  
 <span data-ttu-id="ade72-130">A próxima tarefa criará índices para oferecer suporte à estrutura hierárquica.</span><span class="sxs-lookup"><span data-stu-id="ade72-130">The next task will create indexes to support the hierarchical structure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ade72-131">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="ade72-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ade72-132">Otimizando a tabela NewOrg</span><span class="sxs-lookup"><span data-stu-id="ade72-132">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
  
