---
title: Função RunningValue (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6bee2f15-0e69-49c8-9689-b04544063b1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 168073a0409455041f4ebe3aa4c5dcfc8fa129a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573699"
---
# <a name="runningvalue-function-report-builder-and-ssrs"></a><span data-ttu-id="781ce-102">Função RunningValue (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="781ce-102">RunningValue Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="781ce-103">Retorna uma agregação contínua de todos os valores numéricos não nulos especificados pela expressão, avaliados para o escopo fornecido.</span><span class="sxs-lookup"><span data-stu-id="781ce-103">Returns a running aggregate of all non-null numeric values specified by the expression, evaluated for the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="781ce-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="781ce-104">Syntax</span></span>  
  
```  
  
RunningValue(expression, function, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="781ce-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="781ce-105">Parameters</span></span>  
 <span data-ttu-id="781ce-106">*expressão*</span><span class="sxs-lookup"><span data-stu-id="781ce-106">*expression*</span></span>  
 <span data-ttu-id="781ce-107">A expressão na qual executar a agregação, por exemplo, `[Quantity]`.</span><span class="sxs-lookup"><span data-stu-id="781ce-107">The expression on which to perform the aggregation, for example, `[Quantity]`.</span></span>  
  
 <span data-ttu-id="781ce-108">*função*</span><span class="sxs-lookup"><span data-stu-id="781ce-108">*function*</span></span>  
 <span data-ttu-id="781ce-109">(`Enum`) O nome da função de agregação a ser aplicado à expressão, por exemplo, `Sum`.</span><span class="sxs-lookup"><span data-stu-id="781ce-109">(`Enum`) The name of the aggregate function to apply to the expression, for example, `Sum`.</span></span> <span data-ttu-id="781ce-110">Essa função não pode ser `RunningValue`, `RowNumber` ou `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="781ce-110">This function cannot be `RunningValue`, `RowNumber`, or `Aggregate`.</span></span>  
  
 <span data-ttu-id="781ce-111">*escopo*</span><span class="sxs-lookup"><span data-stu-id="781ce-111">*scope*</span></span>  
 <span data-ttu-id="781ce-112">(`String`) Uma constante de cadeia de caracteres que é o nome de um conjunto de dados, região de dados ou grupo ou nulo (`Nothing` no [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), que especifica o contexto no qual avaliar a agregação.</span><span class="sxs-lookup"><span data-stu-id="781ce-112">(`String`) A string constant that is the name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the aggregation.</span></span> <span data-ttu-id="781ce-113">`Nothing` especifica o contexto mais externo, geralmente o conjunto de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="781ce-113">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="781ce-114">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="781ce-114">Return Type</span></span>  
 <span data-ttu-id="781ce-115">Determinado pela função de agregação especificada no parâmetro *function* .</span><span class="sxs-lookup"><span data-stu-id="781ce-115">Determined by the aggregate function that is specified in the *function* parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="781ce-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="781ce-116">Remarks</span></span>  
 <span data-ttu-id="781ce-117">O valor de `RunningValue` é redefinido como 0 para cada nova instância do escopo.</span><span class="sxs-lookup"><span data-stu-id="781ce-117">The value for `RunningValue` resets to 0 for each new instance of the scope.</span></span> <span data-ttu-id="781ce-118">Se um grupo for especificado, o valor em uso será redefinido quando a expressão de grupo for alterada.</span><span class="sxs-lookup"><span data-stu-id="781ce-118">If a group is specified, the running value is reset when the group expression changes.</span></span> <span data-ttu-id="781ce-119">Se uma região de dados for especificada, o valor em uso será redefinido para cada nova instância da região de dados.</span><span class="sxs-lookup"><span data-stu-id="781ce-119">If a data region is specified, the running value is reset for each new instance of the data region.</span></span> <span data-ttu-id="781ce-120">Se um conjunto de dados for especificado, o valor em uso não será redefinido em todo o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="781ce-120">If a dataset is specified, the running value is not reset throughout the entire dataset.</span></span>  
  
 <span data-ttu-id="781ce-121">`RunningValue` não pode ser usado em um filtro ou expressão de classificação.</span><span class="sxs-lookup"><span data-stu-id="781ce-121">`RunningValue` cannot be used in a filter or sort expression.</span></span>  
  
 <span data-ttu-id="781ce-122">O conjunto de dados para o qual o valor em execução é calculado deve ter o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="781ce-122">The set of data for which the running value is calculated must have the same data type.</span></span> <span data-ttu-id="781ce-123">Para converter dados que têm vários tipos de dados numéricos no mesmo tipo de dados, use funções de conversão, como `CInt`, `CDbl` ou `CDec`.</span><span class="sxs-lookup"><span data-stu-id="781ce-123">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="781ce-124">Para obter mais informações, consulte [Funções de conversão de tipo](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="781ce-124">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="781ce-125">O*Scope* não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="781ce-125">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="781ce-126">*Expression* pode conter chamadas para funções de agregação aninhadas com as seguintes exceções e condições:</span><span class="sxs-lookup"><span data-stu-id="781ce-126">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="781ce-127">O escopo para agregações aninhadas deve ser igual ao escopo da agregação externa ou deve estar contido nela.</span><span class="sxs-lookup"><span data-stu-id="781ce-127">Scope for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="781ce-128">Para todos os escopos distintos na expressão, um escopo deve estar em uma relação filho com todos os outros escopos.</span><span class="sxs-lookup"><span data-stu-id="781ce-128">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="781ce-129">O escopo para agregações aninhadas não pode ser o nome de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="781ce-129">Scope for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="781ce-130">A *expressão* não deve conter `First` funções,, `Last` `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="781ce-130">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="781ce-131">*Expression* não deve conter agregações aninhadas que especifiquem *recursive*.</span><span class="sxs-lookup"><span data-stu-id="781ce-131">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="781ce-132">Para calcular o valor em uso do número de linhas, use `RowNumber`.</span><span class="sxs-lookup"><span data-stu-id="781ce-132">To calculate the running value of the number of rows, use `RowNumber`.</span></span> <span data-ttu-id="781ce-133">Para obter mais informações, consulte [Função RowNumber &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-rownumber-function.md).</span><span class="sxs-lookup"><span data-stu-id="781ce-133">For more information, see [RowNumber Function &#40;Report Builder and SSRS&#41;](report-builder-functions-rownumber-function.md).</span></span>  
  
 <span data-ttu-id="781ce-134">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="781ce-134">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="781ce-135">Para obter mais informações sobre agregações recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="781ce-135">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="781ce-136">Exemplos</span><span class="sxs-lookup"><span data-stu-id="781ce-136">Examples</span></span>  
 <span data-ttu-id="781ce-137">O exemplo de código a seguir fornece uma soma parcial do campo denominado `Cost` no escopo mais externo que é o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="781ce-137">The following code example provides a running sum of the field named `Cost` in the outermost scope, which is the dataset.</span></span>  
  
```  
=RunningValue(Fields!Cost.Value, Sum, Nothing)  
```  
  
 <span data-ttu-id="781ce-138">O exemplo de código a seguir fornece uma soma parcial do campo denominado `Score` no conjunto de dados denominado `DataSet1`.</span><span class="sxs-lookup"><span data-stu-id="781ce-138">The following code example provides a running sum of the field named `Score` in the dataset named `DataSet1`.</span></span>  
  
```  
=RunningValue(Fields!Score.Value,sum,"DataSet1")  
```  
  
 <span data-ttu-id="781ce-139">O exemplo de código a seguir fornece uma soma parcial do campo denominado `Traffic Charges` no escopo mais externo.</span><span class="sxs-lookup"><span data-stu-id="781ce-139">The following code example provides a running sum of the field named `Traffic Charges` in the outermost scope.</span></span>  
  
```  
=RunningValue(Fields!Traffic Charges.Value, Sum, Nothing)  
```  
  
## <a name="see-also"></a><span data-ttu-id="781ce-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="781ce-140">See Also</span></span>  
 <span data-ttu-id="781ce-141">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781ce-141">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="781ce-142">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781ce-142">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="781ce-143">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="781ce-143">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="781ce-144">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="781ce-144">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
