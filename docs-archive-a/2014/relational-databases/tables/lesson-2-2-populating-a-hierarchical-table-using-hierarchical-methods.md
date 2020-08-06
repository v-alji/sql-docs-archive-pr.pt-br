---
title: Populando uma tabela hierárquica usando métodos hierárquicos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- HierarchyID
helpviewer_keywords:
- HierarchyID
ms.assetid: 2c95fa60-5b8e-4a05-ac09-cffe2b05900a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ef99d711a772a075f568a83f5d56fcecaaa598f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575702"
---
# <a name="populating-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="b3d2a-102">Preenchendo uma tabela hierárquica utilizando métodos hierárquicos</span><span class="sxs-lookup"><span data-stu-id="b3d2a-102">Populating a Hierarchical Table Using Hierarchical Methods</span></span>
  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="b3d2a-103">tem oito funcionários que trabalham no departamento de Marketing.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-103">has 8 employees working in the Marketing department.</span></span> <span data-ttu-id="b3d2a-104">A hierarquia dos funcionários é assim:</span><span class="sxs-lookup"><span data-stu-id="b3d2a-104">The employee hierarchy looks like this:</span></span>  
  
 <span data-ttu-id="b3d2a-105">**Davi**, **EmployeeID** 6, é o Gerente de Marketing.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-105">**David**, **EmployeeID** 6, is the Marketing Manager.</span></span> <span data-ttu-id="b3d2a-106">Três especialistas em Marketing são subordinados a **Davi**:</span><span class="sxs-lookup"><span data-stu-id="b3d2a-106">Three Marketing Specialists report to **David**:</span></span>  
  
-   <span data-ttu-id="b3d2a-107">**Sara**, **EmployeeID** 46</span><span class="sxs-lookup"><span data-stu-id="b3d2a-107">**Sariya**, **EmployeeID** 46</span></span>  
  
-   <span data-ttu-id="b3d2a-108">**Bruno**, **EmployeeID** 271</span><span class="sxs-lookup"><span data-stu-id="b3d2a-108">**John**, **EmployeeID** 271</span></span>  
  
-   <span data-ttu-id="b3d2a-109">**Julieta**, **EmployeeID** 119</span><span class="sxs-lookup"><span data-stu-id="b3d2a-109">**Jill**, **EmployeeID** 119</span></span>  
  
 <span data-ttu-id="b3d2a-110">A Assistente de Marketing **Valentina** , (**EmployeeID** 269), é subordinada a **Sara**, e a Assistente de Marketing **Marina** , (**EmployeeID** 272), é subordinada a **Bruno**.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-110">Marketing Assistant **Wanida** (**EmployeeID** 269), reports to **Sariya**, and Marketing Assistant **Mary** (**EmployeeID** 272), reports to **John**.</span></span>  
  
### <a name="to-insert-the-root-of-the-hierarchy-tree"></a><span data-ttu-id="b3d2a-111">Para inserir a raiz da árvore de hierarquia</span><span class="sxs-lookup"><span data-stu-id="b3d2a-111">To insert the root of the hierarchy tree</span></span>  
  
1.  <span data-ttu-id="b3d2a-112">O exemplo a seguir insere **Davi** , o Gerente de Marketing, na tabela da raiz da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-112">The following example inserts **David** the Marketing Manager into the table at the root of the hierarchy.</span></span> <span data-ttu-id="b3d2a-113">A coluna **OrdLevel** é uma coluna calculada.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-113">The **OrdLevel** column is a computed column.</span></span> <span data-ttu-id="b3d2a-114">Portanto, não faz parte da instrução INSERT.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-114">Therefore, it is not part of the INSERT statement.</span></span> <span data-ttu-id="b3d2a-115">Este primeiro registro usa o método [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) para popular o primeiro registro como a raiz da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-115">This first record uses the [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) method to populate this first record as the root of the hierarchy.</span></span>  
  
    ```  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES (hierarchyid::GetRoot(), 6, 'David', 'Marketing Manager') ;  
    GO  
    ```  
  
2.  <span data-ttu-id="b3d2a-116">Execute o seguinte código para examinar a linha inicial na tabela:</span><span class="sxs-lookup"><span data-stu-id="b3d2a-116">Execute the following code to examine initial row in the table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    ```  
  
 <span data-ttu-id="b3d2a-117">Como na lição anterior, usamos o método `ToString()` para converter o tipo de dados `hierarchyid` em um formato mais facilmente entendido.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-117">As in the previous lesson, we use the `ToString()` method to convert the `hierarchyid` data type to a format that is more easily understood.</span></span>  
  
### <a name="to-insert-a-subordinate-employee"></a><span data-ttu-id="b3d2a-118">Para inserir um funcionário subordinado</span><span class="sxs-lookup"><span data-stu-id="b3d2a-118">To insert a subordinate employee</span></span>  
  
1.  <span data-ttu-id="b3d2a-119">**Sara** é subordinada a **Davi**.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-119">**Sariya** reports to **David**.</span></span> <span data-ttu-id="b3d2a-120">Para inserir o nó **de Sariya** , você deve criar um valor de **OrgNode** apropriado do tipo de dados `hierarchyid` .</span><span class="sxs-lookup"><span data-stu-id="b3d2a-120">To insert **Sariya's** node, you must create an appropriate **OrgNode** value of data type `hierarchyid`.</span></span> <span data-ttu-id="b3d2a-121">O código a seguir cria uma variável do tipo de dados `hierarchyid` e a popula com o valor OrgNode de raiz da tabela.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-121">The following code creates a variable of data type `hierarchyid` and populates it with the root OrgNode value of the table.</span></span> <span data-ttu-id="b3d2a-122">Em seguida, usa essa variável com o método [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) para inserir a linha que é um nó subordinado.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-122">Then uses that variable with the [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) method to insert row that is a subordinate node.</span></span> <span data-ttu-id="b3d2a-123">`GetDescendant` usa dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-123">`GetDescendant` takes two arguments.</span></span> <span data-ttu-id="b3d2a-124">Analise as seguintes opções para os valores de argumento:</span><span class="sxs-lookup"><span data-stu-id="b3d2a-124">Review the following options for the argument values:</span></span>  
  
    -   <span data-ttu-id="b3d2a-125">Se o pai for o NULL, o `GetDescendant` retornará NULL.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-125">If parent is NULL, `GetDescendant` returns NULL.</span></span>  
  
    -   <span data-ttu-id="b3d2a-126">Se o pai não for NULL, e child1 e child2 forem NULL, o `GetDescendant` retornará um filho de pai.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-126">If parent is not NULL, and both child1 and child2 are NULL, `GetDescendant` returns a child of parent.</span></span>  
  
    -   <span data-ttu-id="b3d2a-127">Se o pai e child1 forem NULL e child2 for NULL, o `GetDescendant` retornará um filho de pai maior que child1.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-127">If parent and child1 are not NULL, and child2 is NULL, `GetDescendant` returns a child of parent greater than child1.</span></span>  
  
    -   <span data-ttu-id="b3d2a-128">Se o pai e child2 não forem NULL e child1 for NULL, o `GetDescendant` retornará um filho de pai menor que child2.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-128">If parent and child2 are not NULL and child1 is NULL, `GetDescendant` returns a child of parent less than child2.</span></span>  
  
    -   <span data-ttu-id="b3d2a-129">Se o pai, child 1 e child 2 não forem NULL, o `GetDescendant` retornará um filho de pai maior que child1 e menor que child2.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-129">If parent, child1, and child2 are all not NULL, `GetDescendant` returns a child of parent greater than child1 and less than child2.</span></span>  
  
     <span data-ttu-id="b3d2a-130">O código a seguir usa os argumentos `(NULL, NULL)` do pai da raiz, pois ainda não há linhas na tabela exceto a raiz.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-130">The following code uses the `(NULL, NULL)` arguments of the root parent because there are not yet any rows in the table except the root.</span></span> <span data-ttu-id="b3d2a-131">Execute o seguinte código para inserir **Sara**:</span><span class="sxs-lookup"><span data-stu-id="b3d2a-131">Execute the following code to insert **Sariya**:</span></span>  
  
    ```  
    DECLARE @Manager hierarchyid   
    SELECT @Manager = hierarchyid::GetRoot()  
    FROM HumanResources.EmployeeOrg ;  
  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES  
    (@Manager.GetDescendant(NULL, NULL), 46, 'Sariya', 'Marketing Specialist') ;  
  
    ```  
  
2.  <span data-ttu-id="b3d2a-132">Repita a consulta do primeiro procedimento para consultar a tabela e verificar como as entradas são exibidas:</span><span class="sxs-lookup"><span data-stu-id="b3d2a-132">Repeat the query from the first procedure to query the table and see how the entries appear:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    ```  
  
### <a name="to-create-a-procedure-for-entering-new-nodes"></a><span data-ttu-id="b3d2a-133">Para criar um procedimento para inserir novos nós</span><span class="sxs-lookup"><span data-stu-id="b3d2a-133">To create a procedure for entering new nodes</span></span>  
  
1.  <span data-ttu-id="b3d2a-134">Para simplificar a inserção de dados, crie o procedimento armazenado a seguir para adicionar funcionários à tabela **EmployeeOrg** .</span><span class="sxs-lookup"><span data-stu-id="b3d2a-134">To simplify entering data, create the following stored procedure to add employees to the **EmployeeOrg** table.</span></span> <span data-ttu-id="b3d2a-135">O procedimento aceita valores de entrada sobre o empregado sendo adicionado.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-135">The procedure accepts input values about the employee being added.</span></span> <span data-ttu-id="b3d2a-136">Isso inclui o **EmployeeID** do gerente do novo funcionário, o número **EmployeeID** do novo funcionário, além de seu nome e cargo.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-136">This includes the **EmployeeID** of the new employee's manager, the new employee's **EmployeeID** number, and their first name and title.</span></span> <span data-ttu-id="b3d2a-137">O procedimento usa `GetDescendant()` e o método [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="b3d2a-137">The procedure uses `GetDescendant()` and also the [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="b3d2a-138">Execute o seguinte código para criar o procedimento:</span><span class="sxs-lookup"><span data-stu-id="b3d2a-138">Execute the following code to create the procedure:</span></span>  
  
    ```  
    CREATE PROC AddEmp(@mgrid int, @empid int, @e_name varchar(20), @title varchar(20))   
    AS   
    BEGIN  
       DECLARE @mOrgNode hierarchyid, @lc hierarchyid  
       SELECT @mOrgNode = OrgNode   
       FROM HumanResources.EmployeeOrg   
       WHERE EmployeeID = @mgrid  
       SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
       BEGIN TRANSACTION  
          SELECT @lc = max(OrgNode)   
          FROM HumanResources.EmployeeOrg   
          WHERE OrgNode.GetAncestor(1) =@mOrgNode ;  
  
          INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
          VALUES(@mOrgNode.GetDescendant(@lc, NULL), @empid, @e_name, @title)  
       COMMIT  
    END ;  
    GO  
    ```  
  
2.  <span data-ttu-id="b3d2a-139">O exemplo a seguir adiciona os quatro funcionários restantes que são subordinados direta ou indiretamente a **Davi**.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-139">The following example adds the remaining 4 employees that report directly or indirectly to **David**.</span></span>  
  
    ```  
    EXEC AddEmp 6, 271, 'John', 'Marketing Specialist' ;  
    EXEC AddEmp 6, 119, 'Jill', 'Marketing Specialist' ;  
    EXEC AddEmp 46, 269, 'Wanida', 'Marketing Assistant' ;  
    EXEC AddEmp 271, 272, 'Mary', 'Marketing Assistant' ;  
    ```  
  
3.  <span data-ttu-id="b3d2a-140">Novamente, execute a seguinte consulta para examinar as linhas na tabela **EmployeeOrg** :</span><span class="sxs-lookup"><span data-stu-id="b3d2a-140">Again, execute the following query examine the rows in the **EmployeeOrg** table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    /1/1/        0x5AC0  2        269        Wanida  Marketing Assistant  
    /2/          0x68    1        271        John    Marketing Specialist  
    /2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
    /3/          0x78    1        119        Jill    Marketing Specialist  
    ```  
  
 <span data-ttu-id="b3d2a-141">Agora a tabela está totalmente populada com a organização de marketing.</span><span class="sxs-lookup"><span data-stu-id="b3d2a-141">The table is now fully populated with the Marketing organization.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b3d2a-142">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="b3d2a-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b3d2a-143">Consultando uma tabela hierárquica por meio de métodos de hierarquia</span><span class="sxs-lookup"><span data-stu-id="b3d2a-143">Querying a Hierarchical Table Using Hierarchy Methods</span></span>](lesson-2-3-querying-a-hierarchical-table-using-hierarchy-methods.md)  
  
  
