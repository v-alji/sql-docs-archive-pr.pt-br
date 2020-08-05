---
title: Entendendo a ordem de passagem e a ordem de resolução (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- evaluation order [MDX]
- calculation order [MDX]
- SOLVE_ORDER property
- queries [MDX], solve orders
- solve orders [MDX]
- pass orders [MDX]
- expressions [MDX], solve orders
ms.assetid: 7ed7d4ee-4644-4c5d-99a4-c4b429d0203c
author: minewiskan
ms.author: owend
ms.openlocfilehash: d92ccd9d1eeb05272a95c6f429f8c756bcb0022e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572741"
---
# <a name="understanding-pass-order-and-solve-order-mdx"></a><span data-ttu-id="b99a7-102">Entendendo a ordem de passagem e a ordem de resolução (MDX)</span><span class="sxs-lookup"><span data-stu-id="b99a7-102">Understanding Pass Order and Solve Order (MDX)</span></span>
  <span data-ttu-id="b99a7-103">Quando um cubo é calculado como resultado de um script MDX, ele pode passar por várias fases de cálculo dependendo do uso de diversos recursos relacionados ao cálculo.</span><span class="sxs-lookup"><span data-stu-id="b99a7-103">When a cube is calculated as the result of an MDX script, it can go through many stages of computation depending on the use of various calculation-related features.</span></span> <span data-ttu-id="b99a7-104">Cada uma dessas fases é chamada de fase de cálculo.</span><span class="sxs-lookup"><span data-stu-id="b99a7-104">Each of these stages is referred to as a calculation pass.</span></span>  
  
 <span data-ttu-id="b99a7-105">Uma fase de cálculo pode ser denominada por uma posição ordinal, chamada número de fase de cálculo.</span><span class="sxs-lookup"><span data-stu-id="b99a7-105">A calculation pass can be referred to by an ordinal position, called the calculation pass number.</span></span> <span data-ttu-id="b99a7-106">A quantidade de fases de cálculo necessária para computar por completo todas as células de um cubo é conhecida como profundidade de fase de cálculo do cubo.</span><span class="sxs-lookup"><span data-stu-id="b99a7-106">The count of calculation passes that are required to fully compute all the cells of a cube is referred to as the calculation pass depth of the cube.</span></span>  
  
 <span data-ttu-id="b99a7-107">Dados da tabela de fatos e de write-back afetam somente a passagem 0.</span><span class="sxs-lookup"><span data-stu-id="b99a7-107">Fact table and writeback data only impact pass 0.</span></span> <span data-ttu-id="b99a7-108">Os scripts preenchem os dados depois da passagem 0; cada atribuição e instrução calculada de um script criam uma nova passagem.</span><span class="sxs-lookup"><span data-stu-id="b99a7-108">Scripts populate data after pass 0; each assignment and calculate statement in a script creates a new pass.</span></span> <span data-ttu-id="b99a7-109">Fora do script MDX, as referências à passagem 0 absoluta referem-se à última passagem criada pelo script para o cubo.</span><span class="sxs-lookup"><span data-stu-id="b99a7-109">Outside the MDX script, references to absolute pass 0 refer to the last pass created by the script for the cube.</span></span>  
  
 <span data-ttu-id="b99a7-110">São criados membros calculados em todas as passagens, mas a expressão é aplicada à passagem atual.</span><span class="sxs-lookup"><span data-stu-id="b99a7-110">Calculated members are created at all passes, but the expression is applied at the current pass.</span></span> <span data-ttu-id="b99a7-111">Passagens anteriores contêm a medida calculada, mas com um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="b99a7-111">Prior passes contain the calculated measure, but with a null value.</span></span>  
  
## <a name="solve-order"></a><span data-ttu-id="b99a7-112">Ordem de resolução</span><span class="sxs-lookup"><span data-stu-id="b99a7-112">Solve Order</span></span>  
 <span data-ttu-id="b99a7-113">A ordem de resolução determina a prioridade de cálculo no caso de expressões concorrentes.</span><span class="sxs-lookup"><span data-stu-id="b99a7-113">Solve order determines the priority of calculation in the event of competing expressions.</span></span> <span data-ttu-id="b99a7-114">Em uma mesma passagem, a ordem de resolução determina duas coisas:</span><span class="sxs-lookup"><span data-stu-id="b99a7-114">Within a single pass, solve order determines two things:</span></span>  
  
-   <span data-ttu-id="b99a7-115">A ordem na qual [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] avalia as dimensões, os membros, os membros calculados, os rollups personalizados e as células calculadas.</span><span class="sxs-lookup"><span data-stu-id="b99a7-115">The order in which [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates dimensions, members, calculated members, custom rollups, and calculated cells.</span></span>  
  
-   <span data-ttu-id="b99a7-116">A ordem na qual o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calcula membros personalizados, membros calculados, rollups personalizados e células calculadas.</span><span class="sxs-lookup"><span data-stu-id="b99a7-116">The order in which [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates custom members, calculated members, custom rollup, and calculated cells.</span></span>  
  
 <span data-ttu-id="b99a7-117">O membro com a ordem de resolução mais alta tem precedência.</span><span class="sxs-lookup"><span data-stu-id="b99a7-117">The member with the highest solve order takes precedence.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b99a7-118">A exceção a essa precedência é a função Aggregate.</span><span class="sxs-lookup"><span data-stu-id="b99a7-118">The exception to this precedence is the Aggregate function.</span></span> <span data-ttu-id="b99a7-119">A ordem de resolução de membros calculados com a função Aggregate é inferior a qualquer medida calculada de intersecção.</span><span class="sxs-lookup"><span data-stu-id="b99a7-119">Calculated members with the Aggregate function have a lower solve order than any intersecting calculated measure.</span></span>  
  
## <a name="solve-order-values-and-precedence"></a><span data-ttu-id="b99a7-120">Valores e precedência da ordem de resolução</span><span class="sxs-lookup"><span data-stu-id="b99a7-120">Solve Order Values and Precedence</span></span>  
 <span data-ttu-id="b99a7-121">Os valores da ordem de resolução podem variar de -8181 a 65535.</span><span class="sxs-lookup"><span data-stu-id="b99a7-121">Solve order values can range from -8181 to 65535.</span></span> <span data-ttu-id="b99a7-122">Nesse intervalo, alguns valores da ordem de resolução correspondem a tipos específicos de cálculos, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b99a7-122">In this range, some solve order values correspond to specific kinds of calculations, as shown in the following table.</span></span>  
  
|<span data-ttu-id="b99a7-123">Cálculo</span><span class="sxs-lookup"><span data-stu-id="b99a7-123">Calculation</span></span>|<span data-ttu-id="b99a7-124">Ordem de resolução</span><span class="sxs-lookup"><span data-stu-id="b99a7-124">Solve Order</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b99a7-125">Fórmulas de membro personalizado</span><span class="sxs-lookup"><span data-stu-id="b99a7-125">Custom member formulas</span></span>|<span data-ttu-id="b99a7-126">-5119</span><span class="sxs-lookup"><span data-stu-id="b99a7-126">-5119</span></span>|  
|<span data-ttu-id="b99a7-127">Operadores unários</span><span class="sxs-lookup"><span data-stu-id="b99a7-127">Unary operators</span></span>|<span data-ttu-id="b99a7-128">-5119</span><span class="sxs-lookup"><span data-stu-id="b99a7-128">-5119</span></span>|  
|<span data-ttu-id="b99a7-129">Cálculo de totais visuais</span><span class="sxs-lookup"><span data-stu-id="b99a7-129">Visual totals calculation</span></span>|<span data-ttu-id="b99a7-130">-4096</span><span class="sxs-lookup"><span data-stu-id="b99a7-130">-4096</span></span>|  
|<span data-ttu-id="b99a7-131">Todos os outros cálculos (se não for especificado de outra forma)</span><span class="sxs-lookup"><span data-stu-id="b99a7-131">All other calculations (if not otherwise specified)</span></span>|<span data-ttu-id="b99a7-132">0</span><span class="sxs-lookup"><span data-stu-id="b99a7-132">0</span></span>|  
  
 <span data-ttu-id="b99a7-133">É altamente recomendável o uso exclusivo de números inteiros positivos ao definir valores da ordem de resolução.</span><span class="sxs-lookup"><span data-stu-id="b99a7-133">It is highly recommended that you use only positive integers when setting solve order values.</span></span> <span data-ttu-id="b99a7-134">Se você atribuir valores inferiores aos valores da ordem de resolução mostrados na tabela anterior, a fase de cálculo pode tornar-se imprevisível.</span><span class="sxs-lookup"><span data-stu-id="b99a7-134">If you assign values that are lower than the solve order values shown in the previous table, the calculation pass can become unpredictable.</span></span> <span data-ttu-id="b99a7-135">Por exemplo, o cálculo de um membro calculado receberá um valor de ordem de resolução inferior ao valor da fórmula de rollup personalizado de -5119.</span><span class="sxs-lookup"><span data-stu-id="b99a7-135">For example, the calculation for a calculated member receives a solve order value that is lower than the default custom rollup formula value of -5119.</span></span> <span data-ttu-id="b99a7-136">Esse valor de ordem de resolução baixo faz com que os membros calculados sejam calculados antes das fórmulas de rollup personalizado, podendo produzir resultados incorretos.</span><span class="sxs-lookup"><span data-stu-id="b99a7-136">Such a low solve order value causes the calculated members to be calculated before the custom rollup formulas, and can produce incorrect results.</span></span>  
  
### <a name="creating-and-changing-solve-order"></a><span data-ttu-id="b99a7-137">Criando e alterando a ordem de resolução</span><span class="sxs-lookup"><span data-stu-id="b99a7-137">Creating and Changing Solve Order</span></span>  
 <span data-ttu-id="b99a7-138">No Designer de Cubo, no **Painel de Cálculos**, é possível alterar a ordem de resolução de membros calculados e células calculadas mudando a ordem dos cálculos.</span><span class="sxs-lookup"><span data-stu-id="b99a7-138">In Cube Designer, on the **Calculations Pane**, you can change the solve order for calculated members and calculated cells by changing the order of the calculations.</span></span>  
  
 <span data-ttu-id="b99a7-139">No formato MDX, você pode usar a palavra-chave `SOLVE_ORDER` para criar ou alterar membros calculados e células calculadas.</span><span class="sxs-lookup"><span data-stu-id="b99a7-139">In MDX, you can use the `SOLVE_ORDER` keyword to create or change calculated members and calculated cells.</span></span>  
  
## <a name="solve-order-examples"></a><span data-ttu-id="b99a7-140">Exemplos de ordem de resolução</span><span class="sxs-lookup"><span data-stu-id="b99a7-140">Solve Order Examples</span></span>  
 <span data-ttu-id="b99a7-141">Para ilustrar as complexidades inerentes da ordem de resolução, a sequência de consultas MDX a seguir começa com duas consultas, sem problemas de ordem de resolução individualmente.</span><span class="sxs-lookup"><span data-stu-id="b99a7-141">To illustrate the potential complexities of solve order, the following series of MDX queries starts with two queries that each individually have no solve order issues.</span></span> <span data-ttu-id="b99a7-142">Em seguida, essas duas consultas são combinadas em uma consulta que requer uma ordem de resolução.</span><span class="sxs-lookup"><span data-stu-id="b99a7-142">These two queries are then combined into a query that requires solve order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b99a7-143">Você pode executar essas consultas MDX no banco de dados multidimensional de amostra da Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="b99a7-143">You can run these MDX queries against the Adventure Works sample multidimensional database.</span></span> <span data-ttu-id="b99a7-144">Você pode baixar o exemplo de [Modelos multidimensionais do SQL Server 2012 da AdventureWorks](https://msftdbprodsamples.codeplex.com/releases/view/55330) do site do codeplex.</span><span class="sxs-lookup"><span data-stu-id="b99a7-144">You can download the [AdventureWorks Multidimensional Models SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) sample from the codeplex site.</span></span>  
  
### <a name="query-1-differences-in-income-and-expenses"></a><span data-ttu-id="b99a7-145">Consulta 1-diferenças de renda e despesas</span><span class="sxs-lookup"><span data-stu-id="b99a7-145">Query 1-Differences in Income and Expenses</span></span>  
 <span data-ttu-id="b99a7-146">Para a primeira consulta MDX, calcule a diferença entre vendas e custos de cada ano construindo uma consulta MDX simples semelhante a este exemplo:</span><span class="sxs-lookup"><span data-stu-id="b99a7-146">For the first MDX query, calculate the difference in sales and costs for each year by constructing a simple MDX query similar to the following example:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] )  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="b99a7-147">Nessa consulta, existe apenas um membro calculado, `Year Difference`.</span><span class="sxs-lookup"><span data-stu-id="b99a7-147">In this query, there is only one calculated member, `Year Difference`.</span></span> <span data-ttu-id="b99a7-148">Como há somente um membro calculado, a ordem de resolução não é uma preocupação, pois o cubo não usará nenhum membro calculado.</span><span class="sxs-lookup"><span data-stu-id="b99a7-148">Because there is only one calculated member, solve order is not an issue, as long as the cube does not use any calculated members.</span></span>  
  
 <span data-ttu-id="b99a7-149">Essa consulta MDX produz um conjunto de resultados semelhante à tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b99a7-149">This MDX query produces a result set similar to the following table.</span></span>  
  
||<span data-ttu-id="b99a7-150">Valor das Vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="b99a7-150">Internet Sales Amount</span></span>|<span data-ttu-id="b99a7-151">Custo Total do Produto da Internet</span><span class="sxs-lookup"><span data-stu-id="b99a7-151">Internet Total Product Cost</span></span>|  
|-|---------------------------|---------------------------------|  
|<span data-ttu-id="b99a7-152">**AS 2007**</span><span class="sxs-lookup"><span data-stu-id="b99a7-152">**CY 2007**</span></span>|<span data-ttu-id="b99a7-153">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="b99a7-153">$9,791,060.30</span></span>|<span data-ttu-id="b99a7-154">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="b99a7-154">$5,718,327.17</span></span>|  
|<span data-ttu-id="b99a7-155">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="b99a7-155">**CY 2008**</span></span>|<span data-ttu-id="b99a7-156">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="b99a7-156">$9,770,899.74</span></span>|<span data-ttu-id="b99a7-157">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="b99a7-157">$5,721,205.24</span></span>|  
|<span data-ttu-id="b99a7-158">**Diferença anual**</span><span class="sxs-lookup"><span data-stu-id="b99a7-158">**Year Difference**</span></span>|<span data-ttu-id="b99a7-159">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="b99a7-159">($20,160.56)</span></span>|<span data-ttu-id="b99a7-160">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="b99a7-160">$2,878.06</span></span>|  
  
### <a name="query-2-percentage-of-income-after-expenses"></a><span data-ttu-id="b99a7-161">Consulta 2-percentual de renda após despesas</span><span class="sxs-lookup"><span data-stu-id="b99a7-161">Query 2-Percentage of Income after Expenses</span></span>  
 <span data-ttu-id="b99a7-162">Para a segunda consulta MDX, calcule a porcentagem da receita menos as despesas de cada ano, usando a consulta MDX a seguir:</span><span class="sxs-lookup"><span data-stu-id="b99a7-162">For the second query, calculate the percentage of income after expenses for each year using the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Measures].[Profit Margin] AS   
([Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent"  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="b99a7-163">Essa consulta MDX, como a anterior, possui apenas um membro calculado, `Profit Margin`, e, portanto, não tem complicações com a ordem de resolução.</span><span class="sxs-lookup"><span data-stu-id="b99a7-163">This MDX query, like the previous one, has only a single calculated member, `Profit Margin`, and therefore does not have any solve order complications.</span></span>  
  
 <span data-ttu-id="b99a7-164">Essa consulta MDX produz um conjunto de resultados um pouco diferente, semelhante à tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b99a7-164">This MDX query produces a slightly different result set, similar to the following table.</span></span>  
  
||<span data-ttu-id="b99a7-165">Valor das Vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="b99a7-165">Internet Sales Amount</span></span>|<span data-ttu-id="b99a7-166">Custo Total do Produto da Internet</span><span class="sxs-lookup"><span data-stu-id="b99a7-166">Internet Total Product Cost</span></span>|<span data-ttu-id="b99a7-167">Margem de Lucro</span><span class="sxs-lookup"><span data-stu-id="b99a7-167">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="b99a7-168">**AS 2007**</span><span class="sxs-lookup"><span data-stu-id="b99a7-168">**CY 2007**</span></span>|<span data-ttu-id="b99a7-169">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="b99a7-169">$9,791,060.30</span></span>|<span data-ttu-id="b99a7-170">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="b99a7-170">$5,718,327.17</span></span>|<span data-ttu-id="b99a7-171">41.60%</span><span class="sxs-lookup"><span data-stu-id="b99a7-171">41.60%</span></span>|  
|<span data-ttu-id="b99a7-172">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="b99a7-172">**CY 2008**</span></span>|<span data-ttu-id="b99a7-173">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="b99a7-173">$9,770,899.74</span></span>|<span data-ttu-id="b99a7-174">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="b99a7-174">$5,721,205.24</span></span>|<span data-ttu-id="b99a7-175">41.45%</span><span class="sxs-lookup"><span data-stu-id="b99a7-175">41.45%</span></span>|  
  
 <span data-ttu-id="b99a7-176">A diferença entre os conjuntos de resultados da primeira e da segunda consultas é proveniente da diferença no posicionamento do membro calculado.</span><span class="sxs-lookup"><span data-stu-id="b99a7-176">The difference in result sets between the first query and the second query comes from the difference in placement of the calculated member.</span></span> <span data-ttu-id="b99a7-177">Na primeira consulta, o membro calculado faz parte do eixo ROWS e não no eixo COLUMNS mostrado na segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="b99a7-177">In the first query, the calculated member is part of the ROWS axis, not the COLUMNS axis shown in the second query.</span></span> <span data-ttu-id="b99a7-178">A diferença de posicionamento passa a ser importante na próxima consulta, que combina os dois membros calculados em uma única consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="b99a7-178">This difference in placement becomes important in the next query, which combines the two calculated members in a single MDX query.</span></span>  
  
### <a name="query-3-combined-year-difference-and-net-income-calculations"></a><span data-ttu-id="b99a7-179">Consulta 3 – diferença anual combinada e cálculos de rendimento líquido</span><span class="sxs-lookup"><span data-stu-id="b99a7-179">Query 3-Combined Year Difference and Net Income Calculations</span></span>  
 <span data-ttu-id="b99a7-180">Nessa consulta final, a combinação dos exemplos anteriores em uma única consulta MDX, a ordem de resolução passa a ser importante devido aos cálculos nas colunas e nas linhas.</span><span class="sxs-lookup"><span data-stu-id="b99a7-180">In this final query combining both of the previous examples into a single MDX query, solve order becomes important because of the calculations on both columns and rows.</span></span> <span data-ttu-id="b99a7-181">Para confirmar se os cálculos são feitos na sequência correta, defina a sequência de cálculo usando a palavra-chave `SOLVE_ORDER`.</span><span class="sxs-lookup"><span data-stu-id="b99a7-181">To make sure that the calculations occur in the correct sequence, define the sequence in which the calculations occur by using the `SOLVE_ORDER` keyword.</span></span>  
  
 <span data-ttu-id="b99a7-182">A palavra-chave `SOLVE_ORDER` especifica a ordem de resolução de membros calculados em uma consulta MDX ou em um comando `CREATE MEMBER`.</span><span class="sxs-lookup"><span data-stu-id="b99a7-182">The `SOLVE_ORDER` keyword specifies the solve order of calculated members in an MDX query or a `CREATE MEMBER` command.</span></span> <span data-ttu-id="b99a7-183">Os valores de números inteiros usados com a palavra-chave `SOLVE_ORDER` são relativos, não precisam começar em zero e nem serem consecutivos.</span><span class="sxs-lookup"><span data-stu-id="b99a7-183">The integer values used with the `SOLVE_ORDER` keyword are relative, do not need to start at zero, and do not need to be consecutive.</span></span> <span data-ttu-id="b99a7-184">O valor simplesmente orienta o MDX a calcular um membro com base nos valores derivados do cálculo dos membros com um valor mais alto.</span><span class="sxs-lookup"><span data-stu-id="b99a7-184">The value simply tells MDX to calculate a member based on values derived from calculating members with a higher value.</span></span> <span data-ttu-id="b99a7-185">Se um membro calculado for definido sem a palavra-chave `SOLVE_ORDER`, o valor padrão desse membro calculado será zero.</span><span class="sxs-lookup"><span data-stu-id="b99a7-185">If a calculated member is defined without the `SOLVE_ORDER` keyword, the default value of that calculated member is zero.</span></span>  
  
 <span data-ttu-id="b99a7-186">Por exemplo, se você combinar os cálculos usados nos dois primeiros exemplos de consulta, os dois membros calculados, `Year Difference` e `Profit Margin`, encontram-se em uma intersecção em uma única célula do conjunto de dados do resultado da consulta MDX de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b99a7-186">For example, if you combine the calculations used in the first two example queries, the two calculated members, `Year Difference` and `Profit Margin`, intersect at a single cell in the result dataset of the MDX query example.</span></span> <span data-ttu-id="b99a7-187">A única maneira de determinar como o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] avaliará essa célula é pela ordem de resolução.</span><span class="sxs-lookup"><span data-stu-id="b99a7-187">The only way to determine how [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] will evaluate this cell is by the solve order.</span></span> <span data-ttu-id="b99a7-188">As fórmulas usadas para construir essa célula produzirão resultados diferentes de acordo com a ordem de resolução dos dois membros calculados.</span><span class="sxs-lookup"><span data-stu-id="b99a7-188">The formulas that are used to construct this cell will produce different results depending upon the solve order of the two calculated members.</span></span>  
  
 <span data-ttu-id="b99a7-189">Primeiro, tente combinar os cálculos usados nas duas primeiras consultas na consulta MDX a seguir:</span><span class="sxs-lookup"><span data-stu-id="b99a7-189">First, try combining the calculations used in the first two queries in the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 1  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 2  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="b99a7-190">Neste exemplo de consulta MDX combinada, `Profit Margin` tem a ordem de resolução mais alta, portanto terá precedência quando as duas expressões interagirem.</span><span class="sxs-lookup"><span data-stu-id="b99a7-190">In this combined MDX query example, `Profit Margin` has the highest solve order, so it takes precedence when the two expressions interact.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="b99a7-191">avalia a célula em questão usando a fórmula `Profit Margin` .</span><span class="sxs-lookup"><span data-stu-id="b99a7-191">evaluates the cell in question by using the `Profit Margin` formula.</span></span> <span data-ttu-id="b99a7-192">Os resultados desse cálculo aninhado são mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b99a7-192">The results of this nested calculation, as shown in the following table.</span></span>  
  
||<span data-ttu-id="b99a7-193">Valor das Vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="b99a7-193">Internet Sales Amount</span></span>|<span data-ttu-id="b99a7-194">Custo Total do Produto da Internet</span><span class="sxs-lookup"><span data-stu-id="b99a7-194">Internet Total Product Cost</span></span>|<span data-ttu-id="b99a7-195">Margem de Lucro</span><span class="sxs-lookup"><span data-stu-id="b99a7-195">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="b99a7-196">**AS 2007**</span><span class="sxs-lookup"><span data-stu-id="b99a7-196">**CY 2007**</span></span>|<span data-ttu-id="b99a7-197">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="b99a7-197">$9,791,060.30</span></span>|<span data-ttu-id="b99a7-198">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="b99a7-198">$5,718,327.17</span></span>|<span data-ttu-id="b99a7-199">41.60%</span><span class="sxs-lookup"><span data-stu-id="b99a7-199">41.60%</span></span>|  
|<span data-ttu-id="b99a7-200">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="b99a7-200">**CY 2008**</span></span>|<span data-ttu-id="b99a7-201">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="b99a7-201">$9,770,899.74</span></span>|<span data-ttu-id="b99a7-202">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="b99a7-202">$5,721,205.24</span></span>|<span data-ttu-id="b99a7-203">41.45%</span><span class="sxs-lookup"><span data-stu-id="b99a7-203">41.45%</span></span>|  
|<span data-ttu-id="b99a7-204">**Diferença anual**</span><span class="sxs-lookup"><span data-stu-id="b99a7-204">**Year Difference**</span></span>|<span data-ttu-id="b99a7-205">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="b99a7-205">($20,160.56)</span></span>|<span data-ttu-id="b99a7-206">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="b99a7-206">$2,878.06</span></span>|<span data-ttu-id="b99a7-207">114.28%</span><span class="sxs-lookup"><span data-stu-id="b99a7-207">114.28%</span></span>|  
  
 <span data-ttu-id="b99a7-208">O resultado na célula compartilhada baseia-se na fórmula para `Profit Margin`.</span><span class="sxs-lookup"><span data-stu-id="b99a7-208">The result in the shared cell is based on the formula for `Profit Margin`.</span></span> <span data-ttu-id="b99a7-209">Ou seja, o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calcula o resultado da célula compartilhada com os dados de `Year Difference` , produzindo a fórmula a seguir (o resultado foi arredondado para facilitar a leitura):</span><span class="sxs-lookup"><span data-stu-id="b99a7-209">That is, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell with the `Year Difference` data, producing the following formula (the result is rounded for clarity):</span></span>  
  
```  
((9,770,899.74 - 9,791,060.30) - (5,721,205.24 - 5,718,327.17)) / (9,770,899.74 - 9,791,060.30) = 1.14275744   
```  
  
 <span data-ttu-id="b99a7-210">ou o</span><span class="sxs-lookup"><span data-stu-id="b99a7-210">or</span></span>  
  
```  
(23,038.63) / (20,160.56) = 114.28%  
```  
  
 <span data-ttu-id="b99a7-211">Isso está claramente incorreto.</span><span class="sxs-lookup"><span data-stu-id="b99a7-211">This is clearly incorrect.</span></span> <span data-ttu-id="b99a7-212">No entanto, o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculará o resultado da célula compartilhada de forma diferente se você mudar as ordens de resolução dos membros calculados da consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="b99a7-212">However, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell differently if you switch the solve orders for the calculated members in the MDX query.</span></span> <span data-ttu-id="b99a7-213">A consulta MDX combinada a seguir inverte a ordem de resolução dos membros calculados:</span><span class="sxs-lookup"><span data-stu-id="b99a7-213">The following combined MDX query reverses the solve order for the calculated members:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 2  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 1  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="b99a7-214">Como a ordem dos membros calculados foi alterada, o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] usa a fórmula `Year Difference` para avaliar a célula, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b99a7-214">As the order of the calculated members has been switched, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses the `Year Difference` formula to evaluate the cell, as shown in the following table.</span></span>  
  
||<span data-ttu-id="b99a7-215">Valor das Vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="b99a7-215">Internet Sales Amount</span></span>|<span data-ttu-id="b99a7-216">Custo Total do Produto da Internet</span><span class="sxs-lookup"><span data-stu-id="b99a7-216">Internet Total Product Cost</span></span>|<span data-ttu-id="b99a7-217">Margem de Lucro</span><span class="sxs-lookup"><span data-stu-id="b99a7-217">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="b99a7-218">**AS 2007**</span><span class="sxs-lookup"><span data-stu-id="b99a7-218">**CY 2007**</span></span>|<span data-ttu-id="b99a7-219">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="b99a7-219">$9,791,060.30</span></span>|<span data-ttu-id="b99a7-220">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="b99a7-220">$5,718,327.17</span></span>|<span data-ttu-id="b99a7-221">41.60%</span><span class="sxs-lookup"><span data-stu-id="b99a7-221">41.60%</span></span>|  
|<span data-ttu-id="b99a7-222">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="b99a7-222">**CY 2008**</span></span>|<span data-ttu-id="b99a7-223">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="b99a7-223">$9,770,899.74</span></span>|<span data-ttu-id="b99a7-224">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="b99a7-224">$5,721,205.24</span></span>|<span data-ttu-id="b99a7-225">41.45%</span><span class="sxs-lookup"><span data-stu-id="b99a7-225">41.45%</span></span>|  
|<span data-ttu-id="b99a7-226">**Diferença anual**</span><span class="sxs-lookup"><span data-stu-id="b99a7-226">**Year Difference**</span></span>|<span data-ttu-id="b99a7-227">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="b99a7-227">($20,160.56)</span></span>|<span data-ttu-id="b99a7-228">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="b99a7-228">$2,878.06</span></span>|<span data-ttu-id="b99a7-229">(0.15%)</span><span class="sxs-lookup"><span data-stu-id="b99a7-229">(0.15%)</span></span>|  
  
 <span data-ttu-id="b99a7-230">Como essa consulta usa a fórmula `Year Difference` com os dados de `Profit Margin` , a fórmula da célula compartilhada assemelha-se a este cálculo:</span><span class="sxs-lookup"><span data-stu-id="b99a7-230">Because this query uses the `Year Difference` formula with the `Profit Margin` data, the formula for the shared cell resembles the following calculation:</span></span>  
  
```  
(($9,770,899.74 - 5,721,205.24) / $9,770,899.74) - ((9,791,060.30 - 5,718,327.17) / 9,791,060.30) = -0.15   
```  
  
 <span data-ttu-id="b99a7-231">Ou</span><span class="sxs-lookup"><span data-stu-id="b99a7-231">Or</span></span>  
  
```  
0.4145 - 0.4160= -0.15  
```  
  
## <a name="additional-considerations"></a><span data-ttu-id="b99a7-232">Considerações adicionais</span><span class="sxs-lookup"><span data-stu-id="b99a7-232">Additional Considerations</span></span>  
 <span data-ttu-id="b99a7-233">A ordem de resolução pode ser uma questão bastante complexa com que lidar, especialmente em cubos com um grande número de dimensões envolvendo membro calculado, fórmulas de rollup personalizado ou células calculadas.</span><span class="sxs-lookup"><span data-stu-id="b99a7-233">Solve order can be a very complex issue to deal with, especially in cubes with a high number of dimensions involving calculated member, custom rollup formulas, or calculated cells.</span></span> <span data-ttu-id="b99a7-234">Quando o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] avalia uma consulta MDX, o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] leva em consideração os valores da ordem de resolução de tudo que esteja envolvido em uma determinada passagem, incluindo as dimensões do cubo especificadas na consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="b99a7-234">When [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates an MDX query, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] takes into account the solve order values for everything involved within a given pass, including the dimensions of the cube specified in the MDX query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b99a7-235">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b99a7-235">See Also</span></span>  
 <span data-ttu-id="b99a7-236">[CalculationCurrentPass&#41;MDX &#40;](/sql/mdx/calculationcurrentpass-mdx) </span><span class="sxs-lookup"><span data-stu-id="b99a7-236">[CalculationCurrentPass &#40;MDX&#41;](/sql/mdx/calculationcurrentpass-mdx) </span></span>  
 <span data-ttu-id="b99a7-237">[CalculationPassValue&#41;MDX &#40;](/sql/mdx/calculationpassvalue-mdx) </span><span class="sxs-lookup"><span data-stu-id="b99a7-237">[CalculationPassValue &#40;MDX&#41;](/sql/mdx/calculationpassvalue-mdx) </span></span>  
 <span data-ttu-id="b99a7-238">[Instrução CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="b99a7-238">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 [<span data-ttu-id="b99a7-239">Manipulando dados &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b99a7-239">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
