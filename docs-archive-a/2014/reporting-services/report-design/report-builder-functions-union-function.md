---
title: Função Union (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c87e16fe-c12a-4c9d-a9df-7a94e229fd04
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c80926be53254ec512b2189c4b67e8cd5885733f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573694"
---
# <a name="union-function-report-builder-and-ssrs"></a><span data-ttu-id="e333a-102">Função Union (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e333a-102">Union Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e333a-103">Retorna a união de todos os valores numéricos não nulos especificados pela expressão, avaliados no escopo fornecido.</span><span class="sxs-lookup"><span data-stu-id="e333a-103">Returns the union of all the non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="e333a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e333a-104">Syntax</span></span>  
  
```  
  
Union(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e333a-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="e333a-105">Parameters</span></span>  
 <span data-ttu-id="e333a-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="e333a-106">*expression*</span></span>  
 <span data-ttu-id="e333a-107">(`SqlGeometry` ou `SqlGeography`) A expressão na qual executar a agregação.</span><span class="sxs-lookup"><span data-stu-id="e333a-107">(`SqlGeometry` or `SqlGeography`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="e333a-108">*escopo*</span><span class="sxs-lookup"><span data-stu-id="e333a-108">*scope*</span></span>  
 <span data-ttu-id="e333a-109">(`String`) Opcional.</span><span class="sxs-lookup"><span data-stu-id="e333a-109">(`String`) Optional.</span></span> <span data-ttu-id="e333a-110">O nome de um conjunto de dados, um grupo ou uma região de dados que contém os itens de relatório aos quais a função de agregação deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="e333a-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="e333a-111">Se *scope* não estiver especificado, será usado o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e333a-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="e333a-112">*recursivos*</span><span class="sxs-lookup"><span data-stu-id="e333a-112">*recursive*</span></span>  
 <span data-ttu-id="e333a-113">(**Enumerated Type**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="e333a-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="e333a-114">`Simple` (padrão) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="e333a-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="e333a-115">Especifica se a agregação deve ser executada recursivamente.</span><span class="sxs-lookup"><span data-stu-id="e333a-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return"></a><span data-ttu-id="e333a-116">Retorno</span><span class="sxs-lookup"><span data-stu-id="e333a-116">Return</span></span>  
 <span data-ttu-id="e333a-117">Retorna um objeto espacial, `SqlGeometry` ou `SqlGeography` , com base no tipo de expressão.</span><span class="sxs-lookup"><span data-stu-id="e333a-117">Returns a spatial object, either `SqlGeometry` or `SqlGeography`, based on the expression type.</span></span> <span data-ttu-id="e333a-118">Para obter mais informações `SqlGeometry` sobre `SqlGeography` os tipos de dados espaciais e, consulte [visão geral dos tipos de dados espaciais](../../relational-databases/spatial/spatial-data-types-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e333a-118">For more information about `SqlGeometry` and `SqlGeography` spatial data types, see [Spatial Data Types Overview](../../relational-databases/spatial/spatial-data-types-overview.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e333a-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="e333a-119">Remarks</span></span>  
 <span data-ttu-id="e333a-120">O conjunto de dados especificado na expressão deve ter o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="e333a-120">The set of data specified in the expression must have the same data type.</span></span>  
  
 <span data-ttu-id="e333a-121">O valor de *scope* deve ser uma constante de cadeia de caracteres e não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="e333a-121">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="e333a-122">Para agregações externas ou que não especificam outras agregações, *scope* deve se referir ao escopo atual ou a um escopo contentor.</span><span class="sxs-lookup"><span data-stu-id="e333a-122">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="e333a-123">Não há suporte para escopos de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="e333a-123">Dataset scopes are not supported.</span></span> <span data-ttu-id="e333a-124">Para agregações de agregações, as agregações aninhadas podem especificar um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="e333a-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="e333a-125">*Expression* pode conter chamadas para funções de agregação aninhadas com as seguintes exceções e condições:</span><span class="sxs-lookup"><span data-stu-id="e333a-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="e333a-126">*Scope* para agregações aninhadas deve ser igual ao escopo da agregação externa ou deve estar contido nela.</span><span class="sxs-lookup"><span data-stu-id="e333a-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="e333a-127">Para todos os escopos distintos na expressão, um escopo deve estar em uma relação filho com todos os outros escopos.</span><span class="sxs-lookup"><span data-stu-id="e333a-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="e333a-128">*Scope* para agregações aninhadas não pode ser o nome de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="e333a-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="e333a-129">A *expressão* não deve conter `First` funções,, `Last` `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="e333a-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="e333a-130">*Expression* não deve conter agregações aninhadas que especifiquem *recursive*.</span><span class="sxs-lookup"><span data-stu-id="e333a-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="e333a-131">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="e333a-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="e333a-132">Para obter mais informações sobre agregações recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e333a-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e333a-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e333a-133">Example</span></span>  
 <span data-ttu-id="e333a-134">A tabela a seguir mostra exemplos de expressões `SqlGeometry` e expressões de resultado `Union`, mostradas no formato WKT (Well Known Text) para dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="e333a-134">The following table shows examples of `SqlGeometry` expressions and `Union` result expression, shown in WKT (Well Known Text) format for spatial data.</span></span>  
  
|<span data-ttu-id="e333a-135">Campo com dados espaciais</span><span class="sxs-lookup"><span data-stu-id="e333a-135">Field with spatial data</span></span>|<span data-ttu-id="e333a-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e333a-136">Example</span></span>|<span data-ttu-id="e333a-137">Resultado de Union</span><span class="sxs-lookup"><span data-stu-id="e333a-137">Union result</span></span>|  
|-----------------------------|-------------|------------------|  
|<span data-ttu-id="e333a-138">[PointLocation]</span><span class="sxs-lookup"><span data-stu-id="e333a-138">[PointLocation]</span></span>|<span data-ttu-id="e333a-139">POINT(1 2)</span><span class="sxs-lookup"><span data-stu-id="e333a-139">POINT(1 2)</span></span><br /><br /> <span data-ttu-id="e333a-140">POINT(3 4)</span><span class="sxs-lookup"><span data-stu-id="e333a-140">POINT(3 4)</span></span>|<span data-ttu-id="e333a-141">MULTIPOINT((1 2), (3 4))</span><span class="sxs-lookup"><span data-stu-id="e333a-141">MULTIPOINT((1 2), (3 4))</span></span>|  
|<span data-ttu-id="e333a-142">[PathDefinition]</span><span class="sxs-lookup"><span data-stu-id="e333a-142">[PathDefinition]</span></span>|<span data-ttu-id="e333a-143">LINESTRING(1 2, 3 4)</span><span class="sxs-lookup"><span data-stu-id="e333a-143">LINESTRING(1 2, 3 4)</span></span><br /><br /> <span data-ttu-id="e333a-144">LINESTRING(5 6, 7 8)</span><span class="sxs-lookup"><span data-stu-id="e333a-144">LINESTRING(5 6, 7 8)</span></span>|<span data-ttu-id="e333a-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span><span class="sxs-lookup"><span data-stu-id="e333a-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span></span>|  
|<span data-ttu-id="e333a-146">[PolygonDefinition]</span><span class="sxs-lookup"><span data-stu-id="e333a-146">[PolygonDefinition]</span></span>|<span data-ttu-id="e333a-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span><span class="sxs-lookup"><span data-stu-id="e333a-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span></span><br /><br /> <span data-ttu-id="e333a-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span><span class="sxs-lookup"><span data-stu-id="e333a-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span></span>|<span data-ttu-id="e333a-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span><span class="sxs-lookup"><span data-stu-id="e333a-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span></span>|  
  
```  
=Union(Fields!PointLocation.Value)  
=Union(Fields!PathDefinition.Value)  
=Union(Fields!PolygonDefinition.Value, "Group1")  
```  
  
## <a name="see-also"></a><span data-ttu-id="e333a-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e333a-150">See Also</span></span>  
 <span data-ttu-id="e333a-151">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e333a-151">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e333a-152">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e333a-152">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e333a-153">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e333a-153">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e333a-154">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e333a-154">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
