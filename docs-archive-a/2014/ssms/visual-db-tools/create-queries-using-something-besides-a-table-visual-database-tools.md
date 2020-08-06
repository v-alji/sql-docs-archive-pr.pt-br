---
title: Criar consultas usando algo além de uma tabela (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- user-defined functions [SQL Server], queries
- queries [SQL Server], creating
ms.assetid: 8e4a1f0a-8a42-4733-be8d-e21d6dbddb33
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0444c20fe10080949930f23623d5699f7fd3712c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569004"
---
# <a name="create-queries-using-something-besides-a-table-visual-database-tools"></a><span data-ttu-id="5dd82-102">Criar consultas usando algo além de uma tabela (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="5dd82-102">Create Queries using Something Besides a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="5dd82-103">Sempre que você escreve uma consulta de recuperação, você articula as colunas e as linhas que você quer, e onde o processador de consulta deve procurar os dados originais.</span><span class="sxs-lookup"><span data-stu-id="5dd82-103">Whenever you write a retrieval query, you articulate what columns you want, what rows you want, and where the query processor should find the original data.</span></span> <span data-ttu-id="5dd82-104">Tipicamente, esses dados originais consistem em uma tabela ou várias tabelas unidas.</span><span class="sxs-lookup"><span data-stu-id="5dd82-104">Typically, this original data consists of a table or several tables joined together.</span></span> <span data-ttu-id="5dd82-105">Mas os dados originais podem vir de fontes diferentes de tabelas.</span><span class="sxs-lookup"><span data-stu-id="5dd82-105">But the original data can come from sources other than tables.</span></span> <span data-ttu-id="5dd82-106">Na realidade, podem vir de exibições, consultas, sinônimos ou funções definidas pelo usuário que retornam uma tabela.</span><span class="sxs-lookup"><span data-stu-id="5dd82-106">In fact, it can come from views, queries, synonyms, or user-defined functions that return a table.</span></span>  
  
## <a name="using-a-view-in-place-of-a-table"></a><span data-ttu-id="5dd82-107">Usando uma exibição no lugar de uma tabela</span><span class="sxs-lookup"><span data-stu-id="5dd82-107">Using a View in Place of a Table</span></span>  
 <span data-ttu-id="5dd82-108">Você pode selecionar linhas de uma exibição.</span><span class="sxs-lookup"><span data-stu-id="5dd82-108">You can select rows from a view.</span></span> <span data-ttu-id="5dd82-109">Por exemplo, suponha que o banco de dados inclui uma exibição chamada "ExpensiveBooks" na qual cada linha descreve um título cujo preço excede 19,99.</span><span class="sxs-lookup"><span data-stu-id="5dd82-109">For example, suppose the database includes a view called "ExpensiveBooks," in which each row describes a title whose price exceeds 19.99.</span></span> <span data-ttu-id="5dd82-110">A definição da exibição pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="5dd82-110">The view definition might look like this:</span></span>  
  
```  
SELECT *  
FROM titles  
WHERE price > 19.99  
  
```  
  
 <span data-ttu-id="5dd82-111">Você pode selecionar os livros caros de psicologia selecionando apenas os livros de psicologia da exibição ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="5dd82-111">You can select the expensive psychology books merely by selecting the psychology books from the ExpensiveBooks view.</span></span> <span data-ttu-id="5dd82-112">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="5dd82-112">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM ExpensiveBooks  
WHERE type = 'psychology'  
  
```  
  
 <span data-ttu-id="5dd82-113">Semelhantemente, uma exibição pode participar de uma operação JOIN.</span><span class="sxs-lookup"><span data-stu-id="5dd82-113">Similarly, a view can participate in a JOIN operation.</span></span> <span data-ttu-id="5dd82-114">Por exemplo, você pode achar as vendas de livros caros unindo somente a tabela de vendas à exibição ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="5dd82-114">For example, you can find the sales of expensive books merely by joining the sales table to the ExpensiveBooks view.</span></span> <span data-ttu-id="5dd82-115">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="5dd82-115">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM sales   
         INNER JOIN   
         ExpensiveBooks   
         ON sales.title_id   
         =  ExpensiveBooks.title_id  
  
```  
  
 <span data-ttu-id="5dd82-116">Para obter mais informações sobre como adicionar um modo de exibição a uma consulta, veja [Adicionar tabelas a consultas &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5dd82-116">For more information about adding a view to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-query-in-place-of-a-table"></a><span data-ttu-id="5dd82-117">Usando uma consulta no lugar de uma tabela</span><span class="sxs-lookup"><span data-stu-id="5dd82-117">Using a Query in Place of a Table</span></span>  
 <span data-ttu-id="5dd82-118">Você pode selecionar linhas de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="5dd82-118">You can select rows from a query.</span></span> <span data-ttu-id="5dd82-119">Por exemplo, suponha você já escreveu uma consulta que recupera títulos e identificadores dos livros de coautoria, ou seja, livros com mais de um autor.</span><span class="sxs-lookup"><span data-stu-id="5dd82-119">For example, suppose you have already written a query retrieving titles and identifiers of the coauthored books - the books with more than one author.</span></span> <span data-ttu-id="5dd82-120">O SQL pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="5dd82-120">The SQL might look like this:</span></span>  
  
```  
SELECT   
     titles.title_id, title, type  
FROM   
     titleauthor   
         INNER JOIN  
         titles   
         ON titleauthor.title_id   
         =  titles.title_id   
GROUP BY   
     titles.title_id, title, type  
HAVING COUNT(*) > 1  
  
```  
  
 <span data-ttu-id="5dd82-121">Depois, você pode escrever outra consulta compilada nesse resultado.</span><span class="sxs-lookup"><span data-stu-id="5dd82-121">You can then write another query that builds on this result.</span></span> <span data-ttu-id="5dd82-122">Por exemplo, é possível escrever uma consulta que recupera os livros de psicologia com coautoria.</span><span class="sxs-lookup"><span data-stu-id="5dd82-122">For example, you can write a query that retrieves the coauthored psychology books.</span></span> <span data-ttu-id="5dd82-123">Para escrever essa consulta nova, você pode usar a consulta existente como fonte de dados da nova consulta.</span><span class="sxs-lookup"><span data-stu-id="5dd82-123">To write this new query, you can use the existing query as the source of the new query's data.</span></span> <span data-ttu-id="5dd82-124">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="5dd82-124">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    title  
FROM   
    (  
    SELECT   
        titles.title_id,   
        title,   
        type  
    FROM   
        titleauthor   
            INNER JOIN  
            titles   
            ON titleauthor.title_id   
            =  titles.title_id   
    GROUP BY   
        titles.title_id,   
        title,   
        type  
    HAVING COUNT(*) > 1  
    )   
    co_authored_books  
WHERE     type = 'psychology'  
  
```  
  
 <span data-ttu-id="5dd82-125">O texto enfatizado mostra a consulta existente usada como fonte de dados da nova consulta.</span><span class="sxs-lookup"><span data-stu-id="5dd82-125">The emphasized text shows the existing query used as the source of the new query's data.</span></span> <span data-ttu-id="5dd82-126">Note que a nova consulta usa um alias ("co_authored_books") para a consulta existente.</span><span class="sxs-lookup"><span data-stu-id="5dd82-126">Note that the new query uses an alias ("co_authored_books") for the existing query.</span></span> <span data-ttu-id="5dd82-127">Para obter mais informações sobre aliases, consulte [Criar aliases de tabela &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) e [Criar aliases de coluna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5dd82-127">For more information about aliases, see [Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) and [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="5dd82-128">Da mesma forma, uma consulta pode participar de uma operação JOIN.</span><span class="sxs-lookup"><span data-stu-id="5dd82-128">Similarly, a query can participate in a JOIN operation.</span></span> <span data-ttu-id="5dd82-129">Por exemplo, você pode encontrar as vendas de livros caros com coautoria unindo somente a exibição ExpensiveBooks à consulta para recuperar a consulta de livros com coautoria.</span><span class="sxs-lookup"><span data-stu-id="5dd82-129">For example, you can find the sales of expensive coauthored books merely by joining the ExpensiveBooks view to the query retrieving the coauthored books.</span></span> <span data-ttu-id="5dd82-130">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="5dd82-130">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    ExpensiveBooks.title  
FROM   
    ExpensiveBooks   
        INNER JOIN  
        (  
        SELECT   
            titles.title_id,   
            title,   
            type  
        FROM   
            titleauthor   
                INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
        GROUP BY   
            titles.title_id,   
            title,   
            type  
        HAVING COUNT(*) > 1  
        )  
```  
  
 <span data-ttu-id="5dd82-131">Para obter mais informações sobre como adicionar uma consulta a uma consulta, veja [Adicionar tabelas a consultas &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5dd82-131">For more information about adding a query to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-user-defined-function-in-place-of-a-table"></a><span data-ttu-id="5dd82-132">Usando uma função definida pelo usuário no lugar de uma tabela</span><span class="sxs-lookup"><span data-stu-id="5dd82-132">Using a User-Defined Function in Place of a Table</span></span>  
 <span data-ttu-id="5dd82-133">No SQL Server 2000 ou superior, você pode criar uma função definida pelo usuário que retorna uma tabela.</span><span class="sxs-lookup"><span data-stu-id="5dd82-133">In SQL Server 2000 or higher, you can create a user-defined function that returns a table.</span></span> <span data-ttu-id="5dd82-134">Tais funções são úteis para executar lógica complexa ou de procedimento.</span><span class="sxs-lookup"><span data-stu-id="5dd82-134">Such functions are useful for performing complex or procedural logic.</span></span>  
  
 <span data-ttu-id="5dd82-135">Por exemplo, suponha que a tabela de funcionários contenha uma coluna adicional, employee.manager_emp_id, e que exista uma chave estrangeira de manager_emp_id a employee.emp_id.</span><span class="sxs-lookup"><span data-stu-id="5dd82-135">For example, suppose the employee table contains an additional column, employee.manager_emp_id, and that a foreign key exists from manager_emp_id to employee.emp_id.</span></span> <span data-ttu-id="5dd82-136">Dentro de cada linha da tabela de funcionários, a coluna manager_emp_id indica o chefe do funcionário.</span><span class="sxs-lookup"><span data-stu-id="5dd82-136">Within each row of the employee table, the manager_emp_id column indicates the employee's boss.</span></span> <span data-ttu-id="5dd82-137">Mais precisamente, indica a emp_id do chefe do funcionário.</span><span class="sxs-lookup"><span data-stu-id="5dd82-137">More precisely, it indicates the employee's boss's emp_id.</span></span> <span data-ttu-id="5dd82-138">Você pode criar uma função definida pelo usuário que retorna a tabela contendo uma linha para cada funcionário que trabalha em uma determinada hierarquia organizacional de gerenciamento de alto nível.</span><span class="sxs-lookup"><span data-stu-id="5dd82-138">You can create a user-defined function that returns a table containing one row for each employee working within a particular high-level manager's organizational hierarchy.</span></span> <span data-ttu-id="5dd82-139">Você pode chamar a função fn_GetWholeTeam e projetá-la para aceitar uma variável de entrada, ou seja, a emp_id do administrador cuja equipe você quer recuperar.</span><span class="sxs-lookup"><span data-stu-id="5dd82-139">You might call the function fn_GetWholeTeam, and design it to take an input variable - the emp_id of the manager whose team you want to retrieve.</span></span>  
  
 <span data-ttu-id="5dd82-140">Você pode escrever uma consulta que use a função fn_GetWholeTeam como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5dd82-140">You can write a query that uses the fn_GetWholeTeam function as a source of data.</span></span> <span data-ttu-id="5dd82-141">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="5dd82-141">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *   
FROM   
     fn_GetWholeTeam ('VPA30890F')  
  
```  
  
 <span data-ttu-id="5dd82-142">"VPA30890F" é a emp_id do gerente cuja organização você quer recuperar.</span><span class="sxs-lookup"><span data-stu-id="5dd82-142">"VPA30890F" is the emp_id of the manager whose organization you want to retrieve.</span></span> <span data-ttu-id="5dd82-143">Para obter mais informações sobre como adicionar uma função definida pelo usuário a uma consulta, veja [Adicionar tabelas a consultas &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5dd82-143">For more information about adding a user-defined function to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="5dd82-144">Para uma descrição completa de funções definidas pelo usuário, consulte [Funções definidas pelo usuário](../../relational-databases/user-defined-functions/user-defined-functions.md).</span><span class="sxs-lookup"><span data-stu-id="5dd82-144">For a complete description of user-defined functions, see [User-Defined Functions](../../relational-databases/user-defined-functions/user-defined-functions.md).</span></span>  
  
  
