---
title: Reordenando dados em uma tabela hierárquica usando métodos hierárquicos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 7b8064c7-62c6-488d-84d2-57a5828fb907
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac6c93f359a81a80af81182120f213564680de0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569275"
---
# <a name="reordering-data-in-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="4da79-102">Reordenando dados em tabela hierárquica por meio de métodos hierárquicos</span><span class="sxs-lookup"><span data-stu-id="4da79-102">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>
  <span data-ttu-id="4da79-103">Reorganizar uma hierarquia é uma tarefa de manutenção comum.</span><span class="sxs-lookup"><span data-stu-id="4da79-103">Reorganizing a hierarchy is a common maintenance task.</span></span> <span data-ttu-id="4da79-104">Nesta tarefa, usaremos a instrução UPDATE com o método [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) para mover primeiramente uma única linha para um novo local da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="4da79-104">In this task, we will use an UPDATE statement with the [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) method to first move a single row to a new location in the hierarchy.</span></span> <span data-ttu-id="4da79-105">Em seguida, moveremos uma subárvore inteira para um novo local.</span><span class="sxs-lookup"><span data-stu-id="4da79-105">Then we will move an entire sub-tree to a new location.</span></span>  
  
 <span data-ttu-id="4da79-106">O método `GetReparentedValue` toma dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="4da79-106">The `GetReparentedValue` method takes two arguments.</span></span> <span data-ttu-id="4da79-107">O primeiro argumento descreve a parte da hierarquia a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="4da79-107">The first argument describes the part of the hierarchy to be modified.</span></span> <span data-ttu-id="4da79-108">Por exemplo, se uma hierarquia for **/1/4/2/3/** e você desejar alterar a seção **/1/4/** , a hierarquia se tornará **/2/1/2/3/**; se deixar os últimos dois nós (**2/3/**) inalterados, você precisará fornecer os nós que estão sendo alterados (**/1/4/**) como o primeiro argumento.</span><span class="sxs-lookup"><span data-stu-id="4da79-108">For example, if a hierarchy is **/1/4/2/3/** and you want to change the **/1/4/** section, the hierarchy becomes **/2/1/2/3/**, leaving the last two nodes (**2/3/**) unchanged, you must provide the changing nodes (**/1/4/**) as the first argument.</span></span> <span data-ttu-id="4da79-109">O segundo argumento fornece o novo nível hierárquico, em nosso exemplo **/2/1/**.</span><span class="sxs-lookup"><span data-stu-id="4da79-109">The second argument provides the new hierarchy level, in our example **/2/1/**.</span></span> <span data-ttu-id="4da79-110">Os dois argumentos não precisam conter o mesmo número de níveis.</span><span class="sxs-lookup"><span data-stu-id="4da79-110">The two arguments do not have to contain the same number of levels.</span></span>  
  
### <a name="to-move-a-single-row-to-a-new-location-in-the-hierarchy"></a><span data-ttu-id="4da79-111">Para mover uma linha única para um novo local hierárquico</span><span class="sxs-lookup"><span data-stu-id="4da79-111">To move a single row to a new location in the hierarchy</span></span>  
  
1.  <span data-ttu-id="4da79-112">Atualmente, Wanida reporta-se a Sariya.</span><span class="sxs-lookup"><span data-stu-id="4da79-112">Currently Wanida reports to Sariya.</span></span> <span data-ttu-id="4da79-113">Neste procedimento, você move Valentina de seu nó **/1/1/** atual, de modo que ela se reporte a Julieta.</span><span class="sxs-lookup"><span data-stu-id="4da79-113">In this procedure, you move Wanida from her current node **/1/1/,** so that she reports to Jill.</span></span> <span data-ttu-id="4da79-114">Seu novo nó se tornará **/3/1/** e, dessa forma, **/1/** será o primeiro argumento e **/3/** o segundo.</span><span class="sxs-lookup"><span data-stu-id="4da79-114">Her new node will become **/3/1/** so **/1/** is the first argument and **/3/** is the second.</span></span> <span data-ttu-id="4da79-115">Esses correspondem aos valores **OrgNode** de Sara e Julieta.</span><span class="sxs-lookup"><span data-stu-id="4da79-115">These correspond to the **OrgNode** values of Sariya and Jill.</span></span> <span data-ttu-id="4da79-116">Execute o código a seguir para mover Wanida da organização de Sariya para a organização de Jill:</span><span class="sxs-lookup"><span data-stu-id="4da79-116">Execute the following code to move Wanida from Sariya's organization to Jill's:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @CurrentEmployee = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 269 ;   
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 46 ;   
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 119 ;   
  
    UPDATE HumanResources.EmployeeOrg  
    SET OrgNode = @CurrentEmployee. GetReparentedValue(@OldParent, @NewParent)   
    WHERE OrgNode = @CurrentEmployee ;  
    GO  
    ```  
  
2.  <span data-ttu-id="4da79-117">Execute o seguinte código para ver o resultado:</span><span class="sxs-lookup"><span data-stu-id="4da79-117">Execute the following code to see the result:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     <span data-ttu-id="4da79-118">Valentina encontra-se agora no nó **/3/1/**.</span><span class="sxs-lookup"><span data-stu-id="4da79-118">Wanida is now at node **/3/1/**.</span></span>  
  
### <a name="to-reorganize-a-section-of-a-hierarchy"></a><span data-ttu-id="4da79-119">Para reorganizar uma seção de hierarquia</span><span class="sxs-lookup"><span data-stu-id="4da79-119">To reorganize a section of a hierarchy</span></span>  
  
1.  <span data-ttu-id="4da79-120">Para demonstrar como mover um grande número de pessoas ao mesmo tempo, execute primeiramente o código a seguir para adicionar um estagiário se reportando a Wanida:</span><span class="sxs-lookup"><span data-stu-id="4da79-120">To demonstrate how to move a larger number of people at the same time, first execute the following code to add an intern reporting to Wanida:</span></span>  
  
    ```  
    EXEC AddEmp 269, 291, 'Kevin', 'Marketing Intern'  ;  
    GO  
    ```  
  
2.  <span data-ttu-id="4da79-121">Kevin agora se reporta a Wanida, que se reporta a Jill, que se reporta a David.</span><span class="sxs-lookup"><span data-stu-id="4da79-121">Now Kevin reports to Wanida, who reports to Jill, who reports to David.</span></span> <span data-ttu-id="4da79-122">Isso significa que Julio se encontra no nível **/3/1/1/**.</span><span class="sxs-lookup"><span data-stu-id="4da79-122">That means that Kevin is at level **/3/1/1/**.</span></span> <span data-ttu-id="4da79-123">Para mover todos os subordinados de Julieta para um novo administrador, atualizaremos todos os nós com **/3/** como seus **OrgNode** para um novo valor.</span><span class="sxs-lookup"><span data-stu-id="4da79-123">To move all of Jill's subordinates to a new manager, we will update all nodes that have **/3/** as their **OrgNode** to a new value.</span></span> <span data-ttu-id="4da79-124">Execute o seguinte código para atualizar Wanida, de modo que passe a se reportar a Sariya, mas deixando Kevin se reportando a Wanida:</span><span class="sxs-lookup"><span data-stu-id="4da79-124">Execute the following code to update Wanida to report to Sariya, but keep  Kevin reporting to Wanida:</span></span>  
  
    ```  
    DECLARE @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 119 ; -- Jill  
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ; -- Sariya  
    DECLARE children_cursor CURSOR FOR  
    SELECT OrgNode FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @OldParent;  
    DECLARE @ChildId hierarchyid;  
    OPEN children_cursor  
    FETCH NEXT FROM children_cursor INTO @ChildId;  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
    START:  
        DECLARE @NewId hierarchyid;  
        SELECT @NewId = @NewParent.GetDescendant(MAX(OrgNode), NULL)  
        FROM HumanResources.EmployeeOrg WHERE OrgNode.GetAncestor(1) = @NewParent;  
  
        UPDATE HumanResources.EmployeeOrg  
        SET OrgNode = OrgNode.GetReparentedValue(@ChildId, @NewId)  
        WHERE OrgNode.IsDescendantOf(@ChildId) = 1;  
        IF @@error <> 0 GOTO START -- On error, retry  
            FETCH NEXT FROM children_cursor INTO @ChildId;  
    END  
    CLOSE children_cursor;  
    DEALLOCATE children_cursor;  
  
    ```  
  
3.  <span data-ttu-id="4da79-125">Execute o seguinte código para ver o resultado:</span><span class="sxs-lookup"><span data-stu-id="4da79-125">Execute the following code to see the result:</span></span>  
  
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
/1/1//2      0x5AD0  3        291        Kevin   Marketing Intern  
/2/          0x68    1        271        John    Marketing Specialist  
/2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
/3/          0x78    1        119        Jill    Marketing Specialist  
```  
  
 <span data-ttu-id="4da79-126">Toda a árvore organizacional que se reportava a Jill (Wanida e Kevin), agora se reporta a Sariya.</span><span class="sxs-lookup"><span data-stu-id="4da79-126">The entire organizational tree that had reported to Jill (both Wanida and Kevin) now reports to Sariya.</span></span>  
  
 <span data-ttu-id="4da79-127">Para ver um procedimento armazenado que reorganiza uma seção de uma hierarquia, consulte a seção “Movendo subárvores” de [Movendo subárvores](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span><span class="sxs-lookup"><span data-stu-id="4da79-127">For a stored procedure to reorganize a section of a hierarchy, see the "Moving Subtrees" section of [Moving Subtrees](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4da79-128">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="4da79-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4da79-129">Resumo: Gerenciar dados em uma tabela hierárquica</span><span class="sxs-lookup"><span data-stu-id="4da79-129">Summary: Managing Data in a Hierarchical Table</span></span>](lesson-2-5-summary-managing-data-in-a-hierarchical-table.md)  
  
  
