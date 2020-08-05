---
title: Função VarP (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e4f86ab3-bdb3-4e4a-9a9d-7ae7abdf4dc4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 91e35b8be071a3bb46d374edce39894a6bb1f0f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573693"
---
# <a name="varp-function-report-builder-and-ssrs"></a><span data-ttu-id="c8d70-102">Função VarP (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c8d70-102">VarP Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c8d70-103">Retorna a variação da população de todos os valores numéricos não nulos especificados pela expressão, avaliados no contexto do escopo fornecido.</span><span class="sxs-lookup"><span data-stu-id="c8d70-103">Returns the population variance of all non-null numeric values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="c8d70-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c8d70-104">Syntax</span></span>  
  
```  
  
VarP(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8d70-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="c8d70-105">Parameters</span></span>  
 <span data-ttu-id="c8d70-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="c8d70-106">*expression*</span></span>  
 <span data-ttu-id="c8d70-107">(`Integer` ou `Float`) A expressão na qual executar a agregação.</span><span class="sxs-lookup"><span data-stu-id="c8d70-107">(`Integer` or `Float`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="c8d70-108">*escopo*</span><span class="sxs-lookup"><span data-stu-id="c8d70-108">*scope*</span></span>  
 <span data-ttu-id="c8d70-109">(`String`) Opcional.</span><span class="sxs-lookup"><span data-stu-id="c8d70-109">(`String`) Optional.</span></span> <span data-ttu-id="c8d70-110">O nome de um conjunto de dados, um grupo ou uma região de dados que contém os itens de relatório aos quais a função de agregação deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="c8d70-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="c8d70-111">Se *scope* não estiver especificado, será usado o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="c8d70-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="c8d70-112">*recursivos*</span><span class="sxs-lookup"><span data-stu-id="c8d70-112">*recursive*</span></span>  
 <span data-ttu-id="c8d70-113">(**Enumerated Type**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="c8d70-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="c8d70-114">`Simple` (padrão) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="c8d70-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="c8d70-115">Especifica se a agregação deve ser executada recursivamente.</span><span class="sxs-lookup"><span data-stu-id="c8d70-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="c8d70-116">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="c8d70-116">Return Type</span></span>  
 <span data-ttu-id="c8d70-117">Retorna um `Decimal` para expressões decimais e um `Double` para todas as outras expressões.</span><span class="sxs-lookup"><span data-stu-id="c8d70-117">Returns a `Decimal` for decimal expressions and a `Double` for all other expressions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8d70-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="c8d70-118">Remarks</span></span>  
 <span data-ttu-id="c8d70-119">O conjunto de dados especificado na expressão deve ter o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="c8d70-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="c8d70-120">Para converter dados que têm vários tipos de dados numéricos no mesmo tipo de dados, use funções de conversão, como `CInt`, `CDbl` ou `CDec`.</span><span class="sxs-lookup"><span data-stu-id="c8d70-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="c8d70-121">Para obter mais informações, consulte [Funções de conversão de tipo](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="c8d70-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="c8d70-122">O valor de *scope* deve ser uma constante de cadeia de caracteres e não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="c8d70-122">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="c8d70-123">Para agregações externas ou que não especificam outras agregações, *scope* deve se referir ao escopo atual ou a um escopo contentor.</span><span class="sxs-lookup"><span data-stu-id="c8d70-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="c8d70-124">Para agregações de agregações, as agregações aninhadas podem especificar um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="c8d70-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="c8d70-125">*Expression* pode conter chamadas para funções de agregação aninhadas com as seguintes exceções e condições:</span><span class="sxs-lookup"><span data-stu-id="c8d70-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="c8d70-126">*Scope* para agregações aninhadas deve ser igual ao escopo da agregação externa ou deve estar contido nela.</span><span class="sxs-lookup"><span data-stu-id="c8d70-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="c8d70-127">Para todos os escopos distintos na expressão, um escopo deve estar em uma relação filho com todos os outros escopos.</span><span class="sxs-lookup"><span data-stu-id="c8d70-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="c8d70-128">*Scope* para agregações aninhadas não pode ser o nome de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c8d70-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="c8d70-129">A *expressão* não deve conter `First` funções,, `Last` `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="c8d70-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="c8d70-130">*Expression* não deve conter agregações aninhadas que especifiquem *recursive*.</span><span class="sxs-lookup"><span data-stu-id="c8d70-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="c8d70-131">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="c8d70-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="c8d70-132">Para obter mais informações sobre agregações recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c8d70-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8d70-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c8d70-133">Example</span></span>  
 <span data-ttu-id="c8d70-134">O exemplo de código a seguir fornece uma variação da população de totais de itens de linha no grupo `Order` ou na região de dados.</span><span class="sxs-lookup"><span data-stu-id="c8d70-134">The following code example provides a population variance of line item totals in the `Order` group or data region.</span></span>  
  
```  
=VarP(Fields!LineTotal.Value, "Order")  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8d70-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8d70-135">See Also</span></span>  
 <span data-ttu-id="c8d70-136">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c8d70-136">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c8d70-137">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c8d70-137">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c8d70-138">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c8d70-138">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c8d70-139">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c8d70-139">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
