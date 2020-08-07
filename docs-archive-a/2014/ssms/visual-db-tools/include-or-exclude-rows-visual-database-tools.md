---
title: Incluir ou excluir linhas (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- included rows
- search conditions [SQL Server], HAVING clause
- search criteria [SQL Server], including rows
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- search conditions [SQL Server], WHERE clause
- row included in search [SQL Server]
- excluding rows
ms.assetid: ba4e1202-31a2-444d-8365-c68a530ef223
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7b2d31c51296fa73a503e59a14adb60d79a61178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574969"
---
# <a name="include-or-exclude-rows-visual-database-tools"></a><span data-ttu-id="4f8df-102">Incluir ou excluir linhas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4f8df-102">Include or Exclude Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="4f8df-103">Para restringir o número de linhas que uma consulta SELECT deve retornar, crie critérios de pesquisa ou de filtro.</span><span class="sxs-lookup"><span data-stu-id="4f8df-103">To restrict the number of rows a SELECT query should return, you create search conditions or filter criteria.</span></span> <span data-ttu-id="4f8df-104">No SQL, os critérios de pesquisa aparecem na cláusula WHERE da instrução, ou quando se está criando uma consulta de agregação na cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="4f8df-104">In SQL, search conditions appear in the WHERE clause of the statement, or if you are creating an aggregate query, in the HAVING clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f8df-105">É igualmente possível usar critérios de pesquisa para indicar quais linhas são afetadas por consultas Atualizar, Inserir Resultados, Inserir Valores, Excluir ou Criar Tabela.</span><span class="sxs-lookup"><span data-stu-id="4f8df-105">You can also use search conditions to indicate which rows are affected by an Update, Insert Results, Insert Values, Delete, or Make Table query.</span></span>  
  
 <span data-ttu-id="4f8df-106">Quando a consulta é executada, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] examina e aplica o critério de pesquisa a todas as linhas das tabelas que você está pesquisando.</span><span class="sxs-lookup"><span data-stu-id="4f8df-106">When the query runs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] examines and applies the search condition to each row in the tables you are searching.</span></span> <span data-ttu-id="4f8df-107">Se a linha atender aos critérios, será incluída na consulta.</span><span class="sxs-lookup"><span data-stu-id="4f8df-107">If the row meets the condition, it is included in the query.</span></span> <span data-ttu-id="4f8df-108">Por exemplo, um critério de pesquisa que localizasse todos os funcionários de uma determinada região poderia ser:</span><span class="sxs-lookup"><span data-stu-id="4f8df-108">For example, a search condition that would find all the employees in a particular region might be:</span></span>  
  
```  
region = 'UK'  
```  
  
 <span data-ttu-id="4f8df-109">Para estabelecer os critérios de inclusão de linhas em resultado, vários critérios de pesquisa podem ser utilizados.</span><span class="sxs-lookup"><span data-stu-id="4f8df-109">To establish the criteria for including a row in a result, you can use multiple search conditions.</span></span> <span data-ttu-id="4f8df-110">Por exemplo, o critério de pesquisa a seguir consiste em dois critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4f8df-110">For example, the following search criterion consists of two search conditions.</span></span> <span data-ttu-id="4f8df-111">A consulta incluirá uma linha no conjunto de resultados apenas se aquela linha atender às condições.</span><span class="sxs-lookup"><span data-stu-id="4f8df-111">The query includes a row in the result set only if that row satisfies both of the conditions.</span></span>  
  
```  
region = 'UK' AND product_line = 'Housewares'  
```  
  
 <span data-ttu-id="4f8df-112">Você pode combinar essas condições com AND ou OR.</span><span class="sxs-lookup"><span data-stu-id="4f8df-112">You can combine these conditions with AND or OR.</span></span> <span data-ttu-id="4f8df-113">O exemplo anterior utiliza AND.</span><span class="sxs-lookup"><span data-stu-id="4f8df-113">The previous example uses AND.</span></span> <span data-ttu-id="4f8df-114">Por outro lado, o critério a seguir usa OR.</span><span class="sxs-lookup"><span data-stu-id="4f8df-114">In contrast, the following criterion uses OR.</span></span> <span data-ttu-id="4f8df-115">O conjunto de resultados incluirá todas as linhas que atenderem um ou outro ou a ambos os critérios de pesquisa:</span><span class="sxs-lookup"><span data-stu-id="4f8df-115">The result set will include any row that satisfies either or both of the search conditions:</span></span>  
  
```  
region = 'UK' OR product_line = 'Housewares'  
```  
  
 <span data-ttu-id="4f8df-116">É possível combinar critérios de pesquisa até mesmo em uma única coluna.</span><span class="sxs-lookup"><span data-stu-id="4f8df-116">You can even combine search conditions on a single column.</span></span> <span data-ttu-id="4f8df-117">Por exemplo, o critério seguinte combina duas condições na coluna de região:</span><span class="sxs-lookup"><span data-stu-id="4f8df-117">For example, the following criterion combines two conditions on the region column:</span></span>  
  
```  
region = 'UK' OR region = 'US'  
```  
  
 <span data-ttu-id="4f8df-118">Para obter detalhes sobre como combinar critérios de pesquisa, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="4f8df-118">For details about combining search conditions, see the following topics:</span></span>  
  
-   [<span data-ttu-id="4f8df-119">Convenções para combinar critérios de pesquisa no painel Critérios &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4f8df-119">Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;</span></span>](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
  
-   [<span data-ttu-id="4f8df-120">Especificar vários critérios de pesquisa para uma coluna &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4f8df-120">Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
-   [<span data-ttu-id="4f8df-121">Especificar vários critérios de pesquisa para várias colunas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4f8df-121">Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;</span></span>](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md)  
  
-   [<span data-ttu-id="4f8df-122">Combinar condições quando AND tem precedência &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4f8df-122">Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-and-has-precedence-visual-database-tools.md)  
  
-   [<span data-ttu-id="4f8df-123">Combinar condições quando OR tem precedência &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4f8df-123">Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
  
## <a name="examples"></a><span data-ttu-id="4f8df-124">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4f8df-124">Examples</span></span>  
 <span data-ttu-id="4f8df-125">A seguir, alguns exemplos de consultas que usam vários operadores e critérios de linha:</span><span class="sxs-lookup"><span data-stu-id="4f8df-125">Here are some examples of queries using various operators and row criteria:</span></span>  
  
-   <span data-ttu-id="4f8df-126">**Literal** Valor de texto único, numérico, de data ou lógico.</span><span class="sxs-lookup"><span data-stu-id="4f8df-126">**Literal** A single text, numeric, date, or logical value.</span></span> <span data-ttu-id="4f8df-127">O exemplo a seguir utiliza um literal para localizar todas as linhas de funcionários do Reino Unido:</span><span class="sxs-lookup"><span data-stu-id="4f8df-127">The following example uses a literal to find all rows for employees in the United Kingdom:</span></span>  
  
    ```  
    WHERE region = 'UK'  
    ```  
  
-   <span data-ttu-id="4f8df-128">**Referência de coluna** Compara os valores de uma coluna com os valores de outra.</span><span class="sxs-lookup"><span data-stu-id="4f8df-128">**Column reference** Compares the values in one column with the values in another.</span></span> <span data-ttu-id="4f8df-129">O exemplo a seguir pesquisa uma tabela de `products` para todas as linhas nas quais o valor do custo de produção seja inferior ao custo de remessa:</span><span class="sxs-lookup"><span data-stu-id="4f8df-129">The following example searches a `products` table for all rows in which the value of the production cost is lower than the shipping cost:</span></span>  
  
    ```  
    WHERE prod_cost < ship_cost  
    ```  
  
-   <span data-ttu-id="4f8df-130">**Função** Referência a uma função que um back-end de banco de dados pode resolver para calcular o valor da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4f8df-130">**Function** A reference to a function that the database back-end can resolve to calculate a value for the search.</span></span> <span data-ttu-id="4f8df-131">A função pode ser uma função definida pelo servidor de banco de dados ou uma função definida pelo usuário que retorne um valor escalar.</span><span class="sxs-lookup"><span data-stu-id="4f8df-131">The function can be a function defined by the database server or a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="4f8df-132">O exemplo seguinte pesquisa os pedidos feitos hoje (a função GETDATE( ) retorna dados atuais):</span><span class="sxs-lookup"><span data-stu-id="4f8df-132">The following example searches for orders placed today (the GETDATE( ) function returns the current date):</span></span>  
  
    ```  
    WHERE order_date = GETDATE()  
    ```  
  
-   <span data-ttu-id="4f8df-133">**NULL** O exemplo seguinte pesquisa uma tabela `authors` de todos os autores que têm um nome no arquivo:</span><span class="sxs-lookup"><span data-stu-id="4f8df-133">**NULL** The following example searches an `authors` table for all authors who have a first name on file:</span></span>  
  
    ```  
    WHERE au_fname IS NOT NULL  
    ```  
  
-   <span data-ttu-id="4f8df-134">**Cálculo** O resultado de um cálculo que pode envolver literais, referências de coluna ou outras expressões.</span><span class="sxs-lookup"><span data-stu-id="4f8df-134">**Calculation** The result of a calculation that can involve literals, column references, or other expressions.</span></span> <span data-ttu-id="4f8df-135">O exemplo seguinte pesquisa uma tabela de `products` para localizar todas as linhas nas quais o preço de vendas no varejo é superior a duas vezes o custo de produção:</span><span class="sxs-lookup"><span data-stu-id="4f8df-135">The following example searches a `products` table to find all rows in which the retail sales price is more than twice the production cost:</span></span>  
  
    ```  
    WHERE sales_price > (prod_cost * 2)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4f8df-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f8df-136">See Also</span></span>  
 <span data-ttu-id="4f8df-137">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4f8df-137">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="4f8df-138">[Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4f8df-138">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4f8df-139">Consultar com parâmetros &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4f8df-139">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
