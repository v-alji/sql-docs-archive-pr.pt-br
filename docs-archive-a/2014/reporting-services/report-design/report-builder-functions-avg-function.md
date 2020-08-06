---
title: Função Avg (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f1276c4c-bb44-44c0-a1bf-386a0c340003
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfa9d3517e3b3b0c2e4e01853ffa30295ec343df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683411"
---
# <a name="avg-function-report-builder-and-ssrs"></a><span data-ttu-id="19519-102">Função Avg (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="19519-102">Avg Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="19519-103">Retorna a média de todos os valores numéricos não nulos especificados pela expressão, avaliados no escopo fornecido.</span><span class="sxs-lookup"><span data-stu-id="19519-103">Returns the average of all non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="19519-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="19519-104">Syntax</span></span>  
  
```  
  
Avg(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19519-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="19519-105">Parameters</span></span>  
 <span data-ttu-id="19519-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="19519-106">*expression*</span></span>  
 <span data-ttu-id="19519-107">(`Float`) A expressão na qual a agregação será executada.</span><span class="sxs-lookup"><span data-stu-id="19519-107">(`Float`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="19519-108">*escopo*</span><span class="sxs-lookup"><span data-stu-id="19519-108">*scope*</span></span>  
 <span data-ttu-id="19519-109">(`String`) Opcional.</span><span class="sxs-lookup"><span data-stu-id="19519-109">(`String`) Optional.</span></span> <span data-ttu-id="19519-110">O nome de um conjunto de dados, um grupo ou uma região de dados que contém os itens de relatório aos quais a função de agregação deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="19519-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="19519-111">Se *scope* não estiver especificado, será usado o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="19519-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="19519-112">*recursivos*</span><span class="sxs-lookup"><span data-stu-id="19519-112">*recursive*</span></span>  
 <span data-ttu-id="19519-113">(**Enumerated Type**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="19519-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="19519-114">`Simple` (padrão) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="19519-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="19519-115">Especifica se a agregação deve ser executada recursivamente.</span><span class="sxs-lookup"><span data-stu-id="19519-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="19519-116">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="19519-116">Return Type</span></span>  
 <span data-ttu-id="19519-117">Retorna um `Decimal` para expressões decimais e um `Double` para todas as outras expressões.</span><span class="sxs-lookup"><span data-stu-id="19519-117">Returns a `Decimal` for decimal expressions and a `Double` for all other expressions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19519-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="19519-118">Remarks</span></span>  
 <span data-ttu-id="19519-119">O conjunto de dados especificado na expressão deve ter o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="19519-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="19519-120">Para converter dados que têm vários tipos de dados numéricos no mesmo tipo de dados, use funções de conversão, como `CInt`, `CDbl` ou `CDec`.</span><span class="sxs-lookup"><span data-stu-id="19519-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="19519-121">Para obter mais informações, consulte [Funções de conversão de tipo](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="19519-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="19519-122">O valor de *scope* deve ser uma constante de cadeia de caracteres e não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="19519-122">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="19519-123">Para agregações externas ou que não especificam outras agregações, *scope* deve se referir ao escopo atual ou a um escopo contentor.</span><span class="sxs-lookup"><span data-stu-id="19519-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="19519-124">Para agregações de agregações, as agregações aninhadas podem especificar um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="19519-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="19519-125">*Expression* pode conter chamadas para funções de agregação aninhadas com as seguintes exceções e condições:</span><span class="sxs-lookup"><span data-stu-id="19519-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="19519-126">*Scope* para agregações aninhadas deve ser igual ao escopo da agregação externa ou deve estar contido nela.</span><span class="sxs-lookup"><span data-stu-id="19519-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="19519-127">Para todos os escopos distintos na expressão, um escopo deve estar em uma relação filho com todos os outros escopos.</span><span class="sxs-lookup"><span data-stu-id="19519-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="19519-128">*Scope* para agregações aninhadas não pode ser o nome de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="19519-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="19519-129">A *expressão* não deve conter `First` funções,, `Last` `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="19519-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="19519-130">*Expression* não deve conter agregações aninhadas que especifiquem *recursive*.</span><span class="sxs-lookup"><span data-stu-id="19519-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="19519-131">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="19519-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="19519-132">Para obter mais informações sobre agregações recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="19519-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19519-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="19519-133">Example</span></span>  
 <span data-ttu-id="19519-134">Os dois exemplos de código a seguir fornecem uma média de todos os valores do campo `Cost` contidos em um conjunto de dados denominado `Inventory`.</span><span class="sxs-lookup"><span data-stu-id="19519-134">The following two code examples provide an average of all values in the `Cost` field contained in a dataset named `Inventory`.</span></span>  
  
```  
=Avg(Fields!Cost.Value, "Inventory")   
  OR    
=Avg (CDbl(Fields!Cost.Value), "Inventory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="19519-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="19519-135">See Also</span></span>  
 <span data-ttu-id="19519-136">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="19519-136">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="19519-137">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="19519-137">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="19519-138">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="19519-138">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="19519-139">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="19519-139">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
