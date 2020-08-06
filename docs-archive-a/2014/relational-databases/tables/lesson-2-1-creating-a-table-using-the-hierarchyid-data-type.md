---
title: Criando uma tabela usando um tipo de dados hierarchyid | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 0d1f361f-336c-4571-99d1-f4813b2d9fc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2c9b59795949e11cabd21b0be8de844b33d73c37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685040"
---
# <a name="creating-a-table-using-the-hierarchyid-data-type"></a><span data-ttu-id="25c2d-102">Criando uma tabela por meio de um tipo de dados hierarchyid</span><span class="sxs-lookup"><span data-stu-id="25c2d-102">Creating a Table Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="25c2d-103">O exemplo a seguir cria uma tabela com o nome EmployeeOrg, que inclui dados de funcionário junto com sua hierarquia de relatórios.</span><span class="sxs-lookup"><span data-stu-id="25c2d-103">The following example creates a table named EmployeeOrg, which includes employee data together with their reporting hierarchy.</span></span> <span data-ttu-id="25c2d-104">O exemplo cria a tabela no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , mas isso é opcional.</span><span class="sxs-lookup"><span data-stu-id="25c2d-104">The example creates the table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, but that is optional.</span></span> <span data-ttu-id="25c2d-105">Para manter o exemplo simples, essa tabela inclui somente cinco colunas:</span><span class="sxs-lookup"><span data-stu-id="25c2d-105">To keep the example simple, this table includes only five columns:</span></span>  
  
-   <span data-ttu-id="25c2d-106">OrgNode é uma coluna `hierarchyid` que armazena a relação hierárquica.</span><span class="sxs-lookup"><span data-stu-id="25c2d-106">OrgNode is a `hierarchyid` column that stores the hierarchical relationship.</span></span>  
  
-   <span data-ttu-id="25c2d-107">OrgLevel é uma coluna computada, com base na coluna OrgNode, que armazena cada nível de nó na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="25c2d-107">OrgLevel is a computed column, based on the OrgNode column that stores each nodes level in the hierarchy.</span></span> <span data-ttu-id="25c2d-108">Ela será usada para um índice por amplitude.</span><span class="sxs-lookup"><span data-stu-id="25c2d-108">It will be used for a breadth-first index.</span></span>  
  
-   <span data-ttu-id="25c2d-109">EmployeeID contém o número de identificação de funcionário comum usado para aplicativos como folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="25c2d-109">EmployeeID contains the typical employee identification number that is used for applications such as payroll.</span></span> <span data-ttu-id="25c2d-110">No desenvolvimento de um novo aplicativo, os aplicativos podem usar a coluna OrgNode e a coluna EmployeeID separada não é necessária.</span><span class="sxs-lookup"><span data-stu-id="25c2d-110">In new application development, applications can use the OrgNode column and this separate EmployeeID column is not needed.</span></span>  
  
-   <span data-ttu-id="25c2d-111">EmpName contém o nome do funcionário.</span><span class="sxs-lookup"><span data-stu-id="25c2d-111">EmpName contains the name of the employee.</span></span>  
  
-   <span data-ttu-id="25c2d-112">Title contém o cargo do funcionário.</span><span class="sxs-lookup"><span data-stu-id="25c2d-112">Title contains the title of the employee.</span></span>  
  
### <a name="to-create-the-employeeorg-table"></a><span data-ttu-id="25c2d-113">Para criar a tabela EmployeeOrg</span><span class="sxs-lookup"><span data-stu-id="25c2d-113">To create the EmployeeOrg table</span></span>  
  
1.  <span data-ttu-id="25c2d-114">Em uma janela do Editor de Consulta, execute o código a seguir para criar a tabela `EmployeeOrg` .</span><span class="sxs-lookup"><span data-stu-id="25c2d-114">In a Query Editor window, run the following code to create the `EmployeeOrg` table.</span></span> <span data-ttu-id="25c2d-115">A especificação da coluna `OrgNode` como a chave primária com um índice clusterizado criará um índice por amplitude:</span><span class="sxs-lookup"><span data-stu-id="25c2d-115">Specifying the `OrgNode` column as the primary key with a clustered index will create a depth-first index:</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    CREATE TABLE HumanResources.EmployeeOrg  
    (  
       OrgNode hierarchyid PRIMARY KEY CLUSTERED,  
       OrgLevel AS OrgNode.GetLevel(),  
       EmployeeID int UNIQUE NOT NULL,  
       EmpName varchar(20) NOT NULL,  
       Title varchar(20) NULL  
    ) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="25c2d-116">Execute o seguinte código para criar um índice composto nas colunas `OrgLevel` e `OrgNode` para oferecer suporte a pesquisas eficientes por amplitude:</span><span class="sxs-lookup"><span data-stu-id="25c2d-116">Run the following code to create a composite index on the `OrgLevel` and `OrgNode` columns to support efficient breadth-first searches:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmployeeOrgNc1   
    ON HumanResources.EmployeeOrg(OrgLevel, OrgNode) ;  
    GO  
    ```  
  
 <span data-ttu-id="25c2d-117">Agora a tabela está pronta para receber dados.</span><span class="sxs-lookup"><span data-stu-id="25c2d-117">The table is now ready for data.</span></span> <span data-ttu-id="25c2d-118">A próxima tarefa populará a tabela usando métodos hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="25c2d-118">The next task will populate the table by using hierarchical methods.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="25c2d-119">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="25c2d-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="25c2d-120">Preenchendo uma tabela hierárquica utilizando métodos hierárquicos</span><span class="sxs-lookup"><span data-stu-id="25c2d-120">Populating a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-2-populating-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
