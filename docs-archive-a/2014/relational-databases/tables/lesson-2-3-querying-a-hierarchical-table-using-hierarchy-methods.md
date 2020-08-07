---
title: Consultando uma tabela hierárquica usando métodos de hierarquia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 3b4f7dae-65b5-4d8d-8641-87aba9aa692d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c86c8e8678fc821dc3796a511349c1c3498bdb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575037"
---
# <a name="querying-a-hierarchical-table-using-hierarchy-methods"></a><span data-ttu-id="cea62-102">Consultando uma tabela hierárquica por meio de métodos de hierarquia</span><span class="sxs-lookup"><span data-stu-id="cea62-102">Querying a Hierarchical Table Using Hierarchy Methods</span></span>
  <span data-ttu-id="cea62-103">Agora que a tabela HumanResources.EmployeeOrg está completamente populada, essa tarefa mostrará como consultar a hierarquia usando alguns métodos hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="cea62-103">Now that the HumanResources.EmployeeOrg table is fully populated, this task will show you how to query the hierarchy using some of the hierarchical methods.</span></span>  
  
### <a name="to-find-subordinate-nodes"></a><span data-ttu-id="cea62-104">Para localizar nós subordinados</span><span class="sxs-lookup"><span data-stu-id="cea62-104">To find subordinate nodes</span></span>  
  
1.  <span data-ttu-id="cea62-105">Sariya tem um funcionário subordinado.</span><span class="sxs-lookup"><span data-stu-id="cea62-105">Sariya has one subordinate employee.</span></span> <span data-ttu-id="cea62-106">Para consultar os subordinados de Sara, execute a seguinte consulta, que usa o método [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) :</span><span class="sxs-lookup"><span data-stu-id="cea62-106">To query for Sariya's subordinates, execute the following query that uses the [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) method:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.IsDescendantOf(@CurrentEmployee ) = 1 ;  
    ```  
  
     <span data-ttu-id="cea62-107">O resultado lista Sariya e Wanida.</span><span class="sxs-lookup"><span data-stu-id="cea62-107">The result lists both Sariya and Wanida.</span></span> <span data-ttu-id="cea62-108">Sariya é listada porque é a descendente no nível 0.</span><span class="sxs-lookup"><span data-stu-id="cea62-108">Sariya is listed because she is the descendant at the 0 level.</span></span> <span data-ttu-id="cea62-109">Wanida é a descendente no nível 1.</span><span class="sxs-lookup"><span data-stu-id="cea62-109">Wanida is the descendant at the 1 level.</span></span>  
  
2.  <span data-ttu-id="cea62-110">Você também pode consultar essas informações usando o método [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="cea62-110">You can also query for this information by using the [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="cea62-111">`GetAncestor` usa um argumento para o nível que você está tentando retornar.</span><span class="sxs-lookup"><span data-stu-id="cea62-111">`GetAncestor` takes an argument for the level that you are trying to return.</span></span> <span data-ttu-id="cea62-112">Como Wanida está um nível abaixo de Sariya, use `GetAncestor(1)` conforme demonstrado no seguinte código:</span><span class="sxs-lookup"><span data-stu-id="cea62-112">Since Wanida is one level underneath Sariya, use `GetAncestor(1)` as demonstrated in the following code:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="cea62-113">Desta vez o resultado lista apenas Wanida.</span><span class="sxs-lookup"><span data-stu-id="cea62-113">This time the result lists only Wanida.</span></span>  
  
3.  <span data-ttu-id="cea62-114">Agora altere o `@CurrentEmployee` para David (EmployeeID 6) e o nível para 2.</span><span class="sxs-lookup"><span data-stu-id="cea62-114">Now change the `@CurrentEmployee` to David (EmployeeID 6) and the level to 2.</span></span> <span data-ttu-id="cea62-115">Execute o seguinte para retornar também Wanida:</span><span class="sxs-lookup"><span data-stu-id="cea62-115">Execute the following to also return Wanida:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 6 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(2) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="cea62-116">Desta vez, você também recebe Mary que também é subordinada a David, dois níveis abaixo.</span><span class="sxs-lookup"><span data-stu-id="cea62-116">This time, you also receive Mary who also reports to David, two levels down.</span></span>  
  
### <a name="to-use-getroot-and-getlevel"></a><span data-ttu-id="cea62-117">Para usar GetRoot e GetLevel</span><span class="sxs-lookup"><span data-stu-id="cea62-117">To use GetRoot, and GetLevel</span></span>  
  
1.  <span data-ttu-id="cea62-118">À medida que a hierarquia fica maior é mais difícil determinar onde os membros estão na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="cea62-118">As the hierarchy grows larger it is more difficult to determine where the members are in the hierarchy.</span></span> <span data-ttu-id="cea62-119">Use o método [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) para localizar quantos níveis abaixo cada linha está na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="cea62-119">Use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to find how many levels down each row is in the hierarchy.</span></span> <span data-ttu-id="cea62-120">Execute o seguinte código para exibir os níveis de todas as linhas:</span><span class="sxs-lookup"><span data-stu-id="cea62-120">Execute the following code to view the levels of all the rows:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode.GetLevel() AS EmpLevel, *  
    FROM HumanResources.EmployeeOrg ;  
    GO  
  
    ```  
  
2.  <span data-ttu-id="cea62-121">Use o método [GetRoot](/sql/t-sql/data-types/getroot-database-engine) para localizar o nó raiz na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="cea62-121">Use the [GetRoot](/sql/t-sql/data-types/getroot-database-engine) method to find the root node in the hierarchy.</span></span> <span data-ttu-id="cea62-122">O seguinte código retorna uma única linha que é a raiz:</span><span class="sxs-lookup"><span data-stu-id="cea62-122">The following code returns the single row which is the root:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode = hierarchyid::GetRoot() ;  
    GO  
  
    ```  
  
 <span data-ttu-id="cea62-123">A próxima tarefa reorganizará a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="cea62-123">The next task will reorganize the hierarchy.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cea62-124">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="cea62-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cea62-125">Reordenando dados em tabela hierárquica por meio de métodos hierárquicos</span><span class="sxs-lookup"><span data-stu-id="cea62-125">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
