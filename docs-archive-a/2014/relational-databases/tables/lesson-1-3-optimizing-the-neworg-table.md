---
title: Otimizando a tabela NewOrg | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- optimizing tables
ms.assetid: 89ff6d37-94c0-4773-8be9-dde943fff023
author: stevestein
ms.author: sstein
ms.openlocfilehash: 39c09a3a73051e7a61f3a62a125232d83d1570c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568399"
---
# <a name="optimizing-the-neworg-table"></a><span data-ttu-id="3272c-102">Otimizando a tabela NewOrg</span><span class="sxs-lookup"><span data-stu-id="3272c-102">Optimizing the NewOrg Table</span></span>
  <span data-ttu-id="3272c-103">A tabela **NewOrd** que você criou na tarefa [populando uma tabela com dados hierárquicos existentes](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) contém todas as informações do funcionário e representa a estrutura hierárquica usando um `hierarchyid` tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="3272c-103">The **NewOrd** table that you created in the [Populating a Table with Existing Hierarchical Data](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) task contains all the employee information, and represents the hierarchical structure by using a `hierarchyid` data type.</span></span> <span data-ttu-id="3272c-104">Essa tarefa adiciona índices novos para oferecer suporte às pesquisas na coluna `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="3272c-104">This task adds new indexes to support searches on the `hierarchyid` column.</span></span>  
  
## <a name="clustered-index"></a><span data-ttu-id="3272c-105">Índice clusterizado</span><span class="sxs-lookup"><span data-stu-id="3272c-105">Clustered Index</span></span>  
 <span data-ttu-id="3272c-106">A `hierarchyid` coluna (**OrgNode**) é a chave primária para a tabela **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="3272c-106">The `hierarchyid` column (**OrgNode**) is the primary key for the **NewOrg** table.</span></span> <span data-ttu-id="3272c-107">Quando a tabela foi criada, ela continha um índice clusterizado chamado **PK_NewOrg_OrgNode** para impor a exclusividade da coluna **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="3272c-107">When the table was created, it contained a clustered index named **PK_NewOrg_OrgNode** to enforce the uniqueness of the **OrgNode** column.</span></span> <span data-ttu-id="3272c-108">Esse índice clusterizado também oferece suporte a uma pesquisa primária detalhada da tabela.</span><span class="sxs-lookup"><span data-stu-id="3272c-108">This clustered index also supports a depth-first search of the table.</span></span>  
  
## <a name="nonclustered-index"></a><span data-ttu-id="3272c-109">Índice não clusterizado</span><span class="sxs-lookup"><span data-stu-id="3272c-109">Nonclustered Index</span></span>  
 <span data-ttu-id="3272c-110">Este passo cria dois índices não clusterizados para oferecer suporte a pesquisas típicas.</span><span class="sxs-lookup"><span data-stu-id="3272c-110">This step creates two nonclustered indexes to support typical searches.</span></span>  
  
#### <a name="to-index-the-neworg-table-for-efficient-searches"></a><span data-ttu-id="3272c-111">Para indexar a tabela NewOrg para pesquisas eficientes</span><span class="sxs-lookup"><span data-stu-id="3272c-111">To index the NewOrg table for efficient searches</span></span>  
  
1.  <span data-ttu-id="3272c-112">Para ajudar as consultas no mesmo nível na hierarquia, use o método [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) para criar uma coluna calculada que contém o nível na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="3272c-112">To help queries at the same level in the hierarchy, use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to create a computed column that contains the level in the hierarchy.</span></span> <span data-ttu-id="3272c-113">Então, crie um índice composto no nível e a `Hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="3272c-113">Then, create a composite index on the level and the `Hierarchyid`.</span></span> <span data-ttu-id="3272c-114">Execute o código a seguir para criar a coluna computada e o índice de amplitude primária:</span><span class="sxs-lookup"><span data-stu-id="3272c-114">Run the following code to create the computed column and the breadth-first index:</span></span>  
  
    ```  
    ALTER TABLE NewOrg   
       ADD H_Level AS OrgNode.GetLevel() ;  
    CREATE UNIQUE INDEX EmpBFInd   
       ON NewOrg(H_Level, OrgNode) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="3272c-115">Crie um índice exclusivo na coluna **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="3272c-115">Create a unique index on the **EmployeeID** column.</span></span> <span data-ttu-id="3272c-116">Esta é uma pesquisa singleton tradicional de um único funcionário pelo número **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="3272c-116">This is the traditional singleton lookup of a single employee by **EmployeeID** number.</span></span> <span data-ttu-id="3272c-117">Execute o seguinte código para criar um índice em **EmployeeID**:</span><span class="sxs-lookup"><span data-stu-id="3272c-117">Run the following code to create an index on **EmployeeID**:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmpIDs_unq ON NewOrg(EmployeeID) ;  
    GO  
    ```  
  
3.  <span data-ttu-id="3272c-118">Execute o código a seguir para recuperar dados da tabela na ordem de cada um dos três índices:</span><span class="sxs-lookup"><span data-stu-id="3272c-118">Run the following code to retrieve data from the table in the order of each of the three indexes:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID  
    FROM NewOrg   
    ORDER BY OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY H_Level, OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY EmployeeID;  
    GO  
    ```  
  
4.  <span data-ttu-id="3272c-119">Compare os conjuntos de resultados para ver como a ordem está armazenada em cada tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="3272c-119">Compare the result sets to see how the order is stored in each type of index.</span></span> <span data-ttu-id="3272c-120">Seguem apenas as primeiras quatro linhas de cada saída.</span><span class="sxs-lookup"><span data-stu-id="3272c-120">Only the first four rows of each output follow.</span></span>  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     <span data-ttu-id="3272c-121">Índice de profundidade primária: os registros de funcionário são armazenados adjacentes aos de seu gerente.</span><span class="sxs-lookup"><span data-stu-id="3272c-121">Depth-first index: Employee records are stored adjacent to their manager.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     <span data-ttu-id="3272c-122">Índice de**EmployeeID**primário: as linhas são armazenadas na sequência de **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="3272c-122">**EmployeeID**-first index: Rows are stored in **EmployeeID** sequence.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
> [!NOTE]  
>  <span data-ttu-id="3272c-123">Para diagramas que mostram a diferença entre um índice de profundidade primária e um índice de amplitude primária, consulte [Dados hierárquicos &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3272c-123">For diagrams that show the difference between a depth-first index and a breadth-first index, see [Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span></span>  
  
#### <a name="to-drop-the-unnecessary-columns"></a><span data-ttu-id="3272c-124">Para cancelar as colunas desnecessárias</span><span class="sxs-lookup"><span data-stu-id="3272c-124">To drop the unnecessary columns</span></span>  
  
1.  <span data-ttu-id="3272c-125">A coluna **ManagerID** representa a relação funcionário/gerente, que é representada agora pela coluna **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="3272c-125">The **ManagerID** column represents the employee/manager relationship, which is now represented by the **OrgNode** column.</span></span> <span data-ttu-id="3272c-126">Se outros aplicativos não precisarem da coluna **ManagerID** , considere removê-la usando a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="3272c-126">If other applications do not need the **ManagerID** column, consider dropping it by using the following statement:</span></span>  
  
    ```  
    ALTER TABLE NewOrg DROP COLUMN ManagerID ;  
    GO  
    ```  
  
2.  <span data-ttu-id="3272c-127">A coluna **EmployeeID** também é redundante.</span><span class="sxs-lookup"><span data-stu-id="3272c-127">The **EmployeeID** column is also redundant.</span></span> <span data-ttu-id="3272c-128">A coluna **OrgNode** identifica cada empregado de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="3272c-128">The **OrgNode** column uniquely identifies each employee.</span></span> <span data-ttu-id="3272c-129">Se os outros aplicativos não precisarem da coluna **EmployeeID** , considere remover o índice e depois a coluna usando o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="3272c-129">If other applications do not need the **EmployeeID** column, consider dropping the index and then the column by using the following code:</span></span>  
  
    ```  
    DROP INDEX EmpIDs_unq ON NewOrg ;  
    ALTER TABLE NewOrg DROP COLUMN EmployeeID ;  
    GO  
    ```  
  
#### <a name="to-replace-the-original-table-with-the-new-table"></a><span data-ttu-id="3272c-130">Para substituir a tabela original pela tabela nova</span><span class="sxs-lookup"><span data-stu-id="3272c-130">To replace the original table with the new table</span></span>  
  
1.  <span data-ttu-id="3272c-131">Se sua tabela original continha outros índices ou restrições, adicione-os à tabela **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="3272c-131">If your original table contained any additional indexes or constraints, add them to the **NewOrg** table.</span></span>  
  
2.  <span data-ttu-id="3272c-132">Substitua a tabela antiga **EmployeeDemo** pela nova tabela.</span><span class="sxs-lookup"><span data-stu-id="3272c-132">Replace the old **EmployeeDemo** table with the new table.</span></span> <span data-ttu-id="3272c-133">Execute o código a seguir para cancelar a tabela antiga e então renomeie a tabela nova com o nome antigo:</span><span class="sxs-lookup"><span data-stu-id="3272c-133">Run the following code to drop the old table, and then rename the new table with the old name:</span></span>  
  
    ```  
    DROP TABLE EmployeeDemo ;  
    GO  
    sp_rename 'NewOrg', EmployeeDemo ;  
    GO  
    ```  
  
3.  <span data-ttu-id="3272c-134">Execute o código a seguir para examinar a tabela final:</span><span class="sxs-lookup"><span data-stu-id="3272c-134">Run the following code to examine the final table:</span></span>  
  
    ```  
    SELECT * FROM EmployeeDemo ;  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3272c-135">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="3272c-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3272c-136">Resumo: conversão de uma tabela em uma estrutura hierárquica</span><span class="sxs-lookup"><span data-stu-id="3272c-136">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
  
