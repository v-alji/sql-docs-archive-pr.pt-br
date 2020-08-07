---
title: Especificar vários critérios de pesquisa para várias colunas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 06617729-0d0b-4da2-9890-b7e2f5cdbc7b
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccf08a98d39d4ab808b7c2df794164b341be363a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571742"
---
# <a name="specify-multiple-search-conditions-for-multiple-columns-visual-database-tools"></a><span data-ttu-id="da5a0-102">Especificar várias condições de pesquisa para diversas colunas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="da5a0-102">Specify Multiple Search Conditions for Multiple Columns (Visual Database Tools)</span></span>
  <span data-ttu-id="da5a0-103">Você pode expandir ou estreitar o escopo de sua consulta incluindo várias colunas de dados como parte de seu critério de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="da5a0-103">You can expand or narrow the scope of your query by including several data columns as part of your search condition.</span></span> <span data-ttu-id="da5a0-104">Por exemplo, você pode querer:</span><span class="sxs-lookup"><span data-stu-id="da5a0-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="da5a0-105">Pesquisar funcionários que já trabalham há mais de cinco anos na empresa ou que possuam determinados cargos.</span><span class="sxs-lookup"><span data-stu-id="da5a0-105">Search for employees who either have worked more than five years at the company or who hold certain jobs.</span></span>  
  
-   <span data-ttu-id="da5a0-106">Pesquisar um livro publicado por um editor específico e que pertence ao setor de culinária.</span><span class="sxs-lookup"><span data-stu-id="da5a0-106">Search for a book that is both published by a specific publisher and pertains to cooking.</span></span>  
  
 <span data-ttu-id="da5a0-107">Para criar uma consulta que pesquisa valores em duas (ou mais) colunas, você especifica uma condição OR.</span><span class="sxs-lookup"><span data-stu-id="da5a0-107">To create a query that searches for values in either of two (or more) columns, you specify an OR condition.</span></span> <span data-ttu-id="da5a0-108">Para criar uma consulta que atenda todas as condições em duas (ou mais) colunas, você especifica uma condição AND.</span><span class="sxs-lookup"><span data-stu-id="da5a0-108">To create a query that must meet all conditions in two (or more) columns, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="da5a0-109">Especificando um critério OR</span><span class="sxs-lookup"><span data-stu-id="da5a0-109">Specifying an OR Condition</span></span>  
 <span data-ttu-id="da5a0-110">Para criar várias condições vinculadas a OR, você coloca cada condição separada em uma coluna diferente do painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="da5a0-110">To create multiple conditions linked with OR, you put each separate condition in a different column of the Criteria pane.</span></span>  
  
#### <a name="to-specify-an-or-condition-for-two-different-columns"></a><span data-ttu-id="da5a0-111">Para especificar uma condição OR para duas colunas diferentes</span><span class="sxs-lookup"><span data-stu-id="da5a0-111">To specify an OR condition for two different columns</span></span>  
  
1.  <span data-ttu-id="da5a0-112">No [Painel Critérios](visual-database-tools.md), adicione as colunas a serem pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="da5a0-112">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="da5a0-113">Na coluna **Filtro** da primeira coluna a ser pesquisada, especifique a primeira condição.</span><span class="sxs-lookup"><span data-stu-id="da5a0-113">In the **Filter** column for the first column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="da5a0-114">Na coluna **Ou...** da segunda coluna de dados a ser pesquisada, especifique a segunda condição, deixando a coluna **Filtro** em branco.</span><span class="sxs-lookup"><span data-stu-id="da5a0-114">In the **Or...** column for the second data column to search, specify the second condition, leaving the **Filter** column blank.</span></span>  
  
     <span data-ttu-id="da5a0-115">O Designer de Consulta e Exibição cria uma cláusula WHERE que contém um critério OR, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="da5a0-115">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
    ```  
    SELECT job_lvl, hire_date  
    FROM employee  
    WHERE (job_lvl >= 200) OR   
      (hire_date < '01/01/1998')  
    ```  
  
4.  <span data-ttu-id="da5a0-116">Repita as etapas 2 e 3 para cada condição adicional que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="da5a0-116">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span> <span data-ttu-id="da5a0-117">Utilize uma coluna **Ou...** diferente para cada condição nova.</span><span class="sxs-lookup"><span data-stu-id="da5a0-117">Use a different **Or...** column for each new condition.</span></span>  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="da5a0-118">Especificando um critério AND</span><span class="sxs-lookup"><span data-stu-id="da5a0-118">Specifying an AND Condition</span></span>  
 <span data-ttu-id="da5a0-119">Para pesquisar várias colunas de dados usando condições vinculadas a AND, coloque todas as condições na coluna **Filtro** da grade.</span><span class="sxs-lookup"><span data-stu-id="da5a0-119">To search different data columns using conditions linked with AND, you put all the conditions in the **Filter** column of the grid.</span></span>  
  
#### <a name="to-specify-an-and-condition-for-two-different-columns"></a><span data-ttu-id="da5a0-120">Para especificar uma condição AND para duas colunas diferentes</span><span class="sxs-lookup"><span data-stu-id="da5a0-120">To specify an AND condition for two different columns</span></span>  
  
1.  <span data-ttu-id="da5a0-121">No [Painel Critérios](visual-database-tools.md), adicione as colunas a serem pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="da5a0-121">In the [Criteria Pane](visual-database-tools.md), add the columns you want to search.</span></span>  
  
2.  <span data-ttu-id="da5a0-122">Na coluna **Filtro** da primeira coluna de dados a ser pesquisada, especifique a primeira condição.</span><span class="sxs-lookup"><span data-stu-id="da5a0-122">In the **Filter** column for the first data column to search, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="da5a0-123">Na coluna **Filtro** da segunda coluna de dados, especifique a segunda condição.</span><span class="sxs-lookup"><span data-stu-id="da5a0-123">In the **Filter** column for the second data column, specify the second condition.</span></span>  
  
     <span data-ttu-id="da5a0-124">O Designer de Consulta e Exibição cria uma cláusula WHERE que contém uma condição AND, igual a:</span><span class="sxs-lookup"><span data-stu-id="da5a0-124">The Query and View Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
    ```  
    SELECT pub_id, title  
    FROM titles  
    WHERE (pub_id = '0877') AND (title LIKE '%Cook%')  
    ```  
  
4.  <span data-ttu-id="da5a0-125">Repita as etapas 2 e 3 para cada condição adicional que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="da5a0-125">Repeat Steps 2 and 3 for each additional condition you want to add.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5a0-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da5a0-126">See Also</span></span>  
 <span data-ttu-id="da5a0-127">[Combine condições quando AND tem precedência &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="da5a0-127">[Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-and-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="da5a0-128">[Combinar condições quando ou tem precedência &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="da5a0-128">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="da5a0-129">[Convenções para combinar critérios de pesquisa no painel critérios &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="da5a0-129">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="da5a0-130">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="da5a0-130">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
