---
title: Função First (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0914520-30c5-4d63-9b59-8d9342ed63b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cd8578a1d9a17030d603457d4eaadf107316bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573721"
---
# <a name="first-function-report-builder-and-ssrs"></a><span data-ttu-id="e6947-102">Função First (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e6947-102">First Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e6947-103">Retorna o primeiro valor no escopo fornecido da expressão especificada.</span><span class="sxs-lookup"><span data-stu-id="e6947-103">Returns the first value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="e6947-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e6947-104">Syntax</span></span>  
  
```  
  
First(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6947-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="e6947-105">Parameters</span></span>  
 <span data-ttu-id="e6947-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="e6947-106">*expression*</span></span>  
 <span data-ttu-id="e6947-107">(`Variant` ou `Binary`) A expressão na qual executar a agregação, por exemplo, `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="e6947-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="e6947-108">*escopo*</span><span class="sxs-lookup"><span data-stu-id="e6947-108">*scope*</span></span>  
 <span data-ttu-id="e6947-109">(`String`) Opcional.</span><span class="sxs-lookup"><span data-stu-id="e6947-109">(`String`) Optional.</span></span> <span data-ttu-id="e6947-110">O nome de um conjunto de dados, um grupo ou uma região de dados que contém os itens de relatório aos quais a função de agregação deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="e6947-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="e6947-111">Se *scope* não estiver especificado, será usado o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e6947-111">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="e6947-112">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="e6947-112">Return Type</span></span>  
 <span data-ttu-id="e6947-113">Determinado pelo tipo de expressão.</span><span class="sxs-lookup"><span data-stu-id="e6947-113">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6947-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="e6947-114">Remarks</span></span>  
 <span data-ttu-id="e6947-115">A função `First` retorna o primeiro valor em um conjunto de dados depois que toda a classificação e filtragem tiverem sido aplicadas no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="e6947-115">The `First` function returns the first value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="e6947-116">A função `First` não pode ser usada em expressões de filtro de grupo com qualquer coisa, exceto o escopo atual (padrão).</span><span class="sxs-lookup"><span data-stu-id="e6947-116">The `First` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="e6947-117">Também é possível usar a função `First` em um cabeçalho de página para retornar o primeiro valor da coleção `ReportItems` de uma página para produzir cabeçalhos em estilo de dicionário que exibem a primeira e a última entradas em uma página.</span><span class="sxs-lookup"><span data-stu-id="e6947-117">You can also use `First` in a page header to return the first value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="e6947-118">O valor de *scope* deve ser uma constante de cadeia de caracteres e não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="e6947-118">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="e6947-119">Para agregações externas ou que não especificam outras agregações, *scope* deve se referir ao escopo atual ou a um escopo contentor.</span><span class="sxs-lookup"><span data-stu-id="e6947-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="e6947-120">Para agregações de agregações, as agregações aninhadas podem especificar um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="e6947-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="e6947-121">*Expression* pode conter chamadas para funções de agregação aninhadas com as seguintes exceções e condições:</span><span class="sxs-lookup"><span data-stu-id="e6947-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="e6947-122">*Scope* para agregações aninhadas deve ser igual ao escopo da agregação externa ou deve estar contido nela.</span><span class="sxs-lookup"><span data-stu-id="e6947-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="e6947-123">Para todos os escopos distintos na expressão, um escopo deve estar em uma relação filho com todos os outros escopos.</span><span class="sxs-lookup"><span data-stu-id="e6947-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="e6947-124">*Scope* para agregações aninhadas não pode ser o nome de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="e6947-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="e6947-125">A *expressão* não deve conter `First` funções,, `Last` `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="e6947-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="e6947-126">*Expression* não deve conter agregações aninhadas que especifiquem *recursive*.</span><span class="sxs-lookup"><span data-stu-id="e6947-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="e6947-127">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="e6947-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="e6947-128">Para obter mais informações sobre agregações recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e6947-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6947-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e6947-129">Example</span></span>  
 <span data-ttu-id="e6947-130">O exemplo de código a seguir retorna o número do primeiro produto no grupo `Category` de uma região de dados:</span><span class="sxs-lookup"><span data-stu-id="e6947-130">The following code example returns the first product number in the `Category` group of a data region:</span></span>  
  
```  
=First(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6947-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6947-131">See Also</span></span>  
 <span data-ttu-id="e6947-132">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6947-132">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e6947-133">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6947-133">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e6947-134">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e6947-134">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e6947-135">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e6947-135">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
