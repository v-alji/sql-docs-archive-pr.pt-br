---
title: 'Lição 1: Convertendo uma tabela em uma estrutura hierárquica | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 5ee6f19a-6dd7-4730-a91c-bbed1bd77e0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 196a546093786f9be4b88536763b3150ae750f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685043"
---
# <a name="lesson-1-converting-a-table-to-a-hierarchical-structure"></a><span data-ttu-id="49345-102">Lição 1: Convertendo uma tabela em uma estrutura hierárquica</span><span class="sxs-lookup"><span data-stu-id="49345-102">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>
  <span data-ttu-id="49345-103">Os clientes que possuem tabelas que usam autojunções para expressar relações hierárquicas podem converter as tabelas em uma estrutura hierárquica usando esta lição como guia.</span><span class="sxs-lookup"><span data-stu-id="49345-103">Customers who have tables using self joins to express hierarchical relationships can convert their tables to a hierarchical structure using this lesson as a guide.</span></span> <span data-ttu-id="49345-104">É relativamente fácil fazer a migração dessa representação para outra usando `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="49345-104">It is relatively easy to migrate from this representation to one using `hierarchyid`.</span></span> <span data-ttu-id="49345-105">Depois da migração, os usuários terão uma representação hierárquica compacta e fácil de entender, que poderá ser indexada de várias formas para proporcionar consultas eficientes.</span><span class="sxs-lookup"><span data-stu-id="49345-105">After migration, users will have a compact and easy to understand hierarchical representation, which can be indexed in several ways for efficient queries.</span></span>  
  
 <span data-ttu-id="49345-106">Esta lição examina uma tabela existente, cria uma tabela contendo uma coluna `hierarchyid`, popula a tabela com os dados da tabela de origem e, depois, demonstra três estratégias de indexação.</span><span class="sxs-lookup"><span data-stu-id="49345-106">This lesson, examines an existing table, creates a new table containing a `hierarchyid` column, populates the table with the data from the source table, and then demonstrates three indexing strategies.</span></span> <span data-ttu-id="49345-107">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="49345-107">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="49345-108">Examinando a estrutura atual da tabela Employee</span><span class="sxs-lookup"><span data-stu-id="49345-108">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
-   [<span data-ttu-id="49345-109">Populando uma tabela com dados hierárquicos existentes</span><span class="sxs-lookup"><span data-stu-id="49345-109">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
-   [<span data-ttu-id="49345-110">Otimizando a tabela NewOrg</span><span class="sxs-lookup"><span data-stu-id="49345-110">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
-   [<span data-ttu-id="49345-111">Resumo: conversão de uma tabela em uma estrutura hierárquica</span><span class="sxs-lookup"><span data-stu-id="49345-111">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
## <a name="prerequisites"></a><span data-ttu-id="49345-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="49345-112">Prerequisites</span></span>  
 <span data-ttu-id="49345-113">Esta lição exige o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49345-113">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="49345-114">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="49345-114">Next Task in Lesson</span></span>  
 [<span data-ttu-id="49345-115">Examinando a estrutura atual da tabela Employee</span><span class="sxs-lookup"><span data-stu-id="49345-115">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="49345-116">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="49345-116">Next Lesson</span></span>  
 [<span data-ttu-id="49345-117">Lição 2: Criando e gerenciando dados em uma tabela hierárquica</span><span class="sxs-lookup"><span data-stu-id="49345-117">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
  
  
