---
title: Função Previous (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3891deec3f152cdf46da77a7f2d11d38387c5c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573707"
---
# <a name="previous-function-report-builder-and-ssrs"></a><span data-ttu-id="dc780-102">Função Previous (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="dc780-102">Previous Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dc780-103">Retorna o valor ou o valor de agregação especificado para a instância anterior de um item do escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="dc780-103">Returns the value or the specified aggregate value for the previous instance of an item within the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="dc780-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dc780-104">Syntax</span></span>  
  
```  
  
Previous(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc780-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="dc780-105">Parameters</span></span>  
 <span data-ttu-id="dc780-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="dc780-106">*expression*</span></span>  
 <span data-ttu-id="dc780-107">(`Variant` ou `Binary`) A expressão a ser usada para identificar os dados para os quais o valor anterior deve ser recuperado, por exemplo, `Fields!Fieldname.Value` ou `Sum(Fields!Fieldname.Value)`.</span><span class="sxs-lookup"><span data-stu-id="dc780-107">(`Variant` or `Binary`) The expression to use to identify the data and for which to retrieve the previous value, for example, `Fields!Fieldname.Value` or `Sum(Fields!Fieldname.Value)`.</span></span>  
  
 <span data-ttu-id="dc780-108">*escopo*</span><span class="sxs-lookup"><span data-stu-id="dc780-108">*scope*</span></span>  
 <span data-ttu-id="dc780-109">(`String`) Opcional.</span><span class="sxs-lookup"><span data-stu-id="dc780-109">(`String`) Optional.</span></span> <span data-ttu-id="dc780-110">O nome de um grupo ou região de dados, ou NULL ( `Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ), que especifica o escopo do qual recuperar o valor anterior especificado pela *expressão*.</span><span class="sxs-lookup"><span data-stu-id="dc780-110">The name of a group or data region, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the scope from which to retrieve the previous value specified by *expression*.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="dc780-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="dc780-111">Return Type</span></span>  
 <span data-ttu-id="dc780-112">Retorna uma `Variant` ou um `Binary`.</span><span class="sxs-lookup"><span data-stu-id="dc780-112">Returns a `Variant` or `Binary`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc780-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="dc780-113">Remarks</span></span>  
 <span data-ttu-id="dc780-114">A função `Previous` retorna o valor anterior para a expressão avaliada no escopo especificado depois que toda a classificação e filtragem tiverem sido aplicadas.</span><span class="sxs-lookup"><span data-stu-id="dc780-114">The `Previous` function returns the previous value for the expression evaluated in the specified scope after all sorting and filtering have been applied.</span></span>  
  
 <span data-ttu-id="dc780-115">Se a *expressão* não contiver uma agregação, a `Previous` função será padronizada para o escopo atual do item de relatório.</span><span class="sxs-lookup"><span data-stu-id="dc780-115">If *expression* does not contain an aggregate, the `Previous` function defaults to the current scope for the report item.</span></span>  
  
 <span data-ttu-id="dc780-116">Em um grupo de detalhes, use `Previous` para especificar o valor de uma referência de campo na instância anterior da linha de detalhes.</span><span class="sxs-lookup"><span data-stu-id="dc780-116">In a details group, use `Previous` to specify the value of a field reference in the previous instance of the detail row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc780-117">A `Previous` função dá suporte apenas a referências de campo no grupo de detalhes.</span><span class="sxs-lookup"><span data-stu-id="dc780-117">The `Previous` function only supports field references in the details group.</span></span> <span data-ttu-id="dc780-118">Por exemplo, em uma caixa de texto no grupo de detalhes, `=Previous(Fields!Quantity.Value)` retorna os dados para o campo `Quantity` da linha anterior.</span><span class="sxs-lookup"><span data-stu-id="dc780-118">For example, in a text box in the details group, `=Previous(Fields!Quantity.Value)` returns the data for the field `Quantity` from the previous row.</span></span> <span data-ttu-id="dc780-119">Na primeira linha, esta expressão retorna um nulo (`Nothing` em [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="dc780-119">In the first row, this expression returns a null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  
  
 <span data-ttu-id="dc780-120">Se *expression* contiver uma função de agregação que usa um escopo padrão, `Previous` o agregará os dados dentro da instância anterior do escopo especificado na chamada de função de agregação.</span><span class="sxs-lookup"><span data-stu-id="dc780-120">If *expression* contains an aggregate function that uses a default scope, `Previous` aggregates the data within the previous instance of the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="dc780-121">Se *expression* contiver uma função de agregação que especifique um escopo diferente do padrão, o parâmetro de *escopo* da `Previous` função deverá ser um escopo de contenção para o escopo especificado na chamada de função de agregação.</span><span class="sxs-lookup"><span data-stu-id="dc780-121">If *expression* contains an aggregate function that specifies a scope other than the default, the *scope* parameter for the `Previous` function must be a containing scope for the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="dc780-122">As funções `Level` , `InScope` `Aggregate` e `Previous` não podem ser usadas no parâmetro *expression*.</span><span class="sxs-lookup"><span data-stu-id="dc780-122">The functions `Level`, `InScope`, `Aggregate` and `Previous` cannot be used in the *expression*parameter.</span></span> <span data-ttu-id="dc780-123">Não há suporte para a especificação do parâmetro *recursive* para qualquer função de agregação.</span><span class="sxs-lookup"><span data-stu-id="dc780-123">Specifying the *recursive* parameter for any aggregate function is not supported.</span></span>  
  
 <span data-ttu-id="dc780-124">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="dc780-124">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="dc780-125">Exemplos</span><span class="sxs-lookup"><span data-stu-id="dc780-125">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="dc780-126">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="dc780-126">Description</span></span>  
 <span data-ttu-id="dc780-127">O exemplo de código a seguir, quando colocado na linha de dados padrão de uma região de dados, fornece o valor do campo `LineTotal` na linha anterior.</span><span class="sxs-lookup"><span data-stu-id="dc780-127">The following code example, when placed in the default data row of a data region, provides the value for the field `LineTotal` in the previous row.</span></span>  
  
### <a name="code"></a><span data-ttu-id="dc780-128">Código</span><span class="sxs-lookup"><span data-stu-id="dc780-128">Code</span></span>  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### <a name="description"></a><span data-ttu-id="dc780-129">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="dc780-129">Description</span></span>  
 <span data-ttu-id="dc780-130">O exemplo a seguir mostra uma expressão que calcula a soma das vendas em um dia específico do mês e o valor anterior para esse dia do mês em um ano anterior.</span><span class="sxs-lookup"><span data-stu-id="dc780-130">The following example shows an expression that calculates the sum of sales on a specific day of the month and the previous value for that day of the month in a previous year.</span></span> <span data-ttu-id="dc780-131">A expressão é adicionada a uma célula em uma linha que pertence ao `GroupbyDay`do grupo filho.</span><span class="sxs-lookup"><span data-stu-id="dc780-131">The expression is added to a cell in a row that belongs to the child group `GroupbyDay`.</span></span> <span data-ttu-id="dc780-132">Seu grupo pai é `GroupbyMonth`, que tem um grupo pai `GroupbyYear`.</span><span class="sxs-lookup"><span data-stu-id="dc780-132">Its parent group is `GroupbyMonth`, which has a parent group `GroupbyYear`.</span></span> <span data-ttu-id="dc780-133">A expressão exibe os resultados de GroupbyDay (o escopo padrão) e de `GroupbyYear` (o pai do grupo pai `GroupbyMonth`).</span><span class="sxs-lookup"><span data-stu-id="dc780-133">The expression displays the results for GroupbyDay (the default scope) and then for `GroupbyYear` (the parent of the parent group `GroupbyMonth`).</span></span>  
  
 <span data-ttu-id="dc780-134">Por exemplo, para uma região de dados com um grupo pai chamado `Year`, seu grupo filho chamado `Month`e seu grupo filho chamado `Day` (3 níveis aninhados).</span><span class="sxs-lookup"><span data-stu-id="dc780-134">For example, for a data region with a parent group named `Year`, its child group named `Month`, and its child group named `Day` (3 nested levels).</span></span> <span data-ttu-id="dc780-135">A expressão `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` em uma linha associada ao grupo `Day` retorna o valor das vendas para o mesmo dia e mês do ano anterior.</span><span class="sxs-lookup"><span data-stu-id="dc780-135">The expression `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in a row associated with the group `Day` returns the sales value for the same day and month for the previous year.</span></span>  
  
### <a name="code"></a><span data-ttu-id="dc780-136">Código</span><span class="sxs-lookup"><span data-stu-id="dc780-136">Code</span></span>  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc780-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc780-137">See Also</span></span>  
 <span data-ttu-id="dc780-138">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc780-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dc780-139">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc780-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dc780-140">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc780-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dc780-141">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc780-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
