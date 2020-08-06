---
title: Sintaxe de filtro de modelo e exemplos (Analysis Services-Mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filter syntax [data mining]
- filters [data mining]
- filters [Analysis Services]
ms.assetid: c729d9b3-8fda-405e-9497-52b2d7493eae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7ca200d179c0fe81b948793a4b4478f71502657
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679101"
---
# <a name="model-filter-syntax-and-examples-analysis-services---data-mining"></a><span data-ttu-id="be002-102">Sintaxe de filtro de modelo e exemplos (Analysis Services - Mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="be002-102">Model Filter Syntax and Examples (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="be002-103">Esta seção fornece informações detalhadas sobre a sintaxe de filtros de modelo, além de expressões de exemplo.</span><span class="sxs-lookup"><span data-stu-id="be002-103">This section provides detailed information about the syntax for model filters, together with sample expressions.</span></span>  
  
 
  
##  <a name="filter-syntax"></a><a name="bkmk_Syntax"></a><span data-ttu-id="be002-104">Sintaxe de filtro</span><span class="sxs-lookup"><span data-stu-id="be002-104">Filter Syntax</span></span>  
 <span data-ttu-id="be002-105">As expressões de filtro geralmente são equivalentes ao conteúdo de uma cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="be002-105">Filter expressions generally are equivalent to the content of a WHERE clause.</span></span> <span data-ttu-id="be002-106">Você pode conectar várias condições usando os operadores lógicos `AND`, `OR` e `NOT`.</span><span class="sxs-lookup"><span data-stu-id="be002-106">You can connect multiple conditions by using the logical operators `AND`, `OR`, and `NOT`.</span></span>  
  
 <span data-ttu-id="be002-107">Em tabelas aninhadas, você também pode usar os operadores `EXISTS` e `NOT EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="be002-107">In nested tables, you can also use the `EXISTS` and `NOT EXISTS` operators.</span></span> <span data-ttu-id="be002-108">Uma condição `EXISTS` será avaliada como `true` se a subconsulta retornar pelo menos uma linha.</span><span class="sxs-lookup"><span data-stu-id="be002-108">An `EXISTS` condition evaluates to `true` if the subquery returns at least one row.</span></span> <span data-ttu-id="be002-109">Isso é útil nos casos em que você deseja restringir o modelo para os casos que contêm um determinado valor na tabela aninhada: por exemplo, os clientes que compraram pelo menos um item uma vez.</span><span class="sxs-lookup"><span data-stu-id="be002-109">This is useful in cases where you want to restrict the model to cases that contain a particular value in the nested table: for example, customers who have purchased an item at least once.</span></span>  
  
 <span data-ttu-id="be002-110">Uma condição `NOT EXISTS` é avaliada como `true` se a condição especificada na subconsulta não existir.</span><span class="sxs-lookup"><span data-stu-id="be002-110">A `NOT EXISTS` condition evaluates to `true` if the condition specified in the subquery does not exist.</span></span> <span data-ttu-id="be002-111">Um exemplo é quando você deseja restringir o modelo a clientes que nunca compraram um determinado item.</span><span class="sxs-lookup"><span data-stu-id="be002-111">An example is when you want to restrict the model to customers who have never purchased a particular item.</span></span>  
  
 <span data-ttu-id="be002-112">A sintaxe geral é:</span><span class="sxs-lookup"><span data-stu-id="be002-112">The general syntax is as follows:</span></span>  
  
```  
<filter>::=<predicate list>  | ( <predicate list> )  
<predicate list>::= <predicate> | [<logical_operator> <predicate list>]   
<logical_operator::= AND| OR  
<predicate>::= NOT <predicate>|( <predicate> ) <avPredicate> | <nestedTablePredicate> | ( <predicate> )   
<avPredicate>::= <columnName> <operator> <scalar> | <columnName> IS [NOT] NULL  
<operator>::= = | != | <> | > | >= | < | <=  
<nestedTablePredicate>::= EXISTS (<subquery>)  
<subquery>::=SELECT * FROM <columnName>[ WHERE  <predicate list> ]  
```  
  
 <span data-ttu-id="be002-113">*sem*</span><span class="sxs-lookup"><span data-stu-id="be002-113">*filter*</span></span>  
 <span data-ttu-id="be002-114">Contém um ou mais predicados, conectados por operadores lógicos.</span><span class="sxs-lookup"><span data-stu-id="be002-114">Contains one or more predicates, connected by logical operators.</span></span>  
  
 <span data-ttu-id="be002-115">*lista de predicados*</span><span class="sxs-lookup"><span data-stu-id="be002-115">*predicate list*</span></span>  
 <span data-ttu-id="be002-116">Uma ou mais expressões de filtro válidas, separadas por operadores lógicos.</span><span class="sxs-lookup"><span data-stu-id="be002-116">One or more valid filter expressions, separated by logical operators.</span></span>  
  
 <span data-ttu-id="be002-117">*columnName*</span><span class="sxs-lookup"><span data-stu-id="be002-117">*columnName*</span></span>  
 <span data-ttu-id="be002-118">O nome de uma coluna de estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="be002-118">The name of a mining structure column.</span></span>  
  
 <span data-ttu-id="be002-119">operador lógico</span><span class="sxs-lookup"><span data-stu-id="be002-119">logical operator</span></span>  
 <span data-ttu-id="be002-120">`AND`, `OR`, `NOT`</span><span class="sxs-lookup"><span data-stu-id="be002-120">`AND`, `OR`, `NOT`</span></span>  
  
 <span data-ttu-id="be002-121">*avPredicate*</span><span class="sxs-lookup"><span data-stu-id="be002-121">*avPredicate*</span></span>  
 <span data-ttu-id="be002-122">Expressão de filtro que pode ser aplicada somente à coluna da estrutura de mineração escalar.</span><span class="sxs-lookup"><span data-stu-id="be002-122">Filter expression that can be applied to scalar mining structure column only.</span></span> <span data-ttu-id="be002-123">Uma expressão *avPredicate* pode ser usada nos filtros de modelo ou filtros de tabelas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="be002-123">An *avPredicate* expression can be used in both model filters or nested table filters.</span></span>  
  
 <span data-ttu-id="be002-124">Uma expressão que usa quaisquer dos operadores a seguir só pode ser aplicada a uma coluna contínua.</span><span class="sxs-lookup"><span data-stu-id="be002-124">An expression that uses any of the following operators can only be applied to a continuous column.</span></span> <span data-ttu-id="be002-125">:</span><span class="sxs-lookup"><span data-stu-id="be002-125">:</span></span>  
  
-   <span data-ttu-id="be002-126">**\<**(menor que)</span><span class="sxs-lookup"><span data-stu-id="be002-126">**\<** (less than)</span></span>  
  
-   <span data-ttu-id="be002-127">**>**(maior que)</span><span class="sxs-lookup"><span data-stu-id="be002-127">**>** (greater than)</span></span>  
  
-   <span data-ttu-id="be002-128">**>=**(maior ou igual a)</span><span class="sxs-lookup"><span data-stu-id="be002-128">**>=** (greater than or equal to)</span></span>  
  
-   <span data-ttu-id="be002-129">**\<=**(menor que ou igual a)</span><span class="sxs-lookup"><span data-stu-id="be002-129">**\<=** (less than or equal to)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be002-130">Independentemente do tipo de dados, esses operadores não podem ser aplicados a uma coluna que tenha o tipo `Discrete`, `Discretized` ou `Key`.</span><span class="sxs-lookup"><span data-stu-id="be002-130">Regardless of the data type, these operators cannot be applied to a column that has the type `Discrete`, `Discretized`, or `Key`.</span></span>  
  
 <span data-ttu-id="be002-131">Uma expressão que usa quaisquer dos operadores a seguir só pode ser aplicada a uma coluna contínua, discreta, distinta ou chave:</span><span class="sxs-lookup"><span data-stu-id="be002-131">An expression that uses any of the following operators can be applied to a continuous, discrete, discretized, or key column:</span></span>  
  
-   <span data-ttu-id="be002-132">**=** seja</span><span class="sxs-lookup"><span data-stu-id="be002-132">**=** (equals)</span></span>  
  
-   <span data-ttu-id="be002-133">**! =** (diferente de)</span><span class="sxs-lookup"><span data-stu-id="be002-133">**!=** (not equal to)</span></span>  
  
-   <span data-ttu-id="be002-134">**É NULO**</span><span class="sxs-lookup"><span data-stu-id="be002-134">**IS NULL**</span></span>  
  
 <span data-ttu-id="be002-135">Se o argumento *avPredicate*for aplicado a uma coluna de dados discretos, o valor usado no filtro poderá ser qualquer valor em um bloco específico.</span><span class="sxs-lookup"><span data-stu-id="be002-135">If the argument, *avPredicate*, applies to a discretized column, the value used in the filter can be any value in a specific bucket.</span></span>  
  
 <span data-ttu-id="be002-136">Em outras palavras, você não define a condição como `AgeDisc = '25-35'`, mas calcula e usa um valor desse intervalo.</span><span class="sxs-lookup"><span data-stu-id="be002-136">In other words, you do not define the condition as `AgeDisc = '25-35'`, but instead compute and then use a value from that interval.</span></span>  
  
 <span data-ttu-id="be002-137">Exemplo:  `AgeDisc = 27`  significa que qualquer valor no mesmo intervalo como 27, que nesse caso é de 25 a 35.</span><span class="sxs-lookup"><span data-stu-id="be002-137">Example:  `AgeDisc = 27`  means any value in the same interval as 27, which in this case is 25-35.</span></span>  
  
 <span data-ttu-id="be002-138">*nestedTablePredicate*</span><span class="sxs-lookup"><span data-stu-id="be002-138">*nestedTablePredicate*</span></span>  
 <span data-ttu-id="be002-139">A expressão filtrada aplicada a uma tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="be002-139">Filter expression that applies to a nested table.</span></span> <span data-ttu-id="be002-140">Pode ser usado somente nos filtros de modelo.</span><span class="sxs-lookup"><span data-stu-id="be002-140">Can be used in model filters only.</span></span>  
  
 <span data-ttu-id="be002-141">O argumento de subconsulta do argumento *nestedTablePredicate*só pode ser aplicada a uma coluna de estrutura de mineração de tabela</span><span class="sxs-lookup"><span data-stu-id="be002-141">The sub-query argument of the argument, *nestedTablePredicate*, can only apply to a table mining structure column</span></span>  
  
 <span data-ttu-id="be002-142">subconsulta</span><span class="sxs-lookup"><span data-stu-id="be002-142">subquery</span></span>  
 <span data-ttu-id="be002-143">Uma instrução SELECT seguida por um predicado válido ou lista de predicados.</span><span class="sxs-lookup"><span data-stu-id="be002-143">A SELECT statement followed by a valid predicate or list of predicates.</span></span>  
  
 <span data-ttu-id="be002-144">Todos os predicados devem ser do tipo descrito em *avPredicates*.</span><span class="sxs-lookup"><span data-stu-id="be002-144">All the predicates must be of the type described in *avPredicates*.</span></span> <span data-ttu-id="be002-145">Além disso, os predicados só podem se referir a colunas incluídas na tabela aninhada atual, identificada pelo argumento, *columnName*.</span><span class="sxs-lookup"><span data-stu-id="be002-145">Furthermore, the predicates can refer only to columns that are included in the current nested table, identified by the argument, *columnName*.</span></span>  
  
### <a name="limitations-on-filter-syntax"></a><span data-ttu-id="be002-146">Limitações na sintaxe do filtro</span><span class="sxs-lookup"><span data-stu-id="be002-146">Limitations on Filter Syntax</span></span>  
 <span data-ttu-id="be002-147">As restrições a seguir se aplicam a filtros:</span><span class="sxs-lookup"><span data-stu-id="be002-147">The following restrictions apply to filters:</span></span>  
  
-   <span data-ttu-id="be002-148">Um filtro pode conter somente predicados simples.</span><span class="sxs-lookup"><span data-stu-id="be002-148">A filter can contain only simple predicates.</span></span> <span data-ttu-id="be002-149">Esses incluem os operadores matemáticos, escalares e nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="be002-149">These include mathematical operators, scalars, and column names.</span></span>  
  
-   <span data-ttu-id="be002-150">Funções definidas pelo usuário não são suportadas na sintaxe de filtro.</span><span class="sxs-lookup"><span data-stu-id="be002-150">User-defined functions are not supported in the filter syntax.</span></span>  
  
-   <span data-ttu-id="be002-151">Operadores não boolianos, como os sinais de mais ou menos, não são suportados na sintaxe de filtro.</span><span class="sxs-lookup"><span data-stu-id="be002-151">Non-Boolean operators, such as the plus or minus signs, are not supported in the filter syntax.</span></span>  
  
## <a name="examples-of-filters"></a><span data-ttu-id="be002-152">Exemplos de filtros</span><span class="sxs-lookup"><span data-stu-id="be002-152">Examples of Filters</span></span>  
 <span data-ttu-id="be002-153">Os exemplos a seguir demonstram o uso de filtros aplicados a um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="be002-153">The following examples demonstrate the use of filters applied to a mining model.</span></span> <span data-ttu-id="be002-154">Se você criar a expressão de filtro usando [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na janela **Propriedade** e o painel **Expressão** da caixa de diálogo de filtro, você verá somente a cadeia exibida depois das palavras-chave WITH FILTER.</span><span class="sxs-lookup"><span data-stu-id="be002-154">If you create the filter expression by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Property** window and the **Expression** pane of the filter dialog box, you would see only the string that appears after the WITH FILTER keywords.</span></span> <span data-ttu-id="be002-155">A seguir, a definição da estrutura de mineração incluída para facilitar o entendimento do tipo de coluna e uso.</span><span class="sxs-lookup"><span data-stu-id="be002-155">Here, the definition of the mining structure is included to make it easier to understand the column type and usage.</span></span>  
  
###  <a name="example-1-typical-case-level-filtering"></a><a name="bkmk_Ex1"></a><span data-ttu-id="be002-156">Exemplo 1: filtragem de nível de caso típica</span><span class="sxs-lookup"><span data-stu-id="be002-156">Example 1: Typical Case-Level Filtering</span></span>  
 <span data-ttu-id="be002-157">Esse exemplo mostra um simples filtro que restringe os casos usados no modelo para clientes cuja ocupação seja arquiteto e cuja idade seja mais de 30 anos.</span><span class="sxs-lookup"><span data-stu-id="be002-157">This example shows a simple filter that restricts the cases used in the model to customers whose occupation is architect and whose age is over 30.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_1  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH FILTER (Age > 30 AND Occupation='Architect')  
```  
  

  
###  <a name="example-2-case-level-filtering-using-nested-table-attributes"></a><a name="bkmk_Ex2"></a><span data-ttu-id="be002-158">Exemplo 2: filtragem de nível de caso usando atributos de tabela aninhada</span><span class="sxs-lookup"><span data-stu-id="be002-158">Example 2: Case-Level Filtering using Nested Table Attributes</span></span>  
 <span data-ttu-id="be002-159">Se sua estrutura de mineração contiver tabelas aninhadas, você poderá filtrar pela existência de um valor em uma tabela aninhada ou filtrar pelas linhas da tabela aninhada que contêm um valor específico.</span><span class="sxs-lookup"><span data-stu-id="be002-159">If your mining structure contains nested tables, you can either filter on the existence of a value in a nested table, or filter on nested table rows that contain a specific value.</span></span> <span data-ttu-id="be002-160">Esse exemplo restringe os casos usados para o modelo para clientes com mais de 30 anos que fizeram pelo menos uma compra que incluísse leite.</span><span class="sxs-lookup"><span data-stu-id="be002-160">This example restricts the cases used for the model to customers over the age of 30 who made at least one purchase that included milk.</span></span>  
  
 <span data-ttu-id="be002-161">Como esse exemplo mostra, não é necessário que o filtro use somente colunas incluídas no modelo.</span><span class="sxs-lookup"><span data-stu-id="be002-161">As this example shows, it is not necessary that the filter use only columns that are included in the model.</span></span> <span data-ttu-id="be002-162">A tabela aninhada **Produtos** faz parte da estrutura de mineração, mas não está incluída no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="be002-162">The nested table **Products** is part of the mining structure, but is not included in the mining model.</span></span> <span data-ttu-id="be002-163">No entanto, você ainda pode filtrar por valores e atributos na tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="be002-163">However, you can still filter on values and attributes in the nested table.</span></span> <span data-ttu-id="be002-164">Para exibir os detalhes desses casos, o detalhamento deve ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="be002-164">To view the details of these cases, drillthrough must be enabled.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_2  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH DRILLTHROUGH,   
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk')  
)  
```  
  
 
  
###  <a name="example-3-case-level-filtering-on-multiple-nested-table-attributes"></a><a name="bkmk_Ex3"></a><span data-ttu-id="be002-165">Exemplo 3: filtragem de nível de caso em vários atributos de tabela aninhada</span><span class="sxs-lookup"><span data-stu-id="be002-165">Example 3: Case-Level Filtering on Multiple Nested Table Attributes</span></span>  
 <span data-ttu-id="be002-166">Esse exemplo mostra um filtro de três partes: uma condição aplicada à tabela de casos, outra condição para um atributo na tabela aninhada e outra condição em um valor específico em uma das colunas da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="be002-166">This example shows a three-part filter: a condition applies to the case table, another condition to an attribute in the nested table, and another condition on a specific value in one of the nested table columns.</span></span>  
  
 <span data-ttu-id="be002-167">A primeira condição no filtro, `Age > 30`, é aplicada a uma coluna na tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="be002-167">The first condition in the filter, `Age > 30`, applies to a column in the case table.</span></span> <span data-ttu-id="be002-168">As outras condições são aplicadas à tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="be002-168">The remaining conditions apply to the nested table.</span></span>  
  
 <span data-ttu-id="be002-169">A segunda condição, o `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`verifica a presença de, pelo menos, uma compra na tabela aninhada que inclua leite.</span><span class="sxs-lookup"><span data-stu-id="be002-169">The second condition, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, checks for the presence of at least one purchase in the nested table that included milk.</span></span> <span data-ttu-id="be002-170">A terceira condição, `Quantity>=2`, significa que o cliente deve ter comprado pelo menos duas unidades de leite em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="be002-170">The third condition, `Quantity>=2`, means that the customer must have purchased at least two units of milk in a single transaction.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_3  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
)  
)  
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk'  AND Quantity >= 2)   
)  
```  
  

  
###  <a name="example-4-case-level-filtering-on-absence-of-nested-table-attributes"></a><a name="bkmk_Ex4"></a><span data-ttu-id="be002-171">Exemplo 4: filtragem de nível de caso na ausência de atributos de tabela aninhada</span><span class="sxs-lookup"><span data-stu-id="be002-171">Example 4: Case-Level Filtering On Absence of Nested Table Attributes</span></span>  
 <span data-ttu-id="be002-172">Esse exemplo mostra como limitar os casos para o cliente que não comprou um item específico, filtrando pela ausência de um atributo na tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="be002-172">This example shows how to limit cases to customer who did not purchase a specific item, by filtering on the absence of an attribute in the nested table.</span></span> <span data-ttu-id="be002-173">Nesse exemplo, o modelo é treinado usando clientes com mais de 30 anos que nunca compraram leite.</span><span class="sxs-lookup"><span data-stu-id="be002-173">In this example, the model is trained using customers over the age of 30 who have never bought milk.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_4  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName  
)  
)  
FILTER (Age > 30 AND NOT EXISTS (SELECT * FROM Products WHERE ProductName='Milk') )  
```  
  

  
###  <a name="example-5-filtering-on-multiple-nested-table-values"></a><a name="bkmk_Ex5"></a><span data-ttu-id="be002-174">Exemplo 5: filtragem em vários valores de tabela aninhada</span><span class="sxs-lookup"><span data-stu-id="be002-174">Example 5: Filtering on Multiple Nested Table Values</span></span>  
 <span data-ttu-id="be002-175">O objetivo do exemplo é mostrar a filtragem de tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="be002-175">The purpose of the example is to show nested table filtering.</span></span> <span data-ttu-id="be002-176">O filtro da tabela aninhada é aplicado depois do filtro de caso e só restringe as linhas da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="be002-176">The nested table filter is applied after the case filter, and only restricts nested table rows.</span></span>  
  
 <span data-ttu-id="be002-177">Esse modelo pode conter vários casos com tabelas aninhadas vazias porque EXISTS não está especificado.</span><span class="sxs-lookup"><span data-stu-id="be002-177">This model could contain multiple cases with empty nested tables because EXISTS is not specified.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_5  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
WITH DRILLTHROUGH  
```  
  

  
###  <a name="example-6-filtering-on-nested-table-attributes-and-exists"></a><a name="bkmk_Ex6"></a><span data-ttu-id="be002-178">Exemplo 6: filtragem em atributos de tabela aninhada e existe</span><span class="sxs-lookup"><span data-stu-id="be002-178">Example 6: Filtering on Nested Table Attributes and EXISTS</span></span>  
 <span data-ttu-id="be002-179">Nesse exemplo, o filtro na tabela aninhada restringe as linhas para aquelas que contêm leite ou garrafa de água.</span><span class="sxs-lookup"><span data-stu-id="be002-179">In this example, the filter on the nested table restricts the rows to those that contain either milk or bottled water.</span></span> <span data-ttu-id="be002-180">Em seguida, os casos no modelo são restringidos usando uma instrução `EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="be002-180">Then, the cases in the model are restricted by using an `EXISTS` statement.</span></span> <span data-ttu-id="be002-181">Isso garante que a tabela aninhada não está vazia.</span><span class="sxs-lookup"><span data-stu-id="be002-181">This makes sure that the nested table is not empty.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_6  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
FILTER (EXISTS (Products))  
```  
  

  
###  <a name="example-7-complex-filter-combinations"></a><a name="bkmk_Ex7"></a><span data-ttu-id="be002-182">Exemplo 7: combinações de filtros complexos</span><span class="sxs-lookup"><span data-stu-id="be002-182">Example 7: Complex Filter Combinations</span></span>  
 <span data-ttu-id="be002-183">O cenário desse modelo se assemelha a do Exemplo 4, mas é muito mais complexo.</span><span class="sxs-lookup"><span data-stu-id="be002-183">The scenario for this model resembles that of Example 4, but is far more complex.</span></span> <span data-ttu-id="be002-184">A tabela aninhada, **ProductsOnSale**, tem a condição de filtro, o `(OnSale)` que significa que o valor de **onsale** deve ser `true` para o produto listado em **ProductName**.</span><span class="sxs-lookup"><span data-stu-id="be002-184">The nested table, **ProductsOnSale**, has the filter condition `(OnSale)` meaning that the value of **OnSale** must be `true` for the product listed in **ProductName**.</span></span> <span data-ttu-id="be002-185">Aqui, **OnSale** é uma coluna de estrutura.</span><span class="sxs-lookup"><span data-stu-id="be002-185">Here, **OnSale** is a structure column.</span></span>  
  
 <span data-ttu-id="be002-186">A segunda parte do filtro, para **ProductsNotOnSale**, repete essa sintaxe, mas filtra em produtos para os quais o valor de **onsale** é `not true``(!OnSale)` .</span><span class="sxs-lookup"><span data-stu-id="be002-186">The second part of the filter, for **ProductsNotOnSale**, repeats this syntax, but filters on products for which the value of **OnSale** is `not true``(!OnSale)`.</span></span>  
  
 <span data-ttu-id="be002-187">Por fim, as condições são combinadas e uma única restrição adicional é adicionada à tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="be002-187">Finally, the conditions are combined and one additional restriction is added to the case table.</span></span> <span data-ttu-id="be002-188">O resultado é prever compras de produtos na lista **ProductsNotOnSale** , com base nos casos incluídos na lista **ProductsOnSale** , para todos os clientes com mais de 25 anos.</span><span class="sxs-lookup"><span data-stu-id="be002-188">The result is to predict purchases of products in the **ProductsNotOnSale** list, based on the cases that are included in the **ProductsOnSale** list, for all customers over the age of 25.</span></span>  
  
 `ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_7`  
  
 `(`  
  
 `CustomerId,`  
  
 `Age,`  
  
 `Occupation,`  
  
 `MaritalStatus,`  
  
 `ProductsOnSale`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(OnSale),`  
  
 `ProductsNotOnSale PREDICT ONLY`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(!OnSale)`  
  
 `)`  
  
 `WITH DRILLTHROUGH,`  
  
 `FILTER (EXISTS (ProductsOnSale) AND EXISTS(ProductsNotOnSale) AND Age > 25)`  
  
  
  
###  <a name="example-8-filtering-on-dates"></a><a name="bkmk_Ex8"></a><span data-ttu-id="be002-189">Exemplo 8: filtrando em datas</span><span class="sxs-lookup"><span data-stu-id="be002-189">Example 8: Filtering on Dates</span></span>  
 <span data-ttu-id="be002-190">É possível filtrar colunas de entrada por datas, como você faria com qualquer outro dado.</span><span class="sxs-lookup"><span data-stu-id="be002-190">You can filter input columns on dates, as you would any other data.</span></span> <span data-ttu-id="be002-191">As datas contidas em uma coluna de tipo de data/hora são valores contínuos; por isso, é possível especificar um intervalo de datas usando-se operadores como maior que (>) ou menos que (<).</span><span class="sxs-lookup"><span data-stu-id="be002-191">Dates contained in a column of type date/time are continuous values; therefore, you can specify a date range by using operators such as greater than (>) or less than (<).</span></span> <span data-ttu-id="be002-192">Se a fonte de dados não representar datas por um tipo de dados Contínuo, mas como valores discretos ou de texto, não será possível filtrar por um intervalo de datas, e você deverá especificar valores discretos individuais.</span><span class="sxs-lookup"><span data-stu-id="be002-192">If your data source does not represent dates by a Continuous data type, but as discrete or text values, you cannot filter on a date range, but must specify individual discrete values.</span></span>  
  
 <span data-ttu-id="be002-193">No entanto, não será possível criar um filtro na coluna de data em um modelo de série temporal se a coluna de data usada para o filtro também for a coluna de chave do modelo.</span><span class="sxs-lookup"><span data-stu-id="be002-193">However, you cannot create a filter on the date column in a time series model if the date column used for the filter is also the key column for the model.</span></span> <span data-ttu-id="be002-194">Isso porque, em modelos de série temporal e modelos MSC, a coluna de data pode ser manipulada como o tipo `KeyTime` ou `KeySequence`.</span><span class="sxs-lookup"><span data-stu-id="be002-194">That is because, in time series models and sequence clustering models, the date column might be handled as type `KeyTime` or `KeySequence`.</span></span>  
  
 <span data-ttu-id="be002-195">Se precisar filtrar por datas contínuas em um modelo de série temporal, você poderá criar uma cópia da coluna na estrutura de mineração e filtrar o modelo na nova coluna.</span><span class="sxs-lookup"><span data-stu-id="be002-195">If you need to filter on continuous dates in a time series model, you can create a copy of the column in the mining structure, and filter the model on the new column.</span></span>  
  
 <span data-ttu-id="be002-196">Por exemplo, a expressão a seguir representa um filtro em uma coluna de data do tipo `Continuous` que foi adicionado ao modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="be002-196">For example, the following expression represents a filter on a date column of type `Continuous` that has been added to the Forecasting model.</span></span>  
  
 `=[DateCopy] > '12:31:2003:00:00:00'`  
  
> [!NOTE]  
>  <span data-ttu-id="be002-197">Observe que qualquer coluna extra adicionada ao modelo pode afetar os resultados.</span><span class="sxs-lookup"><span data-stu-id="be002-197">Note that any extra columns that you add to the model might affect the results.</span></span> <span data-ttu-id="be002-198">Por isso, se não quiser usar a coluna na computação da série, você só deverá adicionar a coluna à estrutura de mineração, e não ao modelo.</span><span class="sxs-lookup"><span data-stu-id="be002-198">Therefore, if you do not want the column to be used in computation of the series, you should add the column only to the mining structure, and not to the model.</span></span> <span data-ttu-id="be002-199">Também é possível definir o sinalizador de modelo na coluna como `PredictOnly` ou `Ignore`.</span><span class="sxs-lookup"><span data-stu-id="be002-199">You can also set the model flag on the column to `PredictOnly` or to `Ignore`.</span></span> <span data-ttu-id="be002-200">Para obter mais informações, consulte [Sinalizadores de modelagem &#40;Mineração de dados&#41;](modeling-flags-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="be002-200">For more information, see [Modeling Flags &#40;Data Mining&#41;](modeling-flags-data-mining.md).</span></span>  
  
 <span data-ttu-id="be002-201">Para outros tipos de modelo, é possível usar datas como critérios de entrada ou de filtro exatamente como você faria em qualquer outra coluna.</span><span class="sxs-lookup"><span data-stu-id="be002-201">For other model types, you can use dates as input criteria or filter criteria just like you would in any other column.</span></span> <span data-ttu-id="be002-202">No entanto, se precisar usar um nível específico de granularidade não suportado por um tipo de dados `Continuous`, você poderá criar um valor derivado na fonte de dados usando expressões para extrair a unidade a ser usada na filtragem e na análise.</span><span class="sxs-lookup"><span data-stu-id="be002-202">However, if you need to use a specific level of granularity that is not supported by a `Continuous` data type, you can create a derived value in the data source by using expressions to extract the unit to use in filtering and analysis.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="be002-203">Ao especificar uma data como critério de filtro, você deve usar o formato a seguir, independentemente do formato de data do SO atual: `mm/dd/yyyy`.</span><span class="sxs-lookup"><span data-stu-id="be002-203">When you specify a dates as filter criteria, you must use the following format, regardless of the date format for the current OS: `mm/dd/yyyy`.</span></span> <span data-ttu-id="be002-204">Qualquer outro formato resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="be002-204">Any other format results in an error.</span></span>  
  
 <span data-ttu-id="be002-205">Por exemplo, se você quiser filtrar os resultados da central de atendimento para mostrar apenas fins de semana, será possível criar uma expressão na exibição da fonte de dados que extrai o nome do dia da semana para cada data e, em seguida, usar o valor do nome desse dia da semana para entrada ou como um valor discreto na filtragem.</span><span class="sxs-lookup"><span data-stu-id="be002-205">For example, if you want to filter your call center results to show only weekends, you can create an expression in the data source view that extracts the weekday name for each date, and then use that weekday name value for input or as a discrete value in filtering.</span></span> <span data-ttu-id="be002-206">Basta se lembrar de que, como valores repetidos podem afetar o modelo, você só deve usar uma das colunas, e não a coluna de data mais o valor derivado.</span><span class="sxs-lookup"><span data-stu-id="be002-206">Just remember that repeating values can affect the model, so you should use only one of the columns, not the date column plus the derived value.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="be002-207">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="be002-207">See Also</span></span>  
 <span data-ttu-id="be002-208">[Filtros para modelos de mineração &#40;mineração de dados Analysis Services&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="be002-208">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="be002-209">Teste e validação &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="be002-209">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
  
