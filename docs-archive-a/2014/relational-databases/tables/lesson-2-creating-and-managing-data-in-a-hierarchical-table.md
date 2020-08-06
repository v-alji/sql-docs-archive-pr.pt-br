---
title: 'Lição 2: Criando e gerenciando dados em uma tabela hierárquica | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 95f55cff-4abb-4c08-97b3-e3ae5e8b24e2
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2cecdc768b311e53ea7f65d40737fa57477da16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569273"
---
# <a name="lesson-2-creating-and-managing-data-in-a-hierarchical-table"></a><span data-ttu-id="7176e-102">Lição 2: Criando e gerenciando dados em uma tabela hierárquica</span><span class="sxs-lookup"><span data-stu-id="7176e-102">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>
  <span data-ttu-id="7176e-103">Na Lição 1, você modificou uma tabela existente para usar o tipo de dados `hierarchyid` e populou a coluna `hierarchyid` com a representação dos dados existentes.</span><span class="sxs-lookup"><span data-stu-id="7176e-103">In Lesson 1, you modified an existing table to use the `hierarchyid` data type, and populated the `hierarchyid` column with the representation of the existing data.</span></span> <span data-ttu-id="7176e-104">Nesta lição, você iniciará com uma tabela nova, e inserindo dados usando os métodos hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="7176e-104">In this lesson, you will start with a new table, and insert data by using the hierarchical methods.</span></span> <span data-ttu-id="7176e-105">Em seguida, você vai consultar e manipular os dados usando os métodos hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="7176e-105">Then, you will query and manipulate the data by using the hierarchical methods.</span></span>  
  
 <span data-ttu-id="7176e-106">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="7176e-106">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="7176e-107">Criando uma tabela por meio de um tipo de dados hierarchyid</span><span class="sxs-lookup"><span data-stu-id="7176e-107">Creating a Table Using the hierarchyid Data Type</span></span>](lesson-2-1-creating-a-table-using-the-hierarchyid-data-type.md)  
  
-   [<span data-ttu-id="7176e-108">Preenchendo uma tabela hierárquica utilizando métodos hierárquicos</span><span class="sxs-lookup"><span data-stu-id="7176e-108">Populating a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-2-populating-a-hierarchical-table-using-hierarchical-methods.md)  
  
-   [<span data-ttu-id="7176e-109">Consultando uma tabela hierárquica por meio de métodos de hierarquia</span><span class="sxs-lookup"><span data-stu-id="7176e-109">Querying a Hierarchical Table Using Hierarchy Methods</span></span>](lesson-2-3-querying-a-hierarchical-table-using-hierarchy-methods.md)  
  
-   [<span data-ttu-id="7176e-110">Reordenando dados em tabela hierárquica por meio de métodos hierárquicos</span><span class="sxs-lookup"><span data-stu-id="7176e-110">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
-   [<span data-ttu-id="7176e-111">Resumo: Gerenciar dados em uma tabela hierárquica</span><span class="sxs-lookup"><span data-stu-id="7176e-111">Summary: Managing Data in a Hierarchical Table</span></span>](lesson-2-5-summary-managing-data-in-a-hierarchical-table.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7176e-112">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="7176e-112">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7176e-113">Criando uma tabela por meio de um tipo de dados hierarchyid</span><span class="sxs-lookup"><span data-stu-id="7176e-113">Creating a Table Using the hierarchyid Data Type</span></span>](lesson-2-1-creating-a-table-using-the-hierarchyid-data-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="7176e-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7176e-114">See Also</span></span>  
 [<span data-ttu-id="7176e-115">Lição 1: conversão de uma tabela em uma estrutura hierárquica</span><span class="sxs-lookup"><span data-stu-id="7176e-115">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-converting-a-table-to-a-hierarchical-structure.md)  
  
  
