---
title: Criar consultas UNION (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- UNION queries
- Select query
- combining query results
- merged SELECT query [SQL Server]
ms.assetid: b5aafb1d-e4ed-4922-b790-56abc5ec551a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3c10f39c3e44844c4ec8a6a2328c41ea2de350d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574994"
---
# <a name="create-union-queries-visual-database-tools"></a><span data-ttu-id="9027b-102">Criar consultas UNION (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9027b-102">Create UNION Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="9027b-103">A palavra-chave UNION permite que se incluam resultados de duas instruções SELECT em uma tabela resultante.</span><span class="sxs-lookup"><span data-stu-id="9027b-103">The UNION keyword enables you to include the results of two SELECT statements in one resulting table.</span></span> <span data-ttu-id="9027b-104">Todas as linhas retornadas da instrução SELECT são combinadas no resultado da expressão UNION.</span><span class="sxs-lookup"><span data-stu-id="9027b-104">All rows returned from either SELECT statement are combined into the result of the UNION expression.</span></span> <span data-ttu-id="9027b-105">Para obter exemplos, consulte [exemplos de SELECT &#40;&#41;Transact-SQL ](/sql/t-sql/queries/select-examples-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9027b-105">For examples, see [SELECT Examples &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-examples-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9027b-106">O painel Diagrama só pode exibir uma cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="9027b-106">The Diagram pane can only display one SELECT clause.</span></span> <span data-ttu-id="9027b-107">Portanto, ao trabalhar com uma consulta UNION, o Designer de Consulta ocultará o painel Operações da Tabela.</span><span class="sxs-lookup"><span data-stu-id="9027b-107">Therefore, when you are working with a UNION query, Query Designer hides the Table Operations pane.</span></span>  
  
### <a name="to-create-a-merged-select-query"></a><span data-ttu-id="9027b-108">Para criar uma consulta SELECT mesclada</span><span class="sxs-lookup"><span data-stu-id="9027b-108">To create a Merged SELECT query</span></span>  
  
1.  <span data-ttu-id="9027b-109">Abra uma consulta ou crie uma nova.</span><span class="sxs-lookup"><span data-stu-id="9027b-109">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="9027b-110">No painel SQL, digite uma expressão UNION válida.</span><span class="sxs-lookup"><span data-stu-id="9027b-110">In the SQL pane, type a valid UNION expression.</span></span>  
  
     <span data-ttu-id="9027b-111">A seguir, um exemplo de uma expressão UNION válida.</span><span class="sxs-lookup"><span data-stu-id="9027b-111">The following example is a valid UNION expression.</span></span>  
  
    ```  
    SELECT ProductModelID, Name  
    FROM Production.ProductModel  
    UNION  
    SELECT ProductModelID, Name   
    FROM dbo.Gloves;  
    ```  
  
3.  <span data-ttu-id="9027b-112">No menu do **Designer de Consultas** , clique em **Executar SQL** para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="9027b-112">On the **Query Designer** menu, click **Execute SQL** to run the query.</span></span>  
  
     <span data-ttu-id="9027b-113">Nesse momento, a consulta UNION é formatada pelo Designer de Consulta.</span><span class="sxs-lookup"><span data-stu-id="9027b-113">Your UNION query is now formatted by Query Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9027b-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9027b-114">See Also</span></span>  
 <span data-ttu-id="9027b-115">[Tipos de consulta com suporte &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9027b-115">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="9027b-116">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9027b-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="9027b-117">[Executar operações básicas com consultas &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9027b-117">[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9027b-118">UNION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9027b-118">UNION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/set-operators-union-transact-sql)  
  
  
