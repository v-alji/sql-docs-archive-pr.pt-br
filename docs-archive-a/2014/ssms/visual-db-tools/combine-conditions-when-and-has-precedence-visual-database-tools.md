---
title: Combinar condições quando AND tem precedência (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- combining search conditions
- AND, Criteria pane
ms.assetid: 450eb2eb-6ea3-405b-8dd2-1ff926c016e7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 917d5381bc83083ee1fa3c07375945c0908da521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678520"
---
# <a name="combine-conditions-when-and-has-precedence-visual-database-tools"></a><span data-ttu-id="90239-102">Combinar condições quando AND tem precedência (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="90239-102">Combine Conditions When AND Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="90239-103">Para combinar condições com AND, você adiciona a coluna duas vezes à consulta – uma vez para cada condição.</span><span class="sxs-lookup"><span data-stu-id="90239-103">To combine conditions with AND, you add the column to the query twice--once for each condition.</span></span> <span data-ttu-id="90239-104">Para combinar condições com OR, você coloca a primeira na coluna Filtro e as condições adicionais em uma coluna **Ou...** .</span><span class="sxs-lookup"><span data-stu-id="90239-104">To combine conditions with OR, you put the first one in the Filter column and additional conditions into an **Or...** column.</span></span>  
  
 <span data-ttu-id="90239-105">Por exemplo, imagine que você deseja localizar funcionários que estão na empresa por mais de cinco anos em trabalhos de nível inferior ou funcionários com trabalhos de nível médio, independentemente da data de contratação.</span><span class="sxs-lookup"><span data-stu-id="90239-105">For example, imagine that you want to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs regardless of their hire date.</span></span> <span data-ttu-id="90239-106">Essa consulta exige três condições, duas delas vinculadas a AND:</span><span class="sxs-lookup"><span data-stu-id="90239-106">This query requires three conditions, two of them linked with AND:</span></span>  
  
-   <span data-ttu-id="90239-107">Os funcionários com data de contratação anterior há cinco anos AND com um nível de trabalho de 100.</span><span class="sxs-lookup"><span data-stu-id="90239-107">Employees with a hire date earlier than five years ago AND with a job level of 100.</span></span>  
  
     <span data-ttu-id="90239-108">-ou-</span><span class="sxs-lookup"><span data-stu-id="90239-108">-or-</span></span>  
  
-   <span data-ttu-id="90239-109">Funcionários com um nível de trabalho de 200.</span><span class="sxs-lookup"><span data-stu-id="90239-109">Employees with a job level of 200.</span></span>  
  
### <a name="to-combine-conditions-when-and-has-precedence"></a><span data-ttu-id="90239-110">Para combinar condições quando AND tem precedência</span><span class="sxs-lookup"><span data-stu-id="90239-110">To combine conditions when AND has precedence</span></span>  
  
1.  <span data-ttu-id="90239-111">No [Painel Critérios](visual-database-tools.md), adicione as colunas de dados a serem pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="90239-111">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="90239-112">Para pesquisar a mesma coluna usando duas ou mais condições vinculadas com AND, é preciso adicionar o nome da coluna de dados à grade uma vez para cada valor a ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="90239-112">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="90239-113">Na coluna **Filtro** , digite todas as condições que deseja vincular a AND.</span><span class="sxs-lookup"><span data-stu-id="90239-113">In the **Filter** column, enter all the conditions that you want to link with AND.</span></span> <span data-ttu-id="90239-114">Por exemplo, para vincular condições a AND que pesquisam as colunas `hire_date` e `job_lvl` , digite os valores `< '1/1/91'` e `= 100`, respectivamente, na coluna Filtro.</span><span class="sxs-lookup"><span data-stu-id="90239-114">For example, to link conditions with AND that search the `hire_date` and `job_lvl` columns, enter the values `< '1/1/91'` and `= 100`, respectively, in the Filter column.</span></span>  
  
     <span data-ttu-id="90239-115">Essas entradas de grade produzem a seguinte cláusula WHERE na instrução no [Painel SQL](sql-pane-visual-database-tools.md):</span><span class="sxs-lookup"><span data-stu-id="90239-115">These grid entries produce the following WHERE clause in the statement in the [SQL Pane](sql-pane-visual-database-tools.md):</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91') AND  
      (job_lvl = 100)  
    ```  
  
3.  <span data-ttu-id="90239-116">Na coluna de grade **Ou...** , digite as condições que você deseja vincular a OR.</span><span class="sxs-lookup"><span data-stu-id="90239-116">In the **Or...** grid column, enter conditions that you want to link with OR.</span></span> <span data-ttu-id="90239-117">Por exemplo, para adicionar uma condição que pesquisa outro valor na coluna `job_lvl` , digite um valor adicional na coluna **Ou...** , como `= 200`.</span><span class="sxs-lookup"><span data-stu-id="90239-117">For example, to add a condition that searches for another value in the `job_lvl` column, enter an additional value in the **Or...** column, such as `= 200`.</span></span>  
  
     <span data-ttu-id="90239-118">A adição de um valor na coluna **Ou...** adiciona outra condição à cláusula WHERE na instrução no painel SQL:</span><span class="sxs-lookup"><span data-stu-id="90239-118">Adding a value in the **Or...** column adds another condition to the WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91' ) AND  
      (job_lvl = 100) OR   
      (job_lvl = 200)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="90239-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90239-119">See Also</span></span>  
 <span data-ttu-id="90239-120">[Combinar condições quando ou tem precedência &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="90239-120">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="90239-121">[Convenções para combinar critérios de pesquisa no painel critérios &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="90239-121">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 <span data-ttu-id="90239-122">[Regras para inserir valores de pesquisa &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="90239-122">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="90239-123">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="90239-123">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
