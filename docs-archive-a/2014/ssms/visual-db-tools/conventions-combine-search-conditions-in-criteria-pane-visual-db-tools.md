---
title: Convenções para combinar critérios de pesquisa no painel critérios (ferramentas de banco de dados Visual) | Microsoft Docs
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
- multiple OR clauses
- combining search conditions
- OR operator
- AND, Criteria pane
- multiple AND clauses
ms.assetid: d4859be5-ff5b-48b2-a101-ad40c6dbcc68
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684521baa87d5325366a0e18296cd35342a0e947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678519"
---
# <a name="conventions-for-combining-search-conditions-in-the-criteria-pane-visual-database-tools"></a><span data-ttu-id="23bdc-102">Convenções para combinar critérios de pesquisa no painel de Critérios (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="23bdc-102">Conventions for Combining Search Conditions in the Criteria Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="23bdc-103">Você pode criar consultas que incluam qualquer número de critérios de pesquisa, interligadas com qualquer número de operadores AND e OR.</span><span class="sxs-lookup"><span data-stu-id="23bdc-103">You can create queries that include any number of search conditions, linked with any number of AND and OR operators.</span></span> <span data-ttu-id="23bdc-104">Uma consulta com uma combinação de cláusulas AND e OR pode se tornar complexa, então é útil entender como tal consulta é interpretada quando você a executa, e como tal consulta é representada no [Painel Critérios](visual-database-tools.md) e no [Painel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23bdc-104">A query with a combination of AND and OR clauses can become complex, so it is helpful to understand how such a query is interpreted when you execute it, and how such a query is represented in the [Criteria Pane](visual-database-tools.md) and [SQL Pane](sql-pane-visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23bdc-105">Para obter detalhes sobre os critérios de pesquisa que contêm apenas um operador AND ou OR, consulte [Especificar vários critérios de pesquisa para uma coluna &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) e [Especificar vários critérios de pesquisa para várias colunas &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23bdc-105">For details about search conditions that contain only one AND or OR operator, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) and [Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="23bdc-106">Abaixo você achará informações sobre:</span><span class="sxs-lookup"><span data-stu-id="23bdc-106">Below you will find information about:</span></span>  
  
-   <span data-ttu-id="23bdc-107">A precedência de AND e OR em consultas que contenham ambos.</span><span class="sxs-lookup"><span data-stu-id="23bdc-107">The precedence of AND and OR in queries that contain both.</span></span>  
  
-   <span data-ttu-id="23bdc-108">Como as condições em cláusulas AND e OR se relacionam logicamente uma a outra.</span><span class="sxs-lookup"><span data-stu-id="23bdc-108">How the conditions in AND and OR clauses relate logically to one another.</span></span>  
  
-   <span data-ttu-id="23bdc-109">Como os Designers de Consulta e Exibição representam nas consultas do Painel de Critérios que contenham ambos AND e OR</span><span class="sxs-lookup"><span data-stu-id="23bdc-109">How the Query and View Designer represents in the Criteria Pane queries that contain both AND and OR.</span></span>  
  
 <span data-ttu-id="23bdc-110">Para ajudá-lo a entender a discussão abaixo, imagine que está trabalhando com uma tabela `employee` contendo as colunas `hire_date`, `job_lvl`, e `status`.</span><span class="sxs-lookup"><span data-stu-id="23bdc-110">To help you understand the discussion below, imagine that you are working with an `employee` table containing the columns `hire_date`, `job_lvl`, and `status`.</span></span> <span data-ttu-id="23bdc-111">Os exemplos supõem que você precisa conhecer informações como quanto tempo um funcionário trabalha para a companhia (quer dizer, qual a data de contratação do funcionário), que tipo de tarefa que o funcionário executa (qual é o nível do emprego) e o estado do empregado (por exemplo, aposentado).</span><span class="sxs-lookup"><span data-stu-id="23bdc-111">The examples assume that you need to know information such as how long an employee has worked with the company (that is, what the employee's hire date is), what type of job the employee performs (what the job level is), and the employee's status (for example, retired).</span></span>  
  
## <a name="precedence-of-and-and-or"></a><span data-ttu-id="23bdc-112">Precedência de AND e OR</span><span class="sxs-lookup"><span data-stu-id="23bdc-112">Precedence of AND and OR</span></span>  
 <span data-ttu-id="23bdc-113">Quando uma consulta é executada, ela primeiro avalia as cláusulas unidas com AND, e então aquelas unidas com OR.</span><span class="sxs-lookup"><span data-stu-id="23bdc-113">When a query is executed, it evaluates first the clauses linked with AND, and then those linked with OR.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23bdc-114">O operador NOT tem precedência sobre AND e OR.</span><span class="sxs-lookup"><span data-stu-id="23bdc-114">The NOT operator takes precedence over both AND and OR.</span></span>  
  
 <span data-ttu-id="23bdc-115">Por exemplo, para encontrar quais funcionários estão trabalhando para a empresa por mais de cinco anos em funções de níveis menores, ou funcionários com funções de níveis intermediários, sem levar em contar as suas datas de contratação, você pode construir uma cláusula WHERE como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="23bdc-115">For example, to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs without regard for their hire date, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   job_lvl = 100 OR  
   job_lvl = 200  
  
```  
  
 <span data-ttu-id="23bdc-116">Para anular a precedência padrão de AND sobre OR, você pode pôr parênteses ao redor das condições específicas no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="23bdc-116">To override the default precedence of AND over OR, you can put parentheses around specific conditions in the SQL pane.</span></span> <span data-ttu-id="23bdc-117">As condições entre parênteses são sempre avaliadas em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="23bdc-117">Conditions in parentheses are always evaluated first.</span></span> <span data-ttu-id="23bdc-118">Por exemplo, para encontrar todos os funcionários trabalhando para a empresa por mais de cinco anos tanto em funções de nível inferior quanto de níveis intermediários, você pode construir cláusulas WHERE como nos exemplos seguintes:</span><span class="sxs-lookup"><span data-stu-id="23bdc-118">For example, to find all employees who have been with the company more than five years in either lower or middle-level jobs, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
> [!TIP]  
>  <span data-ttu-id="23bdc-119">É recomendado que, para uma maior clareza, você sempre inclua parênteses ao combinar cláusulas AND e OR em vez de confiar na precedência padrão.</span><span class="sxs-lookup"><span data-stu-id="23bdc-119">It is recommended that, for clarity, you always include parentheses when combining AND and OR clauses instead of relying on the default precedence.</span></span>  
  
## <a name="how-and-works-with-multiple-or-clauses"></a><span data-ttu-id="23bdc-120">Como AND trabalha com múltiplas cláusulas OR</span><span class="sxs-lookup"><span data-stu-id="23bdc-120">How AND Works with Multiple OR Clauses</span></span>  
 <span data-ttu-id="23bdc-121">Compreender como as cláusulas AND e OR são relacionadas quando combinadas pode ajudar você a construir e entender consultas complexas no Designer de Exibição e Consulta.</span><span class="sxs-lookup"><span data-stu-id="23bdc-121">Understanding how AND and OR clauses are related when combined can help you construct and understand complex queries in the Query and View Designer.</span></span>  
  
 <span data-ttu-id="23bdc-122">Se você vincular condições múltiplas que usam AND, o primeiro conjunto de condições vinculadas à AND se aplicará a todas as condições no segundo conjunto.</span><span class="sxs-lookup"><span data-stu-id="23bdc-122">If you link multiple conditions using AND, the first set of conditions linked with AND applies to all the conditions in the second set.</span></span> <span data-ttu-id="23bdc-123">Em outras palavras, uma condição vinculada à AND a outra condição é distribuída a todas as condições no segundo conjunto.</span><span class="sxs-lookup"><span data-stu-id="23bdc-123">In other words, a condition linked with AND to another condition is distributed to all the conditions in the second set.</span></span> <span data-ttu-id="23bdc-124">Por exemplo, a representação esquemática seguinte mostra uma condição AND vinculada a um conjunto de condições OR:</span><span class="sxs-lookup"><span data-stu-id="23bdc-124">For example, the following schematic representation shows an AND condition linked to a set of OR conditions:</span></span>  
  
```  
A AND (B OR C)  
```  
  
 <span data-ttu-id="23bdc-125">A representação acima é logicamente equivalente à representação esquemática seguinte, que mostra como a condição AND é distribuída ao segundo conjunto de condições:</span><span class="sxs-lookup"><span data-stu-id="23bdc-125">The representation above is logically equivalent to the following schematic representation, which shows how the AND condition is distributed to the second set of conditions:</span></span>  
  
```  
(A AND B) OR (A AND C)  
```  
  
 <span data-ttu-id="23bdc-126">Este princípio distributivo afeta como você usa o Designer de Consulta e Exibição.</span><span class="sxs-lookup"><span data-stu-id="23bdc-126">This distributive principle affects how you use the Query and View Designer.</span></span> <span data-ttu-id="23bdc-127">Por exemplo, imagine que você pretenda localizar todo os funcionários que trabalhe para a empresa há mais de cinco anos, em cargos de nível inferior ou intermediário.</span><span class="sxs-lookup"><span data-stu-id="23bdc-127">For example, imagine that you are looking for all employees who have been with the company more than five years in either lower or middle-level jobs.</span></span> <span data-ttu-id="23bdc-128">Você entra a seguinte cláusula WHERE na instrução do painel SQL:</span><span class="sxs-lookup"><span data-stu-id="23bdc-128">You enter the following WHERE clause into the statement in the SQL pane:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
 <span data-ttu-id="23bdc-129">A cláusula vinculada com AND se aplica a ambas as cláusulas vinculadas com OR.</span><span class="sxs-lookup"><span data-stu-id="23bdc-129">The clause linked with AND applies to both clauses linked with OR.</span></span> <span data-ttu-id="23bdc-130">Um modo explícito para expressar isto é repetir a condição AND uma vez para cada condição na cláusula OR.</span><span class="sxs-lookup"><span data-stu-id="23bdc-130">An explicit way to express this is to repeat the AND condition once for each condition in the OR clause.</span></span> <span data-ttu-id="23bdc-131">A instrução seguinte é mais explícita (e maior) que a instrução anterior, mas é logicamente equivalente à ela:</span><span class="sxs-lookup"><span data-stu-id="23bdc-131">The following statement is more explicit (and longer) than the previous statement, but is logically equivalent to it:</span></span>  
  
```  
WHERE    (hire_date < '01/01/95' ) AND  
  (job_lvl = 100) OR   
  (hire_date < '01/01/95' ) AND   
  (job_lvl = 200)  
```  
  
 <span data-ttu-id="23bdc-132">O princípio de distribuir cláusulas AND para cláusulas OR vinculadas se aplica, não importando quantas condições individuais estão envolvidas.</span><span class="sxs-lookup"><span data-stu-id="23bdc-132">The principle of distributing AND clauses to linked OR clauses applies no matter how many individual conditions are involved.</span></span> <span data-ttu-id="23bdc-133">Por exemplo, imagine que você queira localizar os funcionários, de funções de nível superior ou intermediário,que trabalhem para a empresa há mais de cinco anos ou que estejam aposentados.</span><span class="sxs-lookup"><span data-stu-id="23bdc-133">For example, imagine that you want to find higher or middle-level employees who have been with the company more than five years or are retired.</span></span> <span data-ttu-id="23bdc-134">A cláusula WHERE pode parecer assim:</span><span class="sxs-lookup"><span data-stu-id="23bdc-134">The WHERE clause might look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 OR job_lvl = 300) AND  
   (hire_date < '01/01/95' ) OR (status = 'R')  
```  
  
 <span data-ttu-id="23bdc-135">Após as condições vinculadas com AND tiverem sido distribuídas, a cláusula WHERE se parecerá com:</span><span class="sxs-lookup"><span data-stu-id="23bdc-135">After the conditions linked with AND have been distributed, the WHERE clause will look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 200 AND status = 'R') OR  
   (job_lvl = 300 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 300 AND status = 'R')   
```  
  
## <a name="how-multiple-and-and-or-clauses-are-represented-in-the-criteria-pane"></a><span data-ttu-id="23bdc-136">Como são representadas as cláusulas múltiplas AND e OR no Painel de Critérios</span><span class="sxs-lookup"><span data-stu-id="23bdc-136">How Multiple AND and OR Clauses Are Represented in the Criteria Pane</span></span>  
 <span data-ttu-id="23bdc-137">O Designer de Consulta e Exibição representa os critérios de pesquisa no [Painel Critérios](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23bdc-137">The Query and View Designer represents your search conditions in the [Criteria Pane](visual-database-tools.md).</span></span> <span data-ttu-id="23bdc-138">Porém, em alguns casos que envolvem cláusulas múltiplas vinculadas com AND e OR, a representação no Painel de Critérios pode não ser o que você espera.</span><span class="sxs-lookup"><span data-stu-id="23bdc-138">However, in some cases that involve multiple clauses linked with AND and OR, the representation in the Criteria Pane might not be what you expect.</span></span> <span data-ttu-id="23bdc-139">Além disso, se você modificar sua consulta no Painel Critérios ou no [Painel Diagrama](diagram-pane-visual-database-tools.md), poderá descobrir que a instrução SQL que você inseriu foi alterada.</span><span class="sxs-lookup"><span data-stu-id="23bdc-139">In addition, if you modify your query in the Criteria Pane or [Diagram Pane](diagram-pane-visual-database-tools.md), you might find that your SQL statement has been changed from what you entered.</span></span>  
  
 <span data-ttu-id="23bdc-140">Em geral, estas regras ditam como as cláusulas AND e OR aparecem no Painel de Critérios:</span><span class="sxs-lookup"><span data-stu-id="23bdc-140">In general, these rules dictate how AND and OR clauses appear in the Criteria Pane:</span></span>  
  
-   <span data-ttu-id="23bdc-141">Todas as condições vinculadas com AND aparecem na coluna de grade **Filtro** ou na mesma coluna **Ou...** .</span><span class="sxs-lookup"><span data-stu-id="23bdc-141">All conditions linked with AND appear in the **Filter** grid column or in the same **Or...** column.</span></span>  
  
-   <span data-ttu-id="23bdc-142">Todas as condições vinculadas com OR aparecem em colunas **Ou...** separadas.</span><span class="sxs-lookup"><span data-stu-id="23bdc-142">All conditions linked with OR appear in separate **Or...** columns.</span></span>  
  
-   <span data-ttu-id="23bdc-143">Se o resultado lógico de uma combinação de cláusulas AND e OR cláusulas for que AND seja distribuído em várias cláusulas OR, o Painel de Critérios representará isto explicitamente repetindo a cláusula AND tantas vezes quanto necessário.</span><span class="sxs-lookup"><span data-stu-id="23bdc-143">If the logical result of a combination of AND and OR clauses is that the AND is distributed into several OR clauses, the Criteria Pane represents this explicitly by repeating the AND clause as many times as necessary.</span></span>  
  
 <span data-ttu-id="23bdc-144">Por exemplo, no painel SQL você pode criar um critério de pesquisa como o seguinte, no qual duas cláusulas vinculadas com AND têm precedência sobre uma terceira vinculada com OR:</span><span class="sxs-lookup"><span data-stu-id="23bdc-144">For example, in the SQL pane you might create a search condition such as the following, in which two clauses linked with AND take precedence over a third one linked with OR:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  (job_lvl = 100) OR   
  (status = 'R')  
```  
  
 <span data-ttu-id="23bdc-145">O Designer de Consulta e Exibição representa essa cláusula WHERE no Painel de Critérios como segue:</span><span class="sxs-lookup"><span data-stu-id="23bdc-145">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="23bdc-146">![Precedência da cláusula OR no painel Critérios](../../database-engine/media//vs-criteriapane1.gif "Precedência da cláusula OR no painel Critérios")</span><span class="sxs-lookup"><span data-stu-id="23bdc-146">![OR clause precedence in the Criteria Pane](../../database-engine/media//vs-criteriapane1.gif "OR clause precedence in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="23bdc-147">Porém, se as cláusulas OR têm precedência sobre uma cláusula AND, a cláusula AND é repetida para cada cláusula OR.</span><span class="sxs-lookup"><span data-stu-id="23bdc-147">However, if the linked OR clauses take precedence over an AND clause, the AND clause is repeated for each OR clause.</span></span> <span data-ttu-id="23bdc-148">Isto faz com que a cláusula AND seja distribuída para cada cláusula OR.</span><span class="sxs-lookup"><span data-stu-id="23bdc-148">This causes the AND clause to be distributed to each OR clause.</span></span> <span data-ttu-id="23bdc-149">Por exemplo, no painel SQL você poderá criar uma cláusula WHERE como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="23bdc-149">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ( (job_lvl = 100) OR   
  (status = 'R') )  
```  
  
 <span data-ttu-id="23bdc-150">O Designer de Consulta e Exibição representa essa cláusula WHERE no Painel de Critérios como segue:</span><span class="sxs-lookup"><span data-stu-id="23bdc-150">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="23bdc-151">![Cláusulas múltiplas AND e OR no Painel de Critérios](../../database-engine/media//vs-criteriapane2.gif "Cláusulas múltiplas AND e OR no Painel de Critérios")</span><span class="sxs-lookup"><span data-stu-id="23bdc-151">![Multiple AND and OR clauses in the Criteria Pane](../../database-engine/media//vs-criteriapane2.gif "Multiple AND and OR clauses in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="23bdc-152">Se as cláusulas vinculadas OR envolverem só uma coluna de dados, o Designer de Consulta e Exibição pode colocar a toda a cláusula OR em uma única célula da grade, evitando a necessidade de repetir a cláusula AND.</span><span class="sxs-lookup"><span data-stu-id="23bdc-152">If the linked OR clauses involve only one data column, the Query and View Designer can place the entire OR clause into a single cell of the grid, avoiding the need to repeat the AND clause.</span></span> <span data-ttu-id="23bdc-153">Por exemplo, no painel SQL você poderá criar uma cláusula WHERE como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="23bdc-153">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ((status = 'R') OR (status = 'A'))  
```  
  
 <span data-ttu-id="23bdc-154">O Designer de Consulta e Exibição representa essa cláusula WHERE no Painel de Critérios como segue:</span><span class="sxs-lookup"><span data-stu-id="23bdc-154">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="23bdc-155">![Cláusulas vinculadas OR definidas no Painel de Critérios](../../database-engine/media//vs-criteriapane3.gif "Cláusulas vinculadas OR definidas no Painel de Critérios")</span><span class="sxs-lookup"><span data-stu-id="23bdc-155">![Linked OR clauses defined in the Criteria Pane](../../database-engine/media//vs-criteriapane3.gif "Linked OR clauses defined in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="23bdc-156">Se você fizer uma mudança na consulta (como alterar um dos valores no Painel de Critérios), o Designer de Consulta e Exibição recriará a instrução SQL no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="23bdc-156">If you make a change to the query (such as changing one of the values in the Criteria Pane), the Query and View Designer recreates the SQL statement in the SQL pane.</span></span> <span data-ttu-id="23bdc-157">A instrução SQL recriada se assemelhará à exibição do Painel de Critérios em vez de sua instrução original.</span><span class="sxs-lookup"><span data-stu-id="23bdc-157">The recreated SQL statement will resemble the Criteria Pane display rather than your original statement.</span></span> <span data-ttu-id="23bdc-158">Por exemplo, se o Painel de Critérios contiver cláusulas AND distribuídas, a instrução resultante no painel SQL será recriada com cláusulas AND explicitamente distribuídas.</span><span class="sxs-lookup"><span data-stu-id="23bdc-158">For example, if the Criteria Pane contains distributed AND clauses, the resulting statement in the SQL pane will be recreated with explicit distributed AND clauses.</span></span> <span data-ttu-id="23bdc-159">Para detalhes, consulte "Como AND funciona com múltiplas cláusulas OR" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="23bdc-159">For details, see "How AND Works with Multiple OR Clauses" earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23bdc-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23bdc-160">See Also</span></span>  
 [<span data-ttu-id="23bdc-161">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="23bdc-161">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
