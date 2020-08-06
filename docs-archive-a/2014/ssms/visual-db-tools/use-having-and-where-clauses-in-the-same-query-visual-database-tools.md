---
title: Usar cláusulas HAVING e WHERE na mesma consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- search conditions [SQL Server], HAVING clause
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- HAVING clause, search criteria
- search conditions [SQL Server], WHERE clause
- WHERE clause, search criteria
- excluding rows
ms.assetid: 1e07cf56-b4b7-4c49-8ddd-c276812a7148
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f6b471a60bf225ee61bdbbf0ecec30f21a92cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679119"
---
# <a name="use-having-and-where-clauses-in-the-same-query-visual-database-tools"></a><span data-ttu-id="fbe29-102">Usar cláusulas HAVING e WHERE na mesma consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fbe29-102">Use HAVING and WHERE Clauses in the Same Query (Visual Database Tools)</span></span>
  <span data-ttu-id="fbe29-103">Em algumas instâncias, talvez você deseje excluir linhas individuais de grupos (usando uma cláusula WHERE) antes de aplicar um critério aos grupos como um todo (usando uma cláusula HAVING).</span><span class="sxs-lookup"><span data-stu-id="fbe29-103">In some instances, you might want to exclude individual rows from groups (using a WHERE clause) before applying a condition to groups as a whole (using a HAVING clause).</span></span>  
  
 <span data-ttu-id="fbe29-104">Uma cláusula HAVING é como uma cláusula WHERE, a diferença é que ela se aplica somente a grupos como um todo (ou seja, as linhas do conjunto de resultados que representam grupos), enquanto a cláusula WHERE se aplica a linhas individuais.</span><span class="sxs-lookup"><span data-stu-id="fbe29-104">A HAVING clause is like a WHERE clause, but applies only to groups as a whole (that is, to the rows in the result set representing groups), whereas the WHERE clause applies to individual rows.</span></span> <span data-ttu-id="fbe29-105">Uma consulta pode conter uma cláusula WHERE e uma cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="fbe29-105">A query can contain both a WHERE clause and a HAVING clause.</span></span> <span data-ttu-id="fbe29-106">Nesse caso:</span><span class="sxs-lookup"><span data-stu-id="fbe29-106">In that case:</span></span>  
  
-   <span data-ttu-id="fbe29-107">A cláusula WHERE é aplicada primeiro às linhas individuais nas tabelas ou objetos com valor de tabela no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="fbe29-107">The WHERE clause is applied first to the individual rows in the tables or table-valued objects in the Diagram pane.</span></span> <span data-ttu-id="fbe29-108">Apenas as linhas que atendem os critérios na cláusula WHERE são agrupadas.</span><span class="sxs-lookup"><span data-stu-id="fbe29-108">Only the rows that meet the conditions in the WHERE clause are grouped.</span></span>  
  
-   <span data-ttu-id="fbe29-109">A cláusula HAVING é aplicada às linhas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="fbe29-109">The HAVING clause is then applied to the rows in the result set.</span></span> <span data-ttu-id="fbe29-110">Somente os grupos que atendem os critérios de HAVING são exibidos na saída da consulta.</span><span class="sxs-lookup"><span data-stu-id="fbe29-110">Only the groups that meet the HAVING conditions appear in the query output.</span></span> <span data-ttu-id="fbe29-111">Você pode aplicar apenas uma cláusula HAVING em colunas que também são exibidas na cláusula GROUP BY ou em uma função de agregação.</span><span class="sxs-lookup"><span data-stu-id="fbe29-111">You can apply a HAVING clause only to columns that also appear in the GROUP BY clause or in an aggregate function.</span></span>  
  
 <span data-ttu-id="fbe29-112">Por exemplo, imagine que você está unindo as tabelas `titles` e `publishers` para criar uma consulta que mostra o preço médio do livro de um conjunto de editoras.</span><span class="sxs-lookup"><span data-stu-id="fbe29-112">For example, imagine that you are joining the `titles` and `publishers` tables to create a query showing the average book price for a set of publishers.</span></span> <span data-ttu-id="fbe29-113">Você quer ver o preço médio de um único conjunto específico de editoras, talvez somente as editoras no estado da Califórnia.</span><span class="sxs-lookup"><span data-stu-id="fbe29-113">You want to see the average price for only a specific set of publishers - perhaps only the publishers in the state of California.</span></span> <span data-ttu-id="fbe29-114">Além disso, desejar ver o preço médio apenas se estiver acima de R$ 10,00.</span><span class="sxs-lookup"><span data-stu-id="fbe29-114">And even then, you want to see the average price only if it is over $10.00.</span></span>  
  
 <span data-ttu-id="fbe29-115">Você pode definir o primeiro critério incluindo uma cláusula WHERE, que descarta todas as editoras que não estejam na Califórnia, antes de calcular os preços médios.</span><span class="sxs-lookup"><span data-stu-id="fbe29-115">You can establish the first condition by including a WHERE clause, which discards any publishers that are not in California, before calculating average prices.</span></span> <span data-ttu-id="fbe29-116">O segundo critério requer uma cláusula HAVING, porque o critério está baseado nos resultados de agrupamento e resumo dos dados.</span><span class="sxs-lookup"><span data-stu-id="fbe29-116">The second condition requires a HAVING clause, because the condition is based on the results of grouping and summarizing the data.</span></span> <span data-ttu-id="fbe29-117">A instrução SQL resultante se parecerá com esta:</span><span class="sxs-lookup"><span data-stu-id="fbe29-117">The resulting SQL statement might look like this:</span></span>  
  
```  
SELECT titles.pub_id, AVG(titles.price)  
FROM titles INNER JOIN publishers  
   ON titles.pub_id = publishers.pub_id  
WHERE publishers.state = 'CA'  
GROUP BY titles.pub_id  
HAVING AVG(price) > 10  
```  
  
 <span data-ttu-id="fbe29-118">Você pode criar cláusulas HAVING e WHERE no painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="fbe29-118">You can create both HAVING and WHERE clauses in the Criteria pane.</span></span> <span data-ttu-id="fbe29-119">Por padrão, se você especificar um critério de pesquisa para uma coluna, o critério se tornará parte da cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="fbe29-119">By default, if you specify a search condition for a column, the condition becomes part of the HAVING clause.</span></span> <span data-ttu-id="fbe29-120">Porém, você pode alterar o critério para ser uma cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="fbe29-120">However, you can change the condition to be a WHERE clause.</span></span>  
  
 <span data-ttu-id="fbe29-121">Você pode criar uma cláusula WHERE e uma cláusula HAVING envolvendo a mesma coluna.</span><span class="sxs-lookup"><span data-stu-id="fbe29-121">You can create a WHERE clause and HAVING clause involving the same column.</span></span> <span data-ttu-id="fbe29-122">Para fazer isso, você deve adicionar a coluna duas vezes ao painel Critérios e, depois, especificar uma instância como parte da cláusula HAVING e a outra instância como parte da cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="fbe29-122">To do so, you must add the column twice to the Criteria pane, then specify one instance as part of the HAVING clause and the other instance as part of the WHERE clause.</span></span>  
  
### <a name="to-specify-a-where-condition-in-an-aggregate-query"></a><span data-ttu-id="fbe29-123">Para especificar um critério WHERE em uma consulta de agregação</span><span class="sxs-lookup"><span data-stu-id="fbe29-123">To specify a WHERE condition in an aggregate query</span></span>  
  
1.  <span data-ttu-id="fbe29-124">Especifique os grupos para a sua consulta.</span><span class="sxs-lookup"><span data-stu-id="fbe29-124">Specify the groups for your query.</span></span> <span data-ttu-id="fbe29-125">Para obter detalhes, veja [Agrupar linhas em resultados da consulta &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fbe29-125">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="fbe29-126">Se já não estiver no painel Critérios, adicione a coluna na qual você deseja basear o critério WHERE.</span><span class="sxs-lookup"><span data-stu-id="fbe29-126">If it is not already in the Criteria pane, add the column on which you want to base the WHERE condition.</span></span>  
  
3.  <span data-ttu-id="fbe29-127">Limpe a coluna **Saída** , a menos que a coluna de dados faça parte da cláusula GROUP BY ou esteja incluída em uma função de agregação.</span><span class="sxs-lookup"><span data-stu-id="fbe29-127">Clear the **Output** column unless the data column is part of the GROUP BY clause or included in an aggregate function.</span></span>  
  
4.  <span data-ttu-id="fbe29-128">Na coluna **Filtro** , especifique o critério WHERE.</span><span class="sxs-lookup"><span data-stu-id="fbe29-128">In the **Filter** column, specify the WHERE condition.</span></span> <span data-ttu-id="fbe29-129">O Designer de Consulta e Exibição adiciona o critério à cláusula HAVING da instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="fbe29-129">The Query and View Designer adds the condition to the HAVING clause of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fbe29-130">A consulta mostrada no exemplo para esse procedimento une duas tabelas, `titles` e `publishers`.</span><span class="sxs-lookup"><span data-stu-id="fbe29-130">The query shown in the example for this procedure joins two tables, `titles` and `publishers`.</span></span>  
  
     <span data-ttu-id="fbe29-131">Neste momento da consulta, a instrução SQL contém uma cláusula HAVING:</span><span class="sxs-lookup"><span data-stu-id="fbe29-131">At this point in the query, the SQL statement contains a HAVING clause:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    GROUP BY titles.pub_id  
    HAVING publishers.state = 'CA'  
    ```  
  
5.  <span data-ttu-id="fbe29-132">Na coluna **Agrupar por** , selecione **Where** na lista de opções de grupo e resumo.</span><span class="sxs-lookup"><span data-stu-id="fbe29-132">In the **Group By** column, select **Where** from the list of group and summary options.</span></span> <span data-ttu-id="fbe29-133">O Designer de Consulta e Exibição remove o critério da cláusula HAVING na instrução SQL e a adiciona à cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="fbe29-133">The Query and View Designer removes the condition from the HAVING clause in the SQL statement and adds it to the WHERE clause.</span></span>  
  
     <span data-ttu-id="fbe29-134">A instrução SQL é alterada para incluir uma cláusula WHERE em vez de:</span><span class="sxs-lookup"><span data-stu-id="fbe29-134">The SQL statement changes to include a WHERE clause instead:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    WHERE publishers.state = 'CA'  
    GROUP BY titles.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fbe29-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fbe29-135">See Also</span></span>  
 <span data-ttu-id="fbe29-136">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="fbe29-136">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="fbe29-137">Resumir resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fbe29-137">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
