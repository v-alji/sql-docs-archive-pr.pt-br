---
title: Examinando a estrutura atual da tabela Employee | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- examining the current structure of the employee
ms.assetid: d546a820-105a-417d-ac35-44a6d1d70ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7f63773ebc1f28fb24f8f1000c3f87ee4d50544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568402"
---
# <a name="examining-the-current-structure-of-the-employee-table"></a><span data-ttu-id="1ec89-102">Examinando a estrutura atual da tabela Employee</span><span class="sxs-lookup"><span data-stu-id="1ec89-102">Examining the Current Structure of the Employee Table</span></span>
  <span data-ttu-id="1ec89-103"> O banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] contém uma tabela **Employee** no esquema **HumanResources**.</span><span class="sxs-lookup"><span data-stu-id="1ec89-103">The sample [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database contains an **Employee** table in the **HumanResources** schema.</span></span> <span data-ttu-id="1ec89-104">Para evitar alterar a tabela original, este passo cria uma cópia da tabela **Employee** nomeada **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="1ec89-104">To avoid changing the original table, this step makes a copy of the **Employee** table named **EmployeeDemo**.</span></span> <span data-ttu-id="1ec89-105">Para simplificar o exemplo, você copia só cinco colunas da tabela original.</span><span class="sxs-lookup"><span data-stu-id="1ec89-105">To simplify the example, you only copy five columns from the original table.</span></span> <span data-ttu-id="1ec89-106">Em seguida, você consulta a tabela **HumanResources. EmployeeDemo** para examinar como os dados são estruturados em uma tabela sem usar o `hierarchyid` tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="1ec89-106">Then, you query the **HumanResources.EmployeeDemo** table to review how the data is structured in a table without using the `hierarchyid` data type.</span></span>  
  
### <a name="to-copy-the-employee-table"></a><span data-ttu-id="1ec89-107">Para copiar a tabela Employee</span><span class="sxs-lookup"><span data-stu-id="1ec89-107">To copy the Employee table</span></span>  
  
1.  <span data-ttu-id="1ec89-108">Em uma janela Editor de Consultas, execute o código seguinte para copiar a estrutura de tabela e dados da tabela **Employee** em uma tabela nova nomeada **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="1ec89-108">In a Query Editor window, run the following code to copy the table structure and data from the **Employee** table into a new table named **EmployeeDemo**.</span></span>  
  
    ```  
    USE AdventureWorks ;  
    GO  
  
    SELECT EmployeeID, LoginID, ManagerID, Title, HireDate   
    INTO HumanResources.EmployeeDemo   
    FROM HumanResources.Employee ;  
    GO  
    ```  
  
### <a name="to-examine-the-structure-and-data-of-the-employeedemo-table"></a><span data-ttu-id="1ec89-109">Para examinar a estrutura e dados da tabela EmployeeDemo</span><span class="sxs-lookup"><span data-stu-id="1ec89-109">To examine the structure and data of the EmployeeDemo table</span></span>  
  
-   <span data-ttu-id="1ec89-110">Esta nova tabela **EmployeeDemo** representa uma tabela típica em um banco de dados existente que você pode querer migrar para uma nova estrutura.</span><span class="sxs-lookup"><span data-stu-id="1ec89-110">This new **EmployeeDemo** table represents a typical table in an existing database that you might want to migrate to a new structure.</span></span> <span data-ttu-id="1ec89-111">Em uma janela de Editor de Consultas, execute o código seguinte para mostrar como a tabela usa uma autojunção para exibir as relações de funcionário/gerente:</span><span class="sxs-lookup"><span data-stu-id="1ec89-111">In a Query Editor window, run the following code to show how the table uses a self join to display the employee/manager relationships:</span></span>  
  
    ```  
    SELECT   
         Mgr.EmployeeID AS MgrID, Mgr.LoginID AS Manager,   
         Emp.EmployeeID AS E_ID, Emp.LoginID, Emp.Title  
    FROM HumanResources.EmployeeDemo AS Emp  
    LEFT JOIN HumanResources.EmployeeDemo AS Mgr  
    ON Emp.ManagerID = Mgr.EmployeeID  
    ORDER BY MgrID, E_ID  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    MgrID Manager                 E_ID LoginID                  Title  
    NULL NULL                      109 adventure-works\ken0     Chief Executive Officer  
    3    adventure-works\roberto0  4   adventure-works\rob0     Senior Tool Designer  
    3    adventure-works\roberto0  9   adventure-works\gail0    Design Engineer  
    3    adventure-works\roberto0  11  adventure-works\jossef0  Design Engineer  
    3    adventure-works\roberto0  158 adventure-works\dylan0   Research and Development Manager  
    3    adventure-works\roberto0  263 adventure-works\ovidiu0  Senior Tool Designer  
    3    adventure-works\roberto0  267 adventure-works\michael8 Senior Design Engineer  
    3    adventure-works\roberto0  270 adventure-works\sharon0  Design Engineer  
    6    adventure-works\david0    2   adventure-works\kevin0   Marketing Assistant  
    ...  
    ```  
  
     <span data-ttu-id="1ec89-112">Os resultados continuam por um total de 290 linhas.</span><span class="sxs-lookup"><span data-stu-id="1ec89-112">The results continue for a total of 290 rows.</span></span>  
  
 <span data-ttu-id="1ec89-113">Observe que a cláusula `ORDER BY` fez com que a saída listasse os relatórios diretos de cada nível de administração junto.</span><span class="sxs-lookup"><span data-stu-id="1ec89-113">Notice that the `ORDER BY` clause caused the output to list the direct reports of each management level together.</span></span> <span data-ttu-id="1ec89-114">Por exemplo, todos os sete relatórios diretos de **MgrID** 3 (roberto0) são listados adjacentes um ao outro.</span><span class="sxs-lookup"><span data-stu-id="1ec89-114">For instance, all seven of the direct reports of **MgrID** 3 (roberto0) are listed adjacent to each other.</span></span> <span data-ttu-id="1ec89-115">Embora não seja impossível, é muito mais difícil de agrupar todos aqueles que eventualmente se reportem ao **MgrID** 3.</span><span class="sxs-lookup"><span data-stu-id="1ec89-115">Although not impossible, it is much more difficult to group all those who eventually report to **MgrID** 3.</span></span>  
  
 <span data-ttu-id="1ec89-116">Na próxima tarefa, nós criaremos uma nova tabela com um tipo de dados `hierarchyid` e moveremos os dados para a nova tabela.</span><span class="sxs-lookup"><span data-stu-id="1ec89-116">In the next task, we will create a new table with a `hierarchyid` data type, and move the data into the new table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="1ec89-117">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="1ec89-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="1ec89-118">Populando uma tabela com dados hierárquicos existentes</span><span class="sxs-lookup"><span data-stu-id="1ec89-118">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
  
