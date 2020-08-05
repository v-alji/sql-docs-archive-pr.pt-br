---
title: Especificar vários critérios de pesquisa para uma coluna (Visual Database Tools) | Microsoft Docs
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
ms.assetid: 2c006e36-56b1-4992-89b4-c6c0b19808f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a07322120bd3b3f543e6f54fa50cdf75aa32be59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573357"
---
# <a name="specify-multiple-search-conditions-for-one-column-visual-database-tools"></a><span data-ttu-id="70918-102">Especificar várias condições de pesquisa para uma coluna (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="70918-102">Specify Multiple Search Conditions for One Column (Visual Database Tools)</span></span>
  <span data-ttu-id="70918-103">Em algumas instâncias, você pode querer aplicar vários critérios de pesquisa à mesma coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="70918-103">In some instances, you might want to apply a number of search conditions to the same data column.</span></span> <span data-ttu-id="70918-104">Por exemplo, você pode querer:</span><span class="sxs-lookup"><span data-stu-id="70918-104">For example, you might want to:</span></span>  
  
-   <span data-ttu-id="70918-105">Pesquisar vários nomes diferentes em uma tabela `employee` ou funcionários que estejam em faixas salariais diferentes.</span><span class="sxs-lookup"><span data-stu-id="70918-105">Search for several different names in an `employee` table or for employees who are in different salary ranges.</span></span> <span data-ttu-id="70918-106">Esse tipo de pesquisa requer um critério OR.</span><span class="sxs-lookup"><span data-stu-id="70918-106">This type of search requires an OR condition.</span></span>  
  
-   <span data-ttu-id="70918-107">Pesquisar o título de um livro que começa com a palavra “O” e tenha a palavra “Cozinheiro”.</span><span class="sxs-lookup"><span data-stu-id="70918-107">Search for a book title that both starts with the word "The" and contains the word "Cook."</span></span> <span data-ttu-id="70918-108">Esse tipo de pesquisa requer um critério AND.</span><span class="sxs-lookup"><span data-stu-id="70918-108">This type of search requires an AND condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70918-109">As informações neste tópico se aplicam a critérios de pesquisa nas cláusulas WHERE e HAVING de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="70918-109">The information in this topic applies to search conditions in both the WHERE and HAVING clauses of a query.</span></span> <span data-ttu-id="70918-110">Os exemplos se concentram em como criar cláusulas WHERE, mas os princípios se aplicam a ambos os tipos de critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="70918-110">The examples focus on creating WHERE clauses, but the principles apply to both types of search conditions.</span></span>  
  
 <span data-ttu-id="70918-111">Para pesquisar valores alternativos na mesma coluna de dados, você deve especificar um critério OR.</span><span class="sxs-lookup"><span data-stu-id="70918-111">To search for alternative values in the same data column, you specify an OR condition.</span></span> <span data-ttu-id="70918-112">Para pesquisar valores que atendem a diversos critérios, você deve especificar um critério AND.</span><span class="sxs-lookup"><span data-stu-id="70918-112">To search for values that meet several conditions, you specify an AND condition.</span></span>  
  
## <a name="specifying-an-or-condition"></a><span data-ttu-id="70918-113">Especificando um critério OR</span><span class="sxs-lookup"><span data-stu-id="70918-113">Specifying an OR Condition</span></span>  
 <span data-ttu-id="70918-114">O uso de um critério OR permite que você especifique vários valores alternativos a serem pesquisados em uma coluna.</span><span class="sxs-lookup"><span data-stu-id="70918-114">Using an OR condition enables you to specify several alternative values to search for in a column.</span></span> <span data-ttu-id="70918-115">Essa opção expande o escopo da pesquisa e pode retornar mais linhas que a pesquisa de um único valor.</span><span class="sxs-lookup"><span data-stu-id="70918-115">This option expands the scope of the search and can return more rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="70918-116">Geralmente, você pode usar o operador IN em vez de pesquisar vários valores na mesma coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="70918-116">You can often use the IN operator instead to search for multiple values in the same data column.</span></span>  
  
#### <a name="to-specify-an-or-condition"></a><span data-ttu-id="70918-117">Para especificar um critério OR</span><span class="sxs-lookup"><span data-stu-id="70918-117">To specify an OR condition</span></span>  
  
1.  <span data-ttu-id="70918-118">No [Painel Critérios](visual-database-tools.md), adicione a coluna a ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="70918-118">In the [Criteria Pane](visual-database-tools.md), add the column to search.</span></span>  
  
2.  <span data-ttu-id="70918-119">Na coluna **Filtro** da coluna de dados adicionada, especifique o primeiro critério.</span><span class="sxs-lookup"><span data-stu-id="70918-119">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="70918-120">Na coluna **Ou...** da mesma coluna de dados, especifique o segundo critério.</span><span class="sxs-lookup"><span data-stu-id="70918-120">In the **Or...** column for the same data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="70918-121">O Designer de Consulta e Exibição cria uma cláusula WHERE que contém um critério OR, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="70918-121">The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:</span></span>  
  
```  
SELECT fname, lname  
FROM employees  
WHERE (salary < 30000) OR (salary > 100000)  
```  
  
## <a name="specifying-an-and-condition"></a><span data-ttu-id="70918-122">Especificando um critério AND</span><span class="sxs-lookup"><span data-stu-id="70918-122">Specifying an AND Condition</span></span>  
 <span data-ttu-id="70918-123">O uso do critério AND permite que você especifique que os valores em uma coluna devem atender a dois (ou mais) critérios para a linha a ser incluída no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="70918-123">Using an AND condition enables you to specify that values in a column must meet two (or more) conditions for the row to be included in the result set.</span></span> <span data-ttu-id="70918-124">Essa opção restringe o escopo da pesquisa e geralmente retorna menos linhas que a pesquisa de um único valor.</span><span class="sxs-lookup"><span data-stu-id="70918-124">This option narrows the scope of the search and usually returns fewer rows than searching for a single value.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="70918-125">Se você estiver procurando um intervalo de valores, poderá usar o operador BETWEEN em vez de vincular dois critérios com AND.</span><span class="sxs-lookup"><span data-stu-id="70918-125">If you are searching for a range of values, you can use the BETWEEN operator instead of linking two conditions with AND.</span></span>  
  
#### <a name="to-specify-an-and-condition"></a><span data-ttu-id="70918-126">Para especificar um critério AND</span><span class="sxs-lookup"><span data-stu-id="70918-126">To specify an AND condition</span></span>  
  
1.  <span data-ttu-id="70918-127">No painel Critérios, adicione a coluna a ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="70918-127">In the Criteria pane, add the column to search.</span></span>  
  
2.  <span data-ttu-id="70918-128">Na coluna **Filtro** da coluna de dados adicionada, especifique o primeiro critério.</span><span class="sxs-lookup"><span data-stu-id="70918-128">In the **Filter** column for the data column you just added, specify the first condition.</span></span>  
  
3.  <span data-ttu-id="70918-129">Adicione a mesma coluna de dados no painel Critérios novamente, colocando-a em uma linha vazia da grade.</span><span class="sxs-lookup"><span data-stu-id="70918-129">Add the same data column to the Criteria pane again, placing it in an empty row of the grid.</span></span>  
  
4.  <span data-ttu-id="70918-130">Na coluna **Filtro** da segunda instância da coluna de dados, especifique o segundo critério.</span><span class="sxs-lookup"><span data-stu-id="70918-130">In the **Filter** column for the second instance of the data column, specify the second condition.</span></span>  
  
 <span data-ttu-id="70918-131">O Designer de Consulta e Exibição cria uma cláusula WHERE que contém um critério AND, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="70918-131">The Query Designer creates a WHERE clause that contains an AND condition such as the following:</span></span>  
  
```  
SELECT title_id, title  
FROM titles  
WHERE (title LIKE '%Cook%') AND   
  (title LIKE '%Recipe%')  
```  
  
## <a name="see-also"></a><span data-ttu-id="70918-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70918-132">See Also</span></span>  
 <span data-ttu-id="70918-133">[Convenções para combinar critérios de pesquisa no painel critérios &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="70918-133">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="70918-134">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="70918-134">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
