---
title: Função Last (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 123b78a0-d6c9-4f78-b0e7-73b21854a250
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c343e72e476d4a717ca551eedeb0f02650479ca4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573718"
---
# <a name="last-function-report-builder-and-ssrs"></a><span data-ttu-id="76905-102">Função Last (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="76905-102">Last Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="76905-103">Retorna o último valor no escopo fornecido da expressão especificada.</span><span class="sxs-lookup"><span data-stu-id="76905-103">Returns the last value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="76905-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="76905-104">Syntax</span></span>  
  
```  
  
Last(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76905-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="76905-105">Parameters</span></span>  
 <span data-ttu-id="76905-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="76905-106">*expression*</span></span>  
 <span data-ttu-id="76905-107">(`Variant` ou `Binary`) A expressão na qual executar a agregação, por exemplo, `=Fields!Fieldname.Value`.</span><span class="sxs-lookup"><span data-stu-id="76905-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!Fieldname.Value`.</span></span>  
  
 <span data-ttu-id="76905-108">*escopo*</span><span class="sxs-lookup"><span data-stu-id="76905-108">*scope*</span></span>  
 <span data-ttu-id="76905-109">(`String`) (Opcional) O nome de um conjunto de dados, região de dados ou grupo que contém os itens do relatório aos quais a função de agregação deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="76905-109">(`String`) (Optional) The name of a dataset, data region, or group that contains the report items to which to apply the function.</span></span> <span data-ttu-id="76905-110">Se *scope* não estiver especificado, será usado o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="76905-110">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="76905-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="76905-111">Return Type</span></span>  
 <span data-ttu-id="76905-112">Determinado pelo tipo de expressão.</span><span class="sxs-lookup"><span data-stu-id="76905-112">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76905-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="76905-113">Remarks</span></span>  
 <span data-ttu-id="76905-114">A função `Last` retorna o valor final em um conjunto de dados depois que toda a classificação e filtragem tiverem sido aplicadas no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="76905-114">The `Last` function returns the final value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="76905-115">A função `Last` não pode ser usada em expressões de filtro de grupo com qualquer coisa, exceto o escopo atual (padrão).</span><span class="sxs-lookup"><span data-stu-id="76905-115">The `Last` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="76905-116">É possível usar também a função `Last` em um cabeçalho de página para retornar o último valor da coleção de `ReportItems` para uma página de modo a produzir cabeçalhos em estilo de dicionário que exibem as primeiras e as últimas entradas em uma página.</span><span class="sxs-lookup"><span data-stu-id="76905-116">You can also use `Last` in a page header to return the last value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="76905-117">O valor de *scope* deve ser uma constante de cadeia de caracteres e não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="76905-117">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="76905-118">Para agregações externas ou que não especificam outras agregações, *scope* deve se referir ao escopo atual ou a um escopo contentor.</span><span class="sxs-lookup"><span data-stu-id="76905-118">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="76905-119">Para agregações de agregações, as agregações aninhadas podem especificar um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="76905-119">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="76905-120">*Expression* pode conter chamadas para funções de agregação aninhadas com as seguintes exceções e condições:</span><span class="sxs-lookup"><span data-stu-id="76905-120">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="76905-121">*Scope* para agregações aninhadas deve ser igual ao escopo da agregação externa ou deve estar contido nela.</span><span class="sxs-lookup"><span data-stu-id="76905-121">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="76905-122">Para todos os escopos distintos na expressão, um escopo deve estar em uma relação filho com todos os outros escopos.</span><span class="sxs-lookup"><span data-stu-id="76905-122">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="76905-123">*Scope* para agregações aninhadas não pode ser o nome de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="76905-123">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="76905-124">A *expressão* não deve conter `First` funções,, `Last` `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="76905-124">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="76905-125">*Expression* não deve conter agregações aninhadas que especifiquem *recursive*.</span><span class="sxs-lookup"><span data-stu-id="76905-125">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="76905-126">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="76905-126">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="76905-127">Para obter mais informações sobre agregações recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="76905-127">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76905-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="76905-128">Example</span></span>  
 <span data-ttu-id="76905-129">O exemplo de código a seguir retorna o número do último produto no grupo `Category` de uma região de dados.</span><span class="sxs-lookup"><span data-stu-id="76905-129">The following code example returns the last product number in the `Category` group of a data region.</span></span>  
  
```  
=Last(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="76905-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="76905-130">See Also</span></span>  
 <span data-ttu-id="76905-131">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76905-131">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="76905-132">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76905-132">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="76905-133">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76905-133">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="76905-134">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="76905-134">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
