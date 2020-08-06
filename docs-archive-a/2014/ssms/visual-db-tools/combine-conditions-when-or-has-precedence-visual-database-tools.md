---
title: Combinar condições quando OR tem precedência (Ferramentas de Banco de Dados Visual) | Microsoft Docs
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
- OR operator
ms.assetid: b30f5ac9-25e7-4163-80ed-44e4bccb455d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8be0d2f783c28662eb01f6bf191dc24d339534f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678517"
---
# <a name="combine-conditions-when-or-has-precedence-visual-database-tools"></a><span data-ttu-id="71865-102">Combinar condições quando OR tem precedência (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="71865-102">Combine Conditions When OR Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="71865-103">Para vincular condições com OR e dar-lhes precedência sobre condições vinculadas com AND, é preciso repetir a condição AND em todas as condições OR.</span><span class="sxs-lookup"><span data-stu-id="71865-103">To link conditions with OR and give them precedence over conditions linked with AND, you must repeat the AND condition for each OR condition.</span></span>  
  
 <span data-ttu-id="71865-104">Por exemplo, suponhamos que você pretenda localizar os funcionários que estão na empresa há mais de cinco anos, que ocupem cargos de nível mais baixo ou que estejam aposentados.</span><span class="sxs-lookup"><span data-stu-id="71865-104">For example, imagine that you want to find all employees who have been with the company more than five years and have lower-level jobs or are retired.</span></span> <span data-ttu-id="71865-105">Essa consulta requer três condições, uma condição única vinculada a duas condições adicionais com AND:</span><span class="sxs-lookup"><span data-stu-id="71865-105">This query requires three conditions, a single condition linked to two additional conditions with AND:</span></span>  
  
-   <span data-ttu-id="71865-106">Funcionários com data de contratação anterior a cinco anos e</span><span class="sxs-lookup"><span data-stu-id="71865-106">Employees with a hire date earlier than five years ago, and</span></span>  
  
-   <span data-ttu-id="71865-107">Funcionários com um nível de cargo 100 ou cujo status é "R" (aposentado).</span><span class="sxs-lookup"><span data-stu-id="71865-107">Employees with a job level of 100 or whose status is "R" (for retired).</span></span>  
  
 <span data-ttu-id="71865-108">O procedimento a seguir explica como criar esse tipo de consulta no Painel de Critérios.</span><span class="sxs-lookup"><span data-stu-id="71865-108">The following procedure illustrates how to create this type of query in the Criteria pane.</span></span>  
  
### <a name="to-combine-conditions-when-or-has-precedence"></a><span data-ttu-id="71865-109">Para combinar condições quando OR  tem precedência</span><span class="sxs-lookup"><span data-stu-id="71865-109">To combine conditions when OR has precedence</span></span>  
  
1.  <span data-ttu-id="71865-110">No [Painel Critérios](visual-database-tools.md), adicione as colunas de dados a serem pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="71865-110">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="71865-111">Para pesquisar a mesma coluna usando duas ou mais condições vinculadas com AND, é preciso adicionar o nome da coluna de dados à grade uma vez para cada valor a ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="71865-111">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="71865-112">Crie as condições a serem vinculadas com OR digitando a primeira na coluna de grade **Filtro** e a segunda (e seguintes) em colunas **Ou...** separadas.</span><span class="sxs-lookup"><span data-stu-id="71865-112">Create the conditions to be linked with OR by entering the first one into the **Filter** grid column and the second (and subsequent ones) into separate **Or...** columns.</span></span> <span data-ttu-id="71865-113">Por exemplo, para vincular condições com OR que pesquisem as colunas `job_lvl` e `status` , digite `= 100` na coluna **Filtro** para `job_lvl` e `= 'R'` na coluna **Ou...** para `status`.</span><span class="sxs-lookup"><span data-stu-id="71865-113">For example, to link conditions with OR that search the `job_lvl` and `status` columns, enter `= 100` in the **Filter** column for `job_lvl` and `= 'R'` in the **Or...** column for `status`.</span></span>  
  
     <span data-ttu-id="71865-114">Digitar esses valores na grade produz a cláusula WHERE seguinte na instrução do Painel SQL:</span><span class="sxs-lookup"><span data-stu-id="71865-114">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) OR (status = 'R')  
    ```  
  
3.  <span data-ttu-id="71865-115">Crie a condição AND inserindo-a uma vez para cada uma das condições OR.</span><span class="sxs-lookup"><span data-stu-id="71865-115">Create the AND condition by entering it once for each OR condition.</span></span> <span data-ttu-id="71865-116">Coloque cada entrada na mesma coluna de grade como sendo a condição OR à qual ela corresponde.</span><span class="sxs-lookup"><span data-stu-id="71865-116">Place each entry in the same grid column as the OR condition it corresponds to.</span></span> <span data-ttu-id="71865-117">Por exemplo, para adicionar uma condição AND que pesquise a coluna `hire_date` e que se aplique a ambas as condições OR, digite `< '1/1/91'` na coluna Critérios e na coluna **Ou...** .</span><span class="sxs-lookup"><span data-stu-id="71865-117">For example, to add an AND condition that searches the `hire_date` column and applies to both OR conditions, enter `< '1/1/91'` in both the Criteria column and the **Or...** column.</span></span>  
  
     <span data-ttu-id="71865-118">Digitar esses valores na grade produz a cláusula WHERE seguinte na instrução do Painel SQL:</span><span class="sxs-lookup"><span data-stu-id="71865-118">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) AND   
      (hire_date < '01/01/91' ) OR  
      (status = 'R') AND   
      (hire_date < '01/01/91' )  
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="71865-119">Repita uma condição AND adicionando-a uma vez e usando os comandos **Recortar** e **Colar** do menu **Editar** para repeti-la em outras condições OR.</span><span class="sxs-lookup"><span data-stu-id="71865-119">You can repeat an AND condition by adding it once, and then using the **Cut** and **Paste** commands from the **Edit** menu to repeat it for other OR conditions.</span></span>  
  
 <span data-ttu-id="71865-120">A cláusula WHERE, criada pelo Designer de Consulta e Exibição, equivale à seguinte cláusula WHERE, que usa parênteses para especificar a precedência de OR sobre AND:</span><span class="sxs-lookup"><span data-stu-id="71865-120">The WHERE clause created by the Query and View Designer is equivalent to the following WHERE clause, which uses parentheses to specify the precedence of OR over AND:</span></span>  
  
```  
WHERE (job_lvl = 100 OR status = 'R') AND  
   (hire_date < '01/01/91')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="71865-121">Se você digitar os critérios de pesquisa no formato mostrado anteriormente no [Painel SQL](sql-pane-visual-database-tools.md), mas depois fizer uma alteração na consulta no Painel Diagrama ou Critérios, o Designer de Consulta e Exibição recriará a instrução SQL para que corresponda ao formato em que a condição AND é explicitamente distribuída em ambas as condições OR.</span><span class="sxs-lookup"><span data-stu-id="71865-121">If you enter the search conditions in the format shown immediately above in the [SQL Pane](sql-pane-visual-database-tools.md), but then make a change to the query in the Diagram or Criteria panes, the Query and View Designer recreates the SQL statement to match the form with the AND condition explicitly distributed to both OR conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71865-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71865-122">See Also</span></span>  
 <span data-ttu-id="71865-123">[Convenções para combinar critérios de pesquisa no painel critérios &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="71865-123">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="71865-124">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="71865-124">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
