---
title: Classificar Linhas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- sorting rows [SQL Server]
- sorting query results [SQL Server]
ms.assetid: 780ef467-f96e-4373-8235-6dacbedb05a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4939c08a4be8c6a7aa3a52d55928abe077f25d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683876"
---
# <a name="sort-rows-visual-database-tools"></a><span data-ttu-id="4e7d2-102">Classificar linhas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4e7d2-102">Sort Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="4e7d2-103">Você pode classificar linhas em um resultado de consulta.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-103">You can order the rows in a query result.</span></span> <span data-ttu-id="4e7d2-104">Isto é, você pode nomear uma coluna particular ou conjunto de colunas cujos valores determinam a classificação das linhas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-104">That is, you can name a particular column or set of columns whose values determine the order of rows in the result set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e7d2-105">A ordem de classificação é determinada em parte pela sequência de ordenação da coluna.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-105">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="4e7d2-106">Você pode alterar a sequência de ordenação na [Caixa de Diálogo de Ordenação](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4e7d2-106">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="4e7d2-107">Existem vários modos onde você pode classificar resultados de consulta:</span><span class="sxs-lookup"><span data-stu-id="4e7d2-107">There are several ways in which you can sort query results:</span></span>  
  
-   <span data-ttu-id="4e7d2-108">**Você pode organizar linhas em ordem crescente ou decrescente** . Por padrão, o SQL usa colunas classificar por para organizar linhas em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-108">**You can arrange rows in ascending or descending order** By default, SQL uses order-by columns to arrange rows in ascending order.</span></span> <span data-ttu-id="4e7d2-109">Por exemplo, para organizar os títulos de livros por preço crescente, simplesmente classifique as linhas pela coluna de preço.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-109">For example, to arrange the book titles by ascending price, simply sort the rows by the price column.</span></span> <span data-ttu-id="4e7d2-110">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="4e7d2-110">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price  
  
    ```  
  
     <span data-ttu-id="4e7d2-111">Por outro lado, se você quiser organizar os títulos com os livros mais caros primeiro, você poderá especificar expressamente uma classificação de primeiro os mais caros.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-111">On the other hand, if you want to arrange the titles with the more expensive books first, you can explicitly specify a highest-first ordering.</span></span> <span data-ttu-id="4e7d2-112">Isto é, você indica se as linhas de resultado devem ser organizadas pelos valores decrescentes da coluna de preço.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-112">That is, you indicate that the result rows should be arranged by descending values of the price column.</span></span> <span data-ttu-id="4e7d2-113">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="4e7d2-113">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="4e7d2-114">**Você pode fazer a classificação por várias colunas** .   Por exemplo, você pode criar um conjunto de resultados com uma linha para cada autor, classificando primeiro por estado e, em seguida, por cidade.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-114">**You can sort by multiple columns** For example, you can create a result set with one row for each author, ordering first by state and then by city.</span></span> <span data-ttu-id="4e7d2-115">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="4e7d2-115">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM authors   
    ORDER BY state, city  
  
    ```  
  
-   <span data-ttu-id="4e7d2-116">**Você pode classificar por colunas que não aparecem no conjunto de resultados** .   Por exemplo, você pode criar um conjunto de resultados com os títulos mais caros primeiro, mesmo se os preços não aparecerem.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-116">**You can sort by columns not appearing in the result set** For example, you can create a result set with the most expensive titles first, even though the prices do not appear.</span></span> <span data-ttu-id="4e7d2-117">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="4e7d2-117">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title_id, title  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="4e7d2-118">**Você pode classificar por colunas derivadas**. Por exemplo, crie um conjunto de resultados no qual cada linha contenha um título de livro, com os livros que pagam os royalties mais altos por cópia aparecendo primeiro.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-118">**You can sort by derived columns** For example, you can create a result set in which each row contains a book title - with the books that pay the highest royalty per copy appearing first.</span></span> <span data-ttu-id="4e7d2-119">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="4e7d2-119">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title, price * royalty / 100 as royalty_per_unit  
    FROM titles  
    ORDER BY royalty_per_unit DESC  
  
    ```  
  
     <span data-ttu-id="4e7d2-120">(A fórmula para calcular royalty que cada livro ganha por cópia está destacada.)</span><span class="sxs-lookup"><span data-stu-id="4e7d2-120">(The formula for calculating the royalty that each book earns per copy is emphasized.)</span></span>  
  
     <span data-ttu-id="4e7d2-121">Para calcular uma coluna derivada, você pode usar sintaxe SQL, como no exemplo anterior, ou pode usar uma função definida pelo usuário que retorna um valor escalar.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-121">To calculate a derived column, you can use SQL syntax, as in the preceding example, or you can use a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="4e7d2-122">Para obter mais informações sobre funções definidas pelo usuário, consulte a documentação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-122">For more information about user-defined functions, see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="4e7d2-123">**Você pode classificar linhas agrupadas**. Por exemplo, crie um conjunto de resultados em que cada linha descreva uma cidade, mais o número de autores naquela cidade – com as cidades contendo muitos autores que aparecem primeiro.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-123">**You can sort grouped rows** For example; you can create a result set in which each row describes a city, plus the number of authors in that city - with the cities containing many authors appearing first.</span></span> <span data-ttu-id="4e7d2-124">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="4e7d2-124">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    ORDER BY COUNT(*) DESC, state  
  
    ```  
  
     <span data-ttu-id="4e7d2-125">Observe que a consulta usa `state` como uma coluna de classificação secundária.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-125">Notice that the query uses `state` as a secondary sort column.</span></span> <span data-ttu-id="4e7d2-126">Assim, se dois estados tiverem o mesmo número de autores, esses estados aparecerão em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-126">Thus, if two states have the same number of authors, those states will appear in alphabetical order.</span></span>  
  
-   <span data-ttu-id="4e7d2-127">**Você pode classificar usando dados internacionais** .   Isto é, você pode classificar uma coluna usando convenções de exame que diferem das convenções padrão daquela coluna.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-127">**You can sort using international data** That is; you can sort a column using collating conventions that differ from the default conventions for that column.</span></span> <span data-ttu-id="4e7d2-128">Por exemplo, você pode escrever uma consulta que recupera todos os títulos de livros de Jaime Pati? minúscula.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-128">For example, you can write a query that retrieves all the book titles by Jaime Pati??o.</span></span> <span data-ttu-id="4e7d2-129">Para exibir os títulos em ordem alfabética, você usa uma sequência de exame espanhol para a coluna de título.</span><span class="sxs-lookup"><span data-stu-id="4e7d2-129">To display the titles in alphabetical order, you use a Spanish collating sequence for the title column.</span></span> <span data-ttu-id="4e7d2-130">O SQL resultante pode ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="4e7d2-130">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title  
    FROM   
        authors   
        INNER JOIN   
            titleauthor   
            ON authors.au_id   
            =  titleauthor.au_id   
            INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
    WHERE   
         au_fname = 'Jaime' AND   
         au_lname = 'Pati??o'  
    ORDER BY   
         title COLLATE SQL_Spanish_Pref_CP1_CI_AS  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4e7d2-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e7d2-131">See Also</span></span>  
 <span data-ttu-id="4e7d2-132">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4e7d2-132">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4e7d2-133">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4e7d2-133">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
