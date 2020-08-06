---
title: Criar consultas de pesquisa de texto completo (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CONTAINS predicate (Transact-SQL)
- queries [full-text search], creating
- full-text queries [SQL Server], creating
ms.assetid: 537fa556-390e-4c88-9b8e-679848d94abc
author: stevestein
ms.author: sstein
ms.openlocfilehash: f84ab465da0a1b7ac1da1211de1d5199fd28ee95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680260"
---
# <a name="create-full-text-search-queries-visual-database-tools"></a><span data-ttu-id="22471-102">Criar consultas de pesquisa de texto completo (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="22471-102">Create Full-Text Search Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="22471-103">Pesquisas de texto completo usam o predicado CONTAINS para localizar linhas que especificaram texto em uma determinada coluna.</span><span class="sxs-lookup"><span data-stu-id="22471-103">Full-text searches use the CONTAINS predicate to locate rows that have specified text in a given column.</span></span> <span data-ttu-id="22471-104">Pesquisas de texto completo somente são possíveis em colunas que têm índices de texto completo ativos.</span><span class="sxs-lookup"><span data-stu-id="22471-104">Full-Text searches are only possible on columns that have active full-text indexes.</span></span> <span data-ttu-id="22471-105">Se você tentar usar a cláusula CONTAINS em uma coluna que não tem um índice de texto completo ativo atualmente, receberá um erro.</span><span class="sxs-lookup"><span data-stu-id="22471-105">If you attempt to use the CONTAINS clause on a column that does not have a currently active full-text index, you will receive an error.</span></span> <span data-ttu-id="22471-106">Para obter mais informações sobre índices de texto completo e a cláusula CONTAINS, consulte [pesquisa de texto completo](../../relational-databases/search/full-text-search.md) e [contém &#40;&#41;Transact-SQL ](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="22471-106">For more information on full-text indexes and the CONTAINS clause, see [Full-Text Search](../../relational-databases/search/full-text-search.md) and [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
### <a name="to-create-a-full-text-search-query"></a><span data-ttu-id="22471-107">Para criar uma consulta de pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="22471-107">To create a full-text search query</span></span>  
  
1.  <span data-ttu-id="22471-108">Abra uma consulta no Gerenciador de Soluções ou crie uma consulta nova.</span><span class="sxs-lookup"><span data-stu-id="22471-108">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="22471-109">Na cláusula WHERE da consulta, use a função CONTAINS para pesquisar uma coluna de texto completo.</span><span class="sxs-lookup"><span data-stu-id="22471-109">In the WHERE clause of your query, use the CONTAINS function to search a full-text column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22471-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22471-110">See Also</span></span>  
 <span data-ttu-id="22471-111">[Tipos de consulta com suporte &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="22471-111">[Supported Query Types &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="22471-112">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="22471-112">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="22471-113">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="22471-113">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
