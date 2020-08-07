---
title: Função Count (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7b50b101-daf8-4fb0-ae04-57384755779f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3617e64d804b6b0f3d9522b5a089f418a942568a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582295"
---
# <a name="count-function-report-builder-and-ssrs"></a><span data-ttu-id="1c7f3-102">função Count (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1c7f3-102">Count Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1c7f3-103">Retorna uma contagem de valores não nulos especificados pela expressão, avaliados no contexto do escopo fornecido.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-103">Returns a count of non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="1c7f3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c7f3-104">Syntax</span></span>  
  
```  
  
Count(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c7f3-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="1c7f3-105">Parameters</span></span>  
 <span data-ttu-id="1c7f3-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="1c7f3-106">*expression*</span></span>  
 <span data-ttu-id="1c7f3-107">(`Variant` ou `Binary`) A expressão na qual executar a agregação, por exemplo, `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="1c7f3-108">*escopo*</span><span class="sxs-lookup"><span data-stu-id="1c7f3-108">*scope*</span></span>  
 <span data-ttu-id="1c7f3-109">(`String`) O nome de um conjunto de dados, grupo ou região de dados que contém os itens do relatório aos quais a função de agregação deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-109">(`String`) The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="1c7f3-110">Se *scope* não estiver especificado, será usado o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-110">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="1c7f3-111">*recursivos*</span><span class="sxs-lookup"><span data-stu-id="1c7f3-111">*recursive*</span></span>  
 <span data-ttu-id="1c7f3-112">(**Enumerated Type**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-112">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="1c7f3-113">`Simple` (padrão) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-113">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="1c7f3-114">Especifica se a agregação deve ser executada recursivamente.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-114">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="1c7f3-115">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="1c7f3-115">Return Type</span></span>  
 <span data-ttu-id="1c7f3-116">Retorna um `Integer`.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-116">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c7f3-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="1c7f3-117">Remarks</span></span>  
 <span data-ttu-id="1c7f3-118">O valor de *scope* deve ser uma constante de cadeia de caracteres e não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-118">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="1c7f3-119">Para agregações externas ou que não especificam outras agregações, *scope* deve se referir ao escopo atual ou a um escopo contentor.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="1c7f3-120">Para agregações de agregações, as agregações aninhadas podem especificar um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="1c7f3-121">*Expression* pode conter chamadas para funções de agregação aninhadas com as seguintes exceções e condições:</span><span class="sxs-lookup"><span data-stu-id="1c7f3-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="1c7f3-122">*Scope* para agregações aninhadas deve ser igual ao escopo da agregação externa ou deve estar contido nela.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="1c7f3-123">Para todos os escopos distintos na expressão, um escopo deve estar em uma relação filho com todos os outros escopos.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="1c7f3-124">*Scope* para agregações aninhadas não pode ser o nome de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="1c7f3-125">A *expressão* não deve conter `First` funções,, `Last` `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="1c7f3-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="1c7f3-126">*Expression* não deve conter agregações aninhadas que especifiquem *recursive*.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="1c7f3-127">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="1c7f3-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="1c7f3-128">Para obter mais informações sobre agregações recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1c7f3-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="1c7f3-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1c7f3-129">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="1c7f3-130">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1c7f3-130">Description</span></span>  
 <span data-ttu-id="1c7f3-131">O seguinte exemplo de código mostra uma expressão que calcula o número de valores não nulos de `Size` para o escopo padrão e para um escopo de grupo pai.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-131">The following code example shows an expression that calculates the number of non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="1c7f3-132">A expressão é adicionada a uma célula em uma linha que pertence ao `GroupbySubcategory`do grupo filho.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="1c7f3-133">O grupo pai é `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="1c7f3-134">A expressão exibe os resultados de `GroupbySubcategory` (o escopo padrão) e de `GroupbyCategory` (o escopo do grupo pai).</span><span class="sxs-lookup"><span data-stu-id="1c7f3-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c7f3-135">As expressões não devem conter retornos de carro reais e quebras de linha. Eles estão incluídos no exemplo para oferecer suporte a processadores de documentação.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example to support documentation renderers.</span></span> <span data-ttu-id="1c7f3-136">Se você copiar o seguinte exemplo, remova os retornos de carro de cada linha.</span><span class="sxs-lookup"><span data-stu-id="1c7f3-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
## <a name="code"></a><span data-ttu-id="1c7f3-137">Código</span><span class="sxs-lookup"><span data-stu-id="1c7f3-137">Code</span></span>  
  
```  
="Count (Subcategory): " & Count(Fields!Size.Value) &   
"Count (Category): " & Count(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c7f3-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1c7f3-138">See Also</span></span>  
 <span data-ttu-id="1c7f3-139">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1c7f3-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1c7f3-140">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1c7f3-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1c7f3-141">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1c7f3-141">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1c7f3-142">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1c7f3-142">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
